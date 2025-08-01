 ---
title: Test Reporting for Web and API Automated Testing
date: 2025-08-01T14:33:38+02:00
lastmod: 2025-08-01T14:33:38+02:00
author: Praseeda Achuthawarrier
avatar: /img/avatarnew.png
# authorlink: https://author.site
cover: /img/test-report.png
images:
 - /img/allure-report-web.png
categories:
  - QA Automation
tags:
- Test distribution
- Test strategy
# nolastmod: true
# math: true
draft: false
---

Test Reporting for Web and API Automated Testing

<!--more-->

# Test Reporting for Web and API Automated Testing

Test reporting in automation runs is critical because it transforms raw test execution into actionable insights. Without a clear and structured report, teams only see a pass/fail result, which offers little value for debugging or decision-making. A good test report highlights which scenarios passed or failed, provides step-by-step visibility, and includes context like logs, screenshots, or API responses to pinpoint the root cause quickly. It enables faster collaboration between QA and development, helps identify flaky tests or recurring failures, and ultimately improves release confidence by showing the real quality state of the application. Well-structured reporting also supports trend analysis over time, guiding teams on where to invest in test stability and product quality.

Allure Reporting provides **structured test reports** with:  
- Step-by-step execution flow  
- Nested steps for complex actions  
- Attachments for screenshots, requests, and responses  
- Filtering and grouping of test results  
- Retry visualization to handle flaky tests

I’ve used Allure in:  
- **Selenium + Java** (Web UI tests)  
- **RestAssured + Java** (API tests)  
- **HTTParty + RSpec** (Ruby API tests)

---

## Sample Allure Report

Here’s a sample visual from Allure showing **step hierarchy with attachments**:

![Sample Allure Report](/img/allure-report-web.png)

*(Replace with your actual screenshot path or hosted image link.)*

---

## 1. Steps, Nested Steps, and Attachments

- **Steps** show major actions  
- **Nested steps** break them into smaller actions  
- **Attachments** give context: screenshots for Web, requests/responses for APIs

### Java + Selenium Example

```java
import io.qameta.allure.*;

public class LoginTest {
    @Step("Login with username: {username}")
    public void login(String username, String password) {
        enterUsername(username);
        enterPassword(password);
        clickLogin();
        attachScreenshot();
    }

    @Step("Enter username")
    public void enterUsername(String username) { ... }

    @Step("Enter password")
    public void enterPassword(String password) { ... }

    public void attachScreenshot() {
        byte[] screenshot = ((TakesScreenshot)driver).getScreenshotAs(OutputType.BYTES);
        Allure.addAttachment("Screenshot", new ByteArrayInputStream(screenshot));
    }
}
```

---

## 2. RSpec + `rspec-allure-commons` for API Testing

![Allure Report for API Testing](/img/allure-report-api.png)

Use **Allure steps and attachments** for better API reporting.  
Steps and attachments can be extracted into a **utility module** for reuse.

### Utility Module

```ruby
# spec/support/allure_steps.rb
module AllureSteps
  def attach_request(request)
    Allure.add_attachment(name: "Request", source: request.to_s, type: Allure::ContentType::TXT)
  end

  def attach_response(response)
    Allure.add_attachment(name: "Response Body", source: response.body, type: Allure::ContentType::JSON)
  end

  def step(name, &block)
    Allure.step(name, &block)
  end
end
```

Include in **`spec_helper.rb`**:

```ruby
RSpec.configure do |config|
  config.include AllureSteps
  config.formatter = AllureRspecFormatter
  config.add_setting :allure, default: AllureRspec::RspecAllureCommons.new
end
```

### Example API Spec

```ruby
RSpec.describe 'User API' do
  it 'fetches user details' do
    step("Prepare request") do
      request = { url: "https://api.example.com/users/1" }
      attach_request(request)
    end

    step("Send request and validate response") do
      response = HTTParty.get("https://api.example.com/users/1")
      attach_response(response)
      expect(response.code).to eq(200)
    end
  end
end
```

**Report Output:**  
- Steps: “Prepare request” and “Send request and validate response”  
- Attachments: Request + Response JSON  

---

## 3. Automatic Retries

- Combine **Allure** with **JUnit/TestNG retry listeners** or **RSpec retry gem**  
- Retries appear in the report with all failed attempts preserved  
- Helps identify flaky steps while reducing noise

---

## 4. Key Takeaways

- **Steps and nested steps** make reports self-explanatory  
- **Attachments** provide immediate debugging context  
- **Automatic retries** improve stability insights  
- Works seamlessly for **Web UI and API testing frameworks**

Allure turns test executions into **actionable, holistic reports** that benefit both QA and development teams.

---

## References

For more details, visit the [Allure Reporting Documentation](https://allurereport.org/docs/).

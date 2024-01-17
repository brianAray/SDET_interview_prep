# Selenium Webdriver - Java
## Orientation
---
- **Selenium WebDriver Introduction**
    - Selenium is a popular open-source test automation tool for web applications
    - Selenium WebDriver is a component of Selenium that allows automation of web browser interactions
    - WebDriver uses browser-specific drivers to control browser interactions
- **Web Element**
    - A web element represents an HTML element on a web page, such as a button, input field, or dropdown
    - Web elements have properties, such as ID, name, class name, tag name, and text
    - WebDriver can locate web elements on a page using different locators, such as ID, name, class name, tag name, CSS selector, and XPath
    - Once a web element is located, WebDriver can perform actions on it, such as clicking, typing, or selecting
## Setup
---
- **WebDriver Configuration**
    - Before using WebDriver, the driver executable for the desired browser needs to be downloaded and configured
    - WebDriver can be configured using system properties, which specify the path to the driver executable and other settings
    - ```java
      import org.openqa.selenium.WebDriver;
      import org.openqa.selenium.chrome.ChromeDriver;
      
      public class WebDriverConfigurationExample {
         public static void main(String[] args) {
            
            // setting the path of the ChromeDriver executable
            System.setProperty("webdriver.chrome.driver", "/path/to/chromedriver");
            
            // creating a new instance of the ChromeDriver
            WebDriver driver = new ChromeDriver();
            
            // navigate to a website
            driver.get("https://www.example.com");
            
            // close the browser
            driver.quit();
         }
      }
- **WebDriverManager**
    - WebDriverManager is a Java library that automates the management of browser drivers for Selenium WebDriver
    - WebDriverManager can automatically download and configure the appropriate driver executable for the desired browser version and operating system
    - ```java
      import io.github.bonigarcia.wdm.WebDriverManager;
      import org.openqa.selenium.WebDriver;
      import org.openqa.selenium.chrome.ChromeDriver;
      
      public class WebDriverManagerExample {
         public static void main(String[] args) {
            
            // setting up the ChromeDriver using the WebDriverManager library
            WebDriverManager.chromedriver().setup();
            
            // creating a new instance of the ChromeDriver
            WebDriver driver = new ChromeDriver();
            
            // navigate to a website
            driver.get("https://www.example.com");
            
            // close the browser
            driver.quit();
         }
      }
## Xpath
---
- **Absolute and Relative Xpath**
    - Xpath is a language used for selecting elements from an XML or HTML document
    - Absolute Xpath specifies the complete path to an element from the root node
    - Relative Xpath specifies the path to an element from any node in the document
    - Example Absolute Xpath: `/html/body/div[2]/form/input[1]`
    - Example Relative Xpath: `//input[@name='username']`
    - ```java
      // Absolute xpath
      WebElement element1 = driver.findElement(By.xpath("/html/body/div[1]/div[2]/form/input[3]"));
      
      // Relative xpath
      WebElement element2 = driver.findElement(By.xpath("//form/input[@name='q']"));
## Locator Strategies
---
- **Locators**
    - Locators are used to identify web elements on a webpage
    - Some examples of locators are:
        - **ID**
            - Used to identify an element with a unique ID attribute
            - ```java
              WebElement element1 = driver.findElement(By.id("element-id"));
        - **Name**
            - Used to identify an element with a name attribute
            - ```java
              WebElement element2 = driver.findElement(By.name("element-name"));
        - **Class name**
            - Used to identify an element with a class attribute
            - ```java
              WebElement element3 = driver.findElement(By.className("element-class"));
        - **Tag name**
            - Used to identify an element by its tag name
            - ```java
              WebElement element4 = driver.findElement(By.tagName("element-tag"));
        - **Link text**
            - Used to identify a hyperlink element by the visible link text
            - ```java
              WebElement element5 = driver.findElement(By.linkText("element-link-text"));
        - **Partial link text**
            - Used to identify a hyperlink element by a partial match of the visible link text
            - ```java
              WebElement element6 = driver.findElement(By.partialLinkText("partial-link-text"));
        - **CSS selector**
            - Used to identify an element by its CSS selector
            - ```java
              WebElement element = driver.findElement(By.cssSelector("#header > h1 > a"));
        - **XPath**
            - Used to identify an element by its XPath
            - Examples shown above for absolute and relative xpath
## Driver Interactions
---
- **`click()`**
    - Used to simulate a click on an element on a webpage
    - ```java
      WebElement button = driver.findElement(By.id("button-id"));
      button.click();
- **`sendKeys()`**
    - Used to simulate typing into an element on a webpage
    - ```java
      WebElement textBox = driver.findElement(By.id("textbox-id"));
      textBox.sendKeys("example text");
- **Implicit Wait**
    - Implicit wait is a setting that waits for a certain amount of time when trying to find an element or elements if they are not immediately available.
    - This setting is applied to the entire lifespan of the WebDriver object and can be set 
    - Implicit wait is useful when the page takes some time to load or the web elements are not immediately visible on the page
    - ```java
      WebDriver driver = new ChromeDriver();
      driver.manage().timeouts().implicitlyWait(10, TimeUnit.SECONDS);
- **Explicit Wait**
    - Explicit wait is a dynamic wait that waits for a certain condition to occur before moving forward in the test.
    - This wait can be applied to a specific element or multiple elements, and the WebDriver will wait for a certain amount of time for that condition to be met.
    - This wait can be created using the `WebDriverWait` class and is typically combined with an expected condition to be checked.
    - ```java
      WebDriver driver = new ChromeDriver();
      WebDriverWait wait = new WebDriverWait(driver, 10);
      WebElement element = wait.until(ExpectedConditions.elementToBeClickable(By.id("someId")));
- **Fluent Wait**
    - Fluent wait is also a dynamic wait that waits for a certain condition to be met before moving forward in the test, but it provides more flexibility compared to explicit wait.
    - This wait can be created using the FluentWait class, and it allows the WebDriver to poll the web element repeatedly until the specified condition is met.
    - ```java
      WebDriver driver = new ChromeDriver();
      Wait<WebDriver> wait = new FluentWait<WebDriver>(driver)
         .withTimeout(Duration.ofSeconds(30))
         .pollingEvery(Duration.ofSeconds(5))
         .ignoring(NoSuchElementException.class);
      WebElement element = wait.until(ExpectedConditions.visibilityOfElementLocated(By.id("someId")));
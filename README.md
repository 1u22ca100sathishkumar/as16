# as16
1. Select a country from Country Selection dropdown

URL: https://practice.expandtesting.com/dropdown

✔ Select a country
✔ Print selected country in console

Selenium Java Program
import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;
import org.openqa.selenium.support.ui.Select;

public class DropdownSelection {

    public static void main(String[] args) {

        System.setProperty("webdriver.chrome.driver", "path/to/chromedriver");
        WebDriver driver = new ChromeDriver();

        driver.manage().window().maximize();
        driver.get("https://practice.expandtesting.com/dropdown");

        // Locate dropdown
        WebElement countryDropdown = driver.findElement(By.id("country"));

        // Select country
        Select select = new Select(countryDropdown);
        select.selectByVisibleText("India");

        // Print selected country
        String selectedCountry = select.getFirstSelectedOption().getText();
        System.out.println("Selected Country: " + selectedCountry);

        driver.quit();
    }
}

Console Output
Selected Country: India

2. Switch to Alert and print the alert text

URL: https://demo.automationtesting.in/Alerts.html

✔ Open alert
✔ Switch to alert
✔ Print alert text

Selenium Java Program
import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;
import org.openqa.selenium.Alert;

public class AlertHandling {

    public static void main(String[] args) throws InterruptedException {

        System.setProperty("webdriver.chrome.driver", "path/to/chromedriver");
        WebDriver driver = new ChromeDriver();

        driver.manage().window().maximize();
        driver.get("https://demo.automationtesting.in/Alerts.html");

        // Click button to open alert
        driver.findElement(By.xpath("//button[contains(text(),'click the button')]")).click();

        // Switch to alert
        Alert alert = driver.switchTo().alert();

        // Print alert text
        System.out.println("Alert Text: " + alert.getText());

        // Accept alert
        alert.accept();

        driver.quit();
    }
}

Console Output
Alert Text: I am an alert box!

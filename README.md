# git-github

selenium hanson for trendNext
package opencartsample;

import java.util.ArrayList;
import java.util.concurrent.TimeUnit;









import org.openqa.selenium.By;
import org.openqa.selenium.JavascriptExecutor;
import org.openqa.selenium.Keys;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;
import org.openqa.selenium.support.ui.Select;
import org.testng.annotations.BeforeTest;
import org.testng.annotations.Test;

public class TC_01_opencartlogin {
	// ChromeDriver = driver;
			WebDriver driver = new ChromeDriver(); 
	
		
		
		
	    

		@BeforeTest
		public void setup() throws Exception {
			// implicit wait
			driver.manage().timeouts().implicitlyWait(60, TimeUnit.SECONDS);
		}

		@Test
		public void Register() throws Exception  {
			// To set the path of the Chrome driver.
			System.setProperty("webdriver.chrome.driver",
					"C:\\Users\\NA370541\\Downloads\\chromedriver_win32\\chromedriver.exe");
			Thread.sleep(7000);
			// To launch opencart
			driver.get("http://10.207.182.108:81/opencart/");
			 // To maximize the browser
			driver.manage().window().maximize();
			//To tap on New application link
			Thread.sleep(7000);
			driver.findElement(By.xpath("//*[@class='panel-body']/ul/li[2]/a")).click();
			ArrayList<String> tabs2 = new ArrayList<String> (driver.getWindowHandles());
		    driver.switchTo().window(tabs2.get(1));
			Thread.sleep(7000);
			//To tap on My Account  
			WebElement MyAccount= driver.findElement(By.xpath("//*[@id='top']/div[1]/div[2]/ul/li[2]"));
			 MyAccount.click();
			//To tap on Login 
			 driver.findElement(By.xpath("//a[contains(text(),'Login')]")).click();
			 //To enter email and password
			 driver.findElement(By.xpath("//*[@id='input-email']")).sendKeys("email2521@gmail.com");
			 driver.findElement(By.xpath("//*[@id='input-password']")).sendKeys("Password");
			 //To tap on login button
			 driver.findElement(By.xpath("//div[@class='well']//input[@class='btn btn-primary']")).click();
			 //To tap on search baox and enter monitor and tap on enter 
			 WebElement searchtextbox=driver.findElement(By.xpath("//*[@id='search']/input[@name='search']"));
			 searchtextbox.sendKeys("monitor");
			 searchtextbox.sendKeys(Keys.ENTER);
			 Thread.sleep(5000);
			 Thread.sleep(5000);
			 //To Tap on subcategories dropdown
			 Select Subcategoriesdrpdwn=new Select(driver.findElement(By.xpath("//*[@name='category_id']")));
			 Subcategoriesdrpdwn.selectByVisibleText("      Monitors");
			 //Subcategoriesdrpdwn.selectByVisibleText("      Monitors");
			 //To check the search in subcategory dialoguebox
			 driver.findElement(By.xpath("//*[@id='content']/div[1]/div[3]/label[1]/input[@name='sub_category']"));
			 //To tap on Search button to search the product
			 driver.findElement(By.xpath("//*[@id='button-search']")).click();
			 driver.findElement(By.xpath("//*[@id='description']")).click();
			 //To tap on phones and pads button
			 driver.findElement(By.xpath("//*[@id='menu']/div[2]/ul[1]/li[6]")).click();
			 Thread.sleep(10000);
			 WebElement pricedropdown = driver.findElement(By.xpath("//*[@id='input-sort']"));
			 Thread.sleep(15000);
			 pricedropdown.click();
			 Thread.sleep(10000);
			 pricedropdown.sendKeys("Price (High > Low)");
			 Thread.sleep(7000);
			 //To tap on first product to compare with another three products
			 JavascriptExecutor je = (JavascriptExecutor) driver;
			 Thread.sleep(7000);
			 je.executeScript("window.scrollBy(0,1000)");
	         Thread.sleep(15000);
	         driver.findElement(By.xpath("//*[@id='content']/div[2]/div[1]//div[@class='button-group']/button[3]")).click();
			 Thread.sleep(7000);
			 //driver.findElement(By.xpath("//div[@class='alert alert-success alert-dismissible']//button[@class='close']")).click();
             je.executeScript("window.scrollBy(0,1000)");
             Thread.sleep(7000);
			//To tap on second product to compare with another three products
			 driver.findElement(By.xpath("//*[@id='content']/div[2]/div[2]//div[@class='button-group']/button[3]")).click();
			// driver.findElement(By.xpath("//div[@class='alert alert-success alert-dismissible']//button[@class='close']")).click();
			 Thread.sleep(7000);
			 je.executeScript("window.scrollBy(0,1000)");
			//To tap on third product to compare with another three products
			 Thread.sleep(7000);
			 driver.findElement(By.xpath("//*[@id='content']/div[2]/div[3]//div[@class='button-group']/button[3]")).click();
			 je.executeScript("window.scrollBy(0,-1000)");
			 //To tap on success banner on the top
			 Thread.sleep(7000);
			 driver.findElement(By.xpath("//div[@class='alert alert-success alert-dismissible']//button[@class='close']")).click();
			 //To tap on product compare link 
			 Thread.sleep(10000);
			 
			 driver.findElement(By.xpath("//*[@class='form-group']")).click();
			 Thread.sleep(10000);

			 //Tap on first product to view the detail of that product
			 driver.findElement(By.xpath("//*[@id='content']/table[1]/tbody[1]/tr[1]/td[2]/a")).click();
			 Thread.sleep(10000);
			 je.executeScript("window.scrollBy(0,1000)");
			 //Tap on add to cart button
			 driver.findElement(By.xpath("//*[@id='button-cart']")).click();
			 Thread.sleep(7000);
			 driver.findElement(By.xpath("//*[@id='top-links']/ul[1]/li[4]")).click();
			 Thread.sleep(7000);
			 driver.findElement(By.xpath("//*[@id='content']//div[@class='buttons clearfix']/div[2]")).click();
			 Thread.sleep(7000);
			 /*driver.findElement(By.xpath("//*[@id='input-payment-firstname']")).sendKeys("F_Name");
			 driver.findElement(By.xpath("//*[@id='input-payment-lastname']")).sendKeys("L_Name");
			 driver.findElement(By.xpath("//*[@id='input-payment-address-1']")).sendKeys("CDC2 Wipro Technologies");
			 driver.findElement(By.xpath("//*[@id='input-payment-city']")).sendKeys("Chennai");
			 driver.findElement(By.xpath("//*[@id='input-payment-postcode']")).sendKeys("600119");
			 //To select the country from dropdown
			 WebElement Countrydrpdwn = driver.findElement(By.xpath("//*[@id='input-payment-country']"));
			 Thread.sleep(15000);
			 Countrydrpdwn.click();
			 Thread.sleep(10000);
			 Countrydrpdwn.sendKeys("India");
			//To select the Region from dropdown
			 WebElement Regorstatedrpdwn = driver.findElement(By.xpath("//*[@id='input-payment-zone']"));
			 Thread.sleep(15000);
			 Regorstatedrpdwn.click();
			 Thread.sleep(10000);
			 Regorstatedrpdwn.sendKeys("Tamil Nadu");
			 //button-payment-address
			  */
			 //To Tap on continue in Billing address
			 driver.findElement(By.xpath("//*[@id='button-payment-address']")).click();
             Thread.sleep(7000);
             //To Tap on continue in Delivery-address
			 driver.findElement(By.xpath("//*[@id='button-shipping-address']")).click();
			 Thread.sleep(7000);
			 //To Tap on continue in delivery method 
             driver.findElement(By.xpath("//*[@id='button-shipping-method']")).click();
			 Thread.sleep(7000);
			/* driver.findElement(By.xpath("//*[@class='pull-right']/a[1]")).click();
			 driver.findElement(By.xpath("//*[@class='close']")).click();*/
			 //To Tap on agree in Payment method
			 driver.findElement(By.xpath("//*[@name='agree']")).click();
			 Thread.sleep(7000);
			 //To Tap on continue in payment-method
			 driver.findElement(By.xpath("//*[@id='button-payment-method']")).click();
			 Thread.sleep(7000);
			 //To Tap on confirm order in confirm order
			 driver.findElement(By.xpath("//*[@id='button-confirm']")).click();
			//To Tap on continue in button-confirm
			 driver.findElement(By.xpath("//*[@id='content']/div[1]/div[1]")).click();
			 //To tap on shopping cart
			 driver.findElement(By.xpath("//*[@id='top-links']/ul[1]/li[4]")).click();
			 Thread.sleep(7000);
			 //To tap on continue button in your store
			 driver.findElement(By.xpath("//*[@id='content']/div[1]/div[1]")).click();
			 Thread.sleep(7000);
			//To tap on My Account  
			 WebElement MyAccount1= driver.findElement(By.xpath("//*[@id='top']/div[1]/div[2]/ul/li[2]"));
			 MyAccount1.click();
			 Thread.sleep(7000);
			 //To tap on orderhistory
			 driver.findElement(By.xpath("//a[contains(text(),'Order History')]")).click();
			 Thread.sleep(7000);
			 //To tap on newsletter in thr right side
			 driver.findElement(By.xpath("//*[@id='column-right']//a[12]")).click();
			 Thread.sleep(10000);
			 je.executeScript("window.scrollBy(0,1000)");
			 Thread.sleep(10000);
			 //To tap on special in extra under footer 
			 
			 driver.findElement(By.xpath("//*[contains(text(),'Specials')]")).click();
			 Thread.sleep(7000);
			 //To tap on list view in your store
			 driver.findElement(By.xpath("//*[@id='list-view']")).click();
			//To tap on grid view in your store
			 driver.findElement(By.xpath("//*[@id='grid-view']")).click();
	}

}

public class java_class {

	public static WebDriver dr;
	public void book() throws InterruptedException
	{
		System.setProperty("webdriver.chrome.driver", "chromedriver.exe");
		WebDriver dr = new ChromeDriver();
		dr.get("https://phptravels.net/home");
		dr.manage().window().maximize();
		dr.manage().timeouts().implicitlyWait(20, TimeUnit.SECONDS);
		
		System.out.println("hotel");
		
		
		dr.findElement(By.xpath("//div[@class='dropdown dropdown-currency']/a")).click(); 
		Thread.sleep(3000);
		dr.findElement(By.xpath("//div[@class='dropdown-menu dropdown-menu-right show']/div[1]/a[4]")).click();
		Thread.sleep(3000);
		dr.findElement(By.xpath("//a[@data-name='flights']")).click();//select flights menu
		Thread.sleep(3000);
		
		
		
		
		dr.findElement(By.xpath("//div[@id='s2id_location_from']/a")).click();
		Thread.sleep(3000);
		dr.findElement(By.xpath("//div[@id='s2id_location_from']/a")).sendKeys("LAX");
		Thread.sleep(3000);
		dr.findElement(By.xpath("//div[@id='select2-drop']/ul/li[1]/div")).click();
		Thread.sleep(3000);
		
		dr.findElement(By.xpath("//div[@id='s2id_location_to']/a")).click();
		Thread.sleep(3000);
		dr.findElement(By.xpath("//div[@id='s2id_location_to']/a")).sendKeys("DFW");
		Thread.sleep(2000);
		dr.findElement(By.xpath("//div[@id='select2-drop']/ul/li[1]/div")).click();
		Thread.sleep(3000);
		
		dr.findElement(By.xpath("//input[@id='FlightsDateStart']")).click();
		
//		String exp_year= "March 2020";
//		String exp_date="16";
//		
//	
//		
//		String act_year=dr.findElement(By.xpath("//div[@id='datepickers-container']/div[1]/nav/div[2]")).getText();
//		
//		while(!exp_year.equals(act_year))
//		{
//			dr.findElement(By.xpath("")).click();
//			act_year=dr.findElement(By.xpath("//div[@id='datepickers-container']/div[1]/nav/div[2]")).getText();
//
//		}
		
		WebElement dateEle= dr.findElement(By.id("FlightsDateStart"));
		JavascriptExecutor js =(JavascriptExecutor) dr;
		js.executeScript("arguments[0].value='2020-03-20'", dateEle);

		
		Thread.sleep(2000);
		
		dr.findElement(By.xpath("//div[@class='col-xs-12 col-md-1']/button")).click(); //search
	}
}

- First run Chrome/Firefox in normal mode on docker container
```
docker run -d -p 4444:4444 -p 7900:7900 --shm-size="2g" selenium/standalone-chrome:latest
docker run -d -p 4444:4444 -p 7900:7900 --shm-size="2g" selenium/standalone-firefox:latest
```
- Run the script and observe that we can see the execution
http://localhost:7900/ works as it is a normal mode

- Running Chrome/Firefox in headless mode on docker container
http://localhost:4444/ - work as it is headless mode
Now set the Firefox Browser to run in headless mode in Selenium Automation Scripts using Firefox Options

```
    //ChromeOptions chromeOptions = new ChromeOptions();
		//chromeOptions.addArguments("--headless");
    
		FirefoxOptions firefoxOptions = new FirefoxOptions();
		firefoxOptions.addArguments("--headless");
		WebDriver driver = new RemoteWebDriver(new URL("http://localhost:4444"),firefoxOptions);
		driver.manage().window().maximize();
		driver.get("https://the-internet.herokuapp.com/");
```

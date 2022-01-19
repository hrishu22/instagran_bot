from selenium import webdriver
import time
from selenium.webdriver.support.ui import WebDriverWait

browser =  webdriver.Chrome()
browser.get("https://www.instagram.com")
time.sleep (1)
username_input = browser.find_element_by_css_selector("input[name='username']").send_keys("username")

password_input = browser.find_element_by_css_selector("input[name='password']").send_keys("password")

login_button = browser.find_element_by_xpath("//button[@type='submit']")
login_button.click()

time.sleep(2)
notNowButton = WebDriverWait(browser, 15).until(
    lambda d: d.find_element_by_xpath('//button[text()="Not Now"]'))
notNowButton.click()

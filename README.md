#
import requests
from bs4 import BeautifulSoup
from selenium import webdriver
from selenium.webdriver import ActionChains
from selenium.webdriver.support.ui import WebDriverWait

options = webdriver.ChromeOptions()
options.add_argument("-incognito")
browser = webdriver.Chrome(executable_path ='C:/Users/fatylk/Desktop/chromedriver_win32/chromedriver.exe', chrome_options=options)
browser.get('http://www.puertos.es/es-es/oceanografia/Paginas/portus.aspx')

wait = WebDriverWait (browser,40)
actions = ActionChains(browser)

#Esto funciona
boton = browser.find_element_by_xpath('//*[@id="hidemenuleft"]')
boton.click()

#Esto da error
browser.switch_to.frame('MSOPageViewerWebPart_WebPartWPQ2')
region=browser.find_element_by_xpath('//*[@id="app"]/div[4]/div/div[1]')
region.click()

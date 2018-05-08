# tm
# coding:utf-8
from selenium import webdriver


def spider():
    list1 = ["https://list.tmall.com/search_product.htm?q=%C5%AE%D7%B0&type=p&vmarket=&spm=875.7931836%2FB.a2227oh.d100&from=mallfp..pc_1_searchbutton",
             "https://list.tmall.com/search_product.htm?q=%C5%AE%D0%AC&type=p&style=&cat=all&vmarket=",
             "https://list.tmall.com/search_product.htm?q=%C4%D0%D7%B0&type=p&spm=a220m.1000858.a2227oh.d100&from=.list.pc_1_searchbutton"
             "https://list.tmall.com/search_product.htm?q=%C4%D0%D0%AC&type=p&spm=a220m.1000858.a2227oh.d100&from=.list.pc_1_searchbutton"]
    for i in list1:
        url = i
        driver = webdriver.Chrome()
        driver.get(url)
        data = driver.find_element_by_xpath('//*[@id="J_ItemList"]').text
        data2 = data.encode("utf-8")

        with open("2.txt", "a")as f:
            f.write(data2)


if __name__ == '__main__':
    spider()


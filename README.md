# RepairTheEconomist

Hello, The Economist. I am one of your readers and today I sadly find out there is a bug on the layout of your search page. I use a Macbook Pro with resolution 1280 x 800 and the displaying result is: 

![this](https://raw.githubusercontent.com/yudazilian/RepairTheEconomist/master/Problems%20Image/Screen%20Shot%202017-04-16%20at%203.18.05%20PM.png)

Therefore, I download your web page and start to debug.

The bug locates here:
    
   @media screen and (min-width:1114px){.main-content__main-column,
	.simple-header__inner{
		position:relative;
		left:17.0579%;
		max-width:48.9037%;
		margin-left:0
	}
	.main-content__clearfix--blog-post{padding:2rem 2.5em}
	.main-content__clearfix--home-page.classified-ads{padding:1.45em 3rem 2rem}
	.main-content__related-column{width:25.58685%;min-width:300px}
	.main-content__related-column>*{float:right}
	.main-content__main-column--home-page{left:0;max-width:100%}
	.main-content__related-column--home-page{width:auto}
    }
    
Please delete the **margin-left** property in the *.main-content_main-column, .simple-header__inner* selector.

Once you delete the margin-left property, the web page can display correctly on the devices which have the same screen size.

![Here](https://raw.githubusercontent.com/yudazilian/RepairTheEconomist/master/Problems%20Image/Screen%20Shot%202017-04-16%20at%2011.50.04%20PM.png)

However, after the modification, the readers with big screen,  will find out that the search results are not placed in middle correctly. Therefore, you have to add few lines of code between your link tag:
    
@media screen and (min-width: 1400px) {
	.main-content__main-column,
	.simple-header__inner{margin-left:0}
}
    
Now users who have screens that are wider than 1400 px can still enjoy original big-screen reading experience. :)

1400px is just a result of some simple experiments, you may find a better numeric value. 

Hope this can solve this web page problem on your site :)



---
title: "Hugo Tutorial"
date: 2020-01-14T13:08:12-06:00
draft: false
---

1. For Windows, download from [https://github.com/gohugoio/hugo/releases](https://github.com/gohugoio/hugo/releases)
1. Extract the zip file in any folder.
1. *(Optional)* You can add the folder path to the PATH environment variable.
	1. Click on the Windows search button and type **env**
	{{< figure src="/img/envsettings.png">}}
	2. Click the **Environment Variables...** button
	{{< figure src="/img/systemproperties.png">}}
	3. Double-click the **Path** variable *(you can also select Path and click on the Edit button)*
	{{< figure src="/img/pathfield.png">}}
	4. Add the full path of the Hugo directory (Hugo.exe). Click OK
	{{< figure src="/img/editenvvar.png">}}
1. Go to a directory where you want your blog to live. Remember that Hugo will automatically create the folder for you so you don't have to create a separate folder by yourself.
	> `hugo new site UltimateBlog`
	
	{{< figure src="/img/hugonewsite.png" caption="*You can also use Command Prompt instead of PowerShell*">}}
1. The new site **UltimateBlog** will be created with its own folder and files.
	{{< figure src="/img/newsitecreated.png" caption="At this point, you can type *hugo serve* and navigate to localhost:1313 in your browser but you will be presented with a blank page. So let's get some themes going!">}}

# THEMES

1. Open up a browser and navigate to https://themes.gohugo.io. We will be selecting the **Paper** theme but you can choose any theme you like. 
	{{< figure src="/img/themessite.png" >}}
1. Even though there is a Download button, I prefer to go to the homepage and download it from the GitHub page (usually they are hosted on GitHub). Click on the **Homepage** button.
	{{< figure src="/img/papertheme.png" >}}
1. Download the ZIP file from GitHub as shown.
	{{< figure src="/img/papergithub.png" >}}
1. You can save it anywhere you like but I prefer to download inside the themes folder of the blog.
	> ../UltimateBlog/themes
1. Unzip the folder. You can change the folder name from **hugo-paper-master** to **paper** only.

1. Inside the theme folder, you will find a file ending with a *.toml extension.
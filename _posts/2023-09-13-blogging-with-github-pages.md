---
author: Theo Okafor
description: This beginner-friendly guide compares GitHub Pages and WordPress, and provides step-by-step instructions for setting up your GitHub Pages blog, updating the Jekyll config, publishing your blog content, and routing your blog to a custom domain. Customising your blog's layouts and views is also covered for those with a technical background.
image: 
---

# Creating Your Blog with GitHub Pages For Free: A Non-Technical Guide

Are you itching to share your thoughts, ideas, or passions with the world through a blog, but don't want to deal with the complexities of web hosting and coding? Don’t worry. This beginner-friendly guide compares GitHub Pages and WordPress, and provides step-by-step instructions for setting up your GitHub Pages blog, updating the Jekyll config, publishing your blog content, and routing your blog to a custom domain. Customising your blog's layouts and views is also covered for those with a technical background.

> 📢 **Git (Version Control)** is also a part of our programme contents. Visit [**dotcampus.co**](http://dotcampus.co) to register for our **web development**, **frontend** or **backend** engineering programme.

## A Comparison of GitHub Pages and WordPress

If you're not sure whether to choose GitHub Pages or WordPress, consider your specific needs, technical expertise, and the type of blog you want to create. GitHub Pages is free, requires technical knowledge, and has limited themes and plugins, but is fast and easy to maintain. WordPress has hosting costs, is user-friendly, and has abundant themes and plugins, but requires regular updates and backups. Below is a more detailed comparison:

| Aspect                   | GitHub Pages                             | WordPress                                    |
|--------------------------|------------------------------------------|----------------------------------------------|
| **Hosting Cost**         | Free                                     | Hosting, domain, premium themes, plugins    |
| **Technical Knowledge**  | Requires technical knowledge             | User-friendly, suitable for non-technical   |
| **Customization**        | Highly customizable with static site generators or custom HTML/CSS | Highly customizable with themes and plugins |
| **Content Management**   | Manual content management through Git    | Built-in CMS for easy content management     |
| **Dynamic Content**      | Limited support for dynamic features     | Supports dynamic features through plugins   |
| **Themes and Plugins**   | Limited themes/plugins                   | Abundant themes and plugins available       |
| **Security**             | Benefits from GitHub's security measures | Vulnerable to attacks, requires security measures |
| **SEO-Friendly**         | Requires manual SEO optimization         | Built-in SEO features and plugins available |
| **User Community**       | Active developer community               | Large and active user community              |
| **Maintenance**          | Requires minimal maintenance             | Regular updates and backups required        |
| **Performance**          | Fast performance with static content     | Performance can vary, may require optimization |
| **Version Control**      | Integrated with Git for version control  | No built-in version control, relies on plugins or external systems |
| **Learning Curve**       | Learning curve for technical setup       | User-friendly interface, less technical      |

## Steps for Setting Up Your GitHub Pages Blog

### **Step 1: Setting Up GitHub**

1. **Create a GitHub Account:** If you don't already have one, sign up for a free GitHub account. This will be your blogging platform.
2. **Visit [github-pages-blog template repository](https://github.com/TheoOkafor/github-pages-blog)**
3. **Create a New Repository from the template repository:** Click on the '`Use this template`' button and select '`Create a new repository.`'
4. **Name your repository correctly**: Name it '[your-github-username.github.io](http://your-github-username.github.io/),' where 'your-github-username' is your GitHub username.
5. **Create Repository:** Click ‘`Create Repository`’ to create your repository

[![TheoOkafor-github-pages-blog-A-template-repository-for-GitHub-Pages-Blog.webm](https://icon-library.com/images/youtube-video-player-icon/youtube-video-player-icon-6.jpg) ](https://github.com/DotCampus/dotcampus.github.io/assets/31534129/9d902360-9ecf-47c9-870d-ffd8629ecb73)

### **Step 2: Update the Jekyll Config**

Here are the non-technical steps to update the Jekyll config file to your own needs:

1. Open the `_config.yml` file in the root directory of your repository.
2. Locate the settings that you want to change. The file is well-documented, so you should be able to find the settings you need to modify easily.
3. Make changes to the file using a text editor. You can customise the site title, description, and other settings.
4. Commit the changes to the repository. Make sure to add a descriptive commit message so that you can easily track your changes.
5. Wait for a few minutes for the changes to propagate to your live site. You can view your site at [your-github-username.github.io](http://your-github-username.github.io/). If the changes don't show up, try clearing your browser cache.

If you're not sure what settings to modify, you can refer to the Jekyll documentation.
Here are some of the common settings that you might want to change:

- Site title: This appears in the browser tab and in the header of your site.
- Site description: This appears in the metadata of your site and in search engine results.
- Theme: You can choose from a variety of Jekyll themes to customise the look and feel of your site.
- Navigation: You can add or remove links in the site's navigation menu.
- Social media links: You can add links to your social media profiles in the site's footer.
- Analytics: You can add tracking codes for Google Analytics or other analytics services to track your site's traffic.

> 📢 **Git (Version Control)** is also a part of our programme contents. Visit [**dotcampus.co**](http://dotcampus.co) to register for our **web development**, **frontend** or **backend** engineering programme.

### **Step 3: Publishing Your Blog Content**

1. If you did everything correctly, few minutes after creating the repository, your blog should be live on [your-github-username.github.io](http://your-github-username.github.io/) with the dummy contents from the template repository
2. Compare the dummy contents on your repository with the contents you see on [your-github-username.github.io](http://your-github-username.github.io/) to understand how to format your own content.
3. Every post files must named using the format: `YEAR-MONTH-DAY-title.md` E.g. `2023-09-13-how-to-write-a-blog.md`. *Do not use a future date.*
4. Commit your changes to GitHub. Your post will be live on '[your-github-username.github.io](http://your-github-username.github.io/)' after a few minutes.

[![publishing content video](https://icon-library.com/images/youtube-video-player-icon/youtube-video-player-icon-6.jpg)](https://github.com/DotCampus/dotcampus.github.io/assets/31534129/4c6a5b36-5941-49a2-bf4a-4b556986a45d)

### Step 4: Routing Your Blog to a Custom Domain (Optional)

To give your blog a custom domain (e.g., '[yourname.com](http://yourname.com/)'), you'll need to purchase a domain and configure it in your GitHub repository settings. GitHub provides detailed instructions for this.

1. **Purchase a Domain**: To give your blog a personalised touch, purchase a domain name from a domain registrar like Namecheap or GoDaddy. Choose a domain name that reflects your blog's identity and resonates with your audience.
2. **Configure DNS Settings**: In your domain registrar's dashboard, locate the DNS settings or domain management section. Create a new DNS record, usually an A record or a CNAME record, that points to your GitHub Pages site -  [your-github-username.github.io](http://your-github-username.github.io/). GitHub provides detailed instructions on how to configure this in your repository's settings.
3. **Update GitHub Repository Settings**: In your GitHub repository settings, scroll down to the "GitHub Pages" section. Under "Custom domain," enter your custom domain name (e.g., [www.yourblog.com](http://www.yourblog.com/)) and click "Save." GitHub will automatically configure your blog to use your custom domain.
4. **Wait for DNS Propagation**: It may take some time for the changes to propagate across the internet. Be patient; it usually takes a few hours to a day for your custom domain to start directing visitors to your blog.

### Step 5: Customising Your Blog’s Layouts and Views (Optional)

If you have a technical background and wish to customise your blog further, follow these steps to run the blog on your personal computer:

- Clone your repository
- Set up [Ruby and Jekyll](https://jekyllrb.com/docs/installation/) on your machine.
- Install Ruby and Jekyll following [the installation guide](https://jekyllrb.com/docs/installation/)
- Run `bundle install` at the root of the repository
- Run `bundle exec jekyll serve` to start the development server
- Open the local version of the blog on [http://localhost:4000](http://localhost:4000/)

That’s it! You now have your blog up and running with your custom domain. Creating and maintaining a blog has never been easier, and with GitHub and Jekyll, you can focus on sharing your content without getting bogged down by technical details.

Happy blogging!

> 📢 **Git (Version Control)** is also a part of our programme contents. Visit [**dotcampus.co**](http://dotcampus.co) to register for our **web development**, **frontend** or **backend** engineering programme.

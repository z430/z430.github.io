---
layout: post
title: Connecting Google Colab + Google Drive
--- 

When we don't have any resources to training deep learning/AI models, Google Colab seems the only solution. But, Google Colab has runtime limitation. Also, if the runtime session expired we cannot recover the trained AI model. Connecting Google Colab and Google Drive will be the solution of this problem. 

We can also load our dataset directly from Colab. Here is the step:

1. Open Google Colab and Sign In with your account
   [Google Colab] (https://colab.research.google.com)
   [<img src="/public/images/colab/colab_home.png" style="width: 800px;"/>]({{ site.baseurl }}/)
2. Create new Notebook or use your existing Notebook
3. Copy this script
   ```python
   from google.colab import drive   # import drive from google colab
   ROOT = "/content/drive/"         # default location for the drive
   drive.mount(ROOT)                # we mount the google drive at /content/drive
   ```

   Then authorize Colab access to Drive, by open the link then copy and paste the toke to the box
   [<img src="/public/images/colab/open_link.png" style="width: 800px;"/>]({{ site.baseurl }}/)

   to make sure the mount drive is correct, list all files in that directory with `%ls`
   [<img src="/public/images/colab/ls.png" style="width: 800px;"/>]({{ site.baseurl }}/)

   Here you can see that the Colab successfully mount the Drive.
   Here is my Google Drive default folder:
   [<img src="/public/images/colab/complete_ls.png" style="width: 800px;"/>]({{ site.baseurl }}/)

4. Change working directory
   If you wish to change the working directory, you can use `%cd [directory]`. 

5. That'all
   
In the Google Colab Cell, you can use linux command or using colab line magic. Colab already have autocomplete for line magic.






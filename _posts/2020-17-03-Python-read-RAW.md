---
layout: post
title: RAW Image with Python vs Adobe Lightroom
--- 

In here, I will tell you how to read RAW Image with Python so you don't have to pay Adobe Lightroom to convert your RAW Images to JPG/JPEG/PNG/other format which your device supported.

Even though the image quality may not as good as Lightroom, but you can use some enhancement Deep Learning Algorithm :). First I will tell you 2 ways (as far as I know) to read the image and convert it to JPG. Then, We will compare the RAW Image from python with Lightroom.

## 1 Using Rawpy (Libraw)

1. Install Rawpy
   ` pip install rawpy`
2. In the text editor import it
   ```python
   import rawpy
   
   image_path = '[your image path]'
   
   with rawpy.imread(raw_path) as raw:
    img = raw.postprocess(raw_config(color_format, gamma)) 
   ```
   You can visit rawpy documentation for the configuration of `color_format` and `gamma` 

3. Save the image with opencv
   ```python
   cv.imwrite('name_image.jpg', img)
   ```
   

## 2 Using Darktable-CLI
1. Install Darktable
   <https://www.darktable.org/>
2. Call Darktable-cli from python
   ```python
    subprocess.run(["darktable-cli", img_path, "--hq", "true", f"{filename}.tif", "--core", "--conf",
                    "plugins/imageio/format/tiff/bpp=16", "--configdir", f"{filename}"], stdout=devnull,
                    stderr=devnull)
    img = tifffile.imread(f"{filename}.tif")
    subprocess.run(["rm", f"{filename}.tif"])
    subprocess.run(["rm", "-rf", f"{filename}"])
    img = skimage.img_as_float32(img)
    img = (img * 255.0).astype(np.uint8)
   ```
   We convert the RAW Image to TIF to keep the image quality in 16bit

3. convert and save the image
   ```python
   cv.imwrite('name_image.jpg', img)
   ```


## Compare with Lightroom






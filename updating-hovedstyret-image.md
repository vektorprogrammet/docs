# Updating the Hovedstyret image

The Hovedstyret image must be a `.jpg` file. In the commands below, replace
`your-image.jpg` with the name of your image file.

1. From your computer, upload the new image to the server:

   ```sh
   scp ~/Downloads/your-image.jpg vektorprogrammet@146.185.181.87:/var/www/vektorprogrammet/web/images
   ```

2. Connect to the server and go to the images folder:

   ```sh
   ssh vektorprogrammet@146.185.181.87
   cd /web/images
   ```

3. Rename the current image to keep a backup, then give the new image the
   filename the website expects:

   ```sh
   mv HS_22.jpg HS_22_old.jpg
   mv your-image.jpg HS_22.jpg
   ```

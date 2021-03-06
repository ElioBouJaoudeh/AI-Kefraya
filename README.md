# Kefraya-AI

This Artificial Intelligence project was meant to detect the presence (plant) or absence (no_plant) of crops in a field using yolov3 algorithm. The user can decide whether to run the code on small or big patches: in the case of big patches, the input image is cropped into smaller patches and then merged after being tested. The accuracy of our algorithm is of 99.5% : in a picture of 3642 plants and no_plants, 3624 plants were detected 3 plants and 15 no_plants weren’t discovered.
(LINK)
The training was done with Google Colab and these are the steps to follow:
1. Prepare your dataset and label them in YOLO format using [LabelImg](https://github.com/tzutalin/labelImg). Once done, zip all the images and their corresponding label files as `images.zip`.

2. Create a folder named `yolov3` on Google Drive and upload the `images.zip` file inside it. The directory structure should look something like the following:
```
yolov3
|__images.zip
   |__ *.jpg (all image files)
   |__ *.txt (all annotation files)
```
Here’s the sample of a training data:

![MicrosoftTeams-image](https://user-images.githubusercontent.com/88712232/130237426-a5d4acf5-efbc-4ce7-859a-ae04f5525c9c.png)
![MicrosoftTeams-image (2)](https://user-images.githubusercontent.com/88712232/130237097-ebf9bbe8-0589-43fb-b042-f1248bd70f60.png)

3. Clone the repository and upload the `Train_YoloV3_Multiple.ipynb` notebook on Google Colab.(LINK)

4. Run the cells one-by-one by following instructions as stated in the notebook. For detailed explanation, refer the following [document](https://github.com/NSTiwari/YOLOv3-Custom-Object-Detection/blob/main/YOLOv3%20Custom%20Object%20Detection%20with%20Transfer%20Learning.pdf).

5. Once the training is completed, download the following files from the `yolov3` folder saved on Google Drive, onto your local machine.
   - `yolov3_training_last.weights`
   - `yolov3_testing.cfg`
   - `classes.txt`
   
6. Copy the downloaded files and save them inside the repository you had cloned on your local machine.

7. Create a new folder named `test_images` inside the repository and save some test images inside it which you'd like to test the model on.

8. Open the `testing.py` file inside the repository and edit **Line 138**  by replacing it with the directory that contains the test patches then while running the code, insert the name of the patch you want to test.

9. Test your patch using the file: `testing.py`.

## Output:
Here’s the result of the testing done on a big patch that was cropped then merged:
![Presentation1](https://user-images.githubusercontent.com/88712232/130236231-593d3c62-eca5-4ba7-8fcf-f782c17f4075.jpg)

and a quick closeup to the given image:
![MicrosoftTeams-image](https://user-images.githubusercontent.com/88712232/130236792-31f618ec-74ce-4dcb-8edd-08bdc290d360.png)

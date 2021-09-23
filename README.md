**Detect people with eye-glasses on photo**

**Algorithm:** (input image) --> (return 1 - photo satisfies properties; 0 - not satisfy)
1. Using pre-trained model count faces on photo.
	1. If no faces were found --> return 0
	2. If more than one face was found --> return 0
	3. If only one face was found --> step2
2. Check size of face using returned boxes from model
	1. Height and Width > 255 pixels --> step3
	2. Otherwise --> return 0
3#(deleted, need to improve) Crop face from image for the next step
3. Using pre-trained model to find eye-glasses on photo(worked only with folders not with single images)
	1. If returned probability of glasses > threshold --> step4
	2. Otherwise --> return 0
4. Move image to output folder

**Used models:**
1. Find glasses - [eyeglasses_classifier_lightweight](https://github.com/acheshkov/eyeglasses_classifier_lightweight)
2. Find faces - [mtccn](https://github.com/timesler/facenet-pytorch)

**Used input dataset:**
1. High quality 1024x1024 people [photo](https://github.com/NVlabs/ffhq-dataset)


**Results:**
1. With the input as a folder with ~10k images I managed to collect ~1000 photo which we detected as fully meeting the requirements.

**TO DO:**
1. Collect photo from instagram/other platforms
2. Train own model to detect glasses
3. Find optimal threshold value for detecting glasses


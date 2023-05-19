# Change-detection---Illegal-dump-detection

User Manual 

Section -1: Describes the steps to download Sentinel-2 images
Section -2: Describes the steps to run the software
Section -1
1. The following steps are to download Sentinel-2 images
Step 1. Create a User Account
Go to https://scihub.copernicus.eu/dhus/#/home
In the top-right of the web map, click the SIGN UP button.
Insert valid entries for your name, email, and location. Click register. Validate your email.
With a few clicks of the mouse, you’ve gained access to ESA’s Sentinel data.

Step 2. Select Your Area of Interest
Where is your study area?
Using the SEARCH CRITERIA text box in the top left, type in your area of interest.
In our example, we’ve typed Malta. Click Enter twice.
From here your search will yield results for all the Sentinel satellite data available.
Sentinel-1 (Synthetic Aperture Radar C-Band) swaths are depicted in red. Sentinel-2 (multi-spectral data) swaths are depicted in green.
READ MORE: What’s the difference between active and passive sensors?

Step 3. Download Sentinel Data
Now, that we have our user account created with our study area defined – all we have to do is sift through the results and download our chosen Sentinel data.
As we are working with large data sets, you will have to be patient with download speeds. It’s easy for the server to timeout during the download.
Select the product you want to download. S1A is Sentinel-1A. S2A is Sentinel-2A.

Below is the product thumbnail that has the download URL. This is what you want to clip in order to download your chosen Sentinel data.
There are 13 bands in total. Four spectral bands have a 10-meter resolution. Six bands have a 20-meter resolution. And the remaining 3 have a spatial resolution of 60 meters.
Step 4. Download Sentinel Data
	After you download Sentinel satellite data, chances are that you are going to want to display 	it in the visible spectrum. This is exactly how our eyes see objects around us.
	Each image is separated by its respective spectral band. See our table below for the spectral 	bands of Sentinel 2. Sentinel 2B will be identical to Sentinel 2A.
Step 5. Simply follow the YouTube video https://www.youtube.com/watch?v=thLDH8AZfyM to 	download sentinel images 
2. All Downloaded 10m resolution SAFE files are copied to a folder, like /opt/nfs/shared/earthobservation/Sentinel

Section -2
1. To run the pipeline of the project, open Terminal or Command Prompt where the project folder is available
2.  Pipeline of the project requires following paths 
    • Path to the SAFE files
    • Path to file contains longitude and latitude positions of dump of interest
    • Path to shape-file which helps to crop sentinel images
    • Path to folder to save results
    • Choice of method of change detection technique
3. Shape-file of Malta can be downloaded from  https://www.eea.europa.eu/data-and-maps
4. run python main.py
			--Path to the SAFE files
			--Path to file contains longitude and latitude positions of dump of interest
              --Path to shape-file which helps to crop sentinel images
              --Path to folder to save results
              -- CD Technique 
5. for example: python main.py
--path_to_SAFE_file   /opt/nfs/shared/earthobservation/Sentinel
--long_lat_values 	 opt/local/data/ckarr01/dowloads/s2cloudmask-master/list_of_long_lat1.ods 
--path_to_output 	 /opt/users/ckarr01/PycharmProjects/pipeline/results1
--path_to_shape_file    --path_to_shape_file /opt/users/ckarr01/Downloads/ffff.shp
--method_of_CD  	 CVA
5.1  --method_of_CD
    • CVA for Change Vector Analysis
    • MAD for Multivariate Alteration Detection
    • PCA_KE2ANS for PCA-KMEANS
    • SFA for Slow Feature Analysis
    • KPCAMNet for KPCA-Mnet
    • DSFANet for Deep Slow Feature Analysis
6. Finlay, results are saved in the result folder.   

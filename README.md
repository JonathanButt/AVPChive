# AVPChive
A tool to assist with importing, archiving, and retrieval of media files for video editing projects

# Requirements
* [Apache Web Server](http://httpd.apache.org/)

# Motivation
During video editing process locating a file can be difficult. I have often spent more time than I would care to admit trying to locate a file with only a vague memory of when, where or how it was created. Sometimes I need to edit files on the go, which means I need to move my project files over to my laptop. Oh no I forgot to copy over some video files and Adobe Premiere is complaining! Where did I save that file to again? That is why I developed a naming scheme and folder organization structure. Here is an example of a folder structure you may have on your machine:

* project1
* project2
* media
	* _audio
		* 2018
			* 20181223_ca_va_iphone6
				* 20181223_ca_va_iphone6_0000.mp3
				* 20181223_ca_va_iphone6_0001.mp3
				* 20181223_ca_va_iphone6_0002.mp3
	* _video
	* _photo
		* 2017
			* 20170812_us_wa_canon650d
				* 20170812_us_wa_canon650d_0000.jpg
				* 20170812_us_wa_canon650d_0001.jpg
				* 20170812_us_wa_canon650d_0002.jpg

The idea is to have a common media folder where all projects reference for their content. A master copy of the media files should exist in a separate location (e.g. cloud server) and downloaded when needed. If any file is missing due to whatever reason (e.g. deletion to save space, migration of project files without media files, etc.) your project will provide you with the name of said file which you can easily locate by looking at the name. Finally all you will need to do is go to the location where the master copy of all your files are saved in and download the appropriate files.

What I aim to do with AVPChive is to automate the importing and archival (organizing, renaming files, uploading to master database) process.

# Use Case: Importing and Archiving
1. Take audio/video/photos on a device
2. Plug device into computer
3. Access AVPChive
4. Selects option to begin importing procedure
5. User is prompted to enter the directory of the media files
6. User is prompted for the device which was used to create these files
	* If set of files were captured over multiple devices, the device name used to capture the photos will have to be manually tagged
7. User is prompted to optionally include a date the files were created on
	* If empty, dates from file meta-data will be used
	* This is in the event where the user may want to override the date with a custom date if a device may have malfunctioned during capturing the files
	* If set of files were captured over multiple days, the date of the photos will have to be manually tagged
8. User is prompted for the country and city/state where the files were captured
	* If set of files were captured over multiple locations, the country and city/state of the photos will have to be manually tagged
9. User is prompted to enter the directory to output imported files
	* Files will be organized into audio/video/photo folders
	* Within each folder will be sub-folders with the name format yyyymmdd_country_city_device
	* Within each of those folders will be the media files prefixed with the same name as the parent folder followed by a sequence number
10. User is prompted for the directory/url to upload archived files to
# Extract-text-from-image-and-audio-using-google-vision-api

We are going to see two mini projects where we will be using `Google Cloud Vision API` for extracting the text from the image and audio.
To start with we have to get an `API-key` of `Google-Cloud-Vision` in order to use their services. 
<b><h3>Step 1: </h3></b>

<h4>Setting up Your Google Platform Account </h4>
<h4><a href ="https://console.cloud.google.com/home/dashboard">Google Cloud Platform Free </a> An account is required to get an api-key.json file. </h4>
<Div><UL>
<li>	Sign-in to Google Cloud Console </li>
<li>	Click “API Manager” </li>
<li>	Click “Credentials” </li>
<li>	Click “Create Credentials” </li>
<li>	Select “Service Account Key” </li>
<li>	Under “Service Account” select “New service account” </li>
<li>	Name service (whatever you’d like) </li>
<li>	Select Role: “Project” -> “Owner” </li>
<li>	Leave “JSON” option selected </li>
<li>	Click “Create” </li>
<li>	Save generated API key file </li>
<li>	Rename file to api-key.json </li>
</ul></div>

<h3>Step 2: </h3>
Convert the Audio file to .WAV file format. We can use any online tools to do it.

<b><h3>Step 3:(For Audio to text):</h3></b>
<li>Break up the audio file into smaller parts. Google Cloud Speech API only accepts files no longer than 60 seconds. To be on safe side, either break your files in 30-seconds chunks or select audio file less than 60 seconds.</li> 

<h4>Break the large file:</h4>
<li>We can either use any online tools or we can use an open source command line library called ffmpeg. It can be downloaded from its site and install it in your machine.
Here is the command to break up the file. <br> </li>

First clean out old parts if needed via `rm -rf parts/*`
Then use the command to break the file. <br>
`ffmpeg -i source/filename.wav -f segment -segment_time 30 -c copy parts/out%09d.wav`

Where, `source/filename.wav` is the name of the input file, and `parts/out%09d.wav` is the format for output files. `%09d` indicated that the file number will be padded with 9 zeros (i.e. out000000001.wav), allowing files to be sorted alphabetically. This way ls command returns files sorted in the right order.

<b><h3>Step 3(For Image to text):</h3></b>
For Image we don’t need to do much pre-work. We have to select the image and keep them in the local directories or we have to mentioned the proper address if the location of the image is different. 

<b><h3>Step 4:</h3></b>
Install the `requirements.txt` file using pip command which contains the required libraries.<br>
`pip install -r requirements.txt`

<b><h3>Step 5: </h3></b>
Run the Code:
 For Audio to text: `python3 audio-to-text.py` <br>
 For Image to text, run the Jupyter Notebook `Image-to-text-using-google-vision-api.ipynb`

<b><h3>Step 6: </h3></b>
These two mini projects should gives an amazing result and it does recognize the words properly even from a song which is amazing. Same goes with the image-to-text project, it reads the words properly, but it is not able to format then properly which is something we have to take care. 

<h2> Special thanks to <a href = "https://github.com/akras14/speech-to-text"> Alex </a></h2>

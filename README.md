Eyetracking.py is a Python script that I was hired to write back in 2013 by a Psychology professor. He had many students who were struggling to use an eye tracker in their research. An eye tracker is a device that has an infrared light source and two infrared cameras. It attaches to a computer screen. It tracks eye movement while people view the computer screen - so you could control the mouse using your eyes, for example. 

The eye tracker unit had a built-in server - it can transmit and receive information as XML statements over TCP. We also had a Linux computer, running Windows inside a virtual machine, running eye tracking software that can also respond to xml statements over TCP. The windows software was very limited, but it was used to calibrate the eye tracker itself for the screen dimensions and resolution, and the distance between the viewer and the screen. The students simply wanted to be able to start their own python script, which would display some images on the screen. At the same time, they wanted to record the x,y coordinates of the point on the screen that the subject's eyes were looking at, measured by the camera, along with the time of each measurement. The camera made all the calculations (involving triangulation), converted the x,y units to pixels, and transmitted it all as XML. The camera simply needed to be connected to over TCP, its built-in calibration procedure started, and the XML data needed to be interpreted,  and saved to a CSV file.  The students were psychology students - they were using Python to run their experiments, but did not understand how to concurrently display images on the screen while handling the TCP connection and the XML processing. They wanted to display things on the screen using python, so they could study eye movement under different conditions, but they were struggling to connect to the camera and run their python scripts at the same time. 

This script handles the communication with the eye tracker unit over TCP/IP. The script is designed to be imported as a module into the researchers' Python code, and it makes it easier for his students to start and stop the eye tracker unit by calling start_eyetracking() and stop_eyetracking(). It uses threading to ensure the experimenter's script can continue to run after calling start_eyetracking(). It also manipulates the XML statements and writes them to an output file. By using this script, the researchers can focus on designing their own experiment, and save their results, without having to understand how the eyetracker connects and what is happening behind-the-scenes.

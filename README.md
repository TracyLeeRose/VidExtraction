Video Frame Extractor

A simple, client-side browser tool for extracting still frames from MP4 video files. This utility runs entirely in your web browser using HTML5 and JavaScript, meaning your video files are never uploaded to a server.
✨ Features
100% Client-Side: All processing is done in your browser. Your videos remain private and are never uploaded.
Frame Selection: Interactively choose the starting point in the video for frame extraction using a slider.
Bulk Extraction: Specify the exact number of frames you wish to extract, from 10 to 1,000.
Custom Filenames: Set a base name for your output files (e.g., my_video_). Frames will be sequentially numbered (e.g., my_video_001.jpg).
Native Resolution: Frames are extracted and saved at the video's original resolution for maximum quality.
Live Preview: See a preview of the video and the selected start frame directly on the page.
Progress Indicator: A progress bar shows the status of the frame extraction process.
Simple Interface: A clean and straightforward user interface for easy operation.
🚀 How to Use
Open the HTML File: Open the index.html file in a modern web browser like Chrome, Firefox, or Edge.
Load a Video: Click the "Choose File" button and select an MP4 video file from your computer.
Set Extraction Parameters:
Start Point: Once the video loads, use the "Start" slider to navigate to the point in the video where you want to begin extracting frames. The timestamp and percentage will update as you move the slider.
Number of Frames: Use the "Number of Frames" slider to select how many frames you want to save.
Base Filename: Enter a descriptive name for your image sequence in the "Base Filename" text field.
Extract Frames: Click the "Extract Frames" button.
Save Files: The tool will begin extracting the frames one by one. Your browser will prompt you to save each JPEG file. The files will typically be saved to your browser's default "Downloads" folder.
Reset: To start over with a new video, click the "Reset" button.
🛠️ How It Works
This tool leverages the capabilities of the modern web browser to process video locally.
Video Loading: When a user selects a file, it is loaded into an HTML <video> element. The application reads the video's metadata (duration, resolution) to initialize the controls.
Seeking: The application uses a JavaScript function to programmatically seek to precise timestamps within the video. To ensure accuracy, it waits for the browser to confirm that the seek operation is complete before proceeding.
Frame Rendering: For each frame, the current video image is drawn onto an offscreen HTML <canvas> element that is sized to the video's native resolution. This ensures the output quality is not limited by the size of the on-screen preview.
Downloading: The content of the offscreen canvas is converted to a JPEG image format using canvas.toDataURL(). A download is then triggered for each frame by creating an <a> link with a download attribute and programmatically clicking it. A small delay is added between each download to ensure the browser can handle the sequence of save prompts.
⚙️ Technical Notes
Frame extraction is based on a time increment calculated from an estimated frame rate (30 FPS). This method is very effective but may not perfectly align with the video's internal frame count if its frame rate is variable or significantly different.
The entire application is a single index.html file with embedded CSS and JavaScript, making it highly portable and easy to run without any build process.
Performance will vary depending on the user's computer hardware, the video's resolution, and its length.

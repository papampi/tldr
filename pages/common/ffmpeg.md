# ffmpeg

> Video conversion tool.

- Extract the sound from a video and save it as MP3:

`ffmpeg -i {{video.mp4}} -vn {{sound}}.mp3`

- Convert frames from a video or GIF into individual numbered images:

`ffmpeg -i {{video.mpg|video.gif}} {{frame_%d.png}}`

- Combine numbered images (frame_1.jpg, frame_2.jpg, etc) into a video or GIF:

`ffmpeg -i {{frame_%d.jpg}} -f image2 {{video.mpg|video.gif}}`

- Quickly extract a single frame from a video at time mm:ss and save it as a 128x128 resolution image:

`ffmpeg -ss {{mm:ss}} -i {{video.mp4}} -frames 1 -s {{128x128}} -f image2 {{image.png}}`

- Convert AVI video to MP4. AAC Audio @ 128kbit, h264 Video @ CRF 23:

`ffmpeg -i {{input_video}}.avi -codec:audio aac -b:audio 128k -codec:video libx264 -crf 23 {{output_video}}.mp4`

- Remux MKV video to MP4 without re-encoding audio or video streams:

`ffmpeg -i {{input_video}}.mkv -codec copy {{output_video}}.mp4`

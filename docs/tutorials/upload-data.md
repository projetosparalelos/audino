## Upload datapoints

The tool provides an end point to upload datapoints. You would need an API Key which can be found on the admin dashboard for all projects. To upload datapoints for a project, you would need to make a `POST` request to `/api/data` end point. API Key should be passed in `Authorization` header.

For every datapoint, we need to provide the following required information:

1. `audio_file`: The audio binary file of `mp3`, `wav` or `ogg` format along with filename.
2. `username`: The username to whom this audio needs to be assigned for annotation. It should be one of the users created.

You can also provide the following optional information:

1. `reference_transcription`: Transcription of audio for reference.
2. `is_marked_for_review`:  Whether this audio should be marked for review or not.

We provide an [example CLI script](../../example/upload_data/upload_data.py) to show how to upload the datapoints.

For example,

```sh
API_KEY=4369e45d3a94466b8fe1efb86b8a4392 python upload_data.py  --username admin --is_marked_for_review True --audio_file OSR_us_000_0010_8k.wav --host localhost --port 80 --reference_transcription "The birch canoe slid on the smooth planks. Glue the sheet to the dark blue background. It's easy to tell the depth of a well. These days a chicken leg is a rare dish. Rice is often served in round bowls. The juice of lemons makes fine punch. The box was thrown beside the parked truck. The hogs were fed chopped corn and garbage. Four hours of steady work faced us. Large size in stockings is hard to sell."
```

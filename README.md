# Share your build on RCBuild.Info

Sharing your build is easy! Heres how to do it:

1. Fork this repo by clicking the fork icon in the upper right of this window.
2. Rename the repo to something specific to you.
  1. Click settings at the right.
  2. Enter the new name in the "Repository name" field. I usually name my quads based on their frame.
  3. Click "Rename".
3. Click `build.json` and click the pencil icon at the top right of the file to edit it to include part ids for every part you have.
  1. Find the part on https://rcbuild.info/parts/supported. If its unavailble, follow the steps outlined [here](https://github.com/tannewt/rcbuild.info-part-skeleton).
  * Fill in the empty `""` next to the part category. For example, `"frame": ""` becomes `"frame": "Blackout/Super-Mini-H-Quad"` if you have a Blackout Super Mini H.
4. Commit and push your new build.json.
5. Visit `https://rcbuild.info/builds/<your github username>/<build repository name>` in another tab.

## Sharing Cleanflight PIDs and settings
To share Cleanflight settings commit your GUI backup file with the name `cleanflight_gui_backup.json` and your CLI dump with the name `cleanflight_cli_dump.txt`.

## Sharing flight videos and blackbox
To share a flight, copy `flights/template.json` to another file in that directory. For example, `<todays date in YYYYMMDD>-<flight number>.json`. Within this file:
* `hd` and `flight` are videos taken during the flight. These should be raw videos because they may be synchronized. Only URLs for YouTube are currently supported.
* `blackbox` is the blackbox file from the flight. Currently only Dropbox is supported.
* `other_quads` is an array of information about flights of other quads that happened at the same time.
  * `id` is their GitHub username / build name.
  * `flight` is the name of their flight file without the .json extension.

All of these resources except blackbox feature an `arm_time` field that should be set to the time in seconds when your quad beeped upon arming. This can be used to synchronize all of the resources together.

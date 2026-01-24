# Harmonica Video Echo Enhancement

## Source File
`/Users/mtosity/Documents/O+ Connect/VID20260124162411.mp4`

## Output File
`/Users/mtosity/Documents/O+ Connect/VID20260124162411_echo.mp4`

## Final FFmpeg Command
```bash
ffmpeg -y -i "/Users/mtosity/Documents/O+ Connect/VID20260124162411.mp4" \
  -af "aecho=0.8:0.88:80|150:0.4|0.25,aecho=0.8:0.88:90:0.3" \
  -c:v copy \
  "/Users/mtosity/Documents/O+ Connect/VID20260124162411_echo.mp4"
```

## Echo Parameters Explained
- `aecho=in_gain:out_gain:delays:decays`
- First echo: delays 80ms & 150ms, decays 0.4 & 0.25
- Second echo: delay 90ms, decay 0.3
- Video is copied without re-encoding (`-c:v copy`)

## Notes
- Tested multiple echo levels before settling on this balanced setting
- Too little: `aecho=0.8:0.88:60:0.4,aecho=0.8:0.88:100:0.27`
- Too much: `aecho=0.8:0.9:200|400:0.5|0.3,aecho=0.8:0.9:150:0.4`

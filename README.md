# HiGlass Plugins

A collection of popular / useful higlass plugins.

**Note**: This is the source code for the plugins only! You might want to check out the following repositories as well:

- HiGlass viewer: https://github.com/higlass/higlass
- HiGlass server: https://github.com/higlass/higlass-server
- HiGlass docker: https://github.com/higlass/higlass-docker

## Included tracks

- [higlass-pileup](https://github.com/higlass/higlass-pileup)
- [higlass-multivec](https://github.com/higlass/higlass-multivec)
- [higlass-labelled-points-track](https://github.com/higlass/higlass-labelled-points-track)
- [higlass-arcs](https://github.com/higlass/higlass-arcs)
- [higlass-transcripts](https://github.com/higlass/higlass-transcripts/)
- [higlass-dynseq](https://github.com/kundajelab/higlass-dynseq)

## Installation

```
npm install higlass-plugins
```

## Usage

The live scripts can be found at:

- https://unpkg.com/higlass-plugins/dist/higlass-plugins.min.js

### Client

1. Make sure you load this component prior to `hglib.js`. For example:

```
<script src="/higlass-plugins.js"></script>
<script src="hglib.js"></script>
<script>
  ...
</script>
```

2. Now, configure the track in your view config and be happy!

```
{
  "editable": true,
  "trackSourceServers": [
    "http://higlass.io/api/v1"
  ],
  "exportViewUrl": "/api/v1/viewconfs",
  "views": [
    {
      "initialXDomain": [
        0,
        100000
      ],
      "tracks": {
        "top": [
          {
            "type": "pileup",
            "options": {
              "axisPositionHorizontal": "right",
              "axisLabelFormatting": "normal",
              "showCoverage": false,
              "colorScale": [
                // A T G C N Other
                "#2c7bb6",
                "#92c5de",
                "#ffffbf",
                "#fdae61",
                "#808080",
                "#DCDCDC"
              ]
            },
            "height": 180,
            "uid": "FylkvVBTSumoJ959HT4-5A",
            "data": {
              "type": "bam",
              "url": "https://pkerp.s3.amazonaws.com/public/bamfile_test/SRR1770413.sorted.bam",
              "chromSizesUrl": "https://pkerp.s3.amazonaws.com/public/bamfile_test/GCF_000005845.2_ASM584v2_genomic.chrom.sizes"
            },
            "width": 470
          }
        ]
      },
      "layout": {
        "w": 12,
        "h": 6,
        "x": 0,
        "y": 0
      }
    }
  ]
}
```

## Support

For questions, please either open an issue or ask on the HiGlass Slack channel at http://bit.ly/higlass-slack

## Development

### Installation

```bash
$ git clone https://github.com/higlass/higlass-plugins && higlass-plugins
$ npm install
```

### Commands

**Developmental server**: `npm start`
**Production build**: `npm run build`

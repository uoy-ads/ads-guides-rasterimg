---
authors:
  - name: null
---

# 3 Archiving Raster Images

## 3.1 Deciding What to Archive

Selecting what to archive will depend on the individual work flow of which the image is a part. General guidance for the majority of cases however is to archive, where possible, the original data in an uncompressed open format.

* Digital cameras often provide limited options in terms of the files that they will produce. With images from digital photography this may entail storing either the original JPG (preferably as an uncompressed TIFF) or raw file in DNG or TIFF format.
* Images from document scanners will normally require the user to select a format to save to once the image has been scanned. With scanned images it is recommended that, prior to any processing and regardless of the final intended format, files should be saved in an open uncompressed (or lossless) format such as TIFF.
* Images created in graphics packages will require the user to select a format to save to and most packages support a wide range of formats. With files output from software such as GIS or CAD, the choice of file format will undoubtedly be more limited. In both cases an uncompressed format is preferred but, where this is not an option, files may be converted in other packages to a suitable archive format.

As highlighted in the formats table in the previous section, many files, and particularly digital photographs, contain metadata packaged within the file format that may be useful for file documentation and reuse. In most cases, where such metadata exists, it is useful to retain and archive it. 

## 3.2 Deciding How to Archive

In many cases, as outlined above, archiving digital images requires either saving directly, or converting to, a stable preservation format (preferred formats are described in the table below). Where composite images have been created in a graphics editing package (e.g. Photoshop or Photo-Paint) then, in addition to saving the final version of the file as a 'merged' or 'flattened' composite, there may be value in saving the individual components as separate archival files.  Such a strategy can also be applied to simple animated image files such as GIFs where each frame would be exported to a separate file in a preservation format.

__Significant Properties__

The significant properties of raster images are discussed in detail in the InSPECT Significant Properties Testing Report on Raster Images [@montague2009testing] but are outlined here below (and described in more detail in the previous section). 

* __Image Size__ and __Resolution__ - conversions should ensure that the original resolution and image size remains the same in the preservation file format. In addition it is important that, when converting files to a new format, lossy compression is not applied to the image.
* __Bit depth__ and __Colour space__ - converted files should ensure that the bit depth and colour space of the original image are supported in preservation formats and that images are not degraded when converted.

Although these properties are components of all image formats it is important to ensure that these properties remain the same/retain the same values when converting files to archival formats. 

In addition, embedded metadata such as EXIF and IPTC can also be seen in certain cases as a significant property of an image and, where relevant, should be preserved with the file or exported to a separate plain or delimited text or XML file to be stored alongside the image. Although it is possible to preserve JPEG EXIF within the TIFF tag structure it is better held in a separate file, avoiding the risk of loss or corruption during later migration and making the metadata more easily accessible. Extraction of EXIF fields is relatively straight forward, with a number of free tools available.

__File Formats__

The formats described in the table below are recommended for the long-term preservation of digital raster images:

```{list-table}
:header-rows: 1

* - Preservation Format
  - Requirements
* - .tif / .tiff
  - TIFF 6.0 remains widely accepted as a preservation format for digital raster images and includes support for EXIF metadata. Extensions of the format, such as TIFF/EP and GeoTIFF and equally valid preservation formats. 
* - .dng
  - As an open extension of the TIFF/EP standard with support for EXIF, IPTC and XMP metadata, the Adobe DNG format is rapidly becoming accepted as a standards for storing raw image data (primarily from digital photography).
```

Alternative files, mainly those using compression to reduce archive sizes, have been suggested and investigated recently [@gillesse2008alternative]. There may be scope to use files such as PNG and JPEG2000 as archival formats but, as these employ compression, they are not recommended within these Guides.

## 3.3 Metadata and Documentation

Metadata for raster images is discussed in detail in 'Guidelines for Handling Image Metadata' [@mwg2009guidelines] and on the JISC Digital Media page discussing 'Metadata and Digital Images'. As highlighted in the JISC Digital Media document, image metadata can cover a wide range of areas (structural, descriptive, administrative and technical metadata) and can be either embedded within the image file (e.g. in EXIF, IPTC and XMP) or stored as a separate file (database, spreadsheet or text document).

__Technical Metadata__

Embedded technical metadata, commonly in the EXIF format, generally relates to the creation of the image file and records various camera settings used in capturing the image. There has been much discussion regarding whether automatically generated metadata such as EXIF should, or should not, be considered a significant property. There are obviously scenarios where such metadata is consciously used by a data creator and inherently significant, but commonly this is not the case. There is also the potential that certain metadata elements (e.g. date), where not deliberately used and set up, can actually contain incorrect information. Embedded metadata within images has, however, become common practice and a decision should be made when converting or reproducing images as to whether this metadata should be retained. Generally, if embedded metadata is seen to be valuable, it should be preserved.

Other technical elements may be included in embedded metadata sets but are more commonly recorded as separate files (e.g. text files or spreadsheets) due to the varying requirements of each data creator and archive. Common technical metadata elements include documenting capture device information, software and editing history.

__Wider Metadata__

Other non-technical metadata elements may also be recorded and either embedded in e.g. IPTC or XML formats or recorded in separate files. Such metadata is primarily aimed at recording descriptive and administrative data and documents the image subject, creators and content. The IPTC Photo Metadata set [@iptc2010photo], created by the International Press Telecommunications Council for news and stock photography, is a good example of the range of coverage that a single standard can have and includes elements that cover the image's content, related location, subject and rights. Additionally, data creators and archives may draw upon the wide array of existing metadata standards such as [Dublin Core](https://www.dublincore.org/), [MIX](https://www.loc.gov/standards/mix//), [PREMIS](https://www.loc.gov/standards/premis/) and [ANSI/NISO Z39.87](https://www.niso.org/publications/ansiniso-z3987-2006-r2017-data-dictionary-technical-metadata-digital-still-images) and specify a set of metadata elements that work best for the images that they are creating and preserving. 

The following are suggested metadata elements and have been drawn together from the sources discussed above (namely AHDS Bitmap handbook, Metadata Working Group guidelines and Dublin Core). It is important to note that many of these elements can be applied to an entire collection (e.g. a set of photographs) and would not need to be repeated for each file.

```{list-table}
:header-rows: 1

* - Element
  - Description
* - Identifier
  - Image filename e.g. survey01.tif
* - Title / Caption
  - The title of the image or a suitable caption
* - Description
  - Description of the image
* - Creator
  - Name of image creator
* - Date
  - Date on which image was created
* - Rights
  - Details of copyright or other rights and holder details
* - Keywords
  - Keywords e.g. period, site or feature terms. Use suitable thesauri where they exist
* - Location
  - Location information for the image. Where possible use a standardised format e.g. Lat/Long or keywords from a suitable thesauri e.g. [Getty Thesaurus of Geographic Names](https://www.getty.edu/research/tools/vocabularies/tgn/index.html)
```

__Additional Basic Technical Metadata__

```{list-table}
:header-rows: 1

* - Element
  - Description
* - File Format and Version
  - e.g. TIFF 6.0
* - File Size
  - Size of the file in bytes
* - Spatial Resolution
  - The resolution of the image measured in pixels per inch (ppi)
* - Dimensions
  - Dimensions of the image in pixels e.g. 400 x 700px
* - Colour Space
  - The colour space used in the image e.g. RGB or grayscale
* - Bit Depth
  - e.g. 24bit or 8bit
* - Capture Device
  - Either the camera make and model or details of the scanner
* - Capture Software
  - Software used to capture the image (generally used for scanned images) e.g. Adobe Photoshop CS3
```

When using embedded metadata, it is important to flag up its use in any project level metadata and to also be aware of how embedded metadata is supported by files and how data migrations affect such metadata. For example, EXIF metadata is supported by JPEG and TIFF but not - at least in the same way - by JPEG2000 [@labarca2010image] and PNG formats. IPTC metadata also exists in two types (the current Photo Metadata set and the legacy IIM set) and is also supported within the XMP format.
 
## 3.4 Structuring your archive

Images should be structured logically and in a matter which suits the particular project. A file structure may reflect a specific site or feature or separate instances of fieldwork or photographic survey. 

Where embedded metadata is to be preserved, it is suggested that it be extracted and stored in a simple text or XML structure, with a text file of metadata per image. ''#image_filename#.meta'' has been suggested as a standard naming scheme, with these files stored in a "documentation" folder alongside the preserved images. Other embedded metadata, such as IPTC or XMP, might also be extracted into this structure. Alternatively, where few elements are used or deemed significant, such data may be easily stored in a spreadsheet or database.
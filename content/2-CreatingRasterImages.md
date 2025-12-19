---
authors:
  - name: null
---

# 2 Creating Raster Images

## 2.1 General Considerations

Although raster images can vary massively in terms of source and use, there are a number of features which remain constant and should be considered when creating and using such files. As with many file types, it is practically impossible to specify a precise setting for these elements and these should be considered within the context of the wider project and used at a level which is fit for purpose.

__Resolution__

Resolution essentially describes the level of detail within an image expressed as a pixel count (e.g. pixels per inch (ppi) but also dots or samples per inch (ddi/spi)). The higher the resolution, the more detail is captured in an image and, consequently, the larger the file size. Image resolution is an important consideration for all raster images and an appropriate resolution should be chosen for the task at hand. As resolution increases so does file size so it is important to balance the level of details required from an image against the size of the files created.

  
__Bit depth__

In addition to the resolution of an image, bit depth (or colour depth) refers to the level of colour information used by each pixel. Images can range in bit depth from 2 bit (i.e. black and white) through to 8 bits (usually grayscale), and 24 bits (standard colour). As with resolutions, it is important to consider the bit depth in relation to the image being created and choose one that captures the information required whilst also minimising file size.

__Colour space__

Colour space should be considered in addition to bit depth and is used to refer to the colour system or model used in an image. Common models include RGB and CMYK for colour images and bitonal and grayscale form black and white and grayscale images. In addition to ensuring that the most appropriate system is used for the image, a key distinction exists between the RGB system, which is used primarily in images destined for on screen display and the CMYK system which is used in printing. The RGB system can hold more combinations of colours than the CMYK system so it is important to be aware that, when printing, RGB based images may not print accurately. 

__Compression__

File format compression has been discussed briefly in the introductory chapter on '[Planning for the Creation of Digital Data](https://doi.org/10.5284/h0p2-5584)'. In relation to images, compression falls into either lossless type file formats (available in GIF and PNG) or lossy formats (such as JPG) in which data is discarded. A number of formats, such as TIFF and PNG, also allow data to be stored without any compression. When creating data it is important to be aware of when compression is being used (e.g. within a camera when capturing a JPG image) and the level at which this is happening. Image compression is covered in detail in 'Digital Preservation Guidance Note 5: Image Compression' produced by The National Archives (UK) (Brown 2009).

__Transparency__

Image transparency, i.e. elements of an image which are transparent, is supported in most vector formats but in only a few raster formats (e.g. TIFF, PNG and GIF). Although a minor consideration, it is important to be aware that, where elements of an image have been made transparent (either through an alpha channel or a transparent colour), such functionality may not be supported in other formats or other stages of a particular workflow. 

__Image layering__

The layering of components within an image is a common function of many popular graphics packages (e.g. Photoshop or Photo-Paint) but is not supported in raster file formats (the layers are conflated or merged from the top down). It is important to be aware that, when saving to a raster format, such layering will be lost.

__Examples__

The elements described above vary in significance depending on the type of raster image being created. For example, in the case of digital photographs, most modern cameras have the option to capture to either a raw (uncompressed) or JPG format at a range of resolutions. A decision must therefore be made by the creator as to what is most suitable for the subject. In addition, many cameras provide black and white or grayscale modes and a choice should be made as to whether these should be used at the point of capture or whether images are later converted to these modes via software. Digital cameras also generally produce images using RGB colour space so, if these are later to be incorporated into a publication, there are potential issues in reliably converting the files to CMYK format. Likewise, with document scanners, it is important to choose an appropriate resolution, bit depth and colour space for the dataset being generated. With many scanned files a later conversion is undertaken - e.g. conversion to PDF files - which often sees the data downsampled (i.e.the resolution is reduced). In such a case it is important the either the original files are both of a suitable resolution to allow such downsampling and that, where seen as significant, the original files are also maintained as the definitive versions.

In cases of data exported from vector applications (e.g. GIS or CAD screenshots) and original data created within applications such as Adobe Photoshop or Illustrator, it is often the case that such images - by virtue of being vector based - have no inherent resolution (or have varying resolution where raster files are layered). In these cases, creating a raster file will mean the fixing of the image at a set resolution and the loss of separate entities and layers in the resulting file. It is therefore important that a suitable resolution, dependant on the image's intended use, is chosen for the output file and that, where possible, the original files follow a separate preservation path where the associated functionality is seen as being worth preserving. 

When creating and working with images, users should be aware of the concept of 'generation loss' (see [Planning for the Creation of Digital Data](https://doi.org/10.5284/h0p2-5584)) in which image quality is gradually degraded through repeated editing and saving (and thus recompressing) of a lossy compressed image.

## 2.2 File Formats

The table below outlines many of the common raster image formats currently in use.

```{list-table}
:header-rows: 1

* - Format
  - Properties/Technologies
  - Description
  - Recommendations
* - .tif / .tiff
  - Uncompressed Baseline TIFF v.6
  - A de facto standard and widely used in an uncompressed form for storing archival versions of images. The TIFF format is flexible and can supports a number of options such as LZW[^1] compression, multiple pages and metadata embedding and data creators should be clear on what type they are producing. The TIFF format supports embedding of EXIF metadata as well as GeoTIFF metadata for georeferencing.
  - Generally the uncompressed baseline v.6 is seen as being the only suitable TIFF for preservation purposes although extensions such as GeoTIFF and TIFF/EP (both containing specialized metadata) are equally acceptable and based on this standard. Aside from the previously noted problems of compression, the LZW algorithm used within TIFF is based on proprietary software and files implementing this are considered unsuitable for long term preservation.
* - .png
  - [Portable Network Graphics](https://www.libpng.org/pub/png/), an ISO standard and supported by the W3C
  - Intended as a replacement for the GIF format, PNG offers 32-bit colour depth, lossless compression, support for an Alpha channel (transparency) amongst a host of other features. PNG does not, however, support standard EXIF metadata and, as the format was primarily designed for internet use, it does not support colour spaces other than RGB.
  - PNG has become the format of choice for lossless presentation. Although TIFF is the preferred format for long term storage of images, the PNG format offers a number of features and should be used in preference over the GIF format where possible e.g. where lossless compression is required. While the format offers certain advantages over JPG (e.g. less visible artefacts) it is not recommended for use with digital photographs.
* - .jpg / .jpeg
  - An ISO standard format developed by the Joint Photographic Expert Group
  - The JPG format was primarily designed for photographic or painted images with smooth varying tones. The format offers 32-bit colour depth and extremely efficient lossy compression algorithms. JPEG also allows EXIF and IPTC metadata to be embedded within the file.
  - Although JPG files are usually drastically smaller than their TIF or PNG equivalents, the use of lossy compression makes them unsuitable for long-term storage. Where compression is required, data creators are advised to use the JPEG2000 format with lossless compression.
* - .jp2 / .jpx
  - [JPEG2000](https://jpeg.org/jpeg2000/index.html), an ISO standard and an intended replacement for the JPG format.
  - The uptake of JPEG2000 has been relatively slow since its release in December 2000 with browser support still lacking. The format offers higher performance and lossless compression ratios aimed at minimising file size and compression artefacts. The format also differs from standard JPG in that it uses XML (the JPX format) to store metadata within the file and can include within this IPTC, GML and Dublin Core metadata elements
  - The format is now widely being investigated as a viable format for preservation due to its use of lossless compression and scalability. Various institutions and organisations such as the Wellcome Library [@buckley2009wellcome], the University of Connecticut [@lowe2009status] and the Digital Preservation Coalition [@buckley2008jpeg] have produced reports in the last few years that suggest JPEG2000 will become increasingly popular as a preservation format.
* - .gif
  - Graphics Interchange Format, a proprietary format developed by Compuserve
  - Widely used on the Web for both still and animated images, the GIF format offers lossless compression but with a limited palette (8 bit / 256 colours) and limited options for embedding metadata.
  - Although it has now been superseded by more up-to-date formats (e.g. PNG), the GIF format is still widely in use. It is recommended that either the PNG format is used if compression is required or TIFF for long-term storage.
* - .bmp
  - Bit-Mapped Graphics Format created and owned by Microsoft
  - Commonly used in many older Windows applications, the BMP format is similar to GIF in that it is ideally suited for simple graphics. The format does optionally incorporate compression although this is not as efficient as that of GIF. BMP has limited options for embedding metadata.
  - Not recommended as either a working format or a format for long-term storage.
* - .psd
  - Adobe Photoshop document file, a proprietary format owned by Adobe. Primarily used for creating or editing images.
  - The PSD format is highly flexible and is often touted as an 'industry standard' imaging solution. The format supports masks and layering, transparency, text and a number of other features making it an ideal format in which to create and edit images, it also supports EXIF, IPTC and XMP metadata. PSD has limited compression support and thus files tend to be large.
  - The PSD format is an ideal format in which to create and edit files but its proprietary and closed nature means that there is limited third-party support and it is unsuitable for long-term storage. Whilst copies of a file could be stored in the PSD format so that future editing (if desired) would be possible, migration of images to open uncompressed formats - i.e. TIFF- is advised for long-term accessibility. 
* - .cpt
  - Corel Photo-Paint image, a proprietary format owned by Corel. Primarily used for creating or editing images.
  - CPT is the native format of Corel's Photo-Paint software and, as the main competitor to Adobe Photoshop, provides a similarly wide range of functionality.
  - As with the PSD format, CPT is ideally suited to the creation and editing of images and, while copies may be kept in this format for possible future editing, the format is highly specific to Corel software and copies of images should be stored in uncompressed formats such as TIFF.
* - .dng
  - Adobe Digital Negative format, an open format developed by Adobe.
  - Based on (and compliant with) the TIFF/EP format, DNG is an openly documented archival format for the storage of raw files generated by digital cameras. Adobe developed DNG in the hope that it will become a single raw processing solution that enables a more efficient workflow when handling raw files from multiple camera models and manufacturers (A free converter to convert existing RAW image formats to DNG can be [downloaded from Adobe's website](https://helpx.adobe.com/uk/camera-raw/using/adobe-dng-converter.html)). The DNG format is able to read all image tagging (EXIF & IPTC) from the original RAW file and store these in the DNG image and, in addition, supports other metadata to be embedded via [XMP](https://www.adobe.com/products/xmp.html).
  - DNG is suitable for the long-term storage of image data.
* - raw (various extensions)
  - Raw bitmap files are usually vendor specific and proprietary in nature.
  - Raw files are unprocessed bitmap files in a number of different formats created directly by a digital camera (and occasionally by digital scanners). Due to the lack of standardisation it is almost impossible to characterise a raw file, many files are uncompressed but other use both lossy or lossless compression (and some allow users to select). The lack of standardisation also means that many files require specific software applications to open the files.
  - Raw formats are unsuitable for long-term storage and data creators are advised to convert such files, where possible to standard formats such as TIFF or DNG. 
```

[^1]: The Lempel-Ziv-Welch lossless data compression algorithm.

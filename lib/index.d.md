* `Options`
  * ⚠️REQUIRED to specify 1 of ⚠️
    * `maxSizeMB`
    * `maxWidthOrHeight`
  * `maxWidthOrHeight?: number`
    * compressedFile -- will scale -- / 
      * width or height < `maxWidthOrHeight` OR
      * \< maximum Canvas' size / -- supported by -- EACH browser
    * see [Caveat](/README.md#caveat)
  * `onProgress?: (progress: number) => void`
    * progress
      * == (0, 100)
  * `libURL?: string`
    * allows
      * importing script | Web Worker
  * `preserveExif?: boolean,`
    * preserve Exif metadata | JPEG image
      * _Example:_ Camera model, Focal length, etc
  * `signal?: AbortSignal,`
    * == abort / cancel the compression
  * `maxIteration?: number`
    * MAX # of iteration -- to compress the -- image
  * `exifOrientation?: number`
    * see [here](https://stackoverflow.com/a/32490603/10395024)
  * `fileType?: string`
    * fileType override
    * _Example:_ 'image/jpeg', 'image/png'
  * `initialQuality?: number`
    * == initial quality value
    * ALLOWED values `[0,1]`
  * `alwaysKeepResolution?: boolean`
    * ONLY reduce quality / keep width & height
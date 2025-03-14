ubii-processing-module-ocr
==========================

Tesseract OCR for Ubi Interact.

Documentation available `here <https://ubii-processing-module-ocr.readthedocs.io/en/latest/>`_.

Requirements
------------

-  `tesseract <https://tesseract-ocr.github.io/>`__ OCR Engine with
   appropriate language packs *(>= 4.0.0)*

-  opencv (some of the modules try to improve OCR performance with
   additional preprocessing, in the future this might become an optional
   requirement)

-  numpy

-  `tesserocr <https://github.com/sirfz/tesserocr>`__

    .. warning:: On windows ``tesserocr`` can’t be installed from PyPi.
        Windows builds for tesserocr are available for
        `some python versions <https://github.com/simonflueckiger/tesserocr-windows_build/releases>`__.
        Only python version **>=3.7 < 3.8** is supported by both
        ``tesserocr`` and the ``ubi-interact-python`` node on Windows.
        Tesseract 5.+ should be compatible with Tesseract 4.0.0 (which is
        used for the Windows builds).

Known Issues
------------

-  The processing modules which use opencv seem to sometimes randomly
   crash under Windows
-  Processing Frequency depends on the module implementation. Typically
   ``TesseractOCR_PURE`` allows for a slightly higher processing
   frequency and is run at **10fps** while the ``TesseractOCR_EAST``
   module is run at **5fps**.
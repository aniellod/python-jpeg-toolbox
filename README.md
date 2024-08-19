# The JPEG Toolbox for Python

This tool is similar to the well-known Matlab JPEG Toolbox. It allows to read and write JPEG low level information as, for example, the DCT coefficients. This project is in development and it is an unstable version. Please use it carefully.

NOTE: Currently, python-jpeg-toolbox only works on Linux.

## Install

```bash
pip3 install git+https://github.com/aniellod/python-jpeg-toolbox --user
```

## Uninstall
```bash
pip3 uninstall jpeg-toolbox
```

## Reading JPEG data

In this exaple we read the JPEG data: Huffman tables, quantization tables, the DCT coefficients, etc.  

```bash
python3
>>> import jpeg_toolbox
>>> from pprint import pprint
>>> img = jpeg_toolbox.load('lena.jpg')
>>> pprint(img)
{'ac_huff_tables': [{'counts': array([0., 1., 3., 2., 4., 3., 5., 6., 3., 7., 3., 3., 3., 1., 5., 9.]),
                     'symbols': array([  1.,   2.,   3.,  17.,   0.,   4.,   5.,  18.,  33.,  49.,   6.,
        65.,  81.,   7.,  19.,  34.,  97., 113.,  20.,  50., 129., 145.,
       161., 240.,   8., 177., 193.,  21.,  35.,  66.,  82., 209., 225.,
       241.,  22.,  51.,  98.,  36., 114., 130.,  67., 146., 162.,  23.,
         9.,  37.,  38.,  68., 178.,  52.,  83.,  84.,  99., 100., 115.,
       131., 194., 210.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,
         0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,
         0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,
         0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,
         0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,
         0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,
         0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,
         0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,
         0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,
         0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,
         0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,
         0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,
         0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,
         0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,
         0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,
         0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,
         0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,
         0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,
         0.,   0.,   0.])},
                    {'counts': array([0., 1., 3., 2., 4., 3., 6., 6., 3., 0., 2., 2., 1., 4., 1., 5.]),
                     'symbols': array([  1.,   0.,   2.,  17.,   3.,  33.,   4.,  18.,  49.,  65.,   5.,
        81., 240.,  19.,  34.,  97., 113., 129., 177.,  50., 145., 161.,
       193., 209., 225.,  20.,  35., 241.,   6.,  66.,  51.,  82.,  36.,
        21.,  98., 114., 162.,  67.,  22.,  52.,  83., 178., 226.,   0.,
         0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,
         0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,
         0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,
         0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,
         0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,
         0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,
         0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,
         0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,
         0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,
         0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,
         0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,
         0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,
         0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,
         0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,
         0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,
         0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,
         0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,
         0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,
         0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,   0.,
         0.,   0.,   0.])}],
 'coef_arrays': [array([[86.,  2.,  2., ...,  0., -1.,  0.],
       [ 4.,  0.,  0., ..., -1.,  0., -1.],
       [-3.,  0., -1., ...,  0.,  0.,  0.],
       ...,
       [ 1.,  0.,  0., ...,  0.,  0.,  0.],
       [ 0.,  0.,  0., ...,  0.,  0.,  0.],
       [ 0.,  0.,  0., ...,  0.,  0.,  0.]]),
                 array([[-60.,   3.,   0., ...,   0.,   0.,   0.],
       [  4.,   0.,   0., ...,   0.,   0.,   0.],
       [ -1.,   0.,   0., ...,   0.,   0.,   0.],
       ...,
       [  0.,   0.,   0., ...,   0.,   0.,   0.],
       [  0.,   0.,   0., ...,   0.,   0.,   0.],
       [  0.,   0.,   0., ...,   0.,   0.,   0.]]),
                 array([[124.,  -3.,   1., ...,   0.,   0.,   0.],
       [ -3.,   0.,   0., ...,   0.,   0.,   0.],
       [  1.,   0.,   0., ...,   0.,   0.,   0.],
       ...,
       [  0.,   0.,   0., ...,   0.,   0.,   0.],
       [  0.,   0.,   0., ...,   0.,   0.,   0.],
       [  0.,   0.,   0., ...,   0.,   0.,   0.]])],
 'comp_info': [{'ac_tbl_no': 0,
                'component_id': 1,
                'dc_tbl_no': 0,
                'h_samp_factor': 1,
                'quant_tbl_no': 0,
                'v_samp_factor': 1},
               {'ac_tbl_no': 1,
                'component_id': 2,
                'dc_tbl_no': 1,
                'h_samp_factor': 1,
                'quant_tbl_no': 1,
                'v_samp_factor': 1},
               {'ac_tbl_no': 1,
                'component_id': 3,
                'dc_tbl_no': 1,
                'h_samp_factor': 1,
                'quant_tbl_no': 1,
                'v_samp_factor': 1}],
 'dc_huff_tables': [{'counts': array([0., 1., 5., 1., 1., 1., 1., 0., 0., 0., 0., 0., 0., 0., 0., 0.]),
                     'symbols': array([5., 3., 4., 6., 7., 8., 2., 1., 0., 9., 0., 0., 0., 0., 0., 0., 0.,
       0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0.,
       0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0.,
       0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0.,
       0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0.,
       0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0.,
       0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0.,
       0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0.,
       0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0.,
       0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0.,
       0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0.,
       0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0.,
       0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0.,
       0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0.,
       0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0.,
       0.])},
                    {'counts': array([0., 2., 3., 1., 1., 1., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0.]),
                     'symbols': array([2., 3., 1., 4., 5., 6., 0., 7., 0., 0., 0., 0., 0., 0., 0., 0., 0.,
       0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0.,
       0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0.,
       0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0.,
       0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0.,
       0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0.,
       0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0.,
       0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0.,
       0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0.,
       0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0.,
       0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0.,
       0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0.,
       0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0.,
       0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0.,
       0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0.,
       0.])}],
 'image_color_space': 2,
 'image_components': 3,
 'image_height': 512,
 'image_width': 512,
 'jpeg_color_space': 3,
 'jpeg_components': 3,
 'progressive_mode': 0,
 'quant_tables': array([[[ 3.,  2.,  2.,  3.,  4.,  6.,  8., 10.],
        [ 2.,  2.,  2.,  3.,  4.,  9., 10.,  9.],
        [ 2.,  2.,  3.,  4.,  6.,  9., 11.,  9.],
        [ 2.,  3.,  4.,  5.,  8., 14., 13., 10.],
        [ 3.,  4.,  6.,  9., 11., 17., 16., 12.],
        [ 4.,  6.,  9., 10., 13., 17., 18., 15.],
        [ 8., 10., 12., 14., 16., 19., 19., 16.],
        [12., 15., 15., 16., 18., 16., 16., 16.]],

       [[ 3.,  3.,  4.,  8., 16., 16., 16., 16.],
        [ 3.,  3.,  4., 11., 16., 16., 16., 16.],
        [ 4.,  4.,  9., 16., 16., 16., 16., 16.],
        [ 8., 11., 16., 16., 16., 16., 16., 16.],
        [16., 16., 16., 16., 16., 16., 16., 16.],
        [16., 16., 16., 16., 16., 16., 16., 16.],
        [16., 16., 16., 16., 16., 16., 16., 16.],
        [16., 16., 16., 16., 16., 16., 16., 16.]]])}


```

## Writing JPEG data
In this example we modify a DCT coefficient. 

```bash
python3
>>> import jpeg_toolbox
>>> img = jpeg_toolbox.load('lena.jpg')
>>> img["coef_arrays"][0][0][0] = 85
>>> jpeg_toolbox.save(img, 'lena2.jpg')
```



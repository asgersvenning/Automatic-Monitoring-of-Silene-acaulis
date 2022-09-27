Metadata and Data Preprocessing
================
Author: Asger Svenning<br>
Date: 2022-09-27<br>
<h1>
Table of Contents
</h1>

-   <a href="#1-data-file-path-indexing"
    id="toc-1-data-file-path-indexing">1 Data file path indexing</a>
    -   <a href="#11-image-metadata" id="toc-11-image-metadata">1.1 Image
        metadata</a>
-   <a href="#2-metadata-overview" id="toc-2-metadata-overview">2 Metadata
    overview</a>

# 1 Data file path indexing

In order to construct a reproducible, first we must index the metadata
and data filepaths. This can be done using the base *R* functions
`list.dir` and `list.files`.

<table class="table" style="margin-left: auto; margin-right: auto;">
<caption>

Table 1.1: Filetype Counts in the Raw File Index

</caption>
<thead>
<tr>
<th style="empty-cells: hide;border-bottom:hidden;" colspan="1">
</th>
<th style="border-bottom:hidden;padding-bottom:0; padding-left:3px;padding-right:3px;text-align: center; font-weight: bold; " colspan="3">

<div style="border-bottom: 1px solid #ddd; padding-bottom: 5px; ">

Subdirectory

</div>

</th>
</tr>
<tr>
<th style="text-align:center;font-weight: normal;">

<b>Filetype</b>

</th>
<th style="text-align:center;font-weight: normal;">

NARS-31

</th>
<th style="text-align:center;font-weight: normal;">

NARS-42

</th>
<th style="text-align:center;font-weight: normal;">

Root

</th>
</tr>
</thead>
<tbody>
<tr>
<td style="text-align:center;font-weight: bold;">

csv

</td>
<td style="text-align:center;width: 3cm; ">

0

</td>
<td style="text-align:center;width: 3cm; ">

0

</td>
<td style="text-align:center;width: 3cm; ">

32

</td>
</tr>
<tr>
<td style="text-align:center;font-weight: bold;">

JPG

</td>
<td style="text-align:center;width: 3cm; ">

89

</td>
<td style="text-align:center;width: 3cm; ">

76

</td>
<td style="text-align:center;width: 3cm; ">

0

</td>
</tr>
</tbody>
</table>

## 1.1 Image metadata

Next I will attempt to extract the file metadata using the R package
`exifr` which is a R wrapper around the file metadata software
`exiftools`. Using this tool it is possible to extract the file metadata
tags, particularly of interest here is the “CreateDate” tag, which
contains the date and time of when the photo was taken. Using this it is
possible to obtain the chronology of the image series:

![](readme_files/chunk_figures/unnamed-chunk-3-1.png)<!-- -->

# 2 Metadata overview

Since I don’t have all the files yet I cannot disaggregate flowering
phenology classes over time, however I can disagreggate over image
series.

<table class="table table-condensed" style="margin-left: auto; margin-right: auto;">
<caption>

Table 2.1: Class Counts in Image Series

</caption>
<thead>
<tr>
<th style="text-align:left;">

series

</th>
<th style="text-align:right;">

Bud

</th>
<th style="text-align:right;">

Flower

</th>
<th style="text-align:right;">

Gone

</th>
<th style="text-align:right;">

Immature

</th>
<th style="text-align:right;">

Mature

</th>
<th style="text-align:right;">

Withered

</th>
<th style="text-align:right;">

NA

</th>
</tr>
</thead>
<tbody>
<tr>
<td style="text-align:left;">

BJOR-01-A-2019

</td>
<td style="text-align:right;">

745

</td>
<td style="text-align:right;">

2268

</td>
<td style="text-align:right;">

51

</td>
<td style="text-align:right;">

98

</td>
<td style="text-align:right;">

1

</td>
<td style="text-align:right;">

1979

</td>
<td style="text-align:right;">

0

</td>
</tr>
<tr>
<td style="text-align:left;">

BJOR-03-A-2019

</td>
<td style="text-align:right;">

1482

</td>
<td style="text-align:right;">

1327

</td>
<td style="text-align:right;">

213

</td>
<td style="text-align:right;">

136

</td>
<td style="text-align:right;">

2

</td>
<td style="text-align:right;">

1382

</td>
<td style="text-align:right;">

0

</td>
</tr>
<tr>
<td style="text-align:left;">

BJOR-04-A-2019

</td>
<td style="text-align:right;">

1684

</td>
<td style="text-align:right;">

3309

</td>
<td style="text-align:right;">

256

</td>
<td style="text-align:right;">

96

</td>
<td style="text-align:right;">

5

</td>
<td style="text-align:right;">

5321

</td>
<td style="text-align:right;">

0

</td>
</tr>
<tr>
<td style="text-align:left;">

BJOR-05-A-2019

</td>
<td style="text-align:right;">

672

</td>
<td style="text-align:right;">

266

</td>
<td style="text-align:right;">

736

</td>
<td style="text-align:right;">

57

</td>
<td style="text-align:right;">

0

</td>
<td style="text-align:right;">

667

</td>
<td style="text-align:right;">

0

</td>
</tr>
<tr>
<td style="text-align:left;">

BJOR-09-A-2019

</td>
<td style="text-align:right;">

478

</td>
<td style="text-align:right;">

2528

</td>
<td style="text-align:right;">

0

</td>
<td style="text-align:right;">

2700

</td>
<td style="text-align:right;">

0

</td>
<td style="text-align:right;">

12585

</td>
<td style="text-align:right;">

3

</td>
</tr>
<tr>
<td style="text-align:left;">

BJOR-09-B-2019

</td>
<td style="text-align:right;">

2

</td>
<td style="text-align:right;">

641

</td>
<td style="text-align:right;">

1

</td>
<td style="text-align:right;">

171

</td>
<td style="text-align:right;">

0

</td>
<td style="text-align:right;">

2867

</td>
<td style="text-align:right;">

38

</td>
</tr>
<tr>
<td style="text-align:left;">

BJOR-11-A-2019

</td>
<td style="text-align:right;">

406

</td>
<td style="text-align:right;">

656

</td>
<td style="text-align:right;">

29

</td>
<td style="text-align:right;">

62

</td>
<td style="text-align:right;">

0

</td>
<td style="text-align:right;">

971

</td>
<td style="text-align:right;">

0

</td>
</tr>
<tr>
<td style="text-align:left;">

BJOR-11-B-2019

</td>
<td style="text-align:right;">

1226

</td>
<td style="text-align:right;">

2672

</td>
<td style="text-align:right;">

134

</td>
<td style="text-align:right;">

236

</td>
<td style="text-align:right;">

16

</td>
<td style="text-align:right;">

3960

</td>
<td style="text-align:right;">

0

</td>
</tr>
<tr>
<td style="text-align:left;">

BJOR-13-A-2019

</td>
<td style="text-align:right;">

1004

</td>
<td style="text-align:right;">

2672

</td>
<td style="text-align:right;">

887

</td>
<td style="text-align:right;">

4034

</td>
<td style="text-align:right;">

0

</td>
<td style="text-align:right;">

9142

</td>
<td style="text-align:right;">

2

</td>
</tr>
<tr>
<td style="text-align:left;">

BJOR-13-B-2019

</td>
<td style="text-align:right;">

1

</td>
<td style="text-align:right;">

564

</td>
<td style="text-align:right;">

467

</td>
<td style="text-align:right;">

663

</td>
<td style="text-align:right;">

0

</td>
<td style="text-align:right;">

1415

</td>
<td style="text-align:right;">

48

</td>
</tr>
<tr>
<td style="text-align:left;">

BJOR-16-A-2019

</td>
<td style="text-align:right;">

2982

</td>
<td style="text-align:right;">

3053

</td>
<td style="text-align:right;">

2902

</td>
<td style="text-align:right;">

907

</td>
<td style="text-align:right;">

0

</td>
<td style="text-align:right;">

5458

</td>
<td style="text-align:right;">

16

</td>
</tr>
<tr>
<td style="text-align:left;">

NARS-04-A-2019

</td>
<td style="text-align:right;">

84

</td>
<td style="text-align:right;">

110

</td>
<td style="text-align:right;">

268

</td>
<td style="text-align:right;">

155

</td>
<td style="text-align:right;">

87

</td>
<td style="text-align:right;">

211

</td>
<td style="text-align:right;">

111

</td>
</tr>
<tr>
<td style="text-align:left;">

NARS-05-A-2019

</td>
<td style="text-align:right;">

55

</td>
<td style="text-align:right;">

43

</td>
<td style="text-align:right;">

0

</td>
<td style="text-align:right;">

0

</td>
<td style="text-align:right;">

0

</td>
<td style="text-align:right;">

692

</td>
<td style="text-align:right;">

146

</td>
</tr>
<tr>
<td style="text-align:left;">

NARS-14-A-2019

</td>
<td style="text-align:right;">

9561

</td>
<td style="text-align:right;">

36104

</td>
<td style="text-align:right;">

41830

</td>
<td style="text-align:right;">

7882

</td>
<td style="text-align:right;">

6900

</td>
<td style="text-align:right;">

265181

</td>
<td style="text-align:right;">

36

</td>
</tr>
<tr>
<td style="text-align:left;">

NARS-20-A-2019

</td>
<td style="text-align:right;">

1627

</td>
<td style="text-align:right;">

2074

</td>
<td style="text-align:right;">

1308

</td>
<td style="text-align:right;">

985

</td>
<td style="text-align:right;">

336

</td>
<td style="text-align:right;">

9522

</td>
<td style="text-align:right;">

30

</td>
</tr>
<tr>
<td style="text-align:left;">

NARS-20-B-2019

</td>
<td style="text-align:right;">

374

</td>
<td style="text-align:right;">

521

</td>
<td style="text-align:right;">

164

</td>
<td style="text-align:right;">

310

</td>
<td style="text-align:right;">

103

</td>
<td style="text-align:right;">

2041

</td>
<td style="text-align:right;">

33

</td>
</tr>
<tr>
<td style="text-align:left;">

NARS-20-C-2019

</td>
<td style="text-align:right;">

942

</td>
<td style="text-align:right;">

1332

</td>
<td style="text-align:right;">

289

</td>
<td style="text-align:right;">

582

</td>
<td style="text-align:right;">

234

</td>
<td style="text-align:right;">

5672

</td>
<td style="text-align:right;">

33

</td>
</tr>
<tr>
<td style="text-align:left;">

NARS-21-A-2019

</td>
<td style="text-align:right;">

3021

</td>
<td style="text-align:right;">

4750

</td>
<td style="text-align:right;">

854

</td>
<td style="text-align:right;">

849

</td>
<td style="text-align:right;">

1083

</td>
<td style="text-align:right;">

28898

</td>
<td style="text-align:right;">

16

</td>
</tr>
<tr>
<td style="text-align:left;">

NARS-21-B-2019

</td>
<td style="text-align:right;">

252

</td>
<td style="text-align:right;">

80

</td>
<td style="text-align:right;">

39

</td>
<td style="text-align:right;">

16

</td>
<td style="text-align:right;">

1

</td>
<td style="text-align:right;">

230

</td>
<td style="text-align:right;">

43

</td>
</tr>
<tr>
<td style="text-align:left;">

NARS-22-A-2019

</td>
<td style="text-align:right;">

2531

</td>
<td style="text-align:right;">

5516

</td>
<td style="text-align:right;">

3060

</td>
<td style="text-align:right;">

1863

</td>
<td style="text-align:right;">

1644

</td>
<td style="text-align:right;">

35790

</td>
<td style="text-align:right;">

19

</td>
</tr>
<tr>
<td style="text-align:left;">

NARS-24-A-2019

</td>
<td style="text-align:right;">

483

</td>
<td style="text-align:right;">

537

</td>
<td style="text-align:right;">

543

</td>
<td style="text-align:right;">

186

</td>
<td style="text-align:right;">

76

</td>
<td style="text-align:right;">

4092

</td>
<td style="text-align:right;">

7

</td>
</tr>
<tr>
<td style="text-align:left;">

NARS-31-A-2019

</td>
<td style="text-align:right;">

6921

</td>
<td style="text-align:right;">

2186

</td>
<td style="text-align:right;">

440

</td>
<td style="text-align:right;">

184

</td>
<td style="text-align:right;">

66

</td>
<td style="text-align:right;">

10835

</td>
<td style="text-align:right;">

21

</td>
</tr>
<tr>
<td style="text-align:left;">

NARS-32-A-2019

</td>
<td style="text-align:right;">

541

</td>
<td style="text-align:right;">

2008

</td>
<td style="text-align:right;">

840

</td>
<td style="text-align:right;">

496

</td>
<td style="text-align:right;">

156

</td>
<td style="text-align:right;">

12586

</td>
<td style="text-align:right;">

65

</td>
</tr>
<tr>
<td style="text-align:left;">

NARS-35-A-2019

</td>
<td style="text-align:right;">

5212

</td>
<td style="text-align:right;">

7591

</td>
<td style="text-align:right;">

237

</td>
<td style="text-align:right;">

1866

</td>
<td style="text-align:right;">

899

</td>
<td style="text-align:right;">

27110

</td>
<td style="text-align:right;">

83

</td>
</tr>
<tr>
<td style="text-align:left;">

NARS-36-A-2019

</td>
<td style="text-align:right;">

2062

</td>
<td style="text-align:right;">

2582

</td>
<td style="text-align:right;">

39

</td>
<td style="text-align:right;">

29

</td>
<td style="text-align:right;">

6

</td>
<td style="text-align:right;">

17124

</td>
<td style="text-align:right;">

38

</td>
</tr>
<tr>
<td style="text-align:left;">

NARS-37-A-2019

</td>
<td style="text-align:right;">

6110

</td>
<td style="text-align:right;">

10209

</td>
<td style="text-align:right;">

686

</td>
<td style="text-align:right;">

3239

</td>
<td style="text-align:right;">

202

</td>
<td style="text-align:right;">

28537

</td>
<td style="text-align:right;">

34

</td>
</tr>
<tr>
<td style="text-align:left;">

NARS-40-A-2019

</td>
<td style="text-align:right;">

3

</td>
<td style="text-align:right;">

6

</td>
<td style="text-align:right;">

0

</td>
<td style="text-align:right;">

0

</td>
<td style="text-align:right;">

0

</td>
<td style="text-align:right;">

39

</td>
<td style="text-align:right;">

40

</td>
</tr>
<tr>
<td style="text-align:left;">

NARS-42-A-2019

</td>
<td style="text-align:right;">

14255

</td>
<td style="text-align:right;">

7880

</td>
<td style="text-align:right;">

285

</td>
<td style="text-align:right;">

273

</td>
<td style="text-align:right;">

60

</td>
<td style="text-align:right;">

46753

</td>
<td style="text-align:right;">

16

</td>
</tr>
<tr>
<td style="text-align:left;">

NARS-43-A-2019

</td>
<td style="text-align:right;">

22

</td>
<td style="text-align:right;">

16

</td>
<td style="text-align:right;">

0

</td>
<td style="text-align:right;">

10

</td>
<td style="text-align:right;">

11

</td>
<td style="text-align:right;">

57

</td>
<td style="text-align:right;">

46

</td>
</tr>
<tr>
<td style="text-align:left;">

NARS-43-B-2019

</td>
<td style="text-align:right;">

129

</td>
<td style="text-align:right;">

127

</td>
<td style="text-align:right;">

46

</td>
<td style="text-align:right;">

147

</td>
<td style="text-align:right;">

98

</td>
<td style="text-align:right;">

355

</td>
<td style="text-align:right;">

31

</td>
</tr>
<tr>
<td style="text-align:left;">

NARS-43-C-2019

</td>
<td style="text-align:right;">

76

</td>
<td style="text-align:right;">

74

</td>
<td style="text-align:right;">

65

</td>
<td style="text-align:right;">

17

</td>
<td style="text-align:right;">

5

</td>
<td style="text-align:right;">

215

</td>
<td style="text-align:right;">

41

</td>
</tr>
<tr>
<td style="text-align:left;">

NARS-44-A-2019

</td>
<td style="text-align:right;">

4222

</td>
<td style="text-align:right;">

7619

</td>
<td style="text-align:right;">

3273

</td>
<td style="text-align:right;">

2980

</td>
<td style="text-align:right;">

1698

</td>
<td style="text-align:right;">

27039

</td>
<td style="text-align:right;">

16

</td>
</tr>
</tbody>
</table>

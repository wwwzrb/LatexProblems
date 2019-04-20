ProblemsDescription:

    1. Change page size.
    2. Fonts not embeded in EDAS.
    3. Bookmarks and external links.
    4. Figure(.png, .jpeg, .tiff) to eps file is not complete.   
       Some figures canot show completely when converted to eps files directly. We resolve this by converting to eps first, next writing          as ps in GSview of WinEdt, finally converting to eps again! 
    5. !pdfTeX error: pdflatex (file mtex.pfb): cannot open Type 1 font file for reading in MikTex.
       This error appears in MikTex release version or MikTex based release version, e.g., CTX. We recommand to use Texlive release              version which can avoid this problem directly. In MikTex, we also give an solution of this problem. 

Solutions:

    1.
    2.
    3.
    4. Figure(.png, .jpeg, .tiff) to eps file is not complete.   
      (1) Convert figure to eps
         sam2p foo.png foo.eps
         bmeps -c foo.png foo.eps
      (2) Convert eps to ps in GSview
         ps2write 600
      (3) Convert ps to eps in GSview

    5. Cannot open Type 1 font file for reading in MikTex. (Only for MikTex and MikTex based release version)
      (1) Run the following line in windows cmd.
          initexmf --edit-config-file updmap
      (2) Adding the following lines in the opend txt.
          # belleek mathtime
          Map mt-belleek.map
          # YY mathtime
          #Map mt-yy.map
          #Map mt-plus.map
      (3) Run this cmd to updating mapping config. 
          initexmf --mkmaps --verbose
      (4) Now the tex file should be compiled successfully by Pdftexify or Texify in WinEdt.
          a. Pdftexify will generate pdf without any problem directly.
          b. Texify generates a dvi file. However, the pdf file is not complete if converting dvi to pdf by dvipdf directly. Two successful methods provided here.
             i.  Convert dvi to ps; Open ps in GSview; Write as pdf by pdfwrite in GSviw (Convert).
             ii. Convert dvi to ps; Open os in GSview; Write as eps by ps2write in GSviw (Convert); Convert eps to pdf by Adobe.
          
  References:
  4.  https://blog.csdn.net/xu_fengyu/article/details/87192066
  
      https://www.zhihu.com/question/24975110
      
  5.  https://www.aeaweb.org/content/file?id=3042
  
      https://tex.stackexchange.com/questions/152721/problems-with-fonts/152749
      
      http://www.tug.org/fonts/fontinstall.html
      
      https://tex.stackexchange.com/questions/88423/manual-font-installation/88424#88424
      
      https://blog.csdn.net/xu_fengyu/article/details/87192066
      
             
          

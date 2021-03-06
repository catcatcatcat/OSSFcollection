# 多功能的標記語言及排版系統 - LaTeX
作者：Kent，2012 年 3 月投稿。




### 簡介

LaTeX 是一個使用同樣名為 LaTeX 的標記語言的排版系統。LaTeX 的使用在學術界尤其興盛。其絕佳的排版以及強大的數學公式和表格生成讓使用者可以很輕易的編輯出高質量的印刷品。很多人會因為 LaTeX 不是一款“所見即所得”（What You See Is What You Get）的排版軟體所以抗拒它，確實 LaTeX 是一款不容易精通的軟體，可是其實透過使用預設好的模板，LaTeX 的上手也就不是那麼的困難了。

* Official website：www.latex-project.org  
* Platform：Cross-platform  
* License：LaTex Project Public License (LPPL)  
* Files：res2.tex (0 views)


本文將介紹一些 LaTeX 的入門知識然後帶領讀者實作幾份文件，透過實例輕鬆學習使用 LaTeX 的方式，希望可以幫助想要學習 LaTeX 的人克服可以被避免的陡峭學習曲線。

### 安裝說明

LaTeX 是個歷史悠久的軟體，所以在各大主流作業系統都有發行版本。以下介紹 Windows, Linux , Mac OS X 上的 LaTeX 圖形界面編輯器：

1.Linux 用戶請下載 [Texmaker](http://www.xm1math.net/texmaker/)  
 2.Windows 使用者請下載 [TeXworks](http://miktex.org/)（此編輯器被包含在 MiKTeX 的安裝包中）  
 3.Mac OS X 使用者可以使用 [TeXShop](http://pages.uoregon.edu/koch/texshop/)

### 使用說明

首先，先介紹一個 LaTeX 文檔如何生成一個 pdf。LaTeX 文檔有著 .tex 的副檔名。首先 .tex 檔需要先被編譯，在確認文檔裡並沒有錯誤以後，一個 .dvi 檔會先被生成然後最終檔案格式才會被生出（如.pdf）。這就是為什麼 LaTeX 並不是一個所見即所得的文檔編輯軟體。接下來，筆者將討論一些 LaTeX 的文檔標籤。

<pre>% this is a comment

\documentclass

% SETTINGS
% \textwidth 6.5truein
% \textwidth 9.5truein

\begin

Hello World!

\end
</pre>

以上是一個簡單的範例。

% 是讓 LaTeX 分辨代碼跟註釋的方式，所以任何在 % 之後的字元（直到換行字元）都不會被 LaTeX 的編譯器檢查。 \documentclass 是用來指定文檔排版的風格。其他常用的風格還有如 book 以及 beamer（可用於製作簡報，詳見之後的介紹）。在 \documentclass 以及 \begin 這些中間一般會針對使用者的需求設置全域的文檔設置。由於這些設置種類繁多，而且詳述這個部分超出本文的範圍，故在此僅提示讀者，若是有想深究的讀者，可 以在閱讀完本文和參考完本文的附件之後實際操作看看。

LaTeX 的格式化以及文字調配基本上可以看作像是在寫程式碼。如果要使一段文字粗體化，就放入那段文字到一個函式中，那可以使用 \textbf，bold 是想要粗體化的文字。 以下的範例表現幾個常用到的函式：

<pre>\documentclass

% SETTINGS
% \textwidth 6.5truein
% \textwidth 9.5truein

\begin

This is \LaTeX

To emphasize something， simply \emph it. Or， make it \textbf.

The date today is \today

\begin
\item one
\item two
\item three
\end

\end
</pre>

文件編譯後的結果如下圖：

如之前所說的，\textbf 會使 text 粗體化，而 \emph 會讓字體斜體化。在 LaTeX 中有些是預設的 macro，像上面的 \LaTeX 跟 \today，可以直接叫喚。另外值得一提的是 itemize。在 \begin 跟 \end 之間的設定將會視 itemize 的環境設定而決定如何編譯之間的文字。在 LaTeX 中，許多的擴充包都是利用這樣來表現專屬的環境設定。這個設計讓 LaTeX 更富有擴充性跟彈性。

在進入案例研究以前，我們先看看 LaTeX 強大的數學公式排版。我們來看以下幾個範例：

<pre>\documentclass

% SETTINGS
% \textwidth 6.5truein
% \textwidth 9.5truein

\begin

Fractions: $\frac$

Greek letters: $\alpha$， $\beta$， $\Sigma$， $\Omega$

\begin
root = \frac}
\end

\end
</pre>

產生出來的結果如下圖:

[![barbecue](http://www.openfoundry.org/images/120327/LaTeX/latex01.png)](http://www.openfoundry.org/images/120327/LaTeX/latex01.png)

▲ 圖1

$ 是用來分別一般字元跟特殊字元（如希臘文字）的，所以在呼叫這些特殊字元時，都需要用 $ 包覆住特殊字元。這裡我們也使用了 equation 這個環境設定。這使得式子置中靠齊並有一個 "(1)" 來標記這是第一個式子。這個簡單的例子很輕易地表現出 LaTeX 在公式排版方面的便利性跟彈性。

接下來， 我們來研究幾個實例。

### 實例研究

學習 LaTeX 最好的方式就是實際運用它。讀者在讀完了前一個段落以後應該已經對 LaTeX 有了足夠的認識可以開始使用了。本文中的實例都是以開源社群中熱心的 LaTeX 愛好者使用的模板加以改造的。以下是以 LaTeX 來編撰的兩個簡單範例。

#### 範例一：簡報

在簡報的實作，我們將會使用到 beamer 這個風格

<pre>\documentclass

% \usepackage // Activate for custom appearance

\title
\author
\date

\begin

\frame

\section[Outline]
\frame

\section
\subsection
\frame

  \begin
  \item＜1-＞ Normal LaTeX class.
  \item＜2-＞ Easy overlays.
  \item＜3-＞ No external programs needed.      
  \end
}
\end
</pre>

輸入以上代碼以後，應該會得到這個檔案 [demo1.pdf]。 beamer 這個 document class 最好的地方在於其非常直觀的函式命名，每張幻燈片都被視為一個 frame，frame title 則用來設定每張的標題。這讓在 LaTeX 中編輯簡報非常的簡單。若是簡報內容涉及許多數學公式，那就更可以發揮 LaTeX 的強大排版功能了。

#### 範例二：個人履歷

LaTeX 可以生成各式各樣的文件。以下就要用 LaTeX 來編寫一份個人履歷。
範例出自 [http://www.rpi.edu/dept/arc/training/latex/resumes/](http://www.rpi.edu/dept/arc/training/latex/resumes/）記得要先下載 [res.cls](http://www.rpi.edu/dept/arc/training/latex/resumes/res.cls) 因為主文檔會使用到這份文件。

如果想要直接下載這份檔案，請下載 [res2.tex](http://www.rpi.edu/dept/arc/training/latex/resumes/res2.tex)。有興趣的讀者現在不妨試者讀讀看代碼然後用之前介紹的概念試著了解一下文檔的結構吧！

<pre>\documentclass[margin] 
% the margin option causes section titles to appear to the left of body text 
\textwidth=5.2in % increase textwidth to get smaller right margin
%\usepackage % uses helvetica postscript font (download helvetica.sty)
%\usepackage   % uses new century schoolbook postscript font 

\begin 

\name % the \\[12pt] adds a blank line after name

\address \\ 204 Pawling Avenue \\ Troy， NY 12180  \\
        (518) 273-4617 }
\address \\ 29 Runner Lane \\ Syosset， NY 11971 \\
        (516) 921-7653 }

\begin 

\section 
Auditing/Analysis of Operations 

\section 
B.S. in Management， Rensselaer Polytechnic Institute， Troy， NY， May 1986 \\
Concentrations in Accounting and Management Systems \\
QPA 3.9 in major， 3.7 overall

\section
  National Money Bank USA， Melville， NY \hfill Summer  1985
 \begin \itemsep -2pt  % reduce space between items
 \item Created regression model to lower check volume 
                 forecast errors
 \item Authored PC-based software to determine optimal 
                 staff levels 
 \end

 Fleet Van Lines， Bayridge， NY \hfill  Summer 1984
\begin \itemsep -2pt %reduce space between items
\item Researched， implemented new computer accounting 
                 system 
\item Customized existing software for inventory 
                 management 
\item Trained employees on both accounting and inventory 
                 systems 
\end

 Solutions Unlimited， Lake Grove， NY \hfill
Summer 1983                
                \begin \itemsep -2pt
                 \item  Demonstrated extensive range of software and 
                 hardware 

                 \item Developed leads by offering seminars for specific 
                 professions 

                 \end

\section 
                Monarch Computer Products Inc.， Freeport， NY    \hfill         1985 
                \begin \itemsep -2pt
              \item Leader of marketing effort for V.R.S. (Video 
                 Rental System)， \\
                  currently in test phase 

                \item  Perform accounting duties 

                 \end

                 Delta Epsilon Pi Fraternity \hfill   1985 
                \begin \itemsep -2pt
                 \item  Responsible for the overall performance of the 
                 chapter 

                 \item Chair all house and alumni committee meetings 

                 \item Liaison to the national fraternity and the RPI 
                 administration 
                 \end

                    Rensselaer Fraternity Managers 
              Association     \hfill                                 1984 
                 \begin \itemsep -2pt

               \item    Evaluated and approved purchases in excess of 
                 1，000，000 yearly 

               \item  Formulated bookkeeping checklists for use by all 
                 fraternities 
                 \end

\section 
Dean's List of Distinguished Students， all semesters \\
National Merit Scholarship \\
Alan T. Hundert Memorial Scholarship \\
 Epsilon Delta Sigma， Honorary Management Society 

% Tabulate Computer Skills; p defines paragraph 3 inches wide
\section
   \begin}
    \underline & COBOL， Pascal，C， APL， Basic \\

     \underline &  SPIRES， dBase III， Datastar database 
                        systems， GPSS simulation， FCS-EPS financial 
                        planning， SAS statistical analysis， 
                        Lotus1-2-3， MPSX optimization modeling 
 \end

\end 
\end 
</pre>

### 結論

LaTeX 是一個非常多功能的標記語言以及排版系統。相關的資源也非常非常多，透過各種函式庫跟模板，LaTeX 可以被用來製作各式各樣的格式跟印刷品。尤其對於需要排版公式的人來說，LaTeX 無疑為他們解決了一個大問題。讀者若是有時間不妨試試看，利用 LaTeX 來取代一些桌面出版的軟體。

### 參考資料

*   LaTeX 履歷模板，[http://www.rpi.edu/dept/arc/training/latex/resumes/](http://www.rpi.edu/dept/arc/training/latex/resumes/)
*   LaTeX 官方網站，[http://www.latex-project.org/](http://www.latex-project.org/)

</div>
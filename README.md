# Código del Curriculum Vitae en LaTeX

%!TEX TS-program = xelatex
\documentclass[]{friggeri-cv}
\usepackage{afterpage}
\usepackage{hyperref}
\usepackage{color}
\usepackage{xcolor}

\documentclass[border=2mm]{standalone}
\usepackage[usenames,dvipsnames]{xcolor}
\usepackage{tikz}
\hypersetup{
    pdftitle={},
    pdfauthor={},
    pdfsubject={},
    pdfkeywords={},
    colorlinks=false,       % no lik border color
   allbordercolors=white    % white border color for all
}
\addbibresource{bibliography.bib}
\RequirePackage{xcolor}
\definecolor{pblue}{HTML}{0395DE}

\begin{document}
\header{Juan Carlos}{Hermoso}
      {Computer Scientist}
      
% Fake text to add separator      
\fcolorbox{white}{gray}{\parbox{\dimexpr\textwidth-2\fboxsep-2\fboxrule}{%
.....
}}

% In the aside, each new line forces a line break
\begin{aside}
  \section{Address}
    Camino de Ronda, 101, Portal 1, 3ºC
    14002 Granada, Spain
    ~
  \section{Tel}
    +34 617 793 067
    ~
  \section{Mail}
    \href{mailto:hermosojc@gmail.com}{\textbf{hermosojc@}\\gmail.com}
    ~
  \section{Github}
    \href{https://github.com/jchermoso}{github.com/jchermoso}
    ~
  \section{OS Experience Level}
    \textbf{GNU/Linux}\includegraphics[scale=0.40]{img/5stars.png}
    \textbf{Unix}\includegraphics[scale=0.40]{img/4stars.png}
    \textbf{Windows}\includegraphics[scale=0.40]{img/4stars.png}
    ~
  \section{Personal Skills}
    \textbf{Initiative}\includegraphics[scale=0.40]{img/5stars.png}
    \textbf{Management}\includegraphics[scale=0.40]{img/5stars.png}
    \textbf{Organize}\includegraphics[scale=0.40]{img/5stars.png}
    \textbf{Team}\includegraphics[scale=0.40]{img/5stars.png}
    
    ~
\section{Languages}
    \textbf{Español}\includegraphics[scale=0.40]{img/5stars.png}
    \textbf{Català}\includegraphics[scale=0.40]{img/5stars.png}
    \textbf{English}\includegraphics[scale=0.40]{img/4stars.png}
    ~
    
\end{aside}


\section{Education}
\begin{entrylist}
  \entry
    {2011 - 2013}
    {Technological Bachelor}
    {IES Cap de Llevant}
    {Main subjects: Maths, Physics, Electrical Engineering, Technology\\}
  \entry
    {2013 - 2015}
    {Computer Science}
    {Universitat de les Illes Balears}
    {Main subjects: Algebra, Digital Systems, Statistics, Programming, Business\\}
  \entry
    {2015 - 2019}
    {Computer Science}
    {ETSIIT - Universidad de Granada}
    {Main subjects: Programming, Software Architecture, Hardware Architecture, Physics, Artificial Inteligence, Server Engineering, Web Development, Software Projects Management\\}
\end{entrylist}

\section{Programming Skills}

\newcommand{\cc}{c\nolinebreak\hspace{-.05em}\raisebox{.2ex}{\tiny\bf +}\nolinebreak\hspace{-.10em}\raisebox{.2ex}{\tiny\bf +}}

\newcommand{\vardonut}[1]{
    \newcounter{num}
    \foreach \content/\size/\colour in {#1}
        \stepcounter{num};
    \foreach \content/\size/\colour [count=\i] in {#1}{
        \draw[white,very thick,top color=\colour!50!cyan, bottom color=\colour, shading angle={-90+360/\thenum/2+(\i-1)*360/\thenum}] 
        ({2*cos((\i-1)*360/\thenum)},{2*sin((\i-1)*360/\thenum)}) arc[radius = 2, start angle={(\i-1)*360/\thenum}, delta angle=360/\thenum] --
        ({(2+\size)*cos(\i*360/\thenum)},{(2+\size)*sin(\i*360/\thenum)}) arc[radius = {2+\size}, start angle={\i*360/\thenum}, delta angle=-360/\thenum] -- 
        cycle;
        \node[white,font=\large] at ({(\i-1)*360/\thenum+360/\thenum/2}:{\size/2+2}) {\content};
    }
}


\begin{tikzpicture}
    \vardonut{
        html       / 5 /, 
        css        / 5 /, 
        php        / 3 /,
        javascript / 3 / 
        sql        / 2 /, 
        java       / 5 /, 
        ruby       / 2 /, 
        c          / 4 /, 
        c++        / 5 /%
    }
\end{tikzpicture}

\end{document}

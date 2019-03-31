cmake_minimum_required(VERSION 2.8.10)
project(thesis)

set(CMAKE_MODULE_PATH ${PROJECT_SOURCE_DIR}/cmake)

set(LATEX_DEFAULT_BUILD safepdf)
set(PS2PDF_CONVERTER ps2pdf)
include(UseLATEX)

add_latex_document (
    src/szakdolgozat.tex
    INPUTS src/kotestabla.tex src/bib/cites.bib
    # IMAGE_DIRS img 
    BIBFILES src/bib/cites.bib src/bib/huplain.bst
    TARGET_NAME thesispaper
    # DEPENDS ${THESIS_DEPENDENCIES}
)

add_latex_document (
    src/kotestabla.tex
    TARGET_NAME frontpage
)

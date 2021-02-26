# Docs Template

Asciidoc

## Export in Docker Container

Run Docker
```sh
# Windows
docker run --rm -it -v %CD%\docs:/documents htakeuchi/docker-asciidoctor-jp

# macOS, Linux
docker run --rm -it -v ${PWD}/docs:/documents htakeuchi/docker-asciidoctor-jp
```

Export File
```sh
TARGET_FILE=minispec/minispec.adoc

# PDF
asciidoctor-pdf -r asciidoctor-diagram -r asciidoctor-pdf-cjk-kai_gen_gothic -a pdf-style=KaiGenGothicJP $TARGET_FILE

# HTML
asciidoctor -r asciidoctor-diagram -r asciidoctor-mathematical -a source-highlighter=highlightjs $TARGET_FILE
#asciidoctor -r asciidoctor-diagram -r asciidoctor-mathematical -a source-highlighter=highlightjs -a stylesheet=/documents/_common/design.css $TARGET_FILE

exit
```
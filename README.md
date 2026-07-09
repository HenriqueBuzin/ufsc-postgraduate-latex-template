# UFSC Postgraduate LaTeX Template

Este repositório mantém uma versão do template LaTeX **Template Trabalhos
Acadêmicos UFSC A4**, voltado a teses e dissertações da Universidade Federal de
Santa Catarina (UFSC), usando a classe `abntex2`.

## Origem

A base inicial deste repositório é o template oficial publicado no Overleaf:

https://pt.overleaf.com/latex/templates/template-trabalhos-academicos-ufsc-a4/vtfjxrcrvnjh

O template original é de autoria de **Alisson Lopes Furlani** e está licenciado
sob a **LaTeX Project Public License 1.3c**.

## Reuso

Este repositório pode ser reutilizado, adaptado e redistribuído, desde que sejam
mantidas as referências ao template original e a esta versão mantida.

## Modificações Mantidas Neste Repositório

A branch `main` deve conter apenas a base oficial importada, a documentação do
projeto e funcionalidades já validadas e integradas por merge. As melhorias são
desenvolvidas em branches separadas antes de serem incorporadas.

Melhorias previstas:

- ajuste da folha de certificação/assinatura ao padrão atual da Biblioteca
  Universitária da UFSC;
- suporte à geração de PDF/A diretamente no fluxo de compilação LaTeX.

## Compilação

O arquivo principal é `main.tex`. Em uma instalação LaTeX com `biber`, o fluxo
geral de compilação é:

```bash
pdflatex main.tex
biber main
pdflatex main.tex
pdflatex main.tex
```

## PDF/A

O template está preparado para gerar PDF/A-2B diretamente na compilação com
LaTeX moderno por meio de `\DocumentMetadata`, declarado no início de `main.tex`:

```tex
\DocumentMetadata{
	pdfstandard=A-2b
}
```

Após a compilação, valide o PDF final em uma ferramenta compatível com PDF/A,
pois arquivos externos incluídos no trabalho, como imagens e PDFs, também podem
influenciar a conformidade final.

O template evita incluir PDFs externos nos elementos pré-textuais para reduzir
problemas de validação, como fontes não incorporadas ou espaços de cor
dependentes de dispositivo. Ao substituir a ficha catalográfica pelo arquivo
definitivo gerado pela BU, verifique se o arquivo incluído também está adequado
para PDF/A.

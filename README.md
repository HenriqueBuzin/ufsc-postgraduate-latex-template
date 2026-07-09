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

Melhorias integradas:

- ajuste da folha de certificação/assinatura ao padrão atual da Biblioteca
  Universitária da UFSC;
- suporte à geração de PDF/A diretamente no fluxo de compilação LaTeX;
- inclusão da ficha catalográfica em PNG para preservar a conformidade PDF/A;
- uso de `\input` nos capítulos para evitar incremento indevido de contadores
  de tabelas ao reutilizar arquivos auxiliares entre compilações.

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

## Ficha Catalográfica

A ficha catalográfica deve ser gerada no site da Biblioteca Universitária da
UFSC:

https://ficha.bu.ufsc.br/

Para manter a conformidade PDF/A, use a opção **Gerar PNG** no sistema da BU e
substitua o arquivo `beforetext/Ficha_Catalografica.png` pelo arquivo gerado. O
template inclui essa imagem automaticamente na página da ficha catalográfica.

Evite incluir diretamente o PDF da ficha catalográfica quando o objetivo for
validar o trabalho como PDF/A. O PDF gerado pelo sistema da BU pode conter fontes
não incorporadas, o que pode impedir a validação do documento final.

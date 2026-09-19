<!DOCTYPE html><html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Orçamento - Marmoraria Pedras do Vale</title>  <script src="https://unpkg.com/pdf-lib@1.17.1/dist/pdf-lib.min.js"></script>  <script src="https://unpkg.com/downloadjs@1.4.7/download.min.js"></script>  <style>
    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
      font-family: 'Segoe UI', Roboto, Helvetica, Arial, sans-serif;
    }

    body {
      background: linear-gradient(135deg, #eef2f3 0%, #8e9eab 100%);
      color: #2c3e50;
      padding: 30px 15px;
      display: flex;
      justify-content: center;
      min-height: 100vh;
    }

    .form-container {
      width: 100%;
      max-width: 700px;
    }

    .form-header {
      background-color: #ffffff;
      border-radius: 12px;
      border-top: 10px solid #1a252f;
      padding: 24px;
      margin-bottom: 20px;
      box-shadow: 0 4px 15px rgba(0,0,0,.1);
      display: flex;
      justify-content: space-between;
      align-items: center;
    }

    .header-info h1 {
      font-size: 20px;
      font-weight: 700;
      color: #1a252f;
      text-transform: uppercase;
    }

    .header-info p {
      font-size: 13px;
      color: #5f6368;
      margin-top: 6px;
      line-height: 1.4;
    }

    .logo-box {
      border: 2px solid #1a252f;
      padding: 10px 14px;
      text-align: center;
      font-weight: bold;
      font-size: 12px;
      letter-spacing: 1px;
      color: #1a252f;
      border-radius: 4px;
      background: #f8f9fa;
    }

    .section-title {
      font-size: 15px;
      font-weight: 700;
      color: #1a252f;
      margin: 24px 0 10px 4px;
      text-transform: uppercase;
      letter-spacing: .5px;
    }

    .card {
      background-color: #fff;
      border-radius: 10px;
      padding: 20px 24px;
      margin-bottom: 14px;
      box-shadow: 0 2px 8px rgba(0,0,0,.06);
    }

    .card:focus-within {
      border-left: 5px solid #1a252f;
      box-shadow: 0 4px 12px rgba(0,0,0,.12);
    }

    .question-label {
      font-size: 14px;
      font-weight: 600;
      margin-bottom: 8px;
      display: block;
      color: #2c3e50;
    }

    .required {
      color: #e74c3c;
    }

    input[type="text"],
    input[type="tel"],
    textarea {
      width: 100%;
      border: none;
      border-bottom: 2px solid #ecf0f1;
      padding: 10px 0;
      font-size: 14px;
      outline: none;
      background: transparent;
      transition: border-color .2s;
    }

    input[type="text"]:focus,
    input[type="tel"]:focus,
    textarea:focus {
      border-bottom: 2px solid #1a252f;
    }

    textarea {
      min-height: 95px;
      resize: vertical;
      line-height: 1.5;
      font-family: inherit;
    }

    .payment-row {
      display: flex;
      align-items: center;
      gap: 12px;
      margin-bottom: 12px;
    }

    .payment-row span {
      font-size: 14px;
      font-weight: 600;
      min-width: 110px;
      color: #34495e;
    }

    .payment-row input {
      flex: 1;
    }

    .grid-2 {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 16px;
    }

    @media (max-width: 520px) {
      .grid-2 {
        grid-template-columns: 1fr;
      }

      .form-header {
        flex-direction: column;
        align-items: flex-start;
        gap: 15px;
      }
    }

    .btn-submit {
      background-color: #1a252f;
      color: white;
      border: none;
      padding: 16px 32px;
      font-size: 15px;
      font-weight: 700;
      border-radius: 6px;
      cursor: pointer;
      box-shadow: 0 4px 10px rgba(26,37,47,.3);
      width: 100%;
      margin-top: 10px;
      transition: background-color .2s;
    }

    .btn-submit:hover {
      background-color: #2c3e50;
    }
  </style></head><body><div class="form-container"><form id="orcamentoForm">  <div class="form-header"><div class="header-info">

  <h1>MARMORARIA PEDRAS DO VALE</h1>

  <p>
    <strong>CNPJ:</strong> 68.952.061/0001-92<br>
    <strong>Telefones:</strong>
    (12) 99221-0262 / (12) 92000-3358
  </p>

</div>

<div class="logo-box">
  PEDRAS DO VALE<br>
  <span style="font-size:9px;font-weight:normal;">
    PROJETOS & ACABAMENTOS
  </span>
</div>

  </div>  <div class="section-title">
    Dados do Cliente
  </div>  <div class="card"><label class="question-label" for="nome">
  Nome do Cliente <span class="required">*</span>
</label>

<input
  type="text"
  id="nome"
  placeholder="Digite o nome completo"
  required
>

  </div>  <div class="card grid-2"><div>

  <label class="question-label" for="telefone">
    Telefone <span class="required">*</span>
  </label>

  <input
    type="tel"
    id="telefone"
    placeholder="(12) 00000-0000"
    required
  >

</div>


<div>

  <label class="question-label" for="cidade">
    Cidade <span class="required">*</span>
  </label>

  <input
    type="text"
    id="cidade"
    placeholder="Digite a cidade"
    required
  >

</div>

  </div>  <div class="card"><label class="question-label" for="endereco">
  Endereço da Obra <span class="required">*</span>
</label>

<input
  type="text"
  id="endereco"
  placeholder="Rua, número, bairro..."
  required
>

  </div>  <div class="section-title">
    Descrição do Serviço / Peças
  </div>  <div class="card grid-2"><div>

  <label class="question-label" for="material">
    Material <span class="required">*</span>
  </label>

  <input
    type="text"
    id="material"
    placeholder="Ex: Granito Preto São Gabriel"
    required
  >

</div>


<div>

  <label class="question-label" for="acabamento">
    Acabamento <span class="required">*</span>
  </label>

  <input
    type="text"
    id="acabamento"
    placeholder="Ex: Meia Esquadria / Polido"
    required
  >

</div>

  </div>  <div class="card grid-2"><div>

  <label class="question-label" for="frontao">
    Frontão
  </label>

  <input
    type="text"
    id="frontao"
    placeholder="Ex: 10 cm"
  >

</div>


<div>

  <label class="question-label" for="saia">
    Saia
  </label>

  <input
    type="text"
    id="saia"
    placeholder="Ex: 4 cm"
  >

</div>

  </div>  <div class="card grid-2"><div>

  <label class="question-label" for="descricaoProduto">
    Descrição do produto
  </label>

  <textarea
    id="descricaoProduto"
    placeholder="Digite a descrição. Pressione Enter para adicionar novas linhas."
  ></textarea>

</div>


<div>

  <label class="question-label" for="materiais">
    Materiais (Ferro / Instalação)
  </label>

  <input
    type="text"
    id="materiais"
    placeholder="Ex: Suporte de ferro + instalação"
  >

</div>

  </div>  <div class="section-title">
    Pagamento e Valores
  </div>  <div class="card"><label class="question-label">
  Forma de Pagamento Editável
</label>


<div class="payment-row">

  <span>À Vista / PIX:</span>

  <input
    type="text"
    id="pag_avista"
    placeholder="Ex: R$ 2.500,00 (5% desconto)"
  >

</div>


<div class="payment-row">

  <span>No Cartão:</span>

  <input
    type="text"
    id="pag_cartao"
    placeholder="Ex: 3x de R$ 900,00 sem juros"
  >

</div>

  </div>  <div class="card"><label class="question-label" for="valor_total">
  Valor Total do Orçamento (R$)
  <span class="required">*</span>
</label>

<input
  type="text"
  id="valor_total"
  placeholder="R$ 2.700,00"
  required
>

  </div><button
type="submit"
class="btn-submit"

«»

GERAR ORÇAMENTO EM PDF

  </button></form></div><script>

function getLogoBase64() {

  const canvas = document.createElement('canvas');

  canvas.width = 400;
  canvas.height = 200;

  const ctx = canvas.getContext('2d');


  ctx.fillStyle = '#f1c40f';

  ctx.beginPath();
  ctx.arc(120,55,24,0,Math.PI*2);
  ctx.fill();


  ctx.fillStyle = '#27ae60';

  ctx.beginPath();
  ctx.moveTo(80,115);
  ctx.lineTo(110,75);
  ctx.lineTo(140,115);
  ctx.closePath();
  ctx.fill();


  ctx.fillStyle = '#2e7d32';

  ctx.beginPath();
  ctx.moveTo(120,115);
  ctx.lineTo(160,50);
  ctx.lineTo(200,115);
  ctx.closePath();
  ctx.fill();


  ctx.fillStyle = '#1b5e20';

  ctx.beginPath();
  ctx.moveTo(170,115);
  ctx.lineTo(210,60);
  ctx.lineTo(250,115);
  ctx.closePath();
  ctx.fill();


  ctx.fillStyle = '#1a252f';

  ctx.font = 'bold 15px Arial';
  ctx.fillText('— MARMORARIA —',90,132);

  ctx.font = 'bold 26px Arial';
  ctx.fillText('PEDRAS DO VALE',40,162);


  return canvas.toDataURL('image/png');
}


/* =====================================================
   QUEBRA DE TEXTO PARA O PDF
===================================================== */

function quebrarTexto(texto, fonte, tamanho, largura) {

  const linhas = [];

  const paragrafos = texto.split(/\r?\n/);


  paragrafos.forEach(paragrafo => {

    if (!paragrafo.trim()) {

      linhas.push('');

      return;

    }


    const palavras = paragrafo.trim().split(/\s+/);

    let linha = '';


    palavras.forEach(palavra => {

      const teste =
        linha.length === 0
          ? palavra
          : linha + ' ' + palavra;


      if (
        fonte.widthOfTextAtSize(teste,tamanho)
        <= largura
      ) {

        linha = teste;

      } else {

        if (linha) {
          linhas.push(linha);
        }

        linha = palavra;

      }

    });


    if (linha) {
      linhas.push(linha);
    }

  });


  return linhas;
}


/* =====================================================
   GERAR PDF
===================================================== */

document
.getElementById('orcamentoForm')
.addEventListener('submit', async function(e) {

  e.preventDefault();


  try {

    const {
      PDFDocument,
      rgb,
      StandardFonts
    } = PDFLib;


    const nome =
      document.getElementById('nome').value.trim();

    const telefone =
      document.getElementById('telefone').value.trim();

    const cidade =
      document.getElementById('cidade').value.trim();

    const endereco =
      document.getElementById('endereco').value.trim();

    const material =
      document.getElementById('material').value.trim();

    const acabamento =
      document.getElementById('acabamento').value.trim();

    const frontao =
      document.getElementById('frontao').value.trim()
      || 'N/A';

    const saia =
      document.getElementById('saia').value.trim()
      || 'N/A';

    const descricaoProduto =
      document.getElementById('descricaoProduto').value
      || 'N/A';

    const materiais =
      document.getElementById('materiais').value.trim()
      || 'N/A';

    const pagAvista =
      document.getElementById('pag_avista').value.trim();

    const pagCartao =
      document.getElementById('pag_cartao').value.trim();

    const valorTotal =
      document.getElementById('valor_total').value.trim();


    /* PDF */

    const pdfDoc =
      await PDFDocument.create();

    const page =
      pdfDoc.addPage([595.28,841.89]);


    const font =
      await pdfDoc.embedFont(
        StandardFonts.Helvetica
      );

    const fontBold =
      await pdfDoc.embedFont(
        StandardFonts.HelveticaBold
      );


    const black =
      rgb(0,0,0);

    const gray =
      rgb(.35,.35,.35);

    const lightGray =
      rgb(.94,.94,.94);


    function box(x,y,w,h,fill=false) {

      page.drawRectangle({

        x,
        y,
        width:w,
        height:h,

        borderColor:black,
        borderWidth:1.2,

        ...(fill
          ? { color:lightGray }
          : {})

      });

    }


    /* =================================================
       CABEÇALHO
    ================================================= */

    box(25,745,545,70);


    page.drawText(
      'ORÇAMENTO',
      {
        x:35,
        y:792,
        size:18,
        font:fontBold,
        color:black
      }
    );


    page.drawText(
      'MARMORARIA PEDRAS DO VALE',
      {
        x:35,
        y:772,
        size:12,
        font:fontBold,
        color:black
      }
    );


    page.drawText(
      'CNPJ: 68.952.061/0001-92',
      {
        x:35,
        y:755,
        size:9.5,
        font,
        color:gray
      }
    );


    page.drawText(
      '(12) 99221-0262 / (12) 92000-3358',
      {
        x:260,
        y:755,
        size:9.5,
        font,
        color:gray
      }
    );


    const logo =
      await pdfDoc.embedPng(
        getLogoBase64()
      );


    page.drawImage(
      logo,
      {
        x:445,
        y:748,
        width:110,
        height:55
      }
    );


    /* =================================================
       CLIENTE
    ================================================= */

    let y = 720;


    page.drawText(
      'DADOS DO CLIENTE',
      {
        x:25,
        y,
        size:11,
        font:fontBold,
        color:black
      }
    );


    y -= 30;


    box(25,y,545,32);


    page.drawText(
      `Nome: ${nome}`,
      {
        x:35,
        y:y+11,
        size:10,
        font:fontBold,
        color:black
      }
    );


    page.drawText(
      `Telefone: ${telefone}`,
      {
        x:360,
        y:y+11,
        size:10,
        font,
        color:black
      }
    );


    y -= 32;


    box(25,y,545,32);


    page.drawText(
      `Endereço: ${endereco}`,
      {
        x:35,
        y:y+11,
        size:10,
        font,
        color:black
      }
    );


    page.drawText(
      `Cidade: ${cidade}`,
      {
        x:400,
        y:y+11,
        size:10,
        font,
        color:black
      }
    );


    /* =================================================
       SERVIÇOS
    ================================================= */

    y -= 35;


    page.drawText(
      'DESCRIÇÃO DO SERVIÇO / PEÇAS',
      {
        x:25,
        y,
        size:11,
        font:fontBold,
        color:black
      }
    );


    y -= 24;


    /* Cabeçalho tabela */

    box(25,y,545,27,true);


    page.drawText(
      'ITEM',
      {
        x:38,
        y:y+8,
        size:9.5,
        font:fontBold,
        color:black
      }
    );


    page.drawText(
      'DESCRIÇÃO',
      {
        x:85,
        y:y+8,
        size:9.5,
        font:fontBold,
        color:black
      }
    );


    page.drawText(
      'VALOR',
      {
        x:490,
        y:y+8,
        size:9.5,
        font:fontBold,
        color:black
      }
    );


    y -= 145;


    /* Área principal */

    box(25,y,545,145);


    page.drawLine({
      start:{x:75,y},
      end:{x:75,y:y+145},
      thickness:1.2,
      color:black
    });


    page.drawLine({
      start:{x:470,y},
      end:{x:470,y:y+145},
      thickness:1.2,
      color:black
    });


    page.drawText(
      '01',
      {
        x:40,
        y:y+118,
        size:10,
        font:fontBold,
        color:black
      }
    );


    const descricaoX = 85;
    const descricaoLargura = 365;


    /* Material */

    page.drawText(
      `Material: ${material}`,
      {
        x:descricaoX,
        y:y+118,
        size:9.5,
        font:fontBold,
        color:black
      }
    );


    /* Acabamento */

    page.drawText(
      `Acabamento: ${acabamento}`,
      {
        x:descricaoX,
        y:y+100,
        size:9,
        font,
        color:black
      }
    );


    /* Frontão / Saia */

    page.drawText(
      `Frontão: ${frontao}   |   Saia: ${saia}`,
      {
        x:descricaoX,
        y:y+82,
        size:9,
        font,
        color:black
      }
    );


    /* Descrição */

    page.drawText(
      'Descrição do produto:',
      {
        x:descricaoX,
        y:y+63,
        size:9,
        font:fontBold,
        color:black
      }
    );


    let descY = y+50;


    const linhas =
      quebrarTexto(
        descricaoProduto,
        font,
        8.5,
        descricaoLargura
      );


    linhas.slice(0,4).forEach(linha => {

      page.drawText(
        linha,
        {
          x:descricaoX,
          y:descY,
          size:8.5,
          font,
          color:black
        }
      );

      descY -= 12;

    });


    /* Materiais */

    page.drawText(
      `Materiais/Instalação: ${materiais}`,
      {
        x:descricaoX,
        y:y+12,
        size:8.5,
        font,
        color:black
      }
    );


    /* Valor */

    page.drawText(
      valorTotal,
      {
        x:482,
        y:y+118,
        size:10,
        font:fontBold,
        color:black
      }
    );


    /* =================================================
       TOTAL
    ================================================= */

    y -= 38;


    box(25,y,545,38,true);


    page.drawText(
      'VALOR TOTAL DO ORÇAMENTO:',
      {
        x:35,
        y:y+13,
        size:11,
        font:fontBold,
        color:black
      }
    );


    page.drawText(
      valorTotal,
      {
        x:475,
        y:y+12,
        size:12,
        font:fontBold,
        color:black
      }
    );


    /* =================================================
       PAGAMENTO
    ================================================= */

    y -= 58;


    box(25,y,545,48);


    page.drawText(
      'FORMA DE PAGAMENTO',
      {
        x:35,
        y:y+31,
        size:10,
        font:fontBold,
        color:black
      }
    );


    let pagamento = 'Conforme alinhado com o vendedor';


    if(pagAvista || pagCartao) {

      pagamento = '';

      if(pagAvista)
        pagamento += `À Vista/PIX: ${pagAvista}`;

      if(pagCartao) {

        if(pagamento)
          pagamento += '   |   ';

        pagamento += `Cartão: ${pagCartao}`;

      }

    }


    page.drawText(
      pagamento,
      {
        x:35,
        y:y+12,
        size:8.5,
        font,
        color:black
      }
    );


    page.drawLine({
      start:{x:350,y},
      end:{x:350,y:y+48},
      thickness:1,
      color:black
    });


    page.drawText(
      'PRAZO DE ENTREGA',
      {
        x:365,
        y:y+31,
        size:10,
        font:fontBold,
        color:black
      }
    );


    page.drawText(
      '20 dias úteis após confirmação',
      {
        x:365,
        y:y+17,
        size:8,
        font,
        color:gray
      }
    );


    page.drawText(
      'do pagamento e medição final.',
      {
        x:365,
        y:y+6,
        size:8,
        font,
        color:gray
      }
    );


    /* =================================================
       OBSERVAÇÕES
    ================================================= */

    y -= 165;


    box(25,y,545,145);


    page.drawText(
      'OBSERVAÇÕES',
      {
        x:35,
        y:y+125,
        size:10,
        font:fontBold,
        color:black
      }
    );


    const observacoes = [

      '01. O orçamento é válido por 07 dias a contar desta data.',

      '02. As medidas deverão ser confirmadas antes do início da fabricação.',

      '03. Produtos confeccionados sob medida poderão apresentar variações naturais de tonalidade e veios.',

      '04. Alterações solicitadas após a aprovação poderão gerar custos adicionais e alteração de prazo.',

      '05. Após a aprovação e início da fabricação, o cancelamento estará sujeito às condições previstas.'
    ];


    let obsY = y+103;


    observacoes.forEach(texto => {

      const linhasObs =
        quebrarTexto(
          texto,
          font,
          7.5,
          510
        );


      linhasObs.forEach(linha => {

        page.drawText(
          linha,
          {
            x:35,
            y:obsY,
            size:7.5,
            font,
            color:gray
          }
        );

        obsY -= 12;

      });

      obsY -= 4;

    });


    /* =================================================
       RODAPÉ
    ================================================= */

    page.drawLine({
      start:{x:25,y:48},
      end:{x:570,y:48},
      thickness:1,
      color:black
    });


    page.drawText(
      'MARMORARIA PEDRAS DO VALE',
      {
        x:35,
        y:32,
        size:9,
        font:fontBold,
        color:black
      }
    );


    page.drawText(
      'CNPJ: 68.952.061/

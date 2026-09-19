<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Orçamento - Marmoraria Pedras do Vale</title>

  <!-- Biblioteca para geração do PDF -->
  <script src="https://unpkg.com/pdf-lib@1.17.1/dist/pdf-lib.min.js"></script>

  <style>
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
      box-shadow: 0 4px 15px rgba(0, 0, 0, 0.1);
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
      letter-spacing: 0.5px;
    }

    .card {
      background-color: #ffffff;
      border-radius: 10px;
      padding: 20px 24px;
      margin-bottom: 14px;
      box-shadow: 0 2px 8px rgba(0, 0, 0, 0.06);
    }

    .card:focus-within {
      border-left: 5px solid #1a252f;
      box-shadow: 0 4px 12px rgba(0, 0, 0, 0.12);
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
      transition: border-color 0.2s;
    }

    input[type="text"]:focus,
    input[type="tel"]:focus,
    textarea:focus {
      border-bottom: 2px solid #1a252f;
    }

    textarea {
      min-height: 120px;
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
      box-shadow: 0 4px 10px rgba(26, 37, 47, 0.3);
      width: 100%;
      margin-top: 10px;
      transition: background-color 0.2s;
    }

    .btn-submit:hover {
      background-color: #2c3e50;
    }

    .btn-submit:disabled {
      opacity: 0.6;
      cursor: wait;
    }
  </style>
</head>

<body>

  <div class="form-container">

    <form id="orcamentoForm">

      <!-- CABEÇALHO -->
      <div class="form-header">

        <div class="header-info">

          <h1>MARMORARIA PEDRAS DO VALE</h1>

          <p>
            <strong>CNPJ:</strong> 68.952.061/0001-92<br>
            <strong>Telefones:</strong> (12) 99221-0262 / (12) 92000-3358
          </p>

        </div>

        <div class="logo-box">
          PEDRAS DO VALE<br>
          <span style="font-size: 9px; font-weight: normal;">
            PROJETOS & ACABAMENTOS
          </span>
        </div>

      </div>


      <!-- DADOS DO CLIENTE -->

      <div class="section-title">
        Dados do Cliente
      </div>


      <div class="card">

        <label class="question-label" for="nome">
          Nome do Cliente <span class="required">*</span>
        </label>

        <input
          type="text"
          id="nome"
          placeholder="Digite o nome completo"
          required
        >

      </div>


      <div class="card grid-2">

        <div>

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

      </div>


      <div class="card">

        <label class="question-label" for="endereco">
          Endereço da Obra <span class="required">*</span>
        </label>

        <input
          type="text"
          id="endereco"
          placeholder="Rua, número, bairro..."
          required
        >

      </div>


      <!-- DESCRIÇÃO DO SERVIÇO / PEÇAS -->

      <div class="section-title">
        Descrição do Serviço / Peças
      </div>


      <div class="card grid-2">

        <div>

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
            placeholder="Ex: Meia Esquadria (45°) / Polido"
            required
          >

        </div>

      </div>


      <div class="card grid-2">

        <div>

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

      </div>


      <!-- DESCRIÇÃO DO PRODUTO -->

      <div class="card grid-2">

        <div>

          <label class="question-label" for="descricaoProduto">
            Descrição do produto
          </label>

          <textarea
            id="descricaoProduto"
            placeholder="Digite a descrição. Pressione Enter para criar uma nova linha."
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

      </div>


      <!-- PAGAMENTO E VALORES -->

      <div class="section-title">
        Pagamento e Valores
      </div>


      <div class="card">

        <label class="question-label">
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

      </div>


      <div class="card">

        <label
          class="question-label"
          for="valor_total"
        >
          Valor Total do Orçamento (R$)
          <span class="required">*</span>
        </label>

        <input
          type="text"
          id="valor_total"
          placeholder="R$ 2.700,00"
          required
        >

      </div>


      <button
        type="submit"
        class="btn-submit"
        id="btnGerarPDF"
      >
        GERAR ORÇAMENTO EM PDF
      </button>

    </form>

  </div>


  <script>

    /* =====================================================
       LOGO
    ===================================================== */

    function getLogoBase64() {

      const canvas =
        document.createElement('canvas');

      canvas.width = 400;
      canvas.height = 200;

      const ctx =
        canvas.getContext('2d');


      ctx.fillStyle = '#f1c40f';

      ctx.beginPath();

      ctx.arc(
        120,
        55,
        24,
        0,
        Math.PI * 2
      );

      ctx.fill();


      ctx.fillStyle = '#27ae60';

      ctx.beginPath();

      ctx.moveTo(80, 115);
      ctx.lineTo(110, 75);
      ctx.lineTo(140, 115);

      ctx.closePath();

      ctx.fill();


      ctx.fillStyle = '#2e7d32';

      ctx.beginPath();

      ctx.moveTo(120, 115);
      ctx.lineTo(160, 50);
      ctx.lineTo(200, 115);

      ctx.closePath();

      ctx.fill();


      ctx.fillStyle = '#1b5e20';

      ctx.beginPath();

      ctx.moveTo(170, 115);
      ctx.lineTo(210, 60);
      ctx.lineTo(250, 115);

      ctx.closePath();

      ctx.fill();


      ctx.fillStyle = '#1a252f';

      ctx.font = 'bold 15px Arial';

      ctx.fillText(
        '— MARMORARIA —',
        90,
        132
      );


      ctx.font = 'bold 26px Arial';

      ctx.fillText(
        'PEDRAS DO VALE',
        40,
        162
      );


      return canvas.toDataURL('image/png');
    }


    /* =====================================================
       QUEBRA DE TEXTO
    ===================================================== */

    function quebrarTexto(
      texto,
      fonte,
      tamanho,
      larguraMaxima
    ) {

      const linhas = [];

      const paragrafos =
        String(texto).split(/\r?\n/);


      for (
        let p = 0;
        p < paragrafos.length;
        p++
      ) {

        const paragrafo =
          paragrafos[p];


        if (
          paragrafo.trim() === ''
        ) {

          linhas.push('');

          continue;

        }


        const palavras =
          paragrafo.trim().split(/\s+/);


        let linha = '';


        for (
          let i = 0;
          i < palavras.length;
          i++
        ) {

          const palavra =
            palavras[i];


          const teste =
            linha === ''
              ? palavra
              : linha + ' ' + palavra;


          const largura =
            fonte.widthOfTextAtSize(
              teste,
              tamanho
            );


          if (
            largura <= larguraMaxima
          ) {

            linha = teste;

          } else {

            if (
              linha !== ''
            ) {

              linhas.push(linha);

            }

            linha = palavra;

          }

        }


        if (
          linha !== ''
        ) {

          linhas.push(linha);

        }

      }


      return linhas;
    }


    /* =====================================================
       DOWNLOAD DO PDF
    ===================================================== */

    async function baixarPDF(
      pdfBytes,
      nomeArquivo
    ) {

      const blob =
        new Blob(
          [pdfBytes],
          {
            type: 'application/pdf'
          }
        );


      /*
       * No Android/Chrome e na maioria dos
       * navegadores atuais, usamos o compartilhamento
       * de arquivos quando disponível.
       */

      if (
        navigator.share &&
        typeof File !== 'undefined'
      ) {

        try {

          const arquivo =
            new File(
              [pdfBytes],
              nomeArquivo,
              {
                type: 'application/pdf'
              }
            );


          if (
            navigator.canShare &&
            navigator.canShare({
              files: [arquivo]
            })
          ) {

            await navigator.share({
              files: [arquivo],
              title: 'Orçamento - Pedras do Vale'
            });

            return;

          }

        } catch (erro) {

          /*
           * Se o usuário cancelar o compartilhamento,
           * não mostra erro.
           */

          if (
            erro.name === 'AbortError'
          ) {

            return;

          }

        }

      }


      /*
       * Método principal de download.
       */

      const url =
        URL.createObjectURL(blob);


      const link =
        document.createElement('a');


      link.href = url;

      link.download =
        nomeArquivo;

      link.setAttribute(
        'download',
        nomeArquivo
      );

      link.style.position =
        'fixed';

      link.style.left =
        '-9999px';

      link.style.top =
        '-9999px';


      document.body.appendChild(
        link
      );


      /*
       * Dispara o download.
       */

      link.click();


      /*
       * Limpa o elemento.
       */

      setTimeout(
        function() {

          if (
            link.parentNode
          ) {

            link.parentNode.removeChild(
              link
            );

          }

          URL.revokeObjectURL(
            url
          );

        },
        3000
      );

    }


    /* =====================================================
       FORMULÁRIO
    ===================================================== */

    document
      .getElementById('orcamentoForm')
      .addEventListener(
        'submit',
        async function(e) {

          e.preventDefault();


          const botao =
            document.getElementById(
              'btnGerarPDF'
            );


          /*
           * Evita dois PDFs sendo gerados
           * ao mesmo tempo.
           */

          if (
            botao.disabled
          ) {

            return;

          }


          botao.disabled = true;

          botao.textContent =
            'GERANDO PDF...';


          try {

            /* =============================================
               VERIFICAÇÃO DA BIBLIOTECA
            ============================================= */

            if (
              typeof PDFLib === 'undefined'
            ) {

              throw new Error(
                'A biblioteca de geração de PDF não foi carregada. Verifique sua conexão com a internet e recarregue a página.'
              );

            }


            const {
              PDFDocument,
              rgb,
              StandardFonts
            } = PDFLib;


            /* =============================================
               DADOS DO FORMULÁRIO
            ============================================= */

            const nome =
              document
                .getElementById('nome')
                .value
                .trim();


            const telefone =
              document
                .getElementById('telefone')
                .value
                .trim();


            const cidade =
              document
                .getElementById('cidade')
                .value
                .trim();


            const endereco =
              document
                .getElementById('endereco')
                .value
                .trim();


            const material =
              document
                .getElementById('material')
                .value
                .trim();


            const acabamento =
              document
                .getElementById('acabamento')
                .value
                .trim();


            const frontao =
              document
                .getElementById('frontao')
                .value
                .trim() || 'N/A';


            const saia =
              document
                .getElementById('saia')
                .value
                .trim() || 'N/A';


            const descricaoProduto =
              document
                .getElementById(
                  'descricaoProduto'
                )
                .value || 'N/A';


            const materiais =
              document
                .getElementById('materiais')
                .value
                .trim() || 'N/A';


            const pagAvista =
              document
                .getElementById('pag_avista')
                .value
                .trim();


            const pagCartao =
              document
                .getElementById('pag_cartao')
                .value
                .trim();


            const valorTotal =
              document
                .getElementById('valor_total')
                .value
                .trim();


            /* =============================================
               CRIA PDF
            ============================================= */

            const pdfDoc =
              await PDFDocument.create();


            const page =
              pdfDoc.addPage(
                [595.28, 841.89]
              );


            const font =
              await pdfDoc.embedFont(
                StandardFonts.Helvetica
              );


            const fontBold =
              await pdfDoc.embedFont(
                StandardFonts.HelveticaBold
              );


            const black =
              rgb(
                0,
                0,
                0
              );


            const darkGray =
              rgb(
                0.15,
                0.15,
                0.15
              );


            const lightGray =
              rgb(
                0.92,
                0.92,
                0.92
              );


            /* =============================================
               CAIXA
            ============================================= */

            function drawBox(
              x,
              y,
              width,
              height,
              borderWidth = 1.2
            ) {

              page.drawRectangle({

                x: x,

                y: y,

                width: width,

                height: height,

                borderColor: black,

                borderWidth:
                  borderWidth

              });

            }


            /* =============================================
               CABEÇALHO
            ============================================= */

            drawBox(
              25,
              735,
              545,
              80,
              1.5
            );


            page.drawText(
              'ORÇAMENTO - MARMORARIA PEDRAS DO VALE',
              {
                x: 35,
                y: 790,
                size: 13,
                font: fontBold,
                color: black
              }
            );


            page.drawText(
              'CNPJ: 68.952.061/0001-92',
              {
                x: 35,
                y: 770,
                size: 10,
                font: fontBold,
                color: darkGray
              }
              

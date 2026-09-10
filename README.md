<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Orçamento - Marmoraria Pedras do Vale</title>

  <!-- Bibliotecas para geração do PDF -->
  <script src="https://unpkg.com/pdf-lib@1.17.1/dist/pdf-lib.min.js"></script>
  <script src="https://unpkg.com/downloadjs@1.4.7/download.min.js"></script>

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
    input[type="tel"] {
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
    input[type="tel"]:focus {
      border-bottom: 2px solid #1a252f;
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
          <span style="font-size: 9px; font-weight: normal;">PROJETOS & ACABAMENTOS</span>
        </div>
      </div>

      <!-- DADOS DO CLIENTE -->
      <div class="section-title">Dados do Cliente</div>

      <div class="card">
        <label class="question-label" for="nome">Nome do Cliente <span class="required">*</span></label>
        <input type="text" id="nome" placeholder="Digite o nome completo" required>
      </div>

      <div class="card grid-2">
        <div>
          <label class="question-label" for="telefone">Telefone <span class="required">*</span></label>
          <input type="tel" id="telefone" placeholder="(12) 00000-0000" required>
        </div>
        <div>
          <label class="question-label" for="cidade">Cidade <span class="required">*</span></label>
          <input type="text" id="cidade" placeholder="Digite a cidade" required>
        </div>
      </div>

      <div class="card">
        <label class="question-label" for="endereco">Endereço da Obra <span class="required">*</span></label>
        <input type="text" id="endereco" placeholder="Rua, número, bairro..." required>
      </div>

      <!-- DESCRIÇÃO DO SERVIÇO / PEÇAS -->
      <div class="section-title">Descrição do Serviço / Peças</div>

      <div class="card grid-2">
        <div>
          <label class="question-label" for="material">Material <span class="required">*</span></label>
          <input type="text" id="material" placeholder="Ex: Granito Preto São Gabriel" required>
        </div>
        <div>
          <label class="question-label" for="acabamento">Acabamento <span class="required">*</span></label>
          <input type="text" id="acabamento" placeholder="Ex: Meia Esquadria (45°) / Polido" required>
        </div>
      </div>

      <div class="card grid-2">
        <div>
          <label class="question-label" for="frontao">Frontão</label>
          <input type="text" id="frontao" placeholder="Ex: 10 cm">
        </div>
        <div>
          <label class="question-label" for="saia">Saia</label>
          <input type="text" id="saia" placeholder="Ex: 4 cm">
        </div>
      </div>

      <div class="card grid-2">
        <div>
          <label class="question-label" for="complemento">Complemento</label>
          <input type="text" id="complemento" placeholder="Ex: Cuba esculpida / Furo cooktop">
        </div>
        <div>
          <label class="question-label" for="materiais">Materiais (Ferro / Instalação)</label>
          <input type="text" id="materiais" placeholder="Ex: Suporte de ferro + instalação">
        </div>
      </div>

      <!-- PAGAMENTO E VALORES -->
      <div class="section-title">Pagamento e Valores</div>

      <div class="card">
        <label class="question-label">Forma de Pagamento Editável</label>
        <div class="payment-row">
          <span>À Vista / PIX:</span>
          <input type="text" id="pag_avista" placeholder="Ex: R$ 2.500,00 (5% desconto)">
        </div>
        <div class="payment-row">
          <span>No Cartão:</span>
          <input type="text" id="pag_cartao" placeholder="Ex: 3x de R$ 900,00 sem juros">
        </div>
      </div>

      <div class="card">
        <label class="question-label" for="valor_total">Valor Total do Orçamento (R$) <span class="required">*</span></label>
        <input type="text" id="valor_total" placeholder="R$ 2.700,00" required>
      </div>

      <button type="submit" class="btn-submit">GERAR ORÇAMENTO EM PDF</button>

    </form>
  </div>

  <script>
    // Função para desenhar a logo diretamente usando Canvas
    function getLogoBase64() {
      const canvas = document.createElement('canvas');
      canvas.width = 400;
      canvas.height = 200;
      const ctx = canvas.getContext('2d');

      // Sol Amarelo
      ctx.fillStyle = '#f1c40f';
      ctx.beginPath();
      ctx.arc(120, 55, 24, 0, Math.PI * 2);
      ctx.fill();

      // Montanha Esquerda
      ctx.fillStyle = '#27ae60';
      ctx.beginPath();
      ctx.moveTo(80, 115);
      ctx.lineTo(110, 75);
      ctx.lineTo(140, 115);
      ctx.closePath();
      ctx.fill();

      // Montanha Centro
      ctx.fillStyle = '#2e7d32';
      ctx.beginPath();
      ctx.moveTo(120, 115);
      ctx.lineTo(160, 50);
      ctx.lineTo(200, 115);
      ctx.closePath();
      ctx.fill();

      // Montanha Direita
      ctx.fillStyle = '#1b5e20';
      ctx.beginPath();
      ctx.moveTo(170, 115);
      ctx.lineTo(210, 60);
      ctx.lineTo(250, 115);
      ctx.closePath();
      ctx.fill();

      // Textos
      ctx.fillStyle = '#1a252f';
      ctx.font = 'bold 15px Arial';
      ctx.fillText('— MARMORARIA —', 90, 132);

      ctx.font = 'bold 26px Arial';
      ctx.fillText('PEDRAS DO VALE', 40, 162);

      return canvas.toDataURL('image/png');
    }

    document.getElementById('orcamentoForm').addEventListener('submit', async function(e) {
      e.preventDefault();

      const { PDFDocument, rgb, StandardFonts } = PDFLib;

      const nome = document.getElementById('nome').value;
      const telefone = document.getElementById('telefone').value;
      const cidade = document.getElementById('cidade').value;
      const endereco = document.getElementById('endereco').value;

      const material = document.getElementById('material').value;
      const acabamento = document.getElementById('acabamento').value;
      const frontao = document.getElementById('frontao').value || 'N/A';
      const saia = document.getElementById('saia').value || 'N/A';
      const complemento = document.getElementById('complemento').value || 'N/A';
      const materiais = document.getElementById('materiais').value || 'N/A';

      const pagAvista = document.getElementById('pag_avista').value;
      const pagCartao = document.getElementById('pag_cartao').value;
      const valorTotal = document.getElementById('valor_total').value;

      try {
        const pdfDoc = await PDFDocument.create();
        const page = pdfDoc.addPage([595.28, 841.89]); // A4 Standard
        
        const font = await pdfDoc.embedFont(StandardFonts.Helvetica);
        const fontBold = await pdfDoc.embedFont(StandardFonts.HelveticaBold);

        const black = rgb(0, 0, 0);
        const darkGray = rgb(0.15, 0.15, 0.15);
        const lightGray = rgb(0.92, 0.92, 0.92);

        const drawBox = (x, y, width, height, borderWidth = 1.2) => {
          page.drawRectangle({
            x, y, width, height,
            borderColor: black,
            borderWidth: borderWidth
          });
        };

        // --- 1. CABEÇALHO COM LOGO NO CANTO SUPERIOR DIREITO ---
        drawBox(25, 735, 545, 80, 1.5);
        
        page.drawText('ORÇAMENTO - MARMORARIA PEDRAS DO VALE', { x: 35, y: 790, size: 13, font: fontBold, color: black });
        page.drawText('CNPJ: 68.952.061/0001-92', { x: 35, y: 770, size: 10, font: fontBold, color: darkGray });
        page.drawText('CONTATO: (12) 99221-0262 / (12) 92000-3358', { x: 35, y: 750, size: 10, font: fontBold, color: darkGray });

        // Desenha a Logo sem Fundo Preto no Canto Superior Direito
        const logoDataUrl = getLogoBase64();
        const logoImage = await pdfDoc.embedPng(logoDataUrl);
        page.drawImage(logoImage, {
          x: 425,
          y: 740,
          width: 135,
          height: 68
        });

        // --- 2. DADOS DO CLIENTE ---
        let y = 705;
        page.drawText('DADOS DO CLIENTE', { x: 25, y, size: 12, font: fontBold, color: black });
        
        y -= 45;
        drawBox(25, y, 545, 38);
        page.drawText(`Nome: ${nome}`, { x: 35, y: y + 13, size: 11, font: fontBold, color: black });
        page.drawText(`Telefone: ${telefone}`, { x: 360, y: y + 13, size: 11, font: fontBold, color: black });
        page.drawLine({ start: { x: 350, y }, end: { x: 350, y: y + 38 }, thickness: 1.2, color: black });

        y -= 38;
        drawBox(25, y, 545, 38);
        page.drawText(`Endereço da Obra: ${endereco}`, { x: 35, y: y + 13, size: 11, font: fontBold, color: black });
        page.drawText(`Cidade: ${cidade}`, { x: 360, y: y + 13, size: 11, font: fontBold, color: black });
        page.drawLine({ start: { x: 350, y }, end: { x: 350, y: y + 38 }, thickness: 1.2, color: black });

        // --- 3. TABELA DE SERVIÇOS ---
        y -= 30;
        page.drawText('DESCRIÇÃO DO SERVIÇO / PEÇAS', { x: 25, y, size: 12, font: fontBold, color: black });

        // Cabeçalho Tabela
        y -= 30;
        page.drawRectangle({ x: 25, y, width: 545, height: 28, color: lightGray });
        drawBox(25, y, 545, 28, 1.2);
        
        page.drawText('ITEM', { x: 35, y: y + 8, size: 11, font: fontBold, color: black });
        page.drawText('DESCRIÇÃO DO SERVIÇO / PEÇA', { x: 85, y: y + 8, size: 11, font: fontBold, color: black });
        page.drawText('VALOR', { x: 475, y: y + 8, size: 11, font: fontBold, color: black });

        // Conteúdo Tabela
        y -= 175;
        drawBox(25, y, 545, 175, 1.2);
        
        page.drawText('01', { x: 40, y: y + 145, size: 11, font: fontBold, color: black });

        page.drawText(`• Material: ${material}`, { x: 85, y: y + 145, size: 11, font: fontBold, color: black });
        page.drawText(`• Acabamento: ${acabamento}`, { x: 85, y: y + 115, size: 10.5, font, color: black });
        page.drawText(`• Frontão: ${frontao}   |   • Saia: ${saia}`, { x: 85, y: y + 85, size: 10.5, font, color: black });
        page.drawText(`• Complemento: ${complemento}`, { x: 85, y: y + 55, size: 10.5, font, color: black });
        page.drawText(`• Materiais/Instalação: ${materiais}`, { x: 85, y: y + 25, size: 10.5, font, color: black });

        page.drawText(valorTotal, { x: 460, y: y + 145, size: 12, font: fontBold, color: black });

        // Divisórias da Tabela
        page.drawLine({ start: { x: 75, y }, end: { x: 75, y: y + 203 }, thickness: 1.2, color: black });
        page.drawLine({ start: { x: 445, y }, end: { x: 445, y: y + 203 }, thickness: 1.2, color: black });

        // --- 4. VALOR TOTAL ---
        y -= 38;
        page.drawRectangle({ x: 25, y, width: 545, height: 38, color: lightGray });
        drawBox(25, y, 545, 38, 1.5);
        
        page.drawText('VALOR TOTAL DO ORÇAMENTO:', { x: 35, y: y + 13, size: 12, font: fontBold, color: black });
        page.drawText(valorTotal, { x: 445, y: y + 12, size: 14, font: fontBold, color: black });

        // --- 5. CONDIÇÕES DE PAGAMENTO ---
        y -= 60;
        drawBox(25, y, 545, 50, 1.2);
        
        page.drawText('FORMA DE PAGAMENTO', { x: 35, y: y + 32, size: 11, font: fontBold, color: black });
        let pagTexto = '';
        if (pagAvista) pagTexto += `À Vista/PIX: ${pagAvista}  `;
        if (pagCartao) pagTexto += `Cartão: ${pagCartao}`;
        page.drawText(pagTexto || 'Conforme alinhado com o vendedor', { x: 35, y: y + 12, size: 10, font, color: black });

        page.drawText('PRAZO DE ENTREGA', { x: 320, y: y + 32, size: 11, font: fontBold, color: black });
        page.drawText('20 dias úteis após confirmação do', { x: 320, y: y + 18, size: 9, font, color: darkGray });
        page.drawText('pagamento e medição final.', { x: 320, y: y + 6, size: 9, font, color: darkGray });
        page.drawLine({ start: { x: 310, y }, end: { x: 310, y: y + 50 }, thickness: 1.2, color: black });

        // --- 6. OBSERVAÇÕES ---
        y -= 175;
        drawBox(25, y, 545, 165, 1.2);
        page.drawText('OBSERVAÇÕES', { x: 35, y: y + 145, size: 11, font: fontBold, color: black });

        const obs = [
          '01. O orçamento é válido por 07 dias a contar desta data.',
          '02. As medidas deverão ser confirmadas antes do início da fabricação.',
          '03. Produtos confeccionados sob medida poderão apresentar variações naturais de tonalidade e veios.',
          '04. Alterações solicitadas após a aprovação do orçamento poderão gerar custos adicionais e alteração de prazo.',
          '05. Após a aprovação e o início da fabricação, o cancelamento estará sujeito às condições previstas no contrato.'
        ];

        let obsY = y + 120;
        obs.forEach(text => {
          page.drawText(text, { x: 35, y: obsY, size: 8.5, font, color: darkGray });
          obsY -= 23;
        });

        // --- ASSINATURA E IDENTIFICAÇÃO FINAL ---
        page.drawText('MARMORARIA PEDRAS DO VALE - CNPJ: 68.952.061/0001-92', { x: 135, y: 35, size: 10, font: fontBold, color: black });
        page.drawText('Contato: (12) 99221-0262 / (12) 92000-3358', { x: 195, y: 20, size: 9, font, color: darkGray });

        const pdfBytes = await pdfDoc.save();
        download(pdfBytes, `Orcamento_Pedras_do_Vale_${nome.replace(/\s+/g, '_')}.pdf`, "application/pdf");

      } catch (err) {
        alert('Erro ao gerar o PDF: ' + err.message);
      }
    });
  </script>
</body>
</html>

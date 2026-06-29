<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <title>Key Generator - d10 Hub</title>
    <style>
        body { background-color: #0c0c0d; color: #ffffff; font-family: 'Segoe UI', Arial, sans-serif; text-align: center; padding-top: 80px; }
        .box { background-color: #131316; border: 1px solid #36175e; display: inline-block; padding: 30px; border-radius: 12px; box-shadow: 0px 0px 20px rgba(138, 43, 226, 0.2); }
        .key { font-size: 22px; font-weight: bold; color: #a020f0; margin: 20px 0; padding: 10px; background: #1c1c24; border-radius: 6px; border: 1px dashed #8a2be2; letter-spacing: 1px; }
        .footer-text { color: #5c5c6d; font-size: 12px; margin-top: 15px; }
    </style>
</head>
<body>
    <div class="box">
        <h2>🔑 Gerador de Chaves d10 Hub</h2>
        <p>Sua chave exclusiva foi gerada com sucesso e expira em 24h:</p>
        <div class="key" id="key-box">Buscando ID...</div>
        <p class="footer-text">Esta chave só funciona na sua conta do Roblox.</p>
    </div>

    <script>
        // Função para pegar o ID enviado pelo link
        const urlParams = new URLSearchParams(window.location.search);
        const userId = urlParams.get('userid');

        if (userId) {
            // Pega a data de hoje (Fuso local)
            const data = new Date();
            const dia = String(data.getDate()).padStart(2, '0');
            const mes = String(data.getMonth() + 1).padStart(2, '0');
            const dataFormatada = dia + mes;

            // Faz a mesma conta matemática secreta do script
            const contaSecreta = (parseInt(userId) * 2) + 500;
            
            // Exibe a chave na tela
            document.getElementById("key-box").innerText = `d10_${contaSecreta}_${dataFormatada}`;
        } else {
            document.getElementById("key-box").innerText = "Erro: Execute o script pelo Roblox para gerar a key.";
            document.getElementById("key-box").style.color = "#ff3333";
        }
    </script>
</body>
</html>

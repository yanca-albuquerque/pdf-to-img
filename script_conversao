import fitz
import os

# Caminhos
caminho_pdf = r"C:\Users\Yanca\Documents\testes.pdf"
pasta_saida = r"C:\Users\Yanca\Documents\testes_Imagens"

# Criar a pasta de saída se não existir
if not os.path.exists(pasta_saida):
    os.makedirs(pasta_saida)

# Abrir o PDF
doc = fitz.open(caminho_pdf)

# Definir a qualidade 
zoom = 3.0 
matriz = fitz.Matrix(zoom, zoom)

print(f"Iniciando conversão de {len(doc)} páginas...")

# Iterar pelas páginas e salvar como imagem
for i in range(len(doc)):
    pagina = doc.load_page(i)
    pix = pagina.get_pixmap(matrix=matriz)
    
    nome_arquivo = f"img_{i + 1}.png"
    caminho_final = os.path.join(pasta_saida, nome_arquivo)
    
    pix.save(caminho_final)
    print(f"Salvo: {nome_arquivo}")

doc.close()
print("Concluído! Verifique os arquivos na pasta:", pasta_saida)

# Documentos de Maracanaú

Documentos extraídos a partir do portal da câmara de Maracanaú

Existem atualmente três objetivos para o projeto

1. Tornar os documentos referentes a leis pesquisáveis. Atualmente parte dos documentos
disponibilizados são PDFs ou imagens não pesquisáveis e indexáveis;
2. Permitir a indexação do google e outros motores de busca de termos e pessoas antigos 
que fizeram parte da nossa sociedade.

## Instalação

Instalação das ferramentas necessárias para a execução dos downloads dos arquivos públicos 
e o processamento para a obtenção do texto.

1. Instale o Tesseract OCR: https://github.com/tesseract-ocr/tesseract/wiki
```
sudo snap install --channel=edge tesseract
```
2. Coloque o modelo LSTM treinado para português em `~/snap/tesseract/common`
```
# Atualmente exitem três versões: tessdata, tessdata_best e tessdata_fast 
# Mude a url conforme queira
cd ~/snap/tesseract/common
## Inglês
wget https://github.com/tesseract-ocr/tessdata_best/raw/master/eng.traineddata
wget https://github.com/tesseract-ocr/tessdata_best/raw/master/por.traineddata
```
3. Verifique se as línguas instaladas
```
tesseract --list-langs
```
4. Configurar ambiente de desenvolvimento
```
cd <projeto clonado>
python -m venv venv
source venv/bin/activate
python setup.py develop
```
5. Abrir Jupyter lab
```
jupyter lab --core-mode 
```
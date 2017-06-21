# automation-with-autoit
Automação de testes utilizando Ruby, Watir-Webdriver e AutoIT


Para usar os recursos do AutoIT sem precisar criar um arquivo exe no autoit, estamos usando a GEM au3
então vc vai:
-instala a gem "gem install au3"
-Não precisa ter o autoit instalado, você so precisa de duas DLL que tem na pasta de instalação do autoit AutoItX3.dll ou AutoItX3_x64.dll
-Se a instalação do seu ruby for 32 bits você pega a dll "AutoItX3" e copia para a pasta bin do ruby e registra essa dll no windows
-Essa gem só funciona para ruby 32, + achamos uma forma malandra de reverter isso. Você copia a dll 64bits e muda o nome dela para AutoItX3.dll ai ele acha que ta usando o 32
-seguindos esses passos já deve funcionar.

EX:

require 'au3'

def clicar_por_posicao(x, y)
  AutoItX3.mouse_click(x, y, 'left')
end

onde X, Y representa a posição do elemento na tela. Isso você pode pegar com aquela ferramenta de spy do autoit.

Para registrar a DLL vc tem que abrir o cmd como adm e digitar regsvr32 "C:\Ruby23\bin\AutoItX3.dll"

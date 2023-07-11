## Atenção:
# Este é um documento encontrado na internet que tem os provaveis problemas de erros das Placas X99
# se você não sabe o que é isso pesquise antes de qualquer coisa.
# não me responsabilizo por nada, é um documento encontrado e traduzido automaticamente para ajudar a resolver problemas nessas placas.
# se for usar use com cuidado, sabedoria e conciência que não é a verdade absoluta, pode haver casos diferentes dos descritos aqui de acordo com fabricantes diferentes.

--------
Código da placa de diagnóstico da placa-mãe Daquan
Todos os códigos da placa de diagnóstico da placa-mãe
Código: FF, 00, C0, D0, CF, F1 ou nada significa que a CPU falhou;
C1, C6, C3, D3, D4, D6, D8, B0, A7, E1 indicam que a memória não é suficiente;
24, 25, 26, 01, 0A, 0B, 2A, 2B, 31 indicam que a placa gráfica não é boa o suficiente;
Algumas placas-mãe gráficas integradas 23, 24 e 25 indicam que elas podem ser acesas normalmente. Alguns chipsets VIA exibem 13 para indicar que eles podem ser acesos. Algumas placas-mãe exibem 0B para indicar normal, e algumas placas-mãe exibem 4E para indicar normal. Ligadas, algumas placas-mãe dos chipsets INTEL exibem 26 ou 16, o que significa que elas podem ser acesas normalmente.
C1, C6, C3, 01, 02 este salto de ciclo combinado é principalmente I/0 ruim ou escova BIOS
Se ele mostra 05, ED, 41, então fchicotear o BIOS diretamente
Existem três casos de códigos especiais "00", "FF" e outros códigos de início:
1. Se "00" ou "FF" aparecer depois que uma série de outros códigos aparecerem, a placa-mãe está OK.
2. Se não houver erro nas configurações no CMOS, a pequena falha não afetará a continuação da auto-verificação do BIOS e, eventualmente, "00" ou "FF" aparecerão.
3. Se "00" ou "FF" ou outros códigos de partida aparecerem assim que a máquina estiver ligada e não mudarem, isso significa que a placa-mãe não está funcionando.
00 co cf f  fd1 CPU não está funcionando, verifique circuitos relacionados e bios para seleção de chip
c1 c3 c6 a7 e1 são todos memória, mas verifique as rotas relevantes
c1-05 ciclo de salto relógio ruim,  bios ruim, ponte sul ruim ou E / O
c1 c3 c6 memória-bios-ponte norte
bo ponte norte é broken
25 AGP fonte de alimentação, a ponte norte está quebrada
Sem luz após a parte da placa gráfica 0d
2d Pressione a linha AD do AGP, inicialize o sinal intr e verifique a fonte de alimentação da ponte norte
Nenhuma luz depois de mostrar 2b Flash o bios, o gerador de relógio é broken, a fonte de alimentação da ponte norte é anormal ou foi desligado
Fonte de alimentação de 50 E/S ou falha de E/S, fonte de alimentação da ponte sul ou falha da ponte sul, falha da bios
41 Brush bios, A18 jumper. Desconexão de PCB, E/S, ponte sul
Se houver um códigoothe r do que o código acima, é um código ilegível, não importa o que o manual diga, basta piscar a bios primeiro.
Tudo isso é resumido a partir de minhas anotações, mas afinal, alguns códigos não foram encontrados muitas vezes, então não há garantia de que eles estejam corretos.
T o add, sehouver um problema com o programa interno do bios, o código acima pode não ser válido, por isso, se você encontrar códigos incomuns, como ff, c1, é melhor piscar o bios primeiro
c0 2a cpu emitiu instruções de endereçamento, bios não está funcionando
c1 d3 d4 bo cpu funcionou, verificar a memória
26 85 8e 7f 4e 42 32 Detectar Gráficos
c1-05 20 ciclo de salto de E/S é ruim ou a interface está com defeito
31 Falha na placa gráfica
Combinado com o caráter do irmão, vá devagar...

Se for Award BISO, o autoteste de memória não passou, verifique o circuito de controle de memória da placa-mãe e os slots de memória e cartões de memória

Se for Phoenix BISO, verifique se a marca "55, AA" DE no setor de inicialização não tem sentido, pode ser que não haja auto-verificação


Aexplicação detalhada do código da placa de diagnóstico da placa-mãe (tabela de comparação) deve ler:
     1. Existem três casos de códigos especiais "00" e "ff" e outros códigos de início:
     (1) Aparece após uma série de outros códigos: "00" ou "ff", então a placa-mãe está ok.
(2) Se não houver erro no cmos, pequenas falhas não afetarão a continuação da auto-verificação da bios e, eventualmente, "00" ou "ff" aparecerão.
     (3) Se "00" ou "ff" ou outros códigos de partida aparecerem assim que a máquina for ligada e se ela não mudar, isso significa que a placa-mãe não está funcionando.
     2. Esta tabela é classificada de acordo com o valor do código de pequeno para grande, e a ordem dos códigos no cartão é incerta.
     3. Os códigos indefinidos não estão listados na tabela.
4. Diferentes bios (comumente usados ami, award, phoenix) têm significados diferentes representados pelo mesmo código, então você deve descobrir a que tipo de bios o computador que você está testando pertence. Você pode consultar o manual do usuário do seu computador, ou a partir dele pode ser visto diretamente  no chip bios na placa-mãe, ou diretamente na tela de inicialização.
5. Em algumas placas-mãe, apenas uma parte do código aparece no  slot pci, mas o slot isa  tem uma saída de código de auto-verificação completa. E até agora, verificou-se que existemalgumas placas-mãe originais que não têm  saída de código no  slot isa, enquanto o slot pci tem saída de código completa. Portanto, é recomendável que você altere a placa de slot duplo para outro slot para tentar se você não conseguir verificar o código. .  Além disso, para  slots pci diferentes  da mesma placa-mãe, alguns slots têm códigos completos enviados. Por exemplo, na placa-mãe dell810, apenas um  slot pci próximo à cpu tem a exibição de código completa, que muda todo o caminho para "00" ou "ff", enquanto outros  slots pci vão para  Depois de "38", ele não continuará a mudar.
6. O tempo necessário para o sinal de reset isa e  pci não  são necessariamente sincronizados, por isso é possível que isa começa a gerar código,  mas a luz de reset  de pci  não está apagada, então o  código pci pára no códigode início.
Tabela de comparação de código
00 .  Configuração do sistema mostrada; prestes a controlar o carregamento de inicialização do INI19.
01 Teste do processador 1, o estado do processador é verificado, se o teste falhar, o loop é infinito. O teste dos registradores do processador está prestes a começar, eas interrupções não questionáveis estão prestes a ser desativadas. Teste de registro da CPU em andamento ou com falha.
02 Determinar o tipo de diagnóstico (normal ou fabricado). Ele falhará se o buffer do teclado contiver dados. Desabilita interrupções não mascaráveis; começa com um atraso. Agravação/leitura do CMO S está em andamento ou falhou.
03 Limpe o controlador de teclado 8042, emita o atraso de inicialização do comando TESTKBRD (AAH) concluído. ROM BIOS componente de verificação em andamento ou com defeito.
04 Redefina o controlador de teclado 8042 e verifique TESTKBRD. Teclado controller soft reset/power up teste. O teste do temporizador de intervalo programável está em andamento ou falhou.
05 Se os ensaios de fabrico 1 a 5 forem repetidos continuamente, pode obter-se o estado de controlo 8042 . Reinicialização suave/potência em determinado; prestes a iniciar a ROM. O DMA parece estar em preparação ou falha.
06 Inicialmente prepara o die, desabilita o vídeo, a paridade, o dado DMA e limpa o dado DMA, todos os registradores de página e bytes de desligamento do CMOS. A ROM inicializada calcula a soma de verificação do BIOS da ROM e verifica se o buffer do teclado está cleared. Teste de leitura/gravação de registro de página inicial do DMA em andamento ou com falha.
07 Teste de processador 2, para verificar o funcionamento dos registradores da CPU. A soma de verificação do BIOS da ROM está OK, os buffers do teclado são limpos, o comando BAT (Basic Assurance Test) é emitido para o keyboard.
08 Faz a preparação inicial do temporizador CMOS, o ciclo normal de atualização do temporizador. Um comando BAT foi emitido para o teclado e o comando BAT está prestes a ser gravado. A verificação de atualização de RAM está em andamento ou falhou.
09 EPROM verifica a soma e deve ser igual a zero para passar. Verifica o teste de garantia básica do teclado, seguido pela verificação dos bytes de comando do teclado. O primeiro teste de 64K RAM está em andamento.
0A Torna a interface de vídeo inicialmente pronta. Execute o código de byte de comando do teclado para gravar os dados do byte de comando. O primeiro chip de RAM de 64K ou linha de dados falha e muda.
0B Testes 8254 canal 0. Escreva o byte de comando do controlador de teclado, o comando lock/unlock para os pinos 23 e 24 está prestes a ser emitido. A primeira lógica ímpar/ev de RAM de 64Kfalha.
Teste 0C 8254 canal 1. Os pinos do controlador de teclado 23, 24 são bloqueados/desbloqueados; O comando NOP foi emitido. Falha de linha de endereço para a primeira RAN de 64K.
0D 1. Verifique se a velocidade da CPU corresponde ao relógio do sistema. 2. Verifique se ovalue programado do chip de comando está em conformidade com a regulação inicial. 3. Teste do canal de vídeo, se falhar, buzine. O comando NOP foi processado; em seguida, o registro de parada do CMOS é testado. Falha de paridade na primeira RAM de 64K
0E Teste o byte de desligamento do CMOS. O CMOS desativa o teste de leitura/gravação do registro; A soma de verificação do CMOS será calculada. Inicialize endereços de porta de entrada/saída.
Teste 0F CMOS estendido. A soma de verificação do CMOS é calculada e os bytes de diagnóstico são gravados; O CMOS começa a preparação inicial. .
10 Teste DMA canal 0. O CMOS foi inicialmente preparado, e o registro de status do CMOS está prestes a ser inicialmente preparado para a data e hora. Primeira falha de 64K RAM bit 0.
11 Teste DMA canal 1. O registro de status do CMOS está inicialmente pronto para desabilitar o DMA e o controlador de interrupção. A primeira falha de 64DK RAM bit 1.
12 Teste o registro de página DMA. Desative o controlador DMA 1 e interrompa os controladores 1 e 2; ou seja, exibir vídeo e tornar a porta B inicial. Primeira falha de 64DK RAM bit 2.
13 Teste a interface do controlador de teclado 8741 . Displa de vídeoy desativado, porta B inicializada; inicialização de matriz/detecção automática de memória prestes a começar. Primeira falha de 64DK RAM bit 3.
14 Teste o circuito de disparo de atualização de memória. A inicialização/detecção automática de matrizes na memória acabou; O teste do temporizador 8254  está prestes a começar. Primeira falha de 64DK RAM bit 4.
15 Teste os primeiros 64K de memória do sistema. O temporizador do canal 2 está a meio do caminho; o temporizador do canal 2 8254 está prestes a completar o teste. A primeira falha de 64DK RAM bit 5.
16 Construa a tabela de vetores de interrupção usada pelo 8259. O teste do temporizador do 2º canal terminou; o temporizador do 1º canal 8254 está prestes a concluir o teste. A primeira falha do bit 6 de RAM 64DK.
17 Ajuste a entrada/saída de vídeo para funcionar, ativado se o BIOS de vídeo estiver instalado. O teste do temporizador do 1º canal terminou; o temporizador do 0º canal 8254 está prestes a concluir o teste. Primeira falha de 64DK RAM bit 7.
18 Teste a memória de vídeo, se o BIOS de vídeo opcional estiver instalado, ele poderá ser ignorado. O teste do temporizador do Canal 0 terminou; a atualização de memória está prestes a começar. A primeira RAM 64DK falhou no bit 8.
19 Test the interrupt controller (8259) mask bit for channel 1. A atualização de memória foi iniciada e a atualização de memória será concluída. A primeira 9ª falha de RAM 64DK RAM.
1A Testa o bit de máscara do controlador de interrupção (8259) para o canal 2. Acionando a linha de atualização de memória, about para verificar 15μs on / off time. A primeira RAM 64DK falhou no bit 10.
Nível de bateria CMOS de teste 1B. Tempo de atualização de memória finalizado teste de 30 microssegundos; prestes a iniciar o teste básico de memória de 64K. A primeira falha de RAM 64DK no bit 11.
Soma de verificação do CMOS de teste 1C. .  Primeira falha de 64DK RAM bit 12.
1D Define a configuração do CMOS. .  Primeira falha de 64DK RAM bit 13.
1E Meça o tamanho da memória do sistema e compare-o com o valor CMOS. .  O 14º bit da primeira RAM 64DK falhou.
1F Teste de memória 64K até 640 K..  Primeira falha de 64DK RAM bit 15.
20 Meça os 8259 bits de interrupção fixos. Inicia um teste básico de memória de 64K; testará as linhas de endereço. Teste de registro DMA escravo em andamento ou com falha.
21 Manter o bit de interrupção não mascarável (NMI) (paridade ou verificação do canal de entrada/saída). Passe em umteste de linha de vestimenta; a paridade está prestes a ser acionada. Teste de registro DMA principal em andamento ou com falha.
22 Testar a função de interrupção do 8259. Paridade de gatilho final; o teste de leitura/gravação de dados seriais começará. O teste de registro de máscara de interrupção principal está em andamento ou falhou.
23 Teste o modo de proteção 8086 modo virtual e o modo de página 8086 . Teste básico de leitura/gravação de dados seriais de 64K OK; prestes a iniciar quaisquer ajustes antes de interromper a inicialização do vetor. O teste de máscara de interrupção escrava está em andamento ou falhou.
24 Measure a memória de expansão de 1MB ou mais. Qualquer ajuste antes da inicialização do vetor está concluído e a preparação inicial do vetor de interrupção está prestes a começar. Defina o registro de registro de endereço de segmento ES para a extremidade superior da memória.
25 Teste toda a memória após os primeiros 64K. Conclua a preparação inicial do vetor de interrupção; a porta de entrada/saída do 8042 será lida para a interrupção rotativa. O carregamento do vetor de interrupção está em andamento ou falhou.
26 Excepções aos métodos de protecção de ensaio. Leia a porta de entrada/saída do 8042; prestes a fazer os preparativos iniciais para o início do soluço rotativo. Ative a linha de endereço A20; fazê-lo participar do endereçamento.
27 Determine a RAM de controle ou máscara para o cache. Os dados de todos os dadosi preparação inicial terminam; qualquer preparação inicial após o vetor de interrupção seguirá. O teste do controlador de teclado está em andamento ou falhou.
28 Determine o controle de cache ou o controlador de teclado 8042 especial. A preparação inicial após a conclusão do vetor de interrupção; o modo monocromático está prestes a ser definido. Cálculo de falha de energia/soma de verificação do CMOS em andamento.
29. O modo monocromático foi definido e o modo de cor está prestes a ser definido. Uma verificação da validade da configuração do CMOS está em andamento.
2A prepara o controlador de teclado para a preparação inicial. O modo de cor é definido, acione a paridade pouco antes do teste da ROM. Esvazie a memória base de 64K.
2B faz a preparação inicial da unidade de disco e do controlador. Fim da paridade do gatilho; prestes a controlar quaisquer ajustesnecessários antes da verificação opcional da ROM de vídeo. Teste de memória de tela em andamento ou com falha.
2C Verifique a porta serial e faça a preparação inicial. Processamento concluído antes do controle da ROM de vídeo; prestes a visualizar e controlar ROMs de vídeo opcionais. A tela napreparação inicial está em andamento ou falhou.
O 2D detecta a porta paralela e a torna inicialmente pronta. O controle opcional da ROM de vídeo foi concluído e está prestes a assumir o controle de qualquer outro processamento após o controle de restauração da ROM de vídeo. Teste de retraçãode tela em andamento ou com falha.
2E Faz a preparação inicial de unidades de disco rígido e controladores. Recuperação do processamento após o controle de ROM de vídeo; teste de leitura/gravação de memória do monitor se EGA/VGA não for encontrado. A detecção de ROM de vídeo está em andamento.
2F Detecta o coprocessador matemático e o torna inicialmente pronto. EGA/VGA não encontrado; prestes a iniciar o teste de leitura/gravação de memória do monitor. .
30 Criar memória base e memória estendida. Passou no teste de leitura/gravação de memória do monitor; verificar a varredura em breve. Pense que a tela está funcionando.
31 Check a ROM opcional de C800:0 para EFFF:0 e fazê-lo para a preparação inicial. Falha no teste de leitura/gravação de memória de exibição ou na verificação de varredura, outro teste de leitura/gravação de memória de exibição está prestes a ocorrer. Monitores monocromáticos funcionarão.
32 Programe os chips de E/S, comodispositivos C OM/LTP/FDD/sound, na placa-mãe para se adequar aos valores de configuração. Passar em outro teste de leitura/gravação de memória do monitor; fará outra verificação de varredura do monitor. Monitores coloridos (40 colunas) estão disponíveis.
33. Verificação do monitor de vídeo concluída; começará a verificar o tipo de monitor off com interruptor de ajuste e cartão real. Monitores coloridos (80 colunas) funcionarão.
34. O adaptador de vídeo foi verificado; o visor será então ajustado. Um teste de interrupção de tick do temporizador está em andamento ou falhou. 35. Termine de configurar o display mode; prestes a verificar a área de dados da ROM do BIOS. Um teste de desligamento está em andamento ou falhou.
36. A área de dados da ROM do BIOS foi verificada; o cursor para informações de ativação está prestes a ser definido. Falha do A-20 no circuito do portão.
37. A configuração do cursor para identificar as informações de ativação está completa; as informações de ativação serão exibidas. Interrupção inesperada no modo de proteção.
38. Terminada a exibição da mensagem de ligar; a nova posição do cursor está prestes a ser lida. Teste de RAM em andamento ou falha de endereçoe > FFFFH.
39. A posição do cursor salva foi lida e a cadeia de caracteres de referência será exibida. .
3A .  O final da cadeia de caracteres de referência é exibido; as informações de descoberta estão prestes a ser exibidas. O canal 2 do temporizador de intervalo foi testado ou falhou.
3B Inicializas o cache secundário com a matriz OPTI (somente 486). Encontrada <ESC> mensagem exibida; modo virtual, o teste de memória está prestes a começar. O teste de relógio do calendário do dia-a-dia está em andamento ou falhou.
3C Estabelece o sinalizador que permite a entrada na configuração do CMOS. .  Seteste de porta rial em andamento ou falhou.
3D Inicialize o teclado/mouse PS2/dispositivo PNP e o nó de memória total.  Teste de porta paralela em andamento ou com falha.
3E Tente abrir o cache L2. .  Teste de coprocessador matemático em andamento ou com falha.
40. A preparação parao teste mod e virtual já começou; a ser verificado a partir da memória de vídeo. Ajuste a velocidade da CPU para corresponder exatamente ao relógio periférico.
41 Interrupção ativada, inicializará dados para detecção 0:0 de alteração de memória (controlador de interrupção ou memória defeituosa) Restaurando a partir de vídeo memory check; prestes a preparar a tabela de descritores. Falha na seleção do quadro do sistema.
42 A janela de exibição vai para SETUP. A tabela de descritores está pronta; teste de memória no modo virtual em breve. Falha de RAM CMOS estendida.
43 Se o BIOS for plug and play, a porta serial e a porta parallel serão inicializadas. Entrando no modo virtual; prestes a implementar uma interrupção para o modo de diagnóstico. .  44. Interrupção implementada (por exemplo, interruptor de diagnóstico ligado; prestes a fazer a preparação inicial de dados para verificar a substituição da memória às 0:0.) Interrupção do BIOS para inicializar.
45 Inicialize o coprocessador matemático. Os dados foram inicialmente preparados; prestes a verificar a sobreposição de memória em 0:0 e descobrir o tamanho da memória do sistema. .
46. A memória de teste retornou; o tamanho da memória foi calculado, a  página está  prestes a ser gravada para testar a memória.  Verifique a versão da ROM de memória somente leitura.
47. Prestes a tentar escrever uma página na memória estendida; prestes a gravar a página na memória básica de 640K.
48. A memória base foi gravada na página; mais de 1MB de memória serão determinados. Inspeção de vídeo, reconfiguração de CMOS.
49. Encontre a memória abaixo de 1BM e verifique-a; prestes a determinar a memória acima de 1MB. .
4A .  Descubra mais de 1MB de memória e verifique; verificará a área de dados da ROM do BIOS. Inicialize o vídeo.
4ºB. A verificação da área de dados da ROM do BIOS é concluída e o <ESC> será verificado e a memória acima de 1MB será limpa para reinicialização suave.  4° C . Limpar mais de 1MB de memória  (soft reset) limpará mais de 1MB de memória. Proteja o vídeo BIOS ROM. . 4ºD. Mais de 1MB de memória foi limpo (soft reset); o tamanho da memória será salvo. .
4E Se um erro for detectado; exibir a mensagem de erro no visor e aguarde até que o cliente pressione a tecla <F1> para continuar. Inicie o teste de memória: (sem redefinição suave); mostrará o primeiro teste de memória de 64K. Exibir informações de direitos autorais.
4F Ler e gravar software e dados do disco rígido, e executar a inicialização do DOS. Começa a exibir o tamanho da memória, a memória que está sendo testada irá atualizá-lo; serão realizados testes de memorandos seriados e aleatórios.
50 Armazene o valor do CMOS no fuso horário de monitoramento do BIOS atual no CMOS. Completar testes de memória com menos de 1MB; ou seja, o tamanho da memória de alta velocidade para realocação e mascaramento. Envie o tipo de CPU e a velocidade para a tela.
51. Teste a memória acima de 1MB. .
52 Todas as ROMs de memória somente leitura do ISA são inicializadas e, finalmente, o PCI recebe o número IRQ e outros trabalhos de inicialização. Concluído o teste de memória de 1MB ou mais; prestes a retornar ao modo de endereço real. Digite a detecção de teclado.
53 Se não for um BIOS plug and play, inicialize a porta serial, a porta paralela e defina o valor de tempo. Salve o tamanho dos registradores de CPU e memória, entrará no modo de endereço real. .
54. O modo de endereço real é ativado com êxito; os registros salvos ao se preparar para parar estão prestes a ser restaurados. Digitalizar "Blow Keys"
55. O registo foi reposto e a linha de endereço do portão A-20 será desativada.
56. Desativou com sucesso as linhas de endereço A-20; prestes a verificar a área de dados da ROM do BIOS. O teclado test acabou.
57. Área de dados da ROM do BIOS verificada a meio caminho; prossiga. .
58. A verificação da área de dados da ROM do BIOS terminou; a mensagem <ESC> encontrada será apagada. Teste de quebra sem configuração.
59. <ESC> mensagem desmarcada; mensagem exibida; Os testes de DMA e controlador de interrupção estão prestes a começar.
5A .  . Pressione a tecla "F2" para definir.
5B .  . Teste o endereço de memória base.
5°C .  . Teste a memória base de 640K.
60 Configurar a proteção contra vírus do setor de inicialização do disco rígido. Aprovado no teste de registro de página DMA; prestes a verificar a memória de vídeo. Teste de memory estendido.
61 Exibe a tabela de configuração do sistema. Verificação de memória de vídeo concluída; O teste de registro de base DMA#1 está prestes a começar.
62 Inicie a inicialização do sistema com a interrupção 19H. Aprovado no teste do registro base DMA#1; teste de DMA # 2 registrar  em breve. Teste as linhas de endereço de memória estendidas.
63. Passe no teste de registro básico DMA#2; verificará a área de dados da ROM do BIOS. .
64. A área de dados da ROM do BIOS foi verificada a meio caminho e prosseguiu. .
65. Verificação da área de dados da ROM do BIOS concluída; Os dispositivos DMA 1 e 2 serão programados.
66. Os dispositivos DMAs 1 e 2 estão programados; prestes a usar o controlador de interrupção nº 59 para a preparação inicial. Registro de cache para configuração otimizada.
67. 8259 preparativos iniciais terminaram; o teste de teclado está prestes a começar. .
68 .  . Faça o Cache externo e o Cache interno da CPU funcionarem.
6A .  . Teste e exiba valores de Cache externos.
6° C .  . Mostrar conteúdo bloqueado.
6E .  . Exibe informações de configuração auxiliar.
70 .  . O código de erro detectado é enviado para a tela para exibição.
72 .  . Verifique se há erros de configuração.
74 .  . Teste o relógio em tempo real.
76 .  . Verificar se há erros de teclado.
7A .  . Bloqueie o teclado.
7° C .  . Configure o vetor de interrupção de hardware.
7E .  . Teste para processadores matemáticos instalados.
80. O teste de teclado começa, limpando e verificando se há teclas presas, prestes a restaurar o teclado. Desligue os dispositivos programáveis de entrada/saída.
81. Encontre a tecla presa errada para a recuperação do teclado; prestes a emitir um comando de teste para a porta de controle do teclado. .
82. O teste de interface do controlador de teclado terminou, prestes a escrever o comm ebyte e fazer a preparação inicial do buffer circular. Detecção e instalação de interface RS232 fixa (porta serial).
83. O byte de comando foi escrito e a preparação inicial dos dados globais foi concluída; prestes a verificar se há key lock. .
84. Verificado se há chaves bloqueadas, prestes a verificar se há incompatibilidade de memória com CMOS. Verifique e instale a porta paralela fixa. 85. Tamanho da memória verificado; erros de software e arranjos de senha ou bypass estão prestes a ser exibidos. .
86. Senha verificada; O agendamento pré-bypass está prestes a acontecer. Reabra dispositivos de E/S programáveis e detecte conflitos de E/S fixos.
87. Conclusão da programação pré-acordo; a programação do acordo CMOS prosseguirá. .
88. Redefina a tela transparente do agendador CMOS; Aprogramação subsequente será realizada. Inicialize a área de dados do BIOS.
89. Conclusão da programação pós-programação; mensagem de tela de inicialização será exibida. .
8A .  Exiba as informações da primeira tela. Inicialize a área de dados estendida do BIOS.
8B .  Mensagem exibida: O BIOS principal e de vídeo será bloqueado em breve. .
8º. Depois de mascarar com sucesso o BIOS principal e de vídeo, a programação das opções de arranjo pós-CMOS começará. Inicialize o controlador da unidade de disquete.
8º. A programação opcional foiprogramada, em seguida, verifique o mouse e faça a preparação inicial.
8E .  Mouse detectado e preparação inicial concluída; discos rígidos e disquetes estão prestes a ser redefinidos. .
8F .  O disquete foi verificado, o disco será inicialmente preparado e, em seguida, equipadocom um disquete.
90. A configuração do disquete está concluída; testará a presença do disco rígido. O controlador de disco rígido é inicializado.
91. O teste de presença do disco rígido terminou; o disco rígido é então configurado. Inicialização do cilindro de cont do disco rígido dobarramento local.
92. A configuração do disco rígido está concluída; a área de  dados da ROM do BIOS está prestes a ser verificada. Vá para o caminho do usuário 2.
93. A área de  dados da ROM do BIOS foi verificada no meio do caminho; prossiga. .
94. Depois de verificar a área de dados da ROM do BIOS, o tamanho da memória básica e estendida é definido. Feche a linha de endereço A-20. 95. Ajuste o tamanho da memória para suporte a mouse e disco rígido tipo 47; a memória de exibição será verificada em breve. .
96. Restaure depois de verificar a memória de exibição; a preparação inicial antes de C800:0 o controle de ROM opcional está prestes a ser realizado. O registro "segmento ES" é limpo.
97. C800:0 Quaisquer preparações iniciais antes que o controle de ROM opcional seja concluído, seguido de inspeção e controle de ROM opcionais. .98. Controle o f ROM opcionalcompleto; qualquer processamento necessário após o controle de recuperação de ROM opcional está prestes a ser executado. Localizar seleção ROM.
99. Qualquer preparação inicial exigida após a conclusão do ensaio de ADM opcional; a área de dados do temporizador ou do endereço base da impressora está prestes a ser estabelecida. .
9ºA. Retornar a operação após a configuração do temporizador e do endereço base da impressora; ou seja, definir o endereço base RS-232. Seleção de ROM de máscara.
9B .  Retorna após o endereço base RS-232; prestes a realizar os preparativos iniciais para o teste de coprocessor. .
9° C .  A preparação inicial necessária antes que o teste do coprocessador seja concluído; em seguida, o coprocessador é inicialmente preparado. Estabeleça um gerenciamento de economia de energia.
9ºD. O coprocessador está pronto para quaisquer preparações iniciais imediatamente após oteste do coprocessador.
9º. Após a preparação inicial do coprocessador, o teclado estendido, o identificador do teclado e o bloqueio numérico serão verificados. Abra as interrupções de hardware.
9º. O teclado estendido foi verificado, o sinalizador de identificaçãoi s definido, o bloqueio numérico está ligado ou desligado e o comando de identificação do teclado será emitido.
A0. Emitir um comando de identificação do teclado; o sinalizador de identificação do teclado está prestes a ser redefinido. Defina a hora e a data.
A1. O sinalizador de identificação do teclado é restaurado; em seguida, um teste da memória cache é realizado.
A2. O teste de cache acabou; quaisquer erros de software estão prestes a ser exibidos. Verifique o bloqueio do teclado.
A3. A exibição de erro suave está concluída; a taxa de acerto do teclado está prestes a ser definida. .
A4. Adjust a taxa de greve do teclado, e o estado de espera da memória está prestes a ser estabelecido. Inicialização da taxa de entrada de repetição do teclado.
A5. O estado de espera da memória foi estabelecido; a tela será então limpa. .
A6. A tela está limpa; paridade e interrupções não mascaráveis estão prestes a começar. .
A7. Interrupções não mascaráveis e paridade habilitada; qualquer preparação inicial necessária para controlar a ROM opcional em E000:0 está prestes a acontecer. .
A8. A preparação inicial da ADM de controlo antes de E000:0 is over, e qualquer preparação inicial necessária após E000:0 serão então controlados. Desmarque o prompt de tecla "F2".
A9. Retorno do Controle E000:0 ROM, que está prestes a fazer todos os preparativos iniciais necessários após o controle E000:0 ROM opcional. .
AA. A preparação inicial após E000:0 controla as extremidades opcionais da ROM; a configuração do sistema está prestes a ser exibida. Escaneie a tecla "F2" a ser atingida.
AC ..  vá para configurações.
AE.  . Desmarque o sinalizador POST.
B0 .  . Verifique se há erros não críticos.
B2 .  . POST completo e ready para inicializar no sistema operacional.
B4 .  . A campainha soa uma vez.
B6 .  . Detectar configurações de senha (opcional).
B8 .  . Limpe todas as tabelas de descrição.
A.C.  . Desmarque o valor de verificação de verificação.
O valor padrão do programa BE entra no chip de controle, que está em conformidade com a tabela de valores padrão binários modulados. .  Limpe a tela (opcional).
BF Teste CMOS valor de liquidação. .  Detectar vírus, solicitar o backup de dados.
C0 inicializa o cache. .  Tente inicializar com a interrupção 19.
Autoteste de memória C1. .  Olhe para fou para as marcas "55" "AA" no setor de inicialização.
C3 primeiro teste de memória de 256K. . .
C5 Copie o BIOS da ROM para um autoteste rápido. . .
Autoteste de cache C6. . .
A autoridade de certificação detecta o cache Micronies (se houver) e o prepara inicialmente. . . .
CC desliga omanipulador i nterrupt não mascarável. . . .
Exceção inesperada para processadores EE. . .
FF dá controle ao carregador de inicialização INI19, placa-mãe OK
![image](https://github.com/luizsnike/placas_x99_codigos_erros/assets/60113208/4a48441e-92ec-491d-945d-3a436f06665b)

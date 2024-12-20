# txt

* Análise do Diodo Varactor
.title Análise do Diodo Varactor
Vin 1 0 PULSE(0 0.1 0 1n 1n 60n 120n)   
Vp 2 0 DC 5.94                           
R1 1 3 1k                                
D1 3 2 SMV1493                           

.model SMV1493 D (IS=1e-14 RS=0.1 N=1.024 CJ0=2.8e-11 VJ=0.63 M=0.47 BV=100 IBV=1e-3)

.tran 0.1n 60n

.control
set color0=white          ; cor do fundo
set xbrushwidth=2         ; espessura da linha
run
plot v(3) v(1) title 'Resposta do Diodo Varactor' xlabel 'Tempo (s)' ylabel 'Tensão (V)'
.endc

.end

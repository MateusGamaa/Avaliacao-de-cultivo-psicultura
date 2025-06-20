# Avaliacao-de-cultivo-psicultura

import streamlit as st

st.title("INFOPESC")

st.subheader(
  "Você já conhece os fatores físico-químicos e o que eles podem alterar em sua psicultura ou carcinicultura, não? então vem aprender conosco!"
)

col1, col2, col3 = st.columns(3)

with col1:
  st.subheader('Oxigênio Dissolvido (O²)')
  st.image("Oxigenio.jpg")

with col2:
  st.subheader('Potencial de Hidrogênio (pH)')
  st.image("Kub_Figura02b.jpg")

with col3:
  st.subheader('Temperatura (c°)')
  st.image("4 sonda-mettler.jpg")

st.subheader("A IMPORTÂNCIA DE MONITORAR A QUALIDADE DA ÁGUA NA PISCICULTURA")
st.markdown(
  "Como o objetivo de qualquer criação animal é o crescimento e o conseqüente ganho de peso, a qualidade da água é crucial para diferenciar o lucro do prejuízo na piscicultura. Para que o peixe alcance um bom indice de crescimento, portanto ganhando peso e reduzindo o tempo de cultivo, é imperativo observar que os peixes tenham, além de uma alimentação adequada, uma água de boa qualidade que esteja em condições de suportar a biomassa existente no tanque ou no açude. Então, para se ter conhecimento sobre a água é necessário que seja realizado um monitoramento continuo de sua qualidade, principalmente para as espécies de piracema (tambaqui, matrinxã, curimată, jaraqui, e outras). O acompanhamento e a anotação devem sempre ser uma preocupação constante do piscicultor. O monitoramento tem que ser efetiva nos parâmetros como temperatura, oxigênio dissolvido, transparência, pH, amônia, dureza da água e nutrientes (nitrogênio, fósforo, potássio, cálcio, etc.). São estes os principais fatores que podem ser medidos com uma certa facilidade, necessitando apenas de kits, pois facilitam o trabalho."
)
st.markdown(
  "Existem fatores que não dependem da concentração (densidade) dos peixes nos viveiros e barragens, como temperatura, componentes químicos da água e nebulosidade; outros já são dependentes, como a concentração do oxigênio dissolvido e a presença de residuos dos peixes bem como de rações."
)
st.markdown(
  "O piscicultor deve entender que o peixe vive no meio onde permanecem os seus residuos, sendo necessário, portanto, proporcionar-lhe as minimas condições de vida, mas, quando colocado em um sistema fechado e adensado, como é a criação semi-intensiva e intensiva, estes cuidados devem ser redobrados."
)

st.subheader("TESTES OS PARÂMETROS DA ÁGUA E VEJA O RESULTADO.")

# nível do pH
level_ph = st.slider("Selecione o nível do pH", 0, 14)

# Coluna com o fatores

col1, col2 = st.columns(2)

with col1:
  especie3 = st.selectbox(
    "Selecione a espécie",
    ("Tillápia do nilo(Oreochromis niloticus)",
     "Tambaqui(Colossoma macropomum)", "Camarão Cinza(Litopenaeus vannamei)"))

  tempea = st.number_input('Temperatura(°C)', min_value=-30, max_value=60)
  st.write(tempea, "°C")

  oxi_disso = st.number_input('Oxigênio Dissolvido(mg/l)')
  st.write(oxi_disso, "mg/l")
  #Botão
  Botão_teste = st.button("Enviar")

with col2:
  Amonia = st.number_input('Amônia(ppm)', min_value=0.01, max_value=0.99)
  st.write(Amonia, "ppm")

  Nitrito = st.number_input('Nitrito(ppm)', min_value=0.01, max_value=0.99)
  st.write(Nitrito, "ppm")

  Nitrato = st.number_input('Nitrato(mg/L)')
  st.write(Nitrato, "mg/L")

#Tilápia
if Botão_teste:
  if especie3 == "Tillápia do nilo(Oreochromis niloticus)":
    st.info('Tillápia do nilo(Oreochromis niloticus)', icon="ℹ️")
    if tempea >= 26 and temperatura <= 32:
      st.success("Temperatura ok! deve estar entre 26 a 32ºC.", icon="✅")
    else:
      st.error(
        "Temperatura inadequada para essa espécie, tilápia deve estar entre 26 a 32ºC.",
        icon="🚨")
    
    if oxi_disso >= 0.7 and oxi_disso >= 1.6:
      st.success(
        "Oxigênio ok! lembre-se a faixa segura de oxigênio dissolvido está ao redor de 5 mg/l.",
        icon="✅")
    else:
      st.error(
        "Oxigênio inadequado para essa espécie,tilápia pode resistir entre 1,6 a 0,7mg/litros.",
        icon="🚨")
    
    if level_ph >= 6 and level_ph <= 8.5:
      st.success("nível do pH está ok!", icon="✅")
    else:
      st.error(
        "Nível do ph inadequado para essa espécie,tilápia pode resistir entre 6 a 8,5. Abaixo de 4,5 e acima de 10,5 a mortalidade é significativa.",
        icon="🚨")
    
    if Amonia <= 0.1:
      st.success("nível de Amônia ok! lembre-se o parâmetro ideal é zero.",
                 icon="✅")
    else:
      st.error(
        "nível da Amônia está alto,o parâmetro ideal é zero, sendo que até 0,1 ppm é tolerável.",
        icon="🚨")
    if Nitrito < 0.2:
      st.success(
        "nitrito ok! a concentração ideal de nitrito  é inferior a 0,2 ppm.",
        icon="✅")
    else:
      st.error(
        "Nitrito alto, a concentração ideal de nitrito  é inferior a 0,2 ppm.",
        icon="🚨")
    if Nitrato < 10:
      st.success('Nitrato ok!', icon="✅")
    else:
      st.error(
        'nitrato alto,água com nível de nitrato abaixo de 10 mg/L é considerada segura.',
        icon="🚨")

  
#Tambaqui
if Botão_teste:
  if especie3 == "Tambaqui(Colossoma macropomum)":
    st.info("Tambaqui(Colossoma macropomum)", icon="ℹ️")
    if tempea >= 27 and tempea <= 30:
      st.success("Temperatura ok!  deve estar entre 27 a 30ºC.", icon="✅")
    else:
      st.error(
        "Temperatura inadequada para essa espécie,deve estar entre 27 a 30ºC.",
        icon="🚨")
    
    if oxi_disso >= 1:
      st.success(
        "Oxigênio ok! lembre-se a faixa segura de oxigênio dissolvido está ao redor de 5 mg/l.",
        icon="✅")
    else:
      st.error(
        "Oxigênio inadequado para essa espécie,tambaqui pode resistir entre 1 a 3mg/litros.",
        icon="🚨")
    
    if level_ph >= 6.5 and level_ph <= 8.5:
      st.success("nível do pH está ok!", icon="✅")
    else:
      st.error(
        "Nível do ph inadequado para essa espécie,tambaqui pode resistir entre 6,5 a 8,5. Abaixo de 4,5 e acima de 10,5 a mortalidade é significativa.",
        icon="🚨")
    
    if Amonia <= 0.1:
      st.success("nível de Amônia ok! lembre-se o parâmetro ideal é zero.",
                 icon="✅")
    else:
      st.error(
        "nível da Amônia está alto,o parâmetro ideal é zero, sendo que até 0,1 ppm é tolerável.",
        icon="🚨")
    if Nitrito < 0.2:
      st.success(
        "nitrito ok! a concentração ideal de nitrito  é inferior a 0,2 ppm.",
        icon="✅")
    else:
      st.error(
        "Nitrito alto, a concentração ideal de nitrito  é inferior a 0,2 ppm.",
        icon="🚨")
    if Nitrato < 10:
      st.success('Nitrato ok!', icon="✅")
    else:
      st.error(
        'nitrato alto,água com nível de nitrato abaixo de 10 mg/L é considerada segura.',
        icon="🚨")

#CAMARÃO L. Vannamei
if Botão_teste:
  if especie3 == "Camarão Cinza(Litopenaeus vannamei)":
    st.info("Camarão Cinza(Litopenaeus vannamei)", icon="ℹ️")
    if tempea >= 24 and tempea <= 33:
      st.success("Temperatura ok!  deve estar entre 24 a 33ºC.", icon="✅")
    else:
      st.error(
        "Temperatura inadequada para essa espécie,deve estar entre 24 a 33ºC.",
        icon="🚨")
    if oxi_disso >= 5:
      st.success(
        "Oxigênio ok! lembre-se a faixa segura de oxigênio dissolvido está ao redor de 5 mg/l.",
        icon="✅")
    else:
      st.error(
        "Oxigênio inadequado para essa espécie,ela pode resistir de 5mg/litros em diante.",
        icon="🚨")
    
    if level_ph >= 7.5 and level_ph <= 8.5:
      st.success("nível do pH está ok!", icon="✅")
    else:
      st.error(
        "Nível do ph inadequado para essa espécie,Vannamei pode resistir entre 7,5 a 8,5.",
        icon="🚨")
    
    if Amonia <= 0.1:
      st.success("nível de Amônia ok! lembre-se o parâmetro ideal é zero.",
                 icon="✅")
    else:
      st.error(
        "nível da Amônia está alto,o parâmetro ideal é zero, sendo que até 0,1 ppm é tolerável.",
        icon="🚨")
    if Nitrito < 0.2:
      st.success(
        "nitrito ok! a concentração ideal de nitrito  é inferior a 0,2 ppm.",
        icon="✅")
    else:
      st.error(
        "Nitrito alto, a concentração ideal de nitrito  é inferior a 0,2 ppm.",
        icon="🚨")
    if Nitrato < 10:
      st.success('Nitrato ok!', icon="✅")
    else:
      st.error(
        'nitrato alto,água com nível de nitrato abaixo de 10 mg/L é considerada segura.',
        icon="🚨")

st.title("TEMPERATURA")
st.markdown(
  "A temperatura em todo o planeta tem como fonte reguladora o Sol. Os raios solares trazem a energia para os tanques, os quais são absorvidos, elevando a temperatura da água. Significando que ao longo de um dia inteiro ocorre uma variação deste parâmetro, elevando, portanto, a temperatura da água nas horas mais quentes. Entretanto, a baixa capacidade de condutividade térmica da água restringe, inicialmente, o aquecimento às partes mais altas da coluna d'água. A temperatura da água depende da latitude, altitude e média diária de número de horas de brilho solar; além disso é afetada também por características especificas, tais como: turbidez (presença de sólidos em suspensão), força do vento, mata ciliar, presença de plantas aquáticas, e outras condições microclimáticas nas proximidades dos tanques ou açudes. As variações de temperatura também podem ser alteradas pela altura da coluna d'água (a profundidade). Em corpos d'água com uma profundidade inferior a 1 m, a temperatura da água pode alcançar 40'C ou mais, sob luz solar direta; já em tanques com uma profundidade maior, o aquecimento fica restrito às camadas superiores da água, causando uma estratificação térmica da coluna d'água (a temperatura da água nas partes mais baixas tende a ser inferior àquelas dos estratos superiores). Durante os períodos mais quentes do ano, o peixe tende a ir para as camadas inferiores, buscando um refúgio térmico, ou seja, a busca de águas mais amenas."
)
st.markdown(
  "Temperaturas de 30°C a 35°C são toleradas pelos peixes tropicais, porém acima disto a vida aquática fica ameaçada. A elevação da temperatura resulta na evaporação da água dos sistemas piscicolas, provocando perdas consideráveis de água, que podem variar de acordo com o grau de umidade do ar e a velocidade do vento. Em países do trópico úmido, por exemplo, a taxa de evaporação pode chegar 25 €/m²/dia."
)
st.markdown(
  "A temperatura é um fator de extrema importância para a piscicultura, pois os peixes, sendo animais ectotérmicos, sofrem influência direta da temperatura do ambiente em que vivem. A temperatura também afeta caracteristicas físicas e químicas da água, em conseqüência disso, pode-se observar que o metabolismo dos organismos aquáticos é dependente da temperatura, bem como a solubilidade do oxigênio dissolvido, a densidade e a viscosidade."
)
st.markdown(
  "Portanto, deve-se observar que quando se está construindo uma instalação piscicola, a coluna d'água deve ter no mínimo 1,5 m de altura, mas quando já existem instalações, é necessário proceder o aprofundamento dos tanques cuja profundidade seja inferior a 1 m, para pelo menos, 1,5 m, a fim de provocar a estratificação da coluna da água. Além de combinar com renovação d'água."
)
st.markdown(
  "O acompanhamento da temperatura da água deve ser diário devido a sua grande variação ao longo do dia, com pelo menos très leituras ao dia. Sua medida é obtida através de uma simples leitura em termômetro simples. Esta exigência se deve ao fato de que as variações podem afetar o crescimento e até a determinação de mortalidade quando do caso de friagem, que em muitos casos, não é ocasionada por grande queda de temperatura do ar, mas pelo aumento da nebulosidade, diminuindo drasticamente a luminosidade e afetando a produção fotossintética."
)

st.title("OXIGÊNIO DISSOLVIDO (O²)")
st.markdown(
  "O oxigênio é um dos fatores-chave para a vida aquática e, como geralmente se encontra com baixa salubilidade na água, é freqüentemente um fator limitante para esse tipo de vida."
)
st.markdown(
  "respiração, trocas do ar com a interface da água e a suplementação da água do tanque (renovação). A quantidade de oxigênio dissolvido na água depende da pressão atmosférica e da pressão parcial deste gás em contato com a superficie da água. Entre os dois se estabelece uma média, um equilibrio, responsável pela passagem do oxigênio entre o ar e a água. O pico da produção está próximo de meio-dia, com a saturação do oxigênio podendo chegar até a 250%. Neste caso a troca de oxigênio beneficiará a atmosfera, ou seja, por estar supersaturado, o oxigênio presente na água, estando acima da média entre o ar e a superficie aquàtica, acaba por deslocar-se da água para a atmosfera."
)
st.markdown(
  "m grande concorrente dos peixes é a decomposição de matéria orgânica, que se localiza no fundo dos tanques. O próprio processo de cultivo dos peixes pode proporcionar um aumento descontrolado da matéria orgânica. Um fator super importante é a densidade de peixes por m², pois a relação ótima é um kg de peixe para um m², portanto, deve-se fazer um acompanhamento periódica do crescimento dos animais para ter a clara certeza da relação pesa e área inundada. As coletas de água, para se medir o oxigênio dissolvido, devem ser realizadas a uma profundidade média de 10 cm, por ser uma zona ótima de produção deste gás, em vidros de cor âmbar e de boca larga. Mas hoje, leituras podem ser feitas diretamente na água do açude/tanques, com aparelhos medidores portáteis de oxigênio que podem ser automáticos ou reguláveis. A faixa segura de oxigênio dissolvido está ao redor de 5 mg/l."
)
st.title("INSTRUÇÕES TÉCNICAS")
st.markdown(
  "cor âmbar e de boca larga. Mas hoje, leituras podem ser feitas diretamente na água do açude/tanques, com aparelhos medidores portáteis de oxigênio que podem ser automáticos ou reguláveis. A faixa segura de oxigênio dissolvido está ao redor de 5 mg/l."
)

st.title("POTENCIAL DE HIDROGÊNIO(pH)")
st.markdown(
  "pH é a medida de concentração do potencial de hidrogênio, o qual determina caracter de acidez, alcalinidade ou neutralidade da água. Ocorre um equilibrio natural na água, através da concentração de dióxido de carbono, bicarbonato e carbonato, sendo o primeiro resultante da respiração dos organismos aquáticos bem como da decomposição de matéria orgânica. Deve ser acompanhado pelo menos uma vez por semana, utilizando-se instrumentos ou papel de medição de pH."
)

st.title("AMÔNIA(NH3)")
st.markdown(
  "A concentração de amonia junto com o pH devem ser monitorados, especialmente quando se adiciona à água fertilizantes que contenham amonia na sua fórmula. Uma das principais fontes de amonia na água dos tanques são a excreção dos peixes e o excesso de alimento que não fora ingerido. Um indice de 0,1 mg/ é o máximo aceitável para a concentração de amonia na água."
)
st.markdown(
  "A amonia sendo tóxica causa desbalanço fisiológico, falha renal, supressão da excreção da amonia endógina, resultando em falhas neural e citológicas, e, também, falhadas branquias, dificultando a respiração. Uma série de fatores influenciam a toxidez da amônia, incluindo uréia, amido e amino óxido derivados, ácido úrico, dióxido de carbono e oxigênio dissolvido."
)
st.markdown(
  "Amônia, sem dúvida, é um grande problema para tanques de piscicultura, entretanto pode ser manejada, por exemplo, buscando-se uma aproximação de N-NH: de 20 ga 80 g por quilo de alimento/dia. Um acompanhamento semanal deste parámetro sería de grande valia para o monitoramento da qualidade da água."
)

st.title("TRANSPARÊNCIA")
st.markdown(
  "A transparência nada mais é do que a penetração dos raios solares na água. Sabemos que parte dos raios que chegam até a superfície da água é refletida de volta para atmosfera, sendo absorvida progressivamente, com a profundidade da água."
)
st.markdown(
  "A fotossíntese é um processo responsável pela entrada de oxigênio no sistema aquático, podendo sofrer limitações quando a irradiação solar estiver abaixo de 1%, ou seja, praticamente não ocorre fotossíntese neste estágio. A absorção gradual através da coluna d'água altera bastante a produção de oxigênio. Quando se observa o indice de transparência, nota-se que na parte superior da coluna d'água ocorre um inibição entre 2 cm a 5 cm de profundidade: logo após esta faixa, que compreende de 5 cm a 20 cm, encontra-se uma área de saturação; entre 20 cm a 60 cm, ocorre uma faixa de transição; acima de 60 cm há um início de inibição da fotossíntese. A função da produção de oxigênio está diretamente ligada à luz e à profundidade do tanque."
)
st.markdown(
  "A medida de transparência é realizada através de um instrumento simples, que pode ser confeccionado pelo próprio piscicultor; trata-se de um prato metálico de superficie plana, com aproximadamente 30 cm de diâmetro, apresentando uma pintura intercalada de branco e preto, acoplado a uma corda com divisões, para se identificar a profundidade."
)
st.markdown(
  "Colocando-se o disco perpendicular à superficie da água, observa-se o reflexo deste em relação à superficie. Quando não se pode mais observar o disco, anota-se aquela d'água,profundidade, e o resultado multiplica-se por dois, para se obter a altura da coluna até onde ocorre o retorno do brilho do reflexo solar."
)

st.title("NEBULOSIDADE")
st.markdown(
  "Um fator de grande importância para piscicultura na região amazónica é a presença de nuvens, por isso fazer uma escala que envolva dias: limpo, com poucas nuvens nublado parcialmente (pela manhã ou à tarde); nublado e extremamente nublado. Devem ser anotados pelo piscicultor, pois, como já foi descrito, a presença da luz solar influencia na temperatura e na concentração de oxigênio dissolvido. Várias quedas de teores de oxigênio acontecem em dias que foram sucedidos por dias extremamente nublados, causando uma baixissima produção de oxigênio, que, sem haver reposição e com o consequente consumo diário pelos peixes, provoca uma queda brusca desse gas na água dos tanques."
)
st.title("NUTRIENTES")
st.markdown(
  "A presença de nutrientes na água é de extrema importância para os peixes, pois os nutrientes representam a fertilidade natural da água, da qual a produtividade primaria e. posteriormente, a produção de peixes dependem. Por isso em vários casos é recomendado o uso de adubos, o que altera a presença de nutrientes na água. Estes nutrientes devem ser acompanhados pelo menos uma vez por mês para que se verifique seu nivel na água. Os principais nutrientes que devem ser acompanhados nas águas amazônicas são: fósforo. potássio e cálcio Por serem limitantes em sistemas aquáticos, podem afetar a produção primária, comprometendo a qualidade da água dos tanques."
)

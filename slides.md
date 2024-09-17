<!--
-------------------------------------------------------------------------------
This file defines the contents of each slide.
The reveal.js configuration can be found in index.html
-------------------------------------------------------------------------------
-->

<!-- .slide: class="slide-title" data-background-color="#262626" data-background-size="contain" -->

<!-- Place the content at the bottom of the slide -->
<div class="r-stretch">
</div>

<h1 id="talk-title">
  Separação regional-residual utilizando ajuste polinomial
</h1>
<p id="talk-authors">
  <a>Yago M Castro</a>
</p>

<!-- Place location and date side-by-side with affiliation logos -->
<div class="row talk-info">
<div class="col-large">

<i class="fa fa-calendar-alt" style="margin: 0 10px 0 0"></i>
17 de Setembro de 2024
<span style="margin: 0 20px"></span>
Seminário  1 | Métodos Geofísicos de Exploração

<!-- Permission to reuse and CC-BY license logo -->
<i class="fa fa-camera" style="margin: 0 10px 0 0"></i>
Sinta-se à vontade para tirar capturas de tela/compartilhar/reutilizar esta apresentação
<span style="margin: 0 20px"></span>
<a href="https://creativecommons.org/licenses/by/4.0/"><i class="fab fa-creative-commons"></i><i class="fab fa-creative-commons-by" style="margin: 0 10px 0 2px"></i>CC-BY 4.0 License</a>

</div>
<div class="col-medium">

<!-- Add logos here. Need these wrappers to align them to the bottom right -->
<div class="talk-logos-container">
<div class="talk-logos">
  <a href="https://www.compgeolab.org"><img src="assets/compgeolab-banner-light.svg" alt="Computer-Oriented Geoscience Lab"></a>
  <a href="https://www.iag.usp.br/"><img src="assets/iag.png" alt="Instituto de Astronomia, Geofísica e Ciências Atmosféricas"></a>
  <a href="https://www.usp.br/"><img src="assets/usp.png" alt="Universidade de São Paulo"></a>
</div>
</div>

</div>
</div>

===============================================================================

# O que é separação regional-residual?

<div class="quote dark fragment">

Separação de componentes de larga escala de pequenas anomalias

</div>

===============================================================================

# Métodos de separação regional-residual

<div class="fragment text-left">

- **Gráfico**
  - Baseados na intuição e experiência do intérprete
  - Altamente subjetivo, mas permite insights geológicos

</div>
 
</div>

<div class="fragment text-left">

- **Métodos espectrais**
  - Separação quantitativa usando filtragem passa-baixa
  - Minimiza a subjetividade, mais rápido que os métodos gráficos
  - Erros: distorção de sinal e transmissão de ruído
  - Uso do filtro de Wiener para reduzir erros

</div>

<div class="fragment text-left">

- **Ajuste Polinomial**

</div>

===============================================================================

# O que é um polinômio?

<div class="quote dark fragment">

$ P(x) = a_0 + a_1 x + a_2 x^2 + \dots + a_n x^n $

</div>

<div class="fragment text-left">

Em que $a_0, a_1, \dots, a_n$ são os coeficientes do polinômio, e \(x\) é a variável independente.

</div>



===============================================================================
# O que é ajuste polinomial?

<div class="quote dark fragment">

É uma técnica que encontra um polinômio que melhor se ajusta aos dados, minimizando a diferença entre os valores observados e os preditos.
</div>

===============================================================================

<!-- .slide: data-background-image="assets/texas.png" data-background-size="contain" data-background-color="#262626" -->

===============================================================================

# Limitações do ajuste polinomial usando mínimos quadrados


<ul class="text-left">
  <li class="fragment text-left">O polinômio é ajustado ao <b>campo total</b>, não ao campo <b>regional desconhecido</b></li>
  <li class="fragment text-left"><b>Polinômios de alta ordem</b> podem ajustar parte do campo residual</li>
  <li class="fragment text-left">Isso leva a <b>amplitudes</b> de resíduos <b>menores</b> do que as reais</li>
  <li class="fragment text-left">O método exige que a <b>soma</b> de todos os resíduos seja <b>zero</b></li>
  <li class="fragment text-left">Isso pode criar resíduos negativos espúrios no processo de ajuste</li>
</ul>


===============================================================================
<!-- .slide: data-background-image="assets/paper2.png" data-background-size="contain" data-background-color="#262626" -->


===============================================================================
<!-- .slide: data-background-image="assets/weights.png" data-background-size="contain" data-background-color="#262626" -->

===============================================================================

# Considerações



<ul class="text-left">
  <li class="fragment text-left">Novo método <b>automático</b> de separação regional-residual em dados gravimétricos</li>
  <li class="fragment text-left">Permite o uso de <b>polinômios de alta ordem</b> sem incluir os resíduos, melhorando o ajuste do campo regional</li>
  <li class="fragment text-left">Reduz a influência dos resíduos assumindo que <b>anomalias isoladas</b> apresentam o <b>mesmo sinal</b></li>
  <li class="fragment text-left">Produz <b>resíduos mais precisos</b> em amplitude, gradiente e tamanho comparado ao método tradicional</li>
  <li class="fragment text-left">Supera <b>métodos espectrais</b>, que têm dificuldade com a <b>sobreposição de espectros</b> regional e residual</li>
</ul>


===============================================================================

<!-- .slide: data-background-image="assets/paper1.png" data-background-size="contain" data-background-color="#262626" -->


===============================================================================


# Resumo

<ul class="text-left">
  <li class="fragment text-left">Computer-Assisted Regional Residual Separation <b>(CARRS)</b></li>
  <li class="fragment text-left">O <b>CARRS</b> simula operações dos antigos métodos gráficos com pouca intervenção do intérprete.</li>
  <li class="fragment text-left">Utiliza <b>ajuste polinomial robusto</b> em pontos com baixo <b>gradiente horizontal</b> e <b>segunda derivada vertical</b></li>
  <li class="fragment text-left">O ajuste polinomial de dados também é implementado com o método <b>LOWESS</b> (Locally Weighted Scatterplot Smoothing), que ajusta polinômios <b>localmente</b> para suavizar os dados</li>

</ul>

===============================================================================
<!-- .slide: data-background-image="assets/mendonca-context.png" data-background-size="contain" data-background-color="#262626" -->


===============================================================================
<!-- .slide: data-background-image="assets/mendonca-maps.png" data-background-size="contain" data-background-color="#262626" -->


===============================================================================
<!-- .slide: data-background-image="assets/mendonca-profiles.png" data-background-size="contain" data-background-color="#262626" -->

===============================================================================

<!-- .slide: data-background-image="assets/paper3.png" data-background-size="contain" data-background-color="#262626" -->

===============================================================================


<!-- .slide: data-background-image="assets/paper3-microgravity.png" data-background-size="contain" data-background-color="#262626" -->

===============================================================================


<!-- .slide: data-background-image="assets/paper3-result.png" data-background-size="contain" data-background-color="#262626" -->


===============================================================================

<!-- .slide: class="slide-contact" data-background-size="contain" data-background-color="#262626" -->


<div class="r-stretch centered">
<div>

<i class="fas fa-comments"></i>
<br>
Contato:
<a href="yagomcastro@usp.br">yagomcastro@usp.br</a>

<i class="fab fa-github"></i>
<br>
Código-fonte para esta apresentação:
<br>
[github.com/YagoMCastro/seminario-metodos-potenciais-msc-2024](https://github.com/YagoMCastro/seminario-metodos-potenciais-msc-2024)
<br>
Material adicional:
<br>
[github.com/YagoMCastro/polynomial-fitting-msc-2024](https://github.com/YagoMCastro/polynomial-fitting-msc-2024)

<i class="fab fa-creative-commons"></i><i class="fab fa-creative-commons-by"></i>
<br>

Salvo indicação em contrário,
o conteúdo desta apresentação está
licenciado sob a
<br>
[Creative Commons Attribution 4.0 International License](https://creativecommons.org/licenses/by/4.0/).

</div>
</div>
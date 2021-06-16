# Responda às seguintes questões:

Podem colocar aqui qualquer texto que quiserem. Aceita formatação markdown, como *itálico*, **negrito** e ~~riscado~~.

{% for pergunta in site.data.perguntas.banco_de_perguntas %}
<fieldset>
<legend><li>{{pergunta.id}}. {{pergunta.titulo}}</li></legend>
<dd><i>{{pergunta.descricao}}</i> (peso {{pergunta.peso_pergunta}})</dd>
<form>
{% for opcao in pergunta.respostas %}
<label><input type="radio" id="{{pergunta.id}}{{opcao}}" name="{{pergunta.id}}" value='{{pergunta.peso_respostas[forloop.index0]}}' /> {{opcao}}</label>
{% endfor %}
</form>
</fieldset>
<br>
{% endfor %}

<button type="button" id='calcular' class='btn' onclick="somar()">Ver resultado</button>
<div id="result"></div>
<button type="button" id='limpar' class='btn' onclick="limpar()" hidden>Recomeçar</button>


{% include scripts.html %}

---

© {{ site.time | date: '%Y' }} [{{ site.desenvolvedor }}]({{site.baseurl}}/time/)

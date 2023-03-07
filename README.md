# Causal-Language-Modeling 

<h2>Que es un Casual Languaje Modeling(CLM)?</h2>
<p>Un CLM tiene la tarea de predir los tokens futuros dado unos tokens previos.</p>
<p>Ejemplo:</p> 
<ul>
    <li><b>La escuela es</b> divertida.</li>
    <li><b>La escuela es</b> mi segundo hogar.</li>
    <li><b>La escuela es</b> divertida.</li>
</ul>
<p>Estos textos fueron creados a partir de la cadena <em>La escuela es</em>.</p>


<h2>Que vas a encontrar en este repositorio?</h2>
<p>En este repositorio encontrara el entrenamiento de un modelo CLM, el modelo sera GPT-2.</p>
<p>El modelo fue entrenado desde 0 con un corpus de chistes en ingles, tambien se brindara en la notebook una API en español que traducira las entradas y salidas a español.</p>
<p>El modelo fue creado gracias a la bbiblioteca Transformers.</p>
<p>Para mas informacion sobre la biblioteca Transformers: https://huggingface.co/docs/transformers/index</p>


<h2>Modelo</h2>
<h3>Puedo usar el modelo?</h3>
<p>Si! EL modelo se puede usar sin necesidad de ejecutar toda la notebook.</p>
<h3>Que necesito usar para el modelo?</h3>
<p>Los pasos son los siguientes:</p>
<ol>
    <li>Descargar las librerias necesarias: Mas info: https://huggingface.co/docs/transformers/installation#install-with-pip</li>
    <li>Descargar el modelo: Ejecute el siguiente codigo.</li>
</ol>

```
    from transformers import pipeline
    import torch

    pipe = pipeline(
        "text-generation", model="Br22/br_CLM"#, device=torch.device(0), descomentar si tenes GPU
    )
```
<ol start="3">
    <li>Probar el modelo:</li>
</ol>

```
    texto = "Texto de ejemplo"
    pipe(texto, max_new_tokens=40, pad_token_id=0, num_return_sequences=1)[0]["generated_text"]
```
<p><b>Aclaracion:</b> En la parte final de la notebook IA se crea una funcion que genera texto y nos brinda la facilidad de usar el modelo en español.<p>

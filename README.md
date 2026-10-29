# Práctica 3.4 – Estilos de vida entre generaciones

| Dato | Valor |
|---|---|
| Estudiante | Roberto Carlos Robles Campos |
| No. de control | 251000068 |
| Escuela | Tecnológico Nacional de México – Instituto Tecnológico de Mazatlán |
| Materia | Desarrollo Sustentable (ACD-0908) |
| Profesor | Miguel Ángel Barrón Hernández |
| Carrera | Ingeniería en Sistemas Computacionales |
| Práctica | 3.4-P8 Página web "Estilos de vida entre generaciones" |
| Modalidad | Individual |
| Fecha | 29 de octubre de 2026 |
| Lugar | Mazatlán, Sinaloa |

**Página publicada:** https://roblescamposcarlos-beep.github.io/Estilos_Vida_Generaciones/

## 1. Objetivo
Distinguir los estilos de vida y de consumo de tres generaciones de mi entorno, construir sin programar una página web conectada a Make e IA para compararlas y formular conclusiones propias sobre su sustentabilidad.

## 2. Cómo funciona
Flujo: **Página web → Make (Webhook → Make AI Agent → Webhook Response) → Página web**.

1. La página (`index.html`, un solo archivo con HTML, CSS y JavaScript) reúne las respuestas de las tres personas y las envía por POST con `URLSearchParams` en tres campos: `abuelo`, `padre` y `amigo`.
2. El escenario `Generaciones_RobertoRobles` en Make recibe los datos con un Custom webhook.
3. El Make AI Agent (conexión Make's AI Provider, sin Knowledge) compara las respuestas con las instrucciones de la práctica y usa solo lo que dicen las entrevistas.
4. Webhook Response devuelve el análisis en texto plano (estado 200, `Content-Type: text/plain; charset=utf-8`, `Access-Control-Allow-Origin: *`) y la página lo muestra.

Consumo: cada análisis gastó aproximadamente **3.6 créditos** (3 operaciones, unos 7 segundos).

## 3. Entrevistas
Se hicieron las mismas 8 preguntas a tres personas. Solo se registró la edad, no el nombre. El abuelo y el padre respondieron pensando en cuando tenían entre 18 y 25 años; el amigo, sobre su vida actual.

| # | Pregunta | Abuelo/a (86 años) | Padre/Madre (56 años) | Amigo/a (20 años) |
|---|---|---|---|---|
| 1 | ¿De dónde conseguían la comida? | Mercado y cultivo | Mercado y cultivo | Mercado y tienda |
| 2 | ¿Qué hacían con la ropa o zapatos viejos? | Los reparaban | Los reparaban | Depende del estado en que se encuentren |
| 3 | ¿Qué aparatos electrónicos tenías y cada cuánto los cambiabas? | Ninguno | Antes ninguno, después una tele | Tele, Xbox, tablet, teléfono, computadora, refrigerador y horno; aún no los cambia |
| 4 | ¿Cómo te transportabas? | A pie, a caballo o en burro | A pie | A pie, en camioneta particular y en camión |
| 5 | ¿Qué hacían con la basura? | La quemaban | La quemaban o la tiraban directamente | No separan ni reutilizan; todo va en una misma bolsa |
| 6 | ¿Usabas bolsas, botellas o envases desechables? | No | Sí, 2 o 3 veces por semana | No / una vez al año |
| 7 | ¿Cómo usaban y cuidaban el agua? | Agua de pozo y de río | Antes de pozo y de río; después la cuidaban mucho porque es importante | No cuida el agua |
| 8 | ¿Qué es necesario para vivir bien? | Salud, dinero y ganas de vivir | Dinero, salud y fe | Mucha feria (dinero) |

> Nota: en la entrevista del amigo/a, la pregunta 6 se registró como "no" y "una vez al año". La respuesta no quedó del todo clara, y esa ambigüedad afecta al análisis de la IA.

## 4. Análisis generado por la IA
```
COMPARACIÓN POR TEMA
Comida: Abuelos y padre combinan mercado y cultivo, mientras amigo/a añade tienda y no menciona cultivo.
Ropa: Los tres hablan de reparar o depender del estado; abuelo y padre reparaban, amigo/a dice que depende del estado.
Electrónicos: Abuelo no tenía; padre tuvo tele; amigo/a tiene varios dispositivos y aún no los cambia.
Transporte: Abuelo iba a caballo o burro; padre iba a pie; amigo/a se mueve en doch, camioneta y camión.
Basura: Abuelo la quemaba; padre la quemaba o tiraba; amigo/a desecha todo en una sola bolsa.
Desechables: Abuelo no usaba desechables; padre sí, 2–3 veces a la semana; amigo/a usa desechables una vez al año.
Agua: Abuelo usaba agua de pozo y de río; padre dice que antes era de pozo y río, luego cuidan mucho el agua; amigo/a no cuida el agua.
Vivir bien: Abuelo dice salud, dinero y ganas de vivir; padre dice dinero, salud y fe; amigo/a dice mucha feria.

ANÁLISIS
Antes había reparación de ropa y autocuidado de recursos (cultivo, agua y basura quemada), lo cual era más autosuficiente. Hoy se observa mayor consumo de electrónica y uso de desechables, además de transporte privado y menor separación de basura; los cambios sociales y tecnológicos influyeron en estos hábitos.

CONCLUSIONES
1. Había mayor autosuficiencia y reparación de objetos en las generaciones mayores; 2. Hoy predomina consumo y uso de desechables, con menor práctica de separación de basura; 3. Acción concreta: retomar la reparación de ropa y reducir el uso de desechables para la generación actual.
```

## 5. Revisión de las conclusiones de la IA

| Conclusión de la IA | ¿De acuerdo? | Por qué |
|---|---|---|
| 1. Las generaciones mayores tenían más autosuficiencia y reparación de objetos | **Sí** | Coincide con las respuestas: cultivo propio, reparar la ropa, agua de pozo y de río. |
| 2. Hoy predomina el consumo y el uso de desechables, con menos separación de basura | **Parcialmente** | Es cierto en electrónicos y transporte privado. Pero el amigo/a dijo que usa desechables solo una vez al año, y el padre es quien los usaba 2 o 3 veces por semana. La IA lo contó como más consumo actual, cuando los datos dicen casi lo contrario en ese punto. |
| 3. Retomar la reparación de ropa y reducir los desechables | **Sí** | Es una acción concreta y viable, y está respaldada por lo que dijeron el abuelo y el padre. |

**Lo que dejó fuera o interpretó mal:**
- Llamó "autocuidado de recursos" a la basura quemada. Quemar la basura contamina el aire y no es una práctica sustentable; era una costumbre por falta de recolección, no un cuidado.
- No destacó que el padre dijo que después empezó a cuidar mucho el agua "porque es importante", es decir, un cambio de conciencia entre generaciones.
- Dijo "abuelos y padre" cuando se entrevistó a un solo abuelo/a.
- No señaló que el amigo/a dijo que no cuida el agua, que es el punto más preocupante de los tres.
- Con respuestas tan cortas, la IA solo pudo describir; no pudo explicar las causas, que dependen de contexto que los entrevistados no dieron.

## 6. Preguntas de reflexión

**1. ¿Qué generación tiene el estilo de vida más sustentable según sus respuestas? ¿Fue por convicción o por necesidad?**
Según las respuestas, el abuelo/a: cultivaba parte de su comida, reparaba la ropa, no usaba desechables, no tenía aparatos electrónicos y se movía a pie o con animales. Casi todo eso fue por necesidad, no por convicción: no había dinero ni productos desechables para consumir de otra forma. El padre/madre es un caso intermedio: empezó con hábitos parecidos, pero con el tiempo adoptó desechables y electrónica, y aun así dijo que cuida el agua "porque es importante", lo que sí suena a convicción. El amigo/a, en cambio, tiene más aparatos, transporte particular y no cuida el agua. Aquí la comodidad y el acceso fácil a las cosas pesan más que la necesidad, y no aparece una convicción ambiental clara. Importante: ser más sustentable por necesidad no es lo mismo que serlo por decisión, y no era perfecto, porque el abuelo y el padre quemaban la basura.

**2. ¿Qué cambios en la sociedad (publicidad, tecnología, ingreso, ciudad) explican las diferencias de consumo entre las tres generaciones?**
Cambió el ingreso y el acceso: hoy hay más productos baratos y fáciles de conseguir en tiendas y supermercados, y se dejó de cultivar o reparar porque resulta más sencillo comprar. La tecnología multiplicó los aparatos: el abuelo no tenía ninguno, el padre tuvo una tele y el amigo/a tiene tele, consola, tablet, teléfono, computadora, refrigerador y horno. La ciudad también influye: pasar de caminar o usar animales a depender de la camioneta o el camión cambia el consumo de energía. La publicidad y el mercado empujan a comprar lo nuevo, aunque lo anterior todavía funcione. Además, en las comunidades con pozo y río el agua se cuidaba porque costaba trabajo conseguirla; con la llave en casa se pierde esa relación directa. El caso de la basura es distinto: antes se quemaba por falta de servicio de recolección, y hoy hay recolección, pero se separa poco.

**3. ¿Están de acuerdo con el análisis de la IA? ¿Qué dejó fuera o qué interpretó mal?**
Estoy de acuerdo en lo general: describe bien las diferencias y su recomendación de reparar y reducir desechables es razonable. Pero cometió errores. Calificó la basura quemada como "autocuidado de recursos", que es incorrecto. Interpretó que hoy se usan más desechables, aunque el padre fue quien dijo usarlos más. Habló de "abuelos" en plural cuando fue una sola persona, y no resaltó el cambio de conciencia sobre el agua del padre ni la falta de cuidado del amigo/a. La IA se limitó a resumir lo que le dieron, y con respuestas de pocas palabras no podía profundizar. Por eso hay que leerla con criterio propio y no tomarla como verdad.

**4. ¿Qué relación tienen estos hábitos con los principios de la Carta de la Tierra o con la Agenda 21?**
La Carta de la Tierra pide respeto y cuidado de la comunidad de la vida, integridad ecológica y justicia social y económica. Los hábitos del abuelo (reparar, reutilizar, cultivar, no usar desechables) coinciden con la integridad ecológica y con el uso responsable de los recursos, aunque la quema de basura la contradice. El caso del amigo/a, que no cuida el agua y no separa la basura, se aleja de esos principios. La Agenda 21 (Río de Janeiro, 1992) incluye un capítulo sobre cambiar las modalidades de consumo, que propone reducir el desperdicio y consumir de forma más eficiente; las respuestas muestran justo ese cambio de modalidades entre generaciones, y no siempre en la dirección sustentable.

**5. ¿Qué hábito de generaciones anteriores están dispuestos a retomar y cómo lo harían?**
Retomaría la reparación y el cuidado de la ropa y los objetos, en lugar de tirarlos al primer desgaste: coser, llevar zapatos con el zapatero y alargar la vida de mis aparatos electrónicos en vez de cambiarlos por moda. También quiero retomar el cuidado del agua que mencionó mi padre/madre, cerrando la llave al enjabonarme o lavar los trastes, y reducir los envases desechables llevando mi propia botella y bolsas reutilizables. Para la basura, haría lo contrario de lo que hacían antes: separar orgánicos y reciclables en casa, que es algo que hoy no hacemos.

## 7. Conclusión
Los hábitos de consumo de las tres generaciones cambiaron con el ingreso, la tecnología y la ciudad. Las generaciones mayores eran más autosuficientes por necesidad, y la actual consume más y cuida menos recursos como el agua, aunque tiene recolección de basura, que antes no existía. La IA ayudó a ordenar la información, pero tuvo errores de interpretación, así que el criterio propio sigue siendo indispensable.

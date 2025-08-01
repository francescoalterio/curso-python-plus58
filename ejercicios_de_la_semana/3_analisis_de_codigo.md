# Ejercicios de Análisis: ¿Qué hace este código?

En estos ejercicios, te doy el código completo y funcional. Tu misión es analizarlo, entender qué hace cada línea y, finalmente, describir el objetivo principal del programa. ¡Es como ser un detective de código!

---

### Código 1

```python
frase = "El rápido zorro marrón salta sobre el perro perezoso"
palabras = frase.lower().split()

contador = 0
for palabra in palabras:
    if palabra.startswith("p"):
        contador = contador + 1

print(f"Resultado: {contador}")
```

<br>
<br>
<details>
  <summary>Haz clic aquí para ver el objetivo del código</summary>
  
  **Objetivo del Código 1:**
  El programa cuenta cuántas palabras en la frase "El rápido zorro marrón salta sobre el perro perezoso" comienzan con la letra "p", sin importar si es mayúscula o minúscula.
</details>

---

### Código 2

```python
numeros = [15, 8, 22, 4, 19, 30, 11]
mayores_de_edad = []

for numero in numeros:
    if numero < 18:
        continue
    mayores_de_edad.append(numero)

mayores_de_edad.sort()

print(mayores_de_edad)
```

<br>
<br>
<details>
  <summary>Haz clic aquí para ver el objetivo del código</summary>
  
  **Objetivo del Código 2:**
  El programa filtra una lista de números para quedarse solo con aquellos que son mayores o iguales a 18. Luego, ordena esta nueva lista de menor a mayor y la imprime.
</details>

---

### Código 3

```python
emails = ["usuario1@test.com", "admin@test.com", "invitado", "usuario2@test.com"]
emails_validos = []

for email in emails:
    if email.find("@") == -1:
        print(f"Ignorando email inválido: {email}")
        continue

    emails_validos.append(email)

print(f"Los emails válidos son: {emails_validos}")
```

<br>
<br>
<details>
  <summary>Haz clic aquí para ver el objetivo del código</summary>
  
  **Objetivo del Código 3:**
  El programa revisa una lista de cadenas de texto, identifica cuáles son emails válidos (verificando si contienen el símbolo "@"), e ignora los inválidos. Finalmente, imprime una lista que contiene solo los emails válidos.
</details>

---

### Código 4

```python
texto = "p-y-t-h-o-n"
caracteres = texto.split("-")

texto_unido = ""
for caracter in caracteres:
    texto_unido = texto_unido + caracter.upper()

print(texto_unido)
```

<br>
<br>
<details>
  <summary>Haz clic aquí para ver el objetivo del código</summary>
  
  **Objetivo del Código 4:**
  El programa toma una cadena de texto con caracteres separados por guiones, la divide en una lista, y luego une los caracteres en una nueva cadena, convirtiéndolos a mayúsculas en el proceso. El resultado final es "PYTHON".
</details>

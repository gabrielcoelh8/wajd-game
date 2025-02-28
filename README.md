# WAJD - Data Structure and Algorithm Game
Platform-Puzzle Educational Game develop in Godot 4

![](https://user-images.githubusercontent.com/64715936/278706322-7c3f7beb-8dee-4550-ae02-e8ec1213f944.png)

## Sobre
Resolva enigmas lógicos de programação com tempo limitado, pulando entre plataformas e levantando caixas numeradas seguindo o algoritmo que for escolhido.

### Mecânica
O jogador deve saltar entre as plataformas e organizar 5 caixas numeradas com números gerados de forma aleatória, ele poderá levantar e soltar caixas, uma por vez. 
A forma pela qual ele vai organizar essas caixas seguirá um algoritmo de programação com tempo limitado entre cada etapa de um minuto, tornando o ato de organizar em não somente um mero organizar. 
Para conseguir completar o enigma, o jogador terá que compreender a estrutura e padrão do algoritmo que ele escolheu para reproduzi-los nas caixas que estarão fora de ordem de forma correta, ordenar as caixas com números seguindo a ordem numérica crescentemente, atentando-se para não errar o padrão de passo a passo do algoritmo de ordenação escolhido. Cada passo deve resultar no exato vetor que o algoritmo gerou em sua execução. Se por fim, no último passo, todas as caixas estiverem na posição correta, o jogador vencerá.

## Controles
Teclado:
* ``Setas direcionais (← ↑ →)``: andar e pular.
* ``Espaço``: levantar uma caixa próxima.
* ``CTRL``: soltar uma caixa da qual levantou em uma plataforma.
* ``H``: ajuda (receber resposta do passo atual em forma de vetor por 10 segundos).
* ``ESC``: pausa.

## Algoritmos de Ordenação
### Bubble Sort
```python
func bubble_sort(arr):
	var n = arr.size()
	var swapped
	while swapped != false:
		swapped = false
		for i in range(1, n):
			if arr[i-1] > arr[i]:
				var temp = arr[i - 1]
				arr[i - 1] = arr[i]
				arr[i] = temp
				swapped = true
```

### Selection Sort
```python
func selection_sort(arr):
	var temp_arr = []
	var n = arr.size()
	var lower
	var temp
	for i in range(n):
		lower = i
		for j in range(i+1, n):
			if arr[j] < arr[lower]:
				lower = j
		if arr[i] != arr[lower]:
			temp = arr[i]
			arr[i] = arr[lower]
			arr[lower] = temp
```

### Shaker Sort
```python
func shaker_sort(arr):
	var temp_arr = []
	var n = arr.size()
	var temp
	var swap: bool
	swap = true
	while(swap):
		swap = false
		#left-right
		for i in range(n-1):
			if arr[i] > arr[i+1]:
				temp = arr[i]
				arr[i] = arr[i + 1]
				arr[i + 1] = temp
				swap = true
		if not swap:
			break
		swap = false
		#right-left
		for i in range(n-2, 0, -1):
			if arr[i] > arr[i+1]:
				temp = arr[i]
				arr[i] = arr[i+1]
				arr[i+1] = temp
				swap = true
```

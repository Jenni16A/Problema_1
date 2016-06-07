# Problema_1
%Jennifer Lizeth Andrés Jorge
%Ángel Gabriel Elías Díaz

% Blindaje de neutrones
%Devuelve el promedio de las probabilidades
x=0;%inicializando el valor de x, el cual será la media de los 20 resultados obtenidos en las 20 iteraciones
for k=1:20%ciclo de las 20 pruebas que hacemos para encontrar las 20 probabilidades
  i=0;%inicalizando el contador de neutrones que atraviesan la lámina
  m=5000;%número de neutrones
  for j=1:m%para cada neutron de los 5000 que están en prueba, se realizará lo siguiente: 
  	n= 1;%inicializando el número de movimientos que puede hacer el neutron (como máximo son 8)
  	disr=1;%distancia recorrida por el neutron en forma horizontal (inicializandola en 1 porque el primer movimiento dentro de la lámina es horizontal)
  	while n < 8
  		a= 2*pi*rand;%devuelve un número aleatorio entre 0 2pi
  		disr=disr+cos(a);%ya que sólo se cuenta la distancia horizontal desde donde choca hasta donde llega el neutron, se toma el coseno del ángulo que se forma entre la el vector que se desplaza y la horizontal (el ángulo que se toma aleatorio está dado por a)
  		n=n+1;%por cada iteración, es decir, por cada movimiento que hace, se aumenta en uno el contador, lo cual hace que disminuya en uno los movimientos que le quedan por hacer
	  	if disr <=0%si el neutron rebota, o en el transcurso en que se sigue moviendo dentro de la lámina sale de ella por el extremo donde entró, entonces se hace lo siguiente:
	  		break% se sale del ciclo, y así ya no se le seguirá sumando distancia, ya que está fuera de la lámina, es absurdo sguir sumando
		elseif disr > 5%si la distancia dentro de la lámina es mayor que 5 entonces:
			i=i+1;%se suma en uno el contador descrito arriba	
			break	
		end
	  end
  end
  x=x+i/m;%sumamos todos los resultados que obtuvimos
end
x/20%encontramos la media de todos los datos

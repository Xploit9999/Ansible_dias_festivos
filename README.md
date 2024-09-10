## Descripcion del playbook

* El objetivo de este playbook es obtener los días festivos según el país y el año que se le proporcione como parámetro en formato año mes y día. 

### Requerimiento antes de usar el playbook

* Se debe de tener salida a internet ya que el playbook consulta las fechas festivas desde la página: https://www.timeanddate.com 

### Modo de Uso del Playbook

* Para poderlo usar de forma dinamica, se debe de pasar como extra vars los valores del país y el año.

Por ejemplo:

```vim
# Se utilizan dos variables 'country' para especificar el país y 'year' para especificar el año.

$ ansible-playbook dias_festivos.yml -e 'country=colombia' -e 'year=2025'
...
```

* Si se quiere dejar estaticamente, por defecto el playbook toma el año en el que se esta realizando la ejecución del playbook, y solamente sería reemplazar el valor por defecto de la variable "country" al país que se quiere dejar como valor estático.

Por ejemplo:

```
---
- name: Obtener días festivos según el país y el año actual
  hosts: localhost
  gather_facts: false
  vars:
    country: "colombia"  # < - Este sería el valor a reemplazar.
```

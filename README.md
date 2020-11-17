## Universidad Distrital Francisco Jose de Caldas
### Especializacion en Ingenieria de Software
### Profesor Alejandro Paolo Daza Corredor
### INFORMATICA I
### MicroServicios

Integrantes:

- Cesar Alfonso Solano Ruiz  202002099036
- Erick Yoan Ahumada Salcedo 202002099020
- Henry Daniel Casas Pira    202002099023 		

## Aplicacion en ArchiMate
Se presenta los diagramas relacionados a la arquitectura de una tienda de productos con sus correspondientes areas, servicios, productos, funciones en el negocio y toda la estructura que se va tener en cuenta para hacer su uso de la aplicacion en cualquier infraestructura de software. 

## Diagramas de diseño

<div align="center">
  <h5>Aplicacion</h5>
  <img src="/images/images/Aplicacion.png" width="750" alt="Aplicacion">
  <h5>Contribucion de objetivos</h5>
  <img src="/images/images/Contribucion_de_objetivos.png" width="550" alt="Contribucion de objetivos">
  <h5>Cooperacion de Aplicacion</h5>
  <img src="/images/images/Cooperacion_de_Aplicacion.png" width="750" alt="Cooperacion de Aplicacion">
  <h5>Cooperacion de Proceso de Negocio</h5>
  <img src="/images/images/CooperacionProcesoNegocio.png" width="550" alt="Cooperacion de Proceso de Negocio">
  <h5>Estructura de aplicacion</h5>
  <img src="/images/images/Estructura_de_aplicacion.png" width="550" alt="Estructura de aplicacion">
  <h5>Estructurade la Informacion</h5>
  <img src="/images/images/EstructuraInformacion.png" width="650" alt="Estructurade la Informacion">
  <h5>Funciones del negocio</h5>
  <img src="/images/images/Funciones_del_negocio.png" width="550" alt="Funciones del negocio">
  <h5>Infraestructura</h5>
  <img src="/images/images/Infraestructura.png" width="550" alt="Infraestructura">
  <h5>Motivacion</h5>
  <img src="/images/images/Motivacion.png" width="650" alt="Motivacion">
  <h5>Organizacion de la implementacion</h5>
  <img src="/images/images/Organizacion_implementacion.png" width="650" alt="Organizacion de la implementacion">
  <h5>Procesos de Negocios</h5>
  <img src="/images/images/ProcesosNegocios.png" width="550" alt="Procesos de Negocios">
  <h5>Producto</h5>
  <img src="/images/images/Producto.png" width="550" alt="Producto">
  <h5>Punto de Vista</h5>
  <img src="/images/images/PuntoVista.png" width="550" alt="Punto de Vista">
  <h5>Realizacion de Requerimientos</h5>
  <img src="/images/images/RealizacionRequerimientos.png" width="550" alt="Realizacion de Requerimientos">
  <h5>Realizacion del Servicio</h5>
  <img src="/images/images/RealizacionServicio.png" width="650" alt="Realizacion del Servicio">
  <h5>Resumen de Capas</h5>
  <img src="/images/images/ResumenCapas.png" width="650" alt="Resumen de Capas">
  <h5>Uso de la Aplicacion</h5>
  <img src="/images/images/UsoAplicacion.png" width="550" alt="Uso de la Aplicacion">
  <h5>Uso de Infraestructura</h5>
  <img src="/images/images/UsoInfraestructura.png" width="700" alt="Uso de Infraestructura">
</div>

### MicroServicios en Python 
Se presentan dos microservicios realizados en python montados en una imagen docker con su debido versionamiento, simulando el listado de clientes y productos correspondientemente.

```python
@app.route("/clientes")
def get_clientes():
    ret = []
    res = Clientes.query.all()
    for cliente in res:
        ret.append(
            {
                'cliente': cliente.nombre,
                'direccion': cliente.direccion,
                'telefono': cliente.telefono
            }
        )
    response = app.response_class(
        response=json.dumps(ret),
        status=200,
        mimetype='application/json'
    )
    return response
```

```python
@app.route("/productos")
def get_productos():
    ret = []
    res = Productos.query.all()
    for producto in res:
        ret.append(
            {
                'producto': producto.nombre,
                'precio': producto.precio
            }
        )
    response = app.response_class(
        response=json.dumps(ret),
        status=200,
        mimetype='application/json'
    )
    return response
```

### Fuentes

- [Docker](https://www.docker.com/)
- [MicroServicios](https://medium.com/@sonusharma.mnnit/building-a-microservice-in-python-ff009da83dac)
- [Open Source ArchiMate Modelling](https://www.archimatetool.com/)

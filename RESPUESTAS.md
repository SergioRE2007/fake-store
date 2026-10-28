# Respuestas

**¿Qué responsabilidad tendrá HttpClient dentro de nuestra aplicación?**
Hacer las peticiones HTTP al servidor y devolver la respuesta.

**¿Por qué hemos creado ProductService en lugar de hacer la petición desde AppComponent?**
Para separar responsabilidades. El componente solo muestra los datos y el servicio se encarga de pedirlos a la API. Así el servicio se puede reutilizar en otros componentes y si cambia la API solo hay que tocar el servicio.

**¿Qué función tiene HttpClient?**
Es la herramienta de Angular para comunicarse con el servidor. En este caso hace el GET a /products.

**¿Qué devuelve el método getProducts()?**
Un Observable<Product[]>. No devuelve los productos directamente, sino algo que avisa cuando llegan.

**¿Para qué utilizamos subscribe()?**
Para recibir los productos cuando la petición termina. Sin subscribe la petición ni siquiera se lanza.

**¿Dónde se almacenan finalmente los productos recibidos?**
En la propiedad products de AppComponent (this.products).

**¿Qué ocurriría si eliminásemos provideHttpClient()?**
Angular no podría inyectar HttpClient en el servicio y la aplicación daría un error al arrancar (NullInjectorError: No provider for HttpClient).

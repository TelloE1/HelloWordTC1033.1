# HelloWorldTC1033.1
# Pensamiento computacional orientado a objetos
## Eduardo Tello
### Carrera - ITC

![Imagen](https://i.imgur.com/FoSpPaN.png)

#### Cosas favoritas de la clase
- Programacion 
- Objetos
- Composicion

#### Pendientes
- [x] Terminar github
- [ ] Terminar avance 3 situación problema
- [ ] Presentar examen final práctico
- [ ] Pasar la clase

#### Ejemplo de codigo
``` c++
int main() {
    //delaracion del objeto con constructor default y constructor con parametros
    int opcion = -1; //inicializando opcion en -1 para que entre al ciclo

    //atributos del objeto tipo serie
    string id;
    string titulo;
    int duracion;
    string genero;
    double calificacionPromedio;
    int cantEpisodios;

    //atributos del objeto tipo episodio
    string tituloEpisodio;
    int temporadaEpsiodio;
    double calificacionEpisodio;



    Serie nuevaSerie; //declarando el objeto nueva serie
    Episodio nuevoEpisodio; //declarando el objeto nuevo episodio
    Serie hoy; //objeto de tipo serie
    Series series; //objeto de tipo series




    cout << "Elegir una ";

    while (opcion != 0) { //ciclo centinela, siempre entrará la primera vez p
        opcion = menu(); //llamando a la funcion

        if (opcion == 0) { //con esta opcion se cierra el programa
            cout << "Programando terminado ";
        }
        else if (opcion == 1) { //leyendo los datos de la serie
            leerSerie(id, titulo, duracion, genero, calificacionPromedio, cantEpisodios);
            nuevaSerie = Serie(id, titulo, duracion, genero, calificacionPromedio, cantEpisodios);

            cout << "Nueva serie creada"; //mensaje de confirmacion

        }
        else if (opcion == 2) { //pidiendo id
            cout << "Cual es el id? ";
            cin >> id;
            nuevaSerie.setId(id); //modificando el objeto con el setter
            cout << "Atributo ha sido modificado"; //mensaje de confirmacion

        }
        else if (opcion == 3) { //pidiendo atributo
            cout << "Cual es el titulo? ";
            cin >> titulo;
            nuevaSerie.setTitulo(titulo);//modificando el objeto con el setter
            cout << "Atributo ha sido modificado"; //mensaje de confirmacion


        }
        else if (opcion == 4) {
            cout << "Cual es la duracion en minutos? ";
            cin >> duracion;
            nuevaSerie.setDuracion(duracion); //modificando el objeto con el setter
            cout << "Atributo ha sido modificado"; //mensaje de confirmacion


        }
        else if (opcion == 5) {
            cout << "Cual es el genero? ";
            cin >> genero;
            nuevaSerie.setGenero(genero);//modificando el objeto con el setter
            cout << "Atributo ha sido modificado"; //mensaje de confirmacion


        }
        else if (opcion == 6) {
            cout << "Cual es la calificacion? ";
            cin >> calificacionPromedio;
            nuevaSerie.setCalificacion(calificacionPromedio);//modificando el objeto con el setter
            cout << "Atributo ha sido modificado"; //mensaje de confirmacion


        }
        else if (opcion == 7) {
            cout << "Cual es la cantidad de episodios? ";
            cin >> cantEpisodios;
            nuevaSerie.setCantidadEpisodios(cantEpisodios);//modificando el objeto con el setter
            cout << "Atributo ha sido modificado"; //mensaje de confirmacion

        }
        else if (opcion == 8) {
            cout << "Desplegando serie " << endl << nuevaSerie.str(); //desplegando la serie con el metodo str

        }
        else if (opcion == 9) { //leyendo datos del episodio
            leeDatosEpisodio(tituloEpisodio, temporadaEpsiodio, calificacionEpisodio);
            nuevoEpisodio = Episodio(tituloEpisodio, temporadaEpsiodio, calificacionEpisodio);

            cout << "Nuevo episodio ha sido creado"; //mensaje de confirmacion
        }
        else if (opcion == 10) { //desplegando el episodio con el metodo str
            cout << "Desplegando episodio " << endl << nuevoEpisodio.str();
        }
        else if (opcion == 11){ //la nueva opcion de composicion
        nuevaSerie.addEpisodio(Episodio("Clases", 1, 90));
        nuevaSerie.addEpisodio(Episodio("Constructores", 1, 90));
        nuevaSerie.addEpisodio(Episodio("Composicion", 1, 99.5));
        nuevaSerie.addEpisodio(Episodio("Arreglos", 1, 99.5));
        nuevaSerie.addEpisodio(Episodio("Clase arreglos", 1, 100));
        nuevaSerie.addEpisodio(Episodio("Calificacion final", 1, 100));
        nuevaSerie.calcularCalificacionPromedio(); //calcular calificacion promedio

        cout << nuevaSerie.str() << endl;
        nuevaSerie.delEpisodio(); //esta opcion no funciona bien. cuando va a la funcion, remplaza el arreglo como si cantEpisodios fuera 0, aunque el debugger no diga eso. no entiendo que pasa.
        hoy.addEpisodio(Episodio("Calificacion Final", 1, 100));
        cout << nuevaSerie.str() << endl;

        } //opciones de la entrega final
        else if (opcion == 12){
            series.leerArchivo();
        }
        else if (opcion == 13){
            series.calcularCalificacionPromedioSerie();
        }
        else if (opcion == 14){

            series.reporteFrecuenciasYPromedioSeries();
        }
    }
    return 0;
}

```

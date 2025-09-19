    color:blanco;
    posición:relativo;
  }

  /*Luna*/
  .Luna{
    posición:absoluto;
    arriba: 20píxeles;
    bien: 20píxeles;
    ancho: 150píxeles;
    altura: 150píxeles;
    fondo: gradiente radial(círculo, #fff 40%, #ddd 70%, #bbb 100%);
    radio del borde: 50%;
    sombra de caja: 0 0 30píxeles #fff;
    índice z: 1;
  }

  /*Estrellas*/
  .estrella{
    posición:absoluto;
    fondo:blanco;
    radio del borde: 50%;
    ancho: 2píxeles;
    altura: 2píxeles;
    opacidad: 0.8;
    animación:parpadeo2salternancia infinita;
    índice z: 0;
  }
  @fotogramas claveparpadeo {
    de{opacidad:0.2;}
    a{opacidad:1;}
  }

  /* Flores animadas */
  .flor{
    posición:absoluto;
    ancho: 25píxeles;
    altura: 25píxeles;
    color de fondo:rosa;
    radio del borde: 50%;
    animación:hermano2shacia adelante;
    sombra de caja: 0 0 10píxeles #ffb3d1;
    índice z: 2;
  }
  @fotogramas clavehermano {
    0%{transformar: escala(0.3);opacidad:0.5;}
    100%{transformar: escala(1.6);opacidad:0;}
  }

  /* Mensaje central */
  .centro{
    posición:relativo;
    índice z: 3;
    altura: 100vh;
    mostrar:doblar;
    dirección flexible:columna;
    justificar-contenido:centro;
    elementos de alineación:centro;
    alineación de texto:centro;
  }
  h1{
    tamaño de fuente: abrazadera(24píxeles, 5Volkswagen, 48píxeles);
    sombra de texto: 0 0 15píxeles #ff9cca;
  }

  /* Botón música */
  .btn-reproducir{
    margen superior: 20píxeles;
    relleno: 10píxeles 20píxeles;
    color de fondo: #ff69b4;
    borde:ninguno;
    radio del borde: 5píxeles;
    color:blanco;
    tamaño de fuente: 18píxeles;
    cursor:puntero;
  }
  .btn-reproducir:flotar{
    color de fondo: #ff1493;
  }
</estilo>
</cabeza>
<cuerpo>

<división clase="Luna"></división>

<división clase="centro">
  <h1>Tú eres mi diosa y yo, un mortal, que se enamoró de ti 💕</h1>
  <botón clase="btn-reproducir"al hacer clic="reproducirMúsica()">▶ Reproducir música</botón>
</división>

<!-- Estrellas generadas por JS -->
<guion>
  // Crear 150 estrellas
  para(dejar i=0;i<150;i++){
    dejar mi = documento.crearElemento('div');
    mi.nombre de clase='estrella';
    mi.estilo.arriba = Matemáticas.aleatorio()*100+'vh';
    mi.estilo.izquierda = Matemáticas.aleatorio()*100+'vw';
    mi.estilo.ancho = (Matemáticas.aleatorio()*3+1)+'px';
    mi.estilo.altura = (Matemáticas.aleatorio()*3+1)+'px';
    mi.estilo.Duración de la animación = (1+Matemáticas.aleatorio()*3)+'s';
    documento.cuerpo.añadirNiño(mi);
  }

  // Crear flores al hacer clic
  documento.agregarListener de eventos('hacer clic', función(mi){
    para(dejar i=0;i<6;i++){
      dejar F = documento.crearElemento('div');
      F.nombre de clase='flor';
      F.estilo.izquierda = mi.páginaX + (Matemáticas.aleatorio()*50-25)+'px';
      F.estilo.arriba = mi.páginaY + (Matemáticas.aleatorio()*50-25)+'px';
      documento.cuerpo.añadirNiño(F);
      establecer tiempo de espera(()=>F.eliminar(),3000);
    }
  });

  // Reproducir música YouTube
  función reproducirMúsica(){
    dejar yt = documento.obtenerElementoPorId('ytPlayer');
    yt.origen += "&reproducción automática=1";
  }
</guion>

<!-- Música de YouTube (invisible) -->
<iframe identificación="Reproductor de YouTube"ancho="0"altura="0"estilo="pantalla:ninguna"
origen="https://www.youtube.com/embed/-DB4ovRXn4k?loop=1&playlist=-DB4ovRXn4k"
borde del marco="0"permitir="reproducción automática; medios cifrados"></iframe>

</cuerpo>
</HTML>

# Vite Comics

## Consegna

---

### **Parte 1**

**Descrizione:**

Create un nuovo progetto utilizzando Vite e Vue 3 e definite i componenti necessari per strutturare il layout come da screenshot allegato.
Quando la struttura a macroblocchi è pronta, popolate le voci di menu dinamicamente usando i data del componente.
Per oggi diamo priorità alla struttura: quando è tutto bello solido, passiamo al Sass!

**Bonus:**

Creare un componente aggiuntivo per gestire la fascia azzurra con le icone

---

### **Parte 2**

**Descrizione:**

Continuate a lavorare nella stessa repo di ieri e create un nuovo componente che rappresenterà le card dei fumetti.
Utilizzate i dati presenti nel file json che trovate in allegato e passateli al componente Card tramite props.
Una volta inseriti tutti i contenuti dinamicamente, completate il vostro layout e rifinite i dettagli con Sass.
buon lavoro!

## Steps

**Steps parte 1:**

1. Tramite terminale inizializzo un progetto Vue

2. Creo i file `scss` necessari quali:

    - main.scss (in questo file importerò tutti i file scss che hanno bisogno di essere utilizzati ovunque e quindi non sarà necessario l'utilizzo di @use)

    - _variables.scss (nel quale dichiaro i vari colori e le varie grandezze dei font)

    - _typography (dove assegno gli stili generali del testo, come ad esempio il font utilizzato e gli stili delle liste)

    - _mixin (dove creo gli stili di mixin che verranno utilizziati nei vari components, come ad esempio `displayFlex`)

    - _general (nel quale sono dichiarate le regole generali, come ad esempio il reset del margin, paddin e il box-sizing)

3. Creo i vari components, quali:

    - Header.vue

    - Main.vue

    - Footer.vue

4. Importo i components in `App.vue`

5. Creo il markup dell'header:

    - Stampo dinamicamente il menu tramite l'import del file `menus.js` che contiene un oggetto avente le voci da stampare e il link

6. Creo il markup della cta:

    - Applico la stessa logica utilizzata nell'header, solo che in questo caso nel file `menu.js` avrò una porprietà contenente il nome dell'immagine e l'estensione ed una proprietà contenente il testo da stampare

    - Stampo le immagini tramite l'uso di una funzione che genera dinamicamente il percorso che porta all'immagine

7. Creo il markup del footer:

    - Creo due partials, rispettivamente `FooterTop.vue` e `FooterBottom.vue`

    - Per il FooterTop.vue uso la stessa logica dell'header

    - Invece per il FooterBottom.vue uso la stessa logica del cta

**Steps parte 2:**

1. Creo un components chiamato `Jumbotron.vue` e lo importo in `App.vue`

2. Importo in `Main.vue` il file `dc-comics.json`

3. Creo un partials chiamato `Card.vue` e lo importo in `Main.vue`

4. All'interno del main ciclo il parziale Card e tramite props invio soltanto le proprietà `thumb` e `series`

5. All'interno di `Card.vue` creo il markup e lo styling delle card
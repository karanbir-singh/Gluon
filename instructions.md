# Guida per l'installazione di Gluon con Android SDK e Gradle su NetBeans 8.2
## Android SDK
* Scaricare l'installer di Android SDK attraverso il seguente link
  ```
  https://dl.google.com/android/installer_r24.4.1-windows.exe
  ```
* Creare una cartella all'interno di **C:** con il nome AndroidSDK
  * Una volta creata la cartella, avviare l'installer precedentemente scaricato
  * Scegliere come percorso di installazione di Android SDK
    ```
    C:\AndroidSDK
    ```
* Avviare SDK Manager che si trova all'interno della cartella creata precedentemente
  #### Appariranno una serie di caselle
  - _**Si possono tenere la caselle spuntate di default**_
  - **Tools** > spuntare la casella **Android SDK Build-tools con Rev. 29.0.3**
  - **Android 10 (API 29)** > spuntare la casella **SDK Platform API 29**
  - **Android 8.10.0 (API 27)** > spuntare la casella **SDK Platform API 27**
  - **Extras** > spuntare la casella **Android Support Repository**
  ##### > Install packages
## Gluon e Gradle
* Aprire NetBeans
  * **Tools > Plugins > Available Plugins** : installare il plugin **Gluon plugin**
  * Accettare le varie licenze
  * In automatico si dovrebbe installare anche **Gradle**
  * Apparirà un finestra che chiede di verificare i certificati, fare **Continue**
  
* Dopo il termine dell'installazione, riavviare NetBeans
  * Una volta riavviato, **Tools > Options > Miscellaneous > Gradle**, spuntare la casella **Prefer wrapper**
  
* Provate a creare un nuovo progetto
  * Tra le **categorie** scegliere **Gluon**
  * Come tipo di progetto, scegliere **Gluon Mobile - Single View Project**
  
* Ogni volta che si crea un nuovo progetto o si apre un progetto non proprio, procedere nel seguente modo:
  * All'interno dell'app, **Build Scripts > Project**: aprire **build.gradle**
  * Cercare il seguente pezzo di codice
    ```
      android {
          manifest = 'src/android/AndroidManifest.xml'
          androidSdk = 'C:/AndroidSDK'
      }
    ```
    Se non è presenta la riga _**androidSdk = 'C:/AndroidSDK'**_ , bisogna **aggiungerla**
    _(Nello specifico, "C:/AndroidSDK" rappresenta il percorso di installazione Android SDK, di conseguenza in realtà dovete mettere il percorso di installazione che avete utilizzato voi, se non avete messo quello della guida)_

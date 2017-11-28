---
title: Debug dell'applicazione C# Hello World con Visual Studio 2017
description: Informazioni su come eseguire il debug di un'applicazione Hello World scritta in C# con Visual Studio 2017.
keywords: .NET Core, applicazione console .NET Core, debug .NET
author: BillWagner
ms.author: wiwagn
ms.date: 08/07/2017
ms.topic: article
ms.prod: .net-core
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: cb213625-cc60-438b-9b9e-49aed0e4a974
ms.openlocfilehash: 6fbebf69b2772b4159841d13068e7b95a39bea92
ms.sourcegitcommit: bbde43da655ae7bea1977f7af7345eb87bd7fd5f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/21/2017
---
# <a name="debug-your-hello-world-application-with-visual-studio-2017"></a>Debug dell'applicazione Hello World con Visual Studio 2017

Finora sono stati seguiti i passaggi nell'argomento [Compilare un'applicazione Hello World usando C# con .NET Core in Visual Studio 2017](.\with-visual-studio.md) o [Compilare un'applicazione Hello World in Visual Basic con .NET Core in Visual Studio 2017](vb-with-visual-studio.md), per creare un'applicazione console semplice. Dopo aver scritto e compilato l'applicazione, è possibile iniziare a testarla. Visual Studio include un set completo di strumenti di debug che è possibile usare durante il test e la risoluzione dei problemi dell'applicazione.

## <a name="debugging-in-debug-mode"></a>Debug in modalità di debug

Le modalità *Debug* e *Rilascio* sono due configurazioni di compilazione predefinite di Visual Studio. La configurazione di compilazione corrente viene visualizzata sulla barra degli strumenti. Nell'immagine della barra degli strumenti seguente è possibile vedere che Visual Studio è configurato per compilare l'applicazione in modalità **Debug**.

   ![Barra degli strumenti di Visual Studio](./media/debugging-with-visual-studio/toolbar1.png)

È necessario iniziare sempre eseguendo il test del programma in modalità Debug. La modalità Debug disattiva la maggior parte delle ottimizzazioni del compilatore e offre informazioni più dettagliate durante il processo di compilazione.

## <a name="setting-a-breakpoint"></a>Impostazione di un punto di interruzione

Eseguire il programma in modalità Debug e provare alcune funzionalità di debug:

1. Il *punto di interruzione* arresta temporaneamente l'esecuzione dell'applicazione *prima* che venga eseguita la riga con il punto di interruzione. 

# <a name="ctabcsharp"></a>[C#](#tab/csharp)
   Impostare un punto di interruzione sulla riga `Console.WriteLine($"\nHello, {name}, on {date:d} at {date:t}!");` facendo clic sul margine sinistro della finestra del codice. In alternativa, scegliere la voce di menu **Debug** > **Imposta/Rimuovi punto di interruzione** per la riga selezionata. Come mostrato nella figura seguente, Visual Studio indica la riga in cui è impostato il punto di interruzione evidenziando tale riga e visualizzando un cerchio rosso sul margine sinistro della finestra.

   ![Finestra del programma in Visual Studio con punto di interruzione impostato](./media/debugging-with-visual-studio/setbreakpoint.png)
# <a name="visual-basictabvisual-basic"></a>[Visual Basic](#tab/visual-basic)
   Impostare un punto di interruzione sulla riga `Console.WriteLine(vbCrLf + $"Hello, {name}, on {currentDate:d} at {currentDate:t}!")` facendo clic sul margine sinistro della finestra del codice. In alternativa, scegliere la voce di menu **Debug** > **Imposta/Rimuovi punto di interruzione** per la riga selezionata. Come mostrato nella figura seguente, Visual Studio indica la riga in cui è impostato il punto di interruzione evidenziando tale riga e visualizzando un cerchio rosso sul margine sinistro della finestra.

   <a name="visual-studio-program-window-with-breakpoint-setmediadebugging-with-visual-studiovb-setbreakpointpng"></a>![Finestra del programma in Visual Studio con punto di interruzione impostato](./media/debugging-with-visual-studio/vb-setbreakpoint.png)
---

1. Eseguire il programma in modalità Debug scegliendo il pulsante **HelloWorld** con la freccia verde sulla barra degli strumenti, premendo F5 o scegliendo **Debug** > **Avvia debug**.

1. Quando il programma chiede di specificare un nome, immettere una stringa nella finestra della console e premere INVIO.

1. L'esecuzione del programma si arresta quando raggiunge il punto di interruzione e prima che il metodo `Console.WriteLine` venga eseguito. Nella finestra **Auto** vengono visualizzati i valori delle variabili usate nella riga corrente. Nella finestra **Variabili locali** (visualizzabile facendo clic sulla scheda **Variabili locali**) vengono visualizzati i valori delle variabili definite nel metodo attualmente in esecuzione.

# <a name="ctabcsharp"></a>[C#](#tab/csharp)
   ![Finestra dell'applicazione in Visual Studio](./media/debugging-with-visual-studio/break.png)
# <a name="visual-basictabvisual-basic"></a>[Visual Basic](#tab/visual-basic)
   <a name="visual-studio-application-windowmediadebugging-with-visual-studiovb-breakpng"></a>![Finestra dell'applicazione in Visual Studio](./media/debugging-with-visual-studio/vb-break.png)
---

1. È possibile modificare il valore delle variabili per vedere in che modo tale operazione influisce sul programma. Se la **Finestra di controllo immediato** non è visibile, visualizzarla scegliendo la voce di menu **Debug** > **Finestre** > **Controllo immediato**. La **Finestra di controllo immediato** consente di interagire con l'applicazione in fase di debug.

1. È possibile modificare in modo interattivo i valori delle variabili. Immettere `name = "Gracie"` nella **Finestra di controllo immediato** e premere INVIO.

# <a name="ctabcsharp"></a>[C#](#tab/csharp)
1. Immettere `date = new DateTime(2016,11,01,11,59,00)` nella **Finestra di controllo immediato** e premere INVIO.

   Si noti che nella **Finestra di controllo immediato** vengono visualizzati il valore della variabile string e le proprietà del valore <xref:System.DateTime>. Inoltre, il valore delle variabili viene aggiornato nelle finestre **Auto** e **Variabili locali**.

   ![Finestra Auto e Finestra controllo immediato](./media/debugging-with-visual-studio/autosimmediate.png)
# <a name="visual-basictabvisual-basic"></a>[Visual Basic](#tab/visual-basic)
1. Immettere `currentDate = new DateTime(2016,11,01,11,59,00)` nella **Finestra di controllo immediato** e premere INVIO.

<!-- The **Immediate Window** displays the value of the string variable and the properties of the <xref:System.DateTime> value. In addition, the value of the variables is updated in the **Autos** and **Locals** windows.

   ![Autos window and Immediate Window](./media/debugging-with-visual-studio/vb-autosimmediate.png)
-->
---

1. Continuare l'esecuzione del programma scegliendo il pulsante **Continua** sulla barra degli strumenti oppure scegliendo la voce di menu **Debug** > **Continua**. I valori visualizzati nella finestra della console corrispondono alle modifiche apportate nella **Finestra di controllo immediato**.

   ![Finestra della console con il valore Jack digitato al prompt dei comandi What is your name? seguito da Hello Gracie 11/1/2016 at 11:59am](./media/debugging-with-visual-studio/changed.png)

1. Premere un tasto qualsiasi per chiudere l'applicazione e uscire dalla modalità di debug.

## <a name="setting-a-conditional-breakpoint"></a>Impostazione di un punto di interruzione condizionale

Il programma visualizza la stringa immessa dall'utente. Ma cosa succede se l'utente non immette alcuna stringa? È possibile testare questa eventualità con un'utile funzionalità di debug, il *punto di interruzione condizionale*, che interrompe l'esecuzione del programma quando vengono soddisfatte una o più condizioni.

Per impostare un punto di interruzione condizionale e verificare cosa succede quando l'utente non immette una stringa, seguire questa procedura:

# <a name="ctabcsharp"></a>[C#](#tab/csharp)
1. Fare clic con il pulsante destro del mouse sul punto rosso che rappresenta il punto di interruzione. Scegliere **Condizioni** dal menu di scelta rapida per aprire la finestra di dialogo **Impostazioni del punto di interruzione**. Selezionare la casella per **Condizioni**.

   ![Pannello Impostazioni del punto di interruzione](./media/debugging-with-visual-studio/breakpointsettings.png)

1. Per l'**Espressione condizionale** sostituire "e.g. x == 5" con quanto segue:

   ```csharp
   String.IsNullOrEmpty(name)
   ```
# <a name="visual-basictabvisual-basic"></a>[Visual Basic](#tab/visual-basic)
1. Fare clic con il pulsante destro del mouse sul punto rosso che rappresenta il punto di interruzione. Scegliere **Condizioni** dal menu di scelta rapida per aprire la finestra di dialogo **Impostazioni del punto di interruzione**. Selezionare la casella per **Condizioni**.

   ![Pannello Impostazioni del punto di interruzione](./media/debugging-with-visual-studio/vb-breakpointsettings.png)

1. Per l'**Espressione condizionale** sostituire "e.g. x = 5" con quanto segue:

   ```vb
   String.IsNullOrEmpty(name)
   ```
---

   Si sta effettuando il test per una condizione di codice, che la chiamata del metodo `String.IsNullOrEmpty(name)` è `true` sia perché a *name* non è stato assegnato un valore o perché il valore è una stringa vuota (""). È anche possibile specificare un *numero di passaggi* in modo da interrompere l'esecuzione del programma prima che un'istruzione venga eseguita un numero di volte specificato. In alternativa, è possibile specificare una *condizione di filtro*, che interrompe l'esecuzione del programma sulla base di attributi quali l'identificatore di thread, il nome del processo e il nome del thread.

1. Scegliere il pulsante **Chiudi** per chiudere la finestra di dialogo.

1. Eseguire il programma in modalità di debug.

1. Nella finestra della console premere INVIO quando viene chiesto di immettere il proprio nome.

1. Poiché la condizione specificata è stata soddisfatta, per cui `name` è `null` o <xref:System.String.Empty?displayProperty=nameWithType>, l'esecuzione del programma si interrompe quando raggiunge il punto di interruzione e prima che venga eseguito il metodo `Console.WriteLine`.

1. Scegliere la finestra **Variabili locali**, dove vengono visualizzati i valori delle variabili che sono locali rispetto al metodo attualmente in esecuzione, in questo caso il metodo `Main`. Si noti che il valore della variabile `name` è `""` o <xref:System.String.Empty?displayProperty=nameWithType>.

# <a name="ctabcsharp"></a>[C#](#tab/csharp)
1. Confermare che il valore è una stringa vuota immettendo l'istruzione seguente nella **Finestra di controllo immediato**. Il risultato è `true`.

   ```csharp
   ? name == String.Empty
   ```

   ![Finestra di controllo immediato che restituisce un valore true dopo l'esecuzione dell'istruzione](./media/debugging-with-visual-studio/emptystring.png)
# <a name="visual-basictabvisual-basic"></a>[Visual Basic](#tab/visual-basic)
1. Confermare che il valore è una stringa vuota immettendo l'istruzione seguente nella **Finestra di controllo immediato**. Il risultato è `true`.

   ```vb
   ? String.IsNullOrEmpty(name)
   ```
  ![Finestra di controllo immediato che restituisce un valore true dopo l'esecuzione dell'istruzione](./media/debugging-with-visual-studio/vb-emptystring.png)
---

1. Selezionare il pulsante **Continua** sulla barra degli strumenti per continuare l'esecuzione del programma.

1. Premere un tasto qualsiasi per chiudere la finestra della console e uscire dalla modalità di debug.

1. Rimuovere il punto di interruzione facendo clic sul punto sul margine sinistro della finestra del codice oppure scegliendo la voce di menu **Debug > Imposta/Rimuovi punto di interruzione** per la riga selezionata.

---
## <a name="stepping-through-a-program"></a>Esecuzione delle singole istruzioni di un programma

Visual Studio consente anche di esaminare il programma una riga alla volta e di monitorarne l'esecuzione. In genere si imposta un punto di interruzione e si usa questa funzionalità per seguire il flusso del programma, anche attraverso una piccola parte del codice. Dal momento che il programma è di piccole dimensioni, è possibile esaminarlo per intero seguendo questa procedura:

# <a name="ctabcsharp"></a>[C#](#tab/csharp)
1. Nella barra dei menu scegliere **Debug** > **Esegui istruzione** oppure premere F11. Visual Studio evidenzia e visualizza una freccia accanto alla riga di esecuzione successiva.

   ![Finestra di Visual Studio](./media/debugging-with-visual-studio/stepinto1.png)

   A questo punto, nella finestra **Auto** viene indicato che il programma ha definito una sola variabile, `args`. Poiché al programma non è stato passato alcun argomento della riga di comando, il relativo valore è una matrice di stringhe vuota. Visual Studio, inoltre, ha aperto una finestra della console vuota.

1. Scegliere **Debug** > **Esegui istruzione** oppure premere F11. Visual Studio evidenzia ora la riga dell'esecuzione successiva. Come illustrato nella figura, l'esecuzione del codice tra l'ultima istruzione e questa ha richiesto 3 millisecondi. `args` rimane l'unica variabile dichiarata e la finestra della console resta vuota.

   ![Finestra di Visual Studio](./media/debugging-with-visual-studio/stepinto2.png)
# <a name="visual-basictabvisual-basic"></a>[Visual Basic](#tab/visual-basic)
1. Nella barra dei menu scegliere **Debug** > **Esegui istruzione** oppure premere F11. Visual Studio evidenzia e visualizza una freccia accanto alla riga di esecuzione successiva.

   ![Finestra di Visual Studio](./media/debugging-with-visual-studio/vb-stepinto1.png)

   A questo punto, poiché al programma non è stato passato alcun argomento della riga di comando, la finestra **Auto** visualizza che il valore della variabile `args` è una matrice di stringhe vuota. Visual Studio, inoltre, ha aperto una finestra della console vuota.

1. Scegliere **Debug** > **Esegui istruzione** oppure premere F11. Visual Studio evidenzia ora la riga dell'esecuzione successiva. Come illustrato nella figura, l'esecuzione del codice tra l'ultima istruzione e questa ha richiesto 3 millisecondi. `args` rimane l'unica variabile dichiarata e la finestra della console resta vuota.

   ![Finestra di Visual Studio](./media/debugging-with-visual-studio/vb-stepinto2.png)
---

1. Scegliere **Debug** > **Esegui istruzione** oppure premere F11. Visual Studio evidenzia l'istruzione che include l'assegnazione della variabile `name`. Nella finestra **Auto** viene mostrato che `name` è `null` (in C#) o `Nothing` (in Visual Basic), mentre nella finestra della console viene visualizzata la stringa "What is your name?".

1. Rispondere al prompt immettendo una stringa nella finestra della console e premendo INVIO. La console non risponde e la stringa immessa non viene visualizzata nella finestra della console. Il metodo <xref:System.Console.ReadLine%2A?displayProperty=nameWithType>, tuttavia, acquisirà l'input.

1. Scegliere **Debug** > **Esegui istruzione** oppure premere F11. Visual Studio evidenzia l'istruzione che include l'assegnazione della variabile `date` (in C#) o `currentDate` (in Visual Basic). Nella finestra **Auto** vengono visualizzati il valore della proprietà <xref:System.DateTime.Now?displayProperty=nameWithType>e il valore restituito dalla chiamata al metodo <xref:System.Console.ReadLine%2A?displayProperty=nameWithType>. Nella finestra della console viene visualizzata anche la stringa immessa quando la console ha richiesto un input.

1. Scegliere **Debug** > **Esegui istruzione** oppure premere F11. Nella finestra **Auto** viene visualizzato il valore della variabile `date` dopo l'assegnazione da parte della proprietà <xref:System.DateTime.Now?displayProperty=nameWithType>. La finestra della console rimane invariata.

1. Scegliere **Debug** > **Esegui istruzione** oppure premere F11. Visual Studio chiama il metodo <xref:System.Console.WriteLine(System.String,System.Object,System.Object)?displayProperty=nameWithType>. I valori delle variabili `date` (o `currentDate`) and `name` vengono visualizzati nella finestra **Auto**, mentre nella finestra della console viene visualizzata la stringa formattata.

1. Selezionare **Debug** > **Esci da istruzione/routine** oppure premere MAIUSC+F11. Questa operazione arresta l'esecuzione passo passo. La finestra della console visualizza un messaggio e attende che venga premuto un tasto.

1. Premere un tasto qualsiasi per chiudere la finestra della console e uscire dalla modalità di debug.

## <a name="building-a-release-version"></a>Compilazione di una versione di rilascio

Dopo aver testato la compilazione di debug dell'applicazione, è necessario anche compilare e testare la versione di rilascio. La versione di rilascio integra le ottimizzazioni del compilatore che possono talvolta influire negativamente sul comportamento di un'applicazione. Ad esempio, le ottimizzazioni del compilatore progettate per migliorare le prestazioni possono creare condizioni di competizione nelle applicazioni asincrone o multithreading.

Per compilare e testare la versione di rilascio dell'applicazione console, modificare la configurazione di compilazione nella barra degli strumenti da **Debug** in **Rilascio**.

![Immagine](./media/debugging-with-visual-studio/toolbar2.png)

Quando si preme F5 o si sceglie **Compila soluzione** dal menu **Compila**, Visual Studio compila la versione di rilascio dell'applicazione console. A questo punto è possibile eseguirla e testarla come è stato fatto per la versione di debug.

Dopo aver terminato il debug dell'applicazione, il passaggio successivo consiste nel pubblicare una versione distribuibile dell'applicazione. Per informazioni su come eseguire questa operazione, vedere [Pubblicazione dell'applicazione Hello World con Visual Studio 2017](./publishing-with-visual-studio.md).

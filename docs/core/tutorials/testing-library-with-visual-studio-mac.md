---
title: Testare una libreria di classi .NET Standard con .NET Core usando Visual Studio per Mac
description: Creare un progetto unit test per una libreria di classi .NET Core. Verificare che una libreria di classi .NET Core funzioni correttamente con gli unit test.
ms.date: 06/08/2020
ms.openlocfilehash: a183049623df44cbb8c4abd47ce6e78d91adae12
ms.sourcegitcommit: 1cbd77da54405ea7dba343ac0334fb03237d25d2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/11/2020
ms.locfileid: "84713609"
---
# <a name="test-a-net-standard-class-library-with-net-core-using-visual-studio"></a>Testare una libreria di classi di .NET Standard con .NET Core con Visual Studio

Questa esercitazione illustra come automatizzare gli unit test aggiungendo un progetto di test a una soluzione.

## <a name="prerequisites"></a>Prerequisiti

- Questa esercitazione funziona con la soluzione creata in [creare una libreria di .NET standard in Visual Studio per Mac](library-with-visual-studio-mac.md).

## <a name="create-a-unit-test-project"></a>Creare un progetto di unit test

Gli unit test forniscono test software automatici durante le fasi di sviluppo e pubblicazione. [MSTest](https://github.com/Microsoft/testfx-docs) è uno dei tre Framework di test tra cui è possibile scegliere. Gli altri sono [xUnit](https://xunit.net/) e [NUnit](https://nunit.org/).

1. Avviare Visual Studio per Mac.

1. Aprire la `ClassLibraryProjects` soluzione creata in [creare una libreria di .NET Standard in Visual Studio per Mac](library-with-visual-studio-mac.md).

1. Nel riquadro della **soluzione** , fare clic con il <kbd>pulsante destro del</kbd>mouse sulla `ClassLibraryProjects` soluzione e scegliere **Aggiungi**  >  **nuovo progetto**.

1. Nella finestra di dialogo **nuovo progetto** selezionare **test** dal nodo **console e Web** . Selezionare il **progetto MSTest** seguito da **Next**.

   :::image type="content" source="media/testing-library-with-visual-studio-mac/visual-studio-mac-unit-test-project.png" alt-text="Finestra di dialogo nuovo progetto di Visual Studio Mac Creazione progetto di test":::

1. Selezionare **.NET Core 3,1**. Assegnare al nuovo progetto il nome "StringLibraryTest" e selezionare **Crea**.

   :::image type="content" source="media/testing-library-with-visual-studio-mac/visual-studio-mac-new-project-name.png" alt-text="Finestra di dialogo Nuovo progetto di Visual Studio per Mac in cui si specifica il nome del progetto":::

   Visual Studio crea un file di classe con il codice seguente:

   ```csharp
   using Microsoft.VisualStudio.TestTools.UnitTesting;

   namespace StringLibraryTest
   {
       [TestClass]
       public class UnitTest1
       {
           [TestMethod]
           public void TestMethod1()
           {
           }
       }
   }
   ```

   Il codice sorgente creato dal modello di unit test esegue le operazioni seguenti:

   - Importa lo spazio dei nomi <xref:Microsoft.VisualStudio.TestTools.UnitTesting?displayProperty=nameWithType>, contenente i tipi usati per il testing unità.
   - Applica l'attributo <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> alla classe `UnitTest1`.
   - Applica l' <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> attributo a `TestMethod1` .

   Ogni metodo contrassegnato con [[TestMethod]](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute) in una classe di test contrassegnata con [[TestClass]](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute) viene eseguito automaticamente quando viene eseguito il unit test.

## <a name="add-a-project-reference"></a>Aggiungere un riferimento al progetto

Per usare il progetto di test con la `StringLibrary` classe, aggiungere un riferimento al `StringLibrary` progetto.

1. Nel riquadro della **soluzione** , <kbd>fare</kbd>clic su **dipendenze** sotto **StringLibraryTest**. Scegliere **Aggiungi riferimento** dal menu di scelta rapida.

1. Nella finestra di dialogo **riferimenti** selezionare il progetto **StringLibrary** . Selezionare **OK**.

      :::image type="content" source="media/testing-library-with-visual-studio-mac/visual-studio-mac-edit-references.png" alt-text="Finestra di dialogo Modifica riferimenti di Visual Studio per Mac":::

## <a name="add-and-run-unit-test-methods"></a>Aggiungere ed eseguire unit test metodi

Quando Visual Studio esegue una unit test, viene eseguito ogni metodo contrassegnato con l' <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> attributo in una classe contrassegnata con l' <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> attributo. Un metodo di test termina quando viene rilevato il primo errore o quando tutti i test contenuti nel metodo hanno avuto esito positivo.

I test più comuni chiamano i membri della classe <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert>. Molti metodi assert includono almeno due parametri, uno dei quali corrisponde al risultato previsto del test, mentre l'altro corrisponde al risultato effettivo. `Assert`Nella tabella seguente sono illustrati alcuni dei metodi chiamati più di frequente della classe:

| Metodi Assert     | Funzione |
| ------------------ | -------- |
| `Assert.AreEqual`  | Verifica che due oggetti o valori siano uguali. L'asserzione ha esito negativo se i valori o gli oggetti non sono uguali. |
| `Assert.AreSame`   | Verifica che due variabili oggetto facciano riferimento allo stesso oggetto. Il metodo ha esito negativo se le variabili fanno riferimento a oggetti diversi. |
| `Assert.IsFalse`   | Verifica che una condizione sia `false`. Il metodo ha esito negativo se la condizione è `true`. |
| `Assert.IsNotNull` | Verifica che un oggetto non sia `null` . Il metodo ha esito negativo se l'oggetto è `null`. |

È anche possibile usare il <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.ThrowsException%2A?displayProperty=nameWithType> metodo in un metodo di test per indicare il tipo di eccezione che si prevede venga generata. Il test ha esito negativo se l'eccezione specificata non viene generata.

Durante il test del metodo `StringLibrary.StartsWithUpper`, è possibile specificare alcune stringhe che iniziano con un carattere maiuscolo. In tal caso si prevede che il metodo restituisca `true`, quindi è possibile chiamare il metodo <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsTrue%2A?displayProperty=nameWithType>. Analogamente, è possibile specificare alcune stringhe che iniziano con un valore diverso da un carattere maiuscolo. In tal caso si prevede che il metodo restituisca `false`, quindi è possibile chiamare il metodo <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsFalse%2A?displayProperty=nameWithType>.

Poiché il metodo della libreria gestisce le stringhe, è anche necessario assicurarsi che gestisca correttamente una [stringa vuota ( `String.Empty` )](xref:System.String.Empty), una stringa valida senza caratteri e il cui valore <xref:System.String.Length> è 0 e una `null` stringa che non è stata inizializzata. È possibile chiamare `StartsWithUpper` direttamente come metodo statico e passare un singolo <xref:System.String> argomento. In alternativa, è possibile chiamare `StartsWithUpper` come metodo di estensione su una `string` variabile assegnata a `null` .

Verranno definiti tre metodi, ognuno dei quali chiama un <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> metodo per ogni elemento in una matrice di stringhe. Si chiamerà un overload del metodo che consente di specificare un messaggio di errore da visualizzare in caso di errore del test. Il messaggio identifica la stringa che ha causato l'errore.

Per creare i metodi di test:

1. Aprire il file *UnitTest1.cs* e sostituire il codice con il codice seguente:

   :::code language="csharp" source="./snippets/library-with-visual-studio/csharp/StringLibraryTest/UnitTest1.cs":::

   Il test dei caratteri maiuscoli nel `TestStartsWithUpper` metodo include la lettera maiuscola greca Alpha (u + 0391) e la lettera maiuscola (u + maiuscola dell'alfabeto) cirillico. Il test di caratteri minuscoli nel `TestDoesNotStartWithUpper` metodo include la piccola lettera greca alfa (u + 03B1) e la lettera minuscola cirillico ghe minuscola (u + 0433).

1. Nella barra dei menu selezionare **file**  >  **Salva con nome**. Nella finestra di dialogo verificare che **Encoding** sia impostato su **Unicode (UTF-8)**.

   :::image type="content" source="media/testing-library-with-visual-studio-mac/save-file-as-dialog.png" alt-text="Finestra di dialogo Salva file con nome di Visual Studio":::

1. Quando viene chiesto se si desidera sostituire il file esistente, selezionare **Sostituisci**.

   Se il salvataggio del codice sorgente come file con codifica UTF8 ha esito negativo, Visual Studio può salvarlo come file ASCII. In tal caso, il runtime non decodifica accuratamente i caratteri UTF8 al di fuori dell'intervallo ASCII e i risultati del test non saranno corretti.

1. Aprire il pannello **Unit test** sul lato destro dello schermo. Selezionare **Visualizza**  >  **test** dal menu.

1. Fare clic sull'icona **Ancora** per mantenere aperto il pannello.

   :::image type="content" source="media/testing-library-with-visual-studio-mac/visual-studio-mac-unit-test-dock-icon.png" alt-text="Icona di ancoraggio del pannello degli unit test di Visual Studio per Mac":::

1. Fare clic sul pulsante **Esegui tutto**.

   Tutti i test hanno esito positivo.

   :::image type="content" source="media/testing-library-with-visual-studio-mac/visual-studio-mac-unit-test-pass.png" alt-text="Visual Studio per Mac sessioni di test previste":::

## <a name="handle-test-failures"></a>Gestione degli errori di test

Se si sta eseguendo lo sviluppo basato su test (TDD), si scrivono prima i test e hanno esito negativo la prima volta che vengono eseguiti. Si aggiunge quindi il codice all'app che rende il test riuscito. Per questa esercitazione è stato creato il test dopo la scrittura del codice dell'app che convalida, quindi non si è visto che il test non è riuscito. Per convalidare l'esito negativo di un test quando si prevede che abbia esito negativo, aggiungere un valore non valido all'input di test.

1. Modificare la matrice `words` del metodo `TestDoesNotStartWithUpper` per includere la stringa "Error". Non è necessario salvare il file perché Visual Studio salva i file aperti automaticamente quando viene creata una soluzione per eseguire i test.

   ```csharp
   string[] words = { "alphabet", "Error", "zebra", "abc", "αυτοκινητοβιομηχανία", "государство",
                      "1234", ".", ";", " " };
   ```

1. Eseguire di nuovo i test.

   Questa volta, la finestra **Esplora test** indica che due test hanno avuto esito positivo e uno non è riuscito.

   :::image type="content" source="media/testing-library-with-visual-studio-mac/failed-test-window.png" alt-text="Finestra di Esplora test con i test non riusciti":::

1. <kbd>premere CTRL</kbd>e fare clic sul test non superato, `TestDoesNotStartWithUpper` quindi selezionare **Mostra riquadro risultati** nel menu di scelta rapida.

   Nel riquadro **dei risultati** viene visualizzato il messaggio prodotto dall'asserzione: "Assert. false non è riuscito. Expected for 'Error': false; actual: True". A causa dell'errore, non sono state testate stringhe nella matrice dopo l'errore.

   :::image type="content" source="media/testing-library-with-visual-studio-mac/visual-studio-mac-unit-test-failure.png" alt-text="Finestra Esplora test che mostra l'errore di asserzione false":::

1. Rimuovere la stringa "Error" aggiunta nel passaggio 1. Eseguire di nuovo il test e i test superati.

## <a name="test-the-release-version-of-the-library"></a>Testare la versione di rilascio della libreria

Ora che i test sono stati superati quando si esegue la build di debug della libreria, eseguire i test per un ulteriore tempo rispetto alla build di rilascio della libreria. Esistono infatti alcuni fattori, ad esempio le ottimizzazioni del compilatore, in grado di generare a volte comportamenti diversi tra la versione di debug e quella di rilascio.

Per testare la versione di rilascio, seguire questa procedura:

1. Nella barra degli strumenti di Visual Studio modificare la configurazione di compilazione da **Debug** a **Rilascio**.

   :::image type="content" source="media/testing-library-with-visual-studio-mac/visual-studio-toolbar-release.png" alt-text="Barra degli strumenti di Visual Studio con la configurazione di rilascio evidenziata":::

1. Nel riquadro della **soluzione** , fare clic con il <kbd>pulsante destro del</kbd>mouse sul progetto **StringLibrary** e scegliere **Compila** dal menu di scelta rapida per ricompilare la libreria.

   :::image type="content" source="media/testing-library-with-visual-studio-mac/build-library-context-menu.png" alt-text="Menu di scelta rapida StringLibrary con il comando di compilazione":::

1. Eseguire di nuovo gli unit test.

   I test avranno esito positivo.

## <a name="debug-tests"></a>Esecuzione del debug dei test

È possibile usare lo stesso processo illustrato in [esercitazione: eseguire il debug di un'applicazione console .NET Core usando Visual Studio per Mac](debugging-with-visual-studio-mac.md) per eseguire il debug del codice usando il progetto unit test. Anziché avviare il progetto di app ShowCase, fare clic con il <kbd>pulsante destro del</kbd>mouse sul progetto **StringLibraryTests** e scegliere **Avvia progetto di debug** dal menu di scelta rapida. Visual Studio avvia il progetto di test con il debugger collegato. L'esecuzione si arresterà in corrispondenza di qualsiasi punto di interruzione aggiunto al progetto di test o al codice della libreria sottostante.

## <a name="additional-resources"></a>Risorse aggiuntive

* [Testing unità in .NET Core e .NET Standard](../testing/index.md)

## <a name="next-steps"></a>Passaggi successivi

In questa esercitazione è stata testata una libreria di classi. Per rendere la libreria disponibile ad altri, è possibile pubblicarla in [NuGet](https://nuget.org) come pacchetto. Per informazioni su come seguire un'esercitazione su NuGet:

> [!div class="nextstepaction"]
> [Creare e pubblicare un pacchetto (interfaccia della riga di comando dotnet)](/nuget/quickstart/create-and-publish-a-package-using-the-dotnet-cli)

Se si pubblica una libreria come pacchetto NuGet, altri utenti possono installarla e usarla. Per informazioni su come seguire un'esercitazione su NuGet:

> [!div class="nextstepaction"]
> [Installare e usare un pacchetto in Visual Studio per Mac](/nuget/quickstart/install-and-use-a-package-in-visual-studio-mac)

Una libreria non deve essere distribuita come pacchetto. Può essere incluso in un'app console che lo usa. Per informazioni su come pubblicare un'app console, vedere l'esercitazione precedente in questa serie:

> [!div class="nextstepaction"]
> [Pubblicare un'applicazione console .NET Core con Visual Studio per Mac](publishing-with-visual-studio-mac.md)

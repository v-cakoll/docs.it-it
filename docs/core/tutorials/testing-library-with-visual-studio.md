---
title: Testare una libreria di classi .NET Standard con .NET Core in Visual Studio
description: Creare un progetto di unit test per la libreria di classi .NET Core. Verificare che la libreria di classi .NET Core funzioni correttamente con gli unit test.
ms.date: 05/21/2020
dev_langs:
- csharp
- vb
ms.custom: vs-dotnet
ms.openlocfilehash: 48ada77b8422030fd93aa29df1df50a3ae5104fe
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84283507"
---
# <a name="tutorial-test-a-net-standard-library-with-net-core-in-visual-studio"></a>Esercitazione: testare una libreria di .NET Standard con .NET Core in Visual Studio

Questa esercitazione illustra come automatizzare gli unit test aggiungendo un progetto di test a una soluzione.

## <a name="prerequisites"></a>Prerequisiti

- Questa esercitazione funziona con la soluzione creata in [creare una libreria di .NET standard in Visual Studio](library-with-visual-studio.md).

## <a name="create-a-unit-test-project"></a>Creare un progetto di unit test

1. Aprire la `ClassLibraryProjects` soluzione creata in [creare una libreria di .NET standard in Visual Studio](library-with-visual-studio.md).

1. Aggiungere un nuovo progetto unit test denominato "StringLibraryTest" alla soluzione.

   1. Fare clic con il pulsante destro del mouse sulla soluzione in **Esplora soluzioni** e scegliere **Aggiungi**  >  **nuovo progetto**.

   1. Nella pagina **Aggiungi nuovo progetto** immettere **MSTest** nella casella di ricerca. Scegliere **C#** o **Visual Basic** dall'elenco lingua, quindi scegliere tutte le **piattaforme** dall'elenco piattaforma.

   1. Scegliere il modello **progetto di test MSTest (.NET Core)** , quindi fare clic su **Avanti**.

   1. Nella pagina **Configura nuovo progetto** immettere **StringLibraryTest** nella casella **nome progetto** . Scegli quindi **Crea**.

   > [!NOTE]
   > MSTest è uno dei tre Framework di test tra cui è possibile scegliere. Gli altri sono xUnit e nUnit.

1. Visual Studio crea il progetto e apre il file di classe nella finestra del codice con il codice seguente. Se la lingua che si desidera utilizzare non è visualizzata, modificare il selettore della lingua nella parte superiore della pagina.

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

   ```vb
   Imports Microsoft.VisualStudio.TestTools.UnitTesting

   Namespace StringLibraryTest
       <TestClass>
       Public Class UnitTest1
           <TestMethod>
           Sub TestSub()

           End Sub
       End Class
   End Namespace
   ```

   Il codice sorgente creato dal modello di unit test esegue le operazioni seguenti:

   - Importa lo spazio dei nomi <xref:Microsoft.VisualStudio.TestTools.UnitTesting?displayProperty=nameWithType>, contenente i tipi usati per il testing unità.
   - Applica l'attributo <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> alla classe `UnitTest1`.
   - Applica l' <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> attributo per definire `TestMethod1` in C# o `TestSub` in Visual Basic.

   Ogni metodo contrassegnato con [[TestMethod]](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute) in una classe di test contrassegnata con [[TestClass]](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute) viene eseguito automaticamente quando viene eseguito il unit test.

1. In **Esplora soluzioni**fare clic con il pulsante destro del mouse sul nodo **dipendenze** del progetto **StringLibraryTest** e scegliere **Aggiungi riferimento al progetto** dal menu di scelta rapida.

1. Nella finestra di dialogo **Gestione riferimenti** espandere il nodo **progetti** , quindi selezionare la casella accanto a **StringLibrary**. L'aggiunta di un riferimento all' `StringLibrary` assembly consente al compilatore di trovare i metodi **StringLibrary** durante la compilazione del progetto **StringLibraryTest** .

1. Selezionare **OK**.

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

Poiché il metodo della libreria gestisce le stringhe, è anche necessario assicurarsi che gestisca correttamente una [stringa vuota ( `String.Empty` )](xref:System.String.Empty), una stringa valida senza caratteri e il cui valore <xref:System.String.Length> è 0 e una `null` stringa che non è stata inizializzata. Se `StartsWithUpper` viene chiamato come metodo di estensione su un' <xref:System.String> istanza, non può essere passato a una `null` stringa. È tuttavia possibile chiamarlo direttamente come metodo statico e passarlo a un singolo argomento <xref:System.String>.

Verranno definiti tre metodi, ognuno dei quali chiama <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> ripetutamente un metodo per ogni elemento in una matrice di stringhe. Poiché il metodo di test ha esito negativo non appena viene trovato il primo errore, verrà chiamato un overload del metodo che consente di passare una stringa che indica il valore stringa usato nella chiamata al metodo.

Per creare i metodi di test:

1. Nella finestra del codice *UnitTest1.cs* o *UnitTest1. vb* sostituire il codice con il codice seguente:

   :::code language="csharp" source="./snippets/library-with-visual-studio/csharp/StringLibraryTest/UnitTest1.cs":::
   :::code language="vb" source="./snippets/library-with-visual-studio/vb/StringLibraryTest/UnitTest1.vb":::

   Il test dei caratteri maiuscoli nel `TestStartsWithUpper` metodo include la lettera maiuscola greca Alpha (u + 0391) e la lettera maiuscola (u + maiuscola dell'alfabeto) cirillico. Il test di caratteri minuscoli nel `TestDoesNotStartWithUpper` metodo include la piccola lettera greca alfa (u + 03B1) e la lettera minuscola cirillico ghe minuscola (u + 0433).

1. Nella barra dei menu selezionare **file**  >  **Salva UnitTest1.cs come** o **file**  >  **Salva UnitTest1. vb con nome**. Nella finestra di dialogo **Salva file con nome** selezionare la freccia accanto al pulsante **Salva** e selezionare **Salva con codifica**.

   > [!div class="mx-imgBorder"]
   > ![Finestra di dialogo Salva file con nome di Visual Studio](./media/testing-library-with-visual-studio/save-file-as-dialog.png)

1. Nella finestra di dialogo **Conferma Salva con nome** selezionare il pulsante **Sì** per salvare il file.

1. Nella finestra di dialogo **Opzioni di salvataggio avanzate** selezionare **Unicode (UTF-8 con firma digitale) - Tabella codici 65001** dall'elenco a discesa **Codifica** e selezionare **OK**.

   > [!div class="mx-imgBorder"]
   > ![Finestra di dialogo di Visual Studio Opzioni di salvataggio avanzate](./media/testing-library-with-visual-studio/advanced-save-options.png)

   Se il salvataggio del codice sorgente come file con codifica UTF8 ha esito negativo, Visual Studio può salvarlo come file ASCII. In tal caso, il runtime non decodifica accuratamente i caratteri UTF8 al di fuori dell'intervallo ASCII e i risultati del test non saranno corretti.

1. Sulla barra dei menu selezionare **test**  >  **Esegui tutti i test**. Se la finestra **Esplora test** non viene aperta, aprirla **scegliendo**  >  **Esplora test**test. I tre test sono elencati nella sezione **Test superati** e nella sezione **Riepilogo** è riportato il risultato dell'esecuzione dei test.

   > [!div class="mx-imgBorder"]
   > ![Finestra di Esplora test con i test riusciti](./media/testing-library-with-visual-studio/test-explorer-window.png)

## <a name="handle-test-failures"></a>Gestione degli errori di test

Se si sta eseguendo lo sviluppo basato su test (TDD), si scrivono prima i test e hanno esito negativo la prima volta che vengono eseguiti. Si aggiunge quindi il codice all'app che rende il test riuscito. In questo caso, il test è stato creato dopo la scrittura del codice dell'app che convalida, quindi non si è visto che il test non è riuscito. Per convalidare l'esito negativo di un test quando si prevede che abbia esito negativo, aggiungere un valore non valido all'input di test.

1. Modificare la matrice `words` del metodo `TestDoesNotStartWithUpper` per includere la stringa "Error". Non è necessario salvare il file perché Visual Studio salva i file aperti automaticamente quando viene creata una soluzione per eseguire i test.

   ```csharp
   string[] words = { "alphabet", "Error", "zebra", "abc", "αυτοκινητοβιομηχανία", "государство",
                      "1234", ".", ";", " " };
   ```

   ```vb
   Dim words() As String = { "alphabet", "Error", "zebra", "abc", "αυτοκινητοβιομηχανία", "государство",
                      "1234", ".", ";", " " }

   ```

1. Eseguire il test selezionando **test**  >  **Esegui tutti i test** dalla barra dei menu. La finestra **Esplora test** indica che due test hanno avuto esito positivo e uno esito negativo.

   > [!div class="mx-imgBorder"]
   > ![Finestra di Esplora test con i test non riusciti](./media/testing-library-with-visual-studio/failed-test-window.png)

1. Selezionare il test non superato `TestDoesNotStartWith` . Nella finestra **Esplora test** viene visualizzato il messaggio generato dal metodo Assert: "Assert.IsFalse failed. Expected for 'Error': false; actual: True". A causa dell'errore, non sono state testate tutte le stringhe della matrice dopo l'errore.

   > [!div class="mx-imgBorder"]
   > ![Finestra Esplora test che mostra l'errore di asserzione false](./media/testing-library-with-visual-studio/failed-test-detail.png)

1. Annullare la modifica apportata nel passaggio 1 e rimuovere la stringa "Error". Eseguire di nuovo il test e i test superati.

## <a name="test-the-release-version-of-the-library"></a>Testare la versione di rilascio della libreria

Ora che i test sono stati superati quando si esegue la versione di debug della libreria, eseguire i test per un ulteriore tempo rispetto alla build di rilascio della libreria. Esistono infatti alcuni fattori, ad esempio le ottimizzazioni del compilatore, in grado di generare a volte comportamenti diversi tra la versione di debug e quella di rilascio.

Per testare la versione di rilascio, seguire questa procedura:

1. Nella barra degli strumenti di Visual Studio modificare la configurazione di compilazione da **Debug** a **Rilascio**.

   > [!div class="mx-imgBorder"]
   > ![Barra degli strumenti di Visual Studio con la configurazione di rilascio evidenziata](./media/testing-library-with-visual-studio/visual-studio-toolbar-release.png)

1. In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul progetto **StringLibrary** e selezionare **Compila** dal menu di scelta rapida per ricompilare la libreria.

   > [!div class="mx-imgBorder"]
   > ![Menu di scelta rapida StringLibrary con il comando di compilazione](./media/testing-library-with-visual-studio/build-library-context-menu.png)

1. Eseguire gli unit test scegliendo **test Esegui**  >  **tutti i test** dalla barra dei menu. I test avranno esito positivo.

## <a name="additional-resources"></a>Risorse aggiuntive

- [Nozioni fondamentali sugli unit test di Visual Studio](/visualstudio/test/unit-test-basics)

## <a name="next-steps"></a>Passaggi successivi

In questa esercitazione è stata testata una libreria di classi. Per rendere la libreria disponibile ad altri, è possibile pubblicarla in [NuGet](https://nuget.org) come pacchetto. Per informazioni su come seguire un'esercitazione su NuGet:

> [!div class="nextstepaction"]
> [Creare e pubblicare un pacchetto NuGet con Visual Studio](/nuget/quickstart/create-and-publish-a-package-using-visual-studio?tabs=netcore-cli)

Se si pubblica una libreria come pacchetto NuGet, altri utenti possono installarla e usarla. Per informazioni su come seguire un'esercitazione su NuGet:

> [!div class="nextstepaction"]
> [Installare e usare un pacchetto in Visual Studio](/nuget/quickstart/install-and-use-a-package-in-visual-studio)

Una libreria non deve essere distribuita come pacchetto. Può essere incluso in un'app console che lo usa. Per informazioni su come pubblicare un'app console, vedere l'esercitazione precedente in questa serie:

> [!div class="nextstepaction"]
> [Pubblicare un'applicazione console .NET Core con Visual Studio](publishing-with-visual-studio.md)

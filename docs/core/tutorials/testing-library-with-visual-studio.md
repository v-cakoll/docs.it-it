---
title: Testare una libreria di classi .NET Standard con .NET Core in Visual StudioTest a .NET Standard class library with .NET Core in Visual Studio
description: Creare un progetto di unit test per la libreria di classi .NET Core. Verificare che la libreria di classi .NET Core funzioni correttamente con gli unit test.
ms.date: 12/24/2019
dev_langs:
- csharp
- vb
ms.custom: vs-dotnet, seodoc18
ms.openlocfilehash: 307261088f5c7c69c0e69fbd6b99940c04842eec
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "78156621"
---
# <a name="test-a-net-standard-library-with-net-core-in-visual-studio"></a>Testare una libreria .NET Standard con .NET Core in Visual StudioTest a .NET Standard library with .NET Core in Visual Studio

In [Compilare una libreria .NET Standard in Visual Studio](library-with-visual-studio.md)è stata <xref:System.String> creata una semplice libreria di classi che aggiunge un metodo di estensione alla classe . Ora verrà creato uno unit test per verificare che tale libreria funzioni nel modo previsto. Il progetto unit test verrà aggiunto alla soluzione creata nell'articolo precedente.

## <a name="create-a-unit-test-project"></a>Creare un progetto di unit test

Per creare un progetto unit test, seguire questa procedura:

1. Aprire `ClassLibraryProjects` la soluzione creata nell'articolo [Compilare una libreria .NET Standard in Visual Studio.Open](library-with-visual-studio.md) the solution you created in the Build a .NET Standard library in Visual Studio article.

1. Aggiungere un nuovo progetto di unit test denominato "StringLibraryTest" alla soluzione.

   1. Fare clic con il pulsante destro del mouse sulla soluzione in **Esplora soluzioni** e selezionare **Aggiungi** > **nuovo progetto**.

   1. Nella pagina **Aggiungi un nuovo progetto** immettere **mstest** nella casella di ricerca. Scegliere **C '** o Visual **Basic** dall'elenco linguaggio e quindi scegliere Tutte **le piattaforme** dall'elenco Piattaforma . Scegliere il modello **MsTest Test Project (.NET Core)** e quindi scegliere **Avanti**.

   1. Nella pagina **Configura il nuovo progetto** immettere **StringLibraryTest** nella casella **Nome progetto.** quindi scegliere **Crea**.

   > [!NOTE]
   > Oltre a MSTest, è anche possibile creare progetti di test xUnit e nUnit per .NET Core in Visual Studio.

1. Visual Studio crea il progetto e apre il file di classe nella finestra del codice con il codice seguente:

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

   - Applica l'attributo [TestClass](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute) alla classe `UnitTest1`. Ogni metodo di test presente in una classe di test contrassegnata con l'attributo [TestMethod](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute) viene eseguito automaticamente durante l'esecuzione dello unit test.

   - Applica l'attributo [TestMethod](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute) da `TestMethod1` `TestSub` definire in C, o in Visual Basic come metodo di test per l'esecuzione automatica quando viene eseguito lo unit test.

1. In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul nodo **Dipendenze** del progetto **StringLibraryTest** e selezionare **Aggiungi riferimento** dal menu di scelta rapida.

   > [!div class="mx-imgBorder"]
   > ![Menu di scelta rapida delle dipendenze StringLibraryTest](./media/testing-library-with-visual-studio/add-reference-context-menu.png)

1. Nella finestra di dialogo **Gestione riferimenti** espandere il nodo **Progetti** e selezionare la casella accanto a **StringLibrary**. L'aggiunta di un riferimento all'assembly `StringLibrary` consente al compilatore di individuare i metodi **StringLibrary**. Selezionare il pulsante **OK.** Un riferimento viene aggiunto al `StringLibrary`progetto di libreria di classi, .

   ![Finestra di dialogo Gestione riferimenti in Visual Studio](./media/testing-library-with-visual-studio/project-reference-manager.png)

## <a name="add-and-run-unit-test-methods"></a>Aggiungere ed eseguire metodi di unit test

Quando Visual Studio esegue uno unit test, esegue ogni <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> metodo contrassegnato con l'attributo <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> in una classe di unit test, la classe a cui viene applicato l'attributo. Un metodo di test termina quando viene rilevato il primo errore o quando tutti i test contenuti nel metodo hanno avuto esito positivo.

I test più comuni chiamano i membri della classe <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert>. Molti metodi assert includono almeno due parametri, uno dei quali corrisponde al risultato previsto del test, mentre l'altro corrisponde al risultato effettivo. Nella tabella `Assert` seguente sono riportati alcuni dei metodi chiamati più di frequente dalla classe:

| Metodi Assert     | Funzione |
| ------------------ | -------- |
| `Assert.AreEqual`  | Verifica che due oggetti o valori siano uguali. L'asserzione ha esito negativo se i valori o gli oggetti non sono uguali. |
| `Assert.AreSame`   | Verifica che due variabili oggetto facciano riferimento allo stesso oggetto. Il metodo ha esito negativo se le variabili fanno riferimento a oggetti diversi. |
| `Assert.IsFalse`   | Verifica che una condizione sia `false`. Il metodo ha esito negativo se la condizione è `true`. |
| `Assert.IsNotNull` | Verifica che un oggetto non `null`sia . Il metodo ha esito negativo se l'oggetto è `null`. |

È inoltre possibile <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.ThrowsException%2A> utilizzare il metodo in un metodo di test per indicare il tipo di eccezione che deve generare. Il test ha esito negativo se non viene generata l'eccezione specificata.

Durante il test del metodo `StringLibrary.StartsWithUpper`, è possibile specificare alcune stringhe che iniziano con un carattere maiuscolo. In tal caso si prevede che il metodo restituisca `true`, quindi è possibile chiamare il metodo <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsTrue%2A>. Analogamente, è possibile specificare alcune stringhe che iniziano con un valore diverso da un carattere maiuscolo. In tal caso si prevede che il metodo restituisca `false`, quindi è possibile chiamare il metodo <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsFalse%2A>.

Poiché il metodo della libreria gestisce le stringhe, è anche necessario assicurarsi che gestisca <xref:System.String.Length> correttamente una `null` stringa [vuota (`String.Empty`)](xref:System.String.Empty), una stringa valida che non contiene caratteri e la cui valore 0 e una stringa che non è stata inizializzata. Se `StartsWithUpper` viene chiamato come metodo <xref:System.String> di estensione in un'istanza, non può essere passata una `null` stringa. È tuttavia possibile chiamarlo direttamente come metodo statico e passarlo a un singolo argomento <xref:System.String>.

Si definiranno tre metodi, ognuno dei quali chiama ripetutamente un <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> metodo per ogni elemento in una matrice di stringhe. Poiché il metodo di test ha esito negativo non appena viene trovato il primo errore, verrà chiamato un overload del metodo che consente di passare una stringa che indica il valore stringa utilizzato nella chiamata al metodo.

Per creare i metodi di test:

1. Nella finestra del codice *UnitTest1.cs* o *UnitTest1.vb* sostituire il codice con il codice seguente:

   [!code-csharp[Test#1](~/samples/snippets/csharp/getting_started/with_visual_studio_2017/testlib1.cs)]
   [!code-vb[Test#1](~/samples/snippets/core/tutorials/vb-library-with-visual-studio/testlib.vb)]

   Il test dei caratteri `TestStartsWithUpper` maiuscoli nel metodo include la lettera maiuscola greca alfa (U-0391) e la lettera maiuscola cirillica EM (U-041C). Il test dei caratteri `TestDoesNotStartWithUpper` minuscoli nel metodo include la lettera piccola greca alfa (U-03B1) e la lettera piccola cirillica Ghe (U-0433).

1. Sulla barra dei menu selezionare **Salva file** > **UnitTest1.cs con nome** o Salva **file** > **UnitTest1.vb con nome**. Nella finestra di dialogo **Salva file con nome** selezionare la freccia accanto al pulsante **Salva** e selezionare **Salva con codifica**.

   > [!div class="mx-imgBorder"]
   > ![Finestra di dialogo Salva file con nome di Visual Studio](./media/testing-library-with-visual-studio/save-file-as-dialog.png)

1. Nella finestra di dialogo **Conferma Salva con nome** selezionare il pulsante **Sì** per salvare il file.

1. Nella finestra di dialogo **Opzioni di salvataggio avanzate** selezionare **Unicode (UTF-8 con firma digitale) - Tabella codici 65001** dall'elenco a discesa **Codifica** e selezionare **OK**.

   > [!div class="mx-imgBorder"]
   > ![Finestra di dialogo di Visual Studio Opzioni di salvataggio avanzate](./media/testing-library-with-visual-studio/advanced-save-options.png)

   Se il salvataggio del codice sorgente come file con codifica UTF8 ha esito negativo, Visual Studio può salvarlo come file ASCII. In questo caso, il runtime non decodifica con precisione i caratteri UTF8 al di fuori dell'intervallo ASCII e i risultati del test non saranno corretti.

1. Sulla barra dei menu selezionare**Esecuzione** >  **dei test** > **di tutti i test**. Viene aperta la finestra **Esplora test** che illustra che i test sono stati eseguiti correttamente. I tre test sono elencati nella sezione **Test superati** e nella sezione **Riepilogo** è riportato il risultato dell'esecuzione dei test.

   > [!div class="mx-imgBorder"]
   > ![Finestra di Esplora test con i test riusciti](./media/testing-library-with-visual-studio/test-explorer-window.png)

## <a name="handle-test-failures"></a>Gestire gli errori di test

L'esecuzione dei test non ha generato errori ma è opportuno apportare qualche modifica in modo che uno dei metodi di test abbia esito negativo:

1. Modificare la matrice `words` del metodo `TestDoesNotStartWithUpper` per includere la stringa "Error". Non è necessario salvare il file perché Visual Studio salva i file aperti automaticamente quando viene creata una soluzione per eseguire i test.

   ```csharp
   string[] words = { "alphabet", "Error", "zebra", "abc", "αυτοκινητοβιομηχανία", "государство",
                      "1234", ".", ";", " " };
   ```

   ```vb
   Dim words() As String = { "alphabet", "Error", "zebra", "abc", "αυτοκινητοβιομηχανία", "государство",
                      "1234", ".", ";", " " }

   ```

1. Eseguire il test selezionando**Esecuzione** >  **dei test** > **tutti i test** dalla barra dei menu. La finestra **Esplora test** indica che due test hanno avuto esito positivo e uno esito negativo.

   > [!div class="mx-imgBorder"]
   > ![Finestra di Esplora test con i test non riusciti](./media/testing-library-with-visual-studio/failed-test-window.png)

1. Selezionare il `TestDoesNotStartWith`test non riuscito, . Nella finestra **Esplora test** viene visualizzato il messaggio generato dal metodo Assert: "Assert.IsFalse failed. Expected for 'Error': false; actual: True". A causa dell'errore, tutte le stringhe nella matrice dopo "Errore" non sono state testate.

   > [!div class="mx-imgBorder"]
   > ![Finestra Esplora test con l'errore di asserzione IsFalse](./media/testing-library-with-visual-studio/failed-test-detail.png)

1. Annullare la modifica apportata nel passaggio 1 e rimuovere la stringa "Error". Eseguire nuovamente il test. I test verranno superati.

## <a name="test-the-release-version-of-the-library"></a>Testare la versione finale della libreria

I test sono stati eseguiti con la versione di debug della libreria. Dopo che tutti i test sono stati superati e la libreria è stata testata in modo adeguato, è necessario ripetere i test con la versione di rilascio della libreria stessa. Esistono infatti alcuni fattori, ad esempio le ottimizzazioni del compilatore, in grado di generare a volte comportamenti diversi tra la versione di debug e quella di rilascio.

Per testare la versione di rilascio, seguire questa procedura:

1. Nella barra degli strumenti di Visual Studio modificare la configurazione di compilazione da **Debug** a **Rilascio**.

   > [!div class="mx-imgBorder"]
   > ![Barra degli strumenti di Visual Studio con la configurazione di rilascio evidenziata](./media/testing-library-with-visual-studio/visual-studio-toolbar-release.png)

1. In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul progetto **StringLibrary** e selezionare **Compila** dal menu di scelta rapida per ricompilare la libreria.

   > [!div class="mx-imgBorder"]
   > ![Menu di scelta rapida StringLibrary con il comando di compilazione](./media/testing-library-with-visual-studio/build-library-context-menu.png)

1. Eseguire gli unit test scegliendo**Esecuzione** >  **dei test** > **tutti i test** dalla barra dei menu. I test avranno esito positivo.

Dopo aver completato le operazioni di test della libreria, il passaggio successivo consiste nel rendere quest'ultima disponibile ai chiamanti. È possibile aggregarla a una o più applicazioni oppure è possibile distribuirla come pacchetto NuGet. Per altre informazioni, vedere [Consuming a .NET Standard Class Library](consuming-library-with-visual-studio.md) (Utilizzo di una libreria di classi .NET Standard).

## <a name="see-also"></a>Vedere anche

- [Nozioni di base su unit test - Visual Studio](/visualstudio/test/unit-test-basics)

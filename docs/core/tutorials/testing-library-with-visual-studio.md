---
title: Testare una libreria di classi .NET Standard con .NET Core in Visual Studio
description: Creare un progetto di unit test per la libreria di classi .NET Core. Verificare che la libreria di classi .NET Core funzioni correttamente con gli unit test.
ms.date: 12/24/2019
dev_langs:
- csharp
- vb
ms.custom: vs-dotnet, seodoc18
ms.openlocfilehash: 3a4f25b0d250469102fdac6ee960e42b2d969aed
ms.sourcegitcommit: f8c36054eab877de4d40a705aacafa2552ce70e9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/31/2019
ms.locfileid: "75559578"
---
# <a name="test-a-net-standard-library-with-net-core-in-visual-studio"></a>Testare una libreria di .NET Standard con .NET Core in Visual Studio

In [creare una libreria di .NET standard in Visual Studio](library-with-visual-studio.md)è stata creata una libreria di classi semplice che aggiunge un metodo di estensione alla classe <xref:System.String>. Ora verrà creato uno unit test per verificare che tale libreria funzioni nel modo previsto. Il progetto unit test verrà aggiunto alla soluzione creata nell'articolo precedente.

## <a name="create-a-unit-test-project"></a>Crea progetto unit test

Per creare un progetto unit test, seguire questa procedura:

1. Aprire la soluzione `ClassLibraryProjects` creata nell'articolo [creare una libreria di .NET standard in Visual Studio](library-with-visual-studio.md) .

1. Aggiungere un nuovo progetto unit test denominato "StringLibraryTest" alla soluzione.

   1. Fare clic con il pulsante destro del mouse sulla soluzione in **Esplora soluzioni** e scegliere **Aggiungi** > **nuovo progetto**.

   1. Nella pagina **Aggiungi nuovo progetto** immettere **MSTest** nella casella di ricerca. Scegliere **C#** o **Visual Basic** dall'elenco lingua, quindi scegliere tutte le **piattaforme** dall'elenco piattaforma. Scegliere il modello **progetto di test MSTest (.NET Core)** , quindi fare clic su **Avanti**.

   1. Nella pagina **Configura nuovo progetto** immettere **StringLibraryTest** nella casella **nome progetto** . Scegli quindi **Crea**.

   > [!NOTE]
   > Oltre a un MSTest, è anche possibile creare progetti di test xUnit e nUnit per .NET Core in Visual Studio.

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

   - Applica l'attributo [TestMethod](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute) per definire `TestMethod1` in C# o `TestSub` in Visual Basic come metodo di test per l'esecuzione automatica quando viene eseguito il unit test.

1. In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul nodo **Dipendenze** del progetto **StringLibraryTest** e selezionare **Aggiungi riferimento** dal menu di scelta rapida.

   > [!div class="mx-imgBorder"]
   > ![menu di scelta rapida delle dipendenze di StringLibraryTest](./media/testing-library-with-visual-studio/add-reference-context-menu.png)

1. Nella finestra di dialogo **Gestione riferimenti** espandere il nodo **Progetti** e selezionare la casella accanto a **StringLibrary**. L'aggiunta di un riferimento all'assembly `StringLibrary` consente al compilatore di individuare i metodi **StringLibrary**. Selezionare il pulsante **OK** . Viene aggiunto un riferimento al progetto di libreria di classi `StringLibrary`.

   ![Finestra di dialogo Gestione riferimenti in Visual Studio](./media/testing-library-with-visual-studio/project-reference-manager.png)

## <a name="add-and-run-unit-test-methods"></a>Aggiungere ed eseguire unit test metodi

Quando Visual Studio esegue una unit test, esegue ogni metodo contrassegnato con l'attributo <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> in una classe unit test, la classe a cui viene applicato l'attributo <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute>. Un metodo di test termina quando viene rilevato il primo errore o quando tutti i test contenuti nel metodo hanno avuto esito positivo.

I test più comuni chiamano i membri della classe <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert>. Molti metodi assert includono almeno due parametri, uno dei quali corrisponde al risultato previsto del test, mentre l'altro corrisponde al risultato effettivo. Nella tabella seguente sono illustrati alcuni dei metodi chiamati più di frequente della classe `Assert`.

| Metodi Assert     | Funzione |
| ------------------ | -------- |
| `Assert.AreEqual`  | Verifica che due oggetti o valori siano uguali. L'asserzione ha esito negativo se i valori o gli oggetti non sono uguali. |
| `Assert.AreSame`   | Verifica che due variabili oggetto facciano riferimento allo stesso oggetto. Il metodo ha esito negativo se le variabili fanno riferimento a oggetti diversi. |
| `Assert.IsFalse`   | Verifica che una condizione sia `false`. Il metodo ha esito negativo se la condizione è `true`. |
| `Assert.IsNotNull` | Verifica che un oggetto non sia `null`. Il metodo ha esito negativo se l'oggetto è `null`. |

È anche possibile usare il metodo <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.ThrowsException%2A> in un metodo di test per indicare il tipo di eccezione che si prevede venga generata. Il test ha esito negativo se l'eccezione specificata non viene generata.

Durante il test del metodo `StringLibrary.StartsWithUpper`, è possibile specificare alcune stringhe che iniziano con un carattere maiuscolo. In tal caso si prevede che il metodo restituisca `true`, quindi è possibile chiamare il metodo <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsTrue%2A>. Analogamente, è possibile specificare alcune stringhe che iniziano con un valore diverso da un carattere maiuscolo. In tal caso si prevede che il metodo restituisca `false`, quindi è possibile chiamare il metodo <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsFalse%2A>.

Poiché il metodo della libreria gestisce le stringhe, è anche necessario assicurarsi che gestisca correttamente una [stringa vuota (`String.Empty`)](xref:System.String.Empty), una stringa valida senza caratteri e la cui <xref:System.String.Length> è 0 e una stringa `null` che non è stata inizializzata. Se `StartsWithUpper` viene chiamato come metodo di estensione su un'istanza di <xref:System.String>, non è possibile passare una stringa di `null`. È tuttavia possibile chiamarlo direttamente come metodo statico e passarlo a un singolo argomento <xref:System.String>.

Verranno definiti tre metodi, ognuno dei quali chiama ripetutamente un metodo di <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> per ogni elemento in una matrice di stringhe. Poiché il metodo di test ha esito negativo non appena viene trovato il primo errore, verrà chiamato un overload del metodo che consente di passare una stringa che indica il valore stringa usato nella chiamata al metodo.

Per creare i metodi di test:

1. Nella finestra del codice *UnitTest1.cs* o *UnitTest1. vb* sostituire il codice con il codice seguente:

   [!code-csharp[Test#1](~/samples/snippets/csharp/getting_started/with_visual_studio_2017/testlib1.cs)]
   [!code-vb[Test#1](~/samples/snippets/core/tutorials/vb-library-with-visual-studio/testlib.vb)]

   Il test dei caratteri maiuscoli nel metodo `TestStartsWithUpper` include la lettera maiuscola greca alfa (U + 0391) e la lettera maiuscola (U + maiuscola dell'alfabeto). Il test di caratteri minuscoli nel metodo di `TestDoesNotStartWithUpper` include la piccola lettera greca Alpha (U + 03B1) e la piccola lettera cirillico ghe minuscola (U + 0433).

1. Nella barra dei menu selezionare **file** > **Salva UnitTest1.cs come** o **file** > **Salva UnitTest1. vb con nome**. Nella finestra di dialogo **Salva file con nome** selezionare la freccia accanto al pulsante **Salva** e selezionare **Salva con codifica**.

   > [!div class="mx-imgBorder"]
   > ![finestra di dialogo Salva file con nome di Visual Studio](./media/testing-library-with-visual-studio/save-file-as-dialog.png)

1. Nella finestra di dialogo **Conferma Salva con nome** selezionare il pulsante **Sì** per salvare il file.

1. Nella finestra di dialogo **Opzioni di salvataggio avanzate** selezionare **Unicode (UTF-8 con firma digitale) - Tabella codici 65001** dall'elenco a discesa **Codifica** e selezionare **OK**.

   > [!div class="mx-imgBorder"]
   > ![finestra di dialogo Opzioni di salvataggio avanzate di Visual Studio](./media/testing-library-with-visual-studio/advanced-save-options.png)

   Se il salvataggio del codice sorgente come file con codifica UTF8 ha esito negativo, Visual Studio può salvarlo come file ASCII. In tal caso, il runtime non decodifica accuratamente i caratteri UTF8 al di fuori dell'intervallo ASCII e i risultati del test non saranno corretti.

1. Nella barra dei menu selezionare **Test** > **Esegui** > **Tutti i test**. Viene aperta la finestra **Esplora test** che illustra che i test sono stati eseguiti correttamente. I tre test sono elencati nella sezione **Test superati** e nella sezione **Riepilogo** è riportato il risultato dell'esecuzione dei test.

   > [!div class="mx-imgBorder"]
   > ![finestra Esplora test con i test superati](./media/testing-library-with-visual-studio/test-explorer-window.png)

## <a name="handle-test-failures"></a>Gestione degli errori di test

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

1. Eseguire il test selezionando **Test** > **Esegui** > **Tutti i test** dalla barra dei menu. La finestra **Esplora test** indica che due test hanno avuto esito positivo e uno esito negativo.

   > [!div class="mx-imgBorder"]
   > ![finestra Esplora test con test non superati](./media/testing-library-with-visual-studio/failed-test-window.png)

1. Selezionare il test non superato, `TestDoesNotStartWith`. Nella finestra **Esplora test** viene visualizzato il messaggio generato dal metodo Assert: "Assert.IsFalse failed. Expected for 'Error': false; actual: True". A causa dell'errore, non sono state testate tutte le stringhe della matrice dopo l'errore.

   > [!div class="mx-imgBorder"]
   > ![finestra Esplora test che mostra l'errore di asserzione false](./media/testing-library-with-visual-studio/failed-test-detail.png)

1. Annullare la modifica apportata nel passaggio 1 e rimuovere la stringa "Error". Eseguire nuovamente il test. I test verranno superati.

## <a name="test-the-release-version-of-the-library"></a>Testare la versione di rilascio della libreria

I test sono stati eseguiti con la versione di debug della libreria. Dopo che tutti i test sono stati superati e la libreria è stata testata in modo adeguato, è necessario ripetere i test con la versione di rilascio della libreria stessa. Esistono infatti alcuni fattori, ad esempio le ottimizzazioni del compilatore, in grado di generare a volte comportamenti diversi tra la versione di debug e quella di rilascio.

Per testare la versione di rilascio, seguire questa procedura:

1. Nella barra degli strumenti di Visual Studio modificare la configurazione di compilazione da **Debug** a **Rilascio**.

   > [!div class="mx-imgBorder"]
   > ![barra degli strumenti di Visual Studio con compilazione versione evidenziata](./media/testing-library-with-visual-studio/visual-studio-toolbar-release.png)

1. In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul progetto **StringLibrary** e selezionare **Compila** dal menu di scelta rapida per ricompilare la libreria.

   > [!div class="mx-imgBorder"]
   > ![menu di scelta rapida StringLibrary con comando di compilazione](./media/testing-library-with-visual-studio/build-library-context-menu.png)

1. Eseguire gli unit test selezionando **Test** > **Esegui** > **Tutti i test** dalla barra dei menu. I test hanno esito positivo.

Dopo aver completato le operazioni di test della libreria, il passaggio successivo consiste nel rendere quest'ultima disponibile ai chiamanti. È possibile aggregarla a una o più applicazioni oppure è possibile distribuirla come pacchetto NuGet. Per altre informazioni, vedere [Consuming a .NET Standard Class Library](consuming-library-with-visual-studio.md) (Utilizzo di una libreria di classi .NET Standard).

## <a name="see-also"></a>Vedere anche

- [Nozioni fondamentali sugli unit test di Visual Studio](/visualstudio/test/unit-test-basics)

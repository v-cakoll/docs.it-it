---
title: 'Procedura dettagliata: Incorporamento dei tipi da assembly gestiti in Visual Studio (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: 56ed12ba-adff-4e9c-a668-7fcba80c4795
ms.openlocfilehash: 18f22a771ab7279f177fe39d8c372a8517056890
ms.sourcegitcommit: 89fcad7e816c12eb1299128481183f01c73f2c07
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/24/2019
ms.locfileid: "63809131"
---
# <a name="walkthrough-embedding-types-from-managed-assemblies-in-visual-studio-visual-basic"></a>Procedura dettagliata: Incorporamento dei tipi da assembly gestiti in Visual Studio (Visual Basic)

Se si incorporano informazioni sul tipo da un assembly gestito con nome sicuro, è possibile effettuare un accoppiamento debole dei tipi in un'applicazione per ottenere l'indipendenza dalla versione. Ovvero, il programma può essere scritto in modo da usare tipi di più versioni di una libreria gestita senza dover essere ricompilato per ogni versione.

L'incorporamento dei tipi viene spesso usato con l'interoperabilità COM, ad esempio nel caso di un'applicazione che usa gli oggetti di automazione di Microsoft Office. L'incorporamento di informazioni sul tipo consente alla stessa build di un programma di funzionare con versioni diverse di Microsoft Office in computer diversi. Tuttavia, è anche possibile usare l'incorporamento dei tipi con una soluzione completamente gestita.

Le informazioni sul tipo possono essere incorporate da un assembly con le caratteristiche seguenti:

- L'assembly espone almeno un'interfaccia pubblica.

- Le interfacce incorporate vengono annotate con un attributo `ComImport` e un attributo `Guid` (e un GUID univoco).

- L'assembly viene annotato con l'attributo `ImportedFromTypeLib` o l'attributo `PrimaryInteropAssembly` e un attributo `Guid` a livello di assembly. (Per impostazione predefinita, i modelli di progetto Visual Basic includono un livello di assembly `Guid` attributo.)

Dopo aver specificato le interfacce pubbliche che possono essere incorporate, è possibile creare classi di runtime che implementano tali interfacce. Un programma client può quindi incorporare le informazioni sul tipo per tali interfacce in fase di progettazione facendo riferimento all'assembly che contiene le interfacce pubbliche e impostando la proprietà `Embed Interop Types` del riferimento su `True`. Ciò equivale a usare il compilatore della riga di comando e fare riferimento all'assembly usando l'opzione del compilatore `/link`. Il programma client può quindi caricare le istanze degli oggetti di runtime tipizzati come tali interfacce. Se si crea una nuova versione dell'assembly di runtime con nome sicuro, il programma client non deve essere ricompilato con l'assembly di runtime aggiornato. Il programma client continua invece a usare qualsiasi versione dell'assembly di runtime disponibile, usando le informazioni sul tipo incorporate per le interfacce pubbliche.

Poiché la funzione principale dell'incorporamento dei tipi è supportare l'incorporamento delle informazioni sui tipi dagli assembly di interoperabilità COM, le limitazioni seguenti si applicano quando si incorporano informazioni sul tipo in una soluzione completamente gestita:

- Vengono incorporati solo gli attributi specifici per l'interoperabilità COM, gli altri attributi vengono ignorati.

- Se un tipo usa parametri generici e il tipo del parametro generico è un tipo incorporato, non è possibile usare quel tipo superando un limite di assembly. Esempi di superamento di un limite di assembly sono chiamare un metodo da un altro assembly o derivare un tipo da un tipo definito in un altro assembly.

- Le costanti non vengono incorporate.

- La classe <xref:System.Collections.Generic.Dictionary%602?displayProperty=nameWithType> non supporta un tipo incorporato come chiave. È possibile implementare un proprio tipo di dizionario per supportare un tipo incorporato come chiave.

 In questa procedura dettagliata, si eseguiranno le operazioni:

- Creare un assembly con nome sicuro che ha un'interfaccia pubblica che contiene informazioni sul tipo che possono essere incorporate.

- Creare un assembly di runtime con nome sicuro che implementa tale interfaccia pubblica.

- Creare un programma client che incorpora le informazioni sul tipo dell'interfaccia pubblica e crea un'istanza della classe dall'assembly di runtime.

- Modificare e ricompilare l'assembly di runtime.

- Eseguire il programma client per verificare se la nuova versione dell'assembly di runtime viene usata senza dover ricompilare il programma client.

[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]

## <a name="creating-an-interface"></a>Creare un'interfaccia

#### <a name="to-create-the-type-equivalence-interface-project"></a>Per creare il progetto di interfaccia di equivalenza del tipo

1. In Visual Studio scegliere **Nuovo** dal menu **File** e quindi fare clic su **Progetto**.

2. Nel riquadro **Tipi di progetto** della finestra di dialogo **Nuovo progetto** verificare che sia selezionata l'opzione **Windows**. Selezionare **Libreria di classi** nel riquadro **Modelli**. Nella casella **Nome** digitare `TypeEquivalenceInterface` e quindi fare clic su **OK**. Il nuovo progetto viene creato.

3. Nelle **Esplora soluzioni**, fare doppio clic su file Class1.vb e fare clic su **rinominare**. Rinominare il file `ISampleInterface.vb` e premere INVIO. Modificando il nome del file, anche la classe verrà rinominata `ISampleInterface`. Questa classe rappresenterà l'interfaccia pubblica per la classe.

4. Fare clic con il pulsante destro del mouse sul progetto TypeEquivalenceInterface e fare clic su **Proprietà**. Fare clic sulla scheda **Compila**. Impostare il percorso di output su un percorso valido nel computer di sviluppo, ad esempio `C:\TypeEquivalenceSample`. Questo percorso verrà usato anche in un passaggio successivo di questa procedura dettagliata.

5. Durante la modifica delle proprietà del progetto scegliere la scheda **Firma**. Selezionare l opzione **Firma assembly**. Nell'elenco **Scegli un file chiave con nome sicuro** fare clic su **<Nuovo…>**. Nella casella **Nome file di chiave** digitare `key.snk`. Deselezionare la casella di controllo **Proteggi file di chiave con una password**. Fare clic su **OK**.

6. Aprire il file vb. Aggiungere il codice seguente al file della classe ISampleInterface per creare l'interfaccia ISampleInterface.

    ```vb
    Imports System.Runtime.InteropServices

    <ComImport()>
    <Guid("8DA56996-A151-4136-B474-32784559F6DF")>
    Public Interface ISampleInterface
        Sub GetUserInput()
        ReadOnly Property UserInput As String
    End Interface
    ```

7. Scegliere **Crea GUID** dal menu **Strumenti**. Nella finestra di dialogo **Crea GUID** fare clic su **Formato del Registro di sistema** e quindi fare clic su **Copia**. Fare clic su **Esci**.

8. Nell'attributo `Guid` eliminare il GUID di esempio e incollare il GUID copiato dalla finestra di dialogo **Crea GUID**. Rimuovere le parentesi graffe ({}) dal GUID copiato.

9. Scegliere **Mostra tutti i file** dal menu **Progetto**.

10. Nelle **Esplora soluzioni**, espandere il **My Project** cartella. Fare doppio clic il file AssemblyInfo. vb. Aggiungere il seguente attributo al file.

    ```vb
    <Assembly: ImportedFromTypeLib("")>
    ```

    Salvare il file.

11. Salvare il progetto.

12. Fare clic con il pulsante destro del mouse sul progetto TypeEquivalenceInterface e fare clic su **Compila**. Il file DLL della libreria di classi viene compilato e salvato nel percorso dell'output di compilazione specificato, ad esempio C:\TypeEquivalenceSample.

## <a name="creating-a-runtime-class"></a>Creare una classe di runtime

#### <a name="to-create-the-type-equivalence-runtime-project"></a>Per creare il progetto di runtime di equivalenza del tipo

1. In Visual Studio scegliere **Nuovo** dal menu **File** e quindi fare clic su **Progetto**.

2. Nel riquadro **Tipi di progetto** della finestra di dialogo **Nuovo progetto** verificare che sia selezionata l'opzione **Windows**. Selezionare **Libreria di classi** nel riquadro **Modelli**. Nella casella **Nome** digitare `TypeEquivalenceRuntime` e quindi fare clic su **OK**. Il nuovo progetto viene creato.

3. Nelle **Esplora soluzioni**, fare doppio clic su file Class1.vb e fare clic su **rinominare**. Rinominare il file `SampleClass.vb` e premere INVIO. Modificando il nome del file, anche la classe verrà rinominata `SampleClass`. Questa classe implementerà l'interfaccia `ISampleInterface`.

4. Fare clic con il pulsante destro del mouse sul progetto TypeEquivalenceRuntime e fare clic su **Proprietà**. Fare clic sulla scheda **Compila**. Impostare il percorso di output sullo stesso percorso usato nel progetto TypeEquivalenceInterface, ad esempio `C:\TypeEquivalenceSample`.

5. Durante la modifica delle proprietà del progetto scegliere la scheda **Firma**. Selezionare l opzione **Firma assembly**. Nell'elenco **Scegli un file chiave con nome sicuro** fare clic su **<Nuovo…>**. Nella casella **Nome file di chiave** digitare `key.snk`. Deselezionare la casella di controllo **Proteggi file di chiave con una password**. Fare clic su **OK**.

6. Fare clic con il pulsante destro del mouse sul progetto TypeEquivalenceRuntime e fare clic su **Aggiungi riferimento**. Fare clic sulla scheda **Sfoglia** e passare alla cartella del percorso di output. Selezionare il file TypeEquivalenceInterface.dll e fare clic su **OK**.

7. Scegliere **Mostra tutti i file** dal menu **Progetto**.

8. In **Esplora soluzioni** espandere la cartella **Riferimenti**. Selezionare il riferimento TypeEquivalenceInterface. Nella finestra Proprietà del riferimento TypeEquivalenceInterface impostare la proprietà **Versione specifica** su **False**.

9. Aggiungere il codice seguente al file della classe SampleClass per creare la classe SampleClass.

    ```vb
    Imports TypeEquivalenceInterface

    Public Class SampleClass
        Implements ISampleInterface

        Private p_UserInput As String
        Public ReadOnly Property UserInput() As String Implements ISampleInterface.UserInput
            Get
                Return p_UserInput
            End Get
        End Property

        Public Sub GetUserInput() Implements ISampleInterface.GetUserInput
            Console.WriteLine("Please enter a value:")
            p_UserInput = Console.ReadLine()
        End Sub
    End Class
    ```

10. Salvare il progetto.

11. Fare clic con il pulsante destro del mouse sul progetto TypeEquivalenceRuntime e fare clic su **Compila**. Il file DLL della libreria di classi viene compilato e salvato nel percorso dell'output di compilazione specificato, ad esempio C:\TypeEquivalenceSample.

## <a name="creating-a-client-project"></a>Creare un progetto client

#### <a name="to-create-the-type-equivalence-client-project"></a>Per creare il progetto client di equivalenza del tipo

1. In Visual Studio scegliere **Nuovo** dal menu **File** e quindi fare clic su **Progetto**.

2. Nel riquadro **Tipi di progetto** della finestra di dialogo **Nuovo progetto** verificare che sia selezionata l'opzione **Windows**. Selezionare **Applicazione console** nel riquadro **Modelli**. Nella casella **Nome** digitare `TypeEquivalenceClient` e quindi fare clic su **OK**. Il nuovo progetto viene creato.

3. Fare clic con il pulsante destro del mouse sul progetto TypeEquivalenceClient e fare clic su **Proprietà**. Fare clic sulla scheda **Compila**. Impostare il percorso di output sullo stesso percorso usato nel progetto TypeEquivalenceInterface, ad esempio `C:\TypeEquivalenceSample`.

4. Fare clic con il pulsante destro del mouse sul progetto TypeEquivalenceClient e fare clic su **Aggiungi riferimento**. Fare clic sulla scheda **Sfoglia** e passare alla cartella del percorso di output. Selezionare il file TypeEquivalenceInterface.dll (non TypeEquivalenceRuntime.dll) e fare clic su **OK**.

5. Scegliere **Mostra tutti i file** dal menu **Progetto**.

6. In **Esplora soluzioni** espandere la cartella **Riferimenti**. Selezionare il riferimento TypeEquivalenceInterface. Nella finestra Proprietà del riferimento TypeEquivalenceInterface impostare la proprietà **Incorpora tipi di interoperabilità** su **True**.

7. Aggiungere il codice seguente nel file Module1.vb per creare il programma client.

    ```vb
    Imports TypeEquivalenceInterface
    Imports System.Reflection

    Module Module1

        Sub Main()
            Dim sampleAssembly = Assembly.Load("TypeEquivalenceRuntime")
            Dim sampleClass As ISampleInterface = CType( _
                sampleAssembly.CreateInstance("TypeEquivalenceRuntime.SampleClass"), ISampleInterface)
            sampleClass.GetUserInput()
            Console.WriteLine(sampleClass.UserInput)
            Console.WriteLine(sampleAssembly.GetName().Version)
            Console.ReadLine()
        End Sub

    End Module
    ```

8. Premere CTRL+F5 per compilare ed eseguire il programma.

## <a name="modifying-the-interface"></a>Modificare l'interfaccia

#### <a name="to-modify-the-interface"></a>Per modificare l'interfaccia

1. In Visual Studio scegliere **Apri** dal menu **File** e quindi fare clic su **Progetto/Soluzione**.

2. Nella finestra di dialogo **Apri progetto** fare clic con il pulsante destro del mouse sul progetto TypeEquivalenceInterface e quindi fare clic su **Proprietà**. Fare clic sulla scheda **Applicazione** . Fare clic sul pulsante **Informazioni assembly**. Modificare i valori di **Versione assembly** e **Versione file** in `2.0.0.0`.

3. Aprire il file vb. Aggiungere la riga di codice seguente all'interfaccia ISampleInterface.

    ```vb
    Function GetDate() As Date
    ```

    Salvare il file.

4. Salvare il progetto.

5. Fare clic con il pulsante destro del mouse sul progetto TypeEquivalenceInterface e fare clic su **Compila**. Una nuova versione del file DLL della libreria di classi viene compilata e salvata nel percorso dell'output di compilazione specificato, ad esempio C:\TypeEquivalenceSample.

## <a name="modifying-the-runtime-class"></a>Modificare la classe di runtime

#### <a name="to-modify-the-runtime-class"></a>Per modificare la classe di runtime

1. In Visual Studio scegliere **Apri** dal menu **File** e quindi fare clic su **Progetto/Soluzione**.

2. Nella finestra di dialogo **Apri progetto** fare clic con il pulsante destro del mouse sul progetto TypeEquivalenceRuntime e fare clic su **Proprietà**. Fare clic sulla scheda **Applicazione** . Fare clic sul pulsante **Informazioni assembly**. Modificare i valori di **Versione assembly** e **Versione file** in `2.0.0.0`.

3. Aprire il file SampleClass. vb. Aggiungere le seguenti righe di codice alla classe SampleClass.

    ```vb
    Public Function GetDate() As DateTime Implements ISampleInterface.GetDate
        Return Now
    End Function
    ```

    Salvare il file.

4. Salvare il progetto.

5. Fare clic con il pulsante destro del mouse sul progetto TypeEquivalenceRuntime e fare clic su **Compila**. Una versione aggiornata del file DLL della libreria di classi viene compilata e salvata nel percorso dell'output di compilazione specificato in precedenza, ad esempio C:\TypeEquivalenceSample.

6. In Esplora File aprire la cartella del percorso di output, ad esempio C:\TypeEquivalenceSample. Fare doppio clic su TypeEquivalenceClient.exe per eseguire il programma. Il programma rifletterà la nuova versione dell'assembly TypeEquivalenceRuntime senza dover essere ricompilato.

## <a name="see-also"></a>Vedere anche

- [/link (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/link.md)
- [Nozioni di base sulla programmazione](../../../../visual-basic/programming-guide/concepts/index.md)
- [Programmazione con gli assembly](../../../../framework/app-domains/programming-with-assemblies.md)
- [Assembly in .NET](../../../../standard/assembly/index.md)

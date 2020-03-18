---
title: 'Procedura dettagliata: Incorporare tipi da assembly gestiti in Visual StudioWalkthrough: Embed types from managed assemblies in Visual Studio'
ms.date: 08/19/2019
ms.assetid: 55ed13c9-c5bb-4bc2-bcd8-0587eb568864
dev_langs:
- csharp
- vb
ms.openlocfilehash: f11fbedad766753ee462c5f597b823493cdaf7cf
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "75338549"
---
# <a name="walkthrough-embed-types-from-managed-assemblies-in-visual-studio"></a>Procedura dettagliata: Incorporare tipi da assembly gestiti in Visual StudioWalkthrough: Embed types from managed assemblies in Visual Studio

Se si incorporano informazioni sul tipo da un assembly gestito con nome sicuro, è possibile effettuare un accoppiamento debole dei tipi in un'applicazione per ottenere l'indipendenza dalla versione. In altre parte, il programma può essere scritto per utilizzare i tipi da qualsiasi versione di una libreria gestita senza dover essere ricompilato per ogni nuova versione.

L'incorporamento dei tipi viene spesso usato con l'interoperabilità COM, ad esempio nel caso di un'applicazione che usa gli oggetti di automazione di Microsoft Office. L'incorporamento di informazioni sul tipo consente alla stessa build di un programma di funzionare con versioni diverse di Microsoft Office in computer diversi. Tuttavia, è anche possibile usare l'incorporamento dei tipi con soluzioni completamente gestite.

Dopo aver specificato le interfacce pubbliche che possono essere incorporate, creare classi di runtime che implementano tali interfacce. Un programma client può incorporare le informazioni sul tipo per le interfacce in fase `Embed Interop Types` di progettazione `True`facendo riferimento all'assembly che contiene le interfacce pubbliche e impostando la proprietà del riferimento su . Il programma client può quindi caricare istanze degli oggetti di runtime tipizzati come tali interfacce. Equivale a utilizzare il compilatore da riga di comando e a fare riferimento all'assembly utilizzando [l'opzione del compilatore -link](../../csharp/language-reference/compiler-options/link-compiler-option.md).

Se si crea una nuova versione dell'assembly di runtime con nome sicuro, il programma client non deve essere ricompilato. Il programma client continua a utilizzare qualsiasi versione dell'assembly di runtime sia disponibile, utilizzando le informazioni sul tipo incorporato per le interfacce pubbliche.

Questa procedura dettagliata è costituita dai passaggi seguenti:

1. Creare un assembly con nome sicuro con un'interfaccia pubblica contenente informazioni sul tipo che possono essere incorporate.
1. Creare un assembly di runtime con nome sicuro che implementa l'interfaccia pubblica.
1. Creare un programma client che incorpora le informazioni sul tipo dell'interfaccia pubblica e crea un'istanza della classe dall'assembly di runtime.
1. Modificare e ricompilare l'assembly di runtime.
1. Eseguire il programma client per verificare che utilizzi la nuova versione dell'assembly di runtime senza dover essere ricompilato.

[!INCLUDE[note_settings_general](../../../includes/note-settings-general-md.md)]

## <a name="conditions-and-limitations"></a>Condizioni e limitazioni

È possibile incorporare informazioni sul tipo da un assembly nelle seguenti condizioni:

- L'assembly espone almeno un'interfaccia pubblica.
- Le interfacce incorporate sono annotate `ComImport` `Guid` con attributi e attributi con GUID univoci.
- L'assembly viene annotato con l'attributo `ImportedFromTypeLib` o l'attributo `PrimaryInteropAssembly` e un attributo `Guid` a livello di assembly. Per impostazione predefinita, i modelli di `Guid` progetto di Visual C è e Visual Basic includono un attributo a livello di assembly.

Poiché la funzione principale dell'incorporamento dei tipi consiste nel supportare gli assembly di interoperabilità COM, quando si incorporano informazioni sul tipo in una soluzione completamente gestita, si applicano le limitazioni seguenti:

- Vengono incorporati solo gli attributi specifici dell'interoperabilità COM. Gli altri attributi vengono ignorati.
- Se un tipo utilizza parametri generici e il tipo del parametro generico è un tipo incorporato, tale tipo non può essere utilizzato attraverso un limite di assembly. Esempi di attraversamento del limite di un assembly includono la chiamata di un metodo da un altro assembly o la derivazione di un tipo da un tipo definito in un altro assembly.
- Le costanti non vengono incorporate.
- La classe <xref:System.Collections.Generic.Dictionary%602?displayProperty=nameWithType> non supporta un tipo incorporato come chiave. È possibile implementare un proprio tipo di dizionario per supportare un tipo incorporato come chiave.

## <a name="create-an-interface"></a>Creare un'interfaccia

Il primo passaggio consiste nel creare l'assembly dell'interfaccia di equivalenza del tipo.

1. In Visual Studio selezionare **File** > **nuovo** > **progetto**.

1. Nella finestra di dialogo **Crea un nuovo progetto** digitare libreria di *classi* nella casella **Cerca modelli.** Selezionare il modello Libreria di classi di Visual Basic (.NET Framework) o di Visual Basic **(.NET Framework),** quindi scegliere **Avanti**.

1. Nella finestra di dialogo **Configura il nuovo progetto** , in Nome **progetto**, digitare *TypeEquivalenceInterface*, quindi selezionare **Crea**. Viene creato il nuovo progetto.

1. In **Esplora soluzioni**fare clic con il pulsante destro del mouse sul file *Class1.cs* o *Class1.vb* , scegliere **Rinomina**e rinominare il file da *Class1* a *ISampleInterface*. Rispondere **Sì** al prompt di rinominare anche la classe in `ISampleInterface`. Questa classe rappresenta l'interfaccia pubblica per la classe.

1. In **Esplora soluzioni**fare clic con il pulsante destro del mouse sul progetto **TypeEquivalenceInterface** , quindi **scegliere Proprietà**.

1. Selezionare **Compila** nel riquadro sinistro della schermata **Proprietà** e impostare il percorso di **output** su un percorso nel computer, ad esempio *C:, TypeEquivalenceSample*. In questa procedura dettagliata si utilizza lo stesso percorso.

1. Selezionare **Firma** nel riquadro sinistro della schermata **Proprietà,** quindi selezionare la casella di controllo **Firma assembly.** Nell'elenco a discesa scegliere un file di chiave con **nome sicuro**selezionare **Nuovo**.

1. Nella finestra di dialogo **Crea chiave** con nome sicuro, in Nome **file chiave**digitare *key.snk*. Deselezionare la casella di controllo **Proteggi il file di chiave con una password** e quindi selezionare **OK**.

1. Aprire il *iSampleInterface* file di classe nell'editor di codice e `ISampleInterface` sostituirne il contenuto con il codice seguente per creare l'interfaccia:

   ```csharp
   using System;
   using System.Runtime.InteropServices;

   namespace TypeEquivalenceInterface
   {
       [ComImport]
       [Guid("8DA56996-A151-4136-B474-32784559F6DF")]
       public interface ISampleInterface
       {
           void GetUserInput();
           string UserInput { get; }
       }
   }
   ```

   ```vb
   Imports System.Runtime.InteropServices

   <ComImport()>
   <Guid("8DA56996-A151-4136-B474-32784559F6DF")>
   Public Interface ISampleInterface
       Sub GetUserInput()
       ReadOnly Property UserInput As String
   End Interface
   ```

1. Scegliere **Crea GUID**dal menu **Strumenti** , quindi nella finestra di dialogo **Crea GUID** selezionare **Formato Registro di sistema**. Selezionare **Copia**, quindi **Esci**.

1. Nell'attributo `Guid` del codice sostituire il GUID di esempio con il GUID copiato e rimuovere le parentesi graffe (** **).

1. In **Esplora soluzioni**espandere la cartella **Proprietà** e selezionare il file *AssemblyInfo.cs* o *AssemblyInfo.vb.* Nell'editor di codice aggiungere il seguente attributo al file:

   ```csharp
   [assembly: ImportedFromTypeLib("")]
   ```

   ```vb
   <Assembly: ImportedFromTypeLib("")>
   ```

1. Selezionare **Salva** > **tutto** file o premere **CTRL**+**Maiusc**+**S** per salvare i file e il progetto.

1. In **Esplora soluzioni**fare clic con il pulsante destro del mouse sul progetto **TypeEquivalenceInterface** e scegliere **Compila**. Il file DLL della libreria di classi viene compilato e salvato nel percorso di output di compilazione specificato, ad esempio *C:.*

## <a name="create-a-runtime-class"></a>Creare una classe di runtimeCreate a runtime class

Successivamente, creare la classe di runtime di equivalenza del tipo.

1. In Visual Studio selezionare **File** > **nuovo** > **progetto**.

1. Nella finestra di dialogo **Crea un nuovo progetto** digitare libreria di *classi* nella casella **Cerca modelli.** Selezionare il modello Libreria di classi di Visual Basic (.NET Framework) o di Visual Basic **(.NET Framework),** quindi scegliere **Avanti**.

1. Nella finestra di dialogo **Configura il nuovo progetto** , in Nome **progetto**, digitare *TypeEquivalenceRuntime*, quindi selezionare **Crea**. Viene creato il nuovo progetto.

1. In **Esplora soluzioni**fare clic con il pulsante destro del mouse sul file *Class1.cs* o *Class1.vb* , scegliere **Rinomina**e rinominare il file da *Class1* a *SampleClass*. Rispondere **Sì** al prompt di rinominare anche la classe in `SampleClass`. La classe implementa l'interfaccia `ISampleInterface`.

1. In **Esplora soluzioni**fare clic con il pulsante destro del mouse sul progetto **TypeEquivalenceInterface** e scegliere **Proprietà**.

1. Selezionare **Compila** nel riquadro sinistro della schermata **Proprietà** e quindi impostare il **percorso** di output sullo stesso percorso utilizzato per il progetto TypeEquivalenceInterface, ad esempio *C:.*

1. Selezionare **Firma** nel riquadro sinistro della schermata **Proprietà,** quindi selezionare la casella di controllo **Firma assembly.** Nell'elenco a discesa scegliere un file di chiave con **nome sicuro**selezionare **Nuovo**.

1. Nella finestra di dialogo **Crea chiave** con nome sicuro, in Nome **file chiave**digitare *key.snk*. Deselezionare la casella di controllo **Proteggi il file di chiave con una password** e quindi selezionare **OK**.

1. In **Esplora soluzioni**fare clic con il pulsante destro del mouse sul progetto **TypeEquivalenceRuntime** e scegliere **Aggiungi** > **riferimento**.

1. Nella finestra di dialogo **Gestione riferimenti,** selezionare **Sfoglia** e individuare la cartella del percorso di output. Selezionare il file *TypeEquivalenceInterface.dll* , selezionare **Aggiungi**, quindi **OK**.

1. In **Esplora soluzioni**espandere la cartella **Riferimenti** e selezionare il riferimento **TypeEquivalenceInterface** . Nel riquadro **Proprietà** impostare **Versione specifica su** **False,** se non lo è già.

1. Aprire il file di classe *SampleClass* nell'editor di codice e `SampleClass` sostituirne il contenuto con il codice seguente per creare la classe:

   ```csharp
   using System;
   using TypeEquivalenceInterface;

   namespace TypeEquivalenceRuntime
   {
       public class SampleClass : ISampleInterface
       {
           private string p_UserInput;
           public string UserInput { get { return p_UserInput; } }

           public void GetUserInput()
           {
               Console.WriteLine("Please enter a value:");
               p_UserInput = Console.ReadLine();
           }
       }
   }
   ```

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

1. Selezionare **Salva** > **tutto** file o premere **CTRL**+**Maiusc**+**S** per salvare i file e il progetto.

1. In **Esplora soluzioni**fare clic con il pulsante destro del mouse sul progetto **TypeEquivalenceRuntime** e **scegliere Compila**. Il file DLL della libreria di classi viene compilato e salvato nel percorso di output di compilazione specificato.

## <a name="create-a-client-project"></a>Creare un progetto clientCreate a client project

Infine, creare un programma client di equivalenza del tipo che fa riferimento all'assembly dell'interfaccia.

1. In Visual Studio selezionare **File** > **nuovo** > **progetto**.

1. Nella finestra di dialogo **Crea un nuovo progetto** digitare *console* nella casella **Cerca modelli.** Selezionare dall'elenco il modello di app console di Visual Basic (.NET Framework) o di Visual Basic App **(.NET Framework),** quindi scegliere **Avanti**.

1. Nella finestra di dialogo **Configura il nuovo progetto** , in Nome **progetto**, digitare *TypeEquivalenceClient*, quindi selezionare **Crea**. Viene creato il nuovo progetto.

1. In **Esplora soluzioni**fare clic con il pulsante destro del mouse sul progetto **TypeEquivalenceClient** e scegliere **Proprietà**.

1. Selezionare **Compila** nel riquadro sinistro della schermata **Proprietà** e quindi impostare il **percorso** di output sullo stesso percorso utilizzato per il progetto TypeEquivalenceInterface, ad esempio *C:.*

1. In **Esplora soluzioni**fare clic con il pulsante destro del mouse sul progetto **TypeEquivalenceClient** e scegliere **Aggiungi** > **riferimento**.

1. Nella finestra di dialogo **Gestione riferimenti,** se il file **TypeEquivalenceInterface.dll** è già presente nell'elenco, selezionarlo. In caso contrario, selezionare **Sfoglia**, individuare la cartella del percorso di output , selezionare il file *TypeEquivalenceInterface.dll* (non *TypeEquivalenceRuntime.dll*) e scegliere **Aggiungi**. Selezionare **OK**.

1. In **Esplora soluzioni**espandere la cartella **Riferimenti** e selezionare il riferimento **TypeEquivalenceInterface** . Nel riquadro **Proprietà** impostare **Incorpora tipi di interoperabilità su** **True**.

1. Aprire il *file Program.cs* o *Module1.vb* nell'editor di codice e sostituirne il contenuto con il codice seguente per creare il programma client:

   ```csharp
   using System;
   using System.Reflection;
   using TypeEquivalenceInterface;

   namespace TypeEquivalenceClient
   {
       class Program
       {
           static void Main(string[] args)
           {
               Assembly sampleAssembly = Assembly.Load("TypeEquivalenceRuntime");
               ISampleInterface sampleClass =
                   (ISampleInterface)sampleAssembly.CreateInstance("TypeEquivalenceRuntime.SampleClass");
               sampleClass.GetUserInput();
               Console.WriteLine(sampleClass.UserInput);
               Console.WriteLine(sampleAssembly.GetName().Version.ToString());
               Console.ReadLine();
           }
       }
   }
   ```

   ```vb
   Imports System.Reflection
   Imports TypeEquivalenceInterface

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

1. Selezionare **Salva** > **tutto** file o premere **CTRL**+**Maiusc**+**S** per salvare i file e il progetto.

1. Premere **Ctrl**+**F5** per compilare ed eseguire il programma. Si noti che l'output della console restituisce l'assembly versione **1.0.0.0**.

## <a name="modify-the-interface"></a>Modificare l'interfaccia

A questo punto, modificare l'assembly dell'interfaccia e modificarne la versione.

1. In Visual Studio selezionare**Progetto/Soluzione****apertura** >  **file** > e aprire il progetto **TypeEquivalenceInterface.**

1. In **Esplora soluzioni**fare clic con il pulsante destro del mouse sul progetto **TypeEquivalenceInterface** e scegliere **Proprietà**.

1. Selezionare **Applicazione** nel riquadro sinistro della schermata **Proprietà,** quindi selezionare **Informazioni assembly**.

1. Nella finestra di dialogo **Informazioni assembly** modificare i valori **Versione assembly** e Versione file **in** *2.0.0.0*, quindi scegliere **OK**.

1. Aprire il *file SampleInterface.cs* o *SampleInterface.vb* e aggiungere `ISampleInterface` la seguente riga di codice all'interfaccia:

   ```csharp
   DateTime GetDate();
   ```

   ```vb
   Function GetDate() As Date
   ```

1. Selezionare **Salva** > **tutto** file o premere **CTRL**+**Maiusc**+**S** per salvare i file e il progetto.

1. In **Esplora soluzioni**fare clic con il pulsante destro del mouse sul progetto **TypeEquivalenceInterface** e scegliere **Compila**. Una nuova versione del file DLL della libreria di classi viene compilata e salvata nel percorso di output di compilazione.

## <a name="modify-the-runtime-class"></a>Modificare la classe di runtime

Modificare anche la classe di runtime e aggiornarne la versione.

1. In Visual Studio selezionare**Open** > **Progetto/Soluzione** **apertura file** > e aprire il progetto **TypeEquivalenceRuntime.**

1. In **Esplora soluzioni**fare clic con il pulsante destro del mouse sul progetto **TypeEquivalenceRuntime** e scegliere **Proprietà**.

1. Selezionare **Applicazione** nel riquadro sinistro della schermata **Proprietà,** quindi selezionare **Informazioni assembly**.

1. Nella finestra di dialogo **Informazioni assembly** modificare i valori **Versione assembly** e Versione file **in** *2.0.0.0*, quindi scegliere **OK**.

1. Aprire il *file SampleClass.cs* o *SampleClass.vb* e `SampleClass` aggiungere il codice seguente alla classe:

   ```csharp
    public DateTime GetDate()
    {
        return DateTime.Now;
    }
   ```

   ```vb
   Public Function GetDate() As DateTime Implements ISampleInterface.GetDate
       Return Now
   End Function
   ```

1. Selezionare **Salva** > **tutto** file o premere **CTRL**+**Maiusc**+**S** per salvare i file e il progetto.

1. In **Esplora soluzioni**fare clic con il pulsante destro del mouse sul progetto **TypeEquivalenceRuntime** e **scegliere Compila**. Una nuova versione del file DLL della libreria di classi viene compilata e salvata nel percorso di output di compilazione.

## <a name="run-the-updated-client-program"></a>Eseguire il programma client aggiornato

Passare al percorso della cartella dell'output di compilazione ed eseguire *TypeEquivalenceClient.exe*. Si noti che l'output della `TypeEquivalenceRuntime` console ora riflette la nuova versione dell'assembly, *2.0.0.0*, senza che il programma venga ricompilato.

## <a name="see-also"></a>Vedere anche

- [-link (opzioni del compilatore C#)](../../csharp/language-reference/compiler-options/link-compiler-option.md)
- [-link (Visual Basic)](../../visual-basic/reference/command-line-compiler/link.md)
- [Guida alla programmazione in C](../../csharp/programming-guide/index.md)
- [Concetti di programmazione (Visual Basic)Programming concepts (Visual Basic)](../../visual-basic/programming-guide/concepts/index.md)
- [Assembly in .NET](index.md)

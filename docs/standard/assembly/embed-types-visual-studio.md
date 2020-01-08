---
title: 'Procedura dettagliata: incorporare i tipi da assembly gestiti in Visual Studio'
ms.date: 08/19/2019
ms.assetid: 55ed13c9-c5bb-4bc2-bcd8-0587eb568864
dev_langs:
- csharp
- vb
ms.openlocfilehash: f11fbedad766753ee462c5f597b823493cdaf7cf
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75338549"
---
# <a name="walkthrough-embed-types-from-managed-assemblies-in-visual-studio"></a>Procedura dettagliata: incorporare i tipi da assembly gestiti in Visual Studio

Se si incorporano informazioni sul tipo da un assembly gestito con nome sicuro, è possibile effettuare un accoppiamento debole dei tipi in un'applicazione per ottenere l'indipendenza dalla versione. Ovvero, il programma può essere scritto in modo da usare i tipi di qualsiasi versione di una libreria gestita senza dover essere ricompilati per ogni nuova versione.

L'incorporamento dei tipi viene spesso usato con l'interoperabilità COM, ad esempio nel caso di un'applicazione che usa gli oggetti di automazione di Microsoft Office. L'incorporamento di informazioni sul tipo consente alla stessa build di un programma di funzionare con versioni diverse di Microsoft Office in computer diversi. Tuttavia, è anche possibile usare l'incorporamento dei tipi con soluzioni completamente gestite.

Dopo aver specificato le interfacce pubbliche che possono essere incorporate, è possibile creare classi di runtime che implementano tali interfacce. Un programma client può incorporare le informazioni sul tipo per le interfacce in fase di progettazione facendo riferimento all'assembly che contiene le interfacce pubbliche e impostando la proprietà `Embed Interop Types` del riferimento su `True`. Il programma client può quindi caricare le istanze degli oggetti di runtime digitati come tali interfacce. Equivale a usare il compilatore della riga di comando e a fare riferimento all'assembly usando l' [opzione del compilatore-link](../../csharp/language-reference/compiler-options/link-compiler-option.md).

Se si crea una nuova versione dell'assembly di runtime con nome sicuro, non è necessario ricompilare il programma client. Il programma client continua a usare la versione dell'assembly di runtime disponibile, usando le informazioni sul tipo incorporate per le interfacce pubbliche.

Questa procedura dettagliata è costituita dai passaggi seguenti:

1. Creare un assembly con nome sicuro con un'interfaccia pubblica che contiene informazioni sul tipo che possono essere incorporate.
1. Creare un assembly di runtime con nome sicuro che implementi l'interfaccia pubblica.
1. Creare un programma client che incorpora le informazioni sul tipo dell'interfaccia pubblica e crea un'istanza della classe dall'assembly di runtime.
1. Modificare e ricompilare l'assembly di runtime.
1. Eseguire il programma client per verificare che usi la nuova versione dell'assembly di runtime senza dover essere ricompilata.

[!INCLUDE[note_settings_general](../../../includes/note-settings-general-md.md)]

## <a name="conditions-and-limitations"></a>Condizioni e limitazioni

È possibile incorporare le informazioni sul tipo da un assembly nelle condizioni seguenti:

- L'assembly espone almeno un'interfaccia pubblica.
- Le interfacce incorporate sono annotate con `ComImport` attributi e `Guid` attributi con GUID univoci.
- L'assembly viene annotato con l'attributo `ImportedFromTypeLib` o l'attributo `PrimaryInteropAssembly` e un attributo `Guid` a livello di assembly. Per impostazione C# predefinita, i modelli di progetto Visual e Visual Basic includono un attributo `Guid` a livello di assembly.

Poiché la funzione primaria dell'incorporamento del tipo prevede il supporto di assembly di interoperabilità COM, quando si incorporano le informazioni sul tipo in una soluzione completamente gestita, si applicano le limitazioni seguenti:

- Sono incorporati solo gli attributi specifici dell'interoperabilità COM. Altri attributi vengono ignorati.
- Se un tipo USA parametri generici e il tipo del parametro generico è un tipo incorporato, tale tipo non può essere usato in un limite di assembly. Esempi di superamento di un limite di assembly includono la chiamata a un metodo da un altro assembly o la derivazione di un tipo da un tipo definito in un altro assembly.
- Le costanti non vengono incorporate.
- La classe <xref:System.Collections.Generic.Dictionary%602?displayProperty=nameWithType> non supporta un tipo incorporato come chiave. È possibile implementare un proprio tipo di dizionario per supportare un tipo incorporato come chiave.

## <a name="create-an-interface"></a>Creare un'interfaccia

Il primo passaggio consiste nel creare l'assembly dell'interfaccia di equivalenza del tipo.

1. In Visual Studio selezionare **File** > **Nuovo** > **Progetto**.

1. Nella finestra di dialogo **Crea un nuovo progetto** Digitare *libreria di classi* nella casella **Cerca modelli** . Selezionare il C# modello o Visual Basic **libreria di classi (.NET Framework)** nell'elenco e quindi fare clic su **Avanti**.

1. Nella finestra di dialogo **Configura nuovo progetto** , in **nome progetto**, digitare *TypeEquivalenceInterface*e quindi selezionare **Crea**. Il nuovo progetto viene creato.

1. In **Esplora soluzioni**fare clic con il pulsante destro del mouse sul file *Class1.cs* o *Class1. vb* , scegliere **Rinomina**e rinominare il file da *Class1* a *ISampleInterface*. Rispondere **Sì** al prompt per rinominare anche la classe in `ISampleInterface`. Questa classe rappresenta l'interfaccia pubblica per la classe.

1. In **Esplora soluzioni**fare clic con il pulsante destro del mouse sul progetto **TypeEquivalenceInterface** , quindi scegliere **proprietà**.

1. Selezionare **Compila** nel riquadro sinistro della schermata **Proprietà** e impostare il **percorso di output** su un percorso nel computer, ad esempio *C:\TypeEquivalenceSample*. Usare la stessa posizione in questa procedura dettagliata.

1. Selezionare **Signing (firma** ) nel riquadro a sinistra della schermata **Proprietà** , quindi selezionare la casella di controllo **Firma assembly** . Nell'elenco a discesa per **scegliere un file di chiave con nome sicuro**selezionare **nuovo**.

1. Nella finestra di dialogo **Crea chiave con nome sicuro** , in **nome file di chiave**, digitare *Key. snk*. Deselezionare la casella **di controllo Proteggi file di chiave con una password** e quindi fare clic su **OK**.

1. Aprire il file di classe *ISampleInterface* nell'editor di codice e sostituirne il contenuto con il codice seguente per creare l'interfaccia `ISampleInterface`:

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

1. Scegliere **Crea GUID**dal menu **strumenti** , quindi nella finestra di dialogo **Crea GUID** selezionare **formato registro di sistema**. Selezionare **copia**, quindi fare clic su **Esci**.

1. Nell'attributo `Guid` del codice sostituire il GUID di esempio con il GUID copiato e rimuovere le parentesi graffe ( **{}** ).

1. In **Esplora soluzioni**espandere la cartella **Proprietà** e selezionare il file *AssemblyInfo.cs* o *AssemblyInfo. vb* . Nell'editor di codice aggiungere l'attributo seguente al file:

   ```csharp
   [assembly: ImportedFromTypeLib("")]
   ```

   ```vb
   <Assembly: ImportedFromTypeLib("")>
   ```

1. Selezionare **file** > **Salva tutto** oppure premere **CTRL**+**MAIUSC**+**S** per salvare i file e il progetto.

1. In **Esplora soluzioni**fare clic con il pulsante destro del mouse sul progetto **TypeEquivalenceInterface** e selezionare **Compila**. Il file DLL della libreria di classi viene compilato e salvato nel percorso dell'output di compilazione specificato, ad esempio *C:\TypeEquivalenceSample*.

## <a name="create-a-runtime-class"></a>Creare una classe di runtime

Successivamente, creare la classe runtime di equivalenza del tipo.

1. In Visual Studio selezionare **File** > **Nuovo** > **Progetto**.

1. Nella finestra di dialogo **Crea un nuovo progetto** Digitare *libreria di classi* nella casella **Cerca modelli** . Selezionare il C# modello o Visual Basic **libreria di classi (.NET Framework)** nell'elenco e quindi fare clic su **Avanti**.

1. Nella finestra di dialogo **Configura nuovo progetto** , in **nome progetto**, digitare *TypeEquivalenceRuntime*e quindi selezionare **Crea**. Il nuovo progetto viene creato.

1. In **Esplora soluzioni**fare clic con il pulsante destro del mouse sul file *Class1.cs* o *Class1. vb* , scegliere **Rinomina**e rinominare il file da *Class1* a *SampleClass*. Rispondere **Sì** al prompt per rinominare anche la classe in `SampleClass`. Questa classe implementa l'interfaccia `ISampleInterface` .

1. In **Esplora soluzioni**fare clic con il pulsante destro del mouse sul progetto **TypeEquivalenceInterface** e scegliere **proprietà**.

1. Selezionare **Compila** nel riquadro sinistro della schermata **Proprietà** , quindi impostare il **percorso di output** sullo stesso percorso usato per il progetto TypeEquivalenceInterface, ad esempio *C:\TypeEquivalenceSample*.

1. Selezionare **Signing (firma** ) nel riquadro a sinistra della schermata **Proprietà** , quindi selezionare la casella di controllo **Firma assembly** . Nell'elenco a discesa per **scegliere un file di chiave con nome sicuro**selezionare **nuovo**.

1. Nella finestra di dialogo **Crea chiave con nome sicuro** , in **nome file di chiave**, digitare *Key. snk*. Deselezionare la casella **di controllo Proteggi file di chiave con una password** e quindi fare clic su **OK**.

1. In **Esplora soluzioni**fare clic con il pulsante destro del mouse sul progetto **TypeEquivalenceRuntime** e scegliere **Aggiungi** > **riferimento**.

1. Nella finestra di dialogo **Gestione riferimenti** selezionare **Sfoglia** e passare alla cartella percorso di output. Selezionare il file *TypeEquivalenceInterface. dll* , selezionare **Aggiungi**e quindi fare clic su **OK**.

1. In **Esplora soluzioni**espandere la cartella **riferimenti** e selezionare il riferimento **TypeEquivalenceInterface** . Nel riquadro **Proprietà** impostare **versione specifica** su **false** se non è già presente.

1. Aprire il file di classe *SampleClass* nell'editor di codice e sostituirne il contenuto con il codice seguente per creare la classe `SampleClass`:

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

1. Selezionare **file** > **Salva tutto** oppure premere **CTRL**+**MAIUSC**+**S** per salvare i file e il progetto.

1. In **Esplora soluzioni**fare clic con il pulsante destro del mouse sul progetto **TypeEquivalenceRuntime** e selezionare **Compila**. Il file DLL della libreria di classi viene compilato e salvato nel percorso dell'output di compilazione specificato.

## <a name="create-a-client-project"></a>Creazione di un progetto client

Infine, creare un programma client di equivalenza del tipo che fa riferimento all'assembly dell'interfaccia.

1. In Visual Studio selezionare **File** > **Nuovo** > **Progetto**.

1. Nella finestra di dialogo **Crea un nuovo progetto** Digitare *console* nella casella **Cerca modelli** . Selezionare il C# modello o Visual Basic **App Console (.NET Framework)** nell'elenco e quindi fare clic su **Avanti**.

1. Nella finestra di dialogo **Configura nuovo progetto** , in **nome progetto**, digitare *TypeEquivalenceClient*e quindi selezionare **Crea**. Il nuovo progetto viene creato.

1. In **Esplora soluzioni**fare clic con il pulsante destro del mouse sul progetto **TypeEquivalenceClient** e scegliere **proprietà**.

1. Selezionare **Compila** nel riquadro sinistro della schermata **Proprietà** , quindi impostare il **percorso di output** sullo stesso percorso usato per il progetto TypeEquivalenceInterface, ad esempio *C:\TypeEquivalenceSample*.

1. In **Esplora soluzioni**fare clic con il pulsante destro del mouse sul progetto **TypeEquivalenceClient** e scegliere **Aggiungi** > **riferimento**.

1. Se il file **TypeEquivalenceInterface. dll** è già elencato nella finestra di dialogo **Gestione riferimenti** , selezionarlo. In caso contrario, selezionare **Sfoglia**, passare alla cartella percorso output, selezionare il file *TypeEquivalenceInterface. dll* (non *TypeEquivalenceRuntime. dll*) e selezionare **Aggiungi**. Scegliere **OK**.

1. In **Esplora soluzioni**espandere la cartella **riferimenti** e selezionare il riferimento **TypeEquivalenceInterface** . Nel riquadro **Proprietà** impostare **Incorpora tipi di interoperabilità** su **true**.

1. Aprire il file *Program.cs* o *Module1. vb* nell'editor di codice e sostituirne il contenuto con il codice seguente per creare il programma client:

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

1. Selezionare **file** > **Salva tutto** oppure premere **CTRL**+**MAIUSC**+**S** per salvare i file e il progetto.

1. Premere **Ctrl**+**F5** per compilare ed eseguire il programma. Si noti che l'output della console restituisce l'assembly versione **1.0.0.0**.

## <a name="modify-the-interface"></a>Modificare l'interfaccia

Modificare ora l'assembly dell'interfaccia e modificarne la versione.

1. In Visual Studio selezionare **File** > **aprire** > **progetto/soluzione**e aprire il progetto **TypeEquivalenceInterface** .

1. In **Esplora soluzioni**fare clic con il pulsante destro del mouse sul progetto **TypeEquivalenceInterface** e scegliere **proprietà**.

1. Selezionare **applicazione** nel riquadro sinistro della schermata **Proprietà** , quindi selezionare **informazioni assembly**.

1. Nella finestra di dialogo **informazioni assembly** modificare i valori versione **assembly** e **versione file** in *2.0.0.0*, quindi fare clic su **OK**.

1. Aprire il file *SampleInterface.cs* o *SampleInterface. vb* e aggiungere la riga di codice seguente all'interfaccia `ISampleInterface`:

   ```csharp
   DateTime GetDate();
   ```

   ```vb
   Function GetDate() As Date
   ```

1. Selezionare **file** > **Salva tutto** oppure premere **CTRL**+**MAIUSC**+**S** per salvare i file e il progetto.

1. In **Esplora soluzioni**fare clic con il pulsante destro del mouse sul progetto **TypeEquivalenceInterface** e selezionare **Compila**. Una nuova versione del file DLL della libreria di classi viene compilata e salvata nel percorso dell'output di compilazione.

## <a name="modify-the-runtime-class"></a>Modificare la classe di runtime

Modificare anche la classe runtime e aggiornarne la versione.

1. In Visual Studio selezionare **File** > **aprire** > **progetto/soluzione**e aprire il progetto **TypeEquivalenceRuntime** .

1. In **Esplora soluzioni**fare clic con il pulsante destro del mouse sul progetto **TypeEquivalenceRuntime** e scegliere **proprietà**.

1. Selezionare **applicazione** nel riquadro sinistro della schermata **Proprietà** , quindi selezionare **informazioni assembly**.

1. Nella finestra di dialogo **informazioni assembly** modificare i valori versione **assembly** e **versione file** in *2.0.0.0*, quindi fare clic su **OK**.

1. Aprire il file *SampleClass.cs* o *SampleClass. vb* e aggiungere il codice seguente alla classe `SampleClass`:

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

1. Selezionare **file** > **Salva tutto** oppure premere **CTRL**+**MAIUSC**+**S** per salvare i file e il progetto.

1. In **Esplora soluzioni**fare clic con il pulsante destro del mouse sul progetto **TypeEquivalenceRuntime** e selezionare **Compila**. Una nuova versione del file DLL della libreria di classi viene compilata e salvata nel percorso dell'output di compilazione.

## <a name="run-the-updated-client-program"></a>Eseguire il programma client aggiornato

Passare al percorso della cartella di output di compilazione ed eseguire *TypeEquivalenceClient. exe*. Si noti che l'output della console ora riflette la nuova versione dell'assembly `TypeEquivalenceRuntime`, *2.0.0.0*, senza il programma da ricompilare.

## <a name="see-also"></a>Vedere anche

- [-link (opzioni del compilatore C#)](../../csharp/language-reference/compiler-options/link-compiler-option.md)
- [-collegamento (Visual Basic)](../../visual-basic/reference/command-line-compiler/link.md)
- [Guida per programmatori C#](../../csharp/programming-guide/index.md)
- [Concetti di programmazione (Visual Basic)](../../visual-basic/programming-guide/concepts/index.md)
- [Assembly in .NET](index.md)

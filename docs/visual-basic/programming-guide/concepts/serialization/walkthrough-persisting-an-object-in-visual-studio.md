---
title: Persistenza di un oggetto in Visual Studio
ms.date: 07/20/2015
ms.assetid: f1d0b562-e349-4dce-ab5f-c05108467030
ms.openlocfilehash: e4eaf87c99ea1577d7f3ca40e628c00cc2700511
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84413129"
---
# <a name="walkthrough-persisting-an-object-in-visual-studio-visual-basic"></a><span data-ttu-id="f1327-102">Procedura dettagliata: Persistenza di un oggetto in Visual Studio (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f1327-102">Walkthrough: Persisting an Object in Visual Studio (Visual Basic)</span></span>
<span data-ttu-id="f1327-103">Sebbene sia possibile impostare le proprietà di un oggetto sui valori predefiniti in fase di progettazione, tutti i valori immessi in fase di esecuzione vengono persi quando l'oggetto viene eliminato.</span><span class="sxs-lookup"><span data-stu-id="f1327-103">Although you can set an object's properties to default values at design time, any values entered at run time are lost when the object is destroyed.</span></span> <span data-ttu-id="f1327-104">È possibile usare la serializzazione per rendere persistenti i dati di un oggetto tra le istanze, consentendo di archiviare i valori e di recuperarli alla successiva creazione di un'istanza dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="f1327-104">You can use serialization to persist an object's data between instances, which enables you to store values and retrieve them the next time that the object is instantiated.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f1327-105">In Visual Basic, per archiviare dati semplici, ad esempio un nome o numero, è possibile usare l'oggetto `My.Settings`.</span><span class="sxs-lookup"><span data-stu-id="f1327-105">In Visual Basic, to store simple data, such as a name or number, you can use the `My.Settings` object.</span></span> <span data-ttu-id="f1327-106">Per altre informazioni, vedere [Oggetto My.Settings](../../../language-reference/objects/my-settings-object.md).</span><span class="sxs-lookup"><span data-stu-id="f1327-106">For more information, see [My.Settings Object](../../../language-reference/objects/my-settings-object.md).</span></span>  
  
 <span data-ttu-id="f1327-107">In questa procedura verrà creato un oggetto `Loan` semplice i cui dati verranno resi persistenti in un file.</span><span class="sxs-lookup"><span data-stu-id="f1327-107">In this walkthrough, you will create a simple `Loan` object and persist its data to a file.</span></span> <span data-ttu-id="f1327-108">I dati verranno quindi recuperati dal file quando si ricrea l'oggetto.</span><span class="sxs-lookup"><span data-stu-id="f1327-108">You will then retrieve the data from the file when you re-create the object.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="f1327-109">Questo esempio crea un nuovo file, se il file non esiste.</span><span class="sxs-lookup"><span data-stu-id="f1327-109">This example creates a new file, if the file does not already exist.</span></span> <span data-ttu-id="f1327-110">Se un'applicazione deve creare un file, per tale applicazione deve essere disponibile l'autorizzazione `Create` per la cartella.</span><span class="sxs-lookup"><span data-stu-id="f1327-110">If an application must create a file, that application must `Create` permission for the folder.</span></span> <span data-ttu-id="f1327-111">Le autorizzazioni vengono impostate usando gli elenchi di controllo di accesso.</span><span class="sxs-lookup"><span data-stu-id="f1327-111">Permissions are set by using access control lists.</span></span> <span data-ttu-id="f1327-112">Se il file esiste già, per l'applicazione è necessaria solo l'autorizzazione `Write`, di livello inferiore.</span><span class="sxs-lookup"><span data-stu-id="f1327-112">If the file already exists, the application needs only `Write` permission, a lesser permission.</span></span> <span data-ttu-id="f1327-113">Se possibile, è più sicuro creare il file durante la distribuzione e concedere solo autorizzazioni `Read` per un singolo file, anziché autorizzazioni Create per una cartella.</span><span class="sxs-lookup"><span data-stu-id="f1327-113">Where possible, it is more secure to create the file during deployment, and only grant `Read` permissions to a single file (instead of Create permissions for a folder).</span></span> <span data-ttu-id="f1327-114">Inoltre, è più sicuro scrivere dati nelle cartelle utente anziché nella cartella radice o nella cartella dei file di programma.</span><span class="sxs-lookup"><span data-stu-id="f1327-114">Also, it is more secure to write data to user folders than to the root folder or the Program Files folder.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="f1327-115">In questo esempio i dati vengono archiviati in un file binario.</span><span class="sxs-lookup"><span data-stu-id="f1327-115">This example stores data in a binary.</span></span> <span data-ttu-id="f1327-116">Non usare questi formati per i dati riservati, ad esempio password o informazioni sulla carta di credito.</span><span class="sxs-lookup"><span data-stu-id="f1327-116">These formats should not be used for sensitive data, such as passwords or credit-card information.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f1327-117">È possibile che le finestre di dialogo e i comandi di menu visualizzati varino da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma.</span><span class="sxs-lookup"><span data-stu-id="f1327-117">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="f1327-118">Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** .</span><span class="sxs-lookup"><span data-stu-id="f1327-118">To change your settings, click **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="f1327-119">Per altre informazioni, vedere [personalizzare l'IDE di Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="f1327-119">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
## <a name="creating-the-loan-object"></a><span data-ttu-id="f1327-120">Creare l'oggetto Loan</span><span class="sxs-lookup"><span data-stu-id="f1327-120">Creating the Loan Object</span></span>  
 <span data-ttu-id="f1327-121">Il primo passaggio consiste nel creare una classe `Loan` e un'applicazione di test che usa la classe.</span><span class="sxs-lookup"><span data-stu-id="f1327-121">The first step is to create a `Loan` class and a test application that uses the class.</span></span>  
  
### <a name="to-create-the-loan-class"></a><span data-ttu-id="f1327-122">Per creare la classe Loan</span><span class="sxs-lookup"><span data-stu-id="f1327-122">To create the Loan class</span></span>  
  
1. <span data-ttu-id="f1327-123">Creare un nuovo progetto di libreria di classi denominato "LoanClass".</span><span class="sxs-lookup"><span data-stu-id="f1327-123">Create a new Class Library project and name it "LoanClass".</span></span> <span data-ttu-id="f1327-124">Per altre informazioni, vedere [Creazione di soluzioni e progetti](https://docs.microsoft.com/visualstudio/ide/creating-solutions-and-projects).</span><span class="sxs-lookup"><span data-stu-id="f1327-124">For more information, see [Creating Solutions and Projects](https://docs.microsoft.com/visualstudio/ide/creating-solutions-and-projects).</span></span>  
  
2. <span data-ttu-id="f1327-125">In **Esplora soluzioni** aprire il menu di scelta rapida per il file Class1 e scegliere **Rinomina**.</span><span class="sxs-lookup"><span data-stu-id="f1327-125">In **Solution Explorer**, open the shortcut menu for the Class1 file and choose **Rename**.</span></span> <span data-ttu-id="f1327-126">Rinominare il file `Loan` e premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="f1327-126">Rename the file to `Loan` and press ENTER.</span></span> <span data-ttu-id="f1327-127">Modificando il nome del file, anche la classe verrà rinominata `Loan`.</span><span class="sxs-lookup"><span data-stu-id="f1327-127">Renaming the file will also rename the class to `Loan`.</span></span>  
  
3. <span data-ttu-id="f1327-128">Aggiungere i seguenti membri pubblici alla classe:</span><span class="sxs-lookup"><span data-stu-id="f1327-128">Add the following public members to the class:</span></span>  
  
    ```vb  
    Public Class Loan  
        Implements System.ComponentModel.INotifyPropertyChanged  
  
        Public Property LoanAmount As Double  
        Public Property InterestRate As Double  
        Public Property Term As Integer  
  
        Private p_Customer As String  
        Public Property Customer As String  
            Get  
                Return p_Customer  
            End Get  
            Set(ByVal value As String)  
                p_Customer = value  
                RaiseEvent PropertyChanged(Me,  
                  New System.ComponentModel.PropertyChangedEventArgs("Customer"))  
            End Set  
        End Property  
  
        Event PropertyChanged As System.ComponentModel.PropertyChangedEventHandler _  
          Implements System.ComponentModel.INotifyPropertyChanged.PropertyChanged  
  
        Public Sub New(ByVal loanAmount As Double,  
                       ByVal interestRate As Double,  
                       ByVal term As Integer,  
                       ByVal customer As String)  
  
            Me.LoanAmount = loanAmount  
            Me.InterestRate = interestRate  
            Me.Term = term  
            p_Customer = customer  
        End Sub  
    End Class  
    ```  
  
 <span data-ttu-id="f1327-129">Sarà anche necessario creare un'applicazione semplice che usa la classe `Loan`.</span><span class="sxs-lookup"><span data-stu-id="f1327-129">You will also have to create a simple application that uses the `Loan` class.</span></span>  
  
### <a name="to-create-a-test-application"></a><span data-ttu-id="f1327-130">Per creare un'applicazione di test</span><span class="sxs-lookup"><span data-stu-id="f1327-130">To create a test application</span></span>  
  
1. <span data-ttu-id="f1327-131">Per aggiungere un progetto di Windows Form Application alla soluzione, nel menu **File** scegliere **Aggiungi**, **Nuovo progetto**.</span><span class="sxs-lookup"><span data-stu-id="f1327-131">To add a Windows Forms Application project to your solution, on the **File** menu, choose **Add**,**New Project**.</span></span>  
  
2. <span data-ttu-id="f1327-132">Scegliere **Windows Forms Application** nella finestra di dialogo **Aggiungi nuovo progetto**, quindi immettere `LoanApp` come nome del progetto e quindi fare clic su **OK** per chiudere la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="f1327-132">In the **Add New Project** dialog box, choose **Windows Forms Application**, and enter `LoanApp` as the name of the project, and then click **OK** to close the dialog box.</span></span>  
  
3. <span data-ttu-id="f1327-133">Scegliere il progetto LoanApp in **Esplora soluzioni**.</span><span class="sxs-lookup"><span data-stu-id="f1327-133">In **Solution Explorer**, choose the LoanApp project.</span></span>  
  
4. <span data-ttu-id="f1327-134">Nel menu **Progetto** scegliere **Imposta come progetto di avvio**.</span><span class="sxs-lookup"><span data-stu-id="f1327-134">On the **Project** menu, choose **Set as StartUp Project**.</span></span>  
  
5. <span data-ttu-id="f1327-135">Scegliere **Aggiungi riferimento**dal menu **progetto** .</span><span class="sxs-lookup"><span data-stu-id="f1327-135">On the **Project** menu, choose **Add Reference**.</span></span>  
  
6. <span data-ttu-id="f1327-136">Nella finestra di dialogo **Aggiungi riferimento** scegliere la scheda **Progetti** e quindi il progetto LoanClass.</span><span class="sxs-lookup"><span data-stu-id="f1327-136">In the **Add Reference** dialog box, choose the **Projects** tab and then choose the LoanClass project.</span></span>  
  
7. <span data-ttu-id="f1327-137">Fare clic su **OK** per chiudere la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="f1327-137">Click **OK** to close the dialog box.</span></span>  
  
8. <span data-ttu-id="f1327-138">Nella finestra di progettazione aggiungere quattro controlli <xref:System.Windows.Forms.TextBox> al form.</span><span class="sxs-lookup"><span data-stu-id="f1327-138">In the designer, add four <xref:System.Windows.Forms.TextBox> controls to the form.</span></span>  
  
9. <span data-ttu-id="f1327-139">Nell'editor di codice aggiungere il seguente codice:</span><span class="sxs-lookup"><span data-stu-id="f1327-139">In the Code Editor, add the following code:</span></span>  
  
    ```vb  
    Private WithEvents TestLoan As New LoanClass.Loan(10000.0, 0.075, 36, "Neil Black")  
  
    Private Sub Form1_Load() Handles MyBase.Load  
        TextBox1.Text = TestLoan.LoanAmount.ToString  
        TextBox2.Text = TestLoan.InterestRate.ToString  
        TextBox3.Text = TestLoan.Term.ToString  
        TextBox4.Text = TestLoan.Customer  
    End Sub  
    ```  
  
10. <span data-ttu-id="f1327-140">Aggiungere al form un gestore eventi per l'evento `PropertyChanged` usando il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="f1327-140">Add an event handler for the `PropertyChanged` event to the form by using the following code:</span></span>  
  
    ```vb  
    Public Sub CustomerPropertyChanged(  
          ByVal sender As Object,  
          ByVal e As System.ComponentModel.PropertyChangedEventArgs  
        ) Handles TestLoan.PropertyChanged  
  
        MsgBox(e.PropertyName & " has been changed.")  
    End Sub  
    ```  
  
 <span data-ttu-id="f1327-141">A questo punto, è possibile compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="f1327-141">At this point, you can build and run the application.</span></span> <span data-ttu-id="f1327-142">Si noti che i valori predefiniti della classe `Loan` vengono visualizzati nelle caselle di testo.</span><span class="sxs-lookup"><span data-stu-id="f1327-142">Note that the default values from the `Loan` class appear in the text boxes.</span></span> <span data-ttu-id="f1327-143">Provare a modificare il valore del tasso di interesse da 7.5 a 7.1, quindi chiudere l'applicazione ed eseguirla nuovamente: verrà ripristinato il valore predefinito 7.5.</span><span class="sxs-lookup"><span data-stu-id="f1327-143">Try to change the interest-rate value from 7.5 to 7.1, and then close the application and run it again—the value reverts to the default of 7.5.</span></span>  
  
 <span data-ttu-id="f1327-144">Nel mondo reale i tassi di interesse variano periodicamente, ma non necessariamente ogni volta che l'applicazione viene eseguita.</span><span class="sxs-lookup"><span data-stu-id="f1327-144">In the real world, interest rates change periodically, but not necessarily every time that the application is run.</span></span> <span data-ttu-id="f1327-145">Anziché fare in modo che l'utente aggiorni il tasso di interesse ogni volta che viene eseguita l'applicazione, è preferibile mantenere il tasso di interesse più recente tra le istanze dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="f1327-145">Rather than making the user update the interest rate every time that the application runs, it is better to preserve the most recent interest rate between instances of the application.</span></span> <span data-ttu-id="f1327-146">Nel passaggio successivo verrà eseguita questa operazione, aggiungendo la serializzazione alla classe Loan.</span><span class="sxs-lookup"><span data-stu-id="f1327-146">In the next step, you will do just that by adding serialization to the Loan class.</span></span>  
  
## <a name="using-serialization-to-persist-the-object"></a><span data-ttu-id="f1327-147">Usare la serializzazione per la persistenza dell'oggetto</span><span class="sxs-lookup"><span data-stu-id="f1327-147">Using Serialization to Persist the Object</span></span>  
 <span data-ttu-id="f1327-148">Per rendere persistenti i valori per la classe Loan, per prima cosa contrassegnare la classe con l'attributo `Serializable`.</span><span class="sxs-lookup"><span data-stu-id="f1327-148">In order to persist the values for the Loan class, you must first mark the class with the `Serializable` attribute.</span></span>  
  
### <a name="to-mark-a-class-as-serializable"></a><span data-ttu-id="f1327-149">Per contrassegnare una classe come serializzabile</span><span class="sxs-lookup"><span data-stu-id="f1327-149">To mark a class as serializable</span></span>  
  
- <span data-ttu-id="f1327-150">Modificare la dichiarazione della classe per la classe Loan come segue:</span><span class="sxs-lookup"><span data-stu-id="f1327-150">Change the class declaration for the Loan class as follows:</span></span>  
  
    ```vb  
    <Serializable()>  
    Public Class Loan  
    ```  
  
 <span data-ttu-id="f1327-151">L'attributo `Serializable` indica al compilatore che tutti gli elementi nella classe possono essere resi persistenti in un file.</span><span class="sxs-lookup"><span data-stu-id="f1327-151">The `Serializable` attribute tells the compiler that everything in the class can be persisted to a file.</span></span> <span data-ttu-id="f1327-152">Poiché l'evento `PropertyChanged` è gestito da un oggetto Windows Form, non può essere serializzato.</span><span class="sxs-lookup"><span data-stu-id="f1327-152">Because the `PropertyChanged` event is handled by a Windows Form object, it cannot be serialized.</span></span> <span data-ttu-id="f1327-153">L'attributo `NonSerialized` può essere usato per contrassegnare i membri della classe che non devono essere resi persistenti.</span><span class="sxs-lookup"><span data-stu-id="f1327-153">The `NonSerialized` attribute can be used to mark class members that should not be persisted.</span></span>  
  
### <a name="to-prevent-a-member-from-being-serialized"></a><span data-ttu-id="f1327-154">Per impedire la serializzazione di un membro</span><span class="sxs-lookup"><span data-stu-id="f1327-154">To prevent a member from being serialized</span></span>  
  
- <span data-ttu-id="f1327-155">Modificare la dichiarazione per l'evento `PropertyChanged` come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="f1327-155">Change the declaration for the `PropertyChanged` event as follows:</span></span>  
  
    ```vb  
    <NonSerialized()>  
    Event PropertyChanged As System.ComponentModel.PropertyChangedEventHandler _  
      Implements System.ComponentModel.INotifyPropertyChanged.PropertyChanged  
    ```  
  
 <span data-ttu-id="f1327-156">Il passaggio successivo consiste nell'aggiungere il codice di serializzazione all'applicazione LoanApp.</span><span class="sxs-lookup"><span data-stu-id="f1327-156">The next step is to add the serialization code to the LoanApp application.</span></span> <span data-ttu-id="f1327-157">Per serializzare la classe e scriverla in un file, si useranno gli spazi dei nomi <xref:System.IO> e <xref:System.Xml.Serialization>.</span><span class="sxs-lookup"><span data-stu-id="f1327-157">In order to serialize the class and write it to a file, you will use the <xref:System.IO> and <xref:System.Xml.Serialization> namespaces.</span></span> <span data-ttu-id="f1327-158">Per evitare di digitare i nomi completi, è possibile aggiungere riferimenti alle librerie di classe necessarie.</span><span class="sxs-lookup"><span data-stu-id="f1327-158">To avoid typing the fully qualified names, you can add references to the necessary class libraries.</span></span>  
  
### <a name="to-add-references-to-namespaces"></a><span data-ttu-id="f1327-159">Per aggiungere riferimenti agli spazi dei nomi</span><span class="sxs-lookup"><span data-stu-id="f1327-159">To add references to namespaces</span></span>  
  
- <span data-ttu-id="f1327-160">Aggiungere le seguenti istruzioni all'inizio della classe `Form1`:</span><span class="sxs-lookup"><span data-stu-id="f1327-160">Add the following statements to the top of the `Form1` class:</span></span>  
  
    ```vb  
    Imports System.IO  
    Imports System.Runtime.Serialization.Formatters.Binary  
    ```  
  
     <span data-ttu-id="f1327-161">In questo caso, si usa un formattatore binario per salvare l'oggetto in formato binario.</span><span class="sxs-lookup"><span data-stu-id="f1327-161">In this case, you are using a binary formatter to save the object in a binary format.</span></span>  
  
 <span data-ttu-id="f1327-162">Il passaggio successivo consiste nell'aggiungere codice per deserializzare l'oggetto dal file quando viene creato l'oggetto.</span><span class="sxs-lookup"><span data-stu-id="f1327-162">The next step is to add code to deserialize the object from the file when the object is created.</span></span>  
  
### <a name="to-deserialize-an-object"></a><span data-ttu-id="f1327-163">Per deserializzare un oggetto</span><span class="sxs-lookup"><span data-stu-id="f1327-163">To deserialize an object</span></span>  
  
1. <span data-ttu-id="f1327-164">Aggiungere una costante alla classe per il nome del file di dati serializzati.</span><span class="sxs-lookup"><span data-stu-id="f1327-164">Add a constant to the class for the serialized data's file name.</span></span>  
  
    ```vb  
    Const FileName As String = "..\..\SavedLoan.bin"  
    ```  
  
2. <span data-ttu-id="f1327-165">Modificare il codice nella routine evento `Form1_Load` come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="f1327-165">Modify the code in the `Form1_Load` event procedure as follows:</span></span>  
  
    ```vb  
    Private WithEvents TestLoan As New LoanClass.Loan(10000.0, 0.075, 36, "Neil Black")  
  
    Private Sub Form1_Load() Handles MyBase.Load  
        If File.Exists(FileName) Then  
            Dim TestFileStream As Stream = File.OpenRead(FileName)  
            Dim deserializer As New BinaryFormatter  
            TestLoan = CType(deserializer.Deserialize(TestFileStream), LoanClass.Loan)  
            TestFileStream.Close()  
        End If  
  
        AddHandler TestLoan.PropertyChanged, AddressOf Me.CustomerPropertyChanged  
  
        TextBox1.Text = TestLoan.LoanAmount.ToString  
        TextBox2.Text = TestLoan.InterestRate.ToString  
        TextBox3.Text = TestLoan.Term.ToString  
        TextBox4.Text = TestLoan.Customer  
    End Sub  
    ```  
  
     <span data-ttu-id="f1327-166">Si noti che è necessario prima verificare che il file esista.</span><span class="sxs-lookup"><span data-stu-id="f1327-166">Note that you first must check that the file exists.</span></span> <span data-ttu-id="f1327-167">Se esiste, creare una classe <xref:System.IO.Stream> per leggere il file binario e una classe <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> per convertire il file.</span><span class="sxs-lookup"><span data-stu-id="f1327-167">If it exists, create a <xref:System.IO.Stream> class to read the binary file and a <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> class to translate the file.</span></span> <span data-ttu-id="f1327-168">È anche necessario eseguire la conversione dal tipo di flusso al tipo di oggetto Loan.</span><span class="sxs-lookup"><span data-stu-id="f1327-168">You also need to convert from the stream type to the Loan object type.</span></span>  
  
 <span data-ttu-id="f1327-169">Successivamente è necessario aggiungere codice alla classe `Loan` per il salvataggio dei dati immessi nelle caselle di testo e quindi serializzare la classe in un file.</span><span class="sxs-lookup"><span data-stu-id="f1327-169">Next you must add code to save the data entered in the text boxes to the `Loan` class, and then you must serialize the class to a file.</span></span>  
  
### <a name="to-save-the-data-and-serialize-the-class"></a><span data-ttu-id="f1327-170">Per salvare i dati e serializzare la classe</span><span class="sxs-lookup"><span data-stu-id="f1327-170">To save the data and serialize the class</span></span>  
  
- <span data-ttu-id="f1327-171">Aggiungere il codice seguente alla routine evento `Form1_FormClosing`:</span><span class="sxs-lookup"><span data-stu-id="f1327-171">Add the following code to the `Form1_FormClosing` event procedure:</span></span>  
  
    ```vb  
    Private Sub Form1_FormClosing() Handles MyBase.FormClosing  
        TestLoan.LoanAmount = CDbl(TextBox1.Text)  
        TestLoan.InterestRate = CDbl(TextBox2.Text)  
        TestLoan.Term = CInt(TextBox3.Text)  
        TestLoan.Customer = TextBox4.Text  
  
        Dim TestFileStream As Stream = File.Create(FileName)  
        Dim serializer As New BinaryFormatter  
        serializer.Serialize(TestFileStream, TestLoan)  
        TestFileStream.Close()  
    End Sub  
    ```  
  
 <span data-ttu-id="f1327-172">A questo punto, è nuovamente possibile compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="f1327-172">At this point, you can again build and run the application.</span></span> <span data-ttu-id="f1327-173">Inizialmente i valori predefiniti vengono visualizzati nelle caselle di testo.</span><span class="sxs-lookup"><span data-stu-id="f1327-173">Initially, the default values appear in the text boxes.</span></span> <span data-ttu-id="f1327-174">Provare a modificare i valori e immettere un nome nella quarta casella di testo.</span><span class="sxs-lookup"><span data-stu-id="f1327-174">Try to change the values and enter a name in the fourth text box.</span></span> <span data-ttu-id="f1327-175">Chiudere l'applicazione ed eseguirla nuovamente.</span><span class="sxs-lookup"><span data-stu-id="f1327-175">Close the application and then run it again.</span></span> <span data-ttu-id="f1327-176">Si noti che i nuovi valori ora appaiono nelle caselle di testo.</span><span class="sxs-lookup"><span data-stu-id="f1327-176">Note that the new values now appear in the text boxes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1327-177">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f1327-177">See also</span></span>

- [<span data-ttu-id="f1327-178">Serializzazione (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f1327-178">Serialization (Visual Basic)</span></span>](index.md)
- [<span data-ttu-id="f1327-179">Guida per programmatori Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f1327-179">Visual Basic Programming Guide</span></span>](../../index.md)

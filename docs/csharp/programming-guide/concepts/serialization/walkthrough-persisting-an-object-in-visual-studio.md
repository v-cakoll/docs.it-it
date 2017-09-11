---
title: 'Procedura dettagliata: Persistenza di un oggetto in Visual Studio (C#)'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: get-started-article
dev_langs:
- CSharp
ms.assetid: a544ce46-ee25-49da-afd4-457a3d59bf63
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 4c8dce64c470f01f540a83f68e3861df56913e4c
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="walkthrough-persisting-an-object-in-visual-studio-c"></a><span data-ttu-id="27252-102">Procedura dettagliata: Persistenza di un oggetto in Visual Studio (C#)</span><span class="sxs-lookup"><span data-stu-id="27252-102">Walkthrough: Persisting an Object in Visual Studio (C#)</span></span>
<span data-ttu-id="27252-103">Sebbene sia possibile impostare le proprietà di un oggetto sui valori predefiniti in fase di progettazione, tutti i valori immessi in fase di esecuzione vengono persi quando l'oggetto viene eliminato.</span><span class="sxs-lookup"><span data-stu-id="27252-103">Although you can set an object's properties to default values at design time, any values entered at run time are lost when the object is destroyed.</span></span> <span data-ttu-id="27252-104">È possibile usare la serializzazione per rendere persistenti i dati di un oggetto tra le istanze, consentendo di archiviare i valori e di recuperarli alla successiva creazione di un'istanza dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="27252-104">You can use serialization to persist an object's data between instances, which enables you to store values and retrieve them the next time that the object is instantiated.</span></span>  
  
 <span data-ttu-id="27252-105">In questa procedura verrà creato un oggetto `Loan` semplice i cui dati verranno resi persistenti in un file.</span><span class="sxs-lookup"><span data-stu-id="27252-105">In this walkthrough, you will create a simple `Loan` object and persist its data to a file.</span></span> <span data-ttu-id="27252-106">I dati verranno quindi recuperati dal file quando si ricrea l'oggetto.</span><span class="sxs-lookup"><span data-stu-id="27252-106">You will then retrieve the data from the file when you re-create the object.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="27252-107">Questo esempio crea un nuovo file se il file non esiste già.</span><span class="sxs-lookup"><span data-stu-id="27252-107">This example creates a new file if the file does not already exist.</span></span> <span data-ttu-id="27252-108">Se un'applicazione deve creare un file, per tale applicazione deve essere disponibile l'autorizzazione `Create` per la cartella.</span><span class="sxs-lookup"><span data-stu-id="27252-108">If an application must create a file, that application must `Create` permission for the folder.</span></span> <span data-ttu-id="27252-109">Le autorizzazioni vengono impostate usando gli elenchi di controllo di accesso.</span><span class="sxs-lookup"><span data-stu-id="27252-109">Permissions are set by using access control lists.</span></span> <span data-ttu-id="27252-110">Se il file esiste già, per l'applicazione è necessaria solo l'autorizzazione `Write`, di livello inferiore.</span><span class="sxs-lookup"><span data-stu-id="27252-110">If the file already exists, the application needs only `Write` permission, a lesser permission.</span></span> <span data-ttu-id="27252-111">Se possibile, è più sicuro creare il file durante la distribuzione e concedere solo autorizzazioni `Read` per un singolo file, anziché autorizzazioni Create per una cartella.</span><span class="sxs-lookup"><span data-stu-id="27252-111">Where possible, it is more secure to create the file during deployment, and only grant `Read` permissions to a single file (instead of Create permissions for a folder).</span></span> <span data-ttu-id="27252-112">Inoltre, è più sicuro scrivere dati nelle cartelle utente anziché nella cartella radice o nella cartella dei file di programma.</span><span class="sxs-lookup"><span data-stu-id="27252-112">Also, it is more secure to write data to user folders than to the root folder or the Program Files folder.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="27252-113">In questo esempio i dati vengono archiviati in un file in formato binario.</span><span class="sxs-lookup"><span data-stu-id="27252-113">This example stores data in a binary format file.</span></span> <span data-ttu-id="27252-114">Non usare questi formati per i dati riservati, ad esempio password o informazioni sulla carta di credito.</span><span class="sxs-lookup"><span data-stu-id="27252-114">These formats should not be used for sensitive data, such as passwords or credit-card information.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="27252-115">Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma.</span><span class="sxs-lookup"><span data-stu-id="27252-115">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="27252-116">Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** .</span><span class="sxs-lookup"><span data-stu-id="27252-116">To change your settings, click **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="27252-117">Per altre informazioni, vedere [Personalizzazione delle impostazioni di sviluppo in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="27252-117">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
## <a name="creating-the-loan-object"></a><span data-ttu-id="27252-118">Creare l'oggetto Loan</span><span class="sxs-lookup"><span data-stu-id="27252-118">Creating the Loan Object</span></span>  
 <span data-ttu-id="27252-119">Il primo passaggio consiste nel creare una classe `Loan` e un'applicazione di test che usa la classe.</span><span class="sxs-lookup"><span data-stu-id="27252-119">The first step is to create a `Loan` class and a test application that uses the class.</span></span>  
  
### <a name="to-create-the-loan-class"></a><span data-ttu-id="27252-120">Per creare la classe Loan</span><span class="sxs-lookup"><span data-stu-id="27252-120">To create the Loan class</span></span>  
  
1.  <span data-ttu-id="27252-121">Creare un nuovo progetto di libreria di classi denominato "LoanClass".</span><span class="sxs-lookup"><span data-stu-id="27252-121">Create a new Class Library project and name it "LoanClass".</span></span> <span data-ttu-id="27252-122">Per altre informazioni, vedere [Creazione di soluzioni e progetti](/visualstudio/ide/creating-solutions-and-projects).</span><span class="sxs-lookup"><span data-stu-id="27252-122">For more information, see [Creating Solutions and Projects](/visualstudio/ide/creating-solutions-and-projects).</span></span>  
  
2.  <span data-ttu-id="27252-123">In **Esplora soluzioni** aprire il menu di scelta rapida per il file Class1 e scegliere **Rinomina**.</span><span class="sxs-lookup"><span data-stu-id="27252-123">In **Solution Explorer**, open the shortcut menu for the Class1 file and choose **Rename**.</span></span> <span data-ttu-id="27252-124">Rinominare il file `Loan` e premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="27252-124">Rename the file to `Loan` and press ENTER.</span></span> <span data-ttu-id="27252-125">Modificando il nome del file, anche la classe verrà rinominata `Loan`.</span><span class="sxs-lookup"><span data-stu-id="27252-125">Renaming the file will also rename the class to `Loan`.</span></span>  
  
3.  <span data-ttu-id="27252-126">Aggiungere i seguenti membri pubblici alla classe:</span><span class="sxs-lookup"><span data-stu-id="27252-126">Add the following public members to the class:</span></span>  
  
    ```csharp  
    public class Loan : System.ComponentModel.INotifyPropertyChanged  
    {  
        public double LoanAmount {get; set;}  
        public double InterestRate {get; set;}  
        public int Term {get; set;}  
  
        private string p_Customer;  
        public string Customer  
        {  
            get { return p_Customer; }  
            set   
            {  
                p_Customer = value;  
                PropertyChanged(this,  
                  new System.ComponentModel.PropertyChangedEventArgs("Customer"));  
            }  
        }  
  
        public event System.ComponentModel.PropertyChangedEventHandler PropertyChanged;  
  
        public Loan(double loanAmount,  
                    double interestRate,  
                    int term,  
                    string customer)  
        {  
            this.LoanAmount = loanAmount;  
            this.InterestRate = interestRate;  
            this.Term = term;  
            p_Customer = customer;  
        }  
    }  
    ```  
  
 <span data-ttu-id="27252-127">Sarà anche necessario creare un'applicazione semplice che usa la classe `Loan`.</span><span class="sxs-lookup"><span data-stu-id="27252-127">You will also have to create a simple application that uses the `Loan` class.</span></span>  
  
### <a name="to-create-a-test-application"></a><span data-ttu-id="27252-128">Per creare un'applicazione di test</span><span class="sxs-lookup"><span data-stu-id="27252-128">To create a test application</span></span>  
  
1.  <span data-ttu-id="27252-129">Per aggiungere un progetto di Windows Form Application alla soluzione, nel menu **File** scegliere **Aggiungi**, **Nuovo progetto**.</span><span class="sxs-lookup"><span data-stu-id="27252-129">To add a Windows Forms Application project to your solution, on the **File** menu, choose **Add**, **New Project**.</span></span>  
  
2.  <span data-ttu-id="27252-130">Scegliere **Windows Forms Application** nella finestra di dialogo **Aggiungi nuovo progetto**, quindi immettere `LoanApp` come nome del progetto e quindi fare clic su **OK** per chiudere la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="27252-130">In the **Add New Project** dialog box, choose **Windows Forms Application**, and enter `LoanApp` as the name of the project, and then click **OK** to close the dialog box.</span></span>  
  
3.  <span data-ttu-id="27252-131">Scegliere il progetto LoanApp in **Esplora soluzioni**.</span><span class="sxs-lookup"><span data-stu-id="27252-131">In **Solution Explorer**, choose the LoanApp project.</span></span>  
  
4.  <span data-ttu-id="27252-132">Nel menu **Progetto** scegliere **Imposta come progetto di avvio**.</span><span class="sxs-lookup"><span data-stu-id="27252-132">On the **Project** menu, choose **Set as StartUp Project**.</span></span>  
  
5.  <span data-ttu-id="27252-133">Scegliere **Aggiungi riferimento** dal menu **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="27252-133">On the **Project** menu, choose **Add Reference**.</span></span>  
  
6.  <span data-ttu-id="27252-134">Nella finestra di dialogo **Aggiungi riferimento** scegliere la scheda **Progetti** e quindi il progetto LoanClass.</span><span class="sxs-lookup"><span data-stu-id="27252-134">In the **Add Reference** dialog box, choose the **Projects** tab and then choose the LoanClass project.</span></span>  
  
7.  <span data-ttu-id="27252-135">Fare clic su **OK** per chiudere la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="27252-135">Click **OK** to close the dialog box.</span></span>  
  
8.  <span data-ttu-id="27252-136">Nella finestra di progettazione aggiungere quattro controlli <xref:System.Windows.Forms.TextBox> al form.</span><span class="sxs-lookup"><span data-stu-id="27252-136">In the designer, add four <xref:System.Windows.Forms.TextBox> controls to the form.</span></span>  
  
9. <span data-ttu-id="27252-137">Nell'editor di codice aggiungere il seguente codice:</span><span class="sxs-lookup"><span data-stu-id="27252-137">In the Code Editor, add the following code:</span></span>  
  
    ```csharp  
    private LoanClass.Loan TestLoan = new LoanClass.Loan(10000.0, 0.075, 36, "Neil Black");  
  
    private void Form1_Load(object sender, EventArgs e)  
    {  
        textBox1.Text = TestLoan.LoanAmount.ToString();  
        textBox2.Text = TestLoan.InterestRate.ToString();  
        textBox3.Text = TestLoan.Term.ToString();  
        textBox4.Text = TestLoan.Customer;  
    }  
    ```  
  
10. <span data-ttu-id="27252-138">Aggiungere al form un gestore eventi per l'evento `PropertyChanged` usando il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="27252-138">Add an event handler for the `PropertyChanged` event to the form by using the following code:</span></span>  
  
    ```csharp  
    private void CustomerPropertyChanged(object sender,   
        System.ComponentModel.PropertyChangedEventArgs e)  
    {  
        MessageBox.Show(e.PropertyName + " has been changed.");  
    }  
    ```  
  
 <span data-ttu-id="27252-139">A questo punto, è possibile compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="27252-139">At this point, you can build and run the application.</span></span> <span data-ttu-id="27252-140">Si noti che i valori predefiniti della classe `Loan` vengono visualizzati nelle caselle di testo.</span><span class="sxs-lookup"><span data-stu-id="27252-140">Note that the default values from the `Loan` class appear in the text boxes.</span></span> <span data-ttu-id="27252-141">Provare a modificare il valore del tasso di interesse da 7.5 a 7.1, quindi chiudere l'applicazione ed eseguirla nuovamente: verrà ripristinato il valore predefinito 7.5.</span><span class="sxs-lookup"><span data-stu-id="27252-141">Try to change the interest-rate value from 7.5 to 7.1, and then close the application and run it again—the value reverts to the default of 7.5.</span></span>  
  
 <span data-ttu-id="27252-142">Nel mondo reale i tassi di interesse variano periodicamente, ma non necessariamente ogni volta che l'applicazione viene eseguita.</span><span class="sxs-lookup"><span data-stu-id="27252-142">In the real world, interest rates change periodically, but not necessarily every time that the application is run.</span></span> <span data-ttu-id="27252-143">Anziché fare in modo che l'utente aggiorni il tasso di interesse ogni volta che viene eseguita l'applicazione, è preferibile mantenere il tasso di interesse più recente tra le istanze dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="27252-143">Rather than making the user update the interest rate every time that the application runs, it is better to preserve the most recent interest rate between instances of the application.</span></span> <span data-ttu-id="27252-144">Nel passaggio successivo verrà eseguita questa operazione, aggiungendo la serializzazione alla classe Loan.</span><span class="sxs-lookup"><span data-stu-id="27252-144">In the next step, you will do just that by adding serialization to the Loan class.</span></span>  
  
## <a name="using-serialization-to-persist-the-object"></a><span data-ttu-id="27252-145">Usare la serializzazione per la persistenza dell'oggetto</span><span class="sxs-lookup"><span data-stu-id="27252-145">Using Serialization to Persist the Object</span></span>  
 <span data-ttu-id="27252-146">Per rendere persistenti i valori per la classe Loan, per prima cosa contrassegnare la classe con l'attributo `Serializable`.</span><span class="sxs-lookup"><span data-stu-id="27252-146">In order to persist the values for the Loan class, you must first mark the class with the `Serializable` attribute.</span></span>  
  
### <a name="to-mark-a-class-as-serializable"></a><span data-ttu-id="27252-147">Per contrassegnare una classe come serializzabile</span><span class="sxs-lookup"><span data-stu-id="27252-147">To mark a class as serializable</span></span>  
  
-   <span data-ttu-id="27252-148">Modificare la dichiarazione della classe per la classe Loan come segue:</span><span class="sxs-lookup"><span data-stu-id="27252-148">Change the class declaration for the Loan class as follows:</span></span>  
  
    ```csharp  
    [Serializable()]  
    public class Loan : System.ComponentModel.INotifyPropertyChanged  
    {  
    ```  
  
 <span data-ttu-id="27252-149">L'attributo `Serializable` indica al compilatore che tutti gli elementi nella classe possono essere resi persistenti in un file.</span><span class="sxs-lookup"><span data-stu-id="27252-149">The `Serializable` attribute tells the compiler that everything in the class can be persisted to a file.</span></span> <span data-ttu-id="27252-150">Poiché l'evento `PropertyChanged` è gestito da un oggetto Windows Form, non può essere serializzato.</span><span class="sxs-lookup"><span data-stu-id="27252-150">Because the `PropertyChanged` event is handled by a Windows Form object, it cannot be serialized.</span></span> <span data-ttu-id="27252-151">L'attributo `NonSerialized` può essere usato per contrassegnare i membri della classe che non devono essere resi persistenti.</span><span class="sxs-lookup"><span data-stu-id="27252-151">The `NonSerialized` attribute can be used to mark class members that should not be persisted.</span></span>  
  
### <a name="to-prevent-a-member-from-being-serialized"></a><span data-ttu-id="27252-152">Per impedire la serializzazione di un membro</span><span class="sxs-lookup"><span data-stu-id="27252-152">To prevent a member from being serialized</span></span>  
  
-   <span data-ttu-id="27252-153">Modificare la dichiarazione per l'evento `PropertyChanged` come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="27252-153">Change the declaration for the `PropertyChanged` event as follows:</span></span>  
  
    ```csharp  
    [field: NonSerialized()]  
    public event System.ComponentModel.PropertyChangedEventHandler PropertyChanged;  
    ```  
  
 <span data-ttu-id="27252-154">Il passaggio successivo consiste nell'aggiungere il codice di serializzazione all'applicazione LoanApp.</span><span class="sxs-lookup"><span data-stu-id="27252-154">The next step is to add the serialization code to the LoanApp application.</span></span> <span data-ttu-id="27252-155">Per serializzare la classe e scriverla in un file, si useranno gli spazi dei nomi <xref:System.IO> e <xref:System.Xml.Serialization>.</span><span class="sxs-lookup"><span data-stu-id="27252-155">In order to serialize the class and write it to a file, you will use the <xref:System.IO> and <xref:System.Xml.Serialization> namespaces.</span></span> <span data-ttu-id="27252-156">Per evitare di digitare i nomi completi, è possibile aggiungere riferimenti alle librerie di classe necessarie.</span><span class="sxs-lookup"><span data-stu-id="27252-156">To avoid typing the fully qualified names, you can add references to the necessary class libraries.</span></span>  
  
### <a name="to-add-references-to-namespaces"></a><span data-ttu-id="27252-157">Per aggiungere riferimenti agli spazi dei nomi</span><span class="sxs-lookup"><span data-stu-id="27252-157">To add references to namespaces</span></span>  
  
-   <span data-ttu-id="27252-158">Aggiungere le seguenti istruzioni all'inizio della classe `Form1`:</span><span class="sxs-lookup"><span data-stu-id="27252-158">Add the following statements to the top of the `Form1` class:</span></span>  
  
    ```csharp  
    using System.IO;  
    using System.Runtime.Serialization.Formatters.Binary;  
    ```  
  
     <span data-ttu-id="27252-159">In questo caso, si usa un formattatore binario per salvare l'oggetto in formato binario.</span><span class="sxs-lookup"><span data-stu-id="27252-159">In this case, you are using a binary formatter to save the object in a binary format.</span></span>  
  
 <span data-ttu-id="27252-160">Il passaggio successivo consiste nell'aggiungere codice per deserializzare l'oggetto dal file quando viene creato l'oggetto.</span><span class="sxs-lookup"><span data-stu-id="27252-160">The next step is to add code to deserialize the object from the file when the object is created.</span></span>  
  
### <a name="to-deserialize-an-object"></a><span data-ttu-id="27252-161">Per deserializzare un oggetto</span><span class="sxs-lookup"><span data-stu-id="27252-161">To deserialize an object</span></span>  
  
1.  <span data-ttu-id="27252-162">Aggiungere una costante alla classe per il nome del file di dati serializzati.</span><span class="sxs-lookup"><span data-stu-id="27252-162">Add a constant to the class for the serialized data's file name.</span></span>  
  
    ```csharp  
    const string FileName = @"..\..\SavedLoan.bin";  
    ```  
  
2.  <span data-ttu-id="27252-163">Modificare il codice nella routine evento `Form1_Load` come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="27252-163">Modify the code in the `Form1_Load` event procedure as follows:</span></span>  
  
    ```csharp  
    private LoanClass.Loan TestLoan = new LoanClass.Loan(10000.0, 0.075, 36, "Neil Black");  
  
    private void Form1_Load(object sender, EventArgs e)  
    {  
        if (File.Exists(FileName))  
        {  
            Stream TestFileStream = File.OpenRead(FileName);  
            BinaryFormatter deserializer = new BinaryFormatter();  
            TestLoan = (LoanClass.Loan)deserializer.Deserialize(TestFileStream);  
            TestFileStream.Close();  
        }  
  
        TestLoan.PropertyChanged += this.CustomerPropertyChanged;  
  
        textBox1.Text = TestLoan.LoanAmount.ToString();  
        textBox2.Text = TestLoan.InterestRate.ToString();  
        textBox3.Text = TestLoan.Term.ToString();  
        textBox4.Text = TestLoan.Customer;  
    }  
    ```  
  
     <span data-ttu-id="27252-164">Si noti che è necessario prima verificare che il file esista.</span><span class="sxs-lookup"><span data-stu-id="27252-164">Note that you first must check that the file exists.</span></span> <span data-ttu-id="27252-165">Se esiste, creare una classe <xref:System.IO.Stream> per leggere il file binario e una classe <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> per convertire il file.</span><span class="sxs-lookup"><span data-stu-id="27252-165">If it exists, create a <xref:System.IO.Stream> class to read the binary file and a <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> class to translate the file.</span></span> <span data-ttu-id="27252-166">È anche necessario eseguire la conversione dal tipo di flusso al tipo di oggetto Loan.</span><span class="sxs-lookup"><span data-stu-id="27252-166">You also need to convert from the stream type to the Loan object type.</span></span>  
  
 <span data-ttu-id="27252-167">Successivamente è necessario aggiungere codice alla classe `Loan` per il salvataggio dei dati immessi nelle caselle di testo e quindi serializzare la classe in un file.</span><span class="sxs-lookup"><span data-stu-id="27252-167">Next you must add code to save the data entered in the text boxes to the `Loan` class, and then you must serialize the class to a file.</span></span>  
  
### <a name="to-save-the-data-and-serialize-the-class"></a><span data-ttu-id="27252-168">Per salvare i dati e serializzare la classe</span><span class="sxs-lookup"><span data-stu-id="27252-168">To save the data and serialize the class</span></span>  
  
-   <span data-ttu-id="27252-169">Aggiungere il codice seguente alla routine evento `Form1_FormClosing`:</span><span class="sxs-lookup"><span data-stu-id="27252-169">Add the following code to the `Form1_FormClosing` event procedure:</span></span>  
  
    ```csharp  
    private void Form1_FormClosing(object sender, FormClosingEventArgs e)  
    {  
        TestLoan.LoanAmount = Convert.ToDouble(textBox1.Text);  
        TestLoan.InterestRate = Convert.ToDouble(textBox2.Text);  
        TestLoan.Term = Convert.ToInt32(textBox3.Text);  
        TestLoan.Customer = textBox4.Text;  
  
        Stream TestFileStream = File.Create(FileName);  
        BinaryFormatter serializer = new BinaryFormatter();  
        serializer.Serialize(TestFileStream, TestLoan);  
        TestFileStream.Close();  
    }  
    ```  
  
 <span data-ttu-id="27252-170">A questo punto, è nuovamente possibile compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="27252-170">At this point, you can again build and run the application.</span></span> <span data-ttu-id="27252-171">Inizialmente i valori predefiniti vengono visualizzati nelle caselle di testo.</span><span class="sxs-lookup"><span data-stu-id="27252-171">Initially, the default values appear in the text boxes.</span></span> <span data-ttu-id="27252-172">Provare a modificare i valori e immettere un nome nella quarta casella di testo.</span><span class="sxs-lookup"><span data-stu-id="27252-172">Try to change the values and enter a name in the fourth text box.</span></span> <span data-ttu-id="27252-173">Chiudere l'applicazione ed eseguirla nuovamente.</span><span class="sxs-lookup"><span data-stu-id="27252-173">Close the application and then run it again.</span></span> <span data-ttu-id="27252-174">Si noti che i nuovi valori ora appaiono nelle caselle di testo.</span><span class="sxs-lookup"><span data-stu-id="27252-174">Note that the new values now appear in the text boxes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27252-175">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="27252-175">See Also</span></span>  
 <span data-ttu-id="27252-176">[Serializzazione (C#)](../../../../csharp/programming-guide/concepts/serialization/index.md) </span><span class="sxs-lookup"><span data-stu-id="27252-176">[Serialization (C# )](../../../../csharp/programming-guide/concepts/serialization/index.md) </span></span>  
 [<span data-ttu-id="27252-177">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="27252-177">C# Programming Guide</span></span>](../../../../csharp/programming-guide/index.md)


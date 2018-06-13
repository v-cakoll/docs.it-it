---
title: 'Procedura: Aprire file con il componente OpenFileDialog'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- OpenFileDialog component [Windows Forms], opening files
- OpenFile method [Windows Forms], OpenFileDialog component
- files [Windows Forms], opening with OpenFileDialog component
ms.assetid: 9d88367a-cc21-4ffd-be74-89fd63767d35
ms.openlocfilehash: d7e1ebb319576aa7a38d55d8cb9f3652626966b6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33542275"
---
# <a name="how-to-open-files-using-the-openfiledialog-component"></a><span data-ttu-id="16b23-102">Procedura: Aprire file con il componente OpenFileDialog</span><span class="sxs-lookup"><span data-stu-id="16b23-102">How to: Open Files Using the OpenFileDialog Component</span></span>
<span data-ttu-id="16b23-103">Il <xref:System.Windows.Forms.OpenFileDialog> consente agli utenti di sfogliare le cartelle del computer o di qualsiasi computer nella rete e selezionare uno o più file da aprire.</span><span class="sxs-lookup"><span data-stu-id="16b23-103">The <xref:System.Windows.Forms.OpenFileDialog> component allows users to browse the folders of their computer or any computer on the network and select one or more files to open.</span></span> <span data-ttu-id="16b23-104">Nella finestra di dialogo vengono restituiti il percorso e il nome del file selezionato dall'utente.</span><span class="sxs-lookup"><span data-stu-id="16b23-104">The dialog box returns the path and name of the file the user selected in the dialog box.</span></span>  
  
 <span data-ttu-id="16b23-105">Dopo avere selezionato il file da aprire, è possibile procedere all'apertura in due modi.</span><span class="sxs-lookup"><span data-stu-id="16b23-105">Once the user has selected the file to be opened, there are two approaches to the mechanism of opening the file.</span></span> <span data-ttu-id="16b23-106">Se si preferisce utilizzare flussi di file, è possibile creare un'istanza di <xref:System.IO.StreamReader> classe.</span><span class="sxs-lookup"><span data-stu-id="16b23-106">If you prefer to work with file streams, you can create an instance of the <xref:System.IO.StreamReader> class.</span></span> <span data-ttu-id="16b23-107">In alternativa, è possibile utilizzare il <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> per aprire il file selezionato.</span><span class="sxs-lookup"><span data-stu-id="16b23-107">Alternately, you can use the <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> method to open the selected file.</span></span>  
  
 <span data-ttu-id="16b23-108">Nel primo esempio riportato di seguito implica un <xref:System.Security.Permissions.FileIOPermission> controllo delle autorizzazioni (come descritto in "Nota sulla protezione" riportata di seguito), ma consente di accedere al nome del file.</span><span class="sxs-lookup"><span data-stu-id="16b23-108">The first example below involves a <xref:System.Security.Permissions.FileIOPermission> permission check (as described in the "Security Note" below), but gives you access to the filename.</span></span> <span data-ttu-id="16b23-109">Questa tecnica può essere usata dal computer locale, dalla rete Intranet e da Internet.</span><span class="sxs-lookup"><span data-stu-id="16b23-109">You can use this technique from the Local Machine, Intranet, and Internet zones.</span></span> <span data-ttu-id="16b23-110">Il secondo metodo esegue inoltre una <xref:System.Security.Permissions.FileIOPermission> controllo delle autorizzazioni, ma è più adatto per le applicazioni nell'area Intranet o Internet.</span><span class="sxs-lookup"><span data-stu-id="16b23-110">The second method also does a <xref:System.Security.Permissions.FileIOPermission> permission check, but is better suited for applications in the Intranet or Internet zones.</span></span>  
  
### <a name="to-open-a-file-as-a-stream-using-the-openfiledialog-component"></a><span data-ttu-id="16b23-111">Per aprire un file come flusso tramite il componente OpenFileDialog</span><span class="sxs-lookup"><span data-stu-id="16b23-111">To open a file as a stream using the OpenFileDialog component</span></span>  
  
1.  <span data-ttu-id="16b23-112">Visualizzare la finestra di dialogo **Apri file** e chiamare un metodo per aprire il file selezionato dall'utente.</span><span class="sxs-lookup"><span data-stu-id="16b23-112">Display the **Open File** dialog box and call a method to open the file selected by the user.</span></span>  
  
     <span data-ttu-id="16b23-113">Un approccio consiste nell'utilizzare il <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> metodo per visualizzare la finestra di dialogo Apri File e di un'istanza del <xref:System.IO.StreamReader> classe per aprire il file.</span><span class="sxs-lookup"><span data-stu-id="16b23-113">One approach is to use the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method to display the Open File dialog box, and use an instance of the <xref:System.IO.StreamReader> class to open the file.</span></span>  
  
     <span data-ttu-id="16b23-114">Nell'esempio seguente viene utilizzato il <xref:System.Windows.Forms.Button> del controllo <xref:System.Windows.Forms.Control.Click> per aprire un'istanza del gestore dell'evento di <xref:System.Windows.Forms.OpenFileDialog> componente.</span><span class="sxs-lookup"><span data-stu-id="16b23-114">The example below uses the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Click> event handler to open an instance of the <xref:System.Windows.Forms.OpenFileDialog> component.</span></span> <span data-ttu-id="16b23-115">Quando viene scelto un file e l'utente fa clic su **OK**, il file selezionato nella finestra di dialogo viene aperto.</span><span class="sxs-lookup"><span data-stu-id="16b23-115">When a file is chosen and the user clicks **OK**, the file selected in the dialog box opens.</span></span> <span data-ttu-id="16b23-116">In questo caso, il contenuto viene visualizzato in una finestra di messaggio per indicare che il flusso di file è stato letto.</span><span class="sxs-lookup"><span data-stu-id="16b23-116">In this case, the contents are displayed in a message box, just to show that the file stream has been read.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="16b23-117">Per ottenere o impostare il <xref:System.Windows.Forms.FileDialog.FileName%2A> proprietà, l'assembly richiede un livello di privilegio concesso per la <xref:System.Security.Permissions.FileIOPermission?displayProperty=nameWithType> classe.</span><span class="sxs-lookup"><span data-stu-id="16b23-117">To get or set the <xref:System.Windows.Forms.FileDialog.FileName%2A> property, your assembly requires a privilege level granted by the <xref:System.Security.Permissions.FileIOPermission?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="16b23-118">Se viene eseguito in un contesto parzialmente attendibile, il processo potrebbe generare un'eccezione a causa di privilegi insufficienti.</span><span class="sxs-lookup"><span data-stu-id="16b23-118">If you are running in a partial-trust context, the process might throw an exception due to insufficient privileges.</span></span> <span data-ttu-id="16b23-119">Per altre informazioni, vedere [Code Access Security Basics](../../../../docs/framework/misc/code-access-security-basics.md) (Nozioni di base sulla sicurezza dell'accesso di codice).</span><span class="sxs-lookup"><span data-stu-id="16b23-119">For more information, see [Code Access Security Basics](../../../../docs/framework/misc/code-access-security-basics.md).</span></span>  
  
     <span data-ttu-id="16b23-120">Nell'esempio si presuppone il modulo contiene un <xref:System.Windows.Forms.Button> controllo e un <xref:System.Windows.Forms.OpenFileDialog> componente.</span><span class="sxs-lookup"><span data-stu-id="16b23-120">The example assumes your form has a <xref:System.Windows.Forms.Button> control and an <xref:System.Windows.Forms.OpenFileDialog> component.</span></span>  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, _  
       ByVal e As System.EventArgs) Handles Button1.Click  
       If OpenFileDialog1.ShowDialog() = System.Windows.Forms.DialogResult.OK Then  
         Dim sr As New System.IO.StreamReader(OpenFileDialog1.FileName)  
         MessageBox.Show(sr.ReadToEnd)  
         sr.Close()  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)  
    {  
       if(openFileDialog1.ShowDialog() == System.Windows.Forms.DialogResult.OK)  
       {  
          System.IO.StreamReader sr = new   
             System.IO.StreamReader(openFileDialog1.FileName);  
          MessageBox.Show(sr.ReadToEnd());  
          sr.Close();  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       void button1_Click(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          if(openFileDialog1->ShowDialog() == System::Windows::Forms::DialogResult::OK)  
          {  
             System::IO::StreamReader ^ sr = gcnew  
                System::IO::StreamReader(openFileDialog1->FileName);  
             MessageBox::Show(sr->ReadToEnd());  
             sr->Close();  
          }  
       }  
    ```  
  
     <span data-ttu-id="16b23-121">(Visual c# e [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) inserire il codice seguente nel costruttore del form per registrare il gestore dell'evento.</span><span class="sxs-lookup"><span data-stu-id="16b23-121">(Visual C# and [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->button1->Click += gcnew  
       System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="16b23-122">Per ulteriori informazioni sulla lettura da flussi di file, vedere <xref:System.IO.FileStream.BeginRead%2A> e <xref:System.IO.FileStream.Read%2A>.</span><span class="sxs-lookup"><span data-stu-id="16b23-122">For more information about reading from file streams, see <xref:System.IO.FileStream.BeginRead%2A> and <xref:System.IO.FileStream.Read%2A>.</span></span>  
  
### <a name="to-open-a-file-as-a-file-using-the-openfiledialog-component"></a><span data-ttu-id="16b23-123">Per aprire un file come file tramite il componente OpenFileDialog</span><span class="sxs-lookup"><span data-stu-id="16b23-123">To open a file as a file using the OpenFileDialog component</span></span>  
  
1.  <span data-ttu-id="16b23-124">Utilizzare il <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> metodo per visualizzare la finestra di dialogo e <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> metodo per aprire il file.</span><span class="sxs-lookup"><span data-stu-id="16b23-124">Use the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method to display the dialog box and the <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> method to open the file.</span></span>  
  
     <span data-ttu-id="16b23-125">Il <xref:System.Windows.Forms.OpenFileDialog> del componente <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> metodo restituisce i byte che compongono il file.</span><span class="sxs-lookup"><span data-stu-id="16b23-125">The <xref:System.Windows.Forms.OpenFileDialog> component's <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> method returns the bytes that compose the file.</span></span> <span data-ttu-id="16b23-126">e che forniscono un flusso da cui leggere.</span><span class="sxs-lookup"><span data-stu-id="16b23-126">These bytes give you a stream to read from.</span></span> <span data-ttu-id="16b23-127">Nell'esempio seguente, un <xref:System.Windows.Forms.OpenFileDialog> componente viene creata un'istanza con un filtro "cursor", che consente all'utente di scegliere solo i file con l'estensione del nome file`.cur`.</span><span class="sxs-lookup"><span data-stu-id="16b23-127">In the example below, an <xref:System.Windows.Forms.OpenFileDialog> component is instantiated with a "cursor" filter on it, allowing the user to choose only files with the file name extension`.cur`.</span></span> <span data-ttu-id="16b23-128">Se si sceglie un file `.cur`, il cursore del form viene impostato sul cursore selezionato.</span><span class="sxs-lookup"><span data-stu-id="16b23-128">If a`.cur` file is chosen, the form's cursor is set to the selected cursor.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="16b23-129">Per chiamare il <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> (metodo), l'assembly richiede un livello di privilegio concesso per la <xref:System.Security.Permissions.FileIOPermission?displayProperty=nameWithType> classe.</span><span class="sxs-lookup"><span data-stu-id="16b23-129">To call the <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> method, your assembly requires a privilege level granted by the <xref:System.Security.Permissions.FileIOPermission?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="16b23-130">Se viene eseguito in un contesto parzialmente attendibile, il processo potrebbe generare un'eccezione a causa di privilegi insufficienti.</span><span class="sxs-lookup"><span data-stu-id="16b23-130">If you are running in a partial-trust context, the process might throw an exception due to insufficient privileges.</span></span> <span data-ttu-id="16b23-131">Per altre informazioni, vedere [Code Access Security Basics](../../../../docs/framework/misc/code-access-security-basics.md) (Nozioni di base sulla sicurezza dell'accesso di codice).</span><span class="sxs-lookup"><span data-stu-id="16b23-131">For more information, see [Code Access Security Basics](../../../../docs/framework/misc/code-access-security-basics.md).</span></span>  
  
     <span data-ttu-id="16b23-132">Nell'esempio si presuppone il modulo contiene un <xref:System.Windows.Forms.Button> controllo.</span><span class="sxs-lookup"><span data-stu-id="16b23-132">The example assumes your form has a <xref:System.Windows.Forms.Button> control.</span></span>  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, _  
       ByVal e As System.EventArgs) Handles Button1.Click  
       ' Displays an OpenFileDialog so the user can select a Cursor.  
       Dim openFileDialog1 As New OpenFileDialog()  
       openFileDialog1.Filter = "Cursor Files|*.cur"  
       openFileDialog1.Title = "Select a Cursor File"  
  
       ' Show the Dialog.  
       ' If the user clicked OK in the dialog and   
       ' a .CUR file was selected, open it.  
       If openFileDialog1.ShowDialog() = System.Windows.Forms.DialogResult.OK Then  
         ' Assign the cursor in the Stream to the Form's Cursor property.  
         Me.Cursor = New Cursor(openFileDialog1.OpenFile())  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)  
    {  
       // Displays an OpenFileDialog so the user can select a Cursor.  
       OpenFileDialog openFileDialog1 = new OpenFileDialog();  
       openFileDialog1.Filter = "Cursor Files|*.cur";  
       openFileDialog1.Title = "Select a Cursor File";  
  
       // Show the Dialog.  
       // If the user clicked OK in the dialog and  
       // a .CUR file was selected, open it.  
        if (openFileDialog1.ShowDialog() == System.Windows.Forms.DialogResult.OK)  
       {  
          // Assign the cursor in the Stream to the Form's Cursor property.  
          this.Cursor = new Cursor(openFileDialog1.OpenFile());  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       void button1_Click(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          // Displays an OpenFileDialog so the user can select a Cursor.  
          OpenFileDialog ^ openFileDialog1 = new OpenFileDialog();  
          openFileDialog1->Filter = "Cursor Files|*.cur";  
          openFileDialog1->Title = "Select a Cursor File";  
  
          // Show the Dialog.  
          // If the user clicked OK in the dialog and  
          // a .CUR file was selected, open it.  
          if (openFileDialog1->ShowDialog() == System::Windows::Forms::DialogResult::OK)  
          {  
             // Assign the cursor in the Stream to  
             // the Form's Cursor property.  
             this->Cursor = gcnew  
                System::Windows::Forms::Cursor(  
                openFileDialog1->OpenFile());  
          }  
       }  
    ```  
  
     <span data-ttu-id="16b23-133">(Visual c# e [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) inserire il codice seguente nel costruttore del form per registrare il gestore dell'evento.</span><span class="sxs-lookup"><span data-stu-id="16b23-133">(Visual C# and [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->button1->Click += gcnew  
       System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="16b23-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="16b23-134">See Also</span></span>  
 <xref:System.Windows.Forms.OpenFileDialog>  
 [<span data-ttu-id="16b23-135">Componente OpenFileDialog</span><span class="sxs-lookup"><span data-stu-id="16b23-135">OpenFileDialog Component</span></span>](../../../../docs/framework/winforms/controls/openfiledialog-component-windows-forms.md)

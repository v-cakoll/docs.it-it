---
title: 'Procedura: Salvare file con il componente SaveFileDialog'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- saving files
- SaveFileDialog component [Windows Forms], saving files
- files [Windows Forms], saving
- OpenFile method [Windows Forms], saving files with SaveFileDialog component
ms.assetid: 02e8f409-b83f-4707-babb-e71f6b223d90
ms.openlocfilehash: 7a3a7d0b12a83b756eb2790a94a95580576a2c32
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2019
ms.locfileid: "70046269"
---
# <a name="how-to-save-files-using-the-savefiledialog-component"></a><span data-ttu-id="86704-102">Procedura: Salvare file con il componente SaveFileDialog</span><span class="sxs-lookup"><span data-stu-id="86704-102">How to: Save Files Using the SaveFileDialog Component</span></span>

<span data-ttu-id="86704-103">Il <xref:System.Windows.Forms.SaveFileDialog> componente consente agli utenti di esplorare il file System e selezionare i file da salvare.</span><span class="sxs-lookup"><span data-stu-id="86704-103">The <xref:System.Windows.Forms.SaveFileDialog> component allows users to browse the file system and select files to be saved.</span></span> <span data-ttu-id="86704-104">Nella finestra di dialogo vengono restituiti il percorso e il nome del file selezionato dall'utente.</span><span class="sxs-lookup"><span data-stu-id="86704-104">The dialog box returns the path and name of the file the user has selected in the dialog box.</span></span> <span data-ttu-id="86704-105">Tuttavia, è necessario scrivere il codice per salvare effettivamente i file sul disco.</span><span class="sxs-lookup"><span data-stu-id="86704-105">However, you must write the code to actually write the files to disk.</span></span>

### <a name="to-save-a-file-using-the-savefiledialog-component"></a><span data-ttu-id="86704-106">Per salvare un file tramite il componente SaveFileDialog</span><span class="sxs-lookup"><span data-stu-id="86704-106">To save a file using the SaveFileDialog component</span></span>

- <span data-ttu-id="86704-107">Visualizzare la finestra di dialogo **Salva file** e chiamare un metodo per salvare il file selezionato dall'utente.</span><span class="sxs-lookup"><span data-stu-id="86704-107">Display the **Save File** dialog box and call a method to save the file selected by the user.</span></span>

  <span data-ttu-id="86704-108">Usare il <xref:System.Windows.Forms.SaveFileDialog> <xref:System.Windows.Forms.SaveFileDialog.OpenFile%2A> metodo del componente per salvare il file.</span><span class="sxs-lookup"><span data-stu-id="86704-108">Use the <xref:System.Windows.Forms.SaveFileDialog> component's <xref:System.Windows.Forms.SaveFileDialog.OpenFile%2A> method to save the file.</span></span> <span data-ttu-id="86704-109">Questo metodo fornisce un <xref:System.IO.Stream> oggetto in cui è possibile scrivere.</span><span class="sxs-lookup"><span data-stu-id="86704-109">This method gives you a <xref:System.IO.Stream> object you can write to.</span></span>

  <span data-ttu-id="86704-110">Nell'esempio seguente viene usata <xref:System.Windows.Forms.DialogResult> la proprietà per ottenere il nome del file e il <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> metodo per salvare il file.</span><span class="sxs-lookup"><span data-stu-id="86704-110">The example below uses the <xref:System.Windows.Forms.DialogResult> property to get the name of the file, and the <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> method to save the file.</span></span> <span data-ttu-id="86704-111">Il <xref:System.Windows.Forms.SaveFileDialog.OpenFile%2A> metodo fornisce un flusso in cui scrivere il file.</span><span class="sxs-lookup"><span data-stu-id="86704-111">The <xref:System.Windows.Forms.SaveFileDialog.OpenFile%2A> method gives you a stream to write the file to.</span></span>

  <span data-ttu-id="86704-112">Nell'esempio seguente è presente un <xref:System.Windows.Forms.Button> controllo a cui è assegnata un'immagine.</span><span class="sxs-lookup"><span data-stu-id="86704-112">In the example below, there is a <xref:System.Windows.Forms.Button> control with an image assigned to it.</span></span> <span data-ttu-id="86704-113">Quando si fa clic sul pulsante, <xref:System.Windows.Forms.SaveFileDialog> viene creata un'istanza di un componente con un filtro che consente di usare file di tipo gif, JPEG e BMP.</span><span class="sxs-lookup"><span data-stu-id="86704-113">When you click the button, a <xref:System.Windows.Forms.SaveFileDialog> component is instantiated with a filter that allows files of type .gif, .jpeg, and .bmp.</span></span> <span data-ttu-id="86704-114">Se si seleziona un file di questo tipo nella finestra di dialogo Salva file, viene salvata l'immagine del pulsante.</span><span class="sxs-lookup"><span data-stu-id="86704-114">If a file of this type is selected in the Save File dialog box, the button's image is saved.</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="86704-115">Per ottenere o impostare la <xref:System.Windows.Forms.FileDialog.FileName%2A> proprietà, l'assembly richiede un livello <xref:System.Security.Permissions.FileIOPermission?displayProperty=nameWithType> di privilegio concesso dalla classe.</span><span class="sxs-lookup"><span data-stu-id="86704-115">To get or set the <xref:System.Windows.Forms.FileDialog.FileName%2A> property, your assembly requires a privilege level granted by the <xref:System.Security.Permissions.FileIOPermission?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="86704-116">Se viene eseguito in un contesto parzialmente attendibile, il processo potrebbe generare un'eccezione a causa di privilegi insufficienti.</span><span class="sxs-lookup"><span data-stu-id="86704-116">If you are running in a partial-trust context, the process might throw an exception due to insufficient privileges.</span></span> <span data-ttu-id="86704-117">Per altre informazioni, vedere [Code Access Security Basics](../../misc/code-access-security-basics.md) (Nozioni di base sulla sicurezza dell'accesso di codice).</span><span class="sxs-lookup"><span data-stu-id="86704-117">For more information, see [Code Access Security Basics](../../misc/code-access-security-basics.md).</span></span>

  <span data-ttu-id="86704-118">Nell'esempio si presuppone che il form <xref:System.Windows.Forms.Button> disponga di un <xref:System.Windows.Forms.ButtonBase.Image%2A> controllo con la proprietà impostata su un file di tipo gif, JPEG o BMP.</span><span class="sxs-lookup"><span data-stu-id="86704-118">The example assumes your form has a <xref:System.Windows.Forms.Button> control with its <xref:System.Windows.Forms.ButtonBase.Image%2A> property set to a file of type .gif, .jpeg, or .bmp.</span></span>

  > [!NOTE]
  > <span data-ttu-id="86704-119">La <xref:System.Windows.Forms.FileDialog> <xref:System.Windows.Forms.FileDialog.FilterIndex%2A> proprietà della classe, che, a causa dell'ereditarietà <xref:System.Windows.Forms.SaveFileDialog> , fa parte della classe, utilizza un indice in base uno.</span><span class="sxs-lookup"><span data-stu-id="86704-119">The <xref:System.Windows.Forms.FileDialog> class's <xref:System.Windows.Forms.FileDialog.FilterIndex%2A> property (which, due to inheritance, is part of the <xref:System.Windows.Forms.SaveFileDialog> class) uses a one-based index.</span></span> <span data-ttu-id="86704-120">caratteristica importante se si scrive codice per salvare i dati in un formato specifico, ad esempio per salvare un file come testo normale invece che in formato binario.</span><span class="sxs-lookup"><span data-stu-id="86704-120">This is important if you are writing code to save data in a specific format (for example, saving a file in plain text versus binary format).</span></span> <span data-ttu-id="86704-121">Questa proprietà è illustrata nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="86704-121">This property is featured in the example below.</span></span>

  ```vb
  Private Sub Button2_Click(ByVal sender As System.Object, _
  ByVal e As System.EventArgs) Handles Button2.Click
      ' Displays a SaveFileDialog so the user can save the Image
      ' assigned to Button2.
      Dim saveFileDialog1 As New SaveFileDialog()
      saveFileDialog1.Filter = "JPeg Image|*.jpg|Bitmap Image|*.bmp|Gif Image|*.gif"
      saveFileDialog1.Title = "Save an Image File"
      saveFileDialog1.ShowDialog()

      ' If the file name is not an empty string open it for saving.
      If saveFileDialog1.FileName <> "" Then
        ' Saves the Image via a FileStream created by the OpenFile method.
        Dim fs As System.IO.FileStream = Ctype _
            (saveFileDialog1.OpenFile(), System.IO.FileStream)
        ' Saves the Image in the appropriate ImageFormat based upon the
        ' file type selected in the dialog box.
        ' NOTE that the FilterIndex property is one-based.
        Select Case saveFileDialog1.FilterIndex
            Case 1
              Me.button2.Image.Save(fs, _
                  System.Drawing.Imaging.ImageFormat.Jpeg)

            Case 2
              Me.button2.Image.Save(fs, _
                  System.Drawing.Imaging.ImageFormat.Bmp)

            Case 3
              Me.button2.Image.Save(fs, _
                  System.Drawing.Imaging.ImageFormat.Gif)
          End Select

          fs.Close()
      End If
  End Sub
  ```

  ```csharp
  private void button2_Click(object sender, System.EventArgs e)
  {
      // Displays a SaveFileDialog so the user can save the Image
      // assigned to Button2.
      SaveFileDialog saveFileDialog1 = new SaveFileDialog();
      saveFileDialog1.Filter = "JPeg Image|*.jpg|Bitmap Image|*.bmp|Gif Image|*.gif";
      saveFileDialog1.Title = "Save an Image File";
      saveFileDialog1.ShowDialog();

      // If the file name is not an empty string open it for saving.
      if(saveFileDialog1.FileName != "")
      {
        // Saves the Image via a FileStream created by the OpenFile method.
        System.IO.FileStream fs =
            (System.IO.FileStream)saveFileDialog1.OpenFile();
        // Saves the Image in the appropriate ImageFormat based upon the
        // File type selected in the dialog box.
        // NOTE that the FilterIndex property is one-based.
        switch(saveFileDialog1.FilterIndex)
        {
            case 1 :
            this.button2.Image.Save(fs,
              System.Drawing.Imaging.ImageFormat.Jpeg);
            break;

            case 2 :
            this.button2.Image.Save(fs,
              System.Drawing.Imaging.ImageFormat.Bmp);
            break;

            case 3 :
            this.button2.Image.Save(fs,
              System.Drawing.Imaging.ImageFormat.Gif);
            break;
        }

      fs.Close();
      }
  }
  ```

  ```cpp
  private:
      System::Void button2_Click(System::Object ^ sender,
        System::EventArgs ^ e)
      {
        // Displays a SaveFileDialog so the user can save the Image
        // assigned to Button2.
        SaveFileDialog ^ saveFileDialog1 = new SaveFileDialog();
        saveFileDialog1->Filter =
            "JPeg Image|*.jpg|Bitmap Image|*.bmp|Gif Image|*.gif";
        saveFileDialog1->Title = "Save an Image File";
        saveFileDialog1->ShowDialog();
        // If the file name is not an empty string, open it for saving.
        if(saveFileDialog1->FileName != "")
        {
            // Saves the Image through a FileStream created by
            // the OpenFile method.
            System::IO::FileStream ^ fs =
              safe_cast\<System::IO::FileStream*>(
              saveFileDialog1->OpenFile());
            // Saves the Image in the appropriate ImageFormat based on
            // the file type selected in the dialog box.
            // Note that the FilterIndex property is one based.
            switch(saveFileDialog1->FilterIndex)
            {
              case 1 :
                  this->button2->Image->Save(fs,
                    System::Drawing::Imaging::ImageFormat::Jpeg);
                  break;
              case 2 :
                  this->button2->Image->Save(fs,
                    System::Drawing::Imaging::ImageFormat::Bmp);
                  break;
              case 3 :
                  this->button2->Image->Save(fs,
                    System::Drawing::Imaging::ImageFormat::Gif);
                  break;
            }
        fs->Close();
        }
      }
  ```

  <span data-ttu-id="86704-122">(Visual C# e Visual C++) Inserire il codice seguente nel costruttore del form per registrare il gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="86704-122">(Visual C# and Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>

  ```csharp
  this.button2.Click += new System.EventHandler(this.button2_Click);
  ```

  ```cpp
  this->button2->Click += gcnew
      System::EventHandler(this, &Form1::button2_Click);
  ```

  <span data-ttu-id="86704-123">Per ulteriori informazioni sulla scrittura di flussi di file <xref:System.IO.FileStream.BeginWrite%2A> , <xref:System.IO.FileStream.Write%2A>vedere e.</span><span class="sxs-lookup"><span data-stu-id="86704-123">For more information about writing file streams, see <xref:System.IO.FileStream.BeginWrite%2A> and <xref:System.IO.FileStream.Write%2A>.</span></span>

  > [!NOTE]
  > <span data-ttu-id="86704-124">Alcuni controlli, ad esempio il <xref:System.Windows.Forms.RichTextBox> controllo, hanno la possibilità di salvare i file.</span><span class="sxs-lookup"><span data-stu-id="86704-124">Certain controls, such as the <xref:System.Windows.Forms.RichTextBox> control, have the ability to save files.</span></span> <span data-ttu-id="86704-125">Per altre informazioni, vedere la sezione relativa al componente SaveFileDialog dell'articolo tecnico di MSDN Online Library [Essential Code for Windows Forms Dialog Boxes](https://go.microsoft.com/fwlink/?LinkID=102575) (Codice di base per le finestre di dialogo di Windows Form).</span><span class="sxs-lookup"><span data-stu-id="86704-125">For more information, see the "SaveFileDialog Component" section of the MSDN Online Library technical article, [Essential Code for Windows Forms Dialog Boxes](https://go.microsoft.com/fwlink/?LinkID=102575).</span></span>

## <a name="see-also"></a><span data-ttu-id="86704-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="86704-126">See also</span></span>

- <xref:System.Windows.Forms.SaveFileDialog>
- [<span data-ttu-id="86704-127">Componente SaveFileDialog</span><span class="sxs-lookup"><span data-stu-id="86704-127">SaveFileDialog Component</span></span>](savefiledialog-component-windows-forms.md)

---
title: 'Procedura: Salvare file con il componente SaveFileDialog'
description: Informazioni su come usare il componente SaveFileDialog per esplorare il file system e selezionare i file da salvare.
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
ms.openlocfilehash: cd773c3d4aa2b907eb09dd87c3fdbe138bf533bb
ms.sourcegitcommit: 3824ff187947572b274b9715b60c11269335c181
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/17/2020
ms.locfileid: "84904403"
---
# <a name="how-to-save-files-using-the-savefiledialog-component"></a><span data-ttu-id="9b9a6-103">Procedura: Salvare file con il componente SaveFileDialog</span><span class="sxs-lookup"><span data-stu-id="9b9a6-103">How to: Save Files Using the SaveFileDialog Component</span></span>

<span data-ttu-id="9b9a6-104">Il <xref:System.Windows.Forms.SaveFileDialog> componente consente agli utenti di esplorare il file System e selezionare i file da salvare.</span><span class="sxs-lookup"><span data-stu-id="9b9a6-104">The <xref:System.Windows.Forms.SaveFileDialog> component allows users to browse the file system and select files to be saved.</span></span> <span data-ttu-id="9b9a6-105">Nella finestra di dialogo vengono restituiti il percorso e il nome del file selezionato dall'utente.</span><span class="sxs-lookup"><span data-stu-id="9b9a6-105">The dialog box returns the path and name of the file the user has selected in the dialog box.</span></span> <span data-ttu-id="9b9a6-106">Tuttavia, è necessario scrivere il codice per salvare effettivamente i file sul disco.</span><span class="sxs-lookup"><span data-stu-id="9b9a6-106">However, you must write the code to actually write the files to disk.</span></span>

### <a name="to-save-a-file-using-the-savefiledialog-component"></a><span data-ttu-id="9b9a6-107">Per salvare un file tramite il componente SaveFileDialog</span><span class="sxs-lookup"><span data-stu-id="9b9a6-107">To save a file using the SaveFileDialog component</span></span>

- <span data-ttu-id="9b9a6-108">Visualizzare la finestra di dialogo **Salva file** e chiamare un metodo per salvare il file selezionato dall'utente.</span><span class="sxs-lookup"><span data-stu-id="9b9a6-108">Display the **Save File** dialog box and call a method to save the file selected by the user.</span></span>

  <span data-ttu-id="9b9a6-109">Usare il <xref:System.Windows.Forms.SaveFileDialog> metodo del componente <xref:System.Windows.Forms.SaveFileDialog.OpenFile%2A> per salvare il file.</span><span class="sxs-lookup"><span data-stu-id="9b9a6-109">Use the <xref:System.Windows.Forms.SaveFileDialog> component's <xref:System.Windows.Forms.SaveFileDialog.OpenFile%2A> method to save the file.</span></span> <span data-ttu-id="9b9a6-110">Questo metodo fornisce un <xref:System.IO.Stream> oggetto in cui è possibile scrivere.</span><span class="sxs-lookup"><span data-stu-id="9b9a6-110">This method gives you a <xref:System.IO.Stream> object you can write to.</span></span>

  <span data-ttu-id="9b9a6-111">Nell'esempio seguente viene usata la <xref:System.Windows.Forms.DialogResult> proprietà per ottenere il nome del file e il <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> metodo per salvare il file.</span><span class="sxs-lookup"><span data-stu-id="9b9a6-111">The example below uses the <xref:System.Windows.Forms.DialogResult> property to get the name of the file, and the <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> method to save the file.</span></span> <span data-ttu-id="9b9a6-112">Il <xref:System.Windows.Forms.SaveFileDialog.OpenFile%2A> metodo fornisce un flusso in cui scrivere il file.</span><span class="sxs-lookup"><span data-stu-id="9b9a6-112">The <xref:System.Windows.Forms.SaveFileDialog.OpenFile%2A> method gives you a stream to write the file to.</span></span>

  <span data-ttu-id="9b9a6-113">Nell'esempio seguente è presente un controllo a cui è <xref:System.Windows.Forms.Button> assegnata un'immagine.</span><span class="sxs-lookup"><span data-stu-id="9b9a6-113">In the example below, there is a <xref:System.Windows.Forms.Button> control with an image assigned to it.</span></span> <span data-ttu-id="9b9a6-114">Quando si fa clic sul pulsante, <xref:System.Windows.Forms.SaveFileDialog> viene creata un'istanza di un componente con un filtro che consente di usare file di tipo gif, JPEG e BMP.</span><span class="sxs-lookup"><span data-stu-id="9b9a6-114">When you click the button, a <xref:System.Windows.Forms.SaveFileDialog> component is instantiated with a filter that allows files of type .gif, .jpeg, and .bmp.</span></span> <span data-ttu-id="9b9a6-115">Se si seleziona un file di questo tipo nella finestra di dialogo Salva file, viene salvata l'immagine del pulsante.</span><span class="sxs-lookup"><span data-stu-id="9b9a6-115">If a file of this type is selected in the Save File dialog box, the button's image is saved.</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="9b9a6-116">Per ottenere o impostare la <xref:System.Windows.Forms.FileDialog.FileName%2A> proprietà, l'assembly richiede un livello di privilegio concesso dalla <xref:System.Security.Permissions.FileIOPermission?displayProperty=nameWithType> classe.</span><span class="sxs-lookup"><span data-stu-id="9b9a6-116">To get or set the <xref:System.Windows.Forms.FileDialog.FileName%2A> property, your assembly requires a privilege level granted by the <xref:System.Security.Permissions.FileIOPermission?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="9b9a6-117">Se viene eseguito in un contesto parzialmente attendibile, il processo potrebbe generare un'eccezione a causa di privilegi insufficienti.</span><span class="sxs-lookup"><span data-stu-id="9b9a6-117">If you are running in a partial-trust context, the process might throw an exception due to insufficient privileges.</span></span> <span data-ttu-id="9b9a6-118">Per altre informazioni, vedere [Code Access Security Basics](../../misc/code-access-security-basics.md) (Nozioni di base sulla sicurezza dell'accesso di codice).</span><span class="sxs-lookup"><span data-stu-id="9b9a6-118">For more information, see [Code Access Security Basics](../../misc/code-access-security-basics.md).</span></span>

  <span data-ttu-id="9b9a6-119">Nell'esempio si presuppone che il form disponga di un <xref:System.Windows.Forms.Button> controllo con la <xref:System.Windows.Forms.ButtonBase.Image%2A> proprietà impostata su un file di tipo gif, JPEG o BMP.</span><span class="sxs-lookup"><span data-stu-id="9b9a6-119">The example assumes your form has a <xref:System.Windows.Forms.Button> control with its <xref:System.Windows.Forms.ButtonBase.Image%2A> property set to a file of type .gif, .jpeg, or .bmp.</span></span>

  > [!NOTE]
  > <span data-ttu-id="9b9a6-120">La <xref:System.Windows.Forms.FileDialog> proprietà della classe, <xref:System.Windows.Forms.FileDialog.FilterIndex%2A> che, a causa dell'ereditarietà, fa parte della <xref:System.Windows.Forms.SaveFileDialog> classe, utilizza un indice in base uno.</span><span class="sxs-lookup"><span data-stu-id="9b9a6-120">The <xref:System.Windows.Forms.FileDialog> class's <xref:System.Windows.Forms.FileDialog.FilterIndex%2A> property (which, due to inheritance, is part of the <xref:System.Windows.Forms.SaveFileDialog> class) uses a one-based index.</span></span> <span data-ttu-id="9b9a6-121">caratteristica importante se si scrive codice per salvare i dati in un formato specifico, ad esempio per salvare un file come testo normale invece che in formato binario.</span><span class="sxs-lookup"><span data-stu-id="9b9a6-121">This is important if you are writing code to save data in a specific format (for example, saving a file in plain text versus binary format).</span></span> <span data-ttu-id="9b9a6-122">Questa proprietà è illustrata nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="9b9a6-122">This property is featured in the example below.</span></span>

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

  <span data-ttu-id="9b9a6-123">(Visual C# e Visual C++) Inserire il codice seguente nel costruttore del form per registrare il gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="9b9a6-123">(Visual C# and Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>

  ```csharp
  this.button2.Click += new System.EventHandler(this.button2_Click);
  ```

  ```cpp
  this->button2->Click += gcnew
      System::EventHandler(this, &Form1::button2_Click);
  ```

  <span data-ttu-id="9b9a6-124">Per ulteriori informazioni sulla scrittura di flussi di file, vedere <xref:System.IO.FileStream.BeginWrite%2A> e <xref:System.IO.FileStream.Write%2A> .</span><span class="sxs-lookup"><span data-stu-id="9b9a6-124">For more information about writing file streams, see <xref:System.IO.FileStream.BeginWrite%2A> and <xref:System.IO.FileStream.Write%2A>.</span></span>

  > [!NOTE]
  > <span data-ttu-id="9b9a6-125">Alcuni controlli, ad esempio il <xref:System.Windows.Forms.RichTextBox> controllo, hanno la possibilità di salvare i file.</span><span class="sxs-lookup"><span data-stu-id="9b9a6-125">Certain controls, such as the <xref:System.Windows.Forms.RichTextBox> control, have the ability to save files.</span></span>

## <a name="see-also"></a><span data-ttu-id="9b9a6-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9b9a6-126">See also</span></span>

- <xref:System.Windows.Forms.SaveFileDialog>
- [<span data-ttu-id="9b9a6-127">Componente SaveFileDialog</span><span class="sxs-lookup"><span data-stu-id="9b9a6-127">SaveFileDialog Component</span></span>](savefiledialog-component-windows-forms.md)

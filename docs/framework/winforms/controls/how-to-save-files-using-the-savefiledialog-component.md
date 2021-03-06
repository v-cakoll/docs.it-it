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
# <a name="how-to-save-files-using-the-savefiledialog-component"></a>Procedura: Salvare file con il componente SaveFileDialog

Il <xref:System.Windows.Forms.SaveFileDialog> componente consente agli utenti di esplorare il file System e selezionare i file da salvare. Nella finestra di dialogo vengono restituiti il percorso e il nome del file selezionato dall'utente. Tuttavia, è necessario scrivere il codice per salvare effettivamente i file sul disco.

### <a name="to-save-a-file-using-the-savefiledialog-component"></a>Per salvare un file tramite il componente SaveFileDialog

- Visualizzare la finestra di dialogo **Salva file** e chiamare un metodo per salvare il file selezionato dall'utente.

  Usare il <xref:System.Windows.Forms.SaveFileDialog> metodo del componente <xref:System.Windows.Forms.SaveFileDialog.OpenFile%2A> per salvare il file. Questo metodo fornisce un <xref:System.IO.Stream> oggetto in cui è possibile scrivere.

  Nell'esempio seguente viene usata la <xref:System.Windows.Forms.DialogResult> proprietà per ottenere il nome del file e il <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> metodo per salvare il file. Il <xref:System.Windows.Forms.SaveFileDialog.OpenFile%2A> metodo fornisce un flusso in cui scrivere il file.

  Nell'esempio seguente è presente un controllo a cui è <xref:System.Windows.Forms.Button> assegnata un'immagine. Quando si fa clic sul pulsante, <xref:System.Windows.Forms.SaveFileDialog> viene creata un'istanza di un componente con un filtro che consente di usare file di tipo gif, JPEG e BMP. Se si seleziona un file di questo tipo nella finestra di dialogo Salva file, viene salvata l'immagine del pulsante.

  > [!IMPORTANT]
  > Per ottenere o impostare la <xref:System.Windows.Forms.FileDialog.FileName%2A> proprietà, l'assembly richiede un livello di privilegio concesso dalla <xref:System.Security.Permissions.FileIOPermission?displayProperty=nameWithType> classe. Se viene eseguito in un contesto parzialmente attendibile, il processo potrebbe generare un'eccezione a causa di privilegi insufficienti. Per altre informazioni, vedere [Code Access Security Basics](../../misc/code-access-security-basics.md) (Nozioni di base sulla sicurezza dell'accesso di codice).

  Nell'esempio si presuppone che il form disponga di un <xref:System.Windows.Forms.Button> controllo con la <xref:System.Windows.Forms.ButtonBase.Image%2A> proprietà impostata su un file di tipo gif, JPEG o BMP.

  > [!NOTE]
  > La <xref:System.Windows.Forms.FileDialog> proprietà della classe, <xref:System.Windows.Forms.FileDialog.FilterIndex%2A> che, a causa dell'ereditarietà, fa parte della <xref:System.Windows.Forms.SaveFileDialog> classe, utilizza un indice in base uno. caratteristica importante se si scrive codice per salvare i dati in un formato specifico, ad esempio per salvare un file come testo normale invece che in formato binario. Questa proprietà è illustrata nell'esempio seguente.

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

  (Visual C# e Visual C++) Inserire il codice seguente nel costruttore del form per registrare il gestore eventi.

  ```csharp
  this.button2.Click += new System.EventHandler(this.button2_Click);
  ```

  ```cpp
  this->button2->Click += gcnew
      System::EventHandler(this, &Form1::button2_Click);
  ```

  Per ulteriori informazioni sulla scrittura di flussi di file, vedere <xref:System.IO.FileStream.BeginWrite%2A> e <xref:System.IO.FileStream.Write%2A> .

  > [!NOTE]
  > Alcuni controlli, ad esempio il <xref:System.Windows.Forms.RichTextBox> controllo, hanno la possibilità di salvare i file.

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.SaveFileDialog>
- [Componente SaveFileDialog](savefiledialog-component-windows-forms.md)

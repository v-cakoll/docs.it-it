---
title: 'Procedura: Aprire i file con il componente OpenFileDialog'
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
ms.openlocfilehash: 87e7640da76205341b9e95310314800ac9dbfe30
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54678811"
---
# <a name="how-to-open-files-using-the-openfiledialog-component"></a>Procedura: Aprire i file con il componente OpenFileDialog
Il <xref:System.Windows.Forms.OpenFileDialog> componente consente agli utenti di sfogliare le cartelle del proprio computer o di qualsiasi computer nella rete e selezionare uno o più file da aprire. Nella finestra di dialogo vengono restituiti il percorso e il nome del file selezionato dall'utente.  
  
 Dopo avere selezionato il file da aprire, è possibile procedere all'apertura in due modi. Se si preferisce usare flussi di file, è possibile creare un'istanza di <xref:System.IO.StreamReader> classe. In alternativa, è possibile usare il <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> metodo per aprire il file selezionato.  
  
 Il primo esempio riportato di seguito implica un <xref:System.Security.Permissions.FileIOPermission> verifica delle autorizzazioni (come descritto nella "Nota sulla protezione" riportata di seguito), ma è possibile accedere al nome del file. Questa tecnica può essere usata dal computer locale, dalla rete Intranet e da Internet. Il secondo metodo esegue anche un <xref:System.Security.Permissions.FileIOPermission> verifica delle autorizzazioni, ma è più adatto per le applicazioni nelle zone Intranet o Internet.  
  
### <a name="to-open-a-file-as-a-stream-using-the-openfiledialog-component"></a>Per aprire un file come flusso tramite il componente OpenFileDialog  
  
1.  Visualizzare la finestra di dialogo **Apri file** e chiamare un metodo per aprire il file selezionato dall'utente.  
  
     Un approccio consiste nell'usare la <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> metodo per visualizzare la finestra di dialogo Apri File e usare un'istanza del <xref:System.IO.StreamReader> classe per aprire il file.  
  
     L'esempio seguente usa il <xref:System.Windows.Forms.Button> del controllo <xref:System.Windows.Forms.Control.Click> gestore dell'evento per aprire un'istanza del <xref:System.Windows.Forms.OpenFileDialog> componente. Quando viene scelto un file e l'utente fa clic su **OK**, il file selezionato nella finestra di dialogo viene aperto. In questo caso, il contenuto viene visualizzato in una finestra di messaggio per indicare che il flusso di file è stato letto.  
  
    > [!IMPORTANT]
    >  Per ottenere o impostare il <xref:System.Windows.Forms.FileDialog.FileName%2A> proprietà, l'assembly richiede un livello di privilegio concesso dal <xref:System.Security.Permissions.FileIOPermission?displayProperty=nameWithType> classe. Se viene eseguito in un contesto parzialmente attendibile, il processo potrebbe generare un'eccezione a causa di privilegi insufficienti. Per altre informazioni, vedere [Code Access Security Basics](../../../../docs/framework/misc/code-access-security-basics.md) (Nozioni di base sulla sicurezza dell'accesso di codice).  
  
     L'esempio presuppone che il form contenga un <xref:System.Windows.Forms.Button> controllo e un <xref:System.Windows.Forms.OpenFileDialog> componente.  
  
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
  
     (Visual c# e [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) inserire il codice seguente nel costruttore del form per registrare il gestore dell'evento.  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->button1->Click += gcnew  
       System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
    > [!NOTE]
    >  Per altre informazioni sulla lettura da flussi di file, vedere <xref:System.IO.FileStream.BeginRead%2A> e <xref:System.IO.FileStream.Read%2A>.  
  
### <a name="to-open-a-file-as-a-file-using-the-openfiledialog-component"></a>Per aprire un file come file tramite il componente OpenFileDialog  
  
1.  Usare la <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> metodo per visualizzare la finestra di dialogo e <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> metodo per aprire il file.  
  
     Il <xref:System.Windows.Forms.OpenFileDialog> del componente <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> metodo restituisce i byte che compongono il file. e che forniscono un flusso da cui leggere. Nell'esempio seguente, un' <xref:System.Windows.Forms.OpenFileDialog> componente viene creata un'istanza con un filtro "cursore" su di esso, per consentire all'utente di scegliere solo i file con l'estensione`.cur`. Se si sceglie un file `.cur`, il cursore del form viene impostato sul cursore selezionato.  
  
    > [!IMPORTANT]
    >  Per chiamare il <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> metodo, l'assembly richiede un livello di privilegio concesso dal <xref:System.Security.Permissions.FileIOPermission?displayProperty=nameWithType> classe. Se viene eseguito in un contesto parzialmente attendibile, il processo potrebbe generare un'eccezione a causa di privilegi insufficienti. Per altre informazioni, vedere [Code Access Security Basics](../../../../docs/framework/misc/code-access-security-basics.md) (Nozioni di base sulla sicurezza dell'accesso di codice).  
  
     L'esempio presuppone che il form contenga un <xref:System.Windows.Forms.Button> controllo.  
  
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
  
     (Visual c# e [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) inserire il codice seguente nel costruttore del form per registrare il gestore dell'evento.  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->button1->Click += gcnew  
       System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Windows.Forms.OpenFileDialog>
- [Componente OpenFileDialog](../../../../docs/framework/winforms/controls/openfiledialog-component-windows-forms.md)

---
title: 'Procedura: Scegliere cartelle con il componente FolderBrowserDialog di Windows Form'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- directories [Windows Forms], choosing
- FolderBrowserDialog component [Windows Forms], choosing directories
- folders [Windows Forms], selecting
- folders [Windows Forms], choosing
- directories [Windows Forms], selecting
ms.assetid: 4593670e-7c7d-4661-b46b-4ffb63258adb
ms.openlocfilehash: 7055875f25aa0f39feb2d944f4b6684c6ae5d9a5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54614693"
---
# <a name="how-to-choose-folders-with-the-windows-forms-folderbrowserdialog-component"></a>Procedura: Scegliere cartelle con il componente FolderBrowserDialog di Windows Form
Spesso nelle applicazioni Windows create è necessario chiedere agli utenti di selezionare una cartella, nella maggior parte dei casi per salvare un insieme di file. I moduli di Windows <xref:System.Windows.Forms.FolderBrowserDialog> componente consente di eseguire facilmente questa operazione.  
  
### <a name="to-choose-folders-with-the-folderbrowserdialog-component"></a>Per scegliere cartelle con il componente FolderBrowserDialog  
  
1.  In una routine, controllare la <xref:System.Windows.Forms.FolderBrowserDialog> del componente <xref:System.Windows.Forms.Form.DialogResult%2A> per vedere come è stata chiusa la finestra di dialogo e ottenere il valore della proprietà il <xref:System.Windows.Forms.FolderBrowserDialog> componente <xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A> proprietà.  
  
2.  Se è necessario per la cartella di set di livello superiore che verrà visualizzato all'interno della visualizzazione struttura ad albero della finestra di dialogo, impostare il <xref:System.Windows.Forms.FolderBrowserDialog.RootFolder%2A> proprietà, che accetta un membro del <xref:System.Environment.SpecialFolder> enumerazione.  
  
3.  Inoltre, è possibile impostare il <xref:System.Windows.Forms.FolderBrowserDialog.Description%2A> proprietà che specifica la stringa di testo viene visualizzato nella parte superiore della visualizzazione albero del visualizzatore cartelle.  
  
     Nell'esempio seguente, il <xref:System.Windows.Forms.FolderBrowserDialog> componente viene usato per selezionare una cartella, simile a quando si crea un progetto in Visual Studio e viene richiesto di selezionare una cartella in cui salvarlo. In questo esempio, il nome della cartella viene quindi visualizzato un <xref:System.Windows.Forms.TextBox> controllo nel form. È consigliabile specificare la posizione in un'area modificabile, ad esempio un <xref:System.Windows.Forms.TextBox> controllo, in modo che gli utenti possano modificare la selezione in caso di errore o altri problemi. Questo esempio si presuppone un form con un <xref:System.Windows.Forms.FolderBrowserDialog> componenti e una <xref:System.Windows.Forms.TextBox> controllo.  
  
    ```vb  
    Public Sub ChooseFolder()  
        If FolderBrowserDialog1.ShowDialog() = DialogResult.OK Then  
            TextBox1.Text = FolderBrowserDialog1.SelectedPath  
        End If  
    End Sub  
    ```  
  
    ```csharp  
    public void ChooseFolder()  
    {  
        if (folderBrowserDialog1.ShowDialog() == DialogResult.OK)   
        {  
            textBox1.Text = folderBrowserDialog1.SelectedPath;  
        }  
    }  
    ```  
  
    ```cpp  
    public:  
       void ChooseFolder()  
       {  
          if (folderBrowserDialog1->ShowDialog() == DialogResult::OK)  
          {  
             textBox1->Text = folderBrowserDialog1->SelectedPath;  
          }  
       }  
    ```  
  
    > [!IMPORTANT]
    >  Per usare questa classe, l'assembly richiede un livello di privilegio concesso dal <xref:System.Security.Permissions.FileIOPermissionAttribute.PathDiscovery%2A> proprietà, che fa parte di <xref:System.Security.Permissions.FileIOPermissionAccess> enumerazione. Se l'esecuzione avviene in un contesto parzialmente attendibile, è possibile che il processo generi un'eccezione dovuta a privilegi insufficienti. Per altre informazioni, vedere [Code Access Security Basics](../../../../docs/framework/misc/code-access-security-basics.md) (Nozioni di base sulla sicurezza dell'accesso di codice).  
  
 Per informazioni su come salvare i file, vedere [come: Salvare i file con il componente SaveFileDialog](../../../../docs/framework/winforms/controls/how-to-save-files-using-the-savefiledialog-component.md).  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Windows.Forms.FolderBrowserDialog>
- [Cenni preliminari sul componente FolderBrowserDialog (Windows Form)](../../../../docs/framework/winforms/controls/folderbrowserdialog-component-overview-windows-forms.md)
- [Componente FolderBrowserDialog](../../../../docs/framework/winforms/controls/folderbrowserdialog-component-windows-forms.md)

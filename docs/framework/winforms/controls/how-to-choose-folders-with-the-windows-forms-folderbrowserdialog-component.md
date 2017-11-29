---
title: 'Procedura: Scegliere cartelle con il componente FolderBrowserDialog di Windows Form'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0824fb70fa67628326af38ff7fb5e6c097a0378c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-choose-folders-with-the-windows-forms-folderbrowserdialog-component"></a>Procedura: Scegliere cartelle con il componente FolderBrowserDialog di Windows Form
Spesso nelle applicazioni Windows create è necessario chiedere agli utenti di selezionare una cartella, nella maggior parte dei casi per salvare un insieme di file. Windows Form <xref:System.Windows.Forms.FolderBrowserDialog> componente consente di eseguire facilmente questa attività.  
  
### <a name="to-choose-folders-with-the-folderbrowserdialog-component"></a>Per scegliere cartelle con il componente FolderBrowserDialog  
  
1.  In una routine, controllare il <xref:System.Windows.Forms.FolderBrowserDialog> del componente <xref:System.Windows.Forms.Form.DialogResult%2A> come è stata chiusa la finestra di dialogo e ottenere il valore della proprietà di <xref:System.Windows.Forms.FolderBrowserDialog> del componente <xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A> proprietà.  
  
2.  Se è necessario nella cartella set di primo livello che verrà visualizzato all'interno della visualizzazione albero nella finestra di dialogo, impostare il <xref:System.Windows.Forms.FolderBrowserDialog.RootFolder%2A> proprietà, che accetta un membro del <xref:System.Environment.SpecialFolder> enumerazione.  
  
3.  Inoltre, è possibile impostare il <xref:System.Windows.Forms.FolderBrowserDialog.Description%2A> proprietà che specifica la stringa di testo viene visualizzato nella parte superiore della visualizzazione albero del visualizzatore cartelle.  
  
     Nell'esempio seguente, il <xref:System.Windows.Forms.FolderBrowserDialog> componente viene utilizzato per selezionare una cartella, simile a quando si crea un progetto in Visual Studio e viene richiesto di selezionare una cartella in cui salvarlo. In questo esempio viene quindi visualizzato il nome della cartella un <xref:System.Windows.Forms.TextBox> controllo nel form. È consigliabile specificare la posizione in un'area modificabile, ad esempio un <xref:System.Windows.Forms.TextBox> controllare, in modo che gli utenti possano modificare la selezione in caso di errore o altri problemi. Questo esempio si presuppone un form con un <xref:System.Windows.Forms.FolderBrowserDialog> componente e un <xref:System.Windows.Forms.TextBox> controllo.  
  
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
    >  Per utilizzare questa classe, l'assembly richiede un livello di privilegio concesso per il <xref:System.Security.Permissions.FileIOPermissionAttribute.PathDiscovery%2A> proprietà, che fa parte di <xref:System.Security.Permissions.FileIOPermissionAccess> enumerazione. Se l'esecuzione avviene in un contesto parzialmente attendibile, è possibile che il processo generi un'eccezione dovuta a privilegi insufficienti. Per altre informazioni, vedere [Code Access Security Basics](../../../../docs/framework/misc/code-access-security-basics.md) (Nozioni di base sulla sicurezza dell'accesso di codice).  
  
 Per informazioni sul salvataggio dei file, vedere [Procedura: Salvare file con il componente SaveFileDialog](../../../../docs/framework/winforms/controls/how-to-save-files-using-the-savefiledialog-component.md).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.FolderBrowserDialog>  
 [Cenni preliminari sul componente FolderBrowserDialog (Windows Form)](../../../../docs/framework/winforms/controls/folderbrowserdialog-component-overview-windows-forms.md)  
 [Componente FolderBrowserDialog](../../../../docs/framework/winforms/controls/folderbrowserdialog-component-windows-forms.md)

---
title: 'Procedura: Scegliere cartelle con il componente FolderBrowserDialog di Windows Forms'
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
ms.openlocfilehash: fc19ea466f535f783d3b0537a973ce41c223902d
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2019
ms.locfileid: "70046126"
---
# <a name="how-to-choose-folders-with-the-windows-forms-folderbrowserdialog-component"></a>Procedura: Scegliere cartelle con il componente FolderBrowserDialog di Windows Forms

Spesso nelle applicazioni Windows create è necessario chiedere agli utenti di selezionare una cartella, nella maggior parte dei casi per salvare un insieme di file. Il componente <xref:System.Windows.Forms.FolderBrowserDialog> Windows Forms consente di eseguire facilmente questa operazione.

### <a name="to-choose-folders-with-the-folderbrowserdialog-component"></a>Per scegliere cartelle con il componente FolderBrowserDialog

1. In una procedura, controllare la <xref:System.Windows.Forms.FolderBrowserDialog> <xref:System.Windows.Forms.Form.DialogResult%2A> proprietà del componente per vedere come la finestra di dialogo è stata chiusa e <xref:System.Windows.Forms.FolderBrowserDialog> ottenere il <xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A> valore della proprietà del componente.

2. Se è necessario impostare la cartella di primo livello che verrà visualizzata nella visualizzazione albero della finestra di dialogo, impostare la <xref:System.Windows.Forms.FolderBrowserDialog.RootFolder%2A> proprietà che accetta un membro <xref:System.Environment.SpecialFolder> dell'enumerazione.

3. Inoltre, è possibile impostare la <xref:System.Windows.Forms.FolderBrowserDialog.Description%2A> proprietà, che specifica la stringa di testo visualizzata nella parte superiore della visualizzazione albero del browser delle cartelle.

    Nell'esempio seguente il <xref:System.Windows.Forms.FolderBrowserDialog> componente viene usato per selezionare una cartella, in modo simile a quando si crea un progetto in Visual Studio e viene richiesto di selezionare una cartella in cui salvarlo. In questo esempio, il nome della cartella viene quindi visualizzato in <xref:System.Windows.Forms.TextBox> un controllo nel form. È consigliabile posizionare il percorso in un'area modificabile, ad esempio un <xref:System.Windows.Forms.TextBox> controllo, in modo che gli utenti possano modificare la selezione in caso di errore o di altri problemi. In questo esempio si presuppone un form <xref:System.Windows.Forms.FolderBrowserDialog> con un componente <xref:System.Windows.Forms.TextBox> e un controllo.

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
    > Per usare questa classe, l'assembly richiede un livello <xref:System.Security.Permissions.FileIOPermissionAttribute.PathDiscovery%2A> <xref:System.Security.Permissions.FileIOPermissionAccess> di privilegio concesso dalla proprietà, che fa parte dell'enumerazione. Se l'esecuzione avviene in un contesto parzialmente attendibile, è possibile che il processo generi un'eccezione dovuta a privilegi insufficienti. Per altre informazioni, vedere [Code Access Security Basics](../../misc/code-access-security-basics.md) (Nozioni di base sulla sicurezza dell'accesso di codice).

Per informazioni su come salvare i file, vedere [procedura: Salvare i file utilizzando il componente](how-to-save-files-using-the-savefiledialog-component.md)SaveFileDialog.

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.FolderBrowserDialog>
- [Cenni preliminari sul componente FolderBrowserDialog (Windows Form)](folderbrowserdialog-component-overview-windows-forms.md)
- [Componente FolderBrowserDialog](folderbrowserdialog-component-windows-forms.md)

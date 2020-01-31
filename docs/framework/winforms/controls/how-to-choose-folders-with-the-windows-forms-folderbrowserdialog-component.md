---
title: Scegliere le cartelle con il componente FolderBrowserDialog
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
ms.openlocfilehash: 313388442101f341cfed366143f3c9669fb45cbd
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742237"
---
# <a name="how-to-choose-folders-with-the-windows-forms-folderbrowserdialog-component"></a>Procedura: Scegliere cartelle con il componente FolderBrowserDialog di Windows Form

Spesso nelle applicazioni Windows create è necessario chiedere agli utenti di selezionare una cartella, nella maggior parte dei casi per salvare un insieme di file. Il componente Windows Forms <xref:System.Windows.Forms.FolderBrowserDialog> consente di eseguire facilmente questa operazione.

### <a name="to-choose-folders-with-the-folderbrowserdialog-component"></a>Per scegliere cartelle con il componente FolderBrowserDialog

1. In una procedura, controllare la proprietà <xref:System.Windows.Forms.Form.DialogResult%2A> del componente <xref:System.Windows.Forms.FolderBrowserDialog> per vedere come la finestra di dialogo è stata chiusa e ottenere il valore della proprietà <xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A> del componente <xref:System.Windows.Forms.FolderBrowserDialog>.

2. Se è necessario impostare la cartella di primo livello che verrà visualizzata nella visualizzazione albero della finestra di dialogo, impostare la proprietà <xref:System.Windows.Forms.FolderBrowserDialog.RootFolder%2A>, che accetta un membro dell'enumerazione <xref:System.Environment.SpecialFolder>.

3. Inoltre, è possibile impostare la proprietà <xref:System.Windows.Forms.FolderBrowserDialog.Description%2A>, che specifica la stringa di testo visualizzata nella parte superiore della visualizzazione albero del browser delle cartelle.

    Nell'esempio seguente il componente <xref:System.Windows.Forms.FolderBrowserDialog> viene usato per selezionare una cartella, in modo simile a quando si crea un progetto in Visual Studio e viene richiesto di selezionare una cartella in cui salvarlo. In questo esempio, il nome della cartella viene quindi visualizzato in un controllo <xref:System.Windows.Forms.TextBox> sul form. È consigliabile posizionare il percorso in un'area modificabile, ad esempio un controllo <xref:System.Windows.Forms.TextBox>, in modo che gli utenti possano modificare la selezione in caso di errore o di altri problemi. In questo esempio si presuppone un modulo con un componente <xref:System.Windows.Forms.FolderBrowserDialog> e un controllo <xref:System.Windows.Forms.TextBox>.

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
    > Per usare questa classe, l'assembly richiede un livello di privilegio concesso dalla proprietà <xref:System.Security.Permissions.FileIOPermissionAttribute.PathDiscovery%2A>, che fa parte dell'enumerazione <xref:System.Security.Permissions.FileIOPermissionAccess>. Se l'esecuzione avviene in un contesto parzialmente attendibile, è possibile che il processo generi un'eccezione dovuta a privilegi insufficienti. Per altre informazioni, vedere [Code Access Security Basics](../../misc/code-access-security-basics.md) (Nozioni di base sulla sicurezza dell'accesso di codice).

Per informazioni sul salvataggio dei file, vedere [Procedura: Salvare file con il componente SaveFileDialog](how-to-save-files-using-the-savefiledialog-component.md).

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.FolderBrowserDialog>
- [Cenni preliminari sul componente FolderBrowserDialog (Windows Form)](folderbrowserdialog-component-overview-windows-forms.md)
- [Componente FolderBrowserDialog](folderbrowserdialog-component-windows-forms.md)

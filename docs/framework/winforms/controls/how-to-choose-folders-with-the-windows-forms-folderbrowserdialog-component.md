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
# <a name="how-to-choose-folders-with-the-windows-forms-folderbrowserdialog-component"></a><span data-ttu-id="45aa1-102">Procedura: Scegliere cartelle con il componente FolderBrowserDialog di Windows Forms</span><span class="sxs-lookup"><span data-stu-id="45aa1-102">How to: Choose Folders with the Windows Forms FolderBrowserDialog Component</span></span>

<span data-ttu-id="45aa1-103">Spesso nelle applicazioni Windows create è necessario chiedere agli utenti di selezionare una cartella, nella maggior parte dei casi per salvare un insieme di file.</span><span class="sxs-lookup"><span data-stu-id="45aa1-103">Often, within Windows applications you create, you will have to prompt users to select a folder, most frequently to save a set of files.</span></span> <span data-ttu-id="45aa1-104">Il componente <xref:System.Windows.Forms.FolderBrowserDialog> Windows Forms consente di eseguire facilmente questa operazione.</span><span class="sxs-lookup"><span data-stu-id="45aa1-104">The Windows Forms <xref:System.Windows.Forms.FolderBrowserDialog> component allows you to easily accomplish this task.</span></span>

### <a name="to-choose-folders-with-the-folderbrowserdialog-component"></a><span data-ttu-id="45aa1-105">Per scegliere cartelle con il componente FolderBrowserDialog</span><span class="sxs-lookup"><span data-stu-id="45aa1-105">To choose folders with the FolderBrowserDialog component</span></span>

1. <span data-ttu-id="45aa1-106">In una procedura, controllare la <xref:System.Windows.Forms.FolderBrowserDialog> <xref:System.Windows.Forms.Form.DialogResult%2A> proprietà del componente per vedere come la finestra di dialogo è stata chiusa e <xref:System.Windows.Forms.FolderBrowserDialog> ottenere il <xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A> valore della proprietà del componente.</span><span class="sxs-lookup"><span data-stu-id="45aa1-106">In a procedure, check the <xref:System.Windows.Forms.FolderBrowserDialog> component's <xref:System.Windows.Forms.Form.DialogResult%2A> property to see how the dialog box was closed and get the value of the <xref:System.Windows.Forms.FolderBrowserDialog> component's <xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A> property.</span></span>

2. <span data-ttu-id="45aa1-107">Se è necessario impostare la cartella di primo livello che verrà visualizzata nella visualizzazione albero della finestra di dialogo, impostare la <xref:System.Windows.Forms.FolderBrowserDialog.RootFolder%2A> proprietà che accetta un membro <xref:System.Environment.SpecialFolder> dell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="45aa1-107">If you need to set the top-most folder that will appear within the tree view of the dialog box, set the <xref:System.Windows.Forms.FolderBrowserDialog.RootFolder%2A> property, which takes a member of the <xref:System.Environment.SpecialFolder> enumeration.</span></span>

3. <span data-ttu-id="45aa1-108">Inoltre, è possibile impostare la <xref:System.Windows.Forms.FolderBrowserDialog.Description%2A> proprietà, che specifica la stringa di testo visualizzata nella parte superiore della visualizzazione albero del browser delle cartelle.</span><span class="sxs-lookup"><span data-stu-id="45aa1-108">Additionally, you can set the <xref:System.Windows.Forms.FolderBrowserDialog.Description%2A> property, which specifies the text string that appears at the top of the folder-browser tree view.</span></span>

    <span data-ttu-id="45aa1-109">Nell'esempio seguente il <xref:System.Windows.Forms.FolderBrowserDialog> componente viene usato per selezionare una cartella, in modo simile a quando si crea un progetto in Visual Studio e viene richiesto di selezionare una cartella in cui salvarlo.</span><span class="sxs-lookup"><span data-stu-id="45aa1-109">In the example below, the <xref:System.Windows.Forms.FolderBrowserDialog> component is used to select a folder, similar to when you create a project in Visual Studio and are prompted to select a folder to save it in.</span></span> <span data-ttu-id="45aa1-110">In questo esempio, il nome della cartella viene quindi visualizzato in <xref:System.Windows.Forms.TextBox> un controllo nel form.</span><span class="sxs-lookup"><span data-stu-id="45aa1-110">In this example, the folder name is then displayed in a <xref:System.Windows.Forms.TextBox> control on the form.</span></span> <span data-ttu-id="45aa1-111">È consigliabile posizionare il percorso in un'area modificabile, ad esempio un <xref:System.Windows.Forms.TextBox> controllo, in modo che gli utenti possano modificare la selezione in caso di errore o di altri problemi.</span><span class="sxs-lookup"><span data-stu-id="45aa1-111">It is a good idea to place the location in an editable area, such as a <xref:System.Windows.Forms.TextBox> control, so that users may edit their selection in case of error or other issues.</span></span> <span data-ttu-id="45aa1-112">In questo esempio si presuppone un form <xref:System.Windows.Forms.FolderBrowserDialog> con un componente <xref:System.Windows.Forms.TextBox> e un controllo.</span><span class="sxs-lookup"><span data-stu-id="45aa1-112">This example assumes a form with a <xref:System.Windows.Forms.FolderBrowserDialog> component and a <xref:System.Windows.Forms.TextBox> control.</span></span>

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
    > <span data-ttu-id="45aa1-113">Per usare questa classe, l'assembly richiede un livello <xref:System.Security.Permissions.FileIOPermissionAttribute.PathDiscovery%2A> <xref:System.Security.Permissions.FileIOPermissionAccess> di privilegio concesso dalla proprietà, che fa parte dell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="45aa1-113">To use this class, your assembly requires a privilege level granted by the <xref:System.Security.Permissions.FileIOPermissionAttribute.PathDiscovery%2A> property, which is part of the <xref:System.Security.Permissions.FileIOPermissionAccess> enumeration.</span></span> <span data-ttu-id="45aa1-114">Se l'esecuzione avviene in un contesto parzialmente attendibile, è possibile che il processo generi un'eccezione dovuta a privilegi insufficienti.</span><span class="sxs-lookup"><span data-stu-id="45aa1-114">If you are running in a partial-trust context, the process might throw an exception because of insufficient privileges.</span></span> <span data-ttu-id="45aa1-115">Per altre informazioni, vedere [Code Access Security Basics](../../misc/code-access-security-basics.md) (Nozioni di base sulla sicurezza dell'accesso di codice).</span><span class="sxs-lookup"><span data-stu-id="45aa1-115">For more information, see [Code Access Security Basics](../../misc/code-access-security-basics.md).</span></span>

<span data-ttu-id="45aa1-116">Per informazioni su come salvare i file, vedere [procedura: Salvare i file utilizzando il componente](how-to-save-files-using-the-savefiledialog-component.md)SaveFileDialog.</span><span class="sxs-lookup"><span data-stu-id="45aa1-116">For information on how to save files, see [How to: Save Files Using the SaveFileDialog Component](how-to-save-files-using-the-savefiledialog-component.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="45aa1-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="45aa1-117">See also</span></span>

- <xref:System.Windows.Forms.FolderBrowserDialog>
- [<span data-ttu-id="45aa1-118">Cenni preliminari sul componente FolderBrowserDialog (Windows Form)</span><span class="sxs-lookup"><span data-stu-id="45aa1-118">FolderBrowserDialog Component Overview (Windows Forms)</span></span>](folderbrowserdialog-component-overview-windows-forms.md)
- [<span data-ttu-id="45aa1-119">Componente FolderBrowserDialog</span><span class="sxs-lookup"><span data-stu-id="45aa1-119">FolderBrowserDialog Component</span></span>](folderbrowserdialog-component-windows-forms.md)

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
# <a name="how-to-choose-folders-with-the-windows-forms-folderbrowserdialog-component"></a><span data-ttu-id="c4f05-102">Procedura: Scegliere cartelle con il componente FolderBrowserDialog di Windows Form</span><span class="sxs-lookup"><span data-stu-id="c4f05-102">How to: Choose Folders with the Windows Forms FolderBrowserDialog Component</span></span>
<span data-ttu-id="c4f05-103">Spesso nelle applicazioni Windows create è necessario chiedere agli utenti di selezionare una cartella, nella maggior parte dei casi per salvare un insieme di file.</span><span class="sxs-lookup"><span data-stu-id="c4f05-103">Often, within Windows applications you create, you will have to prompt users to select a folder, most frequently to save a set of files.</span></span> <span data-ttu-id="c4f05-104">Windows Form <xref:System.Windows.Forms.FolderBrowserDialog> componente consente di eseguire facilmente questa attività.</span><span class="sxs-lookup"><span data-stu-id="c4f05-104">The Windows Forms <xref:System.Windows.Forms.FolderBrowserDialog> component allows you to easily accomplish this task.</span></span>  
  
### <a name="to-choose-folders-with-the-folderbrowserdialog-component"></a><span data-ttu-id="c4f05-105">Per scegliere cartelle con il componente FolderBrowserDialog</span><span class="sxs-lookup"><span data-stu-id="c4f05-105">To choose folders with the FolderBrowserDialog component</span></span>  
  
1.  <span data-ttu-id="c4f05-106">In una routine, controllare il <xref:System.Windows.Forms.FolderBrowserDialog> del componente <xref:System.Windows.Forms.Form.DialogResult%2A> come è stata chiusa la finestra di dialogo e ottenere il valore della proprietà di <xref:System.Windows.Forms.FolderBrowserDialog> del componente <xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="c4f05-106">In a procedure, check the <xref:System.Windows.Forms.FolderBrowserDialog> component's <xref:System.Windows.Forms.Form.DialogResult%2A> property to see how the dialog box was closed and get the value of the <xref:System.Windows.Forms.FolderBrowserDialog> component's <xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A> property.</span></span>  
  
2.  <span data-ttu-id="c4f05-107">Se è necessario nella cartella set di primo livello che verrà visualizzato all'interno della visualizzazione albero nella finestra di dialogo, impostare il <xref:System.Windows.Forms.FolderBrowserDialog.RootFolder%2A> proprietà, che accetta un membro del <xref:System.Environment.SpecialFolder> enumerazione.</span><span class="sxs-lookup"><span data-stu-id="c4f05-107">If you need to set the top-most folder that will appear within the tree view of the dialog box, set the <xref:System.Windows.Forms.FolderBrowserDialog.RootFolder%2A> property, which takes a member of the <xref:System.Environment.SpecialFolder> enumeration.</span></span>  
  
3.  <span data-ttu-id="c4f05-108">Inoltre, è possibile impostare il <xref:System.Windows.Forms.FolderBrowserDialog.Description%2A> proprietà che specifica la stringa di testo viene visualizzato nella parte superiore della visualizzazione albero del visualizzatore cartelle.</span><span class="sxs-lookup"><span data-stu-id="c4f05-108">Additionally, you can set the <xref:System.Windows.Forms.FolderBrowserDialog.Description%2A> property, which specifies the text string that appears at the top of the folder-browser tree view.</span></span>  
  
     <span data-ttu-id="c4f05-109">Nell'esempio seguente, il <xref:System.Windows.Forms.FolderBrowserDialog> componente viene utilizzato per selezionare una cartella, simile a quando si crea un progetto in Visual Studio e viene richiesto di selezionare una cartella in cui salvarlo.</span><span class="sxs-lookup"><span data-stu-id="c4f05-109">In the example below, the <xref:System.Windows.Forms.FolderBrowserDialog> component is used to select a folder, similar to when you create a project in Visual Studio and are prompted to select a folder to save it in.</span></span> <span data-ttu-id="c4f05-110">In questo esempio viene quindi visualizzato il nome della cartella un <xref:System.Windows.Forms.TextBox> controllo nel form.</span><span class="sxs-lookup"><span data-stu-id="c4f05-110">In this example, the folder name is then displayed in a <xref:System.Windows.Forms.TextBox> control on the form.</span></span> <span data-ttu-id="c4f05-111">È consigliabile specificare la posizione in un'area modificabile, ad esempio un <xref:System.Windows.Forms.TextBox> controllare, in modo che gli utenti possano modificare la selezione in caso di errore o altri problemi.</span><span class="sxs-lookup"><span data-stu-id="c4f05-111">It is a good idea to place the location in an editable area, such as a <xref:System.Windows.Forms.TextBox> control, so that users may edit their selection in case of error or other issues.</span></span> <span data-ttu-id="c4f05-112">Questo esempio si presuppone un form con un <xref:System.Windows.Forms.FolderBrowserDialog> componente e un <xref:System.Windows.Forms.TextBox> controllo.</span><span class="sxs-lookup"><span data-stu-id="c4f05-112">This example assumes a form with a <xref:System.Windows.Forms.FolderBrowserDialog> component and a <xref:System.Windows.Forms.TextBox> control.</span></span>  
  
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
    >  <span data-ttu-id="c4f05-113">Per utilizzare questa classe, l'assembly richiede un livello di privilegio concesso per il <xref:System.Security.Permissions.FileIOPermissionAttribute.PathDiscovery%2A> proprietà, che fa parte di <xref:System.Security.Permissions.FileIOPermissionAccess> enumerazione.</span><span class="sxs-lookup"><span data-stu-id="c4f05-113">To use this class, your assembly requires a privilege level granted by the <xref:System.Security.Permissions.FileIOPermissionAttribute.PathDiscovery%2A> property, which is part of the <xref:System.Security.Permissions.FileIOPermissionAccess> enumeration.</span></span> <span data-ttu-id="c4f05-114">Se l'esecuzione avviene in un contesto parzialmente attendibile, è possibile che il processo generi un'eccezione dovuta a privilegi insufficienti.</span><span class="sxs-lookup"><span data-stu-id="c4f05-114">If you are running in a partial-trust context, the process might throw an exception because of insufficient privileges.</span></span> <span data-ttu-id="c4f05-115">Per altre informazioni, vedere [Code Access Security Basics](../../../../docs/framework/misc/code-access-security-basics.md) (Nozioni di base sulla sicurezza dell'accesso di codice).</span><span class="sxs-lookup"><span data-stu-id="c4f05-115">For more information, see [Code Access Security Basics](../../../../docs/framework/misc/code-access-security-basics.md).</span></span>  
  
 <span data-ttu-id="c4f05-116">Per informazioni sul salvataggio dei file, vedere [Procedura: Salvare file con il componente SaveFileDialog](../../../../docs/framework/winforms/controls/how-to-save-files-using-the-savefiledialog-component.md).</span><span class="sxs-lookup"><span data-stu-id="c4f05-116">For information on how to save files, see [How to: Save Files Using the SaveFileDialog Component](../../../../docs/framework/winforms/controls/how-to-save-files-using-the-savefiledialog-component.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4f05-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c4f05-117">See Also</span></span>  
 <xref:System.Windows.Forms.FolderBrowserDialog>  
 [<span data-ttu-id="c4f05-118">Cenni preliminari sul componente FolderBrowserDialog (Windows Form)</span><span class="sxs-lookup"><span data-stu-id="c4f05-118">FolderBrowserDialog Component Overview (Windows Forms)</span></span>](../../../../docs/framework/winforms/controls/folderbrowserdialog-component-overview-windows-forms.md)  
 [<span data-ttu-id="c4f05-119">Componente FolderBrowserDialog</span><span class="sxs-lookup"><span data-stu-id="c4f05-119">FolderBrowserDialog Component</span></span>](../../../../docs/framework/winforms/controls/folderbrowserdialog-component-windows-forms.md)

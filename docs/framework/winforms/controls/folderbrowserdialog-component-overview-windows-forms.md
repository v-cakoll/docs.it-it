---
title: Cenni preliminari sul componente FolderBrowserDialog (Windows Form)
ms.date: 03/30/2017
f1_keywords:
- FolderBrowserDialog
helpviewer_keywords:
- FolderBrowserDialog component [Windows Forms], about FolderBrowserDialog
- directories [Windows Forms], enabling browsing in applications
- folders [Windows Forms], enabling browsing in applications
ms.assetid: 796b622c-3ba9-4356-93bb-e217fc52f2c7
ms.openlocfilehash: a735749698266ac20e2ea9ee5569fd210ee9977b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33525008"
---
# <a name="folderbrowserdialog-component-overview-windows-forms"></a><span data-ttu-id="42f3f-102">Cenni preliminari sul componente FolderBrowserDialog (Windows Form)</span><span class="sxs-lookup"><span data-stu-id="42f3f-102">FolderBrowserDialog Component Overview (Windows Forms)</span></span>
<span data-ttu-id="42f3f-103">Windows Form <xref:System.Windows.Forms.FolderBrowserDialog> componente è una finestra di dialogo modale che viene utilizzato per l'esplorazione e la selezione di cartelle.</span><span class="sxs-lookup"><span data-stu-id="42f3f-103">The Windows Forms <xref:System.Windows.Forms.FolderBrowserDialog> component is a modal dialog box that is used for browsing and selecting folders.</span></span> <span data-ttu-id="42f3f-104">Inoltre è possibile creare nuove cartelle dall'interno di <xref:System.Windows.Forms.FolderBrowserDialog> componente.</span><span class="sxs-lookup"><span data-stu-id="42f3f-104">New folders can also be created from within the <xref:System.Windows.Forms.FolderBrowserDialog> component.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="42f3f-105">Per selezionare i file, cartelle, invece di utilizzare il [OpenFileDialog](../../../../docs/framework/winforms/controls/openfiledialog-component-windows-forms.md) componente.</span><span class="sxs-lookup"><span data-stu-id="42f3f-105">To select files, instead of folders, use the [OpenFileDialog](../../../../docs/framework/winforms/controls/openfiledialog-component-windows-forms.md) component.</span></span>  
  
 <span data-ttu-id="42f3f-106">Il <xref:System.Windows.Forms.FolderBrowserDialog> componente viene visualizzato in fase di esecuzione usando il <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="42f3f-106">The <xref:System.Windows.Forms.FolderBrowserDialog> component is displayed at run time using the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method.</span></span> <span data-ttu-id="42f3f-107">Impostare il <xref:System.Windows.Forms.FolderBrowserDialog.RootFolder%2A> proprietà per determinare la cartella di primo piano ed eventuali sottocartelle che verranno visualizzato all'interno della visualizzazione albero nella finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="42f3f-107">Set the <xref:System.Windows.Forms.FolderBrowserDialog.RootFolder%2A> property to determine the top-most folder and any subfolders that will appear within the tree view of the dialog box.</span></span> <span data-ttu-id="42f3f-108">Una volta la finestra di dialogo, è possibile utilizzare il <xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A> proprietà per ottenere il percorso della cartella in cui è stato selezionato.</span><span class="sxs-lookup"><span data-stu-id="42f3f-108">Once the dialog box has been shown, you can use the <xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A> property to get the path of the folder that was selected.</span></span>  
  
 <span data-ttu-id="42f3f-109">Quando viene aggiunto a un modulo, il <xref:System.Windows.Forms.FolderBrowserDialog> componente viene visualizzato nella barra delle applicazioni nella parte inferiore della finestra di progettazione Windows Form.</span><span class="sxs-lookup"><span data-stu-id="42f3f-109">When it is added to a form, the <xref:System.Windows.Forms.FolderBrowserDialog> component appears in the tray at the bottom of the Windows Forms Designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42f3f-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="42f3f-110">See Also</span></span>  
 <xref:System.Windows.Forms.FolderBrowserDialog>  
 [<span data-ttu-id="42f3f-111">Procedura: Scegliere cartelle con il componente FolderBrowserDialog di Windows Form</span><span class="sxs-lookup"><span data-stu-id="42f3f-111">How to: Choose Folders with the Windows Forms FolderBrowserDialog Component</span></span>](../../../../docs/framework/winforms/controls/how-to-choose-folders-with-the-windows-forms-folderbrowserdialog-component.md)  
 [<span data-ttu-id="42f3f-112">Componente FolderBrowserDialog</span><span class="sxs-lookup"><span data-stu-id="42f3f-112">FolderBrowserDialog Component</span></span>](../../../../docs/framework/winforms/controls/folderbrowserdialog-component-windows-forms.md)

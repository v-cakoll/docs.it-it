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
ms.openlocfilehash: aae18167b29c71ad692cc6ba447457cd079374b4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61651467"
---
# <a name="folderbrowserdialog-component-overview-windows-forms"></a><span data-ttu-id="9a5eb-102">Cenni preliminari sul componente FolderBrowserDialog (Windows Form)</span><span class="sxs-lookup"><span data-stu-id="9a5eb-102">FolderBrowserDialog Component Overview (Windows Forms)</span></span>
<span data-ttu-id="9a5eb-103">I moduli di Windows <xref:System.Windows.Forms.FolderBrowserDialog> componente è una finestra di dialogo modale che viene usata per l'esplorazione e selezione di cartelle.</span><span class="sxs-lookup"><span data-stu-id="9a5eb-103">The Windows Forms <xref:System.Windows.Forms.FolderBrowserDialog> component is a modal dialog box that is used for browsing and selecting folders.</span></span> <span data-ttu-id="9a5eb-104">Sono anche possibile creare nuove cartelle dall'interno di <xref:System.Windows.Forms.FolderBrowserDialog> componente.</span><span class="sxs-lookup"><span data-stu-id="9a5eb-104">New folders can also be created from within the <xref:System.Windows.Forms.FolderBrowserDialog> component.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9a5eb-105">Per selezionare i file, invece di cartelle, usare il [OpenFileDialog](openfiledialog-component-windows-forms.md) componente.</span><span class="sxs-lookup"><span data-stu-id="9a5eb-105">To select files, instead of folders, use the [OpenFileDialog](openfiledialog-component-windows-forms.md) component.</span></span>  
  
 <span data-ttu-id="9a5eb-106">Il <xref:System.Windows.Forms.FolderBrowserDialog> componente è visualizzato in fase di esecuzione usando il <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> (metodo).</span><span class="sxs-lookup"><span data-stu-id="9a5eb-106">The <xref:System.Windows.Forms.FolderBrowserDialog> component is displayed at run time using the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method.</span></span> <span data-ttu-id="9a5eb-107">Impostare il <xref:System.Windows.Forms.FolderBrowserDialog.RootFolder%2A> proprietà per determinare la cartella di livello superiore ed eventuali sottocartelle che verranno visualizzato all'interno della visualizzazione struttura ad albero della finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="9a5eb-107">Set the <xref:System.Windows.Forms.FolderBrowserDialog.RootFolder%2A> property to determine the top-most folder and any subfolders that will appear within the tree view of the dialog box.</span></span> <span data-ttu-id="9a5eb-108">Una volta visualizzata la finestra di dialogo, è possibile usare il <xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A> proprietà da ottenere il percorso della cartella in cui è stato selezionato.</span><span class="sxs-lookup"><span data-stu-id="9a5eb-108">Once the dialog box has been shown, you can use the <xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A> property to get the path of the folder that was selected.</span></span>  
  
 <span data-ttu-id="9a5eb-109">Quando viene aggiunto a un modulo, il <xref:System.Windows.Forms.FolderBrowserDialog> componente è visualizzato nella barra delle applicazioni nella parte inferiore della finestra di progettazione Windows Form.</span><span class="sxs-lookup"><span data-stu-id="9a5eb-109">When it is added to a form, the <xref:System.Windows.Forms.FolderBrowserDialog> component appears in the tray at the bottom of the Windows Forms Designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a5eb-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9a5eb-110">See also</span></span>

- <xref:System.Windows.Forms.FolderBrowserDialog>
- [<span data-ttu-id="9a5eb-111">Procedura: Scegliere cartelle con il componente FolderBrowserDialog di Windows Form</span><span class="sxs-lookup"><span data-stu-id="9a5eb-111">How to: Choose Folders with the Windows Forms FolderBrowserDialog Component</span></span>](how-to-choose-folders-with-the-windows-forms-folderbrowserdialog-component.md)
- [<span data-ttu-id="9a5eb-112">Componente FolderBrowserDialog</span><span class="sxs-lookup"><span data-stu-id="9a5eb-112">FolderBrowserDialog Component</span></span>](folderbrowserdialog-component-windows-forms.md)

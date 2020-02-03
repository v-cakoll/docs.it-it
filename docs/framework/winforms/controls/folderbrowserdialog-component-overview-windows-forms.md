---
title: Panoramica del componente FolderBrowserDialog
ms.date: 03/30/2017
f1_keywords:
- FolderBrowserDialog
helpviewer_keywords:
- FolderBrowserDialog component [Windows Forms], about FolderBrowserDialog
- directories [Windows Forms], enabling browsing in applications
- folders [Windows Forms], enabling browsing in applications
ms.assetid: 796b622c-3ba9-4356-93bb-e217fc52f2c7
ms.openlocfilehash: 8b017ba08ae4205e930ac00177c89a89fde17d3b
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745732"
---
# <a name="folderbrowserdialog-component-overview-windows-forms"></a><span data-ttu-id="ac398-102">Cenni preliminari sul componente FolderBrowserDialog (Windows Form)</span><span class="sxs-lookup"><span data-stu-id="ac398-102">FolderBrowserDialog Component Overview (Windows Forms)</span></span>

<span data-ttu-id="ac398-103">Il componente Windows Forms <xref:System.Windows.Forms.FolderBrowserDialog> è una finestra di dialogo modale utilizzata per l'esplorazione e la selezione di cartelle.</span><span class="sxs-lookup"><span data-stu-id="ac398-103">The Windows Forms <xref:System.Windows.Forms.FolderBrowserDialog> component is a modal dialog box that is used for browsing and selecting folders.</span></span> <span data-ttu-id="ac398-104">È anche possibile creare nuove cartelle dall'interno del componente <xref:System.Windows.Forms.FolderBrowserDialog>.</span><span class="sxs-lookup"><span data-stu-id="ac398-104">New folders can also be created from within the <xref:System.Windows.Forms.FolderBrowserDialog> component.</span></span>

> [!NOTE]
> <span data-ttu-id="ac398-105">Per selezionare i file, anziché le cartelle, utilizzare il componente [OpenFileDialog](openfiledialog-component-windows-forms.md) .</span><span class="sxs-lookup"><span data-stu-id="ac398-105">To select files, instead of folders, use the [OpenFileDialog](openfiledialog-component-windows-forms.md) component.</span></span>

<span data-ttu-id="ac398-106">Il componente <xref:System.Windows.Forms.FolderBrowserDialog> viene visualizzato in fase di esecuzione usando il metodo <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A>.</span><span class="sxs-lookup"><span data-stu-id="ac398-106">The <xref:System.Windows.Forms.FolderBrowserDialog> component is displayed at run time using the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method.</span></span> <span data-ttu-id="ac398-107">Impostare la proprietà <xref:System.Windows.Forms.FolderBrowserDialog.RootFolder%2A> per determinare la cartella più in alto e tutte le sottocartelle che verranno visualizzate nella visualizzazione albero della finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="ac398-107">Set the <xref:System.Windows.Forms.FolderBrowserDialog.RootFolder%2A> property to determine the top-most folder and any subfolders that will appear within the tree view of the dialog box.</span></span> <span data-ttu-id="ac398-108">Una volta visualizzata la finestra di dialogo, è possibile utilizzare la proprietà <xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A> per ottenere il percorso della cartella selezionata.</span><span class="sxs-lookup"><span data-stu-id="ac398-108">Once the dialog box has been shown, you can use the <xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A> property to get the path of the folder that was selected.</span></span>

<span data-ttu-id="ac398-109">Quando viene aggiunto a un modulo, il componente <xref:System.Windows.Forms.FolderBrowserDialog> viene visualizzato nella barra delle applicazioni nella parte inferiore della Progettazione Windows Form in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="ac398-109">When it is added to a form, the <xref:System.Windows.Forms.FolderBrowserDialog> component appears in the tray at the bottom of the Windows Forms Designer in Visual Studio.</span></span>

## <a name="see-also"></a><span data-ttu-id="ac398-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ac398-110">See also</span></span>

- <xref:System.Windows.Forms.FolderBrowserDialog>
- [<span data-ttu-id="ac398-111">Procedura: Scegliere cartelle con il componente FolderBrowserDialog di Windows Form</span><span class="sxs-lookup"><span data-stu-id="ac398-111">How to: Choose Folders with the Windows Forms FolderBrowserDialog Component</span></span>](how-to-choose-folders-with-the-windows-forms-folderbrowserdialog-component.md)
- [<span data-ttu-id="ac398-112">Componente FolderBrowserDialog</span><span class="sxs-lookup"><span data-stu-id="ac398-112">FolderBrowserDialog Component</span></span>](folderbrowserdialog-component-windows-forms.md)

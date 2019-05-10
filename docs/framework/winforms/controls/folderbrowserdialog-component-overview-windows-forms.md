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
ms.openlocfilehash: cd89980ccad7e6c73094c1fb462d93cee8094959
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2019
ms.locfileid: "65210404"
---
# <a name="folderbrowserdialog-component-overview-windows-forms"></a><span data-ttu-id="091bf-102">Cenni preliminari sul componente FolderBrowserDialog (Windows Form)</span><span class="sxs-lookup"><span data-stu-id="091bf-102">FolderBrowserDialog Component Overview (Windows Forms)</span></span>

<span data-ttu-id="091bf-103">I moduli di Windows <xref:System.Windows.Forms.FolderBrowserDialog> componente è una finestra di dialogo modale che viene usata per l'esplorazione e selezione di cartelle.</span><span class="sxs-lookup"><span data-stu-id="091bf-103">The Windows Forms <xref:System.Windows.Forms.FolderBrowserDialog> component is a modal dialog box that is used for browsing and selecting folders.</span></span> <span data-ttu-id="091bf-104">Sono anche possibile creare nuove cartelle dall'interno di <xref:System.Windows.Forms.FolderBrowserDialog> componente.</span><span class="sxs-lookup"><span data-stu-id="091bf-104">New folders can also be created from within the <xref:System.Windows.Forms.FolderBrowserDialog> component.</span></span>

> [!NOTE]
> <span data-ttu-id="091bf-105">Per selezionare i file, invece di cartelle, usare il [OpenFileDialog](openfiledialog-component-windows-forms.md) componente.</span><span class="sxs-lookup"><span data-stu-id="091bf-105">To select files, instead of folders, use the [OpenFileDialog](openfiledialog-component-windows-forms.md) component.</span></span>

<span data-ttu-id="091bf-106">Il <xref:System.Windows.Forms.FolderBrowserDialog> componente è visualizzato in fase di esecuzione usando il <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> (metodo).</span><span class="sxs-lookup"><span data-stu-id="091bf-106">The <xref:System.Windows.Forms.FolderBrowserDialog> component is displayed at run time using the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method.</span></span> <span data-ttu-id="091bf-107">Impostare il <xref:System.Windows.Forms.FolderBrowserDialog.RootFolder%2A> proprietà per determinare la cartella di livello superiore ed eventuali sottocartelle che verranno visualizzato all'interno della visualizzazione struttura ad albero della finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="091bf-107">Set the <xref:System.Windows.Forms.FolderBrowserDialog.RootFolder%2A> property to determine the top-most folder and any subfolders that will appear within the tree view of the dialog box.</span></span> <span data-ttu-id="091bf-108">Una volta visualizzata la finestra di dialogo, è possibile usare il <xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A> proprietà da ottenere il percorso della cartella in cui è stato selezionato.</span><span class="sxs-lookup"><span data-stu-id="091bf-108">Once the dialog box has been shown, you can use the <xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A> property to get the path of the folder that was selected.</span></span>

<span data-ttu-id="091bf-109">Quando viene aggiunto a un modulo, il <xref:System.Windows.Forms.FolderBrowserDialog> componente è visualizzato nella barra delle applicazioni nella parte inferiore della finestra di progettazione Windows Form in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="091bf-109">When it is added to a form, the <xref:System.Windows.Forms.FolderBrowserDialog> component appears in the tray at the bottom of the Windows Forms Designer in Visual Studio.</span></span>

## <a name="see-also"></a><span data-ttu-id="091bf-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="091bf-110">See also</span></span>

- <xref:System.Windows.Forms.FolderBrowserDialog>
- [<span data-ttu-id="091bf-111">Procedura: Scegliere cartelle con il componente FolderBrowserDialog di Windows Form</span><span class="sxs-lookup"><span data-stu-id="091bf-111">How to: Choose Folders with the Windows Forms FolderBrowserDialog Component</span></span>](how-to-choose-folders-with-the-windows-forms-folderbrowserdialog-component.md)
- [<span data-ttu-id="091bf-112">Componente FolderBrowserDialog</span><span class="sxs-lookup"><span data-stu-id="091bf-112">FolderBrowserDialog Component</span></span>](folderbrowserdialog-component-windows-forms.md)

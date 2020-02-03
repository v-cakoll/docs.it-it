---
title: Cenni preliminari sul componente SaveFileDialog
ms.date: 03/30/2017
f1_keywords:
- SaveFileDialog
helpviewer_keywords:
- Save File dialog box [Windows Forms], displaying
- SaveFileDialog component [Windows Forms], about SaveFileDialog
ms.assetid: be7a625f-46fd-4d06-9985-b613dcbf9bd2
ms.openlocfilehash: 7609c29b7e932ecee7dc8a289617094bd8d480e2
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743108"
---
# <a name="savefiledialog-component-overview-windows-forms"></a><span data-ttu-id="0cede-102">Cenni preliminari sul componente SaveFileDialog (Windows Form)</span><span class="sxs-lookup"><span data-stu-id="0cede-102">SaveFileDialog Component Overview (Windows Forms)</span></span>

<span data-ttu-id="0cede-103">Il componente di Windows Form <xref:System.Windows.Forms.SaveFileDialog> è una finestra di dialogo preconfigurata.</span><span class="sxs-lookup"><span data-stu-id="0cede-103">The Windows Forms <xref:System.Windows.Forms.SaveFileDialog> component is a pre-configured dialog box.</span></span> <span data-ttu-id="0cede-104">Corrisponde alla finestra di dialogo **Salva file** standard utilizzata da Windows.</span><span class="sxs-lookup"><span data-stu-id="0cede-104">It is the same as the standard **Save File** dialog box used by Windows.</span></span> <span data-ttu-id="0cede-105">Il componente eredita dalla classe <xref:System.Windows.Forms.CommonDialog>.</span><span class="sxs-lookup"><span data-stu-id="0cede-105">It inherits from the <xref:System.Windows.Forms.CommonDialog> class.</span></span>

## <a name="working-with-the-savefiledialog-component"></a><span data-ttu-id="0cede-106">Utilizzo del componente SaveFileDialog</span><span class="sxs-lookup"><span data-stu-id="0cede-106">Working with the SaveFileDialog Component</span></span>

<span data-ttu-id="0cede-107">Usarlo come soluzione semplice per consentire agli utenti di salvare i file anziché configurare la propria finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="0cede-107">Use it as a simple solution for enabling users to save files instead of configuring your own dialog box.</span></span> <span data-ttu-id="0cede-108">Basandosi sulle finestre di dialogo standard di Windows, le funzionalità di base delle applicazioni create sono immediatamente note agli utenti.</span><span class="sxs-lookup"><span data-stu-id="0cede-108">By relying on standard Windows dialog boxes, the basic functionality of applications you create is immediately familiar to users.</span></span> <span data-ttu-id="0cede-109">Tenere presente, tuttavia, che quando si usa il componente <xref:System.Windows.Forms.SaveFileDialog>, è necessario scrivere una logica di salvataggio file personalizzata.</span><span class="sxs-lookup"><span data-stu-id="0cede-109">Be aware, however, that when using the <xref:System.Windows.Forms.SaveFileDialog> component, you must write your own file-saving logic.</span></span>

<span data-ttu-id="0cede-110">È possibile utilizzare il metodo <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> per visualizzare la finestra di dialogo in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="0cede-110">You can use the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method to display the dialog box at run time.</span></span> <span data-ttu-id="0cede-111">È possibile aprire un file in modalità di lettura/scrittura usando il metodo <xref:System.Windows.Forms.SaveFileDialog.OpenFile%2A>.</span><span class="sxs-lookup"><span data-stu-id="0cede-111">You can open a file in read/write mode using the <xref:System.Windows.Forms.SaveFileDialog.OpenFile%2A> method.</span></span>

<span data-ttu-id="0cede-112">Quando viene aggiunto a un modulo, il componente <xref:System.Windows.Forms.SaveFileDialog> viene visualizzato nella barra delle applicazioni nella parte inferiore della Progettazione Windows Form in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="0cede-112">When it is added to a form, the <xref:System.Windows.Forms.SaveFileDialog> component appears in the tray at the bottom of the Windows Forms Designer in Visual Studio.</span></span>

## <a name="see-also"></a><span data-ttu-id="0cede-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0cede-113">See also</span></span>

- <xref:System.Windows.Forms.SaveFileDialog>
- [<span data-ttu-id="0cede-114">Componente SaveFileDialog</span><span class="sxs-lookup"><span data-stu-id="0cede-114">SaveFileDialog Component</span></span>](savefiledialog-component-windows-forms.md)

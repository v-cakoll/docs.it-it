---
title: Cenni preliminari sul componente SaveFileDialog (Windows Form)
ms.date: 03/30/2017
f1_keywords:
- SaveFileDialog
helpviewer_keywords:
- Save File dialog box [Windows Forms], displaying
- SaveFileDialog component [Windows Forms], about SaveFileDialog
ms.assetid: be7a625f-46fd-4d06-9985-b613dcbf9bd2
ms.openlocfilehash: b06c4d510cefdc7558944995594fd209b6121cb1
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59103042"
---
# <a name="savefiledialog-component-overview-windows-forms"></a><span data-ttu-id="935f9-102">Cenni preliminari sul componente SaveFileDialog (Windows Form)</span><span class="sxs-lookup"><span data-stu-id="935f9-102">SaveFileDialog Component Overview (Windows Forms)</span></span>
<span data-ttu-id="935f9-103">Il componente di Windows Form <xref:System.Windows.Forms.SaveFileDialog> è una finestra di dialogo preconfigurata.</span><span class="sxs-lookup"><span data-stu-id="935f9-103">The Windows Forms <xref:System.Windows.Forms.SaveFileDialog> component is a pre-configured dialog box.</span></span> <span data-ttu-id="935f9-104">È identico allo standard **Salva File** dialogo utilizzata da Windows.</span><span class="sxs-lookup"><span data-stu-id="935f9-104">It is the same as the standard **Save File** dialog box used by Windows.</span></span> <span data-ttu-id="935f9-105">Il componente eredita dalla classe <xref:System.Windows.Forms.CommonDialog>.</span><span class="sxs-lookup"><span data-stu-id="935f9-105">It inherits from the <xref:System.Windows.Forms.CommonDialog> class.</span></span>  
  
## <a name="working-with-the-savefiledialog-component"></a><span data-ttu-id="935f9-106">Utilizzo del componente SaveFileDialog</span><span class="sxs-lookup"><span data-stu-id="935f9-106">Working with the SaveFileDialog Component</span></span>  
 <span data-ttu-id="935f9-107">Usarlo come una soluzione semplice per consentire agli utenti di salvare i file invece di configurare una propria finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="935f9-107">Use it as a simple solution for enabling users to save files instead of configuring your own dialog box.</span></span> <span data-ttu-id="935f9-108">Basandosi sulle finestre di dialogo di Windows standard, la funzionalità di base di applicazioni create è immediatamente familiare agli utenti.</span><span class="sxs-lookup"><span data-stu-id="935f9-108">By relying on standard Windows dialog boxes, the basic functionality of applications you create is immediately familiar to users.</span></span> <span data-ttu-id="935f9-109">Tenere presente, tuttavia, che, quando tramite il <xref:System.Windows.Forms.SaveFileDialog> componente, è necessario scrivere la propria logica di salvataggio dei file.</span><span class="sxs-lookup"><span data-stu-id="935f9-109">Be aware, however, that when using the <xref:System.Windows.Forms.SaveFileDialog> component, you must write your own file-saving logic.</span></span>  
  
 <span data-ttu-id="935f9-110">È possibile usare il <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> metodo per visualizzare la finestra di dialogo in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="935f9-110">You can use the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method to display the dialog box at run time.</span></span> <span data-ttu-id="935f9-111">È possibile aprire un file in modalità di lettura/scrittura tramite il <xref:System.Windows.Forms.SaveFileDialog.OpenFile%2A> (metodo).</span><span class="sxs-lookup"><span data-stu-id="935f9-111">You can open a file in read/write mode using the <xref:System.Windows.Forms.SaveFileDialog.OpenFile%2A> method.</span></span>  
  
 <span data-ttu-id="935f9-112">Quando viene aggiunto a un modulo, il <xref:System.Windows.Forms.SaveFileDialog> componente è visualizzato nella barra delle applicazioni nella parte inferiore della finestra di progettazione Windows Form.</span><span class="sxs-lookup"><span data-stu-id="935f9-112">When it is added to a form, the <xref:System.Windows.Forms.SaveFileDialog> component appears in the tray at the bottom of the Windows Forms Designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="935f9-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="935f9-113">See also</span></span>

- <xref:System.Windows.Forms.SaveFileDialog>
- [<span data-ttu-id="935f9-114">Componente SaveFileDialog</span><span class="sxs-lookup"><span data-stu-id="935f9-114">SaveFileDialog Component</span></span>](savefiledialog-component-windows-forms.md)

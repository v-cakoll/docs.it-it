---
title: Cenni preliminari sul componente SaveFileDialog (Windows Form)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: SaveFileDialog
helpviewer_keywords:
- Save File dialog box [Windows Forms], displaying
- SaveFileDialog component [Windows Forms], about SaveFileDialog
ms.assetid: be7a625f-46fd-4d06-9985-b613dcbf9bd2
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4cbdc1cb96234e302458cbeac6d6ae26b63c956e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="savefiledialog-component-overview-windows-forms"></a><span data-ttu-id="7c25b-102">Cenni preliminari sul componente SaveFileDialog (Windows Form)</span><span class="sxs-lookup"><span data-stu-id="7c25b-102">SaveFileDialog Component Overview (Windows Forms)</span></span>
<span data-ttu-id="7c25b-103">Il componente di Windows Form <xref:System.Windows.Forms.SaveFileDialog> è una finestra di dialogo preconfigurata.</span><span class="sxs-lookup"><span data-stu-id="7c25b-103">The Windows Forms <xref:System.Windows.Forms.SaveFileDialog> component is a pre-configured dialog box.</span></span> <span data-ttu-id="7c25b-104">Ha lo stesso come standard **Salva File** la finestra di dialogo utilizzata da Windows.</span><span class="sxs-lookup"><span data-stu-id="7c25b-104">It is the same as the standard **Save File** dialog box used by Windows.</span></span> <span data-ttu-id="7c25b-105">Il componente eredita dalla classe <xref:System.Windows.Forms.CommonDialog>.</span><span class="sxs-lookup"><span data-stu-id="7c25b-105">It inherits from the <xref:System.Windows.Forms.CommonDialog> class.</span></span>  
  
## <a name="working-with-the-savefiledialog-component"></a><span data-ttu-id="7c25b-106">Utilizzo del componente SaveFileDialog</span><span class="sxs-lookup"><span data-stu-id="7c25b-106">Working with the SaveFileDialog Component</span></span>  
 <span data-ttu-id="7c25b-107">Utilizzarlo come semplice soluzione per consentire agli utenti di salvare i file invece configurare la propria finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="7c25b-107">Use it as a simple solution for enabling users to save files instead of configuring your own dialog box.</span></span> <span data-ttu-id="7c25b-108">Basandosi sulle finestre di dialogo standard di Windows, la funzionalità di base delle applicazioni creati è immediatamente familiare agli utenti.</span><span class="sxs-lookup"><span data-stu-id="7c25b-108">By relying on standard Windows dialog boxes, the basic functionality of applications you create is immediately familiar to users.</span></span> <span data-ttu-id="7c25b-109">Tenere presente, tuttavia, che, quando tramite il <xref:System.Windows.Forms.SaveFileDialog> componente, è necessario scrivere la propria logica di salvataggio di file.</span><span class="sxs-lookup"><span data-stu-id="7c25b-109">Be aware, however, that when using the <xref:System.Windows.Forms.SaveFileDialog> component, you must write your own file-saving logic.</span></span>  
  
 <span data-ttu-id="7c25b-110">È possibile utilizzare il <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> metodo per visualizzare la finestra di dialogo in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="7c25b-110">You can use the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method to display the dialog box at run time.</span></span> <span data-ttu-id="7c25b-111">È possibile aprire un file in modalità lettura/scrittura con la <xref:System.Windows.Forms.SaveFileDialog.OpenFile%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="7c25b-111">You can open a file in read/write mode using the <xref:System.Windows.Forms.SaveFileDialog.OpenFile%2A> method.</span></span>  
  
 <span data-ttu-id="7c25b-112">Quando viene aggiunto a un modulo, il <xref:System.Windows.Forms.SaveFileDialog> componente viene visualizzato nella barra delle applicazioni nella parte inferiore della finestra di progettazione Windows Form.</span><span class="sxs-lookup"><span data-stu-id="7c25b-112">When it is added to a form, the <xref:System.Windows.Forms.SaveFileDialog> component appears in the tray at the bottom of the Windows Forms Designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c25b-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7c25b-113">See Also</span></span>  
 <xref:System.Windows.Forms.SaveFileDialog>  
 [<span data-ttu-id="7c25b-114">Componente SaveFileDialog</span><span class="sxs-lookup"><span data-stu-id="7c25b-114">SaveFileDialog Component</span></span>](../../../../docs/framework/winforms/controls/savefiledialog-component-windows-forms.md)

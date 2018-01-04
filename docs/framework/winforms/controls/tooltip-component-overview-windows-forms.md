---
title: Cenni preliminari sul componente ToolTip (Windows Form)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: ToolTip
helpviewer_keywords:
- tooltips [Windows Forms], about tooltips
- ToolTip component [Windows Forms], about ToolTip component
ms.assetid: 3fbc6f08-c882-4acd-a960-a08efe3c7e6e
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: fce1cb5750197e52461b4883f1238325fa10fc5e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="tooltip-component-overview-windows-forms"></a><span data-ttu-id="2d264-102">Cenni preliminari sul componente ToolTip (Windows Form)</span><span class="sxs-lookup"><span data-stu-id="2d264-102">ToolTip Component Overview (Windows Forms)</span></span>
<span data-ttu-id="2d264-103">Il componente <xref:System.Windows.Forms.ToolTip> di Windows Form visualizza un testo quando l'utente posiziona il puntatore sui controlli.</span><span class="sxs-lookup"><span data-stu-id="2d264-103">The Windows Forms <xref:System.Windows.Forms.ToolTip> component displays text when the user points at controls.</span></span> <span data-ttu-id="2d264-104">Una descrizione comando può essere associata a qualsiasi controllo.</span><span class="sxs-lookup"><span data-stu-id="2d264-104">A ToolTip can be associated with any control.</span></span> <span data-ttu-id="2d264-105">Un esempio di questo componente: per risparmiare spazio in un form, è possibile visualizzare una piccola icona su un pulsante e utilizzare una descrizione comando per illustrare la funzione del pulsante.</span><span class="sxs-lookup"><span data-stu-id="2d264-105">An example use of this component: to save space on a form, you can display a small icon on a button and use a ToolTip to explain the button's function.</span></span>  
  
## <a name="working-with-the-tooltip-component"></a><span data-ttu-id="2d264-106">Utilizzo del componente ToolTip</span><span class="sxs-lookup"><span data-stu-id="2d264-106">Working with the ToolTip Component</span></span>  
 <span data-ttu-id="2d264-107">Oggetto <xref:System.Windows.Forms.ToolTip> componente fornisce un `ToolTip` proprietà a più controlli in un Windows Form o un altro contenitore.</span><span class="sxs-lookup"><span data-stu-id="2d264-107">A <xref:System.Windows.Forms.ToolTip> component provides a `ToolTip` property to multiple controls on a Windows Form or other container.</span></span> <span data-ttu-id="2d264-108">Ad esempio, se si inserisce uno <xref:System.Windows.Forms.ToolTip> componente in un form, è possibile visualizzare il testo "Digitare qui il nome" per un <xref:System.Windows.Forms.TextBox> controllare e "Fare clic qui per salvare le modifiche" per un <xref:System.Windows.Forms.Button> controllo.</span><span class="sxs-lookup"><span data-stu-id="2d264-108">For example, if you place one <xref:System.Windows.Forms.ToolTip> component on a form, you can display "Type your name here" for a <xref:System.Windows.Forms.TextBox> control and "Click here to save changes" for a <xref:System.Windows.Forms.Button> control.</span></span>  
  
 <span data-ttu-id="2d264-109">I metodi principali del <xref:System.Windows.Forms.ToolTip> componente sono <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> e <xref:System.Windows.Forms.ToolTip.GetToolTip%2A>.</span><span class="sxs-lookup"><span data-stu-id="2d264-109">The key methods of the <xref:System.Windows.Forms.ToolTip> component are <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> and <xref:System.Windows.Forms.ToolTip.GetToolTip%2A>.</span></span> <span data-ttu-id="2d264-110">È possibile utilizzare il <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> per impostare le descrizioni comandi visualizzate per i controlli.</span><span class="sxs-lookup"><span data-stu-id="2d264-110">You can use the <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> method to set the ToolTips displayed for controls.</span></span> <span data-ttu-id="2d264-111">Per ulteriori informazioni, vedere [procedura: impostare le descrizioni di comandi per i controlli in un Windows Form in fase di progettazione](../../../../docs/framework/winforms/controls/how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time.md).</span><span class="sxs-lookup"><span data-stu-id="2d264-111">For more information, see [How to: Set ToolTips for Controls on a Windows Form at Design Time](../../../../docs/framework/winforms/controls/how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time.md).</span></span> <span data-ttu-id="2d264-112">Le proprietà principali sono <xref:System.Windows.Forms.ToolTip.Active%2A>, che deve essere impostata su `true` per la descrizione comando viene visualizzata, e <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A>, che imposta il periodo di tempo che la stringa di descrizione comandi, quanto tempo l'utente deve fare riferimento al controllo per la descrizione comando viene visualizzata e come tempo accetta per finestre di descrizione comando successive.</span><span class="sxs-lookup"><span data-stu-id="2d264-112">The key properties are <xref:System.Windows.Forms.ToolTip.Active%2A>, which must be set to `true` for the ToolTip to appear, and <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A>, which sets the length of time that the ToolTip string is shown, how long the user must point at the control for the ToolTip to appear, and how long it takes for subsequent ToolTip windows to appear.</span></span> <span data-ttu-id="2d264-113">Per ulteriori informazioni, vedere [procedura: modificare il ritardo del componente ToolTip di Windows Form](../../../../docs/framework/winforms/controls/how-to-change-the-delay-of-the-windows-forms-tooltip-component.md).</span><span class="sxs-lookup"><span data-stu-id="2d264-113">For more information, see [How to: Change the Delay of the Windows Forms ToolTip Component](../../../../docs/framework/winforms/controls/how-to-change-the-delay-of-the-windows-forms-tooltip-component.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d264-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2d264-114">See Also</span></span>  
 <xref:System.Windows.Forms.ToolTip>  
 [<span data-ttu-id="2d264-115">Procedura: Impostare le descrizioni comandi per i controlli in un Windows Form in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="2d264-115">How to: Set ToolTips for Controls on a Windows Form at Design Time</span></span>](../../../../docs/framework/winforms/controls/how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time.md)  
 [<span data-ttu-id="2d264-116">Procedura: Modifica del ritardo del componente ToolTip di Windows Form</span><span class="sxs-lookup"><span data-stu-id="2d264-116">How to: Change the Delay of the Windows Forms ToolTip Component</span></span>](../../../../docs/framework/winforms/controls/how-to-change-the-delay-of-the-windows-forms-tooltip-component.md)

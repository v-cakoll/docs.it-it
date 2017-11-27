---
title: Sistemi di Guida nelle applicazioni Windows Forms
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Help [Windows Forms], adding to Windows applications
- Windows applications [Windows Forms], providing Help systems
- What's This? Help
- Help [Windows Forms], Windows Forms
- HelpProvider component [Windows Forms], providing Help in Windows applications
ms.assetid: 2a96a278-432c-41fc-9e3c-5bfedf5e1267
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 45d3385d008f823050f213252fdc2e1851cf422b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="help-systems-in-windows-forms-applications"></a><span data-ttu-id="007a8-102">Sistemi di Guida nelle applicazioni Windows Forms</span><span class="sxs-lookup"><span data-stu-id="007a8-102">Help Systems in Windows Forms Applications</span></span>
<span data-ttu-id="007a8-103">Uno di sicuramente, uno sviluppatore di applicazioni, gli utenti è un sistema di Guida competente.</span><span class="sxs-lookup"><span data-stu-id="007a8-103">One of the most important courtesies you, as a developer of applications, can furnish your users with is a competent Help system.</span></span> <span data-ttu-id="007a8-104">Si tratta di dove si attiverà quando essi o disorientanti.</span><span class="sxs-lookup"><span data-stu-id="007a8-104">This is where they will turn when they become confused or disoriented.</span></span> <span data-ttu-id="007a8-105">Fornire un sistema di Guida in un'applicazione basata su Windows viene eseguita facilmente tramite il [HelpProvider (componente)](../../../../docs/framework/winforms/controls/helpprovider-component-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="007a8-105">Providing a Help system in a Windows-based application is easily done by using the [HelpProvider Component](../../../../docs/framework/winforms/controls/helpprovider-component-windows-forms.md).</span></span>  
  
## <a name="different-types-of-help"></a><span data-ttu-id="007a8-106">Diversi tipi di Guida</span><span class="sxs-lookup"><span data-stu-id="007a8-106">Different Types of Help</span></span>  
 <span data-ttu-id="007a8-107">Il componente <xref:System.Windows.Forms.HelpProvider> di Windows Form viene usato per associare un file della Guida HTML Help 1.x, vale a dire un file .chm creato con HTML Help Workshop o un file .htm, alla propria applicazione basata su Windows.</span><span class="sxs-lookup"><span data-stu-id="007a8-107">The Windows Forms <xref:System.Windows.Forms.HelpProvider> component is used to associate an HTML Help 1.x Help file (either a .chm file, produced with the HTML Help Workshop, or an .htm file) with your Windows-based application.</span></span> <span data-ttu-id="007a8-108">Il <xref:System.Windows.Forms.HelpProvider> componente può essere utilizzato per fornire Guida sensibile al contesto per i controlli in Windows Form o controlli specifici.</span><span class="sxs-lookup"><span data-stu-id="007a8-108">The <xref:System.Windows.Forms.HelpProvider> component can be used to provide context-sensitive Help for controls on Windows Forms or specific controls.</span></span> <span data-ttu-id="007a8-109">Inoltre, il <xref:System.Windows.Forms.HelpProvider> componente è possibile aprire un file della Guida per aree specifiche, ad esempio la pagina principale di una tabella di contenuto, un indice o una funzione di ricerca.</span><span class="sxs-lookup"><span data-stu-id="007a8-109">Additionally, the <xref:System.Windows.Forms.HelpProvider> component can open a Help file to specific areas, such as the main page of a table of contents, an index, or a search function.</span></span> <span data-ttu-id="007a8-110">Per informazioni generali di <xref:System.Windows.Forms.HelpProvider> componente, vedere [Cenni preliminari sul componente HelpProvider](../../../../docs/framework/winforms/controls/helpprovider-component-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="007a8-110">For general information about the <xref:System.Windows.Forms.HelpProvider> component, see [HelpProvider Component Overview](../../../../docs/framework/winforms/controls/helpprovider-component-overview-windows-forms.md).</span></span> <span data-ttu-id="007a8-111">Per informazioni su come utilizzare il <xref:System.Windows.Forms.HelpProvider> componente per visualizzare la Guida rapida in Windows Form, vedere [procedura: visualizzazione della Guida](../../../../docs/framework/winforms/advanced/how-to-display-pop-up-help.md).</span><span class="sxs-lookup"><span data-stu-id="007a8-111">For information on how to use the <xref:System.Windows.Forms.HelpProvider> component to show pop-up Help on Windows Forms, see [How to: Display Pop-up Help](../../../../docs/framework/winforms/advanced/how-to-display-pop-up-help.md).</span></span> <span data-ttu-id="007a8-112">Per informazioni sull'utilizzo di <xref:System.Windows.Forms.ToolTip> componente per visualizzare la Guida specifica del controllo, vedere [controllo utilizzo delle descrizioni comandi](../../../../docs/framework/winforms/advanced/control-help-using-tooltips.md).</span><span class="sxs-lookup"><span data-stu-id="007a8-112">For information on using the <xref:System.Windows.Forms.ToolTip> component to show control-specific Help, see [Control Help Using ToolTips](../../../../docs/framework/winforms/advanced/control-help-using-tooltips.md).</span></span>  
  
 <span data-ttu-id="007a8-113">È possibile generare file di 1. x della Guida HTML con HTML Help Workshop.</span><span class="sxs-lookup"><span data-stu-id="007a8-113">You can generate HTML Help 1.x files with the HTML Help Workshop.</span></span> <span data-ttu-id="007a8-114">Per ulteriori informazioni sulla Guida HTML, vedere "HTML Help Workshop" o gli altri argomenti "Della Guida HTML" in MSDN.</span><span class="sxs-lookup"><span data-stu-id="007a8-114">For more information on HTML Help, see the "HTML Help Workshop" or the other "HTML Help" topics in MSDN.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="007a8-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="007a8-115">See Also</span></span>  
 [<span data-ttu-id="007a8-116">Integrazione della Guida dell'utente in Windows Form</span><span class="sxs-lookup"><span data-stu-id="007a8-116">Integrating User Help in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/integrating-user-help-in-windows-forms.md)  
 [<span data-ttu-id="007a8-117">Componente HelpProvider</span><span class="sxs-lookup"><span data-stu-id="007a8-117">HelpProvider Component</span></span>](../../../../docs/framework/winforms/controls/helpprovider-component-windows-forms.md)  
 [<span data-ttu-id="007a8-118">Componente ToolTip</span><span class="sxs-lookup"><span data-stu-id="007a8-118">ToolTip Component</span></span>](../../../../docs/framework/winforms/controls/tooltip-component-windows-forms.md)  
 [<span data-ttu-id="007a8-119">Panoramica sui Windows Form</span><span class="sxs-lookup"><span data-stu-id="007a8-119">Windows Forms Overview</span></span>](../../../../docs/framework/winforms/windows-forms-overview.md)  
 [<span data-ttu-id="007a8-120">Windows Form</span><span class="sxs-lookup"><span data-stu-id="007a8-120">Windows Forms</span></span>](../../../../docs/framework/winforms/index.md)

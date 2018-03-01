---
title: Cenni preliminari sul controllo Splitter (Windows Form)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- Splitter
helpviewer_keywords:
- Splitter control [Windows Forms], about Splitter control
ms.assetid: e2b6ab83-dfdd-40ec-9762-850702c82dcb
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 32d8829e7303ce23a22d0a01f2428a889ce4ae0f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="splitter-control-overview-windows-forms"></a><span data-ttu-id="9a75e-102">Cenni preliminari sul controllo Splitter (Windows Form)</span><span class="sxs-lookup"><span data-stu-id="9a75e-102">Splitter Control Overview (Windows Forms)</span></span>
> [!IMPORTANT]
>  <span data-ttu-id="9a75e-103">Sebbene <xref:System.Windows.Forms.SplitContainer> sostituisce e aggiunge la funzionalità per il <xref:System.Windows.Forms.Splitter> controllo delle versioni precedenti, <xref:System.Windows.Forms.Splitter> viene mantenuto per compatibilità con le versioni precedenti e un utilizzo futuro, se si sceglie.</span><span class="sxs-lookup"><span data-stu-id="9a75e-103">Although <xref:System.Windows.Forms.SplitContainer> replaces and adds functionality to the <xref:System.Windows.Forms.Splitter> control of previous versions, <xref:System.Windows.Forms.Splitter> is retained for both backward compatibility and future use if you choose.</span></span>  
  
 <span data-ttu-id="9a75e-104">Windows Form <xref:System.Windows.Forms.Splitter> controlli vengono usati per ridimensionare i controlli ancorati in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="9a75e-104">Windows Forms <xref:System.Windows.Forms.Splitter> controls are used to resize docked controls at run time.</span></span> <span data-ttu-id="9a75e-105">Il <xref:System.Windows.Forms.Splitter> controllo viene spesso usato nei form con controlli che dispongono di diverse lunghezze dei dati per la presentazione, ad esempio Esplora risorse, il cui riquadri contengono informazioni in momenti diversi.</span><span class="sxs-lookup"><span data-stu-id="9a75e-105">The <xref:System.Windows.Forms.Splitter> control is often used on forms with controls that have varying lengths of data to present, like Windows Explorer, whose data panes contain information of varying widths at different times.</span></span>  
  
## <a name="working-with-the-splitter-control"></a><span data-ttu-id="9a75e-106">Utilizzo del controllo barra di divisione</span><span class="sxs-lookup"><span data-stu-id="9a75e-106">Working with the Splitter Control</span></span>  
 <span data-ttu-id="9a75e-107">Quando l'utente posiziona il puntatore del mouse sul bordo alloggiamento di espansione di un controllo che può essere ridimensionato con un controllo splitter, il puntatore assume l'aspetto per indicare che è possibile ridimensionare il controllo.</span><span class="sxs-lookup"><span data-stu-id="9a75e-107">When the user points the mouse pointer at the undocked edge of a control that can be resized by a splitter control, the pointer changes its appearance to indicate that the control can be resized.</span></span> <span data-ttu-id="9a75e-108">Con il controllo barra di divisione, l'utente può ridimensionare il controllo ancorato immediatamente precedente.</span><span class="sxs-lookup"><span data-stu-id="9a75e-108">With the splitter control, the user can resize the docked control that is immediately before it.</span></span> <span data-ttu-id="9a75e-109">Pertanto, per consentire all'utente di ridimensionare un controllo ancorato in fase di esecuzione, ancorare il controllo deve essere ridimensionato per un bordo di un contenitore e quindi ancorare un controllo splitter sullo stesso lato del contenitore.</span><span class="sxs-lookup"><span data-stu-id="9a75e-109">Therefore, to enable the user to resize a docked control at run time, dock the control to be resized to an edge of a container, and then dock a splitter control to the same side of that container.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a75e-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9a75e-110">See Also</span></span>  
 <xref:System.Windows.Forms.SplitContainer>  
 [<span data-ttu-id="9a75e-111">Procedura: Ancorare i controlli in Windows Form</span><span class="sxs-lookup"><span data-stu-id="9a75e-111">How to: Dock Controls on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/how-to-dock-controls-on-windows-forms.md)  
 [<span data-ttu-id="9a75e-112">Controlli da usare in Windows Form</span><span class="sxs-lookup"><span data-stu-id="9a75e-112">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)

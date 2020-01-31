---
title: Panoramica del controllo Splitter
ms.date: 03/30/2017
f1_keywords:
- Splitter
helpviewer_keywords:
- Splitter control [Windows Forms], about Splitter control
ms.assetid: e2b6ab83-dfdd-40ec-9762-850702c82dcb
ms.openlocfilehash: 3d6da8daf9bb0e8df4f69554a87725a7ddb65acb
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742894"
---
# <a name="splitter-control-overview-windows-forms"></a><span data-ttu-id="6fb8b-102">Cenni preliminari sul controllo Splitter (Windows Form)</span><span class="sxs-lookup"><span data-stu-id="6fb8b-102">Splitter Control Overview (Windows Forms)</span></span>
> [!IMPORTANT]
> <span data-ttu-id="6fb8b-103">Anche se <xref:System.Windows.Forms.SplitContainer> sostituisce e aggiunge funzionalità al controllo <xref:System.Windows.Forms.Splitter> delle versioni precedenti, <xref:System.Windows.Forms.Splitter> viene mantenuta sia per la compatibilità con le versioni precedenti che per un uso futuro, se lo si sceglie.</span><span class="sxs-lookup"><span data-stu-id="6fb8b-103">Although <xref:System.Windows.Forms.SplitContainer> replaces and adds functionality to the <xref:System.Windows.Forms.Splitter> control of previous versions, <xref:System.Windows.Forms.Splitter> is retained for both backward compatibility and future use if you choose.</span></span>  
  
 <span data-ttu-id="6fb8b-104">Windows Forms controlli <xref:System.Windows.Forms.Splitter> vengono usati per ridimensionare i controlli ancorati in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="6fb8b-104">Windows Forms <xref:System.Windows.Forms.Splitter> controls are used to resize docked controls at run time.</span></span> <span data-ttu-id="6fb8b-105">Il controllo <xref:System.Windows.Forms.Splitter> viene spesso usato nei form con controlli con lunghezze diverse di dati da presentare, ad esempio Esplora risorse, i cui riquadri dati contengono informazioni di larghezze variabili in momenti diversi.</span><span class="sxs-lookup"><span data-stu-id="6fb8b-105">The <xref:System.Windows.Forms.Splitter> control is often used on forms with controls that have varying lengths of data to present, like Windows Explorer, whose data panes contain information of varying widths at different times.</span></span>  
  
## <a name="working-with-the-splitter-control"></a><span data-ttu-id="6fb8b-106">Utilizzo del controllo Splitter</span><span class="sxs-lookup"><span data-stu-id="6fb8b-106">Working with the Splitter Control</span></span>  
 <span data-ttu-id="6fb8b-107">Quando l'utente punta il puntatore del mouse sul bordo non ancorato di un controllo che può essere ridimensionato da un controllo Splitter, il puntatore cambia l'aspetto per indicare che è possibile ridimensionare il controllo.</span><span class="sxs-lookup"><span data-stu-id="6fb8b-107">When the user points the mouse pointer at the undocked edge of a control that can be resized by a splitter control, the pointer changes its appearance to indicate that the control can be resized.</span></span> <span data-ttu-id="6fb8b-108">Con il controllo Splitter, l'utente può ridimensionare il controllo ancorato che si trova immediatamente prima.</span><span class="sxs-lookup"><span data-stu-id="6fb8b-108">With the splitter control, the user can resize the docked control that is immediately before it.</span></span> <span data-ttu-id="6fb8b-109">Pertanto, per consentire all'utente di ridimensionare un controllo ancorato in fase di esecuzione, ancorare il controllo da ridimensionare a un bordo di un contenitore e quindi ancorare un controllo Splitter allo stesso lato del contenitore.</span><span class="sxs-lookup"><span data-stu-id="6fb8b-109">Therefore, to enable the user to resize a docked control at run time, dock the control to be resized to an edge of a container, and then dock a splitter control to the same side of that container.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6fb8b-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6fb8b-110">See also</span></span>

- <xref:System.Windows.Forms.SplitContainer>
- [<span data-ttu-id="6fb8b-111">Procedura: Ancorare i controlli in Windows Form</span><span class="sxs-lookup"><span data-stu-id="6fb8b-111">How to: Dock Controls on Windows Forms</span></span>](how-to-dock-controls-on-windows-forms.md)
- [<span data-ttu-id="6fb8b-112">Controlli da utilizzare in Windows Form</span><span class="sxs-lookup"><span data-stu-id="6fb8b-112">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)

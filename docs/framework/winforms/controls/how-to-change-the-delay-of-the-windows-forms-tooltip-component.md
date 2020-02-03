---
title: Modificare il ritardo del componente della descrizione comando
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- ToolTip component [Windows Forms], delay values
- tooltips [Windows Forms], delay values
- examples [Windows Forms], tooltips
ms.assetid: 08979ba7-dd84-477b-ab17-8d06e759be99
ms.openlocfilehash: 8ab0b0760e8c82d752eaada19f14cae57fa63fdc
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746583"
---
# <a name="how-to-change-the-delay-of-the-windows-forms-tooltip-component"></a><span data-ttu-id="3f33d-102">Procedura: modificare il ritardo del componente ToolTip di Windows Form</span><span class="sxs-lookup"><span data-stu-id="3f33d-102">How to: Change the Delay of the Windows Forms ToolTip Component</span></span>
<span data-ttu-id="3f33d-103">Sono disponibili più valori di ritardo che è possibile impostare per un componente Windows Forms <xref:System.Windows.Forms.ToolTip>.</span><span class="sxs-lookup"><span data-stu-id="3f33d-103">There are multiple delay values that you can set for a Windows Forms <xref:System.Windows.Forms.ToolTip> component.</span></span> <span data-ttu-id="3f33d-104">L'unità di misura per tutte queste proprietà è in millisecondi.</span><span class="sxs-lookup"><span data-stu-id="3f33d-104">The unit of measure for all these properties is milliseconds.</span></span> <span data-ttu-id="3f33d-105">La proprietà <xref:System.Windows.Forms.ToolTip.InitialDelay%2A> determina per quanto tempo l'utente deve puntare al controllo associato affinché venga visualizzata la stringa della descrizione comando.</span><span class="sxs-lookup"><span data-stu-id="3f33d-105">The <xref:System.Windows.Forms.ToolTip.InitialDelay%2A> property determines how long the user must point at the associated control for the ToolTip string to appear.</span></span> <span data-ttu-id="3f33d-106">La proprietà <xref:System.Windows.Forms.ToolTip.ReshowDelay%2A> imposta il numero di millisecondi necessari per la visualizzazione delle stringhe di descrizione comando successive quando il mouse passa da un controllo associato alla descrizione comando a un altro.</span><span class="sxs-lookup"><span data-stu-id="3f33d-106">The <xref:System.Windows.Forms.ToolTip.ReshowDelay%2A> property sets the number of milliseconds it takes for subsequent ToolTip strings to appear as the mouse moves from one ToolTip-associated control to another.</span></span> <span data-ttu-id="3f33d-107">La proprietà <xref:System.Windows.Forms.ToolTip.AutoPopDelay%2A> determina il periodo di tempo in cui viene visualizzata la stringa della descrizione comando.</span><span class="sxs-lookup"><span data-stu-id="3f33d-107">The <xref:System.Windows.Forms.ToolTip.AutoPopDelay%2A> property determines the length of time the ToolTip string is shown.</span></span> <span data-ttu-id="3f33d-108">È possibile impostare questi valori singolarmente oppure impostando il valore della proprietà <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A>; le altre proprietà delay vengono impostate in base al valore assegnato alla proprietà <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A>.</span><span class="sxs-lookup"><span data-stu-id="3f33d-108">You can set these values individually, or by setting the value of the <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> property; the other delay properties are set based on the value assigned to the <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> property.</span></span> <span data-ttu-id="3f33d-109">Se, ad esempio, <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> è impostato su un valore N, <xref:System.Windows.Forms.ToolTip.InitialDelay%2A> è impostato su N, <xref:System.Windows.Forms.ToolTip.ReshowDelay%2A> viene impostato sul valore di <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> diviso per cinque (o N/5) e <xref:System.Windows.Forms.ToolTip.AutoPopDelay%2A> viene impostato su un valore cinque volte superiore al valore della proprietà <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> (o 5N).</span><span class="sxs-lookup"><span data-stu-id="3f33d-109">For example, when <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> is set to a value N, <xref:System.Windows.Forms.ToolTip.InitialDelay%2A> is set to N, <xref:System.Windows.Forms.ToolTip.ReshowDelay%2A> is set to the value of <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> divided by five (or N/5), and <xref:System.Windows.Forms.ToolTip.AutoPopDelay%2A> is set to a value that is five times the value of the <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> property (or 5N).</span></span>  
  
### <a name="to-set-the-delay"></a><span data-ttu-id="3f33d-110">Per impostare il ritardo</span><span class="sxs-lookup"><span data-stu-id="3f33d-110">To set the delay</span></span>  
  
1. <span data-ttu-id="3f33d-111">Impostare le proprietà seguenti, come illustrato in questo esempio.</span><span class="sxs-lookup"><span data-stu-id="3f33d-111">Set the following properties as shown in this example.</span></span>  
  
    ```vb  
    ToolTip1.InitialDelay = 500  
    ToolTip1.ReshowDelay = 100  
    ToolTip1.AutoPopDelay = 5000  
    ```  
  
    ```csharp  
    ToolTip1.InitialDelay = 500;  
    ToolTip1.ReshowDelay = 100;  
    ToolTip1.AutoPopDelay = 5000;  
    ```  
  
    ```cpp  
    toolTip1->InitialDelay = 500;  
    toolTip1->ReshowDelay = 100;  
    toolTip1->AutoPopDelay = 5000;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="3f33d-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3f33d-112">See also</span></span>

- [<span data-ttu-id="3f33d-113">Panoramica sul componente ToolTip</span><span class="sxs-lookup"><span data-stu-id="3f33d-113">ToolTip Component Overview</span></span>](tooltip-component-overview-windows-forms.md)
- [<span data-ttu-id="3f33d-114">Procedura: Impostare le descrizioni comandi per i controlli in un Windows Form in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="3f33d-114">How to: Set ToolTips for Controls on a Windows Form at Design Time</span></span>](how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time.md)
- [<span data-ttu-id="3f33d-115">Componente ToolTip</span><span class="sxs-lookup"><span data-stu-id="3f33d-115">ToolTip Component</span></span>](tooltip-component-windows-forms.md)

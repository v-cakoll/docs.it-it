---
title: 'Procedura: modificare il ritardo del componente ToolTip di Windows Form'
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
ms.openlocfilehash: 20dcd941b142daa672312edb618a1c3e4597442d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33530429"
---
# <a name="how-to-change-the-delay-of-the-windows-forms-tooltip-component"></a><span data-ttu-id="b2299-102">Procedura: modificare il ritardo del componente ToolTip di Windows Form</span><span class="sxs-lookup"><span data-stu-id="b2299-102">How to: Change the Delay of the Windows Forms ToolTip Component</span></span>
<span data-ttu-id="b2299-103">Sono presenti più valori di ritardo che è possibile impostare per un Windows Form <xref:System.Windows.Forms.ToolTip> componente.</span><span class="sxs-lookup"><span data-stu-id="b2299-103">There are multiple delay values that you can set for a Windows Forms <xref:System.Windows.Forms.ToolTip> component.</span></span> <span data-ttu-id="b2299-104">L'unità di misura per tutte queste proprietà è millisecondi.</span><span class="sxs-lookup"><span data-stu-id="b2299-104">The unit of measure for all these properties is milliseconds.</span></span> <span data-ttu-id="b2299-105">Il <xref:System.Windows.Forms.ToolTip.InitialDelay%2A> proprietà determina quanto tempo l'utente deve sempre puntare superiore del controllo associato per la stringa di descrizione comando da visualizzare.</span><span class="sxs-lookup"><span data-stu-id="b2299-105">The <xref:System.Windows.Forms.ToolTip.InitialDelay%2A> property determines how long the user must point at the associated control for the ToolTip string to appear.</span></span> <span data-ttu-id="b2299-106">Il <xref:System.Windows.Forms.ToolTip.ReshowDelay%2A> proprietà imposta il numero di millisecondi necessario per le stringhe di descrizione comando successive mentre il mouse viene spostato da un controllo descrizione comandi associato a un altro.</span><span class="sxs-lookup"><span data-stu-id="b2299-106">The <xref:System.Windows.Forms.ToolTip.ReshowDelay%2A> property sets the number of milliseconds it takes for subsequent ToolTip strings to appear as the mouse moves from one ToolTip-associated control to another.</span></span> <span data-ttu-id="b2299-107">Il <xref:System.Windows.Forms.ToolTip.AutoPopDelay%2A> proprietà determina la lunghezza della stringa di descrizione comandi.</span><span class="sxs-lookup"><span data-stu-id="b2299-107">The <xref:System.Windows.Forms.ToolTip.AutoPopDelay%2A> property determines the length of time the ToolTip string is shown.</span></span> <span data-ttu-id="b2299-108">È possibile impostare questi valori, singolarmente o impostando il valore del <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> a; il ritardo di proprietà vengono impostate in base al valore assegnato alla proprietà di <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="b2299-108">You can set these values individually, or by setting the value of the <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> property; the other delay properties are set based on the value assigned to the <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> property.</span></span> <span data-ttu-id="b2299-109">Ad esempio, quando <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> è impostata su un valore N, <xref:System.Windows.Forms.ToolTip.InitialDelay%2A> è impostata su, N <xref:System.Windows.Forms.ToolTip.ReshowDelay%2A> è impostata sul valore di <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> diviso per cinque (o N/5) e <xref:System.Windows.Forms.ToolTip.AutoPopDelay%2A> è impostata su un valore che rappresenta il valore di cinque volte il <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> proprietà (o 5N).</span><span class="sxs-lookup"><span data-stu-id="b2299-109">For example, when <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> is set to a value N, <xref:System.Windows.Forms.ToolTip.InitialDelay%2A> is set to N, <xref:System.Windows.Forms.ToolTip.ReshowDelay%2A> is set to the value of <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> divided by five (or N/5), and <xref:System.Windows.Forms.ToolTip.AutoPopDelay%2A> is set to a value that is five times the value of the <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> property (or 5N).</span></span>  
  
### <a name="to-set-the-delay"></a><span data-ttu-id="b2299-110">Per impostare il ritardo</span><span class="sxs-lookup"><span data-stu-id="b2299-110">To set the delay</span></span>  
  
1.  <span data-ttu-id="b2299-111">Come illustrato in questo esempio, impostare le proprietà seguenti.</span><span class="sxs-lookup"><span data-stu-id="b2299-111">Set the following properties as shown in this example.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="b2299-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b2299-112">See Also</span></span>  
 [<span data-ttu-id="b2299-113">Panoramica sul componente ToolTip</span><span class="sxs-lookup"><span data-stu-id="b2299-113">ToolTip Component Overview</span></span>](../../../../docs/framework/winforms/controls/tooltip-component-overview-windows-forms.md)  
 [<span data-ttu-id="b2299-114">Procedura: Impostare le descrizioni comandi per i controlli in un Windows Form in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="b2299-114">How to: Set ToolTips for Controls on a Windows Form at Design Time</span></span>](../../../../docs/framework/winforms/controls/how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time.md)  
 [<span data-ttu-id="b2299-115">Componente ToolTip</span><span class="sxs-lookup"><span data-stu-id="b2299-115">ToolTip Component</span></span>](../../../../docs/framework/winforms/controls/tooltip-component-windows-forms.md)

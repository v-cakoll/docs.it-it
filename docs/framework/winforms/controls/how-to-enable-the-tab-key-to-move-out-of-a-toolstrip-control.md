---
title: 'Procedura: Abilitare il tasto TAB per uscire da un controllo ToolStrip'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], moving between
- TAB key [Windows Forms], enabling
- ToolStrip control [Windows Forms], moving from
ms.assetid: 40f9e88b-09a3-428e-8da8-c00bb65079c6
ms.openlocfilehash: a98c8a54389daa898c877a08f8cc2cae46a11da9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54663072"
---
# <a name="how-to-enable-the-tab-key-to-move-out-of-a-toolstrip-control"></a><span data-ttu-id="65c7e-102">Procedura: Abilitare il tasto TAB per uscire da un controllo ToolStrip</span><span class="sxs-lookup"><span data-stu-id="65c7e-102">How to: Enable the TAB Key to Move Out of a ToolStrip Control</span></span>
<span data-ttu-id="65c7e-103">Usare la procedura seguente per abilitare l'utente prema il tasto TAB per passare fuori un <xref:System.Windows.Forms.ToolStrip> al controllo successivo nell'ordine di tabulazione.</span><span class="sxs-lookup"><span data-stu-id="65c7e-103">Use the following procedure to enable the user to press the TAB key to move out of a <xref:System.Windows.Forms.ToolStrip> to the next control in the tab order.</span></span>  
  
 <span data-ttu-id="65c7e-104">Il <xref:System.Windows.Forms.ToolStrip> accetta la prima pressione del tasto TAB e i tasti di direzione consentono di selezionare elementi all'interno di <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="65c7e-104">The <xref:System.Windows.Forms.ToolStrip> accepts the first press of the TAB key, and the arrow keys select items within the <xref:System.Windows.Forms.ToolStrip>.</span></span> <span data-ttu-id="65c7e-105">Quando l'utente preme il tasto TAB una seconda volta, richiede all'utente il controllo successivo nell'ordine di tabulazione.</span><span class="sxs-lookup"><span data-stu-id="65c7e-105">When the user presses the TAB key a second time, it takes the user to the next control in the tab order.</span></span>  
  
### <a name="to-enable-the-user-to-press-the-tab-key-to-move-out-of-a-toolstrip-to-the-next-control"></a><span data-ttu-id="65c7e-106">Per consentire all'utente di premere il tasto TAB per uscire da un oggetto ToolStrip per il controllo successivo</span><span class="sxs-lookup"><span data-stu-id="65c7e-106">To enable the user to press the TAB key to move out of a ToolStrip to the next control</span></span>  
  
-   <span data-ttu-id="65c7e-107">Impostare il <xref:System.Windows.Forms.ToolStrip.TabStop%2A> proprietà del <xref:System.Windows.Forms.ToolStrip> a `true`.</span><span class="sxs-lookup"><span data-stu-id="65c7e-107">Set the <xref:System.Windows.Forms.ToolStrip.TabStop%2A> property of the <xref:System.Windows.Forms.ToolStrip> to `true`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65c7e-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="65c7e-108">See also</span></span>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStrip.TabStop%2A>
- [<span data-ttu-id="65c7e-109">Panoramica sul controllo ToolStrip</span><span class="sxs-lookup"><span data-stu-id="65c7e-109">ToolStrip Control Overview</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)

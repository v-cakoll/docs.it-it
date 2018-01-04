---
title: 'Procedura: creare pulsanti interruttore nei controlli ToolStrip'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toggle buttons [Windows Forms], creating
- examples [Windows Forms], toolbars
- ToolStrip control [Windows Forms], creating toggle buttons
ms.assetid: d9c197df-4c65-43f2-beee-b68b52b2befc
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5547b35bda8054b3ca41435e04855408d8a77c8f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-toggle-buttons-in-toolstrip-controls"></a><span data-ttu-id="3484a-102">Procedura: creare pulsanti interruttore nei controlli ToolStrip</span><span class="sxs-lookup"><span data-stu-id="3484a-102">How to: Create Toggle Buttons in ToolStrip Controls</span></span>
<span data-ttu-id="3484a-103">Quando un utente fa clic su un interruttore, appaiono incassato e mantiene tale aspetto fino a quando l'utente fa clic sul pulsante nuovo.</span><span class="sxs-lookup"><span data-stu-id="3484a-103">When a user clicks a toggle button, it appears sunken and retains the sunken appearance until the user clicks the button again.</span></span>  
  
### <a name="to-create-a-toggling-toolstripbutton"></a><span data-ttu-id="3484a-104">Per creare un ToolStripButton</span><span class="sxs-lookup"><span data-stu-id="3484a-104">To create a toggling ToolStripButton</span></span>  
  
-   <span data-ttu-id="3484a-105">Usare codice simile all'esempio di codice seguente.</span><span class="sxs-lookup"><span data-stu-id="3484a-105">Use code such as the following code example.</span></span> <span data-ttu-id="3484a-106">Questo codice presuppone che il modulo contiene un <xref:System.Windows.Forms.ToolStrip> controllo e che il relativo <xref:System.Windows.Forms.ToolStrip.Items%2A> raccolta contiene un <xref:System.Windows.Forms.ToolStripButton> chiamato `toolStripButton1`.</span><span class="sxs-lookup"><span data-stu-id="3484a-106">This code assumes that your form contains a <xref:System.Windows.Forms.ToolStrip> control, and that its <xref:System.Windows.Forms.ToolStrip.Items%2A> collection contains a <xref:System.Windows.Forms.ToolStripButton> called `toolStripButton1`.</span></span> <span data-ttu-id="3484a-107">Inoltre, presuppone che si dispone di un gestore eventi denominato `toolStripButton1_CheckedChanged`.</span><span class="sxs-lookup"><span data-stu-id="3484a-107">It also assumes that you have an event handler called `toolStripButton1_CheckedChanged`.</span></span>  
  
    ```vb  
    toolStripButton1.CheckOnClick = True  
    toolStripButton1.CheckedChanged AddressOf _  
    EventHandler(toolStripButton1_CheckedChanged);  
    ```  
  
    ```csharp  
    toolStripButton1.CheckOnClick = true;  
    toolStripButton1.CheckedChanged += new _  
    EventHandler(toolStripButton1_CheckedChanged);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="3484a-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3484a-108">See Also</span></span>  
 <xref:System.Windows.Forms.ToolStripButton>  
 [<span data-ttu-id="3484a-109">Panoramica sul controllo ToolStrip</span><span class="sxs-lookup"><span data-stu-id="3484a-109">ToolStrip Control Overview</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)

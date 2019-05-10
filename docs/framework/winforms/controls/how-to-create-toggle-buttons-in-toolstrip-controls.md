---
title: 'Procedura: Creare pulsanti interruttore nei controlli ToolStrip'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toggle buttons [Windows Forms], creating
- examples [Windows Forms], toolbars
- ToolStrip control [Windows Forms], creating toggle buttons
ms.assetid: d9c197df-4c65-43f2-beee-b68b52b2befc
ms.openlocfilehash: 21da5564bfeec01d448c23d3e734bdd16fc1566b
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64666426"
---
# <a name="how-to-create-toggle-buttons-in-toolstrip-controls"></a><span data-ttu-id="ca427-102">Procedura: Creare pulsanti interruttore nei controlli ToolStrip</span><span class="sxs-lookup"><span data-stu-id="ca427-102">How to: Create Toggle Buttons in ToolStrip Controls</span></span>
<span data-ttu-id="ca427-103">Quando un utente fa clic su un pulsante Mostra/Nascondi, viene visualizzato incassato e mantiene tale aspetto fino a quando l'utente fa clic sul pulsante nuovo.</span><span class="sxs-lookup"><span data-stu-id="ca427-103">When a user clicks a toggle button, it appears sunken and retains the sunken appearance until the user clicks the button again.</span></span>  
  
### <a name="to-create-a-toggling-toolstripbutton"></a><span data-ttu-id="ca427-104">Per creare un ToolStripButton</span><span class="sxs-lookup"><span data-stu-id="ca427-104">To create a toggling ToolStripButton</span></span>  
  
- <span data-ttu-id="ca427-105">Usare codice simile al codice seguente.</span><span class="sxs-lookup"><span data-stu-id="ca427-105">Use code such as the following code example.</span></span> <span data-ttu-id="ca427-106">Questo codice presuppone che il form contenga un <xref:System.Windows.Forms.ToolStrip> controllo e che il <xref:System.Windows.Forms.ToolStrip.Items%2A> raccolta contiene un <xref:System.Windows.Forms.ToolStripButton> chiamato `toolStripButton1`.</span><span class="sxs-lookup"><span data-stu-id="ca427-106">This code assumes that your form contains a <xref:System.Windows.Forms.ToolStrip> control, and that its <xref:System.Windows.Forms.ToolStrip.Items%2A> collection contains a <xref:System.Windows.Forms.ToolStripButton> called `toolStripButton1`.</span></span> <span data-ttu-id="ca427-107">Si presume anche che un gestore eventi chiamato `toolStripButton1_CheckedChanged`.</span><span class="sxs-lookup"><span data-stu-id="ca427-107">It also assumes that you have an event handler called `toolStripButton1_CheckedChanged`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ca427-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ca427-108">See also</span></span>

- <xref:System.Windows.Forms.ToolStripButton>
- [<span data-ttu-id="ca427-109">Panoramica sul controllo ToolStrip</span><span class="sxs-lookup"><span data-stu-id="ca427-109">ToolStrip Control Overview</span></span>](toolstrip-control-overview-windows-forms.md)

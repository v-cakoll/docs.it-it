---
title: 'Procedura: Riassegnare i controlli esistenti a un elemento padre diverso'
ms.date: 03/30/2017
helpviewer_keywords:
- container controls [Windows Forms], Windows Forms
- layout [Windows Forms], resizing
- layout [Windows Forms], child controls
ms.assetid: 5a5723ff-34e0-4b6f-a57b-be4ebe35cb34
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 84e662e0bd2689115abe128c6442e4462eed3e18
ms.sourcegitcommit: 37616676fde89153f563a485fc6159fc57326fc2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/23/2019
ms.locfileid: "69987032"
---
# <a name="how-to-reassign-existing-controls-to-a-different-parent"></a><span data-ttu-id="7bfbf-102">Procedura: Riassegnare i controlli esistenti a un padre diverso</span><span class="sxs-lookup"><span data-stu-id="7bfbf-102">How to: Reassign existing controls to a different parent</span></span>

<span data-ttu-id="7bfbf-103">È possibile assegnare i controlli presenti nel form a un nuovo controllo contenitore.</span><span class="sxs-lookup"><span data-stu-id="7bfbf-103">You can assign controls that exist on your form to a new container control.</span></span>

1. <span data-ttu-id="7bfbf-104">In Visual Studio trascinare tre <xref:System.Windows.Forms.Button> controlli dalla **casella degli strumenti** nel form.</span><span class="sxs-lookup"><span data-stu-id="7bfbf-104">In Visual Studio, drag three <xref:System.Windows.Forms.Button> controls from the **Toolbox** onto the form.</span></span> <span data-ttu-id="7bfbf-105">Posizionarli uno accanto a altro, ma lasciarli non allineati.</span><span class="sxs-lookup"><span data-stu-id="7bfbf-105">Position them near to each other, but leave them unaligned.</span></span>

2. <span data-ttu-id="7bfbf-106">Nella **Casella degli strumenti**fare clic sull'icona del controllo <xref:System.Windows.Forms.FlowLayoutPanel> .</span><span class="sxs-lookup"><span data-stu-id="7bfbf-106">In the **Toolbox**, click the <xref:System.Windows.Forms.FlowLayoutPanel> control icon.</span></span> <span data-ttu-id="7bfbf-107">Non trascinare l'icona nel form.</span><span class="sxs-lookup"><span data-stu-id="7bfbf-107">(Do not drag the icon onto the form.)</span></span>

3. <span data-ttu-id="7bfbf-108">Spostare il puntatore del mouse accanto ai tre controlli <xref:System.Windows.Forms.Button> .</span><span class="sxs-lookup"><span data-stu-id="7bfbf-108">Move the mouse pointer close to the three <xref:System.Windows.Forms.Button> controls.</span></span>

   <span data-ttu-id="7bfbf-109">Il puntatore assume la forma di un mirino con l'icona del controllo <xref:System.Windows.Forms.FlowLayoutPanel> associata.</span><span class="sxs-lookup"><span data-stu-id="7bfbf-109">The pointer changes to a crosshair with the <xref:System.Windows.Forms.FlowLayoutPanel> control icon attached.</span></span>

4. <span data-ttu-id="7bfbf-110">Fare clic e tenere premuto il pulsante del mouse.</span><span class="sxs-lookup"><span data-stu-id="7bfbf-110">Click and hold the mouse button.</span></span>

5. <span data-ttu-id="7bfbf-111">Trascinare il puntatore del mouse per disegnare la struttura del controllo <xref:System.Windows.Forms.FlowLayoutPanel> .</span><span class="sxs-lookup"><span data-stu-id="7bfbf-111">Drag the mouse pointer to draw the outline of the <xref:System.Windows.Forms.FlowLayoutPanel> control.</span></span>

6. <span data-ttu-id="7bfbf-112">Disegnare la struttura intorno ai tre controlli <xref:System.Windows.Forms.Button> .</span><span class="sxs-lookup"><span data-stu-id="7bfbf-112">Draw the outline around the three <xref:System.Windows.Forms.Button> controls.</span></span>

7. <span data-ttu-id="7bfbf-113">Rilasciare il pulsante del mouse.</span><span class="sxs-lookup"><span data-stu-id="7bfbf-113">Release the mouse button.</span></span>

   <span data-ttu-id="7bfbf-114">I tre controlli <xref:System.Windows.Forms.Button> sono stati inseriti nel controllo <xref:System.Windows.Forms.FlowLayoutPanel> .</span><span class="sxs-lookup"><span data-stu-id="7bfbf-114">The three <xref:System.Windows.Forms.Button> controls are now inserted into the <xref:System.Windows.Forms.FlowLayoutPanel> control.</span></span>

## <a name="see-also"></a><span data-ttu-id="7bfbf-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7bfbf-115">See also</span></span>

- <xref:System.Windows.Forms.FlowLayoutPanel>
- <xref:System.Windows.Forms.TableLayoutPanel>
- [<span data-ttu-id="7bfbf-116">Procedura dettagliata: Disposizione di controlli in Windows Forms tramite TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="7bfbf-116">Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [<span data-ttu-id="7bfbf-117">Procedura dettagliata: Disposizione di controlli in Windows Forms mediante guide di allineamento</span><span class="sxs-lookup"><span data-stu-id="7bfbf-117">Walkthrough: Arranging Controls on Windows Forms Using Snaplines</span></span>](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)

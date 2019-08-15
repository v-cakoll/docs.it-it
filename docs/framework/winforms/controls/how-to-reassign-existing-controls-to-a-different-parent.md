---
title: 'Procedura: Riassegnare i controlli esistenti a un elemento padre diverso'
ms.date: 03/30/2017
helpviewer_keywords:
- container controls [Windows Forms], Windows Forms
- layout [Windows Forms], resizing
- layout [Windows Forms], child controls
ms.assetid: 5a5723ff-34e0-4b6f-a57b-be4ebe35cb34
ms.openlocfilehash: a65b3c2b596a2d88ce4236aeadd86993bb268aa6
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/15/2019
ms.locfileid: "69039784"
---
# <a name="how-to-reassign-existing-controls-to-a-different-parent"></a><span data-ttu-id="d9e07-102">Procedura: Riassegnare i controlli esistenti a un elemento padre diverso</span><span class="sxs-lookup"><span data-stu-id="d9e07-102">How to: Reassign Existing Controls to a Different Parent</span></span>
<span data-ttu-id="d9e07-103">È possibile assegnare i controlli presenti nel form a un nuovo controllo contenitore.</span><span class="sxs-lookup"><span data-stu-id="d9e07-103">You can assign controls that exist on your form to a new container control.</span></span>

## <a name="to-reassign-existing-controls-to-a-different-parent"></a><span data-ttu-id="d9e07-104">Per riassegnare i controlli esistenti a un padre diverso</span><span class="sxs-lookup"><span data-stu-id="d9e07-104">To reassign existing controls to a different parent</span></span>

1. <span data-ttu-id="d9e07-105">Trascinare i tre controlli <xref:System.Windows.Forms.Button> dalla **Casella degli strumenti** al form.</span><span class="sxs-lookup"><span data-stu-id="d9e07-105">Drag three <xref:System.Windows.Forms.Button> controls from the **Toolbox** onto the form.</span></span>

     <span data-ttu-id="d9e07-106">Posizionarli uno accanto a altro, ma lasciarli non allineati.</span><span class="sxs-lookup"><span data-stu-id="d9e07-106">Position them near to each other, but leave them unaligned.</span></span>

2. <span data-ttu-id="d9e07-107">Nella **Casella degli strumenti**fare clic sull'icona del controllo <xref:System.Windows.Forms.FlowLayoutPanel> .</span><span class="sxs-lookup"><span data-stu-id="d9e07-107">In the **Toolbox**, click the <xref:System.Windows.Forms.FlowLayoutPanel> control icon.</span></span>

     <span data-ttu-id="d9e07-108">Non trascinare l'icona nel form.</span><span class="sxs-lookup"><span data-stu-id="d9e07-108">Do not drag the icon onto the form.</span></span>

3. <span data-ttu-id="d9e07-109">Spostare il puntatore del mouse accanto ai tre controlli <xref:System.Windows.Forms.Button> .</span><span class="sxs-lookup"><span data-stu-id="d9e07-109">Move the mouse pointer close to the three <xref:System.Windows.Forms.Button> controls.</span></span>

     <span data-ttu-id="d9e07-110">Il puntatore assume la forma di un mirino con l'icona del controllo <xref:System.Windows.Forms.FlowLayoutPanel> associata.</span><span class="sxs-lookup"><span data-stu-id="d9e07-110">The pointer changes to a crosshair with the <xref:System.Windows.Forms.FlowLayoutPanel> control icon attached.</span></span>

4. <span data-ttu-id="d9e07-111">Fare clic e tenere premuto il pulsante del mouse.</span><span class="sxs-lookup"><span data-stu-id="d9e07-111">Click and hold the mouse button.</span></span>

5. <span data-ttu-id="d9e07-112">Trascinare il puntatore del mouse per disegnare la struttura del controllo <xref:System.Windows.Forms.FlowLayoutPanel> .</span><span class="sxs-lookup"><span data-stu-id="d9e07-112">Drag the mouse pointer to draw the outline of the <xref:System.Windows.Forms.FlowLayoutPanel> control.</span></span>

6. <span data-ttu-id="d9e07-113">Disegnare la struttura intorno ai tre controlli <xref:System.Windows.Forms.Button> .</span><span class="sxs-lookup"><span data-stu-id="d9e07-113">Draw the outline around the three <xref:System.Windows.Forms.Button> controls.</span></span>

7. <span data-ttu-id="d9e07-114">Rilasciare il pulsante del mouse.</span><span class="sxs-lookup"><span data-stu-id="d9e07-114">Release the mouse button.</span></span>

     <span data-ttu-id="d9e07-115">I tre controlli <xref:System.Windows.Forms.Button> sono stati inseriti nel controllo <xref:System.Windows.Forms.FlowLayoutPanel> .</span><span class="sxs-lookup"><span data-stu-id="d9e07-115">The three <xref:System.Windows.Forms.Button> controls are now inserted into the <xref:System.Windows.Forms.FlowLayoutPanel> control.</span></span>

## <a name="see-also"></a><span data-ttu-id="d9e07-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d9e07-116">See also</span></span>

- <xref:System.Windows.Forms.FlowLayoutPanel>
- <xref:System.Windows.Forms.TableLayoutPanel>
- [<span data-ttu-id="d9e07-117">Disposizione di controlli in Windows Form</span><span class="sxs-lookup"><span data-stu-id="d9e07-117">Arranging Controls on Windows Forms</span></span>](arranging-controls-on-windows-forms.md)
- [<span data-ttu-id="d9e07-118">Procedura dettagliata: Disposizione di controlli in Windows Forms tramite TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="d9e07-118">Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [<span data-ttu-id="d9e07-119">Procedura dettagliata: Disposizione di controlli in Windows Forms mediante guide di allineamento</span><span class="sxs-lookup"><span data-stu-id="d9e07-119">Walkthrough: Arranging Controls on Windows Forms Using Snaplines</span></span>](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)

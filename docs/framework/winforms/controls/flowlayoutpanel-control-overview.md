---
title: Cenni preliminari sul controllo FlowLayoutPanel
ms.date: 03/30/2017
f1_keywords:
- FlowLayoutPanel
helpviewer_keywords:
- forms [Windows Forms], dynamic layout
- layout [Windows Forms], dynamic
- Windows Forms, dynamic layout
- FlowLayoutPanel control [Windows Forms], about FlowLayoutPanel control
ms.assetid: 3883e024-f5a0-456d-9c27-b4dfa1cc9045
ms.openlocfilehash: 260146cd901fe2b80a73c01060ccd55958cd169e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59203041"
---
# <a name="flowlayoutpanel-control-overview"></a><span data-ttu-id="5dab0-102">Cenni preliminari sul controllo FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="5dab0-102">FlowLayoutPanel Control Overview</span></span>
<span data-ttu-id="5dab0-103">Il controllo <xref:System.Windows.Forms.FlowLayoutPanel> dispone i contenuti in una direzione di flusso orizzontale o verticale.</span><span class="sxs-lookup"><span data-stu-id="5dab0-103">The <xref:System.Windows.Forms.FlowLayoutPanel> control arranges its contents in a horizontal or vertical flow direction.</span></span> <span data-ttu-id="5dab0-104">È possibile eseguire il wrapping dei contenuti del controllo da una riga a quella successiva o da una colonna a quella successiva.</span><span class="sxs-lookup"><span data-stu-id="5dab0-104">You can wrap the control's contents from one row to the next, or from one column to the next.</span></span> <span data-ttu-id="5dab0-105">In alternativa, è possibile troncare i contenuti.</span><span class="sxs-lookup"><span data-stu-id="5dab0-105">Alternately, you can clip instead of wrap its contents.</span></span>  
  
 <span data-ttu-id="5dab0-106">È possibile specificare la direzione del flusso impostando il valore della proprietà <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A>.</span><span class="sxs-lookup"><span data-stu-id="5dab0-106">You can specify the flow direction by setting the value of the <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A> property.</span></span> <span data-ttu-id="5dab0-107">Il controllo <xref:System.Windows.Forms.FlowLayoutPanel> inverte correttamente la direzione del flusso nei layout da destra a sinistra (RTL, Right-To-Left).</span><span class="sxs-lookup"><span data-stu-id="5dab0-107">The <xref:System.Windows.Forms.FlowLayoutPanel> control correctly reverses its flow direction in Right-to-Left (RTL) layouts.</span></span> <span data-ttu-id="5dab0-108">È anche possibile specificare se i contenuti del controllo <xref:System.Windows.Forms.FlowLayoutPanel> vengono sottoposti a wrapping o troncati impostando il valore della proprietà <xref:System.Windows.Forms.FlowLayoutPanel.WrapContents%2A>.</span><span class="sxs-lookup"><span data-stu-id="5dab0-108">You can also specify whether the <xref:System.Windows.Forms.FlowLayoutPanel> control's contents are wrapped or clipped by setting the value of the <xref:System.Windows.Forms.FlowLayoutPanel.WrapContents%2A> property.</span></span>  
  
 <span data-ttu-id="5dab0-109">Il controllo <xref:System.Windows.Forms.FlowLayoutPanel> viene automaticamente ridimensionato in base ai contenuti quando si imposta la proprietà <xref:System.Windows.Forms.Control.AutoSize%2A> su `true`.</span><span class="sxs-lookup"><span data-stu-id="5dab0-109">The <xref:System.Windows.Forms.FlowLayoutPanel> control automatically sizes to its contents when you set the <xref:System.Windows.Forms.Control.AutoSize%2A> property to `true`.</span></span> <span data-ttu-id="5dab0-110">Fornisce inoltre una **FlowBreak** proprietà ai controlli figlio.</span><span class="sxs-lookup"><span data-stu-id="5dab0-110">It also provides a **FlowBreak** property to its child controls.</span></span> <span data-ttu-id="5dab0-111">Impostando il valore della proprietà FlowBreak su `true` , il controllo <xref:System.Windows.Forms.FlowLayoutPanel> interrompe il layout dei controlli nella direzione di flusso corrente ed esegue il wrapping alla riga o colonna successiva.</span><span class="sxs-lookup"><span data-stu-id="5dab0-111">Setting the value of the FlowBreak property to `true` causes the <xref:System.Windows.Forms.FlowLayoutPanel> control to stop laying out controls in the current flow direction and wrap to the next row or column.</span></span>  
  
 <span data-ttu-id="5dab0-112">Qualsiasi controllo Windows Form può essere figlio del controllo <xref:System.Windows.Forms.FlowLayoutPanel>, tra cui altre istanze di <xref:System.Windows.Forms.FlowLayoutPanel>.</span><span class="sxs-lookup"><span data-stu-id="5dab0-112">Any Windows Forms control can be a child of the <xref:System.Windows.Forms.FlowLayoutPanel> control, including other instances of <xref:System.Windows.Forms.FlowLayoutPanel>.</span></span> <span data-ttu-id="5dab0-113">Con questa funzionalità, è possibile costruire layout sofisticati in grado di adattarsi alle dimensioni del form in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="5dab0-113">With this capability, you can construct sophisticated layouts that adapt to your form's dimensions at run time.</span></span>  
  
 <span data-ttu-id="5dab0-114">Vedere anche [procedura dettagliata: Disposizione dei controlli in Windows Form usando FlowLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md).</span><span class="sxs-lookup"><span data-stu-id="5dab0-114">Also see [Walkthrough: Arranging Controls on Windows Forms Using a FlowLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5dab0-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5dab0-115">See also</span></span>

- <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A>
- <xref:System.Windows.Forms.TableLayoutPanel>
- [<span data-ttu-id="5dab0-116">Controllo FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="5dab0-116">FlowLayoutPanel Control</span></span>](flowlayoutpanel-control-windows-forms.md)

---
title: Wrapping del controllo con ToolStripControlHost
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- ToolStrip control [Windows Forms], wrapping controls
- toolbars [Windows Forms], wrapping controls
- ToolStrip control [Windows Forms], hosting controls
ms.assetid: e2ce4990-661d-4882-a116-8a9eb575dc84
ms.openlocfilehash: c7dbe042623006ed9501016669d6451ba0667cbc
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76728181"
---
# <a name="how-to-wrap-a-windows-forms-control-with-toolstripcontrolhost"></a><span data-ttu-id="d3886-102">Procedura: eseguire il wrapping di un controllo Windows Form con ToolStripControlHost</span><span class="sxs-lookup"><span data-stu-id="d3886-102">How to: Wrap a Windows Forms Control with ToolStripControlHost</span></span>
<span data-ttu-id="d3886-103"><xref:System.Windows.Forms.ToolStripControlHost> è progettato per abilitare l'hosting di controlli Windows Form arbitrari usando il costruttore <xref:System.Windows.Forms.ToolStripControlHost> o estendendo direttamente <xref:System.Windows.Forms.ToolStripControlHost>.</span><span class="sxs-lookup"><span data-stu-id="d3886-103"><xref:System.Windows.Forms.ToolStripControlHost> is designed to enable hosting of arbitrary Windows Forms controls by using the <xref:System.Windows.Forms.ToolStripControlHost> constructor or by extending <xref:System.Windows.Forms.ToolStripControlHost> itself.</span></span> <span data-ttu-id="d3886-104">È più semplice eseguire il wrapping del controllo estendendo <xref:System.Windows.Forms.ToolStripControlHost> e implementando proprietà e metodi che espongono le proprietà e i metodi del controllo usati di frequente.</span><span class="sxs-lookup"><span data-stu-id="d3886-104">It is easier to wrap the control by extending <xref:System.Windows.Forms.ToolStripControlHost> and implementing properties and methods that expose frequently used properties and methods of the control.</span></span> <span data-ttu-id="d3886-105">È anche possibile esporre gli eventi del controllo a livello di <xref:System.Windows.Forms.ToolStripControlHost>.</span><span class="sxs-lookup"><span data-stu-id="d3886-105">You can also expose events for the control at the <xref:System.Windows.Forms.ToolStripControlHost> level.</span></span>  
  
### <a name="to-host-a-control-in-a-toolstripcontrolhost-by-derivation"></a><span data-ttu-id="d3886-106">Per ospitare un controllo in un oggetto ToolStripControlHost tramite derivazione</span><span class="sxs-lookup"><span data-stu-id="d3886-106">To host a control in a ToolStripControlHost by derivation</span></span>  
  
1. <span data-ttu-id="d3886-107">Estendere <xref:System.Windows.Forms.ToolStripControlHost>.</span><span class="sxs-lookup"><span data-stu-id="d3886-107">Extend <xref:System.Windows.Forms.ToolStripControlHost>.</span></span> <span data-ttu-id="d3886-108">Implementare un costruttore senza parametri che chiama il costruttore della classe base passando il controllo desiderato.</span><span class="sxs-lookup"><span data-stu-id="d3886-108">Implement a parameterless constructor that calls the base class constructor passing in the desired control.</span></span>  
  
     [!code-cpp[System.Windows.Forms.ToolStripControlHost#10](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/CPP/form1.cpp#10)]
     [!code-csharp[System.Windows.Forms.ToolStripControlHost#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/CS/form1.cs#10)]
     [!code-vb[System.Windows.Forms.ToolStripControlHost#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/VB/form1.vb#10)]  
  
2. <span data-ttu-id="d3886-109">Dichiarare una proprietà dello stesso tipo del controllo di cui è stato eseguito il wrapping e restituire `Control` come tipo corretto di controllo nella funzione di accesso della proprietà.</span><span class="sxs-lookup"><span data-stu-id="d3886-109">Declare a property of the same type as the wrapped control and return `Control` as the correct type of control in the property's accessor.</span></span>  
  
     [!code-cpp[System.Windows.Forms.ToolStripControlHost#11](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/CPP/form1.cpp#11)]
     [!code-csharp[System.Windows.Forms.ToolStripControlHost#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/CS/form1.cs#11)]
     [!code-vb[System.Windows.Forms.ToolStripControlHost#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/VB/form1.vb#11)]  
  
3. <span data-ttu-id="d3886-110">Esporre altre proprietà e metodi usati di frequente del controllo di cui è stato eseguito il wrapping con le proprietà e i metodi della classe estesa.</span><span class="sxs-lookup"><span data-stu-id="d3886-110">Expose other frequently used properties and methods of the wrapped control with properties and methods in the extended class.</span></span>  
  
     [!code-cpp[System.Windows.Forms.ToolStripControlHost#12](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/CPP/form1.cpp#12)]
     [!code-csharp[System.Windows.Forms.ToolStripControlHost#12](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/CS/form1.cs#12)]
     [!code-vb[System.Windows.Forms.ToolStripControlHost#12](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/VB/form1.vb#12)]  
  
4. <span data-ttu-id="d3886-111">Facoltativamente, eseguire l'override dei metodi <xref:System.Windows.Forms.ToolStripControlHost.OnSubscribeControlEvents%2A> e <xref:System.Windows.Forms.ToolStripControlHost.OnUnsubscribeControlEvents%2A> e aggiungere gli eventi del controllo che si vuole esporre.</span><span class="sxs-lookup"><span data-stu-id="d3886-111">Optionally, override the <xref:System.Windows.Forms.ToolStripControlHost.OnSubscribeControlEvents%2A>, and <xref:System.Windows.Forms.ToolStripControlHost.OnUnsubscribeControlEvents%2A> methods and add the control events you want to expose.</span></span>  
  
     [!code-cpp[System.Windows.Forms.ToolStripControlHost#16](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/CPP/form1.cpp#16)]
     [!code-csharp[System.Windows.Forms.ToolStripControlHost#16](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/CS/form1.cs#16)]
     [!code-vb[System.Windows.Forms.ToolStripControlHost#16](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/VB/form1.vb#16)]  
  
5. <span data-ttu-id="d3886-112">Eseguire il wrapping necessario per gli eventi che si vuole esporre.</span><span class="sxs-lookup"><span data-stu-id="d3886-112">Provide the necessary wrapping for the events you want to expose.</span></span>  
  
     [!code-cpp[System.Windows.Forms.ToolStripControlHost#17](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/CPP/form1.cpp#17)]
     [!code-csharp[System.Windows.Forms.ToolStripControlHost#17](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/CS/form1.cs#17)]
     [!code-vb[System.Windows.Forms.ToolStripControlHost#17](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/VB/form1.vb#17)]  
  
## <a name="example"></a><span data-ttu-id="d3886-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="d3886-113">Example</span></span>  
 [!code-cpp[System.Windows.Forms.ToolStripControlHost#13](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/CPP/form1.cpp#13)]
 [!code-csharp[System.Windows.Forms.ToolStripControlHost#13](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/CS/form1.cs#13)]
 [!code-vb[System.Windows.Forms.ToolStripControlHost#13](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/VB/form1.vb#13)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="d3886-114">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="d3886-114">Compiling the Code</span></span>  
  
<span data-ttu-id="d3886-115">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="d3886-115">This example requires:</span></span>
  
- <span data-ttu-id="d3886-116">Riferimenti agli assembly System e System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="d3886-116">References to the System and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3886-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d3886-117">See also</span></span>

- <xref:System.Windows.Forms.ToolStripControlHost>
- [<span data-ttu-id="d3886-118">Panoramica sul controllo ToolStrip</span><span class="sxs-lookup"><span data-stu-id="d3886-118">ToolStrip Control Overview</span></span>](toolstrip-control-overview-windows-forms.md)
- [<span data-ttu-id="d3886-119">Architettura del controllo ToolStrip</span><span class="sxs-lookup"><span data-stu-id="d3886-119">ToolStrip Control Architecture</span></span>](toolstrip-control-architecture.md)
- [<span data-ttu-id="d3886-120">Riepilogo della tecnologia ToolStrip</span><span class="sxs-lookup"><span data-stu-id="d3886-120">ToolStrip Technology Summary</span></span>](toolstrip-technology-summary.md)

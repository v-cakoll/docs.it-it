---
title: 'Procedura: implementare un oggetto PriorityBinding'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: data binding [WPF], PriorityBinding class
ms.assetid: d63b65ab-b3e9-4322-9aa8-1450f8d89532
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9753462908928eaf177e100a16186826bf4828ee
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-implement-prioritybinding"></a><span data-ttu-id="a41e9-102">Procedura: implementare un oggetto PriorityBinding</span><span class="sxs-lookup"><span data-stu-id="a41e9-102">How to: Implement PriorityBinding</span></span>
<span data-ttu-id="a41e9-103"><xref:System.Windows.Data.PriorityBinding>in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] funziona specificando un elenco di associazioni.</span><span class="sxs-lookup"><span data-stu-id="a41e9-103"><xref:System.Windows.Data.PriorityBinding> in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] works by specifying a list of bindings.</span></span> <span data-ttu-id="a41e9-104">L'elenco di associazioni è ordinato dalla priorità più alta alla priorità più bassa.</span><span class="sxs-lookup"><span data-stu-id="a41e9-104">The list of bindings is ordered from highest priority to lowest priority.</span></span> <span data-ttu-id="a41e9-105">Se l'associazione con la priorità più alta restituisce un valore correttamente quando viene elaborato è mai necessario elaborare altre associazioni nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="a41e9-105">If the highest priority binding returns a value successfully when it is processed then there is never a need to process the other bindings in the list.</span></span> <span data-ttu-id="a41e9-106">È possibile che l'associazione con la priorità più alta richiede molto tempo per essere valutata, verrà utilizzata la priorità più elevata successiva che restituisce un valore correttamente finché un'associazione di una priorità più alta restituisce un valore correttamente.</span><span class="sxs-lookup"><span data-stu-id="a41e9-106">It could be the case that the highest priority binding takes a long time to be evaluated, the next highest priority that returns a value successfully will be used until a binding of a higher priority returns a value successfully.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a41e9-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="a41e9-107">Example</span></span>  
 <span data-ttu-id="a41e9-108">Per illustrare come <xref:System.Windows.Data.PriorityBinding> funziona, il `AsyncDataSource` oggetto è stato creato con le seguenti tre proprietà: `FastDP`, `SlowerDP`, e `SlowestDP`.</span><span class="sxs-lookup"><span data-stu-id="a41e9-108">To demonstrate how <xref:System.Windows.Data.PriorityBinding> works, the `AsyncDataSource` object has been created with the following three properties: `FastDP`, `SlowerDP`, and `SlowestDP`.</span></span>  
  
 <span data-ttu-id="a41e9-109">La funzione di accesso get di `FastDP` restituisce il valore della `_fastDP` (membro dati).</span><span class="sxs-lookup"><span data-stu-id="a41e9-109">The get accessor of `FastDP` returns the value of the `_fastDP` data member.</span></span>  
  
 <span data-ttu-id="a41e9-110">La funzione di accesso get di `SlowerDP` attende 3 secondi prima di restituire il valore della `_slowerDP` (membro dati).</span><span class="sxs-lookup"><span data-stu-id="a41e9-110">The get accessor of `SlowerDP` waits for 3 seconds before returning the value of the `_slowerDP` data member.</span></span>  
  
 <span data-ttu-id="a41e9-111">La funzione di accesso get di `SlowestDP` attende 5 secondi prima di restituire il valore di `_slowestDP` (membro dati).</span><span class="sxs-lookup"><span data-stu-id="a41e9-111">The get accessor of `SlowestDP` waits for 5 seconds before returning the value of the `_slowestDP` data member.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a41e9-112">Questo esempio è solo per scopi dimostrativi.</span><span class="sxs-lookup"><span data-stu-id="a41e9-112">This example is for demonstration purposes only.</span></span> <span data-ttu-id="a41e9-113">Il [!INCLUDE[TLA#tla_net](../../../../includes/tlasharptla-net-md.md)] linee guida si consiglia di non definire le proprietà che gli ordini di grandezza più lente rispetto a un set di campi.</span><span class="sxs-lookup"><span data-stu-id="a41e9-113">The [!INCLUDE[TLA#tla_net](../../../../includes/tlasharptla-net-md.md)] guidelines recommend against defining properties that are orders of magnitude slower than a field set would be.</span></span> <span data-ttu-id="a41e9-114">Per ulteriori informazioni, vedere [NIB: scelta tra proprietà e metodi](http://msdn.microsoft.com/en-us/55825e8f-7e2e-448a-9505-7217cc91b1af).</span><span class="sxs-lookup"><span data-stu-id="a41e9-114">For more information, see [NIB: Choosing Between Properties and Methods](http://msdn.microsoft.com/en-us/55825e8f-7e2e-448a-9505-7217cc91b1af).</span></span>  
  
 [!code-csharp[PriorityBinding#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PriorityBinding/CSharp/Window1.xaml.cs#1)]
 [!code-vb[PriorityBinding#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PriorityBinding/VisualBasic/AsyncDataSource.vb#1)]  
  
 <span data-ttu-id="a41e9-115">Il <xref:System.Windows.Controls.TextBlock.Text%2A> proprietà associa a quanto sopra `AsyncDS` utilizzando <xref:System.Windows.Data.PriorityBinding>:</span><span class="sxs-lookup"><span data-stu-id="a41e9-115">The <xref:System.Windows.Controls.TextBlock.Text%2A> property binds to the above `AsyncDS` using <xref:System.Windows.Data.PriorityBinding>:</span></span>  
  
 [!code-xaml[PriorityBinding#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PriorityBinding/CSharp/Window1.xaml#2)]  
  
 <span data-ttu-id="a41e9-116">Quando il motore di associazione elabora il <xref:System.Windows.Data.Binding> oggetti, inizia con il primo <xref:System.Windows.Data.Binding>, che è associato il `SlowestDP` proprietà.</span><span class="sxs-lookup"><span data-stu-id="a41e9-116">When the binding engine processes the <xref:System.Windows.Data.Binding> objects, it starts with the first <xref:System.Windows.Data.Binding>, which is bound to the `SlowestDP` property.</span></span> <span data-ttu-id="a41e9-117">Quando questo <xref:System.Windows.Data.Binding> viene elaborato, non restituisce un valore correttamente perché rimane inattivo per 5 secondi, pertanto alla successiva <xref:System.Windows.Data.Binding> elemento viene elaborato.</span><span class="sxs-lookup"><span data-stu-id="a41e9-117">When this <xref:System.Windows.Data.Binding> is processed, it does not return a value successfully because it is sleeping for 5 seconds, so the next <xref:System.Windows.Data.Binding> element is processed.</span></span> <span data-ttu-id="a41e9-118">Alla successiva <xref:System.Windows.Data.Binding> non restituisce un valore correttamente perché rimane inattivo per 3 secondi.</span><span class="sxs-lookup"><span data-stu-id="a41e9-118">The next <xref:System.Windows.Data.Binding> does not return a value successfully because it is sleeping for 3 seconds.</span></span> <span data-ttu-id="a41e9-119">Il motore di associazione passa quindi alla successiva <xref:System.Windows.Data.Binding> elemento che è associato il `FastDP` proprietà.</span><span class="sxs-lookup"><span data-stu-id="a41e9-119">The binding engine then moves onto the next <xref:System.Windows.Data.Binding> element, which is bound to the `FastDP` property.</span></span> <span data-ttu-id="a41e9-120">Questo <xref:System.Windows.Data.Binding> restituisce il valore "Fast Value".</span><span class="sxs-lookup"><span data-stu-id="a41e9-120">This <xref:System.Windows.Data.Binding> returns the value "Fast Value".</span></span> <span data-ttu-id="a41e9-121">Il <xref:System.Windows.Controls.TextBlock> verrà visualizzato il valore "Fast Value".</span><span class="sxs-lookup"><span data-stu-id="a41e9-121">The <xref:System.Windows.Controls.TextBlock> now displays the value "Fast Value".</span></span>  
  
 <span data-ttu-id="a41e9-122">Dopo la scadenza di 3 secondi, il `SlowerDP` proprietà restituisce il valore "Slower Value".</span><span class="sxs-lookup"><span data-stu-id="a41e9-122">After 3 seconds elapses, the `SlowerDP` property returns the value "Slower Value".</span></span> <span data-ttu-id="a41e9-123">Il <xref:System.Windows.Controls.TextBlock> quindi Visualizza il valore "Slower Value".</span><span class="sxs-lookup"><span data-stu-id="a41e9-123">The <xref:System.Windows.Controls.TextBlock> then displays the value "Slower Value".</span></span>  
  
 <span data-ttu-id="a41e9-124">Dopo questo intervallo di 5 secondi, il `SlowestDP` proprietà restituisce il valore "lento".</span><span class="sxs-lookup"><span data-stu-id="a41e9-124">After 5 seconds elapses, the `SlowestDP` property returns the value "Slowest Value".</span></span> <span data-ttu-id="a41e9-125">Tale associazione ha la priorità più alta poiché è elencato prima.</span><span class="sxs-lookup"><span data-stu-id="a41e9-125">That binding has the highest priority because it is listed first.</span></span> <span data-ttu-id="a41e9-126">Il <xref:System.Windows.Controls.TextBlock> ora consente di visualizzare il valore "lento".</span><span class="sxs-lookup"><span data-stu-id="a41e9-126">The <xref:System.Windows.Controls.TextBlock> now displays the value "Slowest Value".</span></span>  
  
 <span data-ttu-id="a41e9-127">Vedere <xref:System.Windows.Data.PriorityBinding> per informazioni sulla definizione di un valore restituito correttamente da un'associazione.</span><span class="sxs-lookup"><span data-stu-id="a41e9-127">See <xref:System.Windows.Data.PriorityBinding> for information about what is considered a successful return value from a binding.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a41e9-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a41e9-128">See Also</span></span>  
 <xref:System.Windows.Data.Binding.IsAsync%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="a41e9-129">Cenni preliminari sull'associazione dati</span><span class="sxs-lookup"><span data-stu-id="a41e9-129">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="a41e9-130">Procedure relative</span><span class="sxs-lookup"><span data-stu-id="a41e9-130">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)

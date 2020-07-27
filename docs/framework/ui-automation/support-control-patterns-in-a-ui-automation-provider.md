---
title: Supportare pattern di controllo in un provider di automazione interfaccia utente
description: Informazioni su come implementare i pattern di controllo di supporto in un provider di automazione interfaccia utente in modo che le applicazioni client possano modificare i controlli e ottenere dati da essi.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- control patterns, supporting in UI Automation provider
- UI Automation, supporting control patterns in provider
ms.assetid: 0d635c35-ffa8-4dc8-bbc9-12fcd5445776
ms.openlocfilehash: 82300499520be6b820b361ebdeb56bbf3716afab
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/24/2020
ms.locfileid: "87163506"
---
# <a name="support-control-patterns-in-a-ui-automation-provider"></a><span data-ttu-id="29e4b-103">Supportare pattern di controllo in un provider di automazione interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="29e4b-103">Support Control Patterns in a UI Automation Provider</span></span>

> [!NOTE]
> <span data-ttu-id="29e4b-104">Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="29e4b-104">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="29e4b-105">Per informazioni aggiornate su [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], vedere [Windows Automation API: automazione interfaccia utente](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="29e4b-105">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>

<span data-ttu-id="29e4b-106">In questo argomento viene descritto come implementare uno o più pattern di controllo in un provider di automazione interfaccia utente in modo che le applicazioni client possano modificare i controlli e ottenere dati.</span><span class="sxs-lookup"><span data-stu-id="29e4b-106">This topic shows how to implement one or more control patterns on a UI Automation provider so that client applications can manipulate controls and get data from them.</span></span>

## <a name="support-control-patterns"></a><span data-ttu-id="29e4b-107">Supportare i pattern di controllo</span><span class="sxs-lookup"><span data-stu-id="29e4b-107">Support Control Patterns</span></span>

1. <span data-ttu-id="29e4b-108">Implementare le interfacce appropriate per i pattern di controllo che l'elemento deve supportare, ad esempio <xref:System.Windows.Automation.Provider.IInvokeProvider> per <xref:System.Windows.Automation.InvokePattern>.</span><span class="sxs-lookup"><span data-stu-id="29e4b-108">Implement the appropriate interfaces for the control patterns that the element should support, such as <xref:System.Windows.Automation.Provider.IInvokeProvider> for <xref:System.Windows.Automation.InvokePattern>.</span></span>

2. <span data-ttu-id="29e4b-109">Restituire l'oggetto che contiene l'implementazione di ciascuna interfaccia di controllo nell'implementazione di <xref:System.Windows.Automation.Provider.IRawElementProviderSimple.GetPatternProvider%2A?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="29e4b-109">Return the object containing your implementation of each control interface in your implementation of <xref:System.Windows.Automation.Provider.IRawElementProviderSimple.GetPatternProvider%2A?displayProperty=nameWithType></span></span>

## <a name="example"></a><span data-ttu-id="29e4b-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="29e4b-110">Example</span></span>

<span data-ttu-id="29e4b-111">Nell'esempio seguente viene illustrata un'implementazione di <xref:System.Windows.Automation.Provider.ISelectionProvider> per una casella di riepilogo personalizzata a selezione singola.</span><span class="sxs-lookup"><span data-stu-id="29e4b-111">The following example shows an implementation of <xref:System.Windows.Automation.Provider.ISelectionProvider> for a single-selection custom list box.</span></span> <span data-ttu-id="29e4b-112">Restituisce tre proprietà e ottiene l'elemento attualmente selezionato.</span><span class="sxs-lookup"><span data-stu-id="29e4b-112">It returns three properties and gets the currently selected item.</span></span>

[!code-csharp[UIAFragmentProvider_snip#119](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAFragmentProvider_snip/CSharp/ListPattern.cs#119)]
[!code-vb[UIAFragmentProvider_snip#119](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAFragmentProvider_snip/VisualBasic/ListPattern.vb#119)]

## <a name="example"></a><span data-ttu-id="29e4b-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="29e4b-113">Example</span></span>

<span data-ttu-id="29e4b-114">Nell'esempio seguente viene illustrata un'implementazione <xref:System.Windows.Automation.Provider.IRawElementProviderSimple.GetPatternProvider%2A> che restituisce la classe che implementa <xref:System.Windows.Automation.Provider.ISelectionProvider>.</span><span class="sxs-lookup"><span data-stu-id="29e4b-114">The following example shows an implementation of <xref:System.Windows.Automation.Provider.IRawElementProviderSimple.GetPatternProvider%2A> that returns the class implementing <xref:System.Windows.Automation.Provider.ISelectionProvider>.</span></span> <span data-ttu-id="29e4b-115">La maggior parte dei controlli casella di riepilogo supporta anche altri pattern, ma in questo esempio viene restituito un riferimento null ( `Nothing` in Microsoft Visual Basic .NET) per tutti gli altri identificatori di criteri.</span><span class="sxs-lookup"><span data-stu-id="29e4b-115">Most list box controls would support other patterns as well, but in this example a null reference (`Nothing` in Microsoft Visual Basic .NET) is returned for all other pattern identifiers.</span></span>

[!code-csharp[UIAFragmentProvider_snip#120](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAFragmentProvider_snip/CSharp/ListFragment.cs#120)]
[!code-vb[UIAFragmentProvider_snip#120](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAFragmentProvider_snip/VisualBasic/ListFragment.vb#120)]

## <a name="see-also"></a><span data-ttu-id="29e4b-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="29e4b-116">See also</span></span>

- [<span data-ttu-id="29e4b-117">Cenni preliminari sui provider di automazione interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="29e4b-117">UI Automation Providers Overview</span></span>](ui-automation-providers-overview.md)
- [<span data-ttu-id="29e4b-118">Implementazione del provider di automazione interfaccia utente lato server</span><span class="sxs-lookup"><span data-stu-id="29e4b-118">Server-Side UI Automation Provider Implementation</span></span>](server-side-ui-automation-provider-implementation.md)

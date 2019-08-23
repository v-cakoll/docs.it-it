---
title: Consentire la navigazione in un provider di frammenti di automazione interfaccia utente
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- UI Automation, enabling navigation in provider
- navigation, enabling in UI Automation provider
ms.assetid: 3cb6092a-58c9-4ca0-84a5-0e54d5d00a0d
ms.openlocfilehash: 6410a0f8a991f1dc21a298972182ec630723f627
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69932603"
---
# <a name="enable-navigation-in-a-ui-automation-fragment-provider"></a><span data-ttu-id="6949d-102">Consentire la navigazione in un provider di frammenti di automazione interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="6949d-102">Enable Navigation in a UI Automation Fragment Provider</span></span>
> [!NOTE]
> <span data-ttu-id="6949d-103">Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="6949d-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="6949d-104">Per informazioni aggiornate su, [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]vedere [API di automazione di Windows: Automazione](https://go.microsoft.com/fwlink/?LinkID=156746)interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="6949d-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="6949d-105">Questo argomento contiene codice di esempio che illustra come abilitare la navigazione in un provider di automazione interfaccia utente per un elemento che si trova all'interno di un frammento.</span><span class="sxs-lookup"><span data-stu-id="6949d-105">This topic contains example code that shows how to enable navigation in a UI Automation provider for an element that is within a fragment.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6949d-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="6949d-106">Example</span></span>  
 <span data-ttu-id="6949d-107">L'esempio di codice seguente implementa <xref:System.Windows.Automation.Provider.IRawElementProviderFragment.Navigate%2A> per un elemento dell'elenco all'interno di un elenco.</span><span class="sxs-lookup"><span data-stu-id="6949d-107">The following example code implements <xref:System.Windows.Automation.Provider.IRawElementProviderFragment.Navigate%2A> for a list item within a list.</span></span> <span data-ttu-id="6949d-108">L'elemento padre è l'elemento casella di riepilogo e gli elementi di pari livello sono altri elementi nella raccolta di elenchi.</span><span class="sxs-lookup"><span data-stu-id="6949d-108">The parent element is the list box element, and the sibling elements are other items in the list collection.</span></span> <span data-ttu-id="6949d-109">Il metodo restituisce `null` (`Nothing` in Visual Basic) per le istruzioni che non sono valide; in questo caso, <xref:System.Windows.Automation.Provider.NavigateDirection.FirstChild> e <xref:System.Windows.Automation.Provider.NavigateDirection.LastChild>in quanto l'elemento non ha figli.</span><span class="sxs-lookup"><span data-stu-id="6949d-109">The method returns `null` (`Nothing` in Visual Basic) for directions that are not valid; in this case, <xref:System.Windows.Automation.Provider.NavigateDirection.FirstChild> and <xref:System.Windows.Automation.Provider.NavigateDirection.LastChild>, because the element has no children.</span></span>  
  
 [!code-csharp[UIAFragmentProvider_snip#103](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAFragmentProvider_snip/CSharp/ListItemFragment.cs#103)]
 [!code-vb[UIAFragmentProvider_snip#103](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAFragmentProvider_snip/VisualBasic/ListItemFragment.vb#103)]  
  
## <a name="see-also"></a><span data-ttu-id="6949d-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6949d-110">See also</span></span>

- [<span data-ttu-id="6949d-111">Panoramica dei provider di automazione interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="6949d-111">UI Automation Providers Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-providers-overview.md)
- [<span data-ttu-id="6949d-112">Implementazione del provider di automazione interfaccia utente lato server</span><span class="sxs-lookup"><span data-stu-id="6949d-112">Server-Side UI Automation Provider Implementation</span></span>](../../../docs/framework/ui-automation/server-side-ui-automation-provider-implementation.md)

---
title: Restituire proprietà da un provider di automazione interfaccia utente
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- providers, UI Automation, returning properties
- properties, returned by UI Automation providers
- UI Automation, providers returning properties
ms.assetid: 5eba950e-b9e1-48eb-ab8e-b69db76bf589
ms.openlocfilehash: 5d073af121eae04a973667739c68a90d6dae9f2d
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/17/2019
ms.locfileid: "71042730"
---
# <a name="return-properties-from-a-ui-automation-provider"></a><span data-ttu-id="d7b1a-102">Restituire proprietà da un provider di automazione interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="d7b1a-102">Return Properties from a UI Automation Provider</span></span>
> [!NOTE]
> <span data-ttu-id="d7b1a-103">Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="d7b1a-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="d7b1a-104">Per informazioni aggiornate su, [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]vedere [API di automazione di Windows: Automazione](https://go.microsoft.com/fwlink/?LinkID=156746)interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="d7b1a-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="d7b1a-105">Questo argomento contiene codice di esempio che illustra come un provider di automazione interfaccia utente può restituire le proprietà di un elemento alle applicazioni client.</span><span class="sxs-lookup"><span data-stu-id="d7b1a-105">This topic contains sample code that shows how a UI Automation provider can return properties of an element to client applications.</span></span>  
  
 <span data-ttu-id="d7b1a-106">Per qualsiasi proprietà non supportata in modo esplicito, il provider deve restituire `null` (`Nothing` in Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="d7b1a-106">For any property it does not explicitly support, the provider must return `null` (`Nothing` in Visual Basic).</span></span> <span data-ttu-id="d7b1a-107">In questo modo [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] tenta di ottenere la proprietà da un'altra origine, ad esempio il provider della finestra host.</span><span class="sxs-lookup"><span data-stu-id="d7b1a-107">This ensures that [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] attempts to obtain the property from another source, such as the host window provider.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d7b1a-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="d7b1a-108">Example</span></span>  
 [!code-csharp[UIAFragmentProvider_snip#117](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAFragmentProvider_snip/CSharp/ListFragment.cs#117)]
 [!code-vb[UIAFragmentProvider_snip#117](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAFragmentProvider_snip/VisualBasic/ListFragment.vb#117)]  
  
## <a name="see-also"></a><span data-ttu-id="d7b1a-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d7b1a-109">See also</span></span>

- [<span data-ttu-id="d7b1a-110">Panoramica dei provider di automazione interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="d7b1a-110">UI Automation Providers Overview</span></span>](ui-automation-providers-overview.md)
- [<span data-ttu-id="d7b1a-111">Implementazione del provider di automazione interfaccia utente lato server</span><span class="sxs-lookup"><span data-stu-id="d7b1a-111">Server-Side UI Automation Provider Implementation</span></span>](server-side-ui-automation-provider-implementation.md)

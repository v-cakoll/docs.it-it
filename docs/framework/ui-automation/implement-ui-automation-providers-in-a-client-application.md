---
title: Implementare i provider di automazione interfaccia utente in un'applicazione client
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- client-side UI Automation provider, implementation within applications
- UI Automation, implementing client-side provider within application
ms.assetid: f325f0d8-1715-41ea-85ca-45b82ffea8bc
ms.openlocfilehash: b368ab3bc842fda5a99a64e0220093ebd60698b0
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59105924"
---
# <a name="implement-ui-automation-providers-in-a-client-application"></a><span data-ttu-id="68cd7-102">Implementare i provider di automazione interfaccia utente in un'applicazione client</span><span class="sxs-lookup"><span data-stu-id="68cd7-102">Implement UI Automation Providers in a Client Application</span></span>
> [!NOTE]
>  <span data-ttu-id="68cd7-103">Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="68cd7-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="68cd7-104">Per informazioni aggiornate sulle [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], vedere [Windows Automation API: Automazione interfaccia utente](https://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="68cd7-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="68cd7-105">Questo argomento contiene codice di esempio che illustra come implementare un provider di automazione interfaccia utente sul lato client all'interno di un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="68cd7-105">This topic contains example code that shows how to implement a client-side UI Automation provider within an application.</span></span>  
  
 <span data-ttu-id="68cd7-106">Si tratta di uno scenario comune.</span><span class="sxs-lookup"><span data-stu-id="68cd7-106">This is an uncommon scenario.</span></span> <span data-ttu-id="68cd7-107">In genere, un'applicazione client di automazione interfaccia utente usa provider lato server oppure provider lato client che si trovano in una DLL.</span><span class="sxs-lookup"><span data-stu-id="68cd7-107">Most often, a UI Automation client application uses server-side providers, or client-side providers that reside in a DLL.</span></span>  
  
## <a name="example"></a><span data-ttu-id="68cd7-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="68cd7-108">Example</span></span>  
 <span data-ttu-id="68cd7-109">L'esempio di codice seguente implementa un provider semplice per una finestra della console.</span><span class="sxs-lookup"><span data-stu-id="68cd7-109">The following example code implements a simple provider for a console window.</span></span> <span data-ttu-id="68cd7-110">Il codice non dispone di funzionalità utili, ma intende illustrare i passaggi di base dell'impostazione di un provider all'interno del codice client e della registrazione mediante <xref:System.Windows.Automation.ClientSettings.RegisterClientSideProviders%2A>.</span><span class="sxs-lookup"><span data-stu-id="68cd7-110">The code does not have any useful functionality, but is intended to demonstrate the basic steps in setting up a provider within client code and registering it by using <xref:System.Windows.Automation.ClientSettings.RegisterClientSideProviders%2A>.</span></span>  
  
 [!code-csharp[UIAClientSideProvider_snip#201](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClientSideProvider_snip/CSharp/ClientImplementationProgram.cs#201)]
 [!code-vb[UIAClientSideProvider_snip#201](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClientSideProvider_snip/visualbasic/clientimplementationprogram.vb#201)]  
  
## <a name="see-also"></a><span data-ttu-id="68cd7-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="68cd7-111">See also</span></span>

- [<span data-ttu-id="68cd7-112">Cenni preliminari sui provider di automazione interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="68cd7-112">UI Automation Providers Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-providers-overview.md)
- [<span data-ttu-id="68cd7-113">Registrare un assembly di provider lato client</span><span class="sxs-lookup"><span data-stu-id="68cd7-113">Register a Client-Side Provider Assembly</span></span>](../../../docs/framework/ui-automation/register-a-client-side-provider-assembly.md)
- [<span data-ttu-id="68cd7-114">Creare un provider di automazione interfaccia utente lato client</span><span class="sxs-lookup"><span data-stu-id="68cd7-114">Create a Client-Side UI Automation Provider</span></span>](../../../docs/framework/ui-automation/create-a-client-side-ui-automation-provider.md)
- [<span data-ttu-id="68cd7-115">Implementazione dei provider di automazione interfaccia utente sul lato client</span><span class="sxs-lookup"><span data-stu-id="68cd7-115">Client-Side UI Automation Provider Implementation</span></span>](../../../docs/framework/ui-automation/client-side-ui-automation-provider-implementation.md)

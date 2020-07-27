---
title: Implementare i provider di automazione interfaccia utente in un'applicazione client
description: Vedere un esempio di come implementare un provider di automazione interfaccia utente lato client in un'applicazione. Si noti che si tratta di uno scenario non comune.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- client-side UI Automation provider, implementation within applications
- UI Automation, implementing client-side provider within application
ms.assetid: f325f0d8-1715-41ea-85ca-45b82ffea8bc
ms.openlocfilehash: c604b68021886abdf06360bfb8afefe3640c12fe
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/24/2020
ms.locfileid: "87164115"
---
# <a name="implement-ui-automation-providers-in-a-client-application"></a><span data-ttu-id="a46e7-104">Implementare i provider di automazione interfaccia utente in un'applicazione client</span><span class="sxs-lookup"><span data-stu-id="a46e7-104">Implement UI Automation Providers in a Client Application</span></span>
> [!NOTE]
> <span data-ttu-id="a46e7-105">Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="a46e7-105">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="a46e7-106">Per informazioni aggiornate su [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], vedere [Windows Automation API: automazione interfaccia utente](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="a46e7-106">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="a46e7-107">Questo argomento contiene codice di esempio che illustra come implementare un provider di automazione interfaccia utente sul lato client all'interno di un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="a46e7-107">This topic contains example code that shows how to implement a client-side UI Automation provider within an application.</span></span>  
  
 <span data-ttu-id="a46e7-108">Si tratta di uno scenario comune.</span><span class="sxs-lookup"><span data-stu-id="a46e7-108">This is an uncommon scenario.</span></span> <span data-ttu-id="a46e7-109">In genere, un'applicazione client di automazione interfaccia utente usa provider lato server oppure provider lato client che si trovano in una DLL.</span><span class="sxs-lookup"><span data-stu-id="a46e7-109">Most often, a UI Automation client application uses server-side providers, or client-side providers that reside in a DLL.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a46e7-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="a46e7-110">Example</span></span>  
 <span data-ttu-id="a46e7-111">L'esempio di codice seguente implementa un provider semplice per una finestra della console.</span><span class="sxs-lookup"><span data-stu-id="a46e7-111">The following example code implements a simple provider for a console window.</span></span> <span data-ttu-id="a46e7-112">Il codice non dispone di funzionalità utili, ma intende illustrare i passaggi di base dell'impostazione di un provider all'interno del codice client e della registrazione mediante <xref:System.Windows.Automation.ClientSettings.RegisterClientSideProviders%2A>.</span><span class="sxs-lookup"><span data-stu-id="a46e7-112">The code does not have any useful functionality, but is intended to demonstrate the basic steps in setting up a provider within client code and registering it by using <xref:System.Windows.Automation.ClientSettings.RegisterClientSideProviders%2A>.</span></span>  
  
 [!code-csharp[UIAClientSideProvider_snip#201](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClientSideProvider_snip/CSharp/ClientImplementationProgram.cs#201)]
 [!code-vb[UIAClientSideProvider_snip#201](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClientSideProvider_snip/visualbasic/clientimplementationprogram.vb#201)]  
  
## <a name="see-also"></a><span data-ttu-id="a46e7-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a46e7-113">See also</span></span>

- [<span data-ttu-id="a46e7-114">Cenni preliminari sui provider di automazione interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="a46e7-114">UI Automation Providers Overview</span></span>](ui-automation-providers-overview.md)
- [<span data-ttu-id="a46e7-115">Registrare un assembly di provider lato client</span><span class="sxs-lookup"><span data-stu-id="a46e7-115">Register a Client-Side Provider Assembly</span></span>](register-a-client-side-provider-assembly.md)
- [<span data-ttu-id="a46e7-116">Creare un provider di automazione interfaccia utente lato client</span><span class="sxs-lookup"><span data-stu-id="a46e7-116">Create a Client-Side UI Automation Provider</span></span>](create-a-client-side-ui-automation-provider.md)
- [<span data-ttu-id="a46e7-117">Implementazione dei provider di automazione interfaccia utente sul lato client</span><span class="sxs-lookup"><span data-stu-id="a46e7-117">Client-Side UI Automation Provider Implementation</span></span>](client-side-ui-automation-provider-implementation.md)

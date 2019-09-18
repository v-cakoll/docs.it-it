---
title: Creare un provider di automazione interfaccia utente lato client
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- UI Automation, creating client-side provider
- client-side UI Automation provider, creating
ms.assetid: d91edaf2-be28-41ec-a508-af421cb43c3d
ms.openlocfilehash: 483090b38f58481c992ebabaf26e6cbcf9c6cae8
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/17/2019
ms.locfileid: "71043831"
---
# <a name="create-a-client-side-ui-automation-provider"></a><span data-ttu-id="10a0a-102">Creare un provider di automazione interfaccia utente lato client</span><span class="sxs-lookup"><span data-stu-id="10a0a-102">Create a Client-Side UI Automation Provider</span></span>
> [!NOTE]
> <span data-ttu-id="10a0a-103">Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="10a0a-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="10a0a-104">Per informazioni aggiornate su, [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]vedere [API di automazione di Windows: Automazione](https://go.microsoft.com/fwlink/?LinkID=156746)interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="10a0a-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="10a0a-105">Questo argomento contiene codice di esempio che illustra come implementare un provider di automazione interfaccia utente sul lato client.</span><span class="sxs-lookup"><span data-stu-id="10a0a-105">This topic contains example code that shows how to implement a client-side UI Automation provider.</span></span>  
  
## <a name="example"></a><span data-ttu-id="10a0a-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="10a0a-106">Example</span></span>  
 <span data-ttu-id="10a0a-107">Il codice di esempio seguente può essere compilato in una libreria di collegamento dinamico (DLL) che implementa un provider lato client molto semplice per una finestra della console.</span><span class="sxs-lookup"><span data-stu-id="10a0a-107">The following example code can be built into a dynamic-link library (DLL) that implements a very simple client-side provider for a console window.</span></span> <span data-ttu-id="10a0a-108">Il codice non dispone di funzionalità utili, ma intende illustrare i passaggi di base dell'impostazione di un assembly di provider che può essere registrato da un'applicazione client di automazione interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="10a0a-108">The code does not have any useful functionality, but is intended to demonstrate the basic steps in setting up a provider assembly that can be registered by a UI Automation client application.</span></span>  
  
 [!code-csharp[UIAClientSideProvider_snip#101](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClientSideProvider_snip/CSharp/CSProviderProgram.cs#101)]
 [!code-vb[UIAClientSideProvider_snip#101](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClientSideProvider_snip/visualbasic/csproviderprogram.vb#101)]  
  
## <a name="see-also"></a><span data-ttu-id="10a0a-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="10a0a-109">See also</span></span>

- [<span data-ttu-id="10a0a-110">Panoramica dei provider di automazione interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="10a0a-110">UI Automation Providers Overview</span></span>](ui-automation-providers-overview.md)
- [<span data-ttu-id="10a0a-111">Registrare un assembly di provider lato client</span><span class="sxs-lookup"><span data-stu-id="10a0a-111">Register a Client-Side Provider Assembly</span></span>](register-a-client-side-provider-assembly.md)

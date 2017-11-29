---
title: Creare un provider di automazione interfaccia utente lato client
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- UI Automation, creating client-side provider
- client-side UI Automation provider, creating
ms.assetid: d91edaf2-be28-41ec-a508-af421cb43c3d
caps.latest.revision: "11"
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: 5ff3723e016e01b7c249dc7533f2657ea607cd0c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="create-a-client-side-ui-automation-provider"></a><span data-ttu-id="52b97-102">Creare un provider di automazione interfaccia utente lato client</span><span class="sxs-lookup"><span data-stu-id="52b97-102">Create a Client-Side UI Automation Provider</span></span>
> [!NOTE]
>  <span data-ttu-id="52b97-103">Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="52b97-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="52b97-104">Per informazioni aggiornate su [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], vedere [Windows Automation API: automazione interfaccia utente](http://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="52b97-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="52b97-105">Questo argomento contiene codice di esempio che illustra come implementare un provider di automazione interfaccia utente sul lato client.</span><span class="sxs-lookup"><span data-stu-id="52b97-105">This topic contains example code that shows how to implement a client-side UI Automation provider.</span></span>  
  
## <a name="example"></a><span data-ttu-id="52b97-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="52b97-106">Example</span></span>  
 <span data-ttu-id="52b97-107">L'esempio di codice seguente può essere compilato in una [!INCLUDE[TLA#tla_dll](../../../includes/tlasharptla-dll-md.md)] che implementa un provider lato client molto semplice per una finestra della console.</span><span class="sxs-lookup"><span data-stu-id="52b97-107">The following example code can be built into a [!INCLUDE[TLA#tla_dll](../../../includes/tlasharptla-dll-md.md)] that implements a very simple client-side provider for a console window.</span></span> <span data-ttu-id="52b97-108">Il codice non dispone di funzionalità utili, ma intende illustrare i passaggi di base dell'impostazione di un assembly di provider che può essere registrato da un'applicazione client di automazione interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="52b97-108">The code does not have any useful functionality, but is intended to demonstrate the basic steps in setting up a provider assembly that can be registered by a UI Automation client application.</span></span>  
  
 [!code-csharp[UIAClientSideProvider_snip#101](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClientSideProvider_snip/CSharp/CSProviderProgram.cs#101)]
 [!code-vb[UIAClientSideProvider_snip#101](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClientSideProvider_snip/visualbasic/csproviderprogram.vb#101)]  
  
## <a name="see-also"></a><span data-ttu-id="52b97-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="52b97-109">See Also</span></span>  
 [<span data-ttu-id="52b97-110">Cenni preliminari sui provider di automazione interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="52b97-110">UI Automation Providers Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-providers-overview.md)  
 [<span data-ttu-id="52b97-111">Registrare un Assembly di Provider lato Client</span><span class="sxs-lookup"><span data-stu-id="52b97-111">Register a Client-Side Provider Assembly</span></span>](../../../docs/framework/ui-automation/register-a-client-side-provider-assembly.md)

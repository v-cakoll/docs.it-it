---
title: Esporre un provider di automazione dell'interfaccia utente lato server
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- expose a server-side UI Automation provider
- UI Automation, server-side provider, exposing
- server-side UI Automation provider, exposing
ms.assetid: 55d419c0-2201-4101-90c9-2888df4dbb47
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: 9700b9cfef92da48a61b033ecf7b7357c113a994
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33400380"
---
# <a name="expose-a-server-side-ui-automation-provider"></a><span data-ttu-id="4f4bf-102">Esporre un provider di automazione dell'interfaccia utente lato server</span><span class="sxs-lookup"><span data-stu-id="4f4bf-102">Expose a Server-side UI Automation Provider</span></span>
> [!NOTE]
>  <span data-ttu-id="4f4bf-103">Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="4f4bf-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="4f4bf-104">Per informazioni aggiornate su [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], vedere l'argomento sull' [API Automazione interfaccia utente di Windows](http://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="4f4bf-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="4f4bf-105">In questo argomento contiene codice di esempio che illustra come esporre un provider di automazione interfaccia utente lato server che è ospitato in un <xref:System.Windows.Forms.Control?displayProperty=nameWithType> finestra.</span><span class="sxs-lookup"><span data-stu-id="4f4bf-105">This topic contains example code that shows how to expose a server-side UI Automation provider that is hosted in a <xref:System.Windows.Forms.Control?displayProperty=nameWithType> window.</span></span>  
  
 <span data-ttu-id="4f4bf-106">L'esempio sostituisce la procedura della finestra per intercettare WM_GETOBJECT, ovvero il messaggio inviato dal servizio di base di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] quando un'applicazione client richiede informazioni sulla finestra.</span><span class="sxs-lookup"><span data-stu-id="4f4bf-106">The example overrides the window procedure to trap WM_GETOBJECT, which is the message sent by the [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] core service when a client application requests information about the window.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4f4bf-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="4f4bf-107">Example</span></span>  
 [!code-csharp[UIAFragmentProvider_snip#116](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAFragmentProvider_snip/CSharp/ListFragment.cs#116)]
 [!code-vb[UIAFragmentProvider_snip#116](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAFragmentProvider_snip/VisualBasic/ListFragment.vb#116)]  
  
## <a name="see-also"></a><span data-ttu-id="4f4bf-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4f4bf-108">See Also</span></span>  
 [<span data-ttu-id="4f4bf-109">Panoramica dei provider di automazione interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="4f4bf-109">UI Automation Providers Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-providers-overview.md)  
 [<span data-ttu-id="4f4bf-110">Implementazione del provider di automazione interfaccia utente lato server</span><span class="sxs-lookup"><span data-stu-id="4f4bf-110">Server-Side UI Automation Provider Implementation</span></span>](../../../docs/framework/ui-automation/server-side-ui-automation-provider-implementation.md)

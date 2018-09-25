---
title: Registrare un assembly di provider lato client
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- registering client-side provider assemblies
- client-side provider assemblies, registering
- UI Automation, registering provider assemblies
- provider assemblies, registering
ms.assetid: a03af4d9-2771-43cc-b07b-d468dca23190
author: Xansky
ms.author: mhopkins
ms.openlocfilehash: 51813a6b21114a60831aa1e51e69cad61805f0e4
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/25/2018
ms.locfileid: "47070422"
---
# <a name="register-a-client-side-provider-assembly"></a><span data-ttu-id="fe23d-102">Registrare un assembly di provider lato client</span><span class="sxs-lookup"><span data-stu-id="fe23d-102">Register a Client-Side Provider Assembly</span></span>
> [!NOTE]
>  <span data-ttu-id="fe23d-103">Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="fe23d-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="fe23d-104">Per informazioni aggiornate sulle [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], vedere [Windows Automation API: automazione dell'interfaccia utente](https://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="fe23d-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="fe23d-105">Questo argomento illustra come registrare una DLL contenente provider di automazione interfaccia utente lato client.</span><span class="sxs-lookup"><span data-stu-id="fe23d-105">This topic shows how to register a DLL that contains client-side UI Automation providers.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fe23d-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="fe23d-106">Example</span></span>  
 <span data-ttu-id="fe23d-107">L'esempio seguente illustra come registrare un assembly contenente un provider per una finestra della console.</span><span class="sxs-lookup"><span data-stu-id="fe23d-107">The following example shows how to register an assembly that contains a provider for a console window.</span></span>  
  
 [!code-csharp[UIAClientSideProvider_snip#102](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClientSideProvider_snip/CSharp/CSClientProgram.cs#102)]
 [!code-vb[UIAClientSideProvider_snip#102](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClientSideProvider_snip/visualbasic/csclientprogram.vb#102)]  
  
## <a name="see-also"></a><span data-ttu-id="fe23d-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fe23d-108">See Also</span></span>  
 [<span data-ttu-id="fe23d-109">Creare un provider di automazione interfaccia utente lato client</span><span class="sxs-lookup"><span data-stu-id="fe23d-109">Create a Client-Side UI Automation Provider</span></span>](../../../docs/framework/ui-automation/create-a-client-side-ui-automation-provider.md)

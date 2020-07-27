---
title: Registrare un assembly di provider lato client
description: Esaminare un esempio in cui viene illustrato come registrare una DLL contenente provider di automazione interfaccia utente lato client.
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
ms.openlocfilehash: 034a109bb69c08883c0943b7b6ef69a397a8e7e1
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/24/2020
ms.locfileid: "87168132"
---
# <a name="register-a-client-side-provider-assembly"></a><span data-ttu-id="6835b-103">Registrare un assembly di provider lato client</span><span class="sxs-lookup"><span data-stu-id="6835b-103">Register a Client-Side Provider Assembly</span></span>
> [!NOTE]
> <span data-ttu-id="6835b-104">Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="6835b-104">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="6835b-105">Per informazioni aggiornate su [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], vedere [Windows Automation API: automazione interfaccia utente](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="6835b-105">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="6835b-106">Questo argomento illustra come registrare una DLL contenente provider di automazione interfaccia utente lato client.</span><span class="sxs-lookup"><span data-stu-id="6835b-106">This topic shows how to register a DLL that contains client-side UI Automation providers.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6835b-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="6835b-107">Example</span></span>  
 <span data-ttu-id="6835b-108">L'esempio seguente illustra come registrare un assembly contenente un provider per una finestra della console.</span><span class="sxs-lookup"><span data-stu-id="6835b-108">The following example shows how to register an assembly that contains a provider for a console window.</span></span>  
  
 [!code-csharp[UIAClientSideProvider_snip#102](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClientSideProvider_snip/CSharp/CSClientProgram.cs#102)]
 [!code-vb[UIAClientSideProvider_snip#102](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClientSideProvider_snip/visualbasic/csclientprogram.vb#102)]  
  
## <a name="see-also"></a><span data-ttu-id="6835b-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6835b-109">See also</span></span>

- [<span data-ttu-id="6835b-110">Creare un provider di automazione interfaccia utente lato client</span><span class="sxs-lookup"><span data-stu-id="6835b-110">Create a Client-Side UI Automation Provider</span></span>](create-a-client-side-ui-automation-provider.md)

---
title: Generare eventi da un provider di automazione interfaccia utente
description: Vedere un esempio che illustra come generare un evento da un provider di automazione interfaccia utente. Genera un evento di automazione interfaccia utente nell'implementazione di un controllo Button personalizzato.
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, raising events
- raising UI Automation events
ms.assetid: 9fe2f01b-f7d8-49a8-a185-d4472b9976c0
ms.openlocfilehash: 75af4d05172e2417d44f76beab486de5eb3a4ba7
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/24/2020
ms.locfileid: "87168111"
---
# <a name="raise-events-from-a-ui-automation-provider"></a><span data-ttu-id="37f21-104">Generare eventi da un provider di automazione interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="37f21-104">Raise Events from a UI Automation Provider</span></span>
> [!NOTE]
> <span data-ttu-id="37f21-105">Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="37f21-105">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="37f21-106">Per informazioni aggiornate su [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], vedere [Windows Automation API: automazione interfaccia utente](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="37f21-106">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="37f21-107">Questo argomento contiene il codice di esempio che mostra come generare un evento da un provider di automazione interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="37f21-107">This topic contains example code that shows how to raise an event from a UI Automation provider.</span></span>  
  
## <a name="example"></a><span data-ttu-id="37f21-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="37f21-108">Example</span></span>  
 <span data-ttu-id="37f21-109">Nell'esempio seguente viene generato un evento [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] durante l'implementazione di un pulsante personalizzato.</span><span class="sxs-lookup"><span data-stu-id="37f21-109">In the following example, a [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] event is raised in the implementation of a custom button control.</span></span> <span data-ttu-id="37f21-110">L'implementazione consente a un'applicazione client di automazione interfaccia utente di simulare il clic di un pulsante.</span><span class="sxs-lookup"><span data-stu-id="37f21-110">The implementation enables a UI Automation client application to simulate a button click.</span></span>  
  
 <span data-ttu-id="37f21-111">Per evitare un'elaborazione non necessaria, l'esempio controlla <xref:System.Windows.Automation.Provider.AutomationInteropProvider.ClientsAreListening%2A> per verificare se devono essere generati eventi.</span><span class="sxs-lookup"><span data-stu-id="37f21-111">To avoid unnecessary processing, the example checks <xref:System.Windows.Automation.Provider.AutomationInteropProvider.ClientsAreListening%2A> to see whether events should be raised.</span></span>  
  
 [!code-csharp[UIAProvider_snip#150](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAProvider_snip/CSharp/FragmentRoot.cs#150)]  
  
## <a name="see-also"></a><span data-ttu-id="37f21-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="37f21-112">See also</span></span>

- [<span data-ttu-id="37f21-113">Cenni preliminari sui provider di automazione interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="37f21-113">UI Automation Providers Overview</span></span>](ui-automation-providers-overview.md)

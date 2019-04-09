---
title: Generare eventi da un provider di automazione interfaccia utente
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, raising events
- raising UI Automation events
ms.assetid: 9fe2f01b-f7d8-49a8-a185-d4472b9976c0
ms.openlocfilehash: 3deb4c6716d83af4b05e15b5b8a4b89e28317406
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59138697"
---
# <a name="raise-events-from-a-ui-automation-provider"></a><span data-ttu-id="ece07-102">Generare eventi da un provider di automazione interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="ece07-102">Raise Events from a UI Automation Provider</span></span>
> [!NOTE]
>  <span data-ttu-id="ece07-103">Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="ece07-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="ece07-104">Per informazioni aggiornate sulle [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], vedere [Windows Automation API: Automazione interfaccia utente](https://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="ece07-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="ece07-105">Questo argomento contiene il codice di esempio che mostra come generare un evento da un provider di automazione interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="ece07-105">This topic contains example code that shows how to raise an event from a UI Automation provider.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ece07-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="ece07-106">Example</span></span>  
 <span data-ttu-id="ece07-107">Nell'esempio seguente viene generato un evento [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] durante l'implementazione di un pulsante personalizzato.</span><span class="sxs-lookup"><span data-stu-id="ece07-107">In the following example, a [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] event is raised in the implementation of a custom button control.</span></span> <span data-ttu-id="ece07-108">L'implementazione consente a un'applicazione client di automazione interfaccia utente di simulare il clic di un pulsante.</span><span class="sxs-lookup"><span data-stu-id="ece07-108">The implementation enables a UI Automation client application to simulate a button click.</span></span>  
  
 <span data-ttu-id="ece07-109">Per evitare un'elaborazione non necessaria, l'esempio controlla <xref:System.Windows.Automation.Provider.AutomationInteropProvider.ClientsAreListening%2A> per verificare se devono essere generati eventi.</span><span class="sxs-lookup"><span data-stu-id="ece07-109">To avoid unnecessary processing, the example checks <xref:System.Windows.Automation.Provider.AutomationInteropProvider.ClientsAreListening%2A> to see whether events should be raised.</span></span>  
  
 [!code-csharp[UIAProvider_snip#150](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAProvider_snip/CSharp/FragmentRoot.cs#150)]  
  
## <a name="see-also"></a><span data-ttu-id="ece07-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ece07-110">See also</span></span>

- [<span data-ttu-id="ece07-111">Cenni preliminari sui provider di automazione interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="ece07-111">UI Automation Providers Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-providers-overview.md)

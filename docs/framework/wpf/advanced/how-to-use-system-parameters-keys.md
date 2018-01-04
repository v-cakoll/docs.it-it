---
title: 'Procedura: Usare chiavi dei parametri di sistema'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- resource keys [WPF], SystemParameters class
- classes [WPF], SystemParameters
ms.assetid: 77571283-d16c-45bb-9f69-cafbbf72b21e
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0b2a7352540456b459428dd87f6c60be0b8bc08b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-system-parameters-keys"></a><span data-ttu-id="92b13-102">Procedura: Usare chiavi dei parametri di sistema</span><span class="sxs-lookup"><span data-stu-id="92b13-102">How to: Use System Parameters Keys</span></span>
<span data-ttu-id="92b13-103">Le risorse di sistema espongono diverse metriche di sistema come risorse per consentire agli sviluppatori di creare oggetti visivi coerenti con le impostazioni di sistema.</span><span class="sxs-lookup"><span data-stu-id="92b13-103">System resources expose a number of system metrics as resources to help developers create visuals that are consistent with system settings.</span></span> <span data-ttu-id="92b13-104"><xref:System.Windows.SystemParameters>è una classe che contiene i valori di parametro di sistema e che l'associazione ai valori delle chiavi della risorsa, ad esempio, <xref:System.Windows.SystemParameters.FullPrimaryScreenHeight%2A> e <xref:System.Windows.SystemParameters.FullPrimaryScreenHeightKey%2A>.</span><span class="sxs-lookup"><span data-stu-id="92b13-104"><xref:System.Windows.SystemParameters> is a class that contains both system parameter values and resource keys that bind to the values—for example, <xref:System.Windows.SystemParameters.FullPrimaryScreenHeight%2A> and <xref:System.Windows.SystemParameters.FullPrimaryScreenHeightKey%2A>.</span></span> <span data-ttu-id="92b13-105">Le metriche dei parametri di sistema possono essere usate come risorse statiche o dinamiche.</span><span class="sxs-lookup"><span data-stu-id="92b13-105">System parameter metrics can be used as either static or dynamic resources.</span></span> <span data-ttu-id="92b13-106">Usare una risorsa dinamica per aggiornare automaticamente le metriche dei parametri durante l'esecuzione dell'applicazione; in caso contrario, usare una risorsa statica.</span><span class="sxs-lookup"><span data-stu-id="92b13-106">Use a dynamic resource if you want the parameter metric to update automatically while the application runs; otherwise use a static resource.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="92b13-107">Risorse dinamiche contenere la parola chiave *chiave* aggiunto al nome della proprietà.</span><span class="sxs-lookup"><span data-stu-id="92b13-107">Dynamic resources have the keyword *Key* appended to the property name.</span></span>  
  
 <span data-ttu-id="92b13-108">L'esempio seguente illustra come accedere alle risorse dinamiche dei parametri di sistema e usarle per applicare uno stile a un pulsante o personalizzarlo.</span><span class="sxs-lookup"><span data-stu-id="92b13-108">The following example shows how to access and use system parameter dynamic resources to style or customize a button.</span></span> <span data-ttu-id="92b13-109">Questo [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] viene ridimensionato un pulsante assegnando <xref:System.Windows.SystemParameters> valori di larghezza e altezza del pulsante.</span><span class="sxs-lookup"><span data-stu-id="92b13-109">This [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] example sizes a button by assigning <xref:System.Windows.SystemParameters> values to the button's width and height.</span></span>  
  
## <a name="example"></a><span data-ttu-id="92b13-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="92b13-110">Example</span></span>  
 [!code-xaml[SystemRes_snip#ParameterDynamicResources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/MyApp.xaml#parameterdynamicresources)]  
  
## <a name="see-also"></a><span data-ttu-id="92b13-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="92b13-111">See Also</span></span>  
 [<span data-ttu-id="92b13-112">Disegnare un'area con un pennello di sistema</span><span class="sxs-lookup"><span data-stu-id="92b13-112">Paint an Area with a System Brush</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-paint-an-area-with-a-system-brush.md)  
 [<span data-ttu-id="92b13-113">Utilizzare la classe SystemFonts</span><span class="sxs-lookup"><span data-stu-id="92b13-113">Use SystemFonts</span></span>](../../../../docs/framework/wpf/advanced/how-to-use-systemfonts.md)  
 [<span data-ttu-id="92b13-114">Utilizzare SystemParameters</span><span class="sxs-lookup"><span data-stu-id="92b13-114">Use SystemParameters</span></span>](../../../../docs/framework/wpf/advanced/how-to-use-systemparameters.md)

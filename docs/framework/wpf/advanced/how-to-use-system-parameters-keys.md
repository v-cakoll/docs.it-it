---
title: 'Procedura: Usare le chiavi dei parametri di sistema'
ms.date: 03/30/2017
helpviewer_keywords:
- resource keys [WPF], SystemParameters class
- classes [WPF], SystemParameters
ms.assetid: 77571283-d16c-45bb-9f69-cafbbf72b21e
ms.openlocfilehash: edacb4b98ab01f081f668dc3374f6588492210d9
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69918376"
---
# <a name="how-to-use-system-parameters-keys"></a><span data-ttu-id="d8fc1-102">Procedura: Usare le chiavi dei parametri di sistema</span><span class="sxs-lookup"><span data-stu-id="d8fc1-102">How to: Use System Parameters Keys</span></span>
<span data-ttu-id="d8fc1-103">Le risorse di sistema espongono diverse metriche di sistema come risorse per consentire agli sviluppatori di creare oggetti visivi coerenti con le impostazioni di sistema.</span><span class="sxs-lookup"><span data-stu-id="d8fc1-103">System resources expose a number of system metrics as resources to help developers create visuals that are consistent with system settings.</span></span> <span data-ttu-id="d8fc1-104"><xref:System.Windows.SystemParameters>è una classe che contiene sia i valori dei parametri di sistema che le chiavi di risorsa associate ai valori, <xref:System.Windows.SystemParameters.FullPrimaryScreenHeight%2A> ad <xref:System.Windows.SystemParameters.FullPrimaryScreenHeightKey%2A>esempio e.</span><span class="sxs-lookup"><span data-stu-id="d8fc1-104"><xref:System.Windows.SystemParameters> is a class that contains both system parameter values and resource keys that bind to the values—for example, <xref:System.Windows.SystemParameters.FullPrimaryScreenHeight%2A> and <xref:System.Windows.SystemParameters.FullPrimaryScreenHeightKey%2A>.</span></span> <span data-ttu-id="d8fc1-105">Le metriche dei parametri di sistema possono essere usate come risorse statiche o dinamiche.</span><span class="sxs-lookup"><span data-stu-id="d8fc1-105">System parameter metrics can be used as either static or dynamic resources.</span></span> <span data-ttu-id="d8fc1-106">Usare una risorsa dinamica per aggiornare automaticamente le metriche dei parametri durante l'esecuzione dell'applicazione; in caso contrario, usare una risorsa statica.</span><span class="sxs-lookup"><span data-stu-id="d8fc1-106">Use a dynamic resource if you want the parameter metric to update automatically while the application runs; otherwise use a static resource.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d8fc1-107">Per le risorse dinamiche è stata aggiunta la parola *chiave Key* al nome della proprietà.</span><span class="sxs-lookup"><span data-stu-id="d8fc1-107">Dynamic resources have the keyword *Key* appended to the property name.</span></span>  
  
 <span data-ttu-id="d8fc1-108">L'esempio seguente illustra come accedere alle risorse dinamiche dei parametri di sistema e usarle per applicare uno stile a un pulsante o personalizzarlo.</span><span class="sxs-lookup"><span data-stu-id="d8fc1-108">The following example shows how to access and use system parameter dynamic resources to style or customize a button.</span></span> <span data-ttu-id="d8fc1-109">Questo [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] esempio consente di ridimensionare un pulsante <xref:System.Windows.SystemParameters> assegnando valori alla larghezza e all'altezza del pulsante.</span><span class="sxs-lookup"><span data-stu-id="d8fc1-109">This [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] example sizes a button by assigning <xref:System.Windows.SystemParameters> values to the button's width and height.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d8fc1-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="d8fc1-110">Example</span></span>  
 [!code-xaml[SystemRes_snip#ParameterDynamicResources](~/samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/MyApp.xaml#parameterdynamicresources)]  
  
## <a name="see-also"></a><span data-ttu-id="d8fc1-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d8fc1-111">See also</span></span>

- [<span data-ttu-id="d8fc1-112">Disegnare un'area con un pennello di sistema</span><span class="sxs-lookup"><span data-stu-id="d8fc1-112">Paint an Area with a System Brush</span></span>](../graphics-multimedia/how-to-paint-an-area-with-a-system-brush.md)
- [<span data-ttu-id="d8fc1-113">Utilizzare la classe SystemFonts</span><span class="sxs-lookup"><span data-stu-id="d8fc1-113">Use SystemFonts</span></span>](how-to-use-systemfonts.md)
- [<span data-ttu-id="d8fc1-114">Utilizzare SystemParameters</span><span class="sxs-lookup"><span data-stu-id="d8fc1-114">Use SystemParameters</span></span>](how-to-use-systemparameters.md)

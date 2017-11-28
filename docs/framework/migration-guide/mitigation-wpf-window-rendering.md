---
title: 'Mitigazione: Rendering di finestre WPF'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 28ed6bf8-141b-4b73-a4e3-44a99fae5084
caps.latest.revision: "3"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 57d4cc56cc8d3a4dc3614043779eb09d7a8b8e25
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="mitigation-wpf-window-rendering"></a><span data-ttu-id="1d943-102">Mitigazione: Rendering di finestre WPF</span><span class="sxs-lookup"><span data-stu-id="1d943-102">Mitigation: WPF Window Rendering</span></span>
<span data-ttu-id="1d943-103">In [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] in esecuzione in Windows 8 e versioni successive viene eseguito il rendering dell'intera finestra senza ritaglio quando la finestra si estende al di fuori di un singolo schermo in uno scenario di utilizzo di più monitor.</span><span class="sxs-lookup"><span data-stu-id="1d943-103">In the [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] running on Windows 8 and above, the entire window is rendered without clipping when it extends outside of single display in a multi-monitor scenario.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="1d943-104">Impatto</span><span class="sxs-lookup"><span data-stu-id="1d943-104">Impact</span></span>  
 <span data-ttu-id="1d943-105">In generale, il rendering di un'intera finestra su più monitor senza ritaglio è il comportamento previsto.</span><span class="sxs-lookup"><span data-stu-id="1d943-105">In general, rendering an entire window across multiple monitors without clipping is the expected behavior.</span></span> <span data-ttu-id="1d943-106">Tuttavia, in Windows 7 e versioni precedenti le finestre WPF vengono ritagliate quando si estendono oltre un singolo schermo perché il rendering di una parte della finestra sul secondo monitor ha un impatto significativo sulle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="1d943-106">However, on Windows 7 and earlier versions, WPF windows are clipped when they extend beyond a single display because rendering a portion of the window on the second monitor has a significant performance impact.</span></span>  
  
 <span data-ttu-id="1d943-107">L'impatto esatto del rendering di finestre WPF su più monitor in Windows 8 e versioni successive non è precisamente quantificabile poiché dipende da numerosi fattori.</span><span class="sxs-lookup"><span data-stu-id="1d943-107">The precise impact of rendering WPF windows across monitors on Windows 8 and above is not precisely quantifiable since it depends on a large number of factors.</span></span> <span data-ttu-id="1d943-108">In alcuni casi, potrebbe produrre un impatto indesiderato sulle prestazioni, in particolare per gli utenti che eseguono applicazioni a elevato utilizzo di grafica e hanno finestre che si estendono su più monitor.</span><span class="sxs-lookup"><span data-stu-id="1d943-108">In some cases, it may still produce an undesirable impact on performance, particularly for users who run graphics-intensive applications and have windows straddling monitors.</span></span> <span data-ttu-id="1d943-109">In altri casi, si potrebbe semplicemente volere un comportamento coerente tra le versioni di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="1d943-109">In other cases, you may simply want a consistent behavior across .NET Framework versions.</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="1d943-110">Attenuazione</span><span class="sxs-lookup"><span data-stu-id="1d943-110">Mitigation</span></span>  
 <span data-ttu-id="1d943-111">È possibile disabilitare questa modifica e ripristinare il comportamento precedente di ritaglio di una finestra WPF quando si estende oltre un singolo schermo.</span><span class="sxs-lookup"><span data-stu-id="1d943-111">You can disable this change and revert to the previous behavior of clipping a WPF window when it extends beyond a single display.</span></span> <span data-ttu-id="1d943-112">Questo risultato può essere raggiunto in due modi:</span><span class="sxs-lookup"><span data-stu-id="1d943-112">There are two ways to do this:</span></span>  
  
-   <span data-ttu-id="1d943-113">Aggiungendo l'elemento `<EnableMultiMonitorDisplayClipping>` nella sezione `<appSettings>` del file di configurazione dell'applicazione, è possibile disabilitare o abilitare questo comportamento nelle app che eseguono Windows 8 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="1d943-113">By adding the `<EnableMultiMonitorDisplayClipping>` element to the `<appSettings>` section of your application configuration file, you can disable or enable this behavior on apps running on Windows 8 or later.</span></span> <span data-ttu-id="1d943-114">Ad esempio, la sezione di configurazione seguente disabilita il rendering senza ritaglio:</span><span class="sxs-lookup"><span data-stu-id="1d943-114">For example, the following configuration section disables rendering without clipping:</span></span>  
  
    ```xml  
    <appSettings>  
        <add key="EnableMultiMonitorDisplayClipping" value="true"/>  
      </appSettings>  
    ```  
  
     <span data-ttu-id="1d943-115">L'impostazione di configurazione `<EnableMultiMonitorDisplayClipping>` può avere uno dei due valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="1d943-115">The `<EnableMultiMonitorDisplayClipping>` configuration setting can have either of two values:</span></span>  
  
    -   <span data-ttu-id="1d943-116">`true` per consentire il ritaglio delle finestre in base ai confini del monitor durante il rendering.</span><span class="sxs-lookup"><span data-stu-id="1d943-116">`true`, to enable clipping of windows to monitor bounds during rendering.</span></span>  
  
    -   <span data-ttu-id="1d943-117">`false` per disabilitare il ritaglio delle finestre in base ai confini del monitor durante il rendering.</span><span class="sxs-lookup"><span data-stu-id="1d943-117">`false`, to disable clipping of windows to monitor bounds during rendering.</span></span>  
  
-   <span data-ttu-id="1d943-118">Impostando la proprietà <xref:System.Windows.CoreCompatibilityPreferences.EnableMultiMonitorDisplayClipping%2A> su `true` all'avvio dell'app.</span><span class="sxs-lookup"><span data-stu-id="1d943-118">By setting the <xref:System.Windows.CoreCompatibilityPreferences.EnableMultiMonitorDisplayClipping%2A> property to `true` at app startup.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d943-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1d943-119">See Also</span></span>  
 [<span data-ttu-id="1d943-120">Modifiche al runtime</span><span class="sxs-lookup"><span data-stu-id="1d943-120">Runtime Changes</span></span>](../../../docs/framework/migration-guide/runtime-changes-in-the-net-framework-4-6.md)

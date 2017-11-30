---
title: Localizzazione
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- culture, localization
- application development [.NET Framework], localization
- globalization [.NET Framework], localization
- code blocks
- international applications [.NET Framework], localization
- global applications, localization
- world-ready applications, localization
- user interface blocks
- localization [.NET Framework], about localization
- localizing resources
ms.assetid: 49d520d7-92d7-44ee-bb24-8b615db1d41b
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4aaf2da77a1fab55cbebd6bfa05a2b1c74e5cbbd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="localization"></a><span data-ttu-id="5bc90-102">Localizzazione</span><span class="sxs-lookup"><span data-stu-id="5bc90-102">Localization</span></span>
<span data-ttu-id="5bc90-103">Localizzazione è il processo di conversione di risorse dell'applicazione nelle versioni localizzate per tutte le impostazioni cultura supportate dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="5bc90-103">Localization is the process of translating an application's resources into localized versions for each culture that the application will support.</span></span> <span data-ttu-id="5bc90-104">È consigliabile procedere alla fase di localizzazione solo dopo aver completato il [revisione della localizzabilità](../../../docs/standard/globalization-localization/localizability-review.md) passaggio per verificare che l'applicazione globalizzata sia pronta per la localizzazione.</span><span class="sxs-lookup"><span data-stu-id="5bc90-104">You should proceed to the localization step only after completing the [Localizability Review](../../../docs/standard/globalization-localization/localizability-review.md) step to verify that the globalized application is ready for localization.</span></span>  
  
 <span data-ttu-id="5bc90-105">Un'applicazione che è pronta per la localizzazione viene suddivisa in due blocchi concettuali, un blocco che contiene tutti gli elementi di interfaccia utente e un blocco che contiene il codice eseguibile.</span><span class="sxs-lookup"><span data-stu-id="5bc90-105">An application that is ready for localization is separated into two conceptual blocks, a block that contains all user interface elements and a block that contains executable code.</span></span> <span data-ttu-id="5bc90-106">Il blocco dell'interfaccia utente contiene solo gli elementi dell'interfaccia utente localizzabili, ad esempio stringhe, messaggi di errore, finestre di dialogo, menu, le risorse di oggetti incorporati e così via per la lingua.</span><span class="sxs-lookup"><span data-stu-id="5bc90-106">The user interface block contains only localizable user-interface elements such as strings, error messages, dialog boxes, menus, embedded object resources, and so on for the neutral culture.</span></span> <span data-ttu-id="5bc90-107">Il blocco di codice contiene solo il codice dell'applicazione utilizzabile da tutte le lingue supportate.</span><span class="sxs-lookup"><span data-stu-id="5bc90-107">The code block contains only the application code to be used by all supported cultures.</span></span> <span data-ttu-id="5bc90-108">Common language runtime supporta un modello di risorsa di assembly satellite che separa il codice dell'applicazione eseguibile dalle relative risorse.</span><span class="sxs-lookup"><span data-stu-id="5bc90-108">The common language runtime supports a satellite assembly resource model that separates an application's executable code from its resources.</span></span> <span data-ttu-id="5bc90-109">Per ulteriori informazioni sull'implementazione di questo modello, vedere [risorse nelle applicazioni Desktop](../../../docs/framework/resources/index.md).</span><span class="sxs-lookup"><span data-stu-id="5bc90-109">For more information about implementing this model, see [Resources in Desktop Apps](../../../docs/framework/resources/index.md).</span></span>  
  
 <span data-ttu-id="5bc90-110">Per ogni versione localizzata dell'applicazione, aggiungere un nuovo assembly satellite che contiene il blocco dell'interfaccia utente localizzata tradotto nella lingua appropriata per le impostazioni cultura di destinazione.</span><span class="sxs-lookup"><span data-stu-id="5bc90-110">For each localized version of your application, add a new satellite assembly that contains the localized user interface block translated into the appropriate language for the target culture.</span></span> <span data-ttu-id="5bc90-111">Il blocco di codice per tutte le impostazioni cultura deve rimanere invariate.</span><span class="sxs-lookup"><span data-stu-id="5bc90-111">The code block for all cultures should remain the same.</span></span> <span data-ttu-id="5bc90-112">La combinazione di una versione localizzata del blocco dell'interfaccia utente con il blocco di codice produce una versione localizzata dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="5bc90-112">The combination of a localized version of the user interface block with the code block produces a localized version of your application.</span></span>  
  
 <span data-ttu-id="5bc90-113">Il [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] fornisce l'Editor di risorse form (Winres.exe) di Windows che consente di localizzare rapidamente Windows Form per le lingue di destinazione.</span><span class="sxs-lookup"><span data-stu-id="5bc90-113">The [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] supplies the Windows Forms Resource Editor (Winres.exe) that allows you to quickly localize Windows Forms for target cultures.</span></span> <span data-ttu-id="5bc90-114">Per informazioni sull'utilizzo di questo strumento, vedere [Winres.exe (Editor di risorse di Windows Form)](../../../docs/framework/tools/winres-exe-windows-forms-resource-editor.md).</span><span class="sxs-lookup"><span data-stu-id="5bc90-114">For information about using this tool, see [Winres.exe (Windows Forms Resource Editor)](../../../docs/framework/tools/winres-exe-windows-forms-resource-editor.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5bc90-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5bc90-115">See Also</span></span>  
 [<span data-ttu-id="5bc90-116">Globalizzazione e localizzazione</span><span class="sxs-lookup"><span data-stu-id="5bc90-116">Globalization and Localization</span></span>](../../../docs/standard/globalization-localization/index.md)  
 [<span data-ttu-id="5bc90-117">Revisione della localizzabilità</span><span class="sxs-lookup"><span data-stu-id="5bc90-117">Localizability Review</span></span>](../../../docs/standard/globalization-localization/localizability-review.md)  
 [<span data-ttu-id="5bc90-118">Globalizzazione</span><span class="sxs-lookup"><span data-stu-id="5bc90-118">Globalization</span></span>](../../../docs/standard/globalization-localization/globalization.md)  
 [<span data-ttu-id="5bc90-119">Risorse nelle applicazioni desktop</span><span class="sxs-lookup"><span data-stu-id="5bc90-119">Resources in Desktop Apps</span></span>](../../../docs/framework/resources/index.md)

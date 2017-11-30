---
title: "Revisione della localizzabilità"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- world-ready applications, localizability
- application development [.NET Framework], localization
- localizability [.NET Framework]
- international applications [.NET Framework], localizability
- globalization [.NET Framework], localizability
- culture, localizability
- localization [.NET Framework], localizability
- global applications, localizability
- localizing resources
ms.assetid: 3aee2fbb-de47-4e37-8fe4-ddebb9719247
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7633c7fe9e99bde96ee108460e983eff48f1c7f0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="localizability-review"></a><span data-ttu-id="95754-102">Revisione della localizzabilità</span><span class="sxs-lookup"><span data-stu-id="95754-102">Localizability Review</span></span>
<span data-ttu-id="95754-103">La revisione della localizzabilità è un passaggio intermedio nello sviluppo di un'applicazione internazionale.</span><span class="sxs-lookup"><span data-stu-id="95754-103">The localizability review is an intermediate step in the development of a world-ready application.</span></span> <span data-ttu-id="95754-104">Viene verificato che un'applicazione globalizzata sia pronta per la localizzazione e viene identificato qualsiasi codice o aspetto dell'interfaccia utente per cui è richiesta una gestione speciale.</span><span class="sxs-lookup"><span data-stu-id="95754-104">It verifies that a globalized application is ready for localization and identifies any code or any aspects of the user interface that require special handling.</span></span> <span data-ttu-id="95754-105">Questo passaggio consente di garantire che durante il processo di localizzazione non verranno introdotti difetti funzionali nell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="95754-105">This step also helps ensure that the localization process will not introduce any functional defects into your application.</span></span> <span data-ttu-id="95754-106">Quando tutti i problemi generati dall'analisi della localizzazione vengono risolti, l'applicazione è pronta per la localizzazione.</span><span class="sxs-lookup"><span data-stu-id="95754-106">When all the issues raised by the localizability review have been addressed, your application is ready for localization.</span></span> <span data-ttu-id="95754-107">Se l'analisi della localizzabilità è completa, non è necessario modificare nessun codice sorgente durante il processo di localizzazione.</span><span class="sxs-lookup"><span data-stu-id="95754-107">If the localizability review is thorough, you should not have to modify any source code during the localization process.</span></span>  
  
 <span data-ttu-id="95754-108">La revisione della localizzabilità è costituita dai tre controlli seguenti:</span><span class="sxs-lookup"><span data-stu-id="95754-108">The localizability review consists of the following three checks:</span></span>  
  
-   [<span data-ttu-id="95754-109">I requisiti di globalizzazione sono implementati?</span><span class="sxs-lookup"><span data-stu-id="95754-109">Are the globalization recommendations implemented?</span></span>](#global)  
  
-   [<span data-ttu-id="95754-110">Le funzionalità dipendenti dalle impostazioni cultura sono gestite correttamente?</span><span class="sxs-lookup"><span data-stu-id="95754-110">Are culture-sensitive features handled correctly?</span></span>](#culture)  
  
-   [<span data-ttu-id="95754-111">È stata testata l'applicazione con dati internazionali?</span><span class="sxs-lookup"><span data-stu-id="95754-111">Have you tested your application with international data?</span></span>](#test)  
  
<a name="global"></a>   
## <a name="implementing-globalization-recommendations"></a><span data-ttu-id="95754-112">Implementazione dei requisiti di globalizzazione</span><span class="sxs-lookup"><span data-stu-id="95754-112">Implementing globalization recommendations</span></span>  
 <span data-ttu-id="95754-113">Se aver progettato e sviluppata l'applicazione con localizzazione presente e se sono state eseguite le raccomandazioni descritte nel [globalizzazione](../../../docs/standard/globalization-localization/globalization.md) articolo, la revisione della localizzabilità è principalmente un passaggio di controllo della qualità .</span><span class="sxs-lookup"><span data-stu-id="95754-113">If you have designed and developed your application with localization in mind, and if you have followed the recommendations discussed in the [Globalization](../../../docs/standard/globalization-localization/globalization.md) article, the localizability review will largely be a quality assurance pass.</span></span> <span data-ttu-id="95754-114">In caso contrario, durante questa fase è necessario rivedere e implementare i requisiti per [globalizzazione](../../../docs/standard/globalization-localization/globalization.md)e correggere gli errori nel codice sorgente che impediscono la localizzazione.</span><span class="sxs-lookup"><span data-stu-id="95754-114">Otherwise, during this stage you should review and implement the recommendations for [globalization](../../../docs/standard/globalization-localization/globalization.md), and fix the errors in source code that prevent localization.</span></span>  
  
<a name="culture"></a>   
## <a name="handling-culture-sensitive-features"></a><span data-ttu-id="95754-115">Gestione delle funzionalità dipendenti dalle impostazioni cultura</span><span class="sxs-lookup"><span data-stu-id="95754-115">Handling culture-sensitive features</span></span>  
 <span data-ttu-id="95754-116">.NET Framework non fornisce supporto a livello di codice in numerose aree che variano notevolmente in base alle impostazioni cultura.</span><span class="sxs-lookup"><span data-stu-id="95754-116">The .NET Framework does not provide programmatic support in a number of areas that vary widely by culture.</span></span> <span data-ttu-id="95754-117">Nella maggior parte dei casi, è necessario scrivere codice personalizzato per gestire le aree funzionali come segue:</span><span class="sxs-lookup"><span data-stu-id="95754-117">In most cases, you have to write custom code to handle feature areas like the following:</span></span>  
  
-   <span data-ttu-id="95754-118">Indirizzi.</span><span class="sxs-lookup"><span data-stu-id="95754-118">Addresses.</span></span>  
  
-   <span data-ttu-id="95754-119">Numeri di telefono.</span><span class="sxs-lookup"><span data-stu-id="95754-119">Telephone numbers.</span></span>  
  
-   <span data-ttu-id="95754-120">Formati di carta.</span><span class="sxs-lookup"><span data-stu-id="95754-120">Paper sizes.</span></span>  
  
-   <span data-ttu-id="95754-121">Unità di misura utilizzate per le lunghezze, i pesi, l'area, il volume e le temperature.</span><span class="sxs-lookup"><span data-stu-id="95754-121">Units of measure used for lengths, weights, area, volume, and temperatures.</span></span> <span data-ttu-id="95754-122">Benché .NET Framework non offra il supporto predefinito per la conversione tra le unità di misura, è possibile utilizzare la proprietà <xref:System.Globalization.RegionInfo.IsMetric%2A?displayProperty=nameWithType> per determinare se in un paese o un'area particolare viene utilizzato il sistema metrico, come illustrato di seguito.</span><span class="sxs-lookup"><span data-stu-id="95754-122">Although the .NET Framework does not offer built-in support for converting between units of measure, you can use the <xref:System.Globalization.RegionInfo.IsMetric%2A?displayProperty=nameWithType> property to determine whether a particular country or region uses the metric system, as the following example illustrates.</span></span>  
  
     [!code-csharp[Conceptual.Localizability#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.localizability/cs/ismetric1.cs#1)]
     [!code-vb[Conceptual.Localizability#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.localizability/vb/ismetric1.vb#1)]  
  
<a name="test"></a>   
## <a name="testing-your-application"></a><span data-ttu-id="95754-123">Test dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="95754-123">Testing your application</span></span>  
 <span data-ttu-id="95754-124">Prima di localizzare l'applicazione, è necessario testarla utilizzando i dati internazionali in versioni internazionali del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="95754-124">Before you localize your application, you should test it by using international data on international versions of the operating system.</span></span> <span data-ttu-id="95754-125">Sebbene la maggior parte dell'interfaccia utente non sarà localizzata in questa fase, sarà possibile rilevare problemi come i seguenti:</span><span class="sxs-lookup"><span data-stu-id="95754-125">Although most of the user interface will not be localized at this point, you will be able to detect problems such as the following:</span></span>  
  
-   <span data-ttu-id="95754-126">I dati serializzati che non si deserializzano correttamente nelle versioni del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="95754-126">Serialized data that does not deserialize correctly across operating system versions.</span></span>  
  
-   <span data-ttu-id="95754-127">Dati numerici che non riflettono le convenzioni delle impostazioni cultura correnti.</span><span class="sxs-lookup"><span data-stu-id="95754-127">Numeric data that does not reflect the conventions of the current culture.</span></span> <span data-ttu-id="95754-128">Ad esempio, i numeri possono essere visualizzati con separatori di gruppi, separatori decimali o simboli di valuta non corretti.</span><span class="sxs-lookup"><span data-stu-id="95754-128">For example, numbers may be displayed with inaccurate group separators, decimal separators, or currency symbols.</span></span>  
  
-   <span data-ttu-id="95754-129">Informazioni di data e ora che non riflettono le convenzioni delle impostazioni cultura correnti.</span><span class="sxs-lookup"><span data-stu-id="95754-129">Date and time data that does not reflect the conventions of the current culture.</span></span> <span data-ttu-id="95754-130">Ad esempio, i numeri che rappresentano il mese e il giorno possono essere visualizzati nell'ordine errato e i separatori di data o le informazioni sul fuso orario possono essere errati.</span><span class="sxs-lookup"><span data-stu-id="95754-130">For example, numbers that represent the month and day may appear in the wrong order, date separators may be incorrect, or time zone information may be incorrect.</span></span>  
  
-   <span data-ttu-id="95754-131">Risorse che non sono disponibili in quanto non sono identificate le impostazioni cultura predefinite per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="95754-131">Resources that cannot be found because you have not identified a default culture for your application.</span></span>  
  
-   <span data-ttu-id="95754-132">Stringhe visualizzate in modo anomalo per le impostazioni cultura specifiche.</span><span class="sxs-lookup"><span data-stu-id="95754-132">Strings that are displayed in an unusual order for the specific culture.</span></span>  
  
-   <span data-ttu-id="95754-133">Confronti di stringhe o confronti per l'uguaglianza tramite cui vengono restituiti risultati imprevisti.</span><span class="sxs-lookup"><span data-stu-id="95754-133">String comparisons or comparisons for equality that return unexpected results.</span></span>  
  
 <span data-ttu-id="95754-134">Se aver seguito i requisiti di globalizzazione, quando si sviluppa l'applicazione, gestita correttamente, le funzionalità dipendenti dalle impostazioni cultura e identificato e risolto i problemi di localizzazione che si è verificato durante il test, è possibile procedere al passaggio successivo, [Localizzazione](../../../docs/standard/globalization-localization/localization.md).</span><span class="sxs-lookup"><span data-stu-id="95754-134">If you've followed the globalization recommendations when developing your application, handled culture-sensitive features correctly, and identified and addressed the localization issues that arose during testing, you can proceed to the next step, [Localization](../../../docs/standard/globalization-localization/localization.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95754-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="95754-135">See Also</span></span>  
 [<span data-ttu-id="95754-136">Globalizzazione e localizzazione</span><span class="sxs-lookup"><span data-stu-id="95754-136">Globalization and Localization</span></span>](../../../docs/standard/globalization-localization/index.md)  
 [<span data-ttu-id="95754-137">Localizzazione</span><span class="sxs-lookup"><span data-stu-id="95754-137">Localization</span></span>](../../../docs/standard/globalization-localization/localization.md)  
 [<span data-ttu-id="95754-138">Globalizzazione</span><span class="sxs-lookup"><span data-stu-id="95754-138">Globalization</span></span>](../../../docs/standard/globalization-localization/globalization.md)  
 [<span data-ttu-id="95754-139">Risorse nelle applicazioni desktop</span><span class="sxs-lookup"><span data-stu-id="95754-139">Resources in Desktop Apps</span></span>](../../../docs/framework/resources/index.md)

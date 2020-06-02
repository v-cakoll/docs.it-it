---
title: Revisione della localizzabilità
ms.date: 03/30/2017
ms.technology: dotnet-standard
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
ms.openlocfilehash: ef23cff2416792f13fda04dbe9beb34cbacfd7ea
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84288277"
---
# <a name="localizability-review"></a><span data-ttu-id="b55d3-102">Revisione della localizzabilità</span><span class="sxs-lookup"><span data-stu-id="b55d3-102">Localizability review</span></span>

<span data-ttu-id="b55d3-103">L'analisi della localizzabilità è un passaggio intermedio nello sviluppo di un'applicazione internazionale.</span><span class="sxs-lookup"><span data-stu-id="b55d3-103">The localizability review is an intermediate step in the development of a world-ready application.</span></span> <span data-ttu-id="b55d3-104">Viene verificato che un'applicazione globalizzata sia pronta per la localizzazione e viene identificato qualsiasi codice o aspetto dell'interfaccia utente per cui è richiesta una gestione speciale.</span><span class="sxs-lookup"><span data-stu-id="b55d3-104">It verifies that a globalized application is ready for localization and identifies any code or any aspects of the user interface that require special handling.</span></span> <span data-ttu-id="b55d3-105">Questo passaggio consente di garantire che durante il processo di localizzazione non verranno introdotti difetti funzionali nell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="b55d3-105">This step also helps ensure that the localization process will not introduce any functional defects into your application.</span></span> <span data-ttu-id="b55d3-106">Quando tutti i problemi generati dall'analisi della localizzazione vengono risolti, l'applicazione è pronta per la localizzazione.</span><span class="sxs-lookup"><span data-stu-id="b55d3-106">When all the issues raised by the localizability review have been addressed, your application is ready for localization.</span></span> <span data-ttu-id="b55d3-107">Se l'analisi della localizzabilità è completa, non è necessario modificare nessun codice sorgente durante il processo di localizzazione.</span><span class="sxs-lookup"><span data-stu-id="b55d3-107">If the localizability review is thorough, you should not have to modify any source code during the localization process.</span></span>

<span data-ttu-id="b55d3-108">L'analisi della localizzabilità è costituita dai tre controlli seguenti:</span><span class="sxs-lookup"><span data-stu-id="b55d3-108">The localizability review consists of the following three checks:</span></span>

- [<span data-ttu-id="b55d3-109">I requisiti di globalizzazione sono implementati?</span><span class="sxs-lookup"><span data-stu-id="b55d3-109">Are the globalization recommendations implemented?</span></span>](#global)

- [<span data-ttu-id="b55d3-110">Le funzionalità dipendenti dalle impostazioni cultura sono gestite correttamente?</span><span class="sxs-lookup"><span data-stu-id="b55d3-110">Are culture-sensitive features handled correctly?</span></span>](#culture)

- [<span data-ttu-id="b55d3-111">L'applicazione è stata testata con dati internazionali?</span><span class="sxs-lookup"><span data-stu-id="b55d3-111">Have you tested your application with international data?</span></span>](#test)

<a name="global"></a>
## <a name="implement-globalization-recommendations"></a><span data-ttu-id="b55d3-112">Implementare le raccomandazioni per la globalizzazione</span><span class="sxs-lookup"><span data-stu-id="b55d3-112">Implement globalization recommendations</span></span>

<span data-ttu-id="b55d3-113">Se l'applicazione è stata progettata e sviluppata pensando alla localizzazione e se sono stati seguiti i consigli forniti nell'articolo [Globalizzazione](globalization.md), la revisione della localizzabilità sarà principalmente un passaggio di controllo di qualità.</span><span class="sxs-lookup"><span data-stu-id="b55d3-113">If you have designed and developed your application with localization in mind, and if you have followed the recommendations discussed in the [Globalization](globalization.md) article, the localizability review will largely be a quality assurance pass.</span></span> <span data-ttu-id="b55d3-114">In caso contrario, durante questa fase è necessario rivedere e implementare i consigli per la [globalizzazione](globalization.md) e correggere gli errori nel codice sorgente che impediscono la localizzazione.</span><span class="sxs-lookup"><span data-stu-id="b55d3-114">Otherwise, during this stage you should review and implement the recommendations for [globalization](globalization.md) and fix the errors in source code that prevent localization.</span></span>

<a name="culture"></a>
## <a name="handle-culture-sensitive-features"></a><span data-ttu-id="b55d3-115">Gestire le funzionalità dipendenti dalle impostazioni cultura</span><span class="sxs-lookup"><span data-stu-id="b55d3-115">Handle culture-sensitive features</span></span>

<span data-ttu-id="b55d3-116">.NET non dispone di supporto a livello di codice in numerose aree, che variano notevolmente in base alle impostazioni cultura.</span><span class="sxs-lookup"><span data-stu-id="b55d3-116">.NET does not provide programmatic support in a number of areas that vary widely by culture.</span></span> <span data-ttu-id="b55d3-117">Nella maggior parte dei casi, è necessario scrivere codice personalizzato per gestire le aree funzionali come segue:</span><span class="sxs-lookup"><span data-stu-id="b55d3-117">In most cases, you have to write custom code to handle feature areas like the following:</span></span>

- <span data-ttu-id="b55d3-118">Indirizzi</span><span class="sxs-lookup"><span data-stu-id="b55d3-118">Addresses</span></span>

- <span data-ttu-id="b55d3-119">Numeri di telefono</span><span class="sxs-lookup"><span data-stu-id="b55d3-119">Telephone numbers</span></span>

- <span data-ttu-id="b55d3-120">Formati carta</span><span class="sxs-lookup"><span data-stu-id="b55d3-120">Paper sizes</span></span>

- <span data-ttu-id="b55d3-121">Unità di misura di lunghezza, peso, area, volume e temperatura</span><span class="sxs-lookup"><span data-stu-id="b55d3-121">Units of measure used for lengths, weights, area, volume, and temperatures</span></span>

   <span data-ttu-id="b55d3-122">Anche se .NET non offre il supporto predefinito per la conversione tra le unità di misura, è possibile usare la proprietà <xref:System.Globalization.RegionInfo.IsMetric%2A?displayProperty=nameWithType> per determinare se in un paese o un'area particolare viene usato il sistema metrico, come illustrato di seguito.</span><span class="sxs-lookup"><span data-stu-id="b55d3-122">Although .NET does not offer built-in support for converting between units of measure, you can use the <xref:System.Globalization.RegionInfo.IsMetric%2A?displayProperty=nameWithType> property to determine whether a particular country or region uses the metric system, as the following example illustrates.</span></span>

   [!code-csharp[Conceptual.Localizability#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.localizability/cs/ismetric1.cs#1)]
   [!code-vb[Conceptual.Localizability#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.localizability/vb/ismetric1.vb#1)]

<a name="test"></a>
## <a name="test-your-application"></a><span data-ttu-id="b55d3-123">Testare l'applicazione</span><span class="sxs-lookup"><span data-stu-id="b55d3-123">Test your application</span></span>

<span data-ttu-id="b55d3-124">Prima di localizzare l'applicazione, è necessario testarla utilizzando i dati internazionali in versioni internazionali del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="b55d3-124">Before you localize your application, you should test it by using international data on international versions of the operating system.</span></span> <span data-ttu-id="b55d3-125">Sebbene la maggior parte dell'interfaccia utente non sarà localizzata in questa fase, sarà possibile rilevare problemi come i seguenti:</span><span class="sxs-lookup"><span data-stu-id="b55d3-125">Although most of the user interface will not be localized at this point, you will be able to detect problems such as the following:</span></span>

- <span data-ttu-id="b55d3-126">I dati serializzati che non si deserializzano correttamente nelle versioni del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="b55d3-126">Serialized data that does not deserialize correctly across operating system versions.</span></span>

- <span data-ttu-id="b55d3-127">Dati numerici che non riflettono le convenzioni delle impostazioni cultura correnti.</span><span class="sxs-lookup"><span data-stu-id="b55d3-127">Numeric data that does not reflect the conventions of the current culture.</span></span> <span data-ttu-id="b55d3-128">Ad esempio, i numeri possono essere visualizzati con separatori di gruppi, separatori decimali o simboli di valuta non corretti.</span><span class="sxs-lookup"><span data-stu-id="b55d3-128">For example, numbers may be displayed with inaccurate group separators, decimal separators, or currency symbols.</span></span>

- <span data-ttu-id="b55d3-129">Informazioni di data e ora che non riflettono le convenzioni delle impostazioni cultura correnti.</span><span class="sxs-lookup"><span data-stu-id="b55d3-129">Date and time data that does not reflect the conventions of the current culture.</span></span> <span data-ttu-id="b55d3-130">Ad esempio, i numeri che rappresentano il mese e il giorno possono essere visualizzati nell'ordine errato e i separatori di data o le informazioni sul fuso orario possono essere errati.</span><span class="sxs-lookup"><span data-stu-id="b55d3-130">For example, numbers that represent the month and day may appear in the wrong order, date separators may be incorrect, or time zone information may be incorrect.</span></span>

- <span data-ttu-id="b55d3-131">Risorse che non sono disponibili in quanto non sono identificate le impostazioni cultura predefinite per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="b55d3-131">Resources that cannot be found because you have not identified a default culture for your application.</span></span>

- <span data-ttu-id="b55d3-132">Stringhe visualizzate in modo anomalo per le impostazioni cultura specifiche.</span><span class="sxs-lookup"><span data-stu-id="b55d3-132">Strings that are displayed in an unusual order for the specific culture.</span></span>

- <span data-ttu-id="b55d3-133">Confronti di stringhe o confronti per l'uguaglianza tramite cui vengono restituiti risultati imprevisti.</span><span class="sxs-lookup"><span data-stu-id="b55d3-133">String comparisons or comparisons for equality that return unexpected results.</span></span>

<span data-ttu-id="b55d3-134">Se durante lo sviluppo dell'applicazione sono stati seguiti i consigli per la globalizzazione, le funzionalità dipendenti dalle impostazioni cultura sono state gestite correttamente e i problemi di localizzazione riscontrati durante i test sono stati identificati e risolti, è possibile procedere al passaggio successivo, [Localizzazione](localization.md).</span><span class="sxs-lookup"><span data-stu-id="b55d3-134">If you've followed the globalization recommendations when developing your application, handled culture-sensitive features correctly, and identified and addressed the localization issues that arose during testing, you can proceed to the next step, [Localization](localization.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="b55d3-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b55d3-135">See also</span></span>

- [<span data-ttu-id="b55d3-136">Globalizzazione e localizzazione</span><span class="sxs-lookup"><span data-stu-id="b55d3-136">Globalization and Localization</span></span>](index.md)
- [<span data-ttu-id="b55d3-137">Localizzazione</span><span class="sxs-lookup"><span data-stu-id="b55d3-137">Localization</span></span>](localization.md)
- [<span data-ttu-id="b55d3-138">Globalizzazione</span><span class="sxs-lookup"><span data-stu-id="b55d3-138">Globalization</span></span>](globalization.md)
- [<span data-ttu-id="b55d3-139">Risorse nelle applicazioni desktop</span><span class="sxs-lookup"><span data-stu-id="b55d3-139">Resources in Desktop Apps</span></span>](../../framework/resources/index.md)

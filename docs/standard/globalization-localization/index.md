---
title: Globalizzazione e localizzazione di applicazioni .NET Framework
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- international applications [.NET Framework]
- globalization [.NET Framework], encoding
- global applications
- internationalization
- world-ready applications
- application development [.NET Framework], globalization
- multilingual application development
ms.assetid: 9a59696b-d89b-45bd-946d-c75da4732d02
caps.latest.revision: 42
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 63f0e001280773c55f18f0604ca93986acbb9674
ms.sourcegitcommit: 91691981897cf8451033cb01071d8f5d94017f97
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2018
---
# <a name="globalizing-and-localizing-net-framework-applications"></a><span data-ttu-id="51889-102">Globalizzazione e localizzazione di applicazioni .NET Framework</span><span class="sxs-lookup"><span data-stu-id="51889-102">Globalizing and Localizing .NET Framework Applications</span></span>
<span data-ttu-id="51889-103">Lo sviluppo di [applicazioni internazionali](http://msdn.microsoft.com/goglobal/bb978433.aspx), tra cui un'applicazione che può essere localizzata in una o più lingue, include i seguenti tre passaggi: globalizzazione, analisi della localizzabilità e localizzazione.</span><span class="sxs-lookup"><span data-stu-id="51889-103">Developing a [world-ready application](http://msdn.microsoft.com/goglobal/bb978433.aspx), including an application that can be localized into one or more languages, involves three steps: globalization, localizability review, and localization.</span></span>  
  
 [<span data-ttu-id="51889-104">Globalizzazione</span><span class="sxs-lookup"><span data-stu-id="51889-104">Globalization</span></span>](../../../docs/standard/globalization-localization/globalization.md)  
 <span data-ttu-id="51889-105">Questo passaggio implica la progettazione e la codifica di un'applicazione indipendente dalle impostazioni cultura e dalla lingua che supporti le interfacce utente e i dati internazionali localizzati per tutti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="51889-105">This step involves designing and coding an application that is culture-neutral and language-neutral, and that supports localized user interfaces and regional data for all users.</span></span> <span data-ttu-id="51889-106">Comporta decisioni di progettazione e programmazione non basate su presupposti impostazioni cultura specifiche.</span><span class="sxs-lookup"><span data-stu-id="51889-106">It involves making design and programming decisions that are not based on culture-specific assumptions.</span></span> <span data-ttu-id="51889-107">Quando un'applicazione globalizzata non viene localizzata, è tuttavia progettata e scritta in modo da poter essere successivamente localizzata in una o più lingue in modo relativamente semplice.</span><span class="sxs-lookup"><span data-stu-id="51889-107">While a globalized application is not localized, it nevertheless is designed and written so that it can be subsequently localized into one or more languages with relative ease.</span></span>  
  
 [<span data-ttu-id="51889-108">Revisione della localizzabilità</span><span class="sxs-lookup"><span data-stu-id="51889-108">Localizability Review</span></span>](../../../docs/standard/globalization-localization/localizability-review.md)  
 <span data-ttu-id="51889-109">Questo passaggio prevede la revisione del codice e del progetto di un'applicazione per verificare che possa essere localizzata facilmente e per identificare potenziali problemi per la localizzazione e la verifica che il codice eseguibile dell'applicazione sia separato dalle relative risorse.</span><span class="sxs-lookup"><span data-stu-id="51889-109">This step involves reviewing an application's code and design to ensure that it can be localized easily and to identify potential roadblocks for localization, and verifying that the application's executable code is separated from its resources.</span></span> <span data-ttu-id="51889-110">Se la fase di globalizzazione ha avuto effetto, l'analisi della localizzabilità confermerà le scelte di codifica e di progettazione effettuate durante la globalizzazione.</span><span class="sxs-lookup"><span data-stu-id="51889-110">If the globalization stage was effective, the localizability review will confirm the design and coding choices made during globalization.</span></span> <span data-ttu-id="51889-111">La fase di localizzabilità può inoltre identificare eventuali problemi rimanenti. In questo modo, il codice sorgente di un'applicazione non deve necessariamente essere modificato durante la fase di localizzazione.</span><span class="sxs-lookup"><span data-stu-id="51889-111">The localizability stage may also identify any remaining issues so that an application's source code doesn't have to be modified during the localization stage.</span></span>  
  
 [<span data-ttu-id="51889-112">Localizzazione</span><span class="sxs-lookup"><span data-stu-id="51889-112">Localization</span></span>](../../../docs/standard/globalization-localization/localization.md)  
 <span data-ttu-id="51889-113">Questo passaggio prevede la personalizzazione di un'applicazione per impostazioni cultura e aree specifiche.</span><span class="sxs-lookup"><span data-stu-id="51889-113">This step involves customizing an application for specific cultures or regions.</span></span> <span data-ttu-id="51889-114">Se i passaggi di globalizzazione e possibilità di localizzazione sono stati eseguiti correttamente, la localizzazione consiste principalmente nella traduzione dell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="51889-114">If the globalization and localizability steps have been performed correctly, localization consists primarily of translating the user interface.</span></span>  
  
 <span data-ttu-id="51889-115">Se si ci attiene ai seguenti tre passaggi verranno offerti due vantaggi:</span><span class="sxs-lookup"><span data-stu-id="51889-115">Following these three steps provides two advantages:</span></span>  
  
-   <span data-ttu-id="51889-116">In questo modo, non è necessario adattare un'applicazione progettata per supportare singole lingue, ad esempio Inglese US (Stati Uniti), per supportare le lingue aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="51889-116">It frees you from having to retrofit an application that is designed to support a single culture, such as U.S. English, to support additional cultures.</span></span>  
  
-   <span data-ttu-id="51889-117">Restituisce applicazioni localizzate che sono più stabile e con meno bug.</span><span class="sxs-lookup"><span data-stu-id="51889-117">It results in localized applications that are more stable and have fewer bugs.</span></span>  
  
 <span data-ttu-id="51889-118">In .NET Framework viene fornito supporto esteso per lo sviluppo di applicazioni internazionali e localizzate.</span><span class="sxs-lookup"><span data-stu-id="51889-118">The .NET Framework provides extensive support for the development of world-ready and localized applications.</span></span> <span data-ttu-id="51889-119">In particolare, molti membri del tipo nella libreria di classi .NET Framework facilitano la globalizzazione restituendo valori che riflettono le convenzioni delle impostazioni cultura dell'utente o di impostazioni cultura specifiche.</span><span class="sxs-lookup"><span data-stu-id="51889-119">In particular, many type members in the .NET Framework class library aid globalization by returning values that reflect the conventions of either the current user's culture or a specified culture.</span></span> <span data-ttu-id="51889-120">Inoltre, .NET Framework supporta gli assembly satellite, che semplificano il processo di localizzazione di un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="51889-120">Also, the .NET Framework supports satellite assemblies, which facilitate the process of localizing an application.</span></span>  
  
 <span data-ttu-id="51889-121">Per altre informazioni, vedere la [documentazione sulla globalizzazione](/globalization/).</span><span class="sxs-lookup"><span data-stu-id="51889-121">For additional information, see the [Globalization documentation](/globalization/).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="51889-122">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="51889-122">In This Section</span></span>  
 [<span data-ttu-id="51889-123">Globalizzazione</span><span class="sxs-lookup"><span data-stu-id="51889-123">Globalization</span></span>](../../../docs/standard/globalization-localization/globalization.md)  
 <span data-ttu-id="51889-124">Viene descritta la prima fase di creazione di un'applicazione internazionale, che include la progettazione e la codifica di un'applicazione indipendente dalla lingua e dalle impostazioni cultura.</span><span class="sxs-lookup"><span data-stu-id="51889-124">Discusses the first stage of creating a world-ready application, which involves designing and coding an application that is culture-neutral and language-neutral.</span></span>  
  
 [<span data-ttu-id="51889-125">Revisione della localizzabilità</span><span class="sxs-lookup"><span data-stu-id="51889-125">Localizability Review</span></span>](../../../docs/standard/globalization-localization/localizability-review.md)  
 <span data-ttu-id="51889-126">Viene descritta la seconda fase di creazione di un'applicazione localizzata, che include l'identificazione dei potenziali blocchi stradali per la localizzazione.</span><span class="sxs-lookup"><span data-stu-id="51889-126">Discusses the second stage of creating a localized application, which involves identifying potential roadblocks to localization.</span></span>  
  
 [<span data-ttu-id="51889-127">Localizzazione</span><span class="sxs-lookup"><span data-stu-id="51889-127">Localization</span></span>](../../../docs/standard/globalization-localization/localization.md)  
 <span data-ttu-id="51889-128">Viene illustrata la fase finale della creazione di un'applicazione localizzata, che include la personalizzazione di un'interfaccia utente dell'applicazione per le aree o le impostazioni cultura specifiche.</span><span class="sxs-lookup"><span data-stu-id="51889-128">Discusses the final stage of creating a localized application, which involves customizing an application's user interface for specific regions or cultures.</span></span>  
  
 [<span data-ttu-id="51889-129">Operazioni sulle stringhe indipendenti dalle impostazioni cultura</span><span class="sxs-lookup"><span data-stu-id="51889-129">Culture-Insensitive String Operations</span></span>](../../../docs/standard/globalization-localization/culture-insensitive-string-operations.md)  
 <span data-ttu-id="51889-130">Viene descritto come utilizzare metodi e classi di .NET Framework definiti come dipendenti dalle impostazioni cultura per impostazione predefinita per ottenere risultati indipendenti dalle impostazioni cultura.</span><span class="sxs-lookup"><span data-stu-id="51889-130">Describes how to use .NET Framework methods and classes that are culture-sensitive by default to obtain culture-insensitive results.</span></span>  
  
 [<span data-ttu-id="51889-131">Procedure consigliate per lo sviluppo di applicazioni internazionali</span><span class="sxs-lookup"><span data-stu-id="51889-131">Best Practices for Developing World-Ready Applications</span></span>](../../../docs/standard/globalization-localization/best-practices-for-developing-world-ready-apps.md)  
 <span data-ttu-id="51889-132">Vengono forniti alcuni suggerimenti per la globalizzazione, la localizzazione e lo sviluppo di applicazioni ASP.NET internazionali.</span><span class="sxs-lookup"><span data-stu-id="51889-132">Describes the best practices to follow for globalization, localization, and developing world-ready ASP.NET applications.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="51889-133">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="51889-133">Reference</span></span>  
 <span data-ttu-id="51889-134">Spazio dei nomi <xref:System.Globalization?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="51889-134"><xref:System.Globalization?displayProperty=nameWithType> namespace</span></span>  
 <span data-ttu-id="51889-135">Contiene classi che definiscono informazioni sulle impostazioni cultura, tra cui la lingua, il paese, il calendario, il formato delle date, delle valute e dei numeri e il criterio di ordinamento delle stringhe.</span><span class="sxs-lookup"><span data-stu-id="51889-135">Contains classes that define culture-related information, including the language, the country/region, the calendars in use, the format patterns for dates, currency, and numbers, and the sort order for strings.</span></span>  
  
 <span data-ttu-id="51889-136">Spazio dei nomi <xref:System.Resources></span><span class="sxs-lookup"><span data-stu-id="51889-136"><xref:System.Resources> namespace</span></span>  
 <span data-ttu-id="51889-137">Vengono fornite le classi per la creazione, la manipolazione e l'uso di risorse.</span><span class="sxs-lookup"><span data-stu-id="51889-137">Provides classes for creating, manipulating, and using resources.</span></span>  
  
 <span data-ttu-id="51889-138">Spazio dei nomi <xref:System.Text></span><span class="sxs-lookup"><span data-stu-id="51889-138"><xref:System.Text> namespace</span></span>  
 <span data-ttu-id="51889-139">Contiene le classi che rappresentano le codifiche dei caratteri ASCII, ANSI, Unicode e altri tipi di codifiche.</span><span class="sxs-lookup"><span data-stu-id="51889-139">Contains classes representing ASCII, ANSI, Unicode, and other character encodings.</span></span>  
  
 [<span data-ttu-id="51889-140">Resgen.exe (generatore di file di risorse)</span><span class="sxs-lookup"><span data-stu-id="51889-140">Resgen.exe (Resource File Generator)</span></span>](../../../docs/framework/tools/resgen-exe-resource-file-generator.md)  
 <span data-ttu-id="51889-141">Viene descritto l'utilizzo di Resgen.exe per convertire i file con estensione txt e resx (formato risorse basato su XML) in file binari con estensione resources di Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="51889-141">Describes how to use Resgen.exe to convert .txt files and XML-based resource format (.resx) files to common language runtime binary .resources files.</span></span>  
  
 [<span data-ttu-id="51889-142">Winres.exe (editor di risorse di Windows Form)</span><span class="sxs-lookup"><span data-stu-id="51889-142">Winres.exe (Windows Forms Resource Editor)</span></span>](../../../docs/framework/tools/winres-exe-windows-forms-resource-editor.md)  
 <span data-ttu-id="51889-143">Viene descritto l'uso di Winres.exe per localizzare i form di Windows Form.</span><span class="sxs-lookup"><span data-stu-id="51889-143">Describes how to use Winres.exe to localize Windows Forms forms.</span></span>

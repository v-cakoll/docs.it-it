---
title: Convenzioni di denominazione generali
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- names [.NET Framework], conflicts
- type names, conflicts
- language-specific type names
- names [.NET Framework], about naming guidelines
- names [.NET Framework], abbreviations
- abbreviation naming guidelines
- acronym naming guidelines
- Hungarian notation
- names [.NET Framework], type names
- names [.NET Framework], acronyms
ms.assetid: d3a77ea1-75d2-4969-a8c3-3e1e3e1aaedc
caps.latest.revision: "18"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 5e5c09c4db8e65d836c7afc7cb78c1f9e32bab65
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/23/2017
---
# <a name="general-naming-conventions"></a><span data-ttu-id="6922c-102">Convenzioni di denominazione generali</span><span class="sxs-lookup"><span data-stu-id="6922c-102">General Naming Conventions</span></span>
<span data-ttu-id="6922c-103">Questa sezione descrive convenzioni di denominazione generali correlate alla scelta delle parole, le linee guida sull'utilizzo di abbreviazioni e acronimi e indicazioni su come evitare di utilizzare nomi specifici della lingua.</span><span class="sxs-lookup"><span data-stu-id="6922c-103">This section describes general naming conventions that relate to word choice, guidelines on using abbreviations and acronyms, and recommendations on how to avoid using language-specific names.</span></span>  
  
## <a name="word-choice"></a><span data-ttu-id="6922c-104">Scelta di Word</span><span class="sxs-lookup"><span data-stu-id="6922c-104">Word Choice</span></span>  
 <span data-ttu-id="6922c-105">**✓ SI** scegliere i nomi degli identificatori facilmente leggibili.</span><span class="sxs-lookup"><span data-stu-id="6922c-105">**✓ DO** choose easily readable identifier names.</span></span>  
  
 <span data-ttu-id="6922c-106">Ad esempio, una proprietà denominata `HorizontalAlignment` è più inglese-leggibile `AlignmentHorizontal`.</span><span class="sxs-lookup"><span data-stu-id="6922c-106">For example, a property named `HorizontalAlignment` is more English-readable than `AlignmentHorizontal`.</span></span>  
  
 <span data-ttu-id="6922c-107">**✓ SI** preferire la leggibilità di brevità.</span><span class="sxs-lookup"><span data-stu-id="6922c-107">**✓ DO** favor readability over brevity.</span></span>  
  
 <span data-ttu-id="6922c-108">Il nome della proprietà `CanScrollHorizontally` è migliore `ScrollableX` (un riferimento all'asse x).</span><span class="sxs-lookup"><span data-stu-id="6922c-108">The property name `CanScrollHorizontally` is better than `ScrollableX` (an obscure reference to the X-axis).</span></span>  
  
 <span data-ttu-id="6922c-109">**X non** utilizzare altri caratteri non alfanumerici, trattini o caratteri di sottolineatura.</span><span class="sxs-lookup"><span data-stu-id="6922c-109">**X DO NOT** use underscores, hyphens, or any other nonalphanumeric characters.</span></span>  
  
 <span data-ttu-id="6922c-110">**X non** utilizzare la notazione ungherese.</span><span class="sxs-lookup"><span data-stu-id="6922c-110">**X DO NOT** use Hungarian notation.</span></span>  
  
 <span data-ttu-id="6922c-111">**X evitare** utilizzando gli identificatori che sono in conflitto con le parole chiave di ampiamente utilizzato linguaggi di programmazione.</span><span class="sxs-lookup"><span data-stu-id="6922c-111">**X AVOID** using identifiers that conflict with keywords of widely used programming languages.</span></span>  
  
 <span data-ttu-id="6922c-112">In base alla regola 4 della specifica CLS (Common Language), tutti i linguaggi conformi devono fornire un meccanismo che consente l'accesso agli elementi denominati che usano una parola chiave del linguaggio come identificatore.</span><span class="sxs-lookup"><span data-stu-id="6922c-112">According to Rule 4 of the Common Language Specification (CLS), all compliant languages must provide a mechanism that allows access to named items that use a keyword of that language as an identifier.</span></span> <span data-ttu-id="6922c-113">In c#, ad esempio, Usa il simbolo come meccanismo di escape in questo caso @.</span><span class="sxs-lookup"><span data-stu-id="6922c-113">C#, for example, uses the @ sign as an escape mechanism in this case.</span></span> <span data-ttu-id="6922c-114">Tuttavia, è comunque consigliabile evitare di parole chiave comuni in quanto è molto più difficile usare un metodo con la sequenza di escape quello senza di esso.</span><span class="sxs-lookup"><span data-stu-id="6922c-114">However, it is still a good idea to avoid common keywords because it is much more difficult to use a method with the escape sequence than one without it.</span></span>  
  
## <a name="using-abbreviations-and-acronyms"></a><span data-ttu-id="6922c-115">Utilizzo di abbreviazioni e gli acronimi</span><span class="sxs-lookup"><span data-stu-id="6922c-115">Using Abbreviations and Acronyms</span></span>  
 <span data-ttu-id="6922c-116">**X non** utilizzare abbreviazioni o termini più semplici come parte dei nomi degli identificatori.</span><span class="sxs-lookup"><span data-stu-id="6922c-116">**X DO NOT** use abbreviations or contractions as part of identifier names.</span></span>  
  
 <span data-ttu-id="6922c-117">Ad esempio, utilizzare `GetWindow` anziché `GetWin`.</span><span class="sxs-lookup"><span data-stu-id="6922c-117">For example, use `GetWindow` rather than `GetWin`.</span></span>  
  
 <span data-ttu-id="6922c-118">**X non** utilizzare acronimi che non sono molto diffusa e persino in tal caso, solo quando necessario.</span><span class="sxs-lookup"><span data-stu-id="6922c-118">**X DO NOT** use any acronyms that are not widely accepted, and even if they are, only when necessary.</span></span>  
  
## <a name="avoiding-language-specific-names"></a><span data-ttu-id="6922c-119">Evitare nomi specifici della lingua</span><span class="sxs-lookup"><span data-stu-id="6922c-119">Avoiding Language-Specific Names</span></span>  
 <span data-ttu-id="6922c-120">**✓ SI** utilizzare nomi significativi anziché parole chiave specifiche della lingua per i nomi dei tipi.</span><span class="sxs-lookup"><span data-stu-id="6922c-120">**✓ DO** use semantically interesting names rather than language-specific keywords for type names.</span></span>  
  
 <span data-ttu-id="6922c-121">Ad esempio, `GetLength` è un nome più significativo rispetto a `GetInt`.</span><span class="sxs-lookup"><span data-stu-id="6922c-121">For example, `GetLength` is a better name than `GetInt`.</span></span>  
  
 <span data-ttu-id="6922c-122">**✓ SI** usare un nome di tipo generico di CLR, anziché un nome specifico della lingua, in rari casi in cui un identificatore non ha alcun significato semantico oltre il relativo tipo.</span><span class="sxs-lookup"><span data-stu-id="6922c-122">**✓ DO** use a generic CLR type name, rather than a language-specific name, in the rare cases when an identifier has no semantic meaning beyond its type.</span></span>  
  
 <span data-ttu-id="6922c-123">Ad esempio, un metodo di conversione in <xref:System.Int64> deve essere denominato `ToInt64`, non `ToLong` (perché <xref:System.Int64> è un nome CLR per c#-alias specifico `long`).</span><span class="sxs-lookup"><span data-stu-id="6922c-123">For example, a method converting to <xref:System.Int64> should be named `ToInt64`, not `ToLong` (because <xref:System.Int64> is a CLR name for the C#-specific alias `long`).</span></span> <span data-ttu-id="6922c-124">Nella tabella seguente presenta vari tipi di dati di base utilizzando i nomi dei tipi CLR (nonché i nomi dei tipi corrispondenti per c#, Visual Basic e C++).</span><span class="sxs-lookup"><span data-stu-id="6922c-124">The following table presents several base data types using the CLR type names (as well as the corresponding type names for C#, Visual Basic, and C++).</span></span>  
  
|<span data-ttu-id="6922c-125">C#</span><span class="sxs-lookup"><span data-stu-id="6922c-125">C#</span></span>|<span data-ttu-id="6922c-126">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6922c-126">Visual Basic</span></span>|<span data-ttu-id="6922c-127">C++</span><span class="sxs-lookup"><span data-stu-id="6922c-127">C++</span></span>|<span data-ttu-id="6922c-128">CLR</span><span class="sxs-lookup"><span data-stu-id="6922c-128">CLR</span></span>|  
|---------|------------------|-----------|---------|  
|<span data-ttu-id="6922c-129">**sbyte**</span><span class="sxs-lookup"><span data-stu-id="6922c-129">**sbyte**</span></span>|<span data-ttu-id="6922c-130">**SByte**</span><span class="sxs-lookup"><span data-stu-id="6922c-130">**SByte**</span></span>|<span data-ttu-id="6922c-131">**char**</span><span class="sxs-lookup"><span data-stu-id="6922c-131">**char**</span></span>|<span data-ttu-id="6922c-132">**SByte**</span><span class="sxs-lookup"><span data-stu-id="6922c-132">**SByte**</span></span>|  
|<span data-ttu-id="6922c-133">**byte**</span><span class="sxs-lookup"><span data-stu-id="6922c-133">**byte**</span></span>|<span data-ttu-id="6922c-134">**Byte**</span><span class="sxs-lookup"><span data-stu-id="6922c-134">**Byte**</span></span>|<span data-ttu-id="6922c-135">**unsigned char**</span><span class="sxs-lookup"><span data-stu-id="6922c-135">**unsigned char**</span></span>|<span data-ttu-id="6922c-136">**Byte**</span><span class="sxs-lookup"><span data-stu-id="6922c-136">**Byte**</span></span>|  
|<span data-ttu-id="6922c-137">**short**</span><span class="sxs-lookup"><span data-stu-id="6922c-137">**short**</span></span>|<span data-ttu-id="6922c-138">**Short**</span><span class="sxs-lookup"><span data-stu-id="6922c-138">**Short**</span></span>|<span data-ttu-id="6922c-139">**short**</span><span class="sxs-lookup"><span data-stu-id="6922c-139">**short**</span></span>|<span data-ttu-id="6922c-140">**Int16**</span><span class="sxs-lookup"><span data-stu-id="6922c-140">**Int16**</span></span>|  
|<span data-ttu-id="6922c-141">**ushort**</span><span class="sxs-lookup"><span data-stu-id="6922c-141">**ushort**</span></span>|<span data-ttu-id="6922c-142">**UInt16**</span><span class="sxs-lookup"><span data-stu-id="6922c-142">**UInt16**</span></span>|<span data-ttu-id="6922c-143">**unsigned short**</span><span class="sxs-lookup"><span data-stu-id="6922c-143">**unsigned short**</span></span>|<span data-ttu-id="6922c-144">**UInt16**</span><span class="sxs-lookup"><span data-stu-id="6922c-144">**UInt16**</span></span>|  
|<span data-ttu-id="6922c-145">**int**</span><span class="sxs-lookup"><span data-stu-id="6922c-145">**int**</span></span>|<span data-ttu-id="6922c-146">**Integer**</span><span class="sxs-lookup"><span data-stu-id="6922c-146">**Integer**</span></span>|<span data-ttu-id="6922c-147">**int**</span><span class="sxs-lookup"><span data-stu-id="6922c-147">**int**</span></span>|<span data-ttu-id="6922c-148">**Int32**</span><span class="sxs-lookup"><span data-stu-id="6922c-148">**Int32**</span></span>|  
|<span data-ttu-id="6922c-149">**uint**</span><span class="sxs-lookup"><span data-stu-id="6922c-149">**uint**</span></span>|<span data-ttu-id="6922c-150">**UInt32**</span><span class="sxs-lookup"><span data-stu-id="6922c-150">**UInt32**</span></span>|<span data-ttu-id="6922c-151">**unsigned int**</span><span class="sxs-lookup"><span data-stu-id="6922c-151">**unsigned int**</span></span>|<span data-ttu-id="6922c-152">**UInt32**</span><span class="sxs-lookup"><span data-stu-id="6922c-152">**UInt32**</span></span>|  
|<span data-ttu-id="6922c-153">**long**</span><span class="sxs-lookup"><span data-stu-id="6922c-153">**long**</span></span>|<span data-ttu-id="6922c-154">**Long**</span><span class="sxs-lookup"><span data-stu-id="6922c-154">**Long**</span></span>|<span data-ttu-id="6922c-155">**__int64**</span><span class="sxs-lookup"><span data-stu-id="6922c-155">**__int64**</span></span>|<span data-ttu-id="6922c-156">**Int64**</span><span class="sxs-lookup"><span data-stu-id="6922c-156">**Int64**</span></span>|  
|<span data-ttu-id="6922c-157">**ulong**</span><span class="sxs-lookup"><span data-stu-id="6922c-157">**ulong**</span></span>|<span data-ttu-id="6922c-158">**UInt64**</span><span class="sxs-lookup"><span data-stu-id="6922c-158">**UInt64**</span></span>|<span data-ttu-id="6922c-159">**unsigned __int64**</span><span class="sxs-lookup"><span data-stu-id="6922c-159">**unsigned __int64**</span></span>|<span data-ttu-id="6922c-160">**UInt64**</span><span class="sxs-lookup"><span data-stu-id="6922c-160">**UInt64**</span></span>|  
|<span data-ttu-id="6922c-161">**float**</span><span class="sxs-lookup"><span data-stu-id="6922c-161">**float**</span></span>|<span data-ttu-id="6922c-162">**Single**</span><span class="sxs-lookup"><span data-stu-id="6922c-162">**Single**</span></span>|<span data-ttu-id="6922c-163">**float**</span><span class="sxs-lookup"><span data-stu-id="6922c-163">**float**</span></span>|<span data-ttu-id="6922c-164">**Single**</span><span class="sxs-lookup"><span data-stu-id="6922c-164">**Single**</span></span>|  
|<span data-ttu-id="6922c-165">**double**</span><span class="sxs-lookup"><span data-stu-id="6922c-165">**double**</span></span>|<span data-ttu-id="6922c-166">**Double**</span><span class="sxs-lookup"><span data-stu-id="6922c-166">**Double**</span></span>|<span data-ttu-id="6922c-167">**double**</span><span class="sxs-lookup"><span data-stu-id="6922c-167">**double**</span></span>|<span data-ttu-id="6922c-168">**Double**</span><span class="sxs-lookup"><span data-stu-id="6922c-168">**Double**</span></span>|  
|<span data-ttu-id="6922c-169">**bool**</span><span class="sxs-lookup"><span data-stu-id="6922c-169">**bool**</span></span>|<span data-ttu-id="6922c-170">**Boolean**</span><span class="sxs-lookup"><span data-stu-id="6922c-170">**Boolean**</span></span>|<span data-ttu-id="6922c-171">**bool**</span><span class="sxs-lookup"><span data-stu-id="6922c-171">**bool**</span></span>|<span data-ttu-id="6922c-172">**Boolean**</span><span class="sxs-lookup"><span data-stu-id="6922c-172">**Boolean**</span></span>|  
|<span data-ttu-id="6922c-173">**char**</span><span class="sxs-lookup"><span data-stu-id="6922c-173">**char**</span></span>|<span data-ttu-id="6922c-174">**Char**</span><span class="sxs-lookup"><span data-stu-id="6922c-174">**Char**</span></span>|<span data-ttu-id="6922c-175">**wchar_t**</span><span class="sxs-lookup"><span data-stu-id="6922c-175">**wchar_t**</span></span>|<span data-ttu-id="6922c-176">**Char**</span><span class="sxs-lookup"><span data-stu-id="6922c-176">**Char**</span></span>|  
|<span data-ttu-id="6922c-177">**string**</span><span class="sxs-lookup"><span data-stu-id="6922c-177">**string**</span></span>|<span data-ttu-id="6922c-178">**String**</span><span class="sxs-lookup"><span data-stu-id="6922c-178">**String**</span></span>|<span data-ttu-id="6922c-179">**String**</span><span class="sxs-lookup"><span data-stu-id="6922c-179">**String**</span></span>|<span data-ttu-id="6922c-180">**String**</span><span class="sxs-lookup"><span data-stu-id="6922c-180">**String**</span></span>|  
|<span data-ttu-id="6922c-181">**object**</span><span class="sxs-lookup"><span data-stu-id="6922c-181">**object**</span></span>|<span data-ttu-id="6922c-182">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="6922c-182">**Object**</span></span>|<span data-ttu-id="6922c-183">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="6922c-183">**Object**</span></span>|<span data-ttu-id="6922c-184">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="6922c-184">**Object**</span></span>|  
  
 <span data-ttu-id="6922c-185">**✓ SI** utilizzare un nome comune, ad esempio `value` o `item`, piuttosto che ripetere il nome del tipo, in rari casi in cui un identificatore non ha alcun significato semantico e il tipo del parametro non è importante.</span><span class="sxs-lookup"><span data-stu-id="6922c-185">**✓ DO**  use a common name, such as `value` or `item`, rather than repeating the type name, in the rare cases when an identifier has no semantic meaning and the type of the parameter is not important.</span></span>  
  
## <a name="naming-new-versions-of-existing-apis"></a><span data-ttu-id="6922c-186">Denominazione di nuove versioni delle API esistente</span><span class="sxs-lookup"><span data-stu-id="6922c-186">Naming New Versions of Existing APIs</span></span>  
 <span data-ttu-id="6922c-187">**✓ SI** utilizzare un nome simile all'API precedente durante la creazione di nuove versioni di un'API esistente.</span><span class="sxs-lookup"><span data-stu-id="6922c-187">**✓ DO** use a name similar to the old API when creating new versions of an existing API.</span></span>  
  
 <span data-ttu-id="6922c-188">Ciò consente di evidenziare la relazione tra le API.</span><span class="sxs-lookup"><span data-stu-id="6922c-188">This helps to highlight the relationship between the APIs.</span></span>  
  
 <span data-ttu-id="6922c-189">**✓ SI** preferisce aggiungere un suffisso anziché un prefisso per indicare una nuova versione di un'API esistente.</span><span class="sxs-lookup"><span data-stu-id="6922c-189">**✓ DO** prefer adding a suffix rather than a prefix to indicate a new version of an existing API.</span></span>  
  
 <span data-ttu-id="6922c-190">Questo modo viene agevolata individuazione durante l'esplorazione di documentazione, o l'utilizzo di Intellisense.</span><span class="sxs-lookup"><span data-stu-id="6922c-190">This will assist discovery when browsing documentation, or using Intellisense.</span></span> <span data-ttu-id="6922c-191">La versione precedente dell'API verrà organizzata vicino a nuove API, poiché la maggior parte dei browser e Intellisense Mostra gli identificatori in ordine alfabetico.</span><span class="sxs-lookup"><span data-stu-id="6922c-191">The old version of the API will be organized close to the new APIs, because most browsers and Intellisense show identifiers in alphabetical order.</span></span>  
  
 <span data-ttu-id="6922c-192">**Provare a ✓** utilizzando un identificatore di nuovo, ma è significativo, anziché aggiungere un prefisso o suffisso.</span><span class="sxs-lookup"><span data-stu-id="6922c-192">**✓ CONSIDER** using a brand new, but meaningful identifier, instead of adding a suffix or a prefix.</span></span>  
  
 <span data-ttu-id="6922c-193">**✓ SI** utilizzare un suffisso numerico per indicare una nuova versione di un'API esistente, in particolare se il nome dell'API esistente è l'unico nome appropriato (ad esempio, se si tratta di uno standard del settore) e se si aggiungono significativo qualsiasi suffisso (o la modifica del nome) non è un'app opzione ropriate.</span><span class="sxs-lookup"><span data-stu-id="6922c-193">**✓ DO** use a numeric suffix to indicate a new version of an existing API, particularly if the existing name of the API is the only name that makes sense (i.e., if it is an industry standard) and if adding any meaningful suffix (or changing the name) is not an appropriate option.</span></span>  
  
 <span data-ttu-id="6922c-194">**X non** utilizzare "Ex" (o una simile) suffisso di un identificatore per distinguerlo da una versione precedente dell'API stessa.</span><span class="sxs-lookup"><span data-stu-id="6922c-194">**X DO NOT** use the "Ex" (or a similar) suffix for an identifier to distinguish it from an earlier version of the same API.</span></span>  
  
 <span data-ttu-id="6922c-195">**✓ SI** utilizza il suffisso "64" quando si introduce le versioni delle API che operano su un valore integer a 64 bit (un valore long integer) anziché un intero a 32 bit.</span><span class="sxs-lookup"><span data-stu-id="6922c-195">**✓ DO** use the "64" suffix when introducing versions of APIs that operate on a 64-bit integer (a long integer) instead of a 32-bit integer.</span></span> <span data-ttu-id="6922c-196">È necessario adottare questo approccio quando è presente l'API di 32 bit esistente. non eseguire l'operazione per la nuove API con solo una versione a 64 bit.</span><span class="sxs-lookup"><span data-stu-id="6922c-196">You only need to take this approach when the existing 32-bit API exists; don’t do it for brand new APIs with only a 64-bit version.</span></span>  
  
 <span data-ttu-id="6922c-197">*Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*</span><span class="sxs-lookup"><span data-stu-id="6922c-197">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="6922c-198">*State ristampate dall'autorizzazione di Pearson Education, Inc. da [linee guida: convenzioni, idiomi e modelli per le librerie .NET di riutilizzabile, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina e Brad Abrams, pubblicato il 22 ottobre 2008 di Addison-Wesley Professional come parte della serie di sviluppo di Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="6922c-198">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6922c-199">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6922c-199">See Also</span></span>  
 [<span data-ttu-id="6922c-200">Linee guida per la progettazione di Framework</span><span class="sxs-lookup"><span data-stu-id="6922c-200">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="6922c-201">Convenzioni di denominazione</span><span class="sxs-lookup"><span data-stu-id="6922c-201">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)

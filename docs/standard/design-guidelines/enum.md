---
title: Progettazione di enum
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- type design guidelines, enumerations
- simple enumerations
- enumerations [.NET Framework], design guidelines
- class library design guidelines [.NET Framework], enumerations
- flags enumerations
ms.assetid: dd53c952-9d9a-4736-86ff-9540e815d545
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9dea187b5f3911114e551d640e0bb0aa6fac1143
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2018
ms.locfileid: "43891233"
---
# <a name="enum-design"></a><span data-ttu-id="a5c59-102">Progettazione di enum</span><span class="sxs-lookup"><span data-stu-id="a5c59-102">Enum Design</span></span>
<span data-ttu-id="a5c59-103">Le enumerazioni sono un tipo speciale di tipo di valore.</span><span class="sxs-lookup"><span data-stu-id="a5c59-103">Enums are a special kind of value type.</span></span> <span data-ttu-id="a5c59-104">Esistono due tipi di enumerazioni: semplice enumerazioni di flag e le enumerazioni.</span><span class="sxs-lookup"><span data-stu-id="a5c59-104">There are two kinds of enums: simple enums and flag enums.</span></span>  
  
 <span data-ttu-id="a5c59-105">Enumerazioni semplici rappresentano piccoli set chiuso di scelte.</span><span class="sxs-lookup"><span data-stu-id="a5c59-105">Simple enums represent small closed sets of choices.</span></span> <span data-ttu-id="a5c59-106">Un esempio comune di enumerazione semplice è un set di colori.</span><span class="sxs-lookup"><span data-stu-id="a5c59-106">A common example of the simple enum is a set of colors.</span></span>  
  
 <span data-ttu-id="a5c59-107">Enumerazioni di flag sono progettate per supportare le operazioni bit per bit sui valori di enumerazione.</span><span class="sxs-lookup"><span data-stu-id="a5c59-107">Flag enums are designed to support bitwise operations on the enum values.</span></span> <span data-ttu-id="a5c59-108">Un esempio comune di enumerazione flag è un elenco di opzioni.</span><span class="sxs-lookup"><span data-stu-id="a5c59-108">A common example of the flags enum is a list of options.</span></span>  
  
 <span data-ttu-id="a5c59-109">**✓ DO** utilizzare un'enumerazione per tipizzare parametri, proprietà e restituiscono valori che rappresentano i set di valori.</span><span class="sxs-lookup"><span data-stu-id="a5c59-109">**✓ DO** use an enum to strongly type parameters, properties, and return values that represent sets of values.</span></span>  
  
 <span data-ttu-id="a5c59-110">**✓ DO** preferire l'utilizzo di un'enumerazione anziché costanti statiche.</span><span class="sxs-lookup"><span data-stu-id="a5c59-110">**✓ DO** favor using an enum instead of static constants.</span></span>  
  
 <span data-ttu-id="a5c59-111">**X DO NOT** utilizzare un tipo enum di set aperto (ad esempio la versione del sistema operativo, nomi degli amici, ecc.).</span><span class="sxs-lookup"><span data-stu-id="a5c59-111">**X DO NOT** use an enum for open sets (such as the operating system version, names of your friends, etc.).</span></span>  
  
 <span data-ttu-id="a5c59-112">**X DO NOT** forniscono valori enum riservato che servono per utilizzi futuri.</span><span class="sxs-lookup"><span data-stu-id="a5c59-112">**X DO NOT** provide reserved enum values that are intended for future use.</span></span>  
  
 <span data-ttu-id="a5c59-113">È possibile aggiungere sempre semplicemente i valori per l'enumerazione esistente in una fase successiva.</span><span class="sxs-lookup"><span data-stu-id="a5c59-113">You can always simply add values to the existing enum at a later stage.</span></span> <span data-ttu-id="a5c59-114">Visualizzare [aggiunta di valori per le enumerazioni](#add_value) per altri dettagli su come aggiungere i valori per le enumerazioni.</span><span class="sxs-lookup"><span data-stu-id="a5c59-114">See [Adding Values to Enums](#add_value) for more details on adding values to enums.</span></span> <span data-ttu-id="a5c59-115">Valori riservati solo contamina il set di valori reali e tendono a causare errori dell'utente.</span><span class="sxs-lookup"><span data-stu-id="a5c59-115">Reserved values just pollute the set of real values and tend to lead to user errors.</span></span>  
  
 <span data-ttu-id="a5c59-116">**X AVOID** esporre pubblicamente le enumerazioni con un solo valore.</span><span class="sxs-lookup"><span data-stu-id="a5c59-116">**X AVOID** publicly exposing enums with only one value.</span></span>  
  
 <span data-ttu-id="a5c59-117">Una pratica comune per garantire l'estensibilità futura delle API C consiste nell'aggiungere parametri riservati per le firme del metodo.</span><span class="sxs-lookup"><span data-stu-id="a5c59-117">A common practice for ensuring future extensibility of C APIs is to add reserved parameters to method signatures.</span></span> <span data-ttu-id="a5c59-118">Tali parametri riservati possono essere espresse come le enumerazioni con un singolo valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="a5c59-118">Such reserved parameters can be expressed as enums with a single default value.</span></span> <span data-ttu-id="a5c59-119">Non eseguire questa operazione per le API gestite.</span><span class="sxs-lookup"><span data-stu-id="a5c59-119">This should not be done in managed APIs.</span></span> <span data-ttu-id="a5c59-120">Metodi (overload) consente di aggiungere parametri nelle versioni future.</span><span class="sxs-lookup"><span data-stu-id="a5c59-120">Method overloading allows adding parameters in future releases.</span></span>  
  
 <span data-ttu-id="a5c59-121">**X DO NOT** includono valori sentinel nelle enumerazioni.</span><span class="sxs-lookup"><span data-stu-id="a5c59-121">**X DO NOT** include sentinel values in enums.</span></span>  
  
 <span data-ttu-id="a5c59-122">Anche se in alcuni casi sono utili per gli sviluppatori di framework, i valori di sentinel sono confondere gli utenti del framework.</span><span class="sxs-lookup"><span data-stu-id="a5c59-122">Although they are sometimes helpful to framework developers, sentinel values are confusing to users of the framework.</span></span> <span data-ttu-id="a5c59-123">Vengono utilizzati per tenere traccia dello stato di enum anziché da uno dei valori dal set rappresentato dal tipo enum.</span><span class="sxs-lookup"><span data-stu-id="a5c59-123">They are used to track the state of the enum rather than being one of the values from the set represented by the enum.</span></span>  
  
 <span data-ttu-id="a5c59-124">**✓ DO** fornire un valore pari a zero sulle enumerazioni semplici.</span><span class="sxs-lookup"><span data-stu-id="a5c59-124">**✓ DO** provide a value of zero on simple enums.</span></span>  
  
 <span data-ttu-id="a5c59-125">Si consiglia di chiamare il valore simile a "None".</span><span class="sxs-lookup"><span data-stu-id="a5c59-125">Consider calling the value something like "None."</span></span> <span data-ttu-id="a5c59-126">Se tale valore non è appropriato per questa enumerazione specifica, il valore predefinito più comune per l'enumerazione deve essere assegnato il valore sottostante pari a zero.</span><span class="sxs-lookup"><span data-stu-id="a5c59-126">If such a value is not appropriate for this particular enum, the most common default value for the enum should be assigned the underlying value of zero.</span></span>  
  
 <span data-ttu-id="a5c59-127">**✓ CONSIDER** utilizzando <xref:System.Int32> (impostazione predefinita nella maggior parte dei linguaggi di programmazione) con il tipo sottostante di un'enumerazione, a meno che una delle seguenti è true:</span><span class="sxs-lookup"><span data-stu-id="a5c59-127">**✓ CONSIDER** using <xref:System.Int32> (the default in most programming languages) as the underlying type of an enum unless any of the following is true:</span></span>  
  
-   <span data-ttu-id="a5c59-128">L'enumerazione è un enum di flag e si dispone di più di 32 flag o si aspettano di avere più in futuro.</span><span class="sxs-lookup"><span data-stu-id="a5c59-128">The enum is a flags enum and you have more than 32 flags, or expect to have more in the future.</span></span>  
  
-   <span data-ttu-id="a5c59-129">Il tipo sottostante deve essere diverso da quello <xref:System.Int32> per semplificare l'interoperabilità con codice non gestito è previsto delle enumerazioni di dimensioni diverse.</span><span class="sxs-lookup"><span data-stu-id="a5c59-129">The underlying type needs to be different than <xref:System.Int32> for easier interoperability with unmanaged code expecting different-size enums.</span></span>  
  
-   <span data-ttu-id="a5c59-130">Un tipo sottostante di dimensioni minori comporta risparmi notevoli in uno spazio.</span><span class="sxs-lookup"><span data-stu-id="a5c59-130">A smaller underlying type would result in substantial savings in space.</span></span> <span data-ttu-id="a5c59-131">Se si prevede che l'enumerazione da utilizzare principalmente come argomento per il flusso di controllo, le dimensioni poco rilevante.</span><span class="sxs-lookup"><span data-stu-id="a5c59-131">If you expect the enum to be used mainly as an argument for flow of control, the size makes little difference.</span></span> <span data-ttu-id="a5c59-132">Il risparmio di dimensioni potrebbe essere significativo se:</span><span class="sxs-lookup"><span data-stu-id="a5c59-132">The size savings might be significant if:</span></span>  
  
    -   <span data-ttu-id="a5c59-133">Si prevede che l'enumerazione da utilizzare come un campo in una struttura molto spesso un'istanza o una classe.</span><span class="sxs-lookup"><span data-stu-id="a5c59-133">You expect the enum to be used as a field in a very frequently instantiated structure or class.</span></span>  
  
    -   <span data-ttu-id="a5c59-134">Si prevede che agli utenti di creare matrici di grandi dimensioni o raccolte di istanze di enumerazione.</span><span class="sxs-lookup"><span data-stu-id="a5c59-134">You expect users to create large arrays or collections of the enum instances.</span></span>  
  
    -   <span data-ttu-id="a5c59-135">Previsto un numero elevato di istanze dell'enumerazione da serializzare.</span><span class="sxs-lookup"><span data-stu-id="a5c59-135">You expect a large number of instances of the enum to be serialized.</span></span>  
  
 <span data-ttu-id="a5c59-136">Per informazioni sull'utilizzo in memoria, tenere presente che gli oggetti gestiti siano sempre `DWORD`-allineati, pertanto è necessario in modo efficace più enumerazioni o altre strutture di piccole dimensioni in un'istanza per comprimere un'enumerazione con più piccola per fare la differenza, poiché la dimensione totale dell'istanza è sempre continua a essere arrotondato per eccesso una `DWORD`.</span><span class="sxs-lookup"><span data-stu-id="a5c59-136">For in-memory usage, be aware that managed objects are always `DWORD`-aligned, so you effectively need multiple enums or other small structures in an instance to pack a smaller enum with in order to make a difference, because the total instance size is always going to be rounded up to a `DWORD`.</span></span>  
  
 <span data-ttu-id="a5c59-137">**✓ DO** denominare le enumerazioni di flag con plurale o sintagmi nominali e le enumerazioni semplici con singolare o sintagmi nominali.</span><span class="sxs-lookup"><span data-stu-id="a5c59-137">**✓ DO** name flag enums with plural nouns or noun phrases and simple enums with singular nouns or noun phrases.</span></span>  
  
 <span data-ttu-id="a5c59-138">**X DO NOT** estendere <xref:System.Enum?displayProperty=nameWithType> direttamente.</span><span class="sxs-lookup"><span data-stu-id="a5c59-138">**X DO NOT** extend <xref:System.Enum?displayProperty=nameWithType> directly.</span></span>  
  
 <span data-ttu-id="a5c59-139"><xref:System.Enum?displayProperty=nameWithType> è un tipo speciale utilizzato da CLR per creare enumerazioni definite dall'utente.</span><span class="sxs-lookup"><span data-stu-id="a5c59-139"><xref:System.Enum?displayProperty=nameWithType> is a special type used by the CLR to create user-defined enumerations.</span></span> <span data-ttu-id="a5c59-140">La maggior parte dei linguaggi di programmazione forniscono un elemento di programmazione che consente di accedere a questa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="a5c59-140">Most programming languages provide a programming element that gives you access to this functionality.</span></span> <span data-ttu-id="a5c59-141">Ad esempio, in c# il `enum` parola chiave viene usata per definire un'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="a5c59-141">For example, in C# the `enum` keyword is used to define an enumeration.</span></span>  
  
<a name="design"></a>   
### <a name="designing-flag-enums"></a><span data-ttu-id="a5c59-142">Progettazione enumerazioni di Flag</span><span class="sxs-lookup"><span data-stu-id="a5c59-142">Designing Flag Enums</span></span>  
 <span data-ttu-id="a5c59-143">**✓ DO** applica il <xref:System.FlagsAttribute?displayProperty=nameWithType> per le enumerazioni di flag.</span><span class="sxs-lookup"><span data-stu-id="a5c59-143">**✓ DO** apply the <xref:System.FlagsAttribute?displayProperty=nameWithType> to flag enums.</span></span> <span data-ttu-id="a5c59-144">Non si applica questo attributo per le enumerazioni semplici.</span><span class="sxs-lookup"><span data-stu-id="a5c59-144">Do not apply this attribute to simple enums.</span></span>  
  
 <span data-ttu-id="a5c59-145">**✓ DO** utilizzano potenze di due per i valori di enumerazione flag pertanto possono essere liberamente combinati mediante un'operazione OR bit per bit.</span><span class="sxs-lookup"><span data-stu-id="a5c59-145">**✓ DO** use powers of two for the flag enum values so they can be freely combined using the bitwise OR operation.</span></span>  
  
 <span data-ttu-id="a5c59-146">**✓ CONSIDER** fornendo valori enum speciale per comunemente utilizzato le combinazioni di flag.</span><span class="sxs-lookup"><span data-stu-id="a5c59-146">**✓ CONSIDER** providing special enum values for commonly used combinations of flags.</span></span>  
  
 <span data-ttu-id="a5c59-147">Operazioni bit per bit sono un concetto avanzato e non dovrebbero essere necessarie per eseguire semplici operazioni.</span><span class="sxs-lookup"><span data-stu-id="a5c59-147">Bitwise operations are an advanced concept and should not be required for simple tasks.</span></span> <span data-ttu-id="a5c59-148"><xref:System.IO.FileAccess.ReadWrite> è un esempio di un valore speciale.</span><span class="sxs-lookup"><span data-stu-id="a5c59-148"><xref:System.IO.FileAccess.ReadWrite> is an example of such a special value.</span></span>  
  
 <span data-ttu-id="a5c59-149">**X AVOID** creazione le enumerazioni di flag in cui non sono valide alcune combinazioni di valori.</span><span class="sxs-lookup"><span data-stu-id="a5c59-149">**X AVOID** creating flag enums where certain combinations of values are invalid.</span></span>  
  
 <span data-ttu-id="a5c59-150">**X AVOID** utilizzando flag valori enum pari a zero, a meno che il valore rappresenta "tutti i flag vengono cancellati" ed è denominato in modo appropriato, come stabilito dalla linea guida successiva.</span><span class="sxs-lookup"><span data-stu-id="a5c59-150">**X AVOID** using flag enum values of zero unless the value represents "all flags are cleared" and is named appropriately, as prescribed by the next guideline.</span></span>  
  
 <span data-ttu-id="a5c59-151">**✓ DO** denominare il valore zero di enumerazioni di flag `None`.</span><span class="sxs-lookup"><span data-stu-id="a5c59-151">**✓ DO** name the zero value of flag enums `None`.</span></span> <span data-ttu-id="a5c59-152">Per un enum di flag, il valore deve sempre indicare che "tutti i flag vengono cancellati."</span><span class="sxs-lookup"><span data-stu-id="a5c59-152">For a flag enum, the value must always mean "all flags are cleared."</span></span>  
  
<a name="add_value"></a>   
### <a name="adding-value-to-enums"></a><span data-ttu-id="a5c59-153">Aggiunta di valore per le enumerazioni</span><span class="sxs-lookup"><span data-stu-id="a5c59-153">Adding Value to Enums</span></span>  
 <span data-ttu-id="a5c59-154">È molto comune per individuare che è necessario aggiungere valori a un tipo enum dopo aver spedito già.</span><span class="sxs-lookup"><span data-stu-id="a5c59-154">It is very common to discover that you need to add values to an enum after you have already shipped it.</span></span> <span data-ttu-id="a5c59-155">È un potenziale problema di compatibilità dell'applicazione quando il valore appena aggiunto viene restituito da un'API esistente, poiché le applicazioni scritte in modo inadeguato non potrebbero gestire correttamente il nuovo valore.</span><span class="sxs-lookup"><span data-stu-id="a5c59-155">There is a potential application compatibility problem when the newly added value is returned from an existing API, because poorly written applications might not handle the new value correctly.</span></span>  
  
 <span data-ttu-id="a5c59-156">**✓ CONSIDER** aggiunta di valori per le enumerazioni, nonostante un rischio per la compatibilità di piccole dimensioni.</span><span class="sxs-lookup"><span data-stu-id="a5c59-156">**✓ CONSIDER** adding values to enums, despite a small compatibility risk.</span></span>  
  
 <span data-ttu-id="a5c59-157">Se si dispone di dati reali sull'incompatibilità delle applicazioni causati da aggiunte a un'enumerazione, è consigliabile aggiungere una nuova API che restituisce i valori vecchi e nuovi e deprecare l'API precedente, che deve continuare restituendo solo i valori precedenti.</span><span class="sxs-lookup"><span data-stu-id="a5c59-157">If you have real data about application incompatibilities caused by additions to an enum, consider adding a new API that returns the new and old values, and deprecate the old API, which should continue returning just the old values.</span></span> <span data-ttu-id="a5c59-158">Ciò garantisce che le applicazioni esistenti restino compatibili.</span><span class="sxs-lookup"><span data-stu-id="a5c59-158">This will ensure that your existing applications remain compatible.</span></span>  
  
 <span data-ttu-id="a5c59-159">*Parti protette da copyright © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*</span><span class="sxs-lookup"><span data-stu-id="a5c59-159">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="a5c59-160">*Ristampato con l'autorizzazione di Pearson Education, Inc. da [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2a edizione](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) di Krzysztof Cwalina and Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional nella collana Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="a5c59-160">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5c59-161">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a5c59-161">See also</span></span>

- [<span data-ttu-id="a5c59-162">Linee guida per la progettazione di tipi</span><span class="sxs-lookup"><span data-stu-id="a5c59-162">Type Design Guidelines</span></span>](../../../docs/standard/design-guidelines/type.md)  
- [<span data-ttu-id="a5c59-163">Linee guida per la progettazione di Framework</span><span class="sxs-lookup"><span data-stu-id="a5c59-163">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)

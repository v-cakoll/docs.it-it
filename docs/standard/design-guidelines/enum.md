---
title: Progettazione di enum
description: Progettazione per le enumerazioni, che sono un tipo speciale di tipo di valore. Le enumerazioni semplici contengono set di scelte ridotte e chiuse. Le enumerazioni di flag supportano operazioni bit per bit sui valori enum.
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- type design guidelines, enumerations
- simple enumerations
- enumerations [.NET Framework], design guidelines
- class library design guidelines [.NET Framework], enumerations
- flags enumerations
ms.assetid: dd53c952-9d9a-4736-86ff-9540e815d545
ms.openlocfilehash: 40a9faf53dc8a03674cd59074244c15cd304bdd2
ms.sourcegitcommit: 5fd4696a3e5791b2a8c449ccffda87f2cc2d4894
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/15/2020
ms.locfileid: "84768537"
---
# <a name="enum-design"></a><span data-ttu-id="3ba80-105">Progettazione di enum</span><span class="sxs-lookup"><span data-stu-id="3ba80-105">Enum Design</span></span>

<span data-ttu-id="3ba80-106">Le enumerazioni sono un tipo speciale di tipo di valore.</span><span class="sxs-lookup"><span data-stu-id="3ba80-106">Enums are a special kind of value type.</span></span> <span data-ttu-id="3ba80-107">Esistono due tipi di enumerazioni: enum semplici ed enumerazioni di flag.</span><span class="sxs-lookup"><span data-stu-id="3ba80-107">There are two kinds of enums: simple enums and flag enums.</span></span>

<span data-ttu-id="3ba80-108">Le enumerazioni semplici rappresentano set di scelte chiusi di piccole dimensioni.</span><span class="sxs-lookup"><span data-stu-id="3ba80-108">Simple enums represent small closed sets of choices.</span></span> <span data-ttu-id="3ba80-109">Un esempio comune di enum semplice è costituito da un set di colori.</span><span class="sxs-lookup"><span data-stu-id="3ba80-109">A common example of the simple enum is a set of colors.</span></span>

<span data-ttu-id="3ba80-110">Le enumerazioni di flag sono progettate per supportare operazioni bit per bit sui valori enum.</span><span class="sxs-lookup"><span data-stu-id="3ba80-110">Flag enums are designed to support bitwise operations on the enum values.</span></span> <span data-ttu-id="3ba80-111">Un esempio comune di enumerazione Flags è un elenco di opzioni.</span><span class="sxs-lookup"><span data-stu-id="3ba80-111">A common example of the flags enum is a list of options.</span></span>

<span data-ttu-id="3ba80-112">✔️ utilizzare un'enumerazione per tipizzare in modo sicuro parametri, proprietà e valori restituiti che rappresentano set di valori.</span><span class="sxs-lookup"><span data-stu-id="3ba80-112">✔️ DO use an enum to strongly type parameters, properties, and return values that represent sets of values.</span></span>

<span data-ttu-id="3ba80-113">✔️ prediligono l'uso di un'enumerazione anziché di costanti statiche.</span><span class="sxs-lookup"><span data-stu-id="3ba80-113">✔️ DO favor using an enum instead of static constants.</span></span>

<span data-ttu-id="3ba80-114">❌Non usare un'enumerazione per i set aperti, ad esempio la versione del sistema operativo, i nomi degli amici e così via.</span><span class="sxs-lookup"><span data-stu-id="3ba80-114">❌ DO NOT use an enum for open sets (such as the operating system version, names of your friends, etc.).</span></span>

<span data-ttu-id="3ba80-115">❌NON fornire valori di enumerazione riservati destinati a un uso futuro.</span><span class="sxs-lookup"><span data-stu-id="3ba80-115">❌ DO NOT provide reserved enum values that are intended for future use.</span></span>

<span data-ttu-id="3ba80-116">È sempre possibile aggiungere semplicemente valori all'enum esistente in una fase successiva.</span><span class="sxs-lookup"><span data-stu-id="3ba80-116">You can always simply add values to the existing enum at a later stage.</span></span> <span data-ttu-id="3ba80-117">Per ulteriori informazioni sull'aggiunta di valori alle enumerazioni, vedere [aggiunta di valori alle enumerazioni](#add_value) .</span><span class="sxs-lookup"><span data-stu-id="3ba80-117">See [Adding Values to Enums](#add_value) for more details on adding values to enums.</span></span> <span data-ttu-id="3ba80-118">I valori riservati non inquinano il set di valori reali e tendono a causare errori dell'utente.</span><span class="sxs-lookup"><span data-stu-id="3ba80-118">Reserved values just pollute the set of real values and tend to lead to user errors.</span></span>

<span data-ttu-id="3ba80-119">❌EVITARE di esporre pubblicamente le enumerazioni con un solo valore.</span><span class="sxs-lookup"><span data-stu-id="3ba80-119">❌ AVOID publicly exposing enums with only one value.</span></span>

<span data-ttu-id="3ba80-120">Una procedura comune per garantire l'estendibilità futura delle API C consiste nell'aggiungere parametri riservati alle firme dei metodi.</span><span class="sxs-lookup"><span data-stu-id="3ba80-120">A common practice for ensuring future extensibility of C APIs is to add reserved parameters to method signatures.</span></span> <span data-ttu-id="3ba80-121">Tali parametri riservati possono essere espressi come enum con un unico valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="3ba80-121">Such reserved parameters can be expressed as enums with a single default value.</span></span> <span data-ttu-id="3ba80-122">Questa operazione non deve essere eseguita nelle API gestite.</span><span class="sxs-lookup"><span data-stu-id="3ba80-122">This should not be done in managed APIs.</span></span> <span data-ttu-id="3ba80-123">L'overload dei metodi consente l'aggiunta di parametri nelle versioni future.</span><span class="sxs-lookup"><span data-stu-id="3ba80-123">Method overloading allows adding parameters in future releases.</span></span>

<span data-ttu-id="3ba80-124">❌Non includere valori sentinel nelle enumerazioni.</span><span class="sxs-lookup"><span data-stu-id="3ba80-124">❌ DO NOT include sentinel values in enums.</span></span>

<span data-ttu-id="3ba80-125">Sebbene siano talvolta utili per gli sviluppatori di Framework, i valori sentinella creano confusione per gli utenti del Framework.</span><span class="sxs-lookup"><span data-stu-id="3ba80-125">Although they are sometimes helpful to framework developers, sentinel values are confusing to users of the framework.</span></span> <span data-ttu-id="3ba80-126">Vengono utilizzati per tenere traccia dello stato dell'enumerazione anziché di uno dei valori del set rappresentato dall'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="3ba80-126">They are used to track the state of the enum rather than being one of the values from the set represented by the enum.</span></span>

<span data-ttu-id="3ba80-127">✔️ forniscono un valore pari a zero nelle enumerazioni semplici.</span><span class="sxs-lookup"><span data-stu-id="3ba80-127">✔️ DO provide a value of zero on simple enums.</span></span>

<span data-ttu-id="3ba80-128">Prendere in considerazione la chiamata di un valore simile a "None".</span><span class="sxs-lookup"><span data-stu-id="3ba80-128">Consider calling the value something like "None."</span></span> <span data-ttu-id="3ba80-129">Se tale valore non è appropriato per questa enumerazione specifica, il valore predefinito più comune per l'enumerazione deve essere assegnato al valore sottostante pari a zero.</span><span class="sxs-lookup"><span data-stu-id="3ba80-129">If such a value is not appropriate for this particular enum, the most common default value for the enum should be assigned the underlying value of zero.</span></span>

<span data-ttu-id="3ba80-130">✔️ CONSIGLIABILE utilizzare <xref:System.Int32> (il valore predefinito nella maggior parte dei linguaggi di programmazione) come tipo sottostante di un'enumerazione, a meno che non esista una delle condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="3ba80-130">✔️ CONSIDER using <xref:System.Int32> (the default in most programming languages) as the underlying type of an enum unless any of the following is true:</span></span>

- <span data-ttu-id="3ba80-131">Enum è un'enumerazione Flags e sono presenti più di 32 flag oppure si prevede di avere più in futuro.</span><span class="sxs-lookup"><span data-stu-id="3ba80-131">The enum is a flags enum and you have more than 32 flags, or expect to have more in the future.</span></span>

- <span data-ttu-id="3ba80-132">Il tipo sottostante deve essere diverso da quello <xref:System.Int32> per semplificare l'interoperabilità con codice non gestito che prevede enum di dimensioni diverse.</span><span class="sxs-lookup"><span data-stu-id="3ba80-132">The underlying type needs to be different than <xref:System.Int32> for easier interoperability with unmanaged code expecting different-size enums.</span></span>

- <span data-ttu-id="3ba80-133">Un tipo sottostante più piccolo comporta un notevole risparmio nello spazio.</span><span class="sxs-lookup"><span data-stu-id="3ba80-133">A smaller underlying type would result in substantial savings in space.</span></span> <span data-ttu-id="3ba80-134">Se si prevede che l'enumerazione venga utilizzata principalmente come argomento per il flusso di controllo, le dimensioni hanno poca differenza.</span><span class="sxs-lookup"><span data-stu-id="3ba80-134">If you expect the enum to be used mainly as an argument for flow of control, the size makes little difference.</span></span> <span data-ttu-id="3ba80-135">Il risparmio di dimensioni può essere significativo se:</span><span class="sxs-lookup"><span data-stu-id="3ba80-135">The size savings might be significant if:</span></span>

  - <span data-ttu-id="3ba80-136">Si prevede che l'enumerazione venga utilizzata come campo in una struttura o una classe con un'istanza molto frequente.</span><span class="sxs-lookup"><span data-stu-id="3ba80-136">You expect the enum to be used as a field in a very frequently instantiated structure or class.</span></span>

  - <span data-ttu-id="3ba80-137">Si prevede che gli utenti creino matrici o raccolte di grandi dimensioni delle istanze di enum.</span><span class="sxs-lookup"><span data-stu-id="3ba80-137">You expect users to create large arrays or collections of the enum instances.</span></span>

  - <span data-ttu-id="3ba80-138">Si prevede che un numero elevato di istanze dell'enum venga serializzato.</span><span class="sxs-lookup"><span data-stu-id="3ba80-138">You expect a large number of instances of the enum to be serialized.</span></span>

<span data-ttu-id="3ba80-139">Per quanto riguarda l'utilizzo in memoria, tenere presente che gli oggetti gestiti sono sempre `DWORD` allineati, pertanto è necessario disporre di più enumerazioni o altre strutture di piccole dimensioni in un'istanza per comprimere un'enum più piccola con per fare una differenza, in quanto le dimensioni totali dell'istanza verranno sempre arrotondate per eccesso a un `DWORD` .</span><span class="sxs-lookup"><span data-stu-id="3ba80-139">For in-memory usage, be aware that managed objects are always `DWORD`-aligned, so you effectively need multiple enums or other small structures in an instance to pack a smaller enum with in order to make a difference, because the total instance size is always going to be rounded up to a `DWORD`.</span></span>

<span data-ttu-id="3ba80-140">✔️ le enumerazioni dei flag nome con Sostantivi plurali o frasi sostantivi e semplici enumerazioni con sostantivi singolari o frasi sostantive.</span><span class="sxs-lookup"><span data-stu-id="3ba80-140">✔️ DO name flag enums with plural nouns or noun phrases and simple enums with singular nouns or noun phrases.</span></span>

<span data-ttu-id="3ba80-141">❌NON estendere <xref:System.Enum?displayProperty=nameWithType> direttamente.</span><span class="sxs-lookup"><span data-stu-id="3ba80-141">❌ DO NOT extend <xref:System.Enum?displayProperty=nameWithType> directly.</span></span>

<span data-ttu-id="3ba80-142"><xref:System.Enum?displayProperty=nameWithType>è un tipo speciale utilizzato da CLR per creare enumerazioni definite dall'utente.</span><span class="sxs-lookup"><span data-stu-id="3ba80-142"><xref:System.Enum?displayProperty=nameWithType> is a special type used by the CLR to create user-defined enumerations.</span></span> <span data-ttu-id="3ba80-143">La maggior parte dei linguaggi di programmazione fornisce un elemento di programmazione che consente di accedere a questa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="3ba80-143">Most programming languages provide a programming element that gives you access to this functionality.</span></span> <span data-ttu-id="3ba80-144">In C#, ad esempio, la `enum` parola chiave viene usata per definire un'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="3ba80-144">For example, in C# the `enum` keyword is used to define an enumeration.</span></span>

<a name="design"></a>

### <a name="designing-flag-enums"></a><span data-ttu-id="3ba80-145">Progettazione di enumerazioni di flag</span><span class="sxs-lookup"><span data-stu-id="3ba80-145">Designing Flag Enums</span></span>

<span data-ttu-id="3ba80-146">✔️ applicare l'oggetto <xref:System.FlagsAttribute?displayProperty=nameWithType> per contrassegnare le enumerazioni.</span><span class="sxs-lookup"><span data-stu-id="3ba80-146">✔️ DO apply the <xref:System.FlagsAttribute?displayProperty=nameWithType> to flag enums.</span></span> <span data-ttu-id="3ba80-147">Non applicare questo attributo alle enumerazioni semplici.</span><span class="sxs-lookup"><span data-stu-id="3ba80-147">Do not apply this attribute to simple enums.</span></span>

<span data-ttu-id="3ba80-148">✔️ usano le potenze di due per i valori enum del flag, in modo che possano essere combinati liberamente usando l'operazione OR bit per bit.</span><span class="sxs-lookup"><span data-stu-id="3ba80-148">✔️ DO use powers of two for the flag enum values so they can be freely combined using the bitwise OR operation.</span></span>

<span data-ttu-id="3ba80-149">✔️ CONSIGLIABILE fornire valori enum speciali per le combinazioni di flag comunemente utilizzate.</span><span class="sxs-lookup"><span data-stu-id="3ba80-149">✔️ CONSIDER providing special enum values for commonly used combinations of flags.</span></span>

<span data-ttu-id="3ba80-150">Le operazioni bit per bit sono un concetto avanzato e non devono essere necessarie per le attività semplici.</span><span class="sxs-lookup"><span data-stu-id="3ba80-150">Bitwise operations are an advanced concept and should not be required for simple tasks.</span></span> <span data-ttu-id="3ba80-151"><xref:System.IO.FileAccess.ReadWrite>è un esempio di tale valore speciale.</span><span class="sxs-lookup"><span data-stu-id="3ba80-151"><xref:System.IO.FileAccess.ReadWrite> is an example of such a special value.</span></span>

<span data-ttu-id="3ba80-152">❌EVITARE di creare enumerazioni di flag in cui determinate combinazioni di valori non sono valide.</span><span class="sxs-lookup"><span data-stu-id="3ba80-152">❌ AVOID creating flag enums where certain combinations of values are invalid.</span></span>

<span data-ttu-id="3ba80-153">❌EVITARE di utilizzare valori enum di flag pari a zero, a meno che il valore non rappresenti "tutti i flag sono cancellati" ed è denominato in modo appropriato, come previsto dalle linee guida successive.</span><span class="sxs-lookup"><span data-stu-id="3ba80-153">❌ AVOID using flag enum values of zero unless the value represents "all flags are cleared" and is named appropriately, as prescribed by the next guideline.</span></span>

<span data-ttu-id="3ba80-154">✔️ Denominare il valore zero delle enumerazioni di flag `None` .</span><span class="sxs-lookup"><span data-stu-id="3ba80-154">✔️ DO name the zero value of flag enums `None`.</span></span> <span data-ttu-id="3ba80-155">Per l'enumerazione di un flag, il valore deve sempre indicare che tutti i flag sono cancellati.</span><span class="sxs-lookup"><span data-stu-id="3ba80-155">For a flag enum, the value must always mean "all flags are cleared."</span></span>

<a name="add_value"></a>

### <a name="adding-value-to-enums"></a><span data-ttu-id="3ba80-156">Aggiunta di un valore alle enumerazioni</span><span class="sxs-lookup"><span data-stu-id="3ba80-156">Adding Value to Enums</span></span>

<span data-ttu-id="3ba80-157">È molto comune rilevare che è necessario aggiungere valori a un'enum dopo che è già stato spedito.</span><span class="sxs-lookup"><span data-stu-id="3ba80-157">It is very common to discover that you need to add values to an enum after you have already shipped it.</span></span> <span data-ttu-id="3ba80-158">Si verifica un potenziale problema di compatibilità delle applicazioni quando viene restituito il valore appena aggiunto da un'API esistente, perché le applicazioni scritte in modo non corretto potrebbero non gestire correttamente il nuovo valore.</span><span class="sxs-lookup"><span data-stu-id="3ba80-158">There is a potential application compatibility problem when the newly added value is returned from an existing API, because poorly written applications might not handle the new value correctly.</span></span>

<span data-ttu-id="3ba80-159">✔️ CONSIGLIABILE aggiungere valori alle enumerazioni, nonostante un piccolo rischio di compatibilità.</span><span class="sxs-lookup"><span data-stu-id="3ba80-159">✔️ CONSIDER adding values to enums, despite a small compatibility risk.</span></span>

<span data-ttu-id="3ba80-160">Se sono presenti dati reali sulle incompatibilità delle applicazioni causati da aggiunte a un'enumerazione, è consigliabile aggiungere una nuova API che restituisce i valori nuovi e precedenti e deprecare l'API precedente, che dovrebbe continuare a restituire solo i valori precedenti.</span><span class="sxs-lookup"><span data-stu-id="3ba80-160">If you have real data about application incompatibilities caused by additions to an enum, consider adding a new API that returns the new and old values, and deprecate the old API, which should continue returning just the old values.</span></span> <span data-ttu-id="3ba80-161">In questo modo le applicazioni esistenti rimarranno compatibili.</span><span class="sxs-lookup"><span data-stu-id="3ba80-161">This will ensure that your existing applications remain compatible.</span></span>

<span data-ttu-id="3ba80-162">*Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*</span><span class="sxs-lookup"><span data-stu-id="3ba80-162">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

<span data-ttu-id="3ba80-163">*Ristampato con l'autorizzazione di Pearson Education, Inc. da [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2a edizione](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) di Krzysztof Cwalina and Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional nella collana Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="3ba80-163">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="3ba80-164">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3ba80-164">See also</span></span>

- [<span data-ttu-id="3ba80-165">Linee guida per la progettazione di tipi</span><span class="sxs-lookup"><span data-stu-id="3ba80-165">Type Design Guidelines</span></span>](type.md)
- [<span data-ttu-id="3ba80-166">Linee guida per la progettazione di Framework</span><span class="sxs-lookup"><span data-stu-id="3ba80-166">Framework Design Guidelines</span></span>](index.md)

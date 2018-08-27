---
title: 'Indicazioni per la progettazione di componente F #'
description: "Scopri le linee guida per la scrittura di componenti di F # destinati all'utilizzo da altri chiamanti."
ms.date: 05/14/2018
ms.openlocfilehash: 446cba0f810af9517b655ef5741ddf7a919676d5
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2018
ms.locfileid: "42935597"
---
# <a name="f-component-design-guidelines"></a><span data-ttu-id="e3113-103">Indicazioni per la progettazione di componente F #</span><span class="sxs-lookup"><span data-stu-id="e3113-103">F# component design guidelines</span></span>

<span data-ttu-id="e3113-104">Questo documento è un set di linee guida di progettazione di componenti per F # di programmazione, in base a F # componente linee guida di progettazione, v14, Microsoft Research, e [un'altra versione](https://fsharp.org/specs/component-design-guidelines/) originariamente curata e gestito da F # Software Foundation.</span><span class="sxs-lookup"><span data-stu-id="e3113-104">This document is a set of component design guidelines for F# programming, based on the F# Component Design Guidelines, v14, Microsoft Research, and [another version](https://fsharp.org/specs/component-design-guidelines/) originally curated and maintained by the F# Software Foundation.</span></span>

<span data-ttu-id="e3113-105">Questo documento presuppone che si abbia familiarità con la programmazione F #.</span><span class="sxs-lookup"><span data-stu-id="e3113-105">This document assumes you are familiar with F# programming.</span></span> <span data-ttu-id="e3113-106">Si ringraziano community di F # per i relativi contributi e commenti e suggerimenti utili su varie versioni di questa Guida.</span><span class="sxs-lookup"><span data-stu-id="e3113-106">Many thanks to the F# community for their contributions and helpful feedback on various versions of this guide.</span></span>

## <a name="overview"></a><span data-ttu-id="e3113-107">Panoramica</span><span class="sxs-lookup"><span data-stu-id="e3113-107">Overview</span></span>

<span data-ttu-id="e3113-108">Vengono esaminati alcuni dei problemi relativi alla progettazione del componente F # e codifica.</span><span class="sxs-lookup"><span data-stu-id="e3113-108">This document looks at some of the issues related to F# component design and coding.</span></span> <span data-ttu-id="e3113-109">Un componente può significare che gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="e3113-109">A component can mean any of the following:</span></span>

* <span data-ttu-id="e3113-110">Un livello di progetto F # con utenti esterni all'interno di tale progetto.</span><span class="sxs-lookup"><span data-stu-id="e3113-110">A layer in your F# project that has external consumers within that project.</span></span>
* <span data-ttu-id="e3113-111">Una libreria destinata all'utilizzo tra limiti di assembly dal codice F #.</span><span class="sxs-lookup"><span data-stu-id="e3113-111">A library intended for consumption by F# code across assembly boundaries.</span></span>
* <span data-ttu-id="e3113-112">Una libreria destinata all'utilizzo da qualsiasi linguaggio .NET attraverso i limiti di assembly.</span><span class="sxs-lookup"><span data-stu-id="e3113-112">A library intended for consumption by any .NET language across assembly boundaries.</span></span>
* <span data-ttu-id="e3113-113">Una libreria destinata alla distribuzione tramite un repository dei pacchetti, ad esempio [NuGet](https://nuget.org).</span><span class="sxs-lookup"><span data-stu-id="e3113-113">A library intended for distribution via a package repository, such as [NuGet](https://nuget.org).</span></span>

<span data-ttu-id="e3113-114">Seguono le tecniche descritte in questo articolo il [cinque principi del buon codice F #](index.md#five-principles-of-good-f-code)e pertanto utilizzano entrambi funzionali e oggetti di programmazione come appropriato.</span><span class="sxs-lookup"><span data-stu-id="e3113-114">Techniques described in this article follow the [Five principles of good F# code](index.md#five-principles-of-good-f-code), and thus utilize both functional and object programming as appropriate.</span></span>

<span data-ttu-id="e3113-115">Indipendentemente dalla metodologia, la finestra di progettazione di componenti e la libreria deve affrontare alcuni problemi pratici e banale durante il tentativo di creare un'API più facilmente utilizzabile dagli sviluppatori.</span><span class="sxs-lookup"><span data-stu-id="e3113-115">Regardless of the methodology, the component and library designer faces a number of practical and prosaic issues when trying to craft an API that is most easily usable by developers.</span></span> <span data-ttu-id="e3113-116">Attenta applicazione dei [indicazioni per la progettazione di librerie .NET](../../standard/design-guidelines/index.md) verrà volgere è per la creazione di un set coerente di API che sono piacevole da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="e3113-116">Conscientious application of the [.NET Library Design Guidelines](../../standard/design-guidelines/index.md) will steer you towards creating a consistent set of APIs that are pleasant to consume.</span></span>

## <a name="general-guidelines"></a><span data-ttu-id="e3113-117">Indicazioni generali</span><span class="sxs-lookup"><span data-stu-id="e3113-117">General guidelines</span></span>

<span data-ttu-id="e3113-118">Esistono alcune indicazioni universali che si applicano a librerie F #, indipendentemente dal fatto i destinatari per la libreria.</span><span class="sxs-lookup"><span data-stu-id="e3113-118">There are a few universal guidelines that apply to F# libraries, regardless of the intended audience for the library.</span></span>

### <a name="learn-the-net-library-design-guidelines"></a><span data-ttu-id="e3113-119">Altre linee guida di progettazione di .NET della libreria</span><span class="sxs-lookup"><span data-stu-id="e3113-119">Learn the .NET Library Design Guidelines</span></span>

<span data-ttu-id="e3113-120">Indipendentemente dal tipo di F # codifica si sta eseguendo, è utile per avere una conoscenza del [indicazioni per la progettazione di librerie .NET](../../standard/design-guidelines/index.md).</span><span class="sxs-lookup"><span data-stu-id="e3113-120">Regardless of the kind of F# coding you are doing, it is valuable to have a working knowledge of the [.NET Library Design Guidelines](../../standard/design-guidelines/index.md).</span></span> <span data-ttu-id="e3113-121">La maggior parte delle altre F # e ai programmatori di .NET verranno avere familiarità con queste linee guida e prevede che il codice .NET di conformarsi a essi.</span><span class="sxs-lookup"><span data-stu-id="e3113-121">Most other F# and .NET programmers will be familiar with these guidelines, and expect .NET code to conform to them.</span></span>

<span data-ttu-id="e3113-122">Linee guida di progettazione di .NET della libreria fornite indicazioni generali sulla denominazione, la progettazione di classi e interfacce, progettazione di membri (proprietà, metodi, eventi, e così via) e altro ancora e sono un utile punto prima di riferimento per un'ampia gamma di materiale sussidiario di progettazione.</span><span class="sxs-lookup"><span data-stu-id="e3113-122">The .NET Library Design Guidelines provide general guidance regarding naming, designing classes and interfaces, member design (properties, methods, events, etc.) and more, and are a useful first point of reference for a variety of design guidance.</span></span>

### <a name="add-xml-documentation-comments-to-your-code"></a><span data-ttu-id="e3113-123">Aggiungere commenti in formato documentazione XML nel codice</span><span class="sxs-lookup"><span data-stu-id="e3113-123">Add XML documentation comments to your code</span></span>

<span data-ttu-id="e3113-124">Documentazione XML nelle API pubbliche assicurarsi che gli utenti possono ottenere eccezionali Intellisense e informazioni rapide durante l'utilizzo di questi tipi e membri e Abilita creazione di documentazione dei file per la libreria.</span><span class="sxs-lookup"><span data-stu-id="e3113-124">XML documentation on public APIs ensure that users can get great Intellisense and Quickinfo when using these types and members, and enable building documentation files for the library.</span></span> <span data-ttu-id="e3113-125">Vedere le [della documentazione XML](../language-reference/xml-documentation.md) sui vari tag xml che può essere usato per altri markup all'interno di commenti xmldoc.</span><span class="sxs-lookup"><span data-stu-id="e3113-125">See the [XML Documentation](../language-reference/xml-documentation.md) about various xml tags that can be used for additional markup within xmldoc comments.</span></span>

```fsharp
/// A class for representing (x,y) coordinates
type Point =

    /// Computes the distance between this point and another
    member DistanceTo : otherPoint:Point -> float
```

<span data-ttu-id="e3113-126">È possibile usare entrambi la versione abbreviata commenti in formato XML (`/// comment`), o commenti in formato XML standard (`///<summary>comment</summary>`).</span><span class="sxs-lookup"><span data-stu-id="e3113-126">You can use either the short form XML comments (`/// comment`), or standard XML comments (`///<summary>comment</summary>`).</span></span>

### <a name="consider-using-explicit-signature-files-fsi-for-stable-library-and-component-apis"></a><span data-ttu-id="e3113-127">È consigliabile usare file di firma esplicita (. fsi) per la libreria stabile e componente API</span><span class="sxs-lookup"><span data-stu-id="e3113-127">Consider using explicit signature files (.fsi) for stable library and component APIs</span></span>

<span data-ttu-id="e3113-128">Con le firme espliciti ai file in una libreria F # viene fornito un riepilogo dell'API pubblica, che consente di garantire che si conosce l'area pubblica completa della libreria, nonché offre una netta separazione tra documentazione pubblica e interni conciso dettagli di implementazione.</span><span class="sxs-lookup"><span data-stu-id="e3113-128">Using explicit signatures files in an F# library provides a succinct summary of public API, which both helps to ensure that you know the full public surface of your library, as well as provides a clean separation between public documentation and internal implementation details.</span></span> <span data-ttu-id="e3113-129">Si noti che i file delle firme aggiungono attrito per modificare l'API pubblica, tramite la richiesta di modifiche da apportare nei file di implementazione e la firma.</span><span class="sxs-lookup"><span data-stu-id="e3113-129">Note that signature files add friction to changing the public API, by requiring changes to be made in both the implementation and signature files.</span></span> <span data-ttu-id="e3113-130">Di conseguenza, i file di firma in genere solo da introdurre quando un'API ha diventano solidificata e non è più previsto cambi in modo significativo.</span><span class="sxs-lookup"><span data-stu-id="e3113-130">As a result, signature files should typically only be introduced when an API has become solidified and is no longer expected to change significantly.</span></span>

### <a name="always-follow-best-practices-for-using-strings-in-net"></a><span data-ttu-id="e3113-131">Seguire sempre le procedure consigliate per l'uso delle stringhe in .NET</span><span class="sxs-lookup"><span data-stu-id="e3113-131">Always follow best practices for using strings in .NET</span></span>

<span data-ttu-id="e3113-132">Seguire [procedure consigliate per l'uso di stringhe in .NET](../../standard/base-types/best-practices-strings.md) indicazioni.</span><span class="sxs-lookup"><span data-stu-id="e3113-132">Follow [Best Practices for Using Strings in .NET](../../standard/base-types/best-practices-strings.md) guidance.</span></span> <span data-ttu-id="e3113-133">In particolare, indicare sempre esplicitamente *finalità relative alla lingua* nella conversione e confronto di stringhe (dove applicabile).</span><span class="sxs-lookup"><span data-stu-id="e3113-133">In particular, always explicitly state *cultural intent* in the conversion and comparison of strings (where applicable).</span></span>

## <a name="guidelines-for-f-facing-libraries"></a><span data-ttu-id="e3113-134">Linee guida per F #-rivolta librerie</span><span class="sxs-lookup"><span data-stu-id="e3113-134">Guidelines for F#-facing libraries</span></span>

<span data-ttu-id="e3113-135">In questa sezione vengono offerti suggerimenti per lo sviluppo di pubbliche F #-rivolta alle librerie. vale a dire, le librerie che espone le API pubbliche che devono essere utilizzati dagli sviluppatori di F #.</span><span class="sxs-lookup"><span data-stu-id="e3113-135">This section presents recommendations for developing public F#-facing libraries; that is, libraries exposing public APIs that are intended to be consumed by F# developers.</span></span> <span data-ttu-id="e3113-136">Esistono diverse indicazioni di progettazione di librerie applicabile in particolare a F #.</span><span class="sxs-lookup"><span data-stu-id="e3113-136">There are a variety of library-design recommendations applicable specifically to F#.</span></span> <span data-ttu-id="e3113-137">In assenza di indicazioni specifiche che seguono, linee guida di progettazione di .NET della libreria sono le indicazioni di fallback.</span><span class="sxs-lookup"><span data-stu-id="e3113-137">In the absence of the specific recommendations that follow, the .NET Library Design Guidelines are the fallback guidance.</span></span>

### <a name="naming-conventions"></a><span data-ttu-id="e3113-138">Convenzioni di denominazione</span><span class="sxs-lookup"><span data-stu-id="e3113-138">Naming conventions</span></span>

#### <a name="use-net-naming-and-capitalization-conventions"></a><span data-ttu-id="e3113-139">Usare le convenzioni di denominazione e l'uso delle maiuscole .NET</span><span class="sxs-lookup"><span data-stu-id="e3113-139">Use .NET naming and capitalization conventions</span></span>

<span data-ttu-id="e3113-140">La tabella seguente rispetta le convenzioni di denominazione e l'uso delle maiuscole .NET.</span><span class="sxs-lookup"><span data-stu-id="e3113-140">The following table follows .NET naming and capitalization conventions.</span></span> <span data-ttu-id="e3113-141">Esistono piccole aggiunte per includere anche i costrutti F #.</span><span class="sxs-lookup"><span data-stu-id="e3113-141">There are small additions to also include F# constructs.</span></span>

| <span data-ttu-id="e3113-142">Costrutto</span><span class="sxs-lookup"><span data-stu-id="e3113-142">Construct</span></span> | <span data-ttu-id="e3113-143">Case</span><span class="sxs-lookup"><span data-stu-id="e3113-143">Case</span></span> | <span data-ttu-id="e3113-144">Parte</span><span class="sxs-lookup"><span data-stu-id="e3113-144">Part</span></span> | <span data-ttu-id="e3113-145">Esempi</span><span class="sxs-lookup"><span data-stu-id="e3113-145">Examples</span></span> | <span data-ttu-id="e3113-146">Note</span><span class="sxs-lookup"><span data-stu-id="e3113-146">Notes</span></span> |
|-----------|------|------|----------|-------|
| <span data-ttu-id="e3113-147">Tipi concreti</span><span class="sxs-lookup"><span data-stu-id="e3113-147">Concrete types</span></span> | <span data-ttu-id="e3113-148">PascalCase</span><span class="sxs-lookup"><span data-stu-id="e3113-148">PascalCase</span></span> | <span data-ttu-id="e3113-149">Sostantivo / aggettivali</span><span class="sxs-lookup"><span data-stu-id="e3113-149">Noun/ adjective</span></span> | <span data-ttu-id="e3113-150">Elenco, Double, complesso</span><span class="sxs-lookup"><span data-stu-id="e3113-150">List, Double, Complex</span></span> | <span data-ttu-id="e3113-151">Tipi concreti sono strutture, classi, enumerazioni, delegati, record e unioni.</span><span class="sxs-lookup"><span data-stu-id="e3113-151">Concrete types are structs, classes, enumerations, delegates, records, and unions.</span></span> <span data-ttu-id="e3113-152">Anche se i nomi dei tipi sono in genere in minuscoli in OCaml, F # ha adottato lo schema di denominazione .NET per i tipi.</span><span class="sxs-lookup"><span data-stu-id="e3113-152">Though type names are traditionally lowercase in OCaml, F# has adopted the .NET naming scheme for types.</span></span>
| <span data-ttu-id="e3113-153">DLL</span><span class="sxs-lookup"><span data-stu-id="e3113-153">DLLs</span></span>           | <span data-ttu-id="e3113-154">PascalCase</span><span class="sxs-lookup"><span data-stu-id="e3113-154">PascalCase</span></span> |                 | <span data-ttu-id="e3113-155">Fabrikam.Core.dll</span><span class="sxs-lookup"><span data-stu-id="e3113-155">Fabrikam.Core.dll</span></span> |  |
| <span data-ttu-id="e3113-156">Tag di unione</span><span class="sxs-lookup"><span data-stu-id="e3113-156">Union tags</span></span>     | <span data-ttu-id="e3113-157">PascalCase</span><span class="sxs-lookup"><span data-stu-id="e3113-157">PascalCase</span></span> | <span data-ttu-id="e3113-158">Sostantivo</span><span class="sxs-lookup"><span data-stu-id="e3113-158">Noun</span></span> | <span data-ttu-id="e3113-159">Alcuni casi, aggiungere, operazione riuscita</span><span class="sxs-lookup"><span data-stu-id="e3113-159">Some, Add, Success</span></span> | <span data-ttu-id="e3113-160">Non usare un prefisso nelle API pubbliche.</span><span class="sxs-lookup"><span data-stu-id="e3113-160">Do not use a prefix in public APIs.</span></span> <span data-ttu-id="e3113-161">Se lo si desidera usare un prefisso quando interni, ad esempio ' ' digitare team = TAlpha</span><span class="sxs-lookup"><span data-stu-id="e3113-161">Optionally use a prefix when internal, such as \`\`\`type Teams = TAlpha</span></span> | <span data-ttu-id="e3113-162">TBeta</span><span class="sxs-lookup"><span data-stu-id="e3113-162">TBeta</span></span> | <span data-ttu-id="e3113-163">TDelta. ' '</span><span class="sxs-lookup"><span data-stu-id="e3113-163">TDelta.\`\`\`</span></span> |
| <span data-ttu-id="e3113-164">event</span><span class="sxs-lookup"><span data-stu-id="e3113-164">Event</span></span>          | <span data-ttu-id="e3113-165">PascalCase</span><span class="sxs-lookup"><span data-stu-id="e3113-165">PascalCase</span></span> | <span data-ttu-id="e3113-166">Verbo</span><span class="sxs-lookup"><span data-stu-id="e3113-166">Verb</span></span> | <span data-ttu-id="e3113-167">ValueChanged / ValueChanging</span><span class="sxs-lookup"><span data-stu-id="e3113-167">ValueChanged / ValueChanging</span></span> |  |
| <span data-ttu-id="e3113-168">Eccezioni</span><span class="sxs-lookup"><span data-stu-id="e3113-168">Exceptions</span></span>     | <span data-ttu-id="e3113-169">PascalCase</span><span class="sxs-lookup"><span data-stu-id="e3113-169">PascalCase</span></span> |      | <span data-ttu-id="e3113-170">WebException</span><span class="sxs-lookup"><span data-stu-id="e3113-170">WebException</span></span> | <span data-ttu-id="e3113-171">Nome deve terminare con "Exception".</span><span class="sxs-lookup"><span data-stu-id="e3113-171">Name should end with “Exception”.</span></span> |
| <span data-ttu-id="e3113-172">Campo</span><span class="sxs-lookup"><span data-stu-id="e3113-172">Field</span></span>          | <span data-ttu-id="e3113-173">PascalCase</span><span class="sxs-lookup"><span data-stu-id="e3113-173">PascalCase</span></span> | <span data-ttu-id="e3113-174">Sostantivo</span><span class="sxs-lookup"><span data-stu-id="e3113-174">Noun</span></span> | <span data-ttu-id="e3113-175">CurrentName</span><span class="sxs-lookup"><span data-stu-id="e3113-175">CurrentName</span></span>  | |
| <span data-ttu-id="e3113-176">Tipi interfaccia</span><span class="sxs-lookup"><span data-stu-id="e3113-176">Interface types</span></span> |  <span data-ttu-id="e3113-177">PascalCase</span><span class="sxs-lookup"><span data-stu-id="e3113-177">PascalCase</span></span> | <span data-ttu-id="e3113-178">Sostantivo / aggettivali</span><span class="sxs-lookup"><span data-stu-id="e3113-178">Noun/ adjective</span></span> | <span data-ttu-id="e3113-179">IDisposable</span><span class="sxs-lookup"><span data-stu-id="e3113-179">IDisposable</span></span> | <span data-ttu-id="e3113-180">Nome deve iniziare con "I".</span><span class="sxs-lookup"><span data-stu-id="e3113-180">Name should start with “I”.</span></span> |
| <span data-ttu-id="e3113-181">Metodo</span><span class="sxs-lookup"><span data-stu-id="e3113-181">Method</span></span> |  <span data-ttu-id="e3113-182">PascalCase</span><span class="sxs-lookup"><span data-stu-id="e3113-182">PascalCase</span></span> |  <span data-ttu-id="e3113-183">Verbo</span><span class="sxs-lookup"><span data-stu-id="e3113-183">Verb</span></span> | <span data-ttu-id="e3113-184">ToString</span><span class="sxs-lookup"><span data-stu-id="e3113-184">ToString</span></span> | |
| <span data-ttu-id="e3113-185">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="e3113-185">Namespace</span></span> | <span data-ttu-id="e3113-186">PascalCase</span><span class="sxs-lookup"><span data-stu-id="e3113-186">PascalCase</span></span> | | <span data-ttu-id="e3113-187">FSharp</span><span class="sxs-lookup"><span data-stu-id="e3113-187">Microsoft.FSharp.Core</span></span> | <span data-ttu-id="e3113-188">In genere usano `<Organization>.<Technology>[.<Subnamespace>]`, eliminare anche se l'organizzazione se la tecnologia è indipendente dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e3113-188">Generally use `<Organization>.<Technology>[.<Subnamespace>]`, though drop the organization if the technology is independent of organization.</span></span> |
| <span data-ttu-id="e3113-189">Parametri</span><span class="sxs-lookup"><span data-stu-id="e3113-189">Parameters</span></span> | <span data-ttu-id="e3113-190">camelCase</span><span class="sxs-lookup"><span data-stu-id="e3113-190">camelCase</span></span> | <span data-ttu-id="e3113-191">Sostantivo</span><span class="sxs-lookup"><span data-stu-id="e3113-191">Noun</span></span> |  <span data-ttu-id="e3113-192">typeName, trasformazione, intervallo</span><span class="sxs-lookup"><span data-stu-id="e3113-192">typeName, transform, range</span></span> | |
| <span data-ttu-id="e3113-193">lasciare i valori (interni)</span><span class="sxs-lookup"><span data-stu-id="e3113-193">let values (internal)</span></span> | <span data-ttu-id="e3113-194">camelCase o PascalCase</span><span class="sxs-lookup"><span data-stu-id="e3113-194">camelCase or PascalCase</span></span> | <span data-ttu-id="e3113-195">Sostantivo / verbo</span><span class="sxs-lookup"><span data-stu-id="e3113-195">Noun/ verb</span></span> |  <span data-ttu-id="e3113-196">getValue, myTable</span><span class="sxs-lookup"><span data-stu-id="e3113-196">getValue, myTable</span></span> |
| <span data-ttu-id="e3113-197">lasciare i valori (esterno)</span><span class="sxs-lookup"><span data-stu-id="e3113-197">let values (external)</span></span> | <span data-ttu-id="e3113-198">camelCase o PascalCase</span><span class="sxs-lookup"><span data-stu-id="e3113-198">camelCase or PascalCase</span></span> | <span data-ttu-id="e3113-199">Sostantivo/verbo</span><span class="sxs-lookup"><span data-stu-id="e3113-199">Noun/verb</span></span>  | <span data-ttu-id="e3113-200">List. map, Dates.Today</span><span class="sxs-lookup"><span data-stu-id="e3113-200">List.map, Dates.Today</span></span> | <span data-ttu-id="e3113-201">i valori di associazione let sono pubblici spesso quando si seguono i modelli di progettazione funzionali tradizionale.</span><span class="sxs-lookup"><span data-stu-id="e3113-201">let-bound values are often public when following traditional functional design patterns.</span></span> <span data-ttu-id="e3113-202">Tuttavia, in genere usano la notazione Pascal quando l'identificatore può essere utilizzato da altri linguaggi .NET.</span><span class="sxs-lookup"><span data-stu-id="e3113-202">However, generally use PascalCase when the identifier can be used from other .NET languages.</span></span> |
| <span data-ttu-id="e3113-203">Proprietà</span><span class="sxs-lookup"><span data-stu-id="e3113-203">Property</span></span>  | <span data-ttu-id="e3113-204">PascalCase</span><span class="sxs-lookup"><span data-stu-id="e3113-204">PascalCase</span></span>  | <span data-ttu-id="e3113-205">Sostantivo / aggettivali</span><span class="sxs-lookup"><span data-stu-id="e3113-205">Noun/ adjective</span></span>  | <span data-ttu-id="e3113-206">IsEndOfFile, colore di sfondo</span><span class="sxs-lookup"><span data-stu-id="e3113-206">IsEndOfFile, BackColor</span></span>  | <span data-ttu-id="e3113-207">Le proprietà booleane in genere l'utilizzo è e può e deve essere affermativa perché, come illustrato IsEndOfFile, non IsNotEndOfFile.</span><span class="sxs-lookup"><span data-stu-id="e3113-207">Boolean properties generally use Is and Can and should be affirmative, as in IsEndOfFile, not IsNotEndOfFile.</span></span>

#### <a name="avoid-abbreviations"></a><span data-ttu-id="e3113-208">Evitare le abbreviazioni</span><span class="sxs-lookup"><span data-stu-id="e3113-208">Avoid abbreviations</span></span>

<span data-ttu-id="e3113-209">Linee guida di .NET sconsiglia l'uso di abbreviazioni (ad esempio, "utilizzare `OnButtonClick` anziché `OnBtnClick`").</span><span class="sxs-lookup"><span data-stu-id="e3113-209">The .NET guidelines discourage the use of abbreviations (for example, “use `OnButtonClick` rather than `OnBtnClick`”).</span></span> <span data-ttu-id="e3113-210">Le abbreviazioni comuni, ad esempio `Async` per "Asincrono", è consentito.</span><span class="sxs-lookup"><span data-stu-id="e3113-210">Common abbreviations, such as `Async` for “Asynchronous”, are tolerated.</span></span> <span data-ttu-id="e3113-211">Questa indicazione viene ignorata in alcuni casi per la programmazione funzionale; ad esempio, `List.iter` Usa un'abbreviazione per "eseguire l'iterazione".</span><span class="sxs-lookup"><span data-stu-id="e3113-211">This guideline is sometimes ignored for functional programming; for example, `List.iter` uses an abbreviation for “iterate”.</span></span> <span data-ttu-id="e3113-212">Per questo motivo, uso di abbreviazioni tende a essere tollerati da un livello superiore in F #-a-programmazione in F #, ma comunque generalmente devono essere evitati in Progettazione del componente pubblico.</span><span class="sxs-lookup"><span data-stu-id="e3113-212">For this reason, using abbreviations tends to be tolerated to a greater degree in F#-to-F# programming, but should still generally be avoided in public component design.</span></span>

#### <a name="avoid-casing-name-collisions"></a><span data-ttu-id="e3113-213">Evitare conflitti di nomi di maiuscole e minuscole</span><span class="sxs-lookup"><span data-stu-id="e3113-213">Avoid casing name collisions</span></span>

<span data-ttu-id="e3113-214">Linee guida di .NET si supponga che maiuscole e minuscole da solo non può essere utilizzata per distinguere i conflitti di nomi, poiché alcune lingue di client (ad esempio, Visual Basic) sono tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="e3113-214">The .NET guidelines say that casing alone cannot be used to disambiguate name collisions, since some client languages (for example, Visual Basic) are case-insensitive.</span></span>

#### <a name="use-acronyms-where-appropriate"></a><span data-ttu-id="e3113-215">Usare gli acronimi dove appropriato</span><span class="sxs-lookup"><span data-stu-id="e3113-215">Use acronyms where appropriate</span></span>

<span data-ttu-id="e3113-216">Gli acronimi quali XML non sono abbreviazioni e vengono ampiamente usati nelle librerie .NET in formato minuscolo (Xml).</span><span class="sxs-lookup"><span data-stu-id="e3113-216">Acronyms such as XML are not abbreviations and are widely used in .NET libraries in uncapitalized form (Xml).</span></span> <span data-ttu-id="e3113-217">Devono essere usati solo acronimi ben conosciuti e ampiamente riconosciuti.</span><span class="sxs-lookup"><span data-stu-id="e3113-217">Only well-known, widely recognized acronyms should be used.</span></span>

#### <a name="use-pascalcase-for-generic-parameter-names"></a><span data-ttu-id="e3113-218">Usano la notazione Pascal per i nomi di parametro generico</span><span class="sxs-lookup"><span data-stu-id="e3113-218">Use PascalCase for generic parameter names</span></span>

<span data-ttu-id="e3113-219">Per i nomi dei parametri generici nelle API pubbliche, tra cui per F # usano la notazione Pascal-rivolta librerie.</span><span class="sxs-lookup"><span data-stu-id="e3113-219">Do use PascalCase for generic parameter names in public APIs, including for F#-facing libraries.</span></span> <span data-ttu-id="e3113-220">In particolare, usare nomi quale `T`, `U`, `T1`, `T2` arbitrari parametri generici e se nomi specifici siano significativi, quindi per F #-librerie affiancate utilizzano nomi quale `Key`, `Value`, `Arg`(ma non, ad esempio, `TKey`).</span><span class="sxs-lookup"><span data-stu-id="e3113-220">In particular, use names like `T`, `U`, `T1`, `T2` for arbitrary generic parameters, and when specific names make sense, then for F#-facing libraries use names like `Key`, `Value`, `Arg` (but not for example, `TKey`).</span></span>

#### <a name="use-either-pascalcase-or-camelcase-for-public-functions-and-values-in-f-modules"></a><span data-ttu-id="e3113-221">Usare PascalCase o camelCase per le funzioni pubbliche e i valori nei moduli di F #</span><span class="sxs-lookup"><span data-stu-id="e3113-221">Use either PascalCase or camelCase for public functions and values in F# modules</span></span>

<span data-ttu-id="e3113-222">camelCase viene usato per le funzioni pubbliche che sono progettate per essere usato non qualificato (ad esempio, `invalidArg`) e per le "funzioni di raccolta standard" (ad esempio, List. Map).</span><span class="sxs-lookup"><span data-stu-id="e3113-222">camelCase is used for public functions that are designed to be used unqualified (for example, `invalidArg`), and for the “standard collection functions” (for example, List.map).</span></span> <span data-ttu-id="e3113-223">In entrambi i casi, i nomi delle funzioni funzionano in modo simile le parole chiave nel linguaggio.</span><span class="sxs-lookup"><span data-stu-id="e3113-223">In both these cases, the function names act much like keywords in the language.</span></span>

### <a name="object-type-and-module-design"></a><span data-ttu-id="e3113-224">Oggetto, tipo e modulo di progettazione</span><span class="sxs-lookup"><span data-stu-id="e3113-224">Object, Type, and Module design</span></span>

#### <a name="use-namespaces-or-modules-to-contain-your-types-and-modules"></a><span data-ttu-id="e3113-225">Usare gli spazi dei nomi o moduli per includere i tipi e i moduli</span><span class="sxs-lookup"><span data-stu-id="e3113-225">Use namespaces or modules to contain your types and modules</span></span>

<span data-ttu-id="e3113-226">Ogni file F # in un componente deve iniziare con una dichiarazione dello spazio dei nomi o una dichiarazione di modulo.</span><span class="sxs-lookup"><span data-stu-id="e3113-226">Each F# file in a component should begin with either a namespace declaration or a module declaration.</span></span>

```fsharp
namespace Fabrikam.BasicOperationsAndTypes

type ObjectType1() =
    ...

type ObjectType2() =
     ...

module CommonOperations =
    ...
```

<span data-ttu-id="e3113-227">oppure</span><span class="sxs-lookup"><span data-stu-id="e3113-227">or</span></span>

```fsharp
module Fabrikam.BasicOperationsAndTypes

type ObjectType1() =
    ...

type ObjectType2() =
    ...

module CommonOperations =
    ...
```

<span data-ttu-id="e3113-228">Come indicato di seguito sono riportate le differenze tra l'uso di moduli e spazi dei nomi per organizzare il codice di primo livello:</span><span class="sxs-lookup"><span data-stu-id="e3113-228">The differences between using modules and namespaces to organize code at the top level are as follows:</span></span>

* <span data-ttu-id="e3113-229">Gli spazi dei nomi possono estendersi su più file</span><span class="sxs-lookup"><span data-stu-id="e3113-229">Namespaces can span multiple files</span></span>
* <span data-ttu-id="e3113-230">Gli spazi dei nomi non può contenere funzioni F #, a meno che non sono all'interno di un modulo interno</span><span class="sxs-lookup"><span data-stu-id="e3113-230">Namespaces cannot contain F# functions unless they are within an inner module</span></span>
* <span data-ttu-id="e3113-231">Il codice di qualsiasi modulo specificato deve essere contenuto in un singolo file</span><span class="sxs-lookup"><span data-stu-id="e3113-231">The code for any given module must be contained within a single file</span></span>
* <span data-ttu-id="e3113-232">Moduli di primo livello possono contenere funzioni F # senza la necessità di un modulo interno</span><span class="sxs-lookup"><span data-stu-id="e3113-232">Top-level modules can contain F# functions without the need for an inner module</span></span>

<span data-ttu-id="e3113-233">La scelta tra uno spazio dei nomi di primo livello o un modulo riguarda la forma compilata del codice e pertanto verrà la visualizzazione di altri linguaggi .NET devono API eventualmente essere usato di fuori del codice F #.</span><span class="sxs-lookup"><span data-stu-id="e3113-233">The choice between a top-level namespace or module affects the compiled form of the code, and thus will affect the view from other .NET languages should your API eventually be consumed outside of F# code.</span></span>

#### <a name="use-methods-and-properties-for-operations-intrinsic-to-object-types"></a><span data-ttu-id="e3113-234">Usare i metodi e proprietà per le operazioni intrinseche per i tipi di oggetto</span><span class="sxs-lookup"><span data-stu-id="e3113-234">Use methods and properties for operations intrinsic to object types</span></span>

<span data-ttu-id="e3113-235">Quando si lavora con gli oggetti, è consigliabile assicurarsi che possa essere utilizzata funzionalità viene implementata come metodi e proprietà per quel tipo.</span><span class="sxs-lookup"><span data-stu-id="e3113-235">When working with objects, it is best to ensure that consumable functionality is implemented as methods and properties on that type.</span></span>

```fsharp
type HardwareDevice() =

    member this.ID = ...

    member this.SupportedProtocols = ...

type HashTable<'Key,'Value>(comparer: IEqualityComparer<'Key>) =

    member this.Add(key, value) = ...

    member this.ContainsKey(key) = ...

    member this.ContainsValue(value) = ...
```

<span data-ttu-id="e3113-236">La maggior parte delle funzionalità per un determinato membro non debba necessariamente essere implementata in tale membro, ma deve essere la parte di tale funzionalità può essere utilizzata.</span><span class="sxs-lookup"><span data-stu-id="e3113-236">The bulk of functionality for a given member need not necessarily be implemented in that member, but the consumable piece of that functionality should be.</span></span>

#### <a name="use-classes-to-encapsulate-mutable-state"></a><span data-ttu-id="e3113-237">Usare le classi per incapsulare lo stato modificabile</span><span class="sxs-lookup"><span data-stu-id="e3113-237">Use classes to encapsulate mutable state</span></span>

<span data-ttu-id="e3113-238">In F #, questo deve solo essere eseguita in cui che lo stato non è già incapsulato da un altro costrutto di linguaggio, ad esempio una chiusura, l'espressione di sequenza o calcolo asincrono.</span><span class="sxs-lookup"><span data-stu-id="e3113-238">In F#, this only needs to be done where that state is not already encapsulated by another language construct, such as a closure, sequence expression, or asynchronous computation.</span></span>

```fsharp
type Counter() =
    // let-bound values are private in classes.
    let mutable count = 0

    member this.Next() =
        count <- count + 1
        count
```

#### <a name="use-interfaces-to-group-related-operations"></a><span data-ttu-id="e3113-239">Usare le interfacce per raggruppare le operazioni correlate</span><span class="sxs-lookup"><span data-stu-id="e3113-239">Use interfaces to group related operations</span></span>

<span data-ttu-id="e3113-240">Usare i tipi di interfaccia per rappresentare una serie di operazioni.</span><span class="sxs-lookup"><span data-stu-id="e3113-240">Use interface types to represent a set of operations.</span></span> <span data-ttu-id="e3113-241">Ciò è preferibile ad altre opzioni, ad esempio tuple di funzioni o i record delle funzioni.</span><span class="sxs-lookup"><span data-stu-id="e3113-241">This is preferred to other options, such as tuples of functions or records of functions.</span></span>

```fsharp
type Serializer =
    abstract Serialize<'T> : preserveRefEq: bool -> value: 'T -> string
    abstract Deserialize<'T> : preserveRefEq: bool -> pickle: string -> 'T
```

<span data-ttu-id="e3113-242">In alternativa a:</span><span class="sxs-lookup"><span data-stu-id="e3113-242">In preference to:</span></span>

```fsharp
type Serializer<'T> = {
    Serialize : bool -> 'T -> string
    Deserialize : bool -> string -> 'T
}
```

<span data-ttu-id="e3113-243">Le interfacce sono concetti di prima classe in .NET, che è possibile usare per ottenere la cosa Funtori normalmente verrebbero visualizzate.</span><span class="sxs-lookup"><span data-stu-id="e3113-243">Interfaces are first-class concepts in .NET, which you can use to achieve what Functors would normally give you.</span></span> <span data-ttu-id="e3113-244">Inoltre, possono essere utilizzati per codificare tipi esistenziali nel programma, che non può essere i record delle funzioni.</span><span class="sxs-lookup"><span data-stu-id="e3113-244">Additionally, they can be used to encode existential types into your program, which records of functions cannot.</span></span>

#### <a name="use-a-module-to-group-functions-which-act-on-collections"></a><span data-ttu-id="e3113-245">Usare un modulo per le funzioni di gruppo che agiscono sulle raccolte</span><span class="sxs-lookup"><span data-stu-id="e3113-245">Use a module to group functions which act on collections</span></span>

<span data-ttu-id="e3113-246">Quando si definisce un tipo di raccolta, si consiglia di fornire un set standard di operazioni, ad esempio `CollectionType.map` e `CollectionType.iter`) per i nuovi tipi di raccolta.</span><span class="sxs-lookup"><span data-stu-id="e3113-246">When you define a collection type, consider providing a standard set of operations like `CollectionType.map` and `CollectionType.iter`) for new collection types.</span></span>

```fsharp
module CollectionType =
    let map f c =
        ...
    let iter f c =
        ...
```

<span data-ttu-id="e3113-247">Se si include un modulo di questo tipo, seguire le convenzioni di denominazione standard per le funzioni disponibili in FSharp. Core.</span><span class="sxs-lookup"><span data-stu-id="e3113-247">If you include such a module, follow the standard naming conventions for functions found in FSharp.Core.</span></span>

#### <a name="use-a-module-to-group-functions-for-common-canonical-functions-especially-in-math-and-dsl-libraries"></a><span data-ttu-id="e3113-248">Usare un modulo per le funzioni di gruppo per le funzioni comuni, canoniche, soprattutto in matematica e le librerie DSL</span><span class="sxs-lookup"><span data-stu-id="e3113-248">Use a module to group functions for common, canonical functions, especially in math and DSL libraries</span></span>

<span data-ttu-id="e3113-249">Ad esempio, `Microsoft.FSharp.Core.Operators` aperti automaticamente: raccolta di funzioni di primo livello (ad esempio `abs` e `sin`) fornito da FSharp.</span><span class="sxs-lookup"><span data-stu-id="e3113-249">For example, `Microsoft.FSharp.Core.Operators` is an automatically opened collection of top-level functions (like `abs` and `sin`) provided by FSharp.Core.dll.</span></span>

<span data-ttu-id="e3113-250">Analogamente, una raccolta delle statistiche potrebbe includere un modulo con le funzioni `erf` e `erfc`, in cui questo modulo è progettato per essere automaticamente o in modo esplicito aperto.</span><span class="sxs-lookup"><span data-stu-id="e3113-250">Likewise, a statistics library might include a module with functions `erf` and `erfc`, where this module is designed to be explicitly or automatically opened.</span></span>

#### <a name="consider-using-requirequalifiedaccess-and-carefully-apply-autoopen-attributes"></a><span data-ttu-id="e3113-251">È consigliabile usare RequireQualifiedAccess e attentamente applicare attributi AutoOpen</span><span class="sxs-lookup"><span data-stu-id="e3113-251">Consider using RequireQualifiedAccess and carefully apply AutoOpen attributes</span></span>

<span data-ttu-id="e3113-252">Aggiunta di `[<RequireQualifiedAccess>]` attributo a un modulo indica che il modulo non può essere aperta e che i riferimenti agli elementi del modulo richiedono esplicita completo di accesso.</span><span class="sxs-lookup"><span data-stu-id="e3113-252">Adding the `[<RequireQualifiedAccess>]` attribute to a module indicates that the module may not be opened and that references to the elements of the module require explicit qualified access.</span></span> <span data-ttu-id="e3113-253">Ad esempio, il `Microsoft.FSharp.Collections.List` modulo dispone di questo attributo.</span><span class="sxs-lookup"><span data-stu-id="e3113-253">For example, the `Microsoft.FSharp.Collections.List` module has this attribute.</span></span>

<span data-ttu-id="e3113-254">Ciò è utile quando le funzioni e i valori nel modulo hanno nomi che possono entrare in conflitto con i nomi di altri moduli.</span><span class="sxs-lookup"><span data-stu-id="e3113-254">This is useful when functions and values in the module have names that are likely to conflict with names in other modules.</span></span> <span data-ttu-id="e3113-255">Richiedere l'accesso completo può aumentare notevolmente la manutenibilità a lungo termine e capacità evolutiva di una libreria.</span><span class="sxs-lookup"><span data-stu-id="e3113-255">Requiring qualified access can greatly increase the long-term maintainability and evolvability of a library.</span></span>

<span data-ttu-id="e3113-256">Aggiunta di `[<AutoOpen>]` attributo su un modulo, verrà aperto il modulo quando viene aperto lo spazio dei nomi che lo contiene.</span><span class="sxs-lookup"><span data-stu-id="e3113-256">Adding the `[<AutoOpen>]` attribute to a module means the module will be opened when the containing namespace is opened.</span></span> <span data-ttu-id="e3113-257">Il `[<AutoOpen>]` attributo può anche essere applicato a un assembly per indicare un modulo che viene aperto automaticamente quando viene fatto riferimento all'assembly.</span><span class="sxs-lookup"><span data-stu-id="e3113-257">The `[<AutoOpen>]` attribute may also be applied to an assembly to indicate a module that is automatically opened when the assembly is referenced.</span></span>

<span data-ttu-id="e3113-258">Ad esempio, una raccolta di statistiche **MathsHeaven.Statistics** potrebbe contenere una `module MathsHeaven.Statistics.Operators` contenenti funzioni `erf` e `erfc`.</span><span class="sxs-lookup"><span data-stu-id="e3113-258">For example, a statistics library **MathsHeaven.Statistics** might contain a `module MathsHeaven.Statistics.Operators` containing functions `erf` and `erfc`.</span></span> <span data-ttu-id="e3113-259">È ragionevole contrassegnare questo modulo come `[<AutoOpen>]`.</span><span class="sxs-lookup"><span data-stu-id="e3113-259">It is reasonable to mark this module as `[<AutoOpen>]`.</span></span> <span data-ttu-id="e3113-260">Ciò significa `open MathsHeaven.Statistics` verrà anche aprire questo modulo e visualizzare i nomi `erf` e `erfc` nell'ambito.</span><span class="sxs-lookup"><span data-stu-id="e3113-260">This means `open MathsHeaven.Statistics` will also open this module and bring the names `erf` and `erfc` into scope.</span></span> <span data-ttu-id="e3113-261">Usa un'altra buona `[<AutoOpen>]` è per i moduli contenenti i metodi di estensione.</span><span class="sxs-lookup"><span data-stu-id="e3113-261">Another good use of `[<AutoOpen>]` is for modules containing extension methods.</span></span>

<span data-ttu-id="e3113-262">Utilizzo eccessivo di `[<AutoOpen>]` lead inquinato gli spazi dei nomi e l'attributo deve essere utilizzata con cautela.</span><span class="sxs-lookup"><span data-stu-id="e3113-262">Overuse of `[<AutoOpen>]` leads to polluted namespaces, and the attribute should be used with care.</span></span> <span data-ttu-id="e3113-263">Per le librerie specifiche in domini specifici, uso attento di `[<AutoOpen>]` può portare a una migliore utilizzabilità.</span><span class="sxs-lookup"><span data-stu-id="e3113-263">For specific libraries in specific domains, judicious use of `[<AutoOpen>]` can lead to better usability.</span></span>

#### <a name="consider-defining-operator-members-on-classes-where-using-well-known-operators-is-appropriate"></a><span data-ttu-id="e3113-264">Si consiglia di definire i membri di operatore sulle classi in cui è appropriato usare operatori noti</span><span class="sxs-lookup"><span data-stu-id="e3113-264">Consider defining operator members on classes where using well-known operators is appropriate</span></span>

<span data-ttu-id="e3113-265">In alcuni casi classi vengono utilizzate per la modellazione matematici costrutti come vettori.</span><span class="sxs-lookup"><span data-stu-id="e3113-265">Sometimes classes are used to model mathematical constructs such as Vectors.</span></span> <span data-ttu-id="e3113-266">Quando il dominio in fase di modellazione include operatori noti, vengono definiti come membri intrinseci per la classe è utile.</span><span class="sxs-lookup"><span data-stu-id="e3113-266">When the domain being modeled has well-known operators, defining them as members intrinsic to the class is helpful.</span></span>

```fsharp
type Vector(x:float) =

    member v.X = x

    static member (*) (vector:Vector, scalar:float) = Vector(vector.X * scalar)

    static member (+) (vector1:Vector, vector2:Vector) = Vector(vector1.X + vector2.X)

let v = Vector(5.0)

let u = v * 10.0
```

<span data-ttu-id="e3113-267">Questo materiale sussidiario corrisponde alle linee guida generali di .NET per questi tipi.</span><span class="sxs-lookup"><span data-stu-id="e3113-267">This guidance corresponds to general .NET guidance for these types.</span></span> <span data-ttu-id="e3113-268">Tuttavia, può essere inoltre importante in F # di codifica poiché in questo modo questi tipi da utilizzare in combinazione con le funzioni F # e i metodi con vincoli di membro, ad esempio List. sumBy.</span><span class="sxs-lookup"><span data-stu-id="e3113-268">However, it can be additionally important in F# coding as this allows these types to be used in conjunction with F# functions and methods with member constraints, such as List.sumBy.</span></span>

#### <a name="consider-using-compiledname-to-provide-a-net-friendly-name-for-other-net-language-consumers"></a><span data-ttu-id="e3113-269">È consigliabile usare CompiledName per fornire una. Nome descrittivo del NET per altri consumer di linguaggio .NET</span><span class="sxs-lookup"><span data-stu-id="e3113-269">Consider using CompiledName to provide a .NET-friendly name for other .NET language consumers</span></span>

<span data-ttu-id="e3113-270">In alcuni casi si potrebbe voler assegnare un nome in uno stile per i consumer di F # (ad esempio un membro statico in caratteri minuscoli in modo che venga visualizzato come se fosse una funzione associata al modulo), ma hanno uno stile diverso per il nome quando viene compilato in un assembly.</span><span class="sxs-lookup"><span data-stu-id="e3113-270">Sometimes you may wish to name something in one style for F# consumers (such as a static member in lower case so that it appears as if it were a module-bound function), but have a different style for the name when it is compiled into an assembly.</span></span> <span data-ttu-id="e3113-271">È possibile usare il `[<CompiledName>]` attributo per fornire uno stile diverso per F # non codice che utilizza l'assembly.</span><span class="sxs-lookup"><span data-stu-id="e3113-271">You can use the `[<CompiledName>]` attribute to provide a different style for non F# code consuming the assembly.</span></span>

```fsharp
type Vector(x:float, y:float) =

    member v.X = x
    member v.Y = y

    [<CompiledName("Create")>]
    static member create x y = Vector (x, y)

let v = Vector.create 5.0 3.0
```

<span data-ttu-id="e3113-272">Usando `[<CompiledName>]`, è possibile usare le convenzioni di denominazione .NET per F # non consumer dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="e3113-272">By using `[<CompiledName>]`, you can use .NET naming conventions for non F# consumers of the assembly.</span></span>

#### <a name="use-method-overloading-for-member-functions-if-doing-so-provides-a-simpler-api"></a><span data-ttu-id="e3113-273">Usare metodi (overload) per le funzioni membro, se in questo modo viene fornita un'API più semplice</span><span class="sxs-lookup"><span data-stu-id="e3113-273">Use method overloading for member functions, if doing so provides a simpler API</span></span>

<span data-ttu-id="e3113-274">L'overload di metodo è un potente strumento per la semplificazione di un'API che potrebbe essere necessario eseguire una funzionalità simile, ma con diverse opzioni o argomenti.</span><span class="sxs-lookup"><span data-stu-id="e3113-274">Method overloading is a powerful tool for simplifying an API that may need to perform similar functionality, but with different options or arguments.</span></span>

```fsharp
type Logger() =

    member this.Log(message) =
        ...
    member this.Log(message, retryPolicy) =
        ...
```

<span data-ttu-id="e3113-275">In F #, è più comune per eseguire l'overload di un numero di argomenti anziché i tipi degli argomenti.</span><span class="sxs-lookup"><span data-stu-id="e3113-275">In F#, it is more common to overload on number of arguments rather than types of arguments.</span></span>

#### <a name="hide-the-representations-of-record-and-union-types-if-the-design-of-these-types-is-likely-to-evolve"></a><span data-ttu-id="e3113-276">Se la progettazione di questi tipi è probabile che si evolvono, nascondere le rappresentazioni dei record e i tipi di unione</span><span class="sxs-lookup"><span data-stu-id="e3113-276">Hide the representations of record and union types if the design of these types is likely to evolve</span></span>

<span data-ttu-id="e3113-277">Evitare di rivelare concrete rappresentazioni degli oggetti.</span><span class="sxs-lookup"><span data-stu-id="e3113-277">Avoid revealing concrete representations of objects.</span></span> <span data-ttu-id="e3113-278">Ad esempio, la rappresentazione di concreto <xref:System.DateTime> valori non è stato rivelato dall'API esterno, pubblico di progettazione di librerie di .NET.</span><span class="sxs-lookup"><span data-stu-id="e3113-278">For example, the concrete representation of <xref:System.DateTime> values is not revealed by the external, public API of the .NET library design.</span></span> <span data-ttu-id="e3113-279">In fase di esecuzione, Common Language Runtime sa l'implementazione di commit che verrà usato in tutta l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="e3113-279">At run time, the Common Language Runtime knows the committed implementation that will be used throughout execution.</span></span> <span data-ttu-id="e3113-280">Tuttavia, codice compilato non stesso prelevare le dipendenze alla relativa rappresentazione in concreta.</span><span class="sxs-lookup"><span data-stu-id="e3113-280">However, compiled code doesn't itself pick up dependencies on the concrete representation.</span></span>

#### <a name="avoid-the-use-of-implementation-inheritance-for-extensibility"></a><span data-ttu-id="e3113-281">Evitare l'utilizzo dell'ereditarietà dell'implementazione per l'estensibilità</span><span class="sxs-lookup"><span data-stu-id="e3113-281">Avoid the use of implementation inheritance for extensibility</span></span>

<span data-ttu-id="e3113-282">In F #, viene usato raramente ereditarietà dell'implementazione.</span><span class="sxs-lookup"><span data-stu-id="e3113-282">In F#, implementation inheritance is rarely used.</span></span> <span data-ttu-id="e3113-283">Inoltre, le gerarchie di ereditarietà sono spesso complessi e difficili da modificare quando arrivano nuovi requisiti.</span><span class="sxs-lookup"><span data-stu-id="e3113-283">Furthermore, inheritance hierarchies are often complex and difficult to change when new requirements arrive.</span></span> <span data-ttu-id="e3113-284">Implementazione dell'ereditarietà è ancora presente in F # per la compatibilità e rari casi in cui è la soluzione migliore per risolvere un problema, ma tecniche alternative devono essere ricercate nei programmi F # quando si progetta per il polimorfismo, ad esempio di implementazione dell'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="e3113-284">Inheritance implementation still exists in F# for compatibility and rare cases where it is the best solution to a problem, but alternative techniques should be sought in your F# programs when designing for polymorphism, such as interface implementation.</span></span>

### <a name="function-and-member-signatures"></a><span data-ttu-id="e3113-285">Firme di funzione e membro</span><span class="sxs-lookup"><span data-stu-id="e3113-285">Function and member signatures</span></span>

#### <a name="use-tuples-for-return-values-when-returning-a-small-number-of-multiple-unrelated-values"></a><span data-ttu-id="e3113-286">Usare le tuple per i valori restituiti quando viene restituito un numero ridotto di più valori non correlati</span><span class="sxs-lookup"><span data-stu-id="e3113-286">Use tuples for return values when returning a small number of multiple unrelated values</span></span>

<span data-ttu-id="e3113-287">Ecco un buon esempio di uso di una tupla in un tipo restituito:</span><span class="sxs-lookup"><span data-stu-id="e3113-287">Here is a good example of using a tuple in a return type:</span></span>

```fsharp
val divrem : BigInteger -> BigInteger -> BigInteger * BigInteger
```

<span data-ttu-id="e3113-288">Per restituire i tipi che contengono molti componenti, o se i componenti sono correlati a una singola entità identificabili, valutare l'uso di un tipo denominato anziché una tupla.</span><span class="sxs-lookup"><span data-stu-id="e3113-288">For return types containing many components, or where the components are related to a single identifiable entity, consider using a named type instead of a tuple.</span></span>

#### <a name="use-asynct-for-async-programming-at-f-api-boundaries"></a><span data-ttu-id="e3113-289">Usare `Async<T>` per la programmazione asincrona in base ai limiti API F #</span><span class="sxs-lookup"><span data-stu-id="e3113-289">Use `Async<T>` for async programming at F# API boundaries</span></span>

<span data-ttu-id="e3113-290">Se vi è un'operazione sincrona corrispondente denominata `Operation` che restituisce un `T`, quindi l'operazione asincrona deve essere denominato `AsyncOperation` se il valore restituito `Async<T>` oppure `OperationAsync` se restituisce `Task<T>`.</span><span class="sxs-lookup"><span data-stu-id="e3113-290">If there is a corresponding synchronous operation named `Operation` that returns a `T`, then the async operation should be named `AsyncOperation` if it returns `Async<T>` or `OperationAsync` if it returns `Task<T>`.</span></span> <span data-ttu-id="e3113-291">Per i tipi .NET comunemente utilizzati che espongono i metodi Begin/End, è consigliabile usare `Async.FromBeginEnd` scrivere metodi di estensione come un'interfaccia per fornire il F # async modello di programmazione per le API .NET.</span><span class="sxs-lookup"><span data-stu-id="e3113-291">For commonly used .NET types that expose Begin/End methods, consider using `Async.FromBeginEnd` to write extension methods as a façade to provide the F# async programming model to those .NET APIs.</span></span>

```fsharp
type SomeType =
    member this.Compute(x:int) : int =
        ...
    member this.AsyncCompute(x:int) : Async<int> =
        ...

type System.ServiceModel.Channels.IInputChannel with
    member this.AsyncReceive() =
        ...
```

### <a name="exceptions"></a><span data-ttu-id="e3113-292">Eccezioni</span><span class="sxs-lookup"><span data-stu-id="e3113-292">Exceptions</span></span>

<span data-ttu-id="e3113-293">Visualizzare [gestione degli errori](conventions.md#error-management) per apprendere l'utilizzo appropriato di eccezioni, i risultati e le opzioni.</span><span class="sxs-lookup"><span data-stu-id="e3113-293">See [Error Management](conventions.md#error-management) to learn about appropriate use of exceptions, results, and options.</span></span>

### <a name="extension-members"></a><span data-ttu-id="e3113-294">Membri di estensione</span><span class="sxs-lookup"><span data-stu-id="e3113-294">Extension Members</span></span>

#### <a name="carefully-apply-f-extension-members-in-f-to-f-components"></a><span data-ttu-id="e3113-295">Applicare con attenzione i membri di estensione F # in F #-a-F # componenti</span><span class="sxs-lookup"><span data-stu-id="e3113-295">Carefully apply F# extension members in F#-to-F# components</span></span>

<span data-ttu-id="e3113-296">Membri di estensione F # dovrebbero in genere essere utilizzati solo per le operazioni che si trovano nella chiusura di operazioni intrinseche associate a un tipo nella maggior parte delle relative modalità d'uso.</span><span class="sxs-lookup"><span data-stu-id="e3113-296">F# extension members should generally only be used for operations that are in the closure of intrinsic operations associated with a type in the majority of its modes of use.</span></span> <span data-ttu-id="e3113-297">Un utilizzo comune consiste nel fornire API che sono più a F # idiomatiche per diversi tipi di .NET:</span><span class="sxs-lookup"><span data-stu-id="e3113-297">One common use is to provide APIs that are more idiomatic to F# for various .NET types:</span></span>

```fsharp
type System.ServiceModel.Channels.IInputChannel with
    member this.AsyncReceive() =
        Async.FromBeginEnd(this.BeginReceive, this.EndReceive)

type System.Collections.Generic.IDictionary<'Key,'Value> with
    member this.TryGet key =
        let ok, v = this.TryGetValue key
        if ok then Some v else None
```

### <a name="union-types"></a><span data-ttu-id="e3113-298">Tipi di unione</span><span class="sxs-lookup"><span data-stu-id="e3113-298">Union Types</span></span>

#### <a name="use-discriminated-unions-instead-of-class-hierarchies-for-tree-structured-data"></a><span data-ttu-id="e3113-299">Usare le unioni discriminate invece di gerarchie di classi per i dati di struttura ad albero</span><span class="sxs-lookup"><span data-stu-id="e3113-299">Use discriminated unions instead of class hierarchies for tree-structured data</span></span>

<span data-ttu-id="e3113-300">Strutture ad albero sono definiti in modo ricorsivo.</span><span class="sxs-lookup"><span data-stu-id="e3113-300">Tree-like structures are recursively defined.</span></span> <span data-ttu-id="e3113-301">È difficile con ereditarietà, ma con unioni discriminate elegante.</span><span class="sxs-lookup"><span data-stu-id="e3113-301">This is awkward with inheritance, but elegant with Discriminated Unions.</span></span>

```fsharp
type BST<'T> =
    | Empty
    | Node of 'T * BST<'T> * BST<'T>
```

<span data-ttu-id="e3113-302">Che rappresenta i dati di struttura ad albero con unioni discriminate consente anche di trarre vantaggio da exhaustiveness nei criteri di ricerca.</span><span class="sxs-lookup"><span data-stu-id="e3113-302">Representing tree-like data with Discriminated Unions also allows you to benefit from exhaustiveness in pattern matching.</span></span>

#### <a name="use-requirequalifiedaccess-on-union-types-whose-case-names-are-not-sufficiently-unique"></a><span data-ttu-id="e3113-303">Usare `[<RequireQualifiedAccess>]` su tipi di unione i cui nomi case non sono sufficientemente univoci</span><span class="sxs-lookup"><span data-stu-id="e3113-303">Use `[<RequireQualifiedAccess>]` on union types whose case names are not sufficiently unique</span></span>

<span data-ttu-id="e3113-304">Si potrebbe trovare in un dominio in cui lo stesso nome è il nome migliore per scopi diversi, ad esempio case di unione discriminata.</span><span class="sxs-lookup"><span data-stu-id="e3113-304">You may find yourself in a domain where the same name is the best name for different things, such as Discriminated Union cases.</span></span> <span data-ttu-id="e3113-305">È possibile usare `[<RequireQualifiedAccess>]` per risolvere l'ambiguità di nomi dei casi per evitare di attivare confusi errori a causa di shadowing dipendenti per l'ordinamento delle `open` istruzioni</span><span class="sxs-lookup"><span data-stu-id="e3113-305">You can use `[<RequireQualifiedAccess>]` to disambiguate case names in order to avoid triggering confusing errors due to shadowing dependent on the ordering of `open` statements</span></span>

#### <a name="hide-the-representations-of-discriminated-unions-for-binary-compatible-apis-if-the-design-of-these-types-is-likely-to-evolve"></a><span data-ttu-id="e3113-306">Consente di nascondere le rappresentazioni delle unioni discriminate di API compatibili binarie se la progettazione di questi tipi è probabile che si evolvono</span><span class="sxs-lookup"><span data-stu-id="e3113-306">Hide the representations of discriminated unions for binary compatible APIs if the design of these types is likely to evolve</span></span>

<span data-ttu-id="e3113-307">Le unioni tipi si basano su F # corrispondenza form per un modello di programmazione conciso.</span><span class="sxs-lookup"><span data-stu-id="e3113-307">Unions types rely on F# pattern-matching forms for a succinct programming model.</span></span> <span data-ttu-id="e3113-308">Come accennato in precedenza, è consigliabile evitare di rivelare le rappresentazioni di dati concreti se la progettazione di questi tipi è probabile che si evolvono.</span><span class="sxs-lookup"><span data-stu-id="e3113-308">As mentioned previously, you should avoid revealing concrete data representations if the design of these types is likely to evolve.</span></span>

<span data-ttu-id="e3113-309">Ad esempio, può essere nascosta la rappresentazione di un'unione discriminata con una dichiarazione privata o interna, oppure usando un file della firma.</span><span class="sxs-lookup"><span data-stu-id="e3113-309">For example, the representation of a discriminated union can be hidden using a private or internal declaration, or by using a signature file.</span></span>

```fsharp
type Union =
    private
    | CaseA of int
    | CaseB of string
```

<span data-ttu-id="e3113-310">Se si rivelano le unioni discriminate indiscriminatamente, può risultare difficile da versione libreria senza causare interruzioni nel codice utente.</span><span class="sxs-lookup"><span data-stu-id="e3113-310">If you reveal discriminated unions indiscriminately, you may find it hard to version your library without breaking user code.</span></span> <span data-ttu-id="e3113-311">Si consiglia di rivelare uno o più criteri attivi per consentire la corrispondenza dei valori del tipo in uso.</span><span class="sxs-lookup"><span data-stu-id="e3113-311">Instead, consider revealing one or more active patterns to permit pattern matching over values of your type.</span></span>

<span data-ttu-id="e3113-312">Criteri attivi forniscono un modo alternativo per fornire i consumer di F # con criteri di ricerca si evita di esporre direttamente i tipi di unione F #.</span><span class="sxs-lookup"><span data-stu-id="e3113-312">Active patterns provide an alternate way to provide F# consumers with pattern matching while avoiding exposing F# Union Types directly.</span></span>

### <a name="inline-functions-and-member-constraints"></a><span data-ttu-id="e3113-313">Le funzioni inline e i vincoli di membro</span><span class="sxs-lookup"><span data-stu-id="e3113-313">Inline Functions and Member Constraints</span></span>

#### <a name="define-generic-numeric-algorithms-using-inline-functions-with-implied-member-constraints-and-statically-resolved-generic-types"></a><span data-ttu-id="e3113-314">Definire generici algoritmi numerici utilizzando le funzioni inline con vincoli membro implicito e risolti in modo statico tipi generici</span><span class="sxs-lookup"><span data-stu-id="e3113-314">Define generic numeric algorithms using inline functions with implied member constraints and statically resolved generic types</span></span>

<span data-ttu-id="e3113-315">I vincoli di membro aritmetico e vincoli del confronto F # sono uno standard per la programmazione in F #.</span><span class="sxs-lookup"><span data-stu-id="e3113-315">Arithmetic member constraints and F# comparison constraints are a standard for F# programming.</span></span> <span data-ttu-id="e3113-316">Si consideri il codice di esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="e3113-316">For example, consider the following code:</span></span>

```fsharp
let inline highestCommonFactor a b =
    let rec loop a b =
        if a = LanguagePrimitives.GenericZero<_> then b
        elif a < b then loop a (b - a)
        else loop (a - b) b
    loop a b
```

<span data-ttu-id="e3113-317">Il tipo di questa funzione è come segue:</span><span class="sxs-lookup"><span data-stu-id="e3113-317">The type of this function is as follows:</span></span>

```fsharp
val inline highestCommonFactor : ^T -> ^T -> ^T
                when ^T : (static member Zero : ^T)
                and ^T : (static member ( - ) : ^T * ^T -> ^T)
                and ^T : equality
                and ^T : comparison
```

<span data-ttu-id="e3113-318">Si tratta di una funzione appropriata per un'API pubblica in una libreria matematica.</span><span class="sxs-lookup"><span data-stu-id="e3113-318">This is a suitable function for a public API in a mathematical library.</span></span>

#### <a name="avoid-using-member-constraints-to-simulate-type-classes-and-duck-typing"></a><span data-ttu-id="e3113-319">Evitare l'utilizzo di vincoli relativi ai membri per simulare le classi di tipo e Duck Typing digitando</span><span class="sxs-lookup"><span data-stu-id="e3113-319">Avoid using member constraints to simulate type classes and duck typing</span></span>

<span data-ttu-id="e3113-320">È possibile simulare "siete digitando" usando i vincoli di membro F #.</span><span class="sxs-lookup"><span data-stu-id="e3113-320">It is possible to simulate “duck typing” using F# member constraints.</span></span> <span data-ttu-id="e3113-321">Tuttavia, i membri che rendono utilizzano questa non in generale da usare in F #-a-progetti di libreria F #.</span><span class="sxs-lookup"><span data-stu-id="e3113-321">However, members that make use of this should not in general be used in F#-to-F# library designs.</span></span> <span data-ttu-id="e3113-322">Questo avviene perché le progettazioni di libreria in base ai vincoli impliciti sconosciuti o non standard tendono a causare problemi nel codice utente diventi flessibile e sono associati al modello di un framework specifico.</span><span class="sxs-lookup"><span data-stu-id="e3113-322">This is because library designs based on unfamiliar or non-standard implicit constraints tend to cause user code to become inflexible and tied to one particular framework pattern.</span></span>

<span data-ttu-id="e3113-323">Inoltre, è probabile che un uso massiccio di vincoli relativi ai membri in questo modo può comportare tempi di compilazione molto lunghi.</span><span class="sxs-lookup"><span data-stu-id="e3113-323">Additionally, there is a good chance that heavy use of member constraints in this manner can result in very long compile times.</span></span>

### <a name="operator-definitions"></a><span data-ttu-id="e3113-324">Definizioni dell'operatore</span><span class="sxs-lookup"><span data-stu-id="e3113-324">Operator Definitions</span></span>

#### <a name="avoid-defining-custom-symbolic-operators"></a><span data-ttu-id="e3113-325">Evitare di definire gli operatori simbolici personalizzati</span><span class="sxs-lookup"><span data-stu-id="e3113-325">Avoid defining custom symbolic operators</span></span>

<span data-ttu-id="e3113-326">Gli operatori personalizzati sono essenziali in alcune situazioni e sono estremamente utili notazionale dispositivi all'interno di un corpo di grandi dimensioni del codice di implementazione.</span><span class="sxs-lookup"><span data-stu-id="e3113-326">Custom operators are essential in some situations and are highly useful notational devices within a large body of implementation code.</span></span> <span data-ttu-id="e3113-327">Per i nuovi utenti di una libreria, le funzioni denominate sono spesso più facile da usare.</span><span class="sxs-lookup"><span data-stu-id="e3113-327">For new users of a library, named functions are often easier to use.</span></span> <span data-ttu-id="e3113-328">Inoltre, operatori simbolici personalizzati possono essere difficili al documento e utenti trovarla più difficile per la ricerca della Guida sugli operatori, a causa di limitazioni esistenti nei motori di ricerca e dell'IDE.</span><span class="sxs-lookup"><span data-stu-id="e3113-328">In addition, custom symbolic operators can be hard to document, and users find it more difficult to look up help on operators, due to existing limitations in IDE and search engines.</span></span>

<span data-ttu-id="e3113-329">Di conseguenza, si consiglia di pubblicare la funzionalità come funzioni denominate e i membri e inoltre esporre operatori per questa funzionalità solo se i vantaggi notazionale superano la documentazione e i costi cognitivi di prevedere.</span><span class="sxs-lookup"><span data-stu-id="e3113-329">As a result, it is best to publish your functionality as named functions and members, and additionally expose operators for this functionality only if the notational benefits outweigh the documentation and cognitive cost of having them.</span></span>

### <a name="units-of-measure"></a><span data-ttu-id="e3113-330">Unità di misura</span><span class="sxs-lookup"><span data-stu-id="e3113-330">Units of Measure</span></span>

#### <a name="carefully-use-units-of-measure-for-added-type-safety-in-f-code"></a><span data-ttu-id="e3113-331">Usare con attenzione le unità di misura per motivi di sicurezza di tipo aggiunto nel codice F #</span><span class="sxs-lookup"><span data-stu-id="e3113-331">Carefully use units of measure for added type safety in F# code</span></span>

<span data-ttu-id="e3113-332">Informazioni di tipizzazione aggiuntive per le unità di misura viene cancellate quando viene visualizzato da altri linguaggi .NET.</span><span class="sxs-lookup"><span data-stu-id="e3113-332">Additional typing information for units of measure is erased when viewed by other .NET languages.</span></span> <span data-ttu-id="e3113-333">Tenere presente che la reflection, strumenti e componenti .NET verranno visualizzati i tipi-sans-unità.</span><span class="sxs-lookup"><span data-stu-id="e3113-333">Be aware that .NET components, tools, and reflection will see types-sans-units.</span></span> <span data-ttu-id="e3113-334">Ad esempio, verranno visualizzato c# consumatori `float` anziché `float<kg>`.</span><span class="sxs-lookup"><span data-stu-id="e3113-334">For example, C# consumers will see `float` rather than `float<kg>`.</span></span>

### <a name="type-abbreviations"></a><span data-ttu-id="e3113-335">Abbreviazioni dei tipi</span><span class="sxs-lookup"><span data-stu-id="e3113-335">Type Abbreviations</span></span>

#### <a name="carefully-use-type-abbreviations-to-simplify-f-code"></a><span data-ttu-id="e3113-336">Usare con attenzione le abbreviazioni dei tipi per semplificare il codice F #</span><span class="sxs-lookup"><span data-stu-id="e3113-336">Carefully use type abbreviations to simplify F# code</span></span>

<span data-ttu-id="e3113-337">La reflection, strumenti e componenti .NET non visualizzeranno i nomi abbreviati per i tipi.</span><span class="sxs-lookup"><span data-stu-id="e3113-337">.NET components, tools, and reflection will not see abbreviated names for types.</span></span> <span data-ttu-id="e3113-338">Utilizzo significativo di abbreviazioni dei tipi può inoltre effettuare un dominio vengono visualizzati più complessa di quanto effettivamente è, quale operazione potrebbe confondere gli utenti.</span><span class="sxs-lookup"><span data-stu-id="e3113-338">Significant usage of type abbreviations can also make a domain appear more complex than it actually is, which could confuse consumers.</span></span>

#### <a name="avoid-type-abbreviations-for-public-types-whose-members-and-properties-should-be-intrinsically-different-to-those-available-on-the-type-being-abbreviated"></a><span data-ttu-id="e3113-339">Evitare le abbreviazioni dei tipi per i tipi pubblici di cui i membri e le proprietà devono essere intrinsecamente diversi rispetto a quelli disponibili nel tipo di cui è in corso abbreviato</span><span class="sxs-lookup"><span data-stu-id="e3113-339">Avoid type abbreviations for public types whose members and properties should be intrinsically different to those available on the type being abbreviated</span></span>

<span data-ttu-id="e3113-340">In questo caso, il tipo viene abbreviato rivela troppe operazioni sulla rappresentazione di tipo effettivo da definire.</span><span class="sxs-lookup"><span data-stu-id="e3113-340">In this case, the type being abbreviated reveals too much about the representation of the actual type being defined.</span></span> <span data-ttu-id="e3113-341">Al contrario, prendere in considerazione l'abbreviazione in un tipo di classe o un'unione discriminata case singolo di wrapping (oppure, quando le prestazioni sono essenziali, è consigliabile usare un tipo struct per eseguire il wrapping l'abbreviazione).</span><span class="sxs-lookup"><span data-stu-id="e3113-341">Instead, consider wrapping the abbreviation in a class type or a single-case discriminated union (or, when performance is essential, consider using a struct type to wrap the abbreviation).</span></span>

<span data-ttu-id="e3113-342">Ad esempio, è tentato di definire una mappa a più come un caso speciale di una mappa di F #, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="e3113-342">For example, it is tempting to define a multi-map as a special case of an F# map, for example:</span></span>

```fsharp
type MultiMap<'Key,'Value> = Map<'Key,'Value list>
```

<span data-ttu-id="e3113-343">Tuttavia, le operazioni di notazione con punto logico per questo tipo non sono le stesse operazioni su una mappa, ad esempio, è ragionevole che l'operatore di ricerca siano mappati. [key] Restituisce un elenco vuoto se la chiave non è presente nel dizionario, anziché generare un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="e3113-343">However, the logical dot-notation operations on this type are not the same as the operations on a Map – for example, it is reasonable that the lookup operator map.[key] return the empty list if the key is not in the dictionary, rather than raising an exception.</span></span>

## <a name="guidelines-for-libraries-for-use-from-other-net-languages"></a><span data-ttu-id="e3113-344">Linee guida per le raccolte per l'utilizzo in altri linguaggi .NET</span><span class="sxs-lookup"><span data-stu-id="e3113-344">Guidelines for libraries for Use from other .NET Languages</span></span>

<span data-ttu-id="e3113-345">Durante la progettazione di librerie per l'uso di altri linguaggi .NET, è importante rispettare le [indicazioni per la progettazione di librerie .NET](../../standard/design-guidelines/index.md).</span><span class="sxs-lookup"><span data-stu-id="e3113-345">When designing libraries for use from other .NET languages, it is important to adhere to the [.NET Library Design Guidelines](../../standard/design-guidelines/index.md).</span></span> <span data-ttu-id="e3113-346">In questo documento, queste librerie sono contrassegnate come "vanilla" librerie di .NET, invece di F #-facing librerie che utilizzano F # costruisce senza alcuna restrizione.</span><span class="sxs-lookup"><span data-stu-id="e3113-346">In this document, these libraries are labeled as vanilla .NET libraries, as opposed to F#-facing libraries that use F# constructs without restriction.</span></span> <span data-ttu-id="e3113-347">Progettazione di librerie .NET "vanilla" significa che fornisce le API di familiari e idiomatiche coerente con il resto di .NET Framework, riducendo al minimo l'uso di F #-costrutti specifici nell'API pubblica.</span><span class="sxs-lookup"><span data-stu-id="e3113-347">Designing vanilla .NET libraries means providing familiar and idiomatic APIs consistent with the rest of the .NET Framework by minimizing the use of F#-specific constructs in the public API.</span></span> <span data-ttu-id="e3113-348">Le regole sono illustrate nelle sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="e3113-348">The rules are explained in the following sections.</span></span>

### <a name="namespace-and-type-design-for-libraries-for-use-from-other-net-languages"></a><span data-ttu-id="e3113-349">Namespace e il tipo di progettazione (per le librerie per l'utilizzo in altri linguaggi .NET)</span><span class="sxs-lookup"><span data-stu-id="e3113-349">Namespace and Type design (for libraries for use from other .NET Languages)</span></span>

#### <a name="apply-the-net-naming-conventions-to-the-public-api-of-your-components"></a><span data-ttu-id="e3113-350">Applicare le convenzioni di denominazione .NET per l'API pubblica dei componenti</span><span class="sxs-lookup"><span data-stu-id="e3113-350">Apply the .NET naming conventions to the public API of your components</span></span>

<span data-ttu-id="e3113-351">Prestare particolare attenzione all'uso di nomi abbreviati e linee guida di maiuscole/minuscole di .NET.</span><span class="sxs-lookup"><span data-stu-id="e3113-351">Pay special attention to the use of abbreviated names and the .NET capitalization guidelines.</span></span>

```fsharp
type pCoord = ...
    member this.theta = ...

type PolarCoordinate = ...
    member this.Theta = ...
```

#### <a name="use-namespaces-types-and-members-as-the-primary-organizational-structure-for-your-components"></a><span data-ttu-id="e3113-352">Usare gli spazi dei nomi, tipi e membri della struttura organizzativa primaria per i componenti</span><span class="sxs-lookup"><span data-stu-id="e3113-352">Use namespaces, types, and members as the primary organizational structure for your components</span></span>

<span data-ttu-id="e3113-353">Tutti i file che contiene la funzionalità pubblica devono iniziare con un `namespace` dichiarazione e l'unica entità pubblici negli spazi dei nomi devono essere tipi.</span><span class="sxs-lookup"><span data-stu-id="e3113-353">All files containing public functionality should begin with a `namespace` declaration, and the only public-facing entities in namespaces should be types.</span></span> <span data-ttu-id="e3113-354">Non usare i moduli di F #.</span><span class="sxs-lookup"><span data-stu-id="e3113-354">Do not use F# modules.</span></span>

<span data-ttu-id="e3113-355">Usare i moduli non pubblici per contenere il codice di implementazione, utilità tipi e funzioni di utilità.</span><span class="sxs-lookup"><span data-stu-id="e3113-355">Use non-public modules to hold implementation code, utility types, and utility functions.</span></span>

<span data-ttu-id="e3113-356">I tipi statici devono essere Preferiti a moduli, poiché consentono un'ottica evolutiva future dell'API usare overload e altri concetti di progettazione di API .NET che non possono essere usati all'interno di moduli di F #.</span><span class="sxs-lookup"><span data-stu-id="e3113-356">Static types should be preferred over modules, as they allow for future evolution of the API to use overloading and other .NET API design concepts that may not be used within F# modules.</span></span>

<span data-ttu-id="e3113-357">Ad esempio, al posto dell'API pubblica seguente:</span><span class="sxs-lookup"><span data-stu-id="e3113-357">For example, in place of the following public API:</span></span>

```fsharp
module Fabrikam

module Utilities =
    let Name = "Bob"
    let Add2 x y = x + y
    let Add3 x y z = x + y + z
```

<span data-ttu-id="e3113-358">Si consideri invece:</span><span class="sxs-lookup"><span data-stu-id="e3113-358">Consider instead:</span></span>

```fsharp
namespace Fabrikam

[<AbstractClass; Sealed>]
type Utilities =
    static member Name = "Bob"
    static member Add(x,y) = x + y
    static member Add(x,y,z) = x + y + z
```

#### <a name="use-f-record-types-in-vanilla-net-apis-if-the-design-of-the-types-wont-evolve"></a><span data-ttu-id="e3113-359">Usare i tipi di record F # in vanilla API .NET se non si evoluzione la progettazione dei tipi</span><span class="sxs-lookup"><span data-stu-id="e3113-359">Use F# record types in vanilla .NET APIs if the design of the types won't evolve</span></span>

<span data-ttu-id="e3113-360">I tipi di record F # compilate in una classe .NET semplice.</span><span class="sxs-lookup"><span data-stu-id="e3113-360">F# record types compile to a simple .NET class.</span></span> <span data-ttu-id="e3113-361">Questi sono adatti per alcuni tipi semplici e stabili per le API.</span><span class="sxs-lookup"><span data-stu-id="e3113-361">These are suitable for some simple, stable types in APIs.</span></span> <span data-ttu-id="e3113-362">È consigliabile usare la `[<NoEquality>]` e `[<NoComparison>]` attributi per eliminare la generazione automatica delle interfacce.</span><span class="sxs-lookup"><span data-stu-id="e3113-362">You should consider using the `[<NoEquality>]` and `[<NoComparison>]` attributes to suppress the automatic generation of interfaces.</span></span> <span data-ttu-id="e3113-363">Anche evitare di usare campi modificabili record vanilla API .NET come questi espone un campo pubblico.</span><span class="sxs-lookup"><span data-stu-id="e3113-363">Also avoid using mutable record fields in vanilla .NET APIs as these exposes a public field.</span></span> <span data-ttu-id="e3113-364">Valutare sempre se una classe fornisce un'opzione più flessibile per evoluzione futura dell'API.</span><span class="sxs-lookup"><span data-stu-id="e3113-364">Always consider whether a class would provide a more flexible option for future evolution of the API.</span></span>

<span data-ttu-id="e3113-365">Ad esempio, il codice F # seguente espone l'API pubblica a un consumer in c#:</span><span class="sxs-lookup"><span data-stu-id="e3113-365">For example, the following F# code exposes the public API to a C# consumer:</span></span>

<span data-ttu-id="e3113-366">F #:</span><span class="sxs-lookup"><span data-stu-id="e3113-366">F#:</span></span>

```fsharp
[<NoEquality; NoComparison>]
type MyRecord =
    { FirstThing : int
        SecondThing : string }
```

<span data-ttu-id="e3113-367">C#:</span><span class="sxs-lookup"><span data-stu-id="e3113-367">C#:</span></span>

```csharp
public sealed class MyRecord
{
    public MyRecord(int firstThing, string secondThing);
    public int FirstThing { get; }
    public string SecondThing { get; }
}
```

#### <a name="hide-the-representation-of-f-union-types-in-vanilla-net-apis"></a><span data-ttu-id="e3113-368">Nascondere la rappresentazione dei tipi unione F # in vanilla API .NET</span><span class="sxs-lookup"><span data-stu-id="e3113-368">Hide the representation of F# union types in vanilla .NET APIs</span></span>

<span data-ttu-id="e3113-369">Tipi di unione F # non usati comunemente nei limiti dei componenti, anche per F #-a-F # di codifica.</span><span class="sxs-lookup"><span data-stu-id="e3113-369">F# union types are not commonly used across component boundaries, even for F#-to-F# coding.</span></span> <span data-ttu-id="e3113-370">Si tratta di un dispositivo di implementazione eccellenti quando usata internamente all'interno di componenti e librerie.</span><span class="sxs-lookup"><span data-stu-id="e3113-370">They are an excellent implementation device when used internally within components and libraries.</span></span>

<span data-ttu-id="e3113-371">Quando si progetta un'API .NET di vanilla, prendere in considerazione se si nasconde la rappresentazione di un tipo di unione tramite una dichiarazione privata o un file della firma.</span><span class="sxs-lookup"><span data-stu-id="e3113-371">When designing a vanilla .NET API, consider hiding the representation of a union type by using either a private declaration or a signature file.</span></span>

```fsharp
type PropLogic =
    private
    | And of PropLogic * PropLogic
    | Not of PropLogic
    | True
```

<span data-ttu-id="e3113-372">Si potrebbero aumentare anche tipi che utilizzano internamente una rappresentazione in forma unione con i membri per fornire un desiderato. API rivolte NET.</span><span class="sxs-lookup"><span data-stu-id="e3113-372">You may also augment types that use a union representation internally with members to provide a desired .NET-facing API.</span></span>

```fsharp
type PropLogic =
    private
    | And of PropLogic * PropLogic
    | Not of PropLogic
    | True

    /// A public member for use from C#
    member x.Evaluate =
        match x with
        | And(a,b) -> a.Evaluate && b.Evaluate
        | Not a -> not a.Evaluate
        | True -> true

    /// A public member for use from C#
    static member CreateAnd(a,b) = And(a,b)
```

#### <a name="design-gui-and-other-components-using-the-design-patterns-of-the-framework"></a><span data-ttu-id="e3113-373">Progettazione interfaccia utente grafica e altri componenti tramite i modelli di progettazione di framework</span><span class="sxs-lookup"><span data-stu-id="e3113-373">Design GUI and other components using the design patterns of the framework</span></span>

<span data-ttu-id="e3113-374">Sono disponibili molti framework differenti all'interno di .NET, ad esempio WinForms, WPF e ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="e3113-374">There are many different frameworks available within .NET, such as WinForms, WPF, and ASP.NET.</span></span> <span data-ttu-id="e3113-375">Convenzioni di denominazione e progettazione per ognuno devono essere utilizzate se si progettano i componenti per l'utilizzo in tali Framework.</span><span class="sxs-lookup"><span data-stu-id="e3113-375">Naming and design conventions for each should be used if you are designing components for use in these frameworks.</span></span> <span data-ttu-id="e3113-376">Ad esempio, per la programmazione WPF, adottare i modelli di progettazione WPF per le classi che si sta progettando.</span><span class="sxs-lookup"><span data-stu-id="e3113-376">For example, for WPF programming, adopt WPF design patterns for the classes you are designing.</span></span> <span data-ttu-id="e3113-377">Per i modelli di programmazione dell'interfaccia utente, usare modelli di progettazione, ad esempio eventi e le raccolte basato sulla notifica, ad esempio quelli disponibili in <xref:System.Collections.ObjectModel>.</span><span class="sxs-lookup"><span data-stu-id="e3113-377">For models in user interface programming, use design patterns such as events and notification-based collections such as those found in <xref:System.Collections.ObjectModel>.</span></span>

### <a name="object-and-member-design-for-libraries-for-use-from-other-net-languages"></a><span data-ttu-id="e3113-378">Progettazione di oggetti e membri (per le librerie per l'utilizzo in altri linguaggi .NET)</span><span class="sxs-lookup"><span data-stu-id="e3113-378">Object and Member design (for libraries for use from other .NET Languages)</span></span>

#### <a name="use-the-clievent-attribute-to-expose-net-events"></a><span data-ttu-id="e3113-379">Usare l'attributo CLIEvent per esporre gli eventi .NET</span><span class="sxs-lookup"><span data-stu-id="e3113-379">Use the CLIEvent attribute to expose .NET events</span></span>

<span data-ttu-id="e3113-380">Costruire una `DelegateEvent` con una specifica di .NET tipo che accetta un oggetto delegato e `EventArgs` (anziché un' `Event`, che usa solo il `FSharpHandler` tipo per impostazione predefinita), in modo che gli eventi vengono pubblicati in modo familiare per altri linguaggi .NET.</span><span class="sxs-lookup"><span data-stu-id="e3113-380">Construct a `DelegateEvent` with a specific .NET delegate type that takes an object and `EventArgs` (rather than an `Event`, which just uses the `FSharpHandler` type by default) so that the events are published in the familiar way to other .NET languages.</span></span>

```fsharp
type MyBadType() =
    let myEv = new Event<int>()

    [<CLIEvent>]
    member this.MyEvent = myEv.Publish

type MyEventArgs(x:int) =
    inherit System.EventArgs()
    member this.X = x

    /// A type in a component designed for use from other .NET languages
type MyGoodType() =
    let myEv = new DelegateEvent<EventHandler<MyEventArgs>>()

    [<CLIEvent>]
    member this.MyEvent = myEv.Publish
```

#### <a name="expose-asynchronous-operations-as-methods-which-return-net-tasks"></a><span data-ttu-id="e3113-381">Esponi le operazioni asincrone come metodi che restituiscono le attività .NET</span><span class="sxs-lookup"><span data-stu-id="e3113-381">Expose asynchronous operations as methods which return .NET tasks</span></span>

<span data-ttu-id="e3113-382">Le attività vengono usate in .NET per rappresentare i calcoli asincroni attivi.</span><span class="sxs-lookup"><span data-stu-id="e3113-382">Tasks are used in .NET to represent active asynchronous computations.</span></span> <span data-ttu-id="e3113-383">Le attività sono in genere meno composizionale rispetto a F # `Async<T>` oggetti, poiché rappresentano le attività "già in esecuzione" e non possono essere composti insieme nei modi che eseguire la composizione di parallel, o che nasconde la propagazione dei segnali di annullamento e le altre parametri di contestuali.</span><span class="sxs-lookup"><span data-stu-id="e3113-383">Tasks are in general less compositional than F# `Async<T>` objects, since they represent “already executing” tasks and can’t be composed together in ways that perform parallel composition, or which hide the propagation of cancellation signals and other contextual parameters.</span></span>

<span data-ttu-id="e3113-384">Tuttavia, nonostante ciò, i metodi che restituiscono le attività sono la rappresentazione della programmazione asincrona in .NET standard.</span><span class="sxs-lookup"><span data-stu-id="e3113-384">However, despite this, methods which return Tasks are the standard representation of asynchronous programming on .NET.</span></span>

```fsharp
/// A type in a component designed for use from other .NET languages
type MyType() =

    let compute (x: int) : Async<int> = async { ... }

    member this.ComputeAsync(x) = compute x |> Async.StartAsTask
```

<span data-ttu-id="e3113-385">Sarà spesso anche vuole accettare un token di annullamento esplicito:</span><span class="sxs-lookup"><span data-stu-id="e3113-385">You will frequently also want to accept an explicit cancellation token:</span></span>

```fsharp
/// A type in a component designed for use from other .NET languages
type MyType() =
    let compute(x:int) : Async<int> = async { ... }
    member this.ComputeAsTask(x, cancellationToken) = Async.StartAsTask(compute x, cancellationToken)
```

#### <a name="use-net-delegate-types-instead-of-f-function-types"></a><span data-ttu-id="e3113-386">Usare i tipi di delegati di .NET anziché dei tipi di funzione F #</span><span class="sxs-lookup"><span data-stu-id="e3113-386">Use .NET delegate types instead of F# function types</span></span>

<span data-ttu-id="e3113-387">In questo caso "tipi di funzione F #" significa che i tipi di "freccia" come `int -> int`.</span><span class="sxs-lookup"><span data-stu-id="e3113-387">Here “F# function types” mean “arrow” types like `int -> int`.</span></span>

<span data-ttu-id="e3113-388">Anziché il seguente:</span><span class="sxs-lookup"><span data-stu-id="e3113-388">Instead of this:</span></span>

```fsharp
member this.Transform(f:int->int) =
    ...
```

<span data-ttu-id="e3113-389">Eseguire questa operazione:</span><span class="sxs-lookup"><span data-stu-id="e3113-389">Do this:</span></span>

```fsharp
member this.Transform(f:Func<int,int>) =
    ...
```

<span data-ttu-id="e3113-390">Viene visualizzato il tipo di funzione F # come `class FSharpFunc<T,U>` per altri linguaggi .NET ed è meno adatto per le funzionalità del linguaggio e gli strumenti che supportano i tipi delegati.</span><span class="sxs-lookup"><span data-stu-id="e3113-390">The F# function type appears as `class FSharpFunc<T,U>` to other .NET languages, and is less suitable for language features and tooling that understand delegate types.</span></span> <span data-ttu-id="e3113-391">Durante la creazione di un metodo di ordine superiore destinate a .NET Framework 3.5 o versione successiva, il `System.Func` e `System.Action` i delegati sono le API a destra per la pubblicazione per consentire agli sviluppatori .NET di usare queste API in modo semplice.</span><span class="sxs-lookup"><span data-stu-id="e3113-391">When authoring a higher-order method targeting .NET Framework 3.5 or higher, the `System.Func` and `System.Action` delegates are the right APIs to publish to enable .NET developers to consume these APIs in a low-friction manner.</span></span> <span data-ttu-id="e3113-392">(Quando la destinazione è .NET Framework 2.0, i tipi delegati definiti dal sistema sono più limitati, è consigliabile usare tipi delegato predefinito, ad esempio `System.Converter<T,U>` o definizione di un tipo delegato specifico.)</span><span class="sxs-lookup"><span data-stu-id="e3113-392">(When targeting .NET Framework 2.0, the system-defined delegate types are more limited; consider using predefined delegate types such as `System.Converter<T,U>` or defining a specific delegate type.)</span></span>

<span data-ttu-id="e3113-393">D'altra parte, i delegati di .NET non siano naturali per F #-rivolta librerie (vedere la sezione successiva in F #-rivolta librerie).</span><span class="sxs-lookup"><span data-stu-id="e3113-393">On the flip side, .NET delegates are not natural for F#-facing libraries (see the next Section on F#-facing libraries).</span></span> <span data-ttu-id="e3113-394">Di conseguenza, una strategia di implementazione comune quando si sviluppano i metodi di ordine superiore per vanilla librerie .NET consiste nel creare tutto l'implementazione che usa tipi di funzione F # e quindi creare l'API pubblica uso dei delegati come un'interfaccia thin sopra l'effettivo F # implementazione.</span><span class="sxs-lookup"><span data-stu-id="e3113-394">As a result, a common implementation strategy when developing higher-order methods for vanilla .NET libraries is to author all the implementation using F# function types, and then create the public API using delegates as a thin façade atop the actual F# implementation.</span></span>

#### <a name="use-the-trygetvalue-pattern-instead-of-returning-f-option-values-and-prefer-method-overloading-to-taking-f-option-values-as-arguments"></a><span data-ttu-id="e3113-395">Usare il modello TryGetValue invece di restituire i valori delle opzioni F # e preferiscono l'overload di metodo all'esecuzione di valori delle opzioni F # come argomenti</span><span class="sxs-lookup"><span data-stu-id="e3113-395">Use the TryGetValue pattern instead of returning F# option values, and prefer method overloading to taking F# option values as arguments</span></span>

<span data-ttu-id="e3113-396">Modelli comuni di utilizzo per il tipo di opzione F # per le API sono preferibili implementato in vanilla tecniche di progettazione API .NET con .NET standard.</span><span class="sxs-lookup"><span data-stu-id="e3113-396">Common patterns of use for the F# option type in APIs are better implemented in vanilla .NET APIs using standard .NET design techniques.</span></span> <span data-ttu-id="e3113-397">Invece di restituire un valore di opzione di F #, è consigliabile usare il tipo restituito bool oltre a un parametro out come il modello "TryGetValue".</span><span class="sxs-lookup"><span data-stu-id="e3113-397">Instead of returning an F# option value, consider using the bool return type plus an out parameter as in the "TryGetValue" pattern.</span></span> <span data-ttu-id="e3113-398">E anziché adottare valori delle opzioni F # come parametri, è consigliabile usare l'overload di metodo o argomenti facoltativi.</span><span class="sxs-lookup"><span data-stu-id="e3113-398">And instead of taking F# option values as parameters, consider using method overloading or optional arguments.</span></span>

```fsharp
member this.ReturnOption() = Some 3

member this.ReturnBoolAndOut(outVal : byref<int>) =
    outVal <- 3
    true

member this.ParamOption(x : int, y : int option) =
    match y with
    | Some y2 -> x + y2
    | None -> x

member this.ParamOverload(x : int) = x

member this.ParamOverload(x : int, y : int) = x + y
```

#### <a name="use-the-net-collection-interface-types-ienumerablet-and-idictionarykeyvalue-for-parameters-and-return-values"></a><span data-ttu-id="e3113-399">Usare l'interfaccia di raccolta .NET i tipi di IEnumerable\<T\> e IDictionary\<chiave, valore\> per i parametri e valori restituiti</span><span class="sxs-lookup"><span data-stu-id="e3113-399">Use the .NET collection interface types IEnumerable\<T\> and IDictionary\<Key,Value\> for parameters and return values</span></span>

<span data-ttu-id="e3113-400">Evitare l'utilizzo di tipi, ad esempio le matrici .NET di raccolta concreti `T[]`, i tipi F # `list<T>`, `Map<Key,Value>` e `Set<T>`, e i tipi di raccolta concreti .NET, ad esempio `Dictionary<Key,Value>`.</span><span class="sxs-lookup"><span data-stu-id="e3113-400">Avoid the use of concrete collection types such as .NET arrays `T[]`, F# types `list<T>`, `Map<Key,Value>` and `Set<T>`, and .NET concrete collection types such as `Dictionary<Key,Value>`.</span></span> <span data-ttu-id="e3113-401">Linee guida di progettazione di .NET della libreria sono ottimo suggerimento relative all'utilizzo di diversi tipi di raccolta, ad esempio `IEnumerable<T>`.</span><span class="sxs-lookup"><span data-stu-id="e3113-401">The .NET Library Design Guidelines have good advice regarding when to use various collection types like `IEnumerable<T>`.</span></span> <span data-ttu-id="e3113-402">Utilizzato per scopi di matrici (`T[]`) è accettabile in alcune circostanze, per motivi di prestazioni.</span><span class="sxs-lookup"><span data-stu-id="e3113-402">Some use of arrays (`T[]`) is acceptable in some circumstances, on performance grounds.</span></span> <span data-ttu-id="e3113-403">Si noti che in particolare `seq<T>` è solo di F # alias di `IEnumerable<T>`, ed è pertanto seq spesso un tipo appropriato per un normale API .NET.</span><span class="sxs-lookup"><span data-stu-id="e3113-403">Note especially that `seq<T>` is just the F# alias for `IEnumerable<T>`, and thus seq is often an appropriate type for a vanilla .NET API.</span></span>

<span data-ttu-id="e3113-404">Invece di elenchi F #:</span><span class="sxs-lookup"><span data-stu-id="e3113-404">Instead of F# lists:</span></span>

```fsharp
member this.PrintNames(names : string list) =
    ...
```

<span data-ttu-id="e3113-405">Usare le sequenze di F #:</span><span class="sxs-lookup"><span data-stu-id="e3113-405">Use F# sequences:</span></span>

```fsharp
member this.PrintNames(names : seq<string>) =
    ...
```

#### <a name="use-the-unit-type-as-the-only-input-type-of-a-method-to-define-a-zero-argument-method-or-as-the-only-return-type-to-define-a-void-returning-method"></a><span data-ttu-id="e3113-406">Usare il tipo di unità come l'unico tipo di input di un metodo per definire un metodo specificato dall'argomento di zero o come unico tipo per definire un metodo che restituisce void restituito</span><span class="sxs-lookup"><span data-stu-id="e3113-406">Use the unit type as the only input type of a method to define a zero-argument method, or as the only return type to define a void-returning method</span></span>

<span data-ttu-id="e3113-407">Evitare di altri utilizzi del tipo di unità.</span><span class="sxs-lookup"><span data-stu-id="e3113-407">Avoid other uses of the unit type.</span></span> <span data-ttu-id="e3113-408">Si tratta di una buona:</span><span class="sxs-lookup"><span data-stu-id="e3113-408">These are good:</span></span>

```fsharp
✔ member this.NoArguments() = 3

✔ member this.ReturnVoid(x : int) = ()
```

<span data-ttu-id="e3113-409">Si tratta di una non valido:</span><span class="sxs-lookup"><span data-stu-id="e3113-409">This is bad:</span></span>

```fsharp
member this.WrongUnit( x:unit, z:int) = ((), ())
```

#### <a name="check-for-null-values-on-vanilla-net-api-boundaries"></a><span data-ttu-id="e3113-410">Verificare la presenza di valori null in "vanilla" dei limiti delle API .NET</span><span class="sxs-lookup"><span data-stu-id="e3113-410">Check for null values on vanilla .NET API boundaries</span></span>

<span data-ttu-id="e3113-411">Codice di implementazione F # tende ad avere un minor numero di valori null, a causa di limitazioni sull'utilizzo di valori letterali null mobili per i tipi F # e modelli di progettazione non modificabile.</span><span class="sxs-lookup"><span data-stu-id="e3113-411">F# implementation code tends to have fewer null values, due to immutable design patterns and restrictions on use of null literals for F# types.</span></span> <span data-ttu-id="e3113-412">Altri linguaggi .NET utilizzano spesso null come un valore molto più frequentemente.</span><span class="sxs-lookup"><span data-stu-id="e3113-412">Other .NET languages often use null as a value much more frequently.</span></span> <span data-ttu-id="e3113-413">Per questo motivo, codice F # che espone un'API .NET di vanilla deve controllare i parametri i valori null in corrispondenza del limite di API e impedire che tali valori pervengono più approfondito il codice di implementazione F #.</span><span class="sxs-lookup"><span data-stu-id="e3113-413">Because of this, F# code that is exposing a vanilla .NET API should check parameters for null at the API boundary, and prevent these values from flowing deeper into the F# implementation code.</span></span> <span data-ttu-id="e3113-414">Il `isNull` funzione o criteri di ricerca nel `null` modello può essere usato.</span><span class="sxs-lookup"><span data-stu-id="e3113-414">The `isNull` function or pattern matching on the `null` pattern can be used.</span></span>

```fsharp
let checkNonNull argName (arg: obj) =
    match arg with
    | null -> nullArg argName
    | _ -> ()

let checkNonNull` argName (arg: obj) =
    if isNull arg then nullArg argName
    else ()
```

#### <a name="avoid-using-tuples-as-return-values"></a><span data-ttu-id="e3113-415">Evitare di usare le tuple come valori restituiti</span><span class="sxs-lookup"><span data-stu-id="e3113-415">Avoid using tuples as return values</span></span>

<span data-ttu-id="e3113-416">Preferire invece la restituzione di un tipo denominato che contiene i dati aggregati o tramite i parametri out per restituire più valori.</span><span class="sxs-lookup"><span data-stu-id="e3113-416">Instead, prefer returning a named type holding the aggregate data, or using out parameters to return multiple values.</span></span> <span data-ttu-id="e3113-417">Anche se esistono le tuple e le tuple struct in .NET, incluso supporto del linguaggio c# per le tuple struct, vengono in genere non fornirà l'API ideale e previsto per gli sviluppatori .NET.</span><span class="sxs-lookup"><span data-stu-id="e3113-417">Although tuples and struct tuples exist in .NET (including C# language support for struct tuples), they will most often not provide the ideal and expected API for .NET developers.</span></span>

#### <a name="avoid-the-use-of-currying-of-parameters"></a><span data-ttu-id="e3113-418">Evitare l'uso di currying dei parametri</span><span class="sxs-lookup"><span data-stu-id="e3113-418">Avoid the use of currying of parameters</span></span>

<span data-ttu-id="e3113-419">Usare invece le convenzioni di chiamata .NET ``Method(arg1,arg2,…,argN)``.</span><span class="sxs-lookup"><span data-stu-id="e3113-419">Instead, use .NET calling conventions ``Method(arg1,arg2,…,argN)``.</span></span>

```fsharp
member this.TupledArguments(str, num) = String.replicate num str
```

<span data-ttu-id="e3113-420">Suggerimento: Se si sta progettando le librerie per l'utilizzo in qualsiasi linguaggio .NET, non è alcuna sostituzione di effettivamente eseguite alcune sperimentale in c# e Visual Basic programming per garantire che le librerie "aspetto destra" da questi linguaggi.</span><span class="sxs-lookup"><span data-stu-id="e3113-420">Tip: If you’re designing libraries for use from any .NET language, then there’s no substitute for actually doing some experimental C# and Visual Basic programming to ensure that your libraries "feel right" from these languages.</span></span> <span data-ttu-id="e3113-421">È anche possibile usare strumenti, ad esempio .NET Reflector e il Visualizzatore oggetti di Visual Studio per garantire che le librerie e la relativa documentazione vengono visualizzati come previsto per gli sviluppatori.</span><span class="sxs-lookup"><span data-stu-id="e3113-421">You can also use tools such as .NET Reflector and the Visual Studio Object Browser to ensure that libraries and their documentation appear as expected to developers.</span></span>

## <a name="appendix"></a><span data-ttu-id="e3113-422">Appendice</span><span class="sxs-lookup"><span data-stu-id="e3113-422">Appendix</span></span>

### <a name="end-to-end-example-of-designing-f-code-for-use-by-other-net-languages"></a><span data-ttu-id="e3113-423">Esempio end-to-end di progettazione di codice F # per l'uso da altri linguaggi .NET</span><span class="sxs-lookup"><span data-stu-id="e3113-423">End-to-end example of designing F# code for use by other .NET languages</span></span>

<span data-ttu-id="e3113-424">Si consideri la classe seguente:</span><span class="sxs-lookup"><span data-stu-id="e3113-424">Consider the following class:</span></span>

```fsharp
open System

type Point1(angle,radius) =
    new() = Point1(angle=0.0, radius=0.0)
    member x.Angle = angle
    member x.Radius = radius
    member x.Stretch(l) = Point1(angle=x.Angle, radius=x.Radius * l)
    member x.Warp(f) = Point1(angle=f(x.Angle), radius=x.Radius)
    static member Circle(n) =
        [ for i in 1..n -> Point1(angle=2.0*Math.PI/float(n), radius=1.0) ]
```

<span data-ttu-id="e3113-425">Il tipo F # derivato di questa classe è il seguente:</span><span class="sxs-lookup"><span data-stu-id="e3113-425">The inferred F# type of this class is as follows:</span></span>

```fsharp
type Point1 =
    new : unit -> Point1
    new : angle:double * radius:double -> Point1
    static member Circle : n:int -> Point1 list
    member Stretch : l:double -> Point1
    member Warp : f:(double -> double) -> Point1
    member Angle : double
    member Radius : double
```

<span data-ttu-id="e3113-426">Diamo un'occhiata a come viene visualizzato questo tipo di F # per un programmatore che utilizza un altro linguaggio .NET.</span><span class="sxs-lookup"><span data-stu-id="e3113-426">Let’s take a look at how this F# type appears to a programmer using another .NET language.</span></span> <span data-ttu-id="e3113-427">Ad esempio, approssimativo c# "firma" è come segue:</span><span class="sxs-lookup"><span data-stu-id="e3113-427">For example, the approximate C# “signature” is as follows:</span></span>

```csharp
// C# signature for the unadjusted Point1 class
public class Point1
{
    public Point1();

    public Point1(double angle, double radius);

    public static Microsoft.FSharp.Collections.List<Point1> Circle(int count);

    public Point1 Stretch(double factor);

    public Point1 Warp(Microsoft.FSharp.Core.FastFunc<double,double> transform);

    public double Angle { get; }

    public double Radius { get; }
}
```

<span data-ttu-id="e3113-428">Esistono alcuni aspetti importanti da notare il modo in F # rappresenta costrutti qui.</span><span class="sxs-lookup"><span data-stu-id="e3113-428">There are some important points to notice about how F# represents constructs here.</span></span> <span data-ttu-id="e3113-429">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="e3113-429">For example:</span></span>

* <span data-ttu-id="e3113-430">I metadati, ad esempio i nomi degli argomenti sono stato mantenuto.</span><span class="sxs-lookup"><span data-stu-id="e3113-430">Metadata such as argument names has been preserved.</span></span>

* <span data-ttu-id="e3113-431">Metodi di F # che accettano due argomenti diventano c# i metodi che accettano due argomenti.</span><span class="sxs-lookup"><span data-stu-id="e3113-431">F# methods that take two arguments become C# methods that take two arguments.</span></span>

* <span data-ttu-id="e3113-432">Funzioni e gli elenchi diventano i riferimenti ai tipi corrispondenti nella libreria di F #.</span><span class="sxs-lookup"><span data-stu-id="e3113-432">Functions and lists become references to corresponding types in the F# library.</span></span>

<span data-ttu-id="e3113-433">Il codice seguente viene illustrato come modificare il codice per tenere conto di queste operazioni.</span><span class="sxs-lookup"><span data-stu-id="e3113-433">The following code shows how to adjust this code to take these things into account.</span></span>

```fsharp
namespace SuperDuperFSharpLibrary.Types

type RadialPoint(angle:double, radius:double) =

    /// Return a point at the origin
    new() = RadialPoint(angle=0.0, radius=0.0)

    /// The angle to the point, from the x-axis
    member x.Angle = angle

    /// The distance to the point, from the origin
    member x.Radius = radius

    /// Return a new point, with radius multiplied by the given factor
    member x.Stretch(factor) =
        RadialPoint(angle=angle, radius=radius * factor)

    /// Return a new point, with angle transformed by the function
    member x.Warp(transform:Func<_,_>) =
        RadialPoint(angle=transform.Invoke angle, radius=radius)

    /// Return a sequence of points describing an approximate circle using
    /// the given count of points
    static member Circle(count) =
        seq { for i in 1..count ->
                RadialPoint(angle=2.0*Math.PI/float(count), radius=1.0) }
```

<span data-ttu-id="e3113-434">Il tipo F # dedotto del codice è il seguente:</span><span class="sxs-lookup"><span data-stu-id="e3113-434">The inferred F# type of the code is as follows:</span></span>

```fsharp
type RadialPoint =
    new : unit -> RadialPoint
    new : angle:double * radius:double -> RadialPoint
    static member Circle : count:int -> seq<RadialPoint>
    member Stretch : factor:double -> RadialPoint
    member Warp : transform:System.Func<double,double> -> RadialPoint
    member Angle : double
    member Radius : double
```

<span data-ttu-id="e3113-435">La firma c# è ora come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="e3113-435">The C# signature is now as follows:</span></span>

```csharp
public class RadialPoint
{
    public RadialPoint();

    public RadialPoint(double angle, double radius);

    public static System.Collections.Generic.IEnumerable<RadialPoint> Circle(int count);

    public RadialPoint Stretch(double factor);

    public RadialPoint Warp(System.Func<double,double> transform);

    public double Angle { get; }

    public double Radius { get; }
}
```

<span data-ttu-id="e3113-436">Le correzioni apportate per preparare questo tipo per l'uso come parte di una libreria .NET "vanilla" sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="e3113-436">The fixes made to prepare this type for use as part of a vanilla .NET library are as follows:</span></span>

* <span data-ttu-id="e3113-437">Regolato diversi nomi: `Point1`, `n`, `l`, e `f` è diventato `RadialPoint`, `count`, `factor`, e `transform`, rispettivamente.</span><span class="sxs-lookup"><span data-stu-id="e3113-437">Adjusted several names: `Point1`, `n`, `l`, and `f` became `RadialPoint`, `count`, `factor`, and `transform`, respectively.</span></span>

* <span data-ttu-id="e3113-438">Utilizzato un tipo restituito `seq<RadialPoint>` invece di `RadialPoint list` modificando una costruzione elenco utilizzando `[ ... ]` a una sequenza di costruzione utilizzando `IEnumerable<RadialPoint>`.</span><span class="sxs-lookup"><span data-stu-id="e3113-438">Used a return type of `seq<RadialPoint>` instead of `RadialPoint list` by changing a list construction using `[ ... ]` to a sequence construction using `IEnumerable<RadialPoint>`.</span></span>

* <span data-ttu-id="e3113-439">Utilizzare il tipo di delegato .NET `System.Func` invece di un tipo di funzione F #.</span><span class="sxs-lookup"><span data-stu-id="e3113-439">Used the .NET delegate type `System.Func` instead of an F# function type.</span></span>

<span data-ttu-id="e3113-440">Questo rende molto accattivante utilizzare nel codice c#.</span><span class="sxs-lookup"><span data-stu-id="e3113-440">This makes it far nicer to consume in C# code.</span></span>

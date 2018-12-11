---
title: F#linee guida di progettazione componenti
description: Le linee guida per la scrittura di informazioni su F# componenti destinati all'utilizzo da altri chiamanti.
ms.date: 05/14/2018
ms.openlocfilehash: bc8d4908912c4630f649ba30593d43a557278efa
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2018
ms.locfileid: "53145673"
---
# <a name="f-component-design-guidelines"></a><span data-ttu-id="c732e-103">F#linee guida di progettazione componenti</span><span class="sxs-lookup"><span data-stu-id="c732e-103">F# component design guidelines</span></span>

<span data-ttu-id="c732e-104">Questo documento è un set di linee guida di progettazione di componenti per F# programmazione, in base il F# linee guida di progettazione di componenti, v14, Microsoft Research, e [un'altra versione](https://fsharp.org/specs/component-design-guidelines/) originariamente curata e gestito dal F# Software Foundation.</span><span class="sxs-lookup"><span data-stu-id="c732e-104">This document is a set of component design guidelines for F# programming, based on the F# Component Design Guidelines, v14, Microsoft Research, and [another version](https://fsharp.org/specs/component-design-guidelines/) originally curated and maintained by the F# Software Foundation.</span></span>

<span data-ttu-id="c732e-105">Questo documento presuppone una familiarità con F# programmazione.</span><span class="sxs-lookup"><span data-stu-id="c732e-105">This document assumes you are familiar with F# programming.</span></span> <span data-ttu-id="c732e-106">Molti grazie ai F# community per i relativi contributi e commenti e suggerimenti utili su varie versioni di questa Guida.</span><span class="sxs-lookup"><span data-stu-id="c732e-106">Many thanks to the F# community for their contributions and helpful feedback on various versions of this guide.</span></span>

## <a name="overview"></a><span data-ttu-id="c732e-107">Panoramica</span><span class="sxs-lookup"><span data-stu-id="c732e-107">Overview</span></span>

<span data-ttu-id="c732e-108">Questo documento vengono esaminati alcuni dei problemi correlati a F# componente progettazione e codifica.</span><span class="sxs-lookup"><span data-stu-id="c732e-108">This document looks at some of the issues related to F# component design and coding.</span></span> <span data-ttu-id="c732e-109">Un componente può significare che gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="c732e-109">A component can mean any of the following:</span></span>

* <span data-ttu-id="c732e-110">Un livello all'interno di F# progetto con gli utenti esterni all'interno di tale progetto.</span><span class="sxs-lookup"><span data-stu-id="c732e-110">A layer in your F# project that has external consumers within that project.</span></span>
* <span data-ttu-id="c732e-111">Una libreria destinata all'utilizzo da F# codice attraverso i limiti di assembly.</span><span class="sxs-lookup"><span data-stu-id="c732e-111">A library intended for consumption by F# code across assembly boundaries.</span></span>
* <span data-ttu-id="c732e-112">Una libreria destinata all'utilizzo da qualsiasi linguaggio .NET attraverso i limiti di assembly.</span><span class="sxs-lookup"><span data-stu-id="c732e-112">A library intended for consumption by any .NET language across assembly boundaries.</span></span>
* <span data-ttu-id="c732e-113">Una libreria destinata alla distribuzione tramite un repository dei pacchetti, ad esempio [NuGet](https://nuget.org).</span><span class="sxs-lookup"><span data-stu-id="c732e-113">A library intended for distribution via a package repository, such as [NuGet](https://nuget.org).</span></span>

<span data-ttu-id="c732e-114">Seguono le tecniche descritte in questo articolo il [cinque principi buone F# codice](index.md#five-principles-of-good-f-code)e pertanto utilizzano entrambi funzionali e oggetti di programmazione come appropriato.</span><span class="sxs-lookup"><span data-stu-id="c732e-114">Techniques described in this article follow the [Five principles of good F# code](index.md#five-principles-of-good-f-code), and thus utilize both functional and object programming as appropriate.</span></span>

<span data-ttu-id="c732e-115">Indipendentemente dalla metodologia, la finestra di progettazione di componenti e la libreria deve affrontare alcuni problemi pratici e banale durante il tentativo di creare un'API più facilmente utilizzabile dagli sviluppatori.</span><span class="sxs-lookup"><span data-stu-id="c732e-115">Regardless of the methodology, the component and library designer faces a number of practical and prosaic issues when trying to craft an API that is most easily usable by developers.</span></span> <span data-ttu-id="c732e-116">Attenta applicazione dei [indicazioni per la progettazione di librerie .NET](../../standard/design-guidelines/index.md) verrà volgere è per la creazione di un set coerente di API che sono piacevole da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="c732e-116">Conscientious application of the [.NET Library Design Guidelines](../../standard/design-guidelines/index.md) will steer you towards creating a consistent set of APIs that are pleasant to consume.</span></span>

## <a name="general-guidelines"></a><span data-ttu-id="c732e-117">Indicazioni generali</span><span class="sxs-lookup"><span data-stu-id="c732e-117">General guidelines</span></span>

<span data-ttu-id="c732e-118">Esistono alcune indicazioni universali che si applicano a F# le librerie, indipendentemente dai destinatari per la libreria.</span><span class="sxs-lookup"><span data-stu-id="c732e-118">There are a few universal guidelines that apply to F# libraries, regardless of the intended audience for the library.</span></span>

### <a name="learn-the-net-library-design-guidelines"></a><span data-ttu-id="c732e-119">Altre linee guida di progettazione di .NET della libreria</span><span class="sxs-lookup"><span data-stu-id="c732e-119">Learn the .NET Library Design Guidelines</span></span>

<span data-ttu-id="c732e-120">Indipendentemente dal tipo di F# scrittura di codice si esegue, è utile per avere una conoscenza del [indicazioni per la progettazione di librerie .NET](../../standard/design-guidelines/index.md).</span><span class="sxs-lookup"><span data-stu-id="c732e-120">Regardless of the kind of F# coding you are doing, it is valuable to have a working knowledge of the [.NET Library Design Guidelines](../../standard/design-guidelines/index.md).</span></span> <span data-ttu-id="c732e-121">Maggior parte degli altri F# , i programmatori di .NET verranno avere familiarità con queste linee guida e prevede che il codice .NET di conformarsi a essi.</span><span class="sxs-lookup"><span data-stu-id="c732e-121">Most other F# and .NET programmers will be familiar with these guidelines, and expect .NET code to conform to them.</span></span>

<span data-ttu-id="c732e-122">Linee guida di progettazione di .NET della libreria fornite indicazioni generali sulla denominazione, la progettazione di classi e interfacce, progettazione di membri (proprietà, metodi, eventi, e così via) e altro ancora e sono un utile punto prima di riferimento per un'ampia gamma di materiale sussidiario di progettazione.</span><span class="sxs-lookup"><span data-stu-id="c732e-122">The .NET Library Design Guidelines provide general guidance regarding naming, designing classes and interfaces, member design (properties, methods, events, etc.) and more, and are a useful first point of reference for a variety of design guidance.</span></span>

### <a name="add-xml-documentation-comments-to-your-code"></a><span data-ttu-id="c732e-123">Aggiungere commenti in formato documentazione XML nel codice</span><span class="sxs-lookup"><span data-stu-id="c732e-123">Add XML documentation comments to your code</span></span>

<span data-ttu-id="c732e-124">Documentazione XML nelle API pubbliche assicurarsi che gli utenti possono ottenere eccezionali Intellisense e informazioni rapide durante l'utilizzo di questi tipi e membri e Abilita creazione di documentazione dei file per la libreria.</span><span class="sxs-lookup"><span data-stu-id="c732e-124">XML documentation on public APIs ensure that users can get great Intellisense and Quickinfo when using these types and members, and enable building documentation files for the library.</span></span> <span data-ttu-id="c732e-125">Vedere le [della documentazione XML](../language-reference/xml-documentation.md) sui vari tag xml che può essere usato per altri markup all'interno di commenti xmldoc.</span><span class="sxs-lookup"><span data-stu-id="c732e-125">See the [XML Documentation](../language-reference/xml-documentation.md) about various xml tags that can be used for additional markup within xmldoc comments.</span></span>

```fsharp
/// A class for representing (x,y) coordinates
type Point =

    /// Computes the distance between this point and another
    member DistanceTo : otherPoint:Point -> float
```

<span data-ttu-id="c732e-126">È possibile usare entrambi la versione abbreviata commenti in formato XML (`/// comment`), o commenti in formato XML standard (`///<summary>comment</summary>`).</span><span class="sxs-lookup"><span data-stu-id="c732e-126">You can use either the short form XML comments (`/// comment`), or standard XML comments (`///<summary>comment</summary>`).</span></span>

### <a name="consider-using-explicit-signature-files-fsi-for-stable-library-and-component-apis"></a><span data-ttu-id="c732e-127">È consigliabile usare file di firma esplicita (. fsi) per la libreria stabile e componente API</span><span class="sxs-lookup"><span data-stu-id="c732e-127">Consider using explicit signature files (.fsi) for stable library and component APIs</span></span>

<span data-ttu-id="c732e-128">Usa le firme esplicita ai file in un F# libreria fornisce un riepilogo dell'API pubblica, che consente di assicurarsi di conoscere il pubblico completo superficie della libreria, nonché offre una netta separazione tra documentazione pubblica e interno dettagli di implementazione.</span><span class="sxs-lookup"><span data-stu-id="c732e-128">Using explicit signatures files in an F# library provides a succinct summary of public API, which both helps to ensure that you know the full public surface of your library, as well as provides a clean separation between public documentation and internal implementation details.</span></span> <span data-ttu-id="c732e-129">Si noti che i file delle firme aggiungono attrito per modificare l'API pubblica, tramite la richiesta di modifiche da apportare nei file di implementazione e la firma.</span><span class="sxs-lookup"><span data-stu-id="c732e-129">Note that signature files add friction to changing the public API, by requiring changes to be made in both the implementation and signature files.</span></span> <span data-ttu-id="c732e-130">Di conseguenza, i file di firma in genere solo da introdurre quando un'API ha diventano solidificata e non è più previsto cambi in modo significativo.</span><span class="sxs-lookup"><span data-stu-id="c732e-130">As a result, signature files should typically only be introduced when an API has become solidified and is no longer expected to change significantly.</span></span>

### <a name="always-follow-best-practices-for-using-strings-in-net"></a><span data-ttu-id="c732e-131">Seguire sempre le procedure consigliate per l'uso delle stringhe in .NET</span><span class="sxs-lookup"><span data-stu-id="c732e-131">Always follow best practices for using strings in .NET</span></span>

<span data-ttu-id="c732e-132">Seguire [procedure consigliate per l'uso di stringhe in .NET](../../standard/base-types/best-practices-strings.md) indicazioni.</span><span class="sxs-lookup"><span data-stu-id="c732e-132">Follow [Best Practices for Using Strings in .NET](../../standard/base-types/best-practices-strings.md) guidance.</span></span> <span data-ttu-id="c732e-133">In particolare, indicare sempre esplicitamente *finalità relative alla lingua* nella conversione e confronto di stringhe (dove applicabile).</span><span class="sxs-lookup"><span data-stu-id="c732e-133">In particular, always explicitly state *cultural intent* in the conversion and comparison of strings (where applicable).</span></span>

## <a name="guidelines-for-f-facing-libraries"></a><span data-ttu-id="c732e-134">Linee guida per F#-con le librerie di connessione</span><span class="sxs-lookup"><span data-stu-id="c732e-134">Guidelines for F#-facing libraries</span></span>

<span data-ttu-id="c732e-135">In questa sezione vengono offerti suggerimenti per lo sviluppo di pubbliche F#-rivolta alle librerie. vale a dire, le librerie che espone le API pubbliche che devono essere utilizzati da F# gli sviluppatori.</span><span class="sxs-lookup"><span data-stu-id="c732e-135">This section presents recommendations for developing public F#-facing libraries; that is, libraries exposing public APIs that are intended to be consumed by F# developers.</span></span> <span data-ttu-id="c732e-136">Esistono diverse indicazioni di progettazione di librerie applicabile in particolare per F#.</span><span class="sxs-lookup"><span data-stu-id="c732e-136">There are a variety of library-design recommendations applicable specifically to F#.</span></span> <span data-ttu-id="c732e-137">In assenza di indicazioni specifiche che seguono, linee guida di progettazione di .NET della libreria sono le indicazioni di fallback.</span><span class="sxs-lookup"><span data-stu-id="c732e-137">In the absence of the specific recommendations that follow, the .NET Library Design Guidelines are the fallback guidance.</span></span>

### <a name="naming-conventions"></a><span data-ttu-id="c732e-138">Convenzioni di denominazione</span><span class="sxs-lookup"><span data-stu-id="c732e-138">Naming conventions</span></span>

#### <a name="use-net-naming-and-capitalization-conventions"></a><span data-ttu-id="c732e-139">Usare le convenzioni di denominazione e l'uso delle maiuscole .NET</span><span class="sxs-lookup"><span data-stu-id="c732e-139">Use .NET naming and capitalization conventions</span></span>

<span data-ttu-id="c732e-140">La tabella seguente rispetta le convenzioni di denominazione e l'uso delle maiuscole .NET.</span><span class="sxs-lookup"><span data-stu-id="c732e-140">The following table follows .NET naming and capitalization conventions.</span></span> <span data-ttu-id="c732e-141">Esistono piccole aggiunte per includere anche F# costrutti di.</span><span class="sxs-lookup"><span data-stu-id="c732e-141">There are small additions to also include F# constructs.</span></span>

| <span data-ttu-id="c732e-142">Costrutto</span><span class="sxs-lookup"><span data-stu-id="c732e-142">Construct</span></span> | <span data-ttu-id="c732e-143">Case</span><span class="sxs-lookup"><span data-stu-id="c732e-143">Case</span></span> | <span data-ttu-id="c732e-144">Parte</span><span class="sxs-lookup"><span data-stu-id="c732e-144">Part</span></span> | <span data-ttu-id="c732e-145">Esempi</span><span class="sxs-lookup"><span data-stu-id="c732e-145">Examples</span></span> | <span data-ttu-id="c732e-146">Note</span><span class="sxs-lookup"><span data-stu-id="c732e-146">Notes</span></span> |
|-----------|------|------|----------|-------|
| <span data-ttu-id="c732e-147">Tipi concreti</span><span class="sxs-lookup"><span data-stu-id="c732e-147">Concrete types</span></span> | <span data-ttu-id="c732e-148">PascalCase</span><span class="sxs-lookup"><span data-stu-id="c732e-148">PascalCase</span></span> | <span data-ttu-id="c732e-149">Sostantivo / aggettivali</span><span class="sxs-lookup"><span data-stu-id="c732e-149">Noun/ adjective</span></span> | <span data-ttu-id="c732e-150">Elenco, Double, complesso</span><span class="sxs-lookup"><span data-stu-id="c732e-150">List, Double, Complex</span></span> | <span data-ttu-id="c732e-151">Tipi concreti sono strutture, classi, enumerazioni, delegati, record e unioni.</span><span class="sxs-lookup"><span data-stu-id="c732e-151">Concrete types are structs, classes, enumerations, delegates, records, and unions.</span></span> <span data-ttu-id="c732e-152">Anche se i nomi dei tipi sono in genere in minuscoli in OCaml, F# ha adottato lo schema di denominazione .NET per i tipi.</span><span class="sxs-lookup"><span data-stu-id="c732e-152">Though type names are traditionally lowercase in OCaml, F# has adopted the .NET naming scheme for types.</span></span>
| <span data-ttu-id="c732e-153">DLL</span><span class="sxs-lookup"><span data-stu-id="c732e-153">DLLs</span></span>           | <span data-ttu-id="c732e-154">PascalCase</span><span class="sxs-lookup"><span data-stu-id="c732e-154">PascalCase</span></span> |                 | <span data-ttu-id="c732e-155">Fabrikam.Core.dll</span><span class="sxs-lookup"><span data-stu-id="c732e-155">Fabrikam.Core.dll</span></span> |  |
| <span data-ttu-id="c732e-156">Tag di unione</span><span class="sxs-lookup"><span data-stu-id="c732e-156">Union tags</span></span>     | <span data-ttu-id="c732e-157">PascalCase</span><span class="sxs-lookup"><span data-stu-id="c732e-157">PascalCase</span></span> | <span data-ttu-id="c732e-158">Sostantivo</span><span class="sxs-lookup"><span data-stu-id="c732e-158">Noun</span></span> | <span data-ttu-id="c732e-159">Alcuni casi, aggiungere, operazione riuscita</span><span class="sxs-lookup"><span data-stu-id="c732e-159">Some, Add, Success</span></span> | <span data-ttu-id="c732e-160">Non usare un prefisso nelle API pubbliche.</span><span class="sxs-lookup"><span data-stu-id="c732e-160">Do not use a prefix in public APIs.</span></span> <span data-ttu-id="c732e-161">Se lo si desidera usare un prefisso quando interni, ad esempio ' digitare team = TAlpha</span><span class="sxs-lookup"><span data-stu-id="c732e-161">Optionally use a prefix when internal, such as \`type Teams = TAlpha</span></span> | <span data-ttu-id="c732e-162">TBeta</span><span class="sxs-lookup"><span data-stu-id="c732e-162">TBeta</span></span> | <span data-ttu-id="c732e-163">TDelta.'</span><span class="sxs-lookup"><span data-stu-id="c732e-163">TDelta.\`</span></span> |
| <span data-ttu-id="c732e-164">event</span><span class="sxs-lookup"><span data-stu-id="c732e-164">Event</span></span>          | <span data-ttu-id="c732e-165">PascalCase</span><span class="sxs-lookup"><span data-stu-id="c732e-165">PascalCase</span></span> | <span data-ttu-id="c732e-166">Verbo</span><span class="sxs-lookup"><span data-stu-id="c732e-166">Verb</span></span> | <span data-ttu-id="c732e-167">ValueChanged / ValueChanging</span><span class="sxs-lookup"><span data-stu-id="c732e-167">ValueChanged / ValueChanging</span></span> |  |
| <span data-ttu-id="c732e-168">Eccezioni</span><span class="sxs-lookup"><span data-stu-id="c732e-168">Exceptions</span></span>     | <span data-ttu-id="c732e-169">PascalCase</span><span class="sxs-lookup"><span data-stu-id="c732e-169">PascalCase</span></span> |      | <span data-ttu-id="c732e-170">WebException</span><span class="sxs-lookup"><span data-stu-id="c732e-170">WebException</span></span> | <span data-ttu-id="c732e-171">Nome deve terminare con "Exception".</span><span class="sxs-lookup"><span data-stu-id="c732e-171">Name should end with “Exception”.</span></span> |
| <span data-ttu-id="c732e-172">Campo</span><span class="sxs-lookup"><span data-stu-id="c732e-172">Field</span></span>          | <span data-ttu-id="c732e-173">PascalCase</span><span class="sxs-lookup"><span data-stu-id="c732e-173">PascalCase</span></span> | <span data-ttu-id="c732e-174">Sostantivo</span><span class="sxs-lookup"><span data-stu-id="c732e-174">Noun</span></span> | <span data-ttu-id="c732e-175">CurrentName</span><span class="sxs-lookup"><span data-stu-id="c732e-175">CurrentName</span></span>  | |
| <span data-ttu-id="c732e-176">Tipi interfaccia</span><span class="sxs-lookup"><span data-stu-id="c732e-176">Interface types</span></span> |  <span data-ttu-id="c732e-177">PascalCase</span><span class="sxs-lookup"><span data-stu-id="c732e-177">PascalCase</span></span> | <span data-ttu-id="c732e-178">Sostantivo / aggettivali</span><span class="sxs-lookup"><span data-stu-id="c732e-178">Noun/ adjective</span></span> | <span data-ttu-id="c732e-179">IDisposable</span><span class="sxs-lookup"><span data-stu-id="c732e-179">IDisposable</span></span> | <span data-ttu-id="c732e-180">Nome deve iniziare con "I".</span><span class="sxs-lookup"><span data-stu-id="c732e-180">Name should start with “I”.</span></span> |
| <span data-ttu-id="c732e-181">Metodo</span><span class="sxs-lookup"><span data-stu-id="c732e-181">Method</span></span> |  <span data-ttu-id="c732e-182">PascalCase</span><span class="sxs-lookup"><span data-stu-id="c732e-182">PascalCase</span></span> |  <span data-ttu-id="c732e-183">Verbo</span><span class="sxs-lookup"><span data-stu-id="c732e-183">Verb</span></span> | <span data-ttu-id="c732e-184">ToString</span><span class="sxs-lookup"><span data-stu-id="c732e-184">ToString</span></span> | |
| <span data-ttu-id="c732e-185">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="c732e-185">Namespace</span></span> | <span data-ttu-id="c732e-186">PascalCase</span><span class="sxs-lookup"><span data-stu-id="c732e-186">PascalCase</span></span> | | <span data-ttu-id="c732e-187">FSharp</span><span class="sxs-lookup"><span data-stu-id="c732e-187">Microsoft.FSharp.Core</span></span> | <span data-ttu-id="c732e-188">In genere usano `<Organization>.<Technology>[.<Subnamespace>]`, eliminare anche se l'organizzazione se la tecnologia è indipendente dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c732e-188">Generally use `<Organization>.<Technology>[.<Subnamespace>]`, though drop the organization if the technology is independent of organization.</span></span> |
| <span data-ttu-id="c732e-189">Parametri</span><span class="sxs-lookup"><span data-stu-id="c732e-189">Parameters</span></span> | <span data-ttu-id="c732e-190">camelCase</span><span class="sxs-lookup"><span data-stu-id="c732e-190">camelCase</span></span> | <span data-ttu-id="c732e-191">Sostantivo</span><span class="sxs-lookup"><span data-stu-id="c732e-191">Noun</span></span> |  <span data-ttu-id="c732e-192">typeName, trasformazione, intervallo</span><span class="sxs-lookup"><span data-stu-id="c732e-192">typeName, transform, range</span></span> | |
| <span data-ttu-id="c732e-193">lasciare i valori (interni)</span><span class="sxs-lookup"><span data-stu-id="c732e-193">let values (internal)</span></span> | <span data-ttu-id="c732e-194">camelCase o PascalCase</span><span class="sxs-lookup"><span data-stu-id="c732e-194">camelCase or PascalCase</span></span> | <span data-ttu-id="c732e-195">Sostantivo / verbo</span><span class="sxs-lookup"><span data-stu-id="c732e-195">Noun/ verb</span></span> |  <span data-ttu-id="c732e-196">getValue, myTable</span><span class="sxs-lookup"><span data-stu-id="c732e-196">getValue, myTable</span></span> |
| <span data-ttu-id="c732e-197">lasciare i valori (esterno)</span><span class="sxs-lookup"><span data-stu-id="c732e-197">let values (external)</span></span> | <span data-ttu-id="c732e-198">camelCase o PascalCase</span><span class="sxs-lookup"><span data-stu-id="c732e-198">camelCase or PascalCase</span></span> | <span data-ttu-id="c732e-199">Sostantivo/verbo</span><span class="sxs-lookup"><span data-stu-id="c732e-199">Noun/verb</span></span>  | <span data-ttu-id="c732e-200">List. map, Dates.Today</span><span class="sxs-lookup"><span data-stu-id="c732e-200">List.map, Dates.Today</span></span> | <span data-ttu-id="c732e-201">i valori di associazione let sono pubblici spesso quando si seguono i modelli di progettazione funzionali tradizionale.</span><span class="sxs-lookup"><span data-stu-id="c732e-201">let-bound values are often public when following traditional functional design patterns.</span></span> <span data-ttu-id="c732e-202">Tuttavia, in genere usano la notazione Pascal quando l'identificatore può essere utilizzato da altri linguaggi .NET.</span><span class="sxs-lookup"><span data-stu-id="c732e-202">However, generally use PascalCase when the identifier can be used from other .NET languages.</span></span> |
| <span data-ttu-id="c732e-203">Proprietà</span><span class="sxs-lookup"><span data-stu-id="c732e-203">Property</span></span>  | <span data-ttu-id="c732e-204">PascalCase</span><span class="sxs-lookup"><span data-stu-id="c732e-204">PascalCase</span></span>  | <span data-ttu-id="c732e-205">Sostantivo / aggettivali</span><span class="sxs-lookup"><span data-stu-id="c732e-205">Noun/ adjective</span></span>  | <span data-ttu-id="c732e-206">IsEndOfFile, colore di sfondo</span><span class="sxs-lookup"><span data-stu-id="c732e-206">IsEndOfFile, BackColor</span></span>  | <span data-ttu-id="c732e-207">Le proprietà booleane in genere l'utilizzo è e può e deve essere affermativa perché, come illustrato IsEndOfFile, non IsNotEndOfFile.</span><span class="sxs-lookup"><span data-stu-id="c732e-207">Boolean properties generally use Is and Can and should be affirmative, as in IsEndOfFile, not IsNotEndOfFile.</span></span>

#### <a name="avoid-abbreviations"></a><span data-ttu-id="c732e-208">Evitare le abbreviazioni</span><span class="sxs-lookup"><span data-stu-id="c732e-208">Avoid abbreviations</span></span>

<span data-ttu-id="c732e-209">Linee guida di .NET sconsiglia l'uso di abbreviazioni (ad esempio, "utilizzare `OnButtonClick` anziché `OnBtnClick`").</span><span class="sxs-lookup"><span data-stu-id="c732e-209">The .NET guidelines discourage the use of abbreviations (for example, “use `OnButtonClick` rather than `OnBtnClick`”).</span></span> <span data-ttu-id="c732e-210">Le abbreviazioni comuni, ad esempio `Async` per "Asincrono", è consentito.</span><span class="sxs-lookup"><span data-stu-id="c732e-210">Common abbreviations, such as `Async` for “Asynchronous”, are tolerated.</span></span> <span data-ttu-id="c732e-211">Questa indicazione viene ignorata in alcuni casi per la programmazione funzionale; ad esempio, `List.iter` Usa un'abbreviazione per "eseguire l'iterazione".</span><span class="sxs-lookup"><span data-stu-id="c732e-211">This guideline is sometimes ignored for functional programming; for example, `List.iter` uses an abbreviation for “iterate”.</span></span> <span data-ttu-id="c732e-212">Per questo motivo, uso di abbreviazioni tende a essere tollerati da un livello superiore in F#- a -F# programmazione, ma comunque generalmente devono essere evitati in Progettazione del componente pubblico.</span><span class="sxs-lookup"><span data-stu-id="c732e-212">For this reason, using abbreviations tends to be tolerated to a greater degree in F#-to-F# programming, but should still generally be avoided in public component design.</span></span>

#### <a name="avoid-casing-name-collisions"></a><span data-ttu-id="c732e-213">Evitare conflitti di nomi di maiuscole e minuscole</span><span class="sxs-lookup"><span data-stu-id="c732e-213">Avoid casing name collisions</span></span>

<span data-ttu-id="c732e-214">Linee guida di .NET si supponga che maiuscole e minuscole da solo non può essere utilizzata per distinguere i conflitti di nomi, poiché alcune lingue di client (ad esempio, Visual Basic) sono tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="c732e-214">The .NET guidelines say that casing alone cannot be used to disambiguate name collisions, since some client languages (for example, Visual Basic) are case-insensitive.</span></span>

#### <a name="use-acronyms-where-appropriate"></a><span data-ttu-id="c732e-215">Usare gli acronimi dove appropriato</span><span class="sxs-lookup"><span data-stu-id="c732e-215">Use acronyms where appropriate</span></span>

<span data-ttu-id="c732e-216">Gli acronimi quali XML non sono abbreviazioni e vengono ampiamente usati nelle librerie .NET in formato minuscolo (Xml).</span><span class="sxs-lookup"><span data-stu-id="c732e-216">Acronyms such as XML are not abbreviations and are widely used in .NET libraries in uncapitalized form (Xml).</span></span> <span data-ttu-id="c732e-217">Devono essere usati solo acronimi ben conosciuti e ampiamente riconosciuti.</span><span class="sxs-lookup"><span data-stu-id="c732e-217">Only well-known, widely recognized acronyms should be used.</span></span>

#### <a name="use-pascalcase-for-generic-parameter-names"></a><span data-ttu-id="c732e-218">Usano la notazione Pascal per i nomi di parametro generico</span><span class="sxs-lookup"><span data-stu-id="c732e-218">Use PascalCase for generic parameter names</span></span>

<span data-ttu-id="c732e-219">Usano la notazione Pascal per i nomi dei parametri generici nelle API pubbliche, inclusi per F#-con le librerie di connessione.</span><span class="sxs-lookup"><span data-stu-id="c732e-219">Do use PascalCase for generic parameter names in public APIs, including for F#-facing libraries.</span></span> <span data-ttu-id="c732e-220">In particolare, usare nomi quale `T`, `U`, `T1`, `T2` arbitrari parametri generici e se nomi specifici siano significativi, quindi F#-librerie affiancate utilizzano nomi quale `Key`, `Value`, `Arg` (ma non, ad esempio, `TKey`).</span><span class="sxs-lookup"><span data-stu-id="c732e-220">In particular, use names like `T`, `U`, `T1`, `T2` for arbitrary generic parameters, and when specific names make sense, then for F#-facing libraries use names like `Key`, `Value`, `Arg` (but not for example, `TKey`).</span></span>

#### <a name="use-either-pascalcase-or-camelcase-for-public-functions-and-values-in-f-modules"></a><span data-ttu-id="c732e-221">Usare PascalCase o camelCase per le funzioni pubbliche e i valori in F# i moduli</span><span class="sxs-lookup"><span data-stu-id="c732e-221">Use either PascalCase or camelCase for public functions and values in F# modules</span></span>

<span data-ttu-id="c732e-222">camelCase viene usato per le funzioni pubbliche che sono progettate per essere usato non qualificato (ad esempio, `invalidArg`) e per le "funzioni di raccolta standard" (ad esempio, List. Map).</span><span class="sxs-lookup"><span data-stu-id="c732e-222">camelCase is used for public functions that are designed to be used unqualified (for example, `invalidArg`), and for the “standard collection functions” (for example, List.map).</span></span> <span data-ttu-id="c732e-223">In entrambi i casi, i nomi delle funzioni funzionano in modo simile le parole chiave nel linguaggio.</span><span class="sxs-lookup"><span data-stu-id="c732e-223">In both these cases, the function names act much like keywords in the language.</span></span>

### <a name="object-type-and-module-design"></a><span data-ttu-id="c732e-224">Oggetto, tipo e modulo di progettazione</span><span class="sxs-lookup"><span data-stu-id="c732e-224">Object, Type, and Module design</span></span>

#### <a name="use-namespaces-or-modules-to-contain-your-types-and-modules"></a><span data-ttu-id="c732e-225">Usare gli spazi dei nomi o moduli per includere i tipi e i moduli</span><span class="sxs-lookup"><span data-stu-id="c732e-225">Use namespaces or modules to contain your types and modules</span></span>

<span data-ttu-id="c732e-226">Ogni F# file in un componente deve iniziare con una dichiarazione dello spazio dei nomi o una dichiarazione di modulo.</span><span class="sxs-lookup"><span data-stu-id="c732e-226">Each F# file in a component should begin with either a namespace declaration or a module declaration.</span></span>

```fsharp
namespace Fabrikam.BasicOperationsAndTypes

type ObjectType1() =
    ...

type ObjectType2() =
     ...

module CommonOperations =
    ...
```

<span data-ttu-id="c732e-227">oppure</span><span class="sxs-lookup"><span data-stu-id="c732e-227">or</span></span>

```fsharp
module Fabrikam.BasicOperationsAndTypes

type ObjectType1() =
    ...

type ObjectType2() =
    ...

module CommonOperations =
    ...
```

<span data-ttu-id="c732e-228">Come indicato di seguito sono riportate le differenze tra l'uso di moduli e spazi dei nomi per organizzare il codice di primo livello:</span><span class="sxs-lookup"><span data-stu-id="c732e-228">The differences between using modules and namespaces to organize code at the top level are as follows:</span></span>

* <span data-ttu-id="c732e-229">Gli spazi dei nomi possono estendersi su più file</span><span class="sxs-lookup"><span data-stu-id="c732e-229">Namespaces can span multiple files</span></span>
* <span data-ttu-id="c732e-230">Non può contenere spazi dei nomi F# funzioni a meno che non sono all'interno di un modulo interno</span><span class="sxs-lookup"><span data-stu-id="c732e-230">Namespaces cannot contain F# functions unless they are within an inner module</span></span>
* <span data-ttu-id="c732e-231">Il codice di qualsiasi modulo specificato deve essere contenuto in un singolo file</span><span class="sxs-lookup"><span data-stu-id="c732e-231">The code for any given module must be contained within a single file</span></span>
* <span data-ttu-id="c732e-232">Moduli di primo livello possono contenere F# funzioni senza la necessità di un modulo interno</span><span class="sxs-lookup"><span data-stu-id="c732e-232">Top-level modules can contain F# functions without the need for an inner module</span></span>

<span data-ttu-id="c732e-233">La scelta tra uno spazio dei nomi di primo livello o un modulo riguarda la forma compilata del codice e pertanto verrà la visualizzazione di altri linguaggi .NET devono API infine essere utilizzata all'esterno di F# codice.</span><span class="sxs-lookup"><span data-stu-id="c732e-233">The choice between a top-level namespace or module affects the compiled form of the code, and thus will affect the view from other .NET languages should your API eventually be consumed outside of F# code.</span></span>

#### <a name="use-methods-and-properties-for-operations-intrinsic-to-object-types"></a><span data-ttu-id="c732e-234">Usare i metodi e proprietà per le operazioni intrinseche per i tipi di oggetto</span><span class="sxs-lookup"><span data-stu-id="c732e-234">Use methods and properties for operations intrinsic to object types</span></span>

<span data-ttu-id="c732e-235">Quando si lavora con gli oggetti, è consigliabile assicurarsi che possa essere utilizzata funzionalità viene implementata come metodi e proprietà per quel tipo.</span><span class="sxs-lookup"><span data-stu-id="c732e-235">When working with objects, it is best to ensure that consumable functionality is implemented as methods and properties on that type.</span></span>

```fsharp
type HardwareDevice() =

    member this.ID = ...

    member this.SupportedProtocols = ...

type HashTable<'Key,'Value>(comparer: IEqualityComparer<'Key>) =

    member this.Add(key, value) = ...

    member this.ContainsKey(key) = ...

    member this.ContainsValue(value) = ...
```

<span data-ttu-id="c732e-236">La maggior parte delle funzionalità per un determinato membro non debba necessariamente essere implementata in tale membro, ma deve essere la parte di tale funzionalità può essere utilizzata.</span><span class="sxs-lookup"><span data-stu-id="c732e-236">The bulk of functionality for a given member need not necessarily be implemented in that member, but the consumable piece of that functionality should be.</span></span>

#### <a name="use-classes-to-encapsulate-mutable-state"></a><span data-ttu-id="c732e-237">Usare le classi per incapsulare lo stato modificabile</span><span class="sxs-lookup"><span data-stu-id="c732e-237">Use classes to encapsulate mutable state</span></span>

<span data-ttu-id="c732e-238">In F#, questo deve solo essere eseguita in cui che lo stato non è già incapsulato da un altro costrutto di linguaggio, ad esempio una chiusura, l'espressione di sequenza o calcolo asincrono.</span><span class="sxs-lookup"><span data-stu-id="c732e-238">In F#, this only needs to be done where that state is not already encapsulated by another language construct, such as a closure, sequence expression, or asynchronous computation.</span></span>

```fsharp
type Counter() =
    // let-bound values are private in classes.
    let mutable count = 0

    member this.Next() =
        count <- count + 1
        count
```

#### <a name="use-interfaces-to-group-related-operations"></a><span data-ttu-id="c732e-239">Usare le interfacce per raggruppare le operazioni correlate</span><span class="sxs-lookup"><span data-stu-id="c732e-239">Use interfaces to group related operations</span></span>

<span data-ttu-id="c732e-240">Usare i tipi di interfaccia per rappresentare una serie di operazioni.</span><span class="sxs-lookup"><span data-stu-id="c732e-240">Use interface types to represent a set of operations.</span></span> <span data-ttu-id="c732e-241">Ciò è preferibile ad altre opzioni, ad esempio tuple di funzioni o i record delle funzioni.</span><span class="sxs-lookup"><span data-stu-id="c732e-241">This is preferred to other options, such as tuples of functions or records of functions.</span></span>

```fsharp
type Serializer =
    abstract Serialize<'T> : preserveRefEq: bool -> value: 'T -> string
    abstract Deserialize<'T> : preserveRefEq: bool -> pickle: string -> 'T
```

<span data-ttu-id="c732e-242">In alternativa a:</span><span class="sxs-lookup"><span data-stu-id="c732e-242">In preference to:</span></span>

```fsharp
type Serializer<'T> = {
    Serialize : bool -> 'T -> string
    Deserialize : bool -> string -> 'T
}
```

<span data-ttu-id="c732e-243">Le interfacce sono concetti di prima classe in .NET, che è possibile usare per ottenere la cosa Funtori normalmente verrebbero visualizzate.</span><span class="sxs-lookup"><span data-stu-id="c732e-243">Interfaces are first-class concepts in .NET, which you can use to achieve what Functors would normally give you.</span></span> <span data-ttu-id="c732e-244">Inoltre, possono essere utilizzati per codificare tipi esistenziali nel programma, che non può essere i record delle funzioni.</span><span class="sxs-lookup"><span data-stu-id="c732e-244">Additionally, they can be used to encode existential types into your program, which records of functions cannot.</span></span>

#### <a name="use-a-module-to-group-functions-which-act-on-collections"></a><span data-ttu-id="c732e-245">Usare un modulo per le funzioni di gruppo che agiscono sulle raccolte</span><span class="sxs-lookup"><span data-stu-id="c732e-245">Use a module to group functions which act on collections</span></span>

<span data-ttu-id="c732e-246">Quando si definisce un tipo di raccolta, si consiglia di fornire un set standard di operazioni, ad esempio `CollectionType.map` e `CollectionType.iter`) per i nuovi tipi di raccolta.</span><span class="sxs-lookup"><span data-stu-id="c732e-246">When you define a collection type, consider providing a standard set of operations like `CollectionType.map` and `CollectionType.iter`) for new collection types.</span></span>

```fsharp
module CollectionType =
    let map f c =
        ...
    let iter f c =
        ...
```

<span data-ttu-id="c732e-247">Se si include un modulo di questo tipo, seguire le convenzioni di denominazione standard per le funzioni disponibili in FSharp. Core.</span><span class="sxs-lookup"><span data-stu-id="c732e-247">If you include such a module, follow the standard naming conventions for functions found in FSharp.Core.</span></span>

#### <a name="use-a-module-to-group-functions-for-common-canonical-functions-especially-in-math-and-dsl-libraries"></a><span data-ttu-id="c732e-248">Usare un modulo per le funzioni di gruppo per le funzioni comuni, canoniche, soprattutto in matematica e le librerie DSL</span><span class="sxs-lookup"><span data-stu-id="c732e-248">Use a module to group functions for common, canonical functions, especially in math and DSL libraries</span></span>

<span data-ttu-id="c732e-249">Ad esempio, `Microsoft.FSharp.Core.Operators` aperti automaticamente: raccolta di funzioni di primo livello (ad esempio `abs` e `sin`) fornito da FSharp.</span><span class="sxs-lookup"><span data-stu-id="c732e-249">For example, `Microsoft.FSharp.Core.Operators` is an automatically opened collection of top-level functions (like `abs` and `sin`) provided by FSharp.Core.dll.</span></span>

<span data-ttu-id="c732e-250">Analogamente, una raccolta delle statistiche potrebbe includere un modulo con le funzioni `erf` e `erfc`, in cui questo modulo è progettato per essere automaticamente o in modo esplicito aperto.</span><span class="sxs-lookup"><span data-stu-id="c732e-250">Likewise, a statistics library might include a module with functions `erf` and `erfc`, where this module is designed to be explicitly or automatically opened.</span></span>

#### <a name="consider-using-requirequalifiedaccess-and-carefully-apply-autoopen-attributes"></a><span data-ttu-id="c732e-251">È consigliabile usare RequireQualifiedAccess e attentamente applicare attributi AutoOpen</span><span class="sxs-lookup"><span data-stu-id="c732e-251">Consider using RequireQualifiedAccess and carefully apply AutoOpen attributes</span></span>

<span data-ttu-id="c732e-252">Aggiunta di `[<RequireQualifiedAccess>]` attributo a un modulo indica che il modulo non può essere aperta e che i riferimenti agli elementi del modulo richiedono esplicita completo di accesso.</span><span class="sxs-lookup"><span data-stu-id="c732e-252">Adding the `[<RequireQualifiedAccess>]` attribute to a module indicates that the module may not be opened and that references to the elements of the module require explicit qualified access.</span></span> <span data-ttu-id="c732e-253">Ad esempio, il `Microsoft.FSharp.Collections.List` modulo dispone di questo attributo.</span><span class="sxs-lookup"><span data-stu-id="c732e-253">For example, the `Microsoft.FSharp.Collections.List` module has this attribute.</span></span>

<span data-ttu-id="c732e-254">Ciò è utile quando le funzioni e i valori nel modulo hanno nomi che possono entrare in conflitto con i nomi di altri moduli.</span><span class="sxs-lookup"><span data-stu-id="c732e-254">This is useful when functions and values in the module have names that are likely to conflict with names in other modules.</span></span> <span data-ttu-id="c732e-255">Richiedere l'accesso completo può aumentare notevolmente la manutenibilità a lungo termine e capacità evolutiva di una libreria.</span><span class="sxs-lookup"><span data-stu-id="c732e-255">Requiring qualified access can greatly increase the long-term maintainability and evolvability of a library.</span></span>

<span data-ttu-id="c732e-256">Aggiunta di `[<AutoOpen>]` attributo su un modulo, verrà aperto il modulo quando viene aperto lo spazio dei nomi che lo contiene.</span><span class="sxs-lookup"><span data-stu-id="c732e-256">Adding the `[<AutoOpen>]` attribute to a module means the module will be opened when the containing namespace is opened.</span></span> <span data-ttu-id="c732e-257">Il `[<AutoOpen>]` attributo può anche essere applicato a un assembly per indicare un modulo che viene aperto automaticamente quando viene fatto riferimento all'assembly.</span><span class="sxs-lookup"><span data-stu-id="c732e-257">The `[<AutoOpen>]` attribute may also be applied to an assembly to indicate a module that is automatically opened when the assembly is referenced.</span></span>

<span data-ttu-id="c732e-258">Ad esempio, una raccolta di statistiche **MathsHeaven.Statistics** potrebbe contenere una `module MathsHeaven.Statistics.Operators` contenenti funzioni `erf` e `erfc`.</span><span class="sxs-lookup"><span data-stu-id="c732e-258">For example, a statistics library **MathsHeaven.Statistics** might contain a `module MathsHeaven.Statistics.Operators` containing functions `erf` and `erfc`.</span></span> <span data-ttu-id="c732e-259">È ragionevole contrassegnare questo modulo come `[<AutoOpen>]`.</span><span class="sxs-lookup"><span data-stu-id="c732e-259">It is reasonable to mark this module as `[<AutoOpen>]`.</span></span> <span data-ttu-id="c732e-260">Ciò significa `open MathsHeaven.Statistics` verrà anche aprire questo modulo e visualizzare i nomi `erf` e `erfc` nell'ambito.</span><span class="sxs-lookup"><span data-stu-id="c732e-260">This means `open MathsHeaven.Statistics` will also open this module and bring the names `erf` and `erfc` into scope.</span></span> <span data-ttu-id="c732e-261">Usa un'altra buona `[<AutoOpen>]` è per i moduli contenenti i metodi di estensione.</span><span class="sxs-lookup"><span data-stu-id="c732e-261">Another good use of `[<AutoOpen>]` is for modules containing extension methods.</span></span>

<span data-ttu-id="c732e-262">Utilizzo eccessivo di `[<AutoOpen>]` lead inquinato gli spazi dei nomi e l'attributo deve essere utilizzata con cautela.</span><span class="sxs-lookup"><span data-stu-id="c732e-262">Overuse of `[<AutoOpen>]` leads to polluted namespaces, and the attribute should be used with care.</span></span> <span data-ttu-id="c732e-263">Per le librerie specifiche in domini specifici, uso attento di `[<AutoOpen>]` può portare a una migliore utilizzabilità.</span><span class="sxs-lookup"><span data-stu-id="c732e-263">For specific libraries in specific domains, judicious use of `[<AutoOpen>]` can lead to better usability.</span></span>

#### <a name="consider-defining-operator-members-on-classes-where-using-well-known-operators-is-appropriate"></a><span data-ttu-id="c732e-264">Si consiglia di definire i membri di operatore sulle classi in cui è appropriato usare operatori noti</span><span class="sxs-lookup"><span data-stu-id="c732e-264">Consider defining operator members on classes where using well-known operators is appropriate</span></span>

<span data-ttu-id="c732e-265">In alcuni casi classi vengono utilizzate per la modellazione matematici costrutti come vettori.</span><span class="sxs-lookup"><span data-stu-id="c732e-265">Sometimes classes are used to model mathematical constructs such as Vectors.</span></span> <span data-ttu-id="c732e-266">Quando il dominio in fase di modellazione include operatori noti, vengono definiti come membri intrinseci per la classe è utile.</span><span class="sxs-lookup"><span data-stu-id="c732e-266">When the domain being modeled has well-known operators, defining them as members intrinsic to the class is helpful.</span></span>

```fsharp
type Vector(x:float) =

    member v.X = x

    static member (*) (vector:Vector, scalar:float) = Vector(vector.X * scalar)

    static member (+) (vector1:Vector, vector2:Vector) = Vector(vector1.X + vector2.X)

let v = Vector(5.0)

let u = v * 10.0
```

<span data-ttu-id="c732e-267">Questo materiale sussidiario corrisponde alle linee guida generali di .NET per questi tipi.</span><span class="sxs-lookup"><span data-stu-id="c732e-267">This guidance corresponds to general .NET guidance for these types.</span></span> <span data-ttu-id="c732e-268">Tuttavia, può essere inoltre importante in F# codifica poiché in questo modo questi tipi da utilizzare in combinazione con F# funzioni e metodi con vincoli di membro, ad esempio List. sumBy.</span><span class="sxs-lookup"><span data-stu-id="c732e-268">However, it can be additionally important in F# coding as this allows these types to be used in conjunction with F# functions and methods with member constraints, such as List.sumBy.</span></span>

#### <a name="consider-using-compiledname-to-provide-a-net-friendly-name-for-other-net-language-consumers"></a><span data-ttu-id="c732e-269">È consigliabile usare CompiledName per fornire una. Nome descrittivo del NET per altri consumer di linguaggio .NET</span><span class="sxs-lookup"><span data-stu-id="c732e-269">Consider using CompiledName to provide a .NET-friendly name for other .NET language consumers</span></span>

<span data-ttu-id="c732e-270">In alcuni casi si potrebbe voler assegnare un nome in uno stile per F# consumer (ad esempio un membro statico in caratteri minuscoli in modo che venga visualizzato come se fosse una funzione associata al modulo), ma hanno uno stile diverso per il nome quando viene compilato in un assembly.</span><span class="sxs-lookup"><span data-stu-id="c732e-270">Sometimes you may wish to name something in one style for F# consumers (such as a static member in lower case so that it appears as if it were a module-bound function), but have a different style for the name when it is compiled into an assembly.</span></span> <span data-ttu-id="c732e-271">È possibile usare la `[<CompiledName>]` attributo per fornire uno stile diverso per non F# codice che utilizza l'assembly.</span><span class="sxs-lookup"><span data-stu-id="c732e-271">You can use the `[<CompiledName>]` attribute to provide a different style for non F# code consuming the assembly.</span></span>

```fsharp
type Vector(x:float, y:float) =

    member v.X = x
    member v.Y = y

    [<CompiledName("Create")>]
    static member create x y = Vector (x, y)

let v = Vector.create 5.0 3.0
```

<span data-ttu-id="c732e-272">Usando `[<CompiledName>]`, è possibile usare convenzioni di denominazione .NET per non F# consumer dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="c732e-272">By using `[<CompiledName>]`, you can use .NET naming conventions for non F# consumers of the assembly.</span></span>

#### <a name="use-method-overloading-for-member-functions-if-doing-so-provides-a-simpler-api"></a><span data-ttu-id="c732e-273">Usare metodi (overload) per le funzioni membro, se in questo modo viene fornita un'API più semplice</span><span class="sxs-lookup"><span data-stu-id="c732e-273">Use method overloading for member functions, if doing so provides a simpler API</span></span>

<span data-ttu-id="c732e-274">L'overload di metodo è un potente strumento per la semplificazione di un'API che potrebbe essere necessario eseguire una funzionalità simile, ma con diverse opzioni o argomenti.</span><span class="sxs-lookup"><span data-stu-id="c732e-274">Method overloading is a powerful tool for simplifying an API that may need to perform similar functionality, but with different options or arguments.</span></span>

```fsharp
type Logger() =

    member this.Log(message) =
        ...
    member this.Log(message, retryPolicy) =
        ...
```

<span data-ttu-id="c732e-275">In F#, è più comune per eseguire l'overload di un numero di argomenti anziché i tipi degli argomenti.</span><span class="sxs-lookup"><span data-stu-id="c732e-275">In F#, it is more common to overload on number of arguments rather than types of arguments.</span></span>

#### <a name="hide-the-representations-of-record-and-union-types-if-the-design-of-these-types-is-likely-to-evolve"></a><span data-ttu-id="c732e-276">Se la progettazione di questi tipi è probabile che si evolvono, nascondere le rappresentazioni dei record e i tipi di unione</span><span class="sxs-lookup"><span data-stu-id="c732e-276">Hide the representations of record and union types if the design of these types is likely to evolve</span></span>

<span data-ttu-id="c732e-277">Evitare di rivelare concrete rappresentazioni degli oggetti.</span><span class="sxs-lookup"><span data-stu-id="c732e-277">Avoid revealing concrete representations of objects.</span></span> <span data-ttu-id="c732e-278">Ad esempio, la rappresentazione di concreto <xref:System.DateTime> valori non è stato rivelato dall'API esterno, pubblico di progettazione di librerie di .NET.</span><span class="sxs-lookup"><span data-stu-id="c732e-278">For example, the concrete representation of <xref:System.DateTime> values is not revealed by the external, public API of the .NET library design.</span></span> <span data-ttu-id="c732e-279">In fase di esecuzione, Common Language Runtime sa l'implementazione di commit che verrà usato in tutta l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="c732e-279">At run time, the Common Language Runtime knows the committed implementation that will be used throughout execution.</span></span> <span data-ttu-id="c732e-280">Tuttavia, codice compilato non stesso prelevare le dipendenze alla relativa rappresentazione in concreta.</span><span class="sxs-lookup"><span data-stu-id="c732e-280">However, compiled code doesn't itself pick up dependencies on the concrete representation.</span></span>

#### <a name="avoid-the-use-of-implementation-inheritance-for-extensibility"></a><span data-ttu-id="c732e-281">Evitare l'utilizzo dell'ereditarietà dell'implementazione per l'estensibilità</span><span class="sxs-lookup"><span data-stu-id="c732e-281">Avoid the use of implementation inheritance for extensibility</span></span>

<span data-ttu-id="c732e-282">In F#, viene usato raramente ereditarietà dell'implementazione.</span><span class="sxs-lookup"><span data-stu-id="c732e-282">In F#, implementation inheritance is rarely used.</span></span> <span data-ttu-id="c732e-283">Inoltre, le gerarchie di ereditarietà sono spesso complessi e difficili da modificare quando arrivano nuovi requisiti.</span><span class="sxs-lookup"><span data-stu-id="c732e-283">Furthermore, inheritance hierarchies are often complex and difficult to change when new requirements arrive.</span></span> <span data-ttu-id="c732e-284">Implementazione dell'ereditarietà è ancora presente F# per la compatibilità e rari casi in cui è la soluzione migliore per risolvere un problema, ma tecniche alternative devono essere cercate nel F# programmi durante la progettazione per il polimorfismo, ad esempio di interfaccia implementazione.</span><span class="sxs-lookup"><span data-stu-id="c732e-284">Inheritance implementation still exists in F# for compatibility and rare cases where it is the best solution to a problem, but alternative techniques should be sought in your F# programs when designing for polymorphism, such as interface implementation.</span></span>

### <a name="function-and-member-signatures"></a><span data-ttu-id="c732e-285">Firme di funzione e membro</span><span class="sxs-lookup"><span data-stu-id="c732e-285">Function and member signatures</span></span>

#### <a name="use-tuples-for-return-values-when-returning-a-small-number-of-multiple-unrelated-values"></a><span data-ttu-id="c732e-286">Usare le tuple per i valori restituiti quando viene restituito un numero ridotto di più valori non correlati</span><span class="sxs-lookup"><span data-stu-id="c732e-286">Use tuples for return values when returning a small number of multiple unrelated values</span></span>

<span data-ttu-id="c732e-287">Ecco un buon esempio di uso di una tupla in un tipo restituito:</span><span class="sxs-lookup"><span data-stu-id="c732e-287">Here is a good example of using a tuple in a return type:</span></span>

```fsharp
val divrem : BigInteger -> BigInteger -> BigInteger * BigInteger
```

<span data-ttu-id="c732e-288">Per restituire i tipi che contengono molti componenti, o se i componenti sono correlati a una singola entità identificabili, valutare l'uso di un tipo denominato anziché una tupla.</span><span class="sxs-lookup"><span data-stu-id="c732e-288">For return types containing many components, or where the components are related to a single identifiable entity, consider using a named type instead of a tuple.</span></span>

#### <a name="use-asynct-for-async-programming-at-f-api-boundaries"></a><span data-ttu-id="c732e-289">Uso `Async<T>` per async programming in F# dei limiti delle API</span><span class="sxs-lookup"><span data-stu-id="c732e-289">Use `Async<T>` for async programming at F# API boundaries</span></span>

<span data-ttu-id="c732e-290">Se vi è un'operazione sincrona corrispondente denominata `Operation` che restituisce un `T`, quindi l'operazione asincrona deve essere denominato `AsyncOperation` se il valore restituito `Async<T>` oppure `OperationAsync` se restituisce `Task<T>`.</span><span class="sxs-lookup"><span data-stu-id="c732e-290">If there is a corresponding synchronous operation named `Operation` that returns a `T`, then the async operation should be named `AsyncOperation` if it returns `Async<T>` or `OperationAsync` if it returns `Task<T>`.</span></span> <span data-ttu-id="c732e-291">Per i tipi .NET comunemente utilizzati che espongono i metodi Begin/End, è consigliabile usare `Async.FromBeginEnd` scrivere metodi di estensione come un'interfaccia per fornire i F# modello di programmazione asincroni per le API .NET.</span><span class="sxs-lookup"><span data-stu-id="c732e-291">For commonly used .NET types that expose Begin/End methods, consider using `Async.FromBeginEnd` to write extension methods as a façade to provide the F# async programming model to those .NET APIs.</span></span>

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

### <a name="exceptions"></a><span data-ttu-id="c732e-292">Eccezioni</span><span class="sxs-lookup"><span data-stu-id="c732e-292">Exceptions</span></span>

<span data-ttu-id="c732e-293">Visualizzare [gestione degli errori](conventions.md#error-management) per apprendere l'utilizzo appropriato di eccezioni, i risultati e le opzioni.</span><span class="sxs-lookup"><span data-stu-id="c732e-293">See [Error Management](conventions.md#error-management) to learn about appropriate use of exceptions, results, and options.</span></span>

### <a name="extension-members"></a><span data-ttu-id="c732e-294">Membri di estensione</span><span class="sxs-lookup"><span data-stu-id="c732e-294">Extension Members</span></span>

#### <a name="carefully-apply-f-extension-members-in-f-to-f-components"></a><span data-ttu-id="c732e-295">Applicare con attenzione F# i membri di estensione in F#- a -F# componenti</span><span class="sxs-lookup"><span data-stu-id="c732e-295">Carefully apply F# extension members in F#-to-F# components</span></span>

<span data-ttu-id="c732e-296">F#membri di estensione devono in genere essere utilizzati solo per le operazioni che si trovano nella chiusura di operazioni intrinseche associate a un tipo nella maggior parte delle relative modalità d'uso.</span><span class="sxs-lookup"><span data-stu-id="c732e-296">F# extension members should generally only be used for operations that are in the closure of intrinsic operations associated with a type in the majority of its modes of use.</span></span> <span data-ttu-id="c732e-297">Un utilizzo comune consiste nel fornire le API che sono più idiomatiche per F# per diversi tipi di .NET:</span><span class="sxs-lookup"><span data-stu-id="c732e-297">One common use is to provide APIs that are more idiomatic to F# for various .NET types:</span></span>

```fsharp
type System.ServiceModel.Channels.IInputChannel with
    member this.AsyncReceive() =
        Async.FromBeginEnd(this.BeginReceive, this.EndReceive)

type System.Collections.Generic.IDictionary<'Key,'Value> with
    member this.TryGet key =
        let ok, v = this.TryGetValue key
        if ok then Some v else None
```

### <a name="union-types"></a><span data-ttu-id="c732e-298">Tipi di unione</span><span class="sxs-lookup"><span data-stu-id="c732e-298">Union Types</span></span>

#### <a name="use-discriminated-unions-instead-of-class-hierarchies-for-tree-structured-data"></a><span data-ttu-id="c732e-299">Usare le unioni discriminate invece di gerarchie di classi per i dati di struttura ad albero</span><span class="sxs-lookup"><span data-stu-id="c732e-299">Use discriminated unions instead of class hierarchies for tree-structured data</span></span>

<span data-ttu-id="c732e-300">Strutture ad albero sono definiti in modo ricorsivo.</span><span class="sxs-lookup"><span data-stu-id="c732e-300">Tree-like structures are recursively defined.</span></span> <span data-ttu-id="c732e-301">È difficile con ereditarietà, ma con unioni discriminate elegante.</span><span class="sxs-lookup"><span data-stu-id="c732e-301">This is awkward with inheritance, but elegant with Discriminated Unions.</span></span>

```fsharp
type BST<'T> =
    | Empty
    | Node of 'T * BST<'T> * BST<'T>
```

<span data-ttu-id="c732e-302">Che rappresenta i dati di struttura ad albero con unioni discriminate consente anche di trarre vantaggio da exhaustiveness nei criteri di ricerca.</span><span class="sxs-lookup"><span data-stu-id="c732e-302">Representing tree-like data with Discriminated Unions also allows you to benefit from exhaustiveness in pattern matching.</span></span>

#### <a name="use-requirequalifiedaccess-on-union-types-whose-case-names-are-not-sufficiently-unique"></a><span data-ttu-id="c732e-303">Usare `[<RequireQualifiedAccess>]` su tipi di unione i cui nomi case non sono sufficientemente univoci</span><span class="sxs-lookup"><span data-stu-id="c732e-303">Use `[<RequireQualifiedAccess>]` on union types whose case names are not sufficiently unique</span></span>

<span data-ttu-id="c732e-304">Si potrebbe trovare in un dominio in cui lo stesso nome è il nome migliore per scopi diversi, ad esempio case di unione discriminata.</span><span class="sxs-lookup"><span data-stu-id="c732e-304">You may find yourself in a domain where the same name is the best name for different things, such as Discriminated Union cases.</span></span> <span data-ttu-id="c732e-305">È possibile usare `[<RequireQualifiedAccess>]` per risolvere l'ambiguità di nomi dei casi per evitare di attivare confusi errori a causa di shadowing dipendenti per l'ordinamento delle `open` istruzioni</span><span class="sxs-lookup"><span data-stu-id="c732e-305">You can use `[<RequireQualifiedAccess>]` to disambiguate case names in order to avoid triggering confusing errors due to shadowing dependent on the ordering of `open` statements</span></span>

#### <a name="hide-the-representations-of-discriminated-unions-for-binary-compatible-apis-if-the-design-of-these-types-is-likely-to-evolve"></a><span data-ttu-id="c732e-306">Consente di nascondere le rappresentazioni delle unioni discriminate di API compatibili binarie se la progettazione di questi tipi è probabile che si evolvono</span><span class="sxs-lookup"><span data-stu-id="c732e-306">Hide the representations of discriminated unions for binary compatible APIs if the design of these types is likely to evolve</span></span>

<span data-ttu-id="c732e-307">Le unioni tipi si basano sulla F# criteri di ricerca di form per un modello di programmazione conciso.</span><span class="sxs-lookup"><span data-stu-id="c732e-307">Unions types rely on F# pattern-matching forms for a succinct programming model.</span></span> <span data-ttu-id="c732e-308">Come accennato in precedenza, è consigliabile evitare di rivelare le rappresentazioni di dati concreti se la progettazione di questi tipi è probabile che si evolvono.</span><span class="sxs-lookup"><span data-stu-id="c732e-308">As mentioned previously, you should avoid revealing concrete data representations if the design of these types is likely to evolve.</span></span>

<span data-ttu-id="c732e-309">Ad esempio, può essere nascosta la rappresentazione di un'unione discriminata con una dichiarazione privata o interna, oppure usando un file della firma.</span><span class="sxs-lookup"><span data-stu-id="c732e-309">For example, the representation of a discriminated union can be hidden using a private or internal declaration, or by using a signature file.</span></span>

```fsharp
type Union =
    private
    | CaseA of int
    | CaseB of string
```

<span data-ttu-id="c732e-310">Se si rivelano le unioni discriminate indiscriminatamente, può risultare difficile da versione libreria senza causare interruzioni nel codice utente.</span><span class="sxs-lookup"><span data-stu-id="c732e-310">If you reveal discriminated unions indiscriminately, you may find it hard to version your library without breaking user code.</span></span> <span data-ttu-id="c732e-311">Si consiglia di rivelare uno o più criteri attivi per consentire la corrispondenza dei valori del tipo in uso.</span><span class="sxs-lookup"><span data-stu-id="c732e-311">Instead, consider revealing one or more active patterns to permit pattern matching over values of your type.</span></span>

<span data-ttu-id="c732e-312">Criteri attivi forniscono un modo alternativo per specificare F# utenti con criteri di ricerca evitando l'esposizione di F# direttamente i tipi di unione.</span><span class="sxs-lookup"><span data-stu-id="c732e-312">Active patterns provide an alternate way to provide F# consumers with pattern matching while avoiding exposing F# Union Types directly.</span></span>

### <a name="inline-functions-and-member-constraints"></a><span data-ttu-id="c732e-313">Le funzioni inline e i vincoli di membro</span><span class="sxs-lookup"><span data-stu-id="c732e-313">Inline Functions and Member Constraints</span></span>

#### <a name="define-generic-numeric-algorithms-using-inline-functions-with-implied-member-constraints-and-statically-resolved-generic-types"></a><span data-ttu-id="c732e-314">Definire generici algoritmi numerici utilizzando le funzioni inline con vincoli membro implicito e risolti in modo statico tipi generici</span><span class="sxs-lookup"><span data-stu-id="c732e-314">Define generic numeric algorithms using inline functions with implied member constraints and statically resolved generic types</span></span>

<span data-ttu-id="c732e-315">I vincoli di membro aritmetico e F# vincoli del confronto sono standard per F# di programmazione.</span><span class="sxs-lookup"><span data-stu-id="c732e-315">Arithmetic member constraints and F# comparison constraints are a standard for F# programming.</span></span> <span data-ttu-id="c732e-316">Si consideri il codice di esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="c732e-316">For example, consider the following code:</span></span>

```fsharp
let inline highestCommonFactor a b =
    let rec loop a b =
        if a = LanguagePrimitives.GenericZero<_> then b
        elif a < b then loop a (b - a)
        else loop (a - b) b
    loop a b
```

<span data-ttu-id="c732e-317">Il tipo di questa funzione è come segue:</span><span class="sxs-lookup"><span data-stu-id="c732e-317">The type of this function is as follows:</span></span>

```fsharp
val inline highestCommonFactor : ^T -> ^T -> ^T
                when ^T : (static member Zero : ^T)
                and ^T : (static member ( - ) : ^T * ^T -> ^T)
                and ^T : equality
                and ^T : comparison
```

<span data-ttu-id="c732e-318">Si tratta di una funzione appropriata per un'API pubblica in una libreria matematica.</span><span class="sxs-lookup"><span data-stu-id="c732e-318">This is a suitable function for a public API in a mathematical library.</span></span>

#### <a name="avoid-using-member-constraints-to-simulate-type-classes-and-duck-typing"></a><span data-ttu-id="c732e-319">Evitare l'utilizzo di vincoli relativi ai membri per simulare le classi di tipo e Duck Typing digitando</span><span class="sxs-lookup"><span data-stu-id="c732e-319">Avoid using member constraints to simulate type classes and duck typing</span></span>

<span data-ttu-id="c732e-320">È possibile simulare l'utilizzo di "duck typing" F# vincoli di membro.</span><span class="sxs-lookup"><span data-stu-id="c732e-320">It is possible to simulate “duck typing” using F# member constraints.</span></span> <span data-ttu-id="c732e-321">Tuttavia, i membri che rendono utilizzano questa non in generale da usare in F#- a -F# le progettazioni di libreria.</span><span class="sxs-lookup"><span data-stu-id="c732e-321">However, members that make use of this should not in general be used in F#-to-F# library designs.</span></span> <span data-ttu-id="c732e-322">Questo avviene perché le progettazioni di libreria in base ai vincoli impliciti sconosciuti o non standard tendono a causare problemi nel codice utente diventi flessibile e sono associati al modello di un framework specifico.</span><span class="sxs-lookup"><span data-stu-id="c732e-322">This is because library designs based on unfamiliar or non-standard implicit constraints tend to cause user code to become inflexible and tied to one particular framework pattern.</span></span>

<span data-ttu-id="c732e-323">Inoltre, è probabile che un uso massiccio di vincoli relativi ai membri in questo modo può comportare tempi di compilazione molto lunghi.</span><span class="sxs-lookup"><span data-stu-id="c732e-323">Additionally, there is a good chance that heavy use of member constraints in this manner can result in very long compile times.</span></span>

### <a name="operator-definitions"></a><span data-ttu-id="c732e-324">Definizioni dell'operatore</span><span class="sxs-lookup"><span data-stu-id="c732e-324">Operator Definitions</span></span>

#### <a name="avoid-defining-custom-symbolic-operators"></a><span data-ttu-id="c732e-325">Evitare di definire gli operatori simbolici personalizzati</span><span class="sxs-lookup"><span data-stu-id="c732e-325">Avoid defining custom symbolic operators</span></span>

<span data-ttu-id="c732e-326">Gli operatori personalizzati sono essenziali in alcune situazioni e sono estremamente utili notazionale dispositivi all'interno di un corpo di grandi dimensioni del codice di implementazione.</span><span class="sxs-lookup"><span data-stu-id="c732e-326">Custom operators are essential in some situations and are highly useful notational devices within a large body of implementation code.</span></span> <span data-ttu-id="c732e-327">Per i nuovi utenti di una libreria, le funzioni denominate sono spesso più facile da usare.</span><span class="sxs-lookup"><span data-stu-id="c732e-327">For new users of a library, named functions are often easier to use.</span></span> <span data-ttu-id="c732e-328">Inoltre, operatori simbolici personalizzati possono essere difficili al documento e utenti trovarla più difficile per la ricerca della Guida sugli operatori, a causa di limitazioni esistenti nei motori di ricerca e dell'IDE.</span><span class="sxs-lookup"><span data-stu-id="c732e-328">In addition, custom symbolic operators can be hard to document, and users find it more difficult to look up help on operators, due to existing limitations in IDE and search engines.</span></span>

<span data-ttu-id="c732e-329">Di conseguenza, si consiglia di pubblicare la funzionalità come funzioni denominate e i membri e inoltre esporre operatori per questa funzionalità solo se i vantaggi notazionale superano la documentazione e i costi cognitivi di prevedere.</span><span class="sxs-lookup"><span data-stu-id="c732e-329">As a result, it is best to publish your functionality as named functions and members, and additionally expose operators for this functionality only if the notational benefits outweigh the documentation and cognitive cost of having them.</span></span>

### <a name="units-of-measure"></a><span data-ttu-id="c732e-330">Unità di misura</span><span class="sxs-lookup"><span data-stu-id="c732e-330">Units of Measure</span></span>

#### <a name="carefully-use-units-of-measure-for-added-type-safety-in-f-code"></a><span data-ttu-id="c732e-331">Usare con attenzione le unità di misura per motivi di sicurezza di tipo aggiunto in F# codice</span><span class="sxs-lookup"><span data-stu-id="c732e-331">Carefully use units of measure for added type safety in F# code</span></span>

<span data-ttu-id="c732e-332">Informazioni di tipizzazione aggiuntive per le unità di misura viene cancellate quando viene visualizzato da altri linguaggi .NET.</span><span class="sxs-lookup"><span data-stu-id="c732e-332">Additional typing information for units of measure is erased when viewed by other .NET languages.</span></span> <span data-ttu-id="c732e-333">Tenere presente che la reflection, strumenti e componenti .NET verranno visualizzati i tipi-sans-unità.</span><span class="sxs-lookup"><span data-stu-id="c732e-333">Be aware that .NET components, tools, and reflection will see types-sans-units.</span></span> <span data-ttu-id="c732e-334">Ad esempio, verranno visualizzato c# consumatori `float` anziché `float<kg>`.</span><span class="sxs-lookup"><span data-stu-id="c732e-334">For example, C# consumers will see `float` rather than `float<kg>`.</span></span>

### <a name="type-abbreviations"></a><span data-ttu-id="c732e-335">Abbreviazioni dei tipi</span><span class="sxs-lookup"><span data-stu-id="c732e-335">Type Abbreviations</span></span>

#### <a name="carefully-use-type-abbreviations-to-simplify-f-code"></a><span data-ttu-id="c732e-336">Usare con attenzione le abbreviazioni dei tipi per semplificare la F# codice</span><span class="sxs-lookup"><span data-stu-id="c732e-336">Carefully use type abbreviations to simplify F# code</span></span>

<span data-ttu-id="c732e-337">La reflection, strumenti e componenti .NET non visualizzeranno i nomi abbreviati per i tipi.</span><span class="sxs-lookup"><span data-stu-id="c732e-337">.NET components, tools, and reflection will not see abbreviated names for types.</span></span> <span data-ttu-id="c732e-338">Utilizzo significativo di abbreviazioni dei tipi può inoltre effettuare un dominio vengono visualizzati più complessa di quanto effettivamente è, quale operazione potrebbe confondere gli utenti.</span><span class="sxs-lookup"><span data-stu-id="c732e-338">Significant usage of type abbreviations can also make a domain appear more complex than it actually is, which could confuse consumers.</span></span>

#### <a name="avoid-type-abbreviations-for-public-types-whose-members-and-properties-should-be-intrinsically-different-to-those-available-on-the-type-being-abbreviated"></a><span data-ttu-id="c732e-339">Evitare le abbreviazioni dei tipi per i tipi pubblici di cui i membri e le proprietà devono essere intrinsecamente diversi rispetto a quelli disponibili nel tipo di cui è in corso abbreviato</span><span class="sxs-lookup"><span data-stu-id="c732e-339">Avoid type abbreviations for public types whose members and properties should be intrinsically different to those available on the type being abbreviated</span></span>

<span data-ttu-id="c732e-340">In questo caso, il tipo viene abbreviato rivela troppe operazioni sulla rappresentazione di tipo effettivo da definire.</span><span class="sxs-lookup"><span data-stu-id="c732e-340">In this case, the type being abbreviated reveals too much about the representation of the actual type being defined.</span></span> <span data-ttu-id="c732e-341">Al contrario, prendere in considerazione l'abbreviazione in un tipo di classe o un'unione discriminata case singolo di wrapping (oppure, quando le prestazioni sono essenziali, è consigliabile usare un tipo struct per eseguire il wrapping l'abbreviazione).</span><span class="sxs-lookup"><span data-stu-id="c732e-341">Instead, consider wrapping the abbreviation in a class type or a single-case discriminated union (or, when performance is essential, consider using a struct type to wrap the abbreviation).</span></span>

<span data-ttu-id="c732e-342">Ad esempio, è tentato di definire una mappa più come un caso speciale di un F# esegue il mapping, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="c732e-342">For example, it is tempting to define a multi-map as a special case of an F# map, for example:</span></span>

```fsharp
type MultiMap<'Key,'Value> = Map<'Key,'Value list>
```

<span data-ttu-id="c732e-343">Tuttavia, le operazioni di notazione con punto logico per questo tipo non sono le stesse operazioni su una mappa, ad esempio, è ragionevole che l'operatore di ricerca siano mappati. [key] Restituisce un elenco vuoto se la chiave non è presente nel dizionario, anziché generare un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="c732e-343">However, the logical dot-notation operations on this type are not the same as the operations on a Map – for example, it is reasonable that the lookup operator map.[key] return the empty list if the key is not in the dictionary, rather than raising an exception.</span></span>

## <a name="guidelines-for-libraries-for-use-from-other-net-languages"></a><span data-ttu-id="c732e-344">Linee guida per le raccolte per l'utilizzo in altri linguaggi .NET</span><span class="sxs-lookup"><span data-stu-id="c732e-344">Guidelines for libraries for Use from other .NET Languages</span></span>

<span data-ttu-id="c732e-345">Durante la progettazione di librerie per l'uso di altri linguaggi .NET, è importante rispettare le [indicazioni per la progettazione di librerie .NET](../../standard/design-guidelines/index.md).</span><span class="sxs-lookup"><span data-stu-id="c732e-345">When designing libraries for use from other .NET languages, it is important to adhere to the [.NET Library Design Guidelines](../../standard/design-guidelines/index.md).</span></span> <span data-ttu-id="c732e-346">In questo documento, queste librerie sono contrassegnate come "vanilla" librerie di .NET, in contrapposizione a F#-per le raccolte che usano F# costruisce senza alcuna restrizione.</span><span class="sxs-lookup"><span data-stu-id="c732e-346">In this document, these libraries are labeled as vanilla .NET libraries, as opposed to F#-facing libraries that use F# constructs without restriction.</span></span> <span data-ttu-id="c732e-347">Progettazione di librerie .NET "vanilla" significa fornire familiari e idiomatiche API coerente con il resto di .NET Framework, riducendo al minimo l'uso di F#-costrutti specifici nell'API pubblica.</span><span class="sxs-lookup"><span data-stu-id="c732e-347">Designing vanilla .NET libraries means providing familiar and idiomatic APIs consistent with the rest of the .NET Framework by minimizing the use of F#-specific constructs in the public API.</span></span> <span data-ttu-id="c732e-348">Le regole sono illustrate nelle sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="c732e-348">The rules are explained in the following sections.</span></span>

### <a name="namespace-and-type-design-for-libraries-for-use-from-other-net-languages"></a><span data-ttu-id="c732e-349">Namespace e il tipo di progettazione (per le librerie per l'utilizzo in altri linguaggi .NET)</span><span class="sxs-lookup"><span data-stu-id="c732e-349">Namespace and Type design (for libraries for use from other .NET Languages)</span></span>

#### <a name="apply-the-net-naming-conventions-to-the-public-api-of-your-components"></a><span data-ttu-id="c732e-350">Applicare le convenzioni di denominazione .NET per l'API pubblica dei componenti</span><span class="sxs-lookup"><span data-stu-id="c732e-350">Apply the .NET naming conventions to the public API of your components</span></span>

<span data-ttu-id="c732e-351">Prestare particolare attenzione all'uso di nomi abbreviati e linee guida di maiuscole/minuscole di .NET.</span><span class="sxs-lookup"><span data-stu-id="c732e-351">Pay special attention to the use of abbreviated names and the .NET capitalization guidelines.</span></span>

```fsharp
type pCoord = ...
    member this.theta = ...

type PolarCoordinate = ...
    member this.Theta = ...
```

#### <a name="use-namespaces-types-and-members-as-the-primary-organizational-structure-for-your-components"></a><span data-ttu-id="c732e-352">Usare gli spazi dei nomi, tipi e membri della struttura organizzativa primaria per i componenti</span><span class="sxs-lookup"><span data-stu-id="c732e-352">Use namespaces, types, and members as the primary organizational structure for your components</span></span>

<span data-ttu-id="c732e-353">Tutti i file che contiene la funzionalità pubblica devono iniziare con un `namespace` dichiarazione e l'unica entità pubblici negli spazi dei nomi devono essere tipi.</span><span class="sxs-lookup"><span data-stu-id="c732e-353">All files containing public functionality should begin with a `namespace` declaration, and the only public-facing entities in namespaces should be types.</span></span> <span data-ttu-id="c732e-354">Non usare F# i moduli.</span><span class="sxs-lookup"><span data-stu-id="c732e-354">Do not use F# modules.</span></span>

<span data-ttu-id="c732e-355">Usare i moduli non pubblici per contenere il codice di implementazione, utilità tipi e funzioni di utilità.</span><span class="sxs-lookup"><span data-stu-id="c732e-355">Use non-public modules to hold implementation code, utility types, and utility functions.</span></span>

<span data-ttu-id="c732e-356">I tipi statici devono essere Preferiti a moduli, poiché consentono un'ottica evolutiva future dell'API usare overload e altri concetti di progettazione di API .NET che non possono essere usati all'interno di F# i moduli.</span><span class="sxs-lookup"><span data-stu-id="c732e-356">Static types should be preferred over modules, as they allow for future evolution of the API to use overloading and other .NET API design concepts that may not be used within F# modules.</span></span>

<span data-ttu-id="c732e-357">Ad esempio, al posto dell'API pubblica seguente:</span><span class="sxs-lookup"><span data-stu-id="c732e-357">For example, in place of the following public API:</span></span>

```fsharp
module Fabrikam

module Utilities =
    let Name = "Bob"
    let Add2 x y = x + y
    let Add3 x y z = x + y + z
```

<span data-ttu-id="c732e-358">Si consideri invece:</span><span class="sxs-lookup"><span data-stu-id="c732e-358">Consider instead:</span></span>

```fsharp
namespace Fabrikam

[<AbstractClass; Sealed>]
type Utilities =
    static member Name = "Bob"
    static member Add(x,y) = x + y
    static member Add(x,y,z) = x + y + z
```

#### <a name="use-f-record-types-in-vanilla-net-apis-if-the-design-of-the-types-wont-evolve"></a><span data-ttu-id="c732e-359">Usare F# tipi di record nell'API .NET di vanilla se non si evoluzione la progettazione dei tipi</span><span class="sxs-lookup"><span data-stu-id="c732e-359">Use F# record types in vanilla .NET APIs if the design of the types won't evolve</span></span>

<span data-ttu-id="c732e-360">F#tipi di record è compilata in una classe .NET semplice.</span><span class="sxs-lookup"><span data-stu-id="c732e-360">F# record types compile to a simple .NET class.</span></span> <span data-ttu-id="c732e-361">Questi sono adatti per alcuni tipi semplici e stabili per le API.</span><span class="sxs-lookup"><span data-stu-id="c732e-361">These are suitable for some simple, stable types in APIs.</span></span> <span data-ttu-id="c732e-362">È consigliabile usare la `[<NoEquality>]` e `[<NoComparison>]` attributi per eliminare la generazione automatica delle interfacce.</span><span class="sxs-lookup"><span data-stu-id="c732e-362">You should consider using the `[<NoEquality>]` and `[<NoComparison>]` attributes to suppress the automatic generation of interfaces.</span></span> <span data-ttu-id="c732e-363">Anche evitare di usare campi modificabili record vanilla API .NET come questi espone un campo pubblico.</span><span class="sxs-lookup"><span data-stu-id="c732e-363">Also avoid using mutable record fields in vanilla .NET APIs as these exposes a public field.</span></span> <span data-ttu-id="c732e-364">Valutare sempre se una classe fornisce un'opzione più flessibile per evoluzione futura dell'API.</span><span class="sxs-lookup"><span data-stu-id="c732e-364">Always consider whether a class would provide a more flexible option for future evolution of the API.</span></span>

<span data-ttu-id="c732e-365">Il seguente, ad esempio, F# codice espone l'API pubblica a un C# consumer:</span><span class="sxs-lookup"><span data-stu-id="c732e-365">For example, the following F# code exposes the public API to a C# consumer:</span></span>

<span data-ttu-id="c732e-366">F#:</span><span class="sxs-lookup"><span data-stu-id="c732e-366">F#:</span></span>

```fsharp
[<NoEquality; NoComparison>]
type MyRecord =
    { FirstThing : int
        SecondThing : string }
```

<span data-ttu-id="c732e-367">C#:</span><span class="sxs-lookup"><span data-stu-id="c732e-367">C#:</span></span>

```csharp
public sealed class MyRecord
{
    public MyRecord(int firstThing, string secondThing);
    public int FirstThing { get; }
    public string SecondThing { get; }
}
```

#### <a name="hide-the-representation-of-f-union-types-in-vanilla-net-apis"></a><span data-ttu-id="c732e-368">Nascondere la rappresentazione di F# tipi di unione in vanilla API .NET</span><span class="sxs-lookup"><span data-stu-id="c732e-368">Hide the representation of F# union types in vanilla .NET APIs</span></span>

<span data-ttu-id="c732e-369">F#tipi di unione non usati comunemente nei limiti dei componenti, anche per F#- a -F# scrittura di codice.</span><span class="sxs-lookup"><span data-stu-id="c732e-369">F# union types are not commonly used across component boundaries, even for F#-to-F# coding.</span></span> <span data-ttu-id="c732e-370">Si tratta di un dispositivo di implementazione eccellenti quando usata internamente all'interno di componenti e librerie.</span><span class="sxs-lookup"><span data-stu-id="c732e-370">They are an excellent implementation device when used internally within components and libraries.</span></span>

<span data-ttu-id="c732e-371">Quando si progetta un'API .NET di vanilla, prendere in considerazione se si nasconde la rappresentazione di un tipo di unione tramite una dichiarazione privata o un file della firma.</span><span class="sxs-lookup"><span data-stu-id="c732e-371">When designing a vanilla .NET API, consider hiding the representation of a union type by using either a private declaration or a signature file.</span></span>

```fsharp
type PropLogic =
    private
    | And of PropLogic * PropLogic
    | Not of PropLogic
    | True
```

<span data-ttu-id="c732e-372">Si potrebbero aumentare anche tipi che utilizzano internamente una rappresentazione in forma unione con i membri per fornire un desiderato. API rivolte NET.</span><span class="sxs-lookup"><span data-stu-id="c732e-372">You may also augment types that use a union representation internally with members to provide a desired .NET-facing API.</span></span>

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

#### <a name="design-gui-and-other-components-using-the-design-patterns-of-the-framework"></a><span data-ttu-id="c732e-373">Progettazione interfaccia utente grafica e altri componenti tramite i modelli di progettazione di framework</span><span class="sxs-lookup"><span data-stu-id="c732e-373">Design GUI and other components using the design patterns of the framework</span></span>

<span data-ttu-id="c732e-374">Sono disponibili molti framework differenti all'interno di .NET, ad esempio WinForms, WPF e ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="c732e-374">There are many different frameworks available within .NET, such as WinForms, WPF, and ASP.NET.</span></span> <span data-ttu-id="c732e-375">Convenzioni di denominazione e progettazione per ognuno devono essere utilizzate se si progettano i componenti per l'utilizzo in tali Framework.</span><span class="sxs-lookup"><span data-stu-id="c732e-375">Naming and design conventions for each should be used if you are designing components for use in these frameworks.</span></span> <span data-ttu-id="c732e-376">Ad esempio, per la programmazione WPF, adottare i modelli di progettazione WPF per le classi che si sta progettando.</span><span class="sxs-lookup"><span data-stu-id="c732e-376">For example, for WPF programming, adopt WPF design patterns for the classes you are designing.</span></span> <span data-ttu-id="c732e-377">Per i modelli di programmazione dell'interfaccia utente, usare modelli di progettazione, ad esempio eventi e le raccolte basato sulla notifica, ad esempio quelli disponibili in <xref:System.Collections.ObjectModel>.</span><span class="sxs-lookup"><span data-stu-id="c732e-377">For models in user interface programming, use design patterns such as events and notification-based collections such as those found in <xref:System.Collections.ObjectModel>.</span></span>

### <a name="object-and-member-design-for-libraries-for-use-from-other-net-languages"></a><span data-ttu-id="c732e-378">Progettazione di oggetti e membri (per le librerie per l'utilizzo in altri linguaggi .NET)</span><span class="sxs-lookup"><span data-stu-id="c732e-378">Object and Member design (for libraries for use from other .NET Languages)</span></span>

#### <a name="use-the-clievent-attribute-to-expose-net-events"></a><span data-ttu-id="c732e-379">Usare l'attributo CLIEvent per esporre gli eventi .NET</span><span class="sxs-lookup"><span data-stu-id="c732e-379">Use the CLIEvent attribute to expose .NET events</span></span>

<span data-ttu-id="c732e-380">Costruire una `DelegateEvent` con una specifica di .NET tipo che accetta un oggetto delegato e `EventArgs` (anziché un' `Event`, che usa solo il `FSharpHandler` tipo per impostazione predefinita), in modo che gli eventi vengono pubblicati in modo familiare per altri linguaggi .NET.</span><span class="sxs-lookup"><span data-stu-id="c732e-380">Construct a `DelegateEvent` with a specific .NET delegate type that takes an object and `EventArgs` (rather than an `Event`, which just uses the `FSharpHandler` type by default) so that the events are published in the familiar way to other .NET languages.</span></span>

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

#### <a name="expose-asynchronous-operations-as-methods-which-return-net-tasks"></a><span data-ttu-id="c732e-381">Esponi le operazioni asincrone come metodi che restituiscono le attività .NET</span><span class="sxs-lookup"><span data-stu-id="c732e-381">Expose asynchronous operations as methods which return .NET tasks</span></span>

<span data-ttu-id="c732e-382">Le attività vengono usate in .NET per rappresentare i calcoli asincroni attivi.</span><span class="sxs-lookup"><span data-stu-id="c732e-382">Tasks are used in .NET to represent active asynchronous computations.</span></span> <span data-ttu-id="c732e-383">Le attività sono in genere meno composizionale rispetto a F# `Async<T>` oggetti, poiché rappresentano le attività "già in esecuzione" e non possono essere combinate insieme nei modi che eseguire la composizione di parallel, o che nasconde la propagazione di segnali di annullamento e altri parametri contestuali.</span><span class="sxs-lookup"><span data-stu-id="c732e-383">Tasks are in general less compositional than F# `Async<T>` objects, since they represent “already executing” tasks and can’t be composed together in ways that perform parallel composition, or which hide the propagation of cancellation signals and other contextual parameters.</span></span>

<span data-ttu-id="c732e-384">Tuttavia, nonostante ciò, i metodi che restituiscono le attività sono la rappresentazione della programmazione asincrona in .NET standard.</span><span class="sxs-lookup"><span data-stu-id="c732e-384">However, despite this, methods which return Tasks are the standard representation of asynchronous programming on .NET.</span></span>

```fsharp
/// A type in a component designed for use from other .NET languages
type MyType() =

    let compute (x: int) : Async<int> = async { ... }

    member this.ComputeAsync(x) = compute x |> Async.StartAsTask
```

<span data-ttu-id="c732e-385">Sarà spesso anche vuole accettare un token di annullamento esplicito:</span><span class="sxs-lookup"><span data-stu-id="c732e-385">You will frequently also want to accept an explicit cancellation token:</span></span>

```fsharp
/// A type in a component designed for use from other .NET languages
type MyType() =
    let compute(x:int) : Async<int> = async { ... }
    member this.ComputeAsTask(x, cancellationToken) = Async.StartAsTask(compute x, cancellationToken)
```

#### <a name="use-net-delegate-types-instead-of-f-function-types"></a><span data-ttu-id="c732e-386">Usare tipi di delegati di .NET al posto di F# tipi di funzione</span><span class="sxs-lookup"><span data-stu-id="c732e-386">Use .NET delegate types instead of F# function types</span></span>

<span data-ttu-id="c732e-387">In questo caso "F# tipi di funzione" significa che i tipi di "freccia" come `int -> int`.</span><span class="sxs-lookup"><span data-stu-id="c732e-387">Here “F# function types” mean “arrow” types like `int -> int`.</span></span>

<span data-ttu-id="c732e-388">Anziché il seguente:</span><span class="sxs-lookup"><span data-stu-id="c732e-388">Instead of this:</span></span>

```fsharp
member this.Transform(f:int->int) =
    ...
```

<span data-ttu-id="c732e-389">Eseguire questa operazione:</span><span class="sxs-lookup"><span data-stu-id="c732e-389">Do this:</span></span>

```fsharp
member this.Transform(f:Func<int,int>) =
    ...
```

<span data-ttu-id="c732e-390">Il F# tipo di funzione viene visualizzato come `class FSharpFunc<T,U>` ad altri linguaggi .NET ed è meno adatto per le funzionalità del linguaggio e gli strumenti che supportano i tipi delegati.</span><span class="sxs-lookup"><span data-stu-id="c732e-390">The F# function type appears as `class FSharpFunc<T,U>` to other .NET languages, and is less suitable for language features and tooling that understand delegate types.</span></span> <span data-ttu-id="c732e-391">Durante la creazione di un metodo di ordine superiore destinate a .NET Framework 3.5 o versione successiva, il `System.Func` e `System.Action` i delegati sono le API a destra per la pubblicazione per consentire agli sviluppatori .NET di usare queste API in modo semplice.</span><span class="sxs-lookup"><span data-stu-id="c732e-391">When authoring a higher-order method targeting .NET Framework 3.5 or higher, the `System.Func` and `System.Action` delegates are the right APIs to publish to enable .NET developers to consume these APIs in a low-friction manner.</span></span> <span data-ttu-id="c732e-392">(Quando la destinazione è .NET Framework 2.0, i tipi delegati definiti dal sistema sono più limitati, è consigliabile usare tipi delegato predefinito, ad esempio `System.Converter<T,U>` o definizione di un tipo delegato specifico.)</span><span class="sxs-lookup"><span data-stu-id="c732e-392">(When targeting .NET Framework 2.0, the system-defined delegate types are more limited; consider using predefined delegate types such as `System.Converter<T,U>` or defining a specific delegate type.)</span></span>

<span data-ttu-id="c732e-393">D'altra parte, non siano naturali per i delegati di .NET F#-con le librerie di connessione (vedere la sezione successiva in F#-rivolta librerie).</span><span class="sxs-lookup"><span data-stu-id="c732e-393">On the flip side, .NET delegates are not natural for F#-facing libraries (see the next Section on F#-facing libraries).</span></span> <span data-ttu-id="c732e-394">Di conseguenza, una strategia di implementazione comune durante lo sviluppo di metodi di ordine superiore per vanilla librerie .NET consiste nel creare tutti l'implementazione tramite F# tipi di funzione e quindi creare l'API pubblica uso dei delegati come un'interfaccia thin sopra l'effettivo F#implementazione.</span><span class="sxs-lookup"><span data-stu-id="c732e-394">As a result, a common implementation strategy when developing higher-order methods for vanilla .NET libraries is to author all the implementation using F# function types, and then create the public API using delegates as a thin façade atop the actual F# implementation.</span></span>

#### <a name="use-the-trygetvalue-pattern-instead-of-returning-f-option-values-and-prefer-method-overloading-to-taking-f-option-values-as-arguments"></a><span data-ttu-id="c732e-395">Usare il modello TryGetValue invece di restituire F# i valori delle opzioni e preferiscono l'overload dei metodi di acquisizione F# i valori come argomenti delle opzioni</span><span class="sxs-lookup"><span data-stu-id="c732e-395">Use the TryGetValue pattern instead of returning F# option values, and prefer method overloading to taking F# option values as arguments</span></span>

<span data-ttu-id="c732e-396">Modelli comuni di utilizzo per il F# tipo di opzione per le API sono preferibili implementato in vanilla tecniche di progettazione API .NET con .NET standard.</span><span class="sxs-lookup"><span data-stu-id="c732e-396">Common patterns of use for the F# option type in APIs are better implemented in vanilla .NET APIs using standard .NET design techniques.</span></span> <span data-ttu-id="c732e-397">Invece di restituire un F# valore dell'opzione, è possibile usare il tipo restituito bool oltre a un parametro out come il modello "TryGetValue".</span><span class="sxs-lookup"><span data-stu-id="c732e-397">Instead of returning an F# option value, consider using the bool return type plus an out parameter as in the "TryGetValue" pattern.</span></span> <span data-ttu-id="c732e-398">E invece di acquisizione F# i valori come parametri di opzione, è possibile usare gli argomenti del metodo overload o facoltativi.</span><span class="sxs-lookup"><span data-stu-id="c732e-398">And instead of taking F# option values as parameters, consider using method overloading or optional arguments.</span></span>

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

#### <a name="use-the-net-collection-interface-types-ienumerablet-and-idictionarykeyvalue-for-parameters-and-return-values"></a><span data-ttu-id="c732e-399">Usare l'interfaccia di raccolta .NET i tipi di IEnumerable\<T\> e IDictionary\<chiave, valore\> per i parametri e valori restituiti</span><span class="sxs-lookup"><span data-stu-id="c732e-399">Use the .NET collection interface types IEnumerable\<T\> and IDictionary\<Key,Value\> for parameters and return values</span></span>

<span data-ttu-id="c732e-400">Evitare l'utilizzo di tipi, ad esempio le matrici .NET di raccolta concreti `T[]`, F# tipi `list<T>`, `Map<Key,Value>` e `Set<T>`, e i tipi di raccolta concreti .NET, ad esempio `Dictionary<Key,Value>`.</span><span class="sxs-lookup"><span data-stu-id="c732e-400">Avoid the use of concrete collection types such as .NET arrays `T[]`, F# types `list<T>`, `Map<Key,Value>` and `Set<T>`, and .NET concrete collection types such as `Dictionary<Key,Value>`.</span></span> <span data-ttu-id="c732e-401">Linee guida di progettazione di .NET della libreria sono ottimo suggerimento relative all'utilizzo di diversi tipi di raccolta, ad esempio `IEnumerable<T>`.</span><span class="sxs-lookup"><span data-stu-id="c732e-401">The .NET Library Design Guidelines have good advice regarding when to use various collection types like `IEnumerable<T>`.</span></span> <span data-ttu-id="c732e-402">Utilizzato per scopi di matrici (`T[]`) è accettabile in alcune circostanze, per motivi di prestazioni.</span><span class="sxs-lookup"><span data-stu-id="c732e-402">Some use of arrays (`T[]`) is acceptable in some circumstances, on performance grounds.</span></span> <span data-ttu-id="c732e-403">Si noti che in particolare `seq<T>` è solo per il F# alias di `IEnumerable<T>`, e pertanto spesso seq è un tipo appropriato per un normale API .NET.</span><span class="sxs-lookup"><span data-stu-id="c732e-403">Note especially that `seq<T>` is just the F# alias for `IEnumerable<T>`, and thus seq is often an appropriate type for a vanilla .NET API.</span></span>

<span data-ttu-id="c732e-404">Invece di F# Elenca:</span><span class="sxs-lookup"><span data-stu-id="c732e-404">Instead of F# lists:</span></span>

```fsharp
member this.PrintNames(names : string list) =
    ...
```

<span data-ttu-id="c732e-405">Usare F# sequenze:</span><span class="sxs-lookup"><span data-stu-id="c732e-405">Use F# sequences:</span></span>

```fsharp
member this.PrintNames(names : seq<string>) =
    ...
```

#### <a name="use-the-unit-type-as-the-only-input-type-of-a-method-to-define-a-zero-argument-method-or-as-the-only-return-type-to-define-a-void-returning-method"></a><span data-ttu-id="c732e-406">Usare il tipo di unità come l'unico tipo di input di un metodo per definire un metodo specificato dall'argomento di zero o come unico tipo per definire un metodo che restituisce void restituito</span><span class="sxs-lookup"><span data-stu-id="c732e-406">Use the unit type as the only input type of a method to define a zero-argument method, or as the only return type to define a void-returning method</span></span>

<span data-ttu-id="c732e-407">Evitare di altri utilizzi del tipo di unità.</span><span class="sxs-lookup"><span data-stu-id="c732e-407">Avoid other uses of the unit type.</span></span> <span data-ttu-id="c732e-408">Si tratta di una buona:</span><span class="sxs-lookup"><span data-stu-id="c732e-408">These are good:</span></span>

```fsharp
✔ member this.NoArguments() = 3

✔ member this.ReturnVoid(x : int) = ()
```

<span data-ttu-id="c732e-409">Si tratta di una non valido:</span><span class="sxs-lookup"><span data-stu-id="c732e-409">This is bad:</span></span>

```fsharp
member this.WrongUnit( x:unit, z:int) = ((), ())
```

#### <a name="check-for-null-values-on-vanilla-net-api-boundaries"></a><span data-ttu-id="c732e-410">Verificare la presenza di valori null in "vanilla" dei limiti delle API .NET</span><span class="sxs-lookup"><span data-stu-id="c732e-410">Check for null values on vanilla .NET API boundaries</span></span>

<span data-ttu-id="c732e-411">F#codice di implementazione tende ad avere un minor numero di valori null, a causa di modelli di progettazione non modificabile e limitazioni sull'utilizzo di valori letterali null mobili per F# tipi.</span><span class="sxs-lookup"><span data-stu-id="c732e-411">F# implementation code tends to have fewer null values, due to immutable design patterns and restrictions on use of null literals for F# types.</span></span> <span data-ttu-id="c732e-412">Altri linguaggi .NET utilizzano spesso null come un valore molto più frequentemente.</span><span class="sxs-lookup"><span data-stu-id="c732e-412">Other .NET languages often use null as a value much more frequently.</span></span> <span data-ttu-id="c732e-413">Per questo motivo, F# codice che espone un'API .NET di vanilla deve controllare i parametri i valori null in corrispondenza del limite di API e impedire questi valori verso più approfondita in di F# il codice di implementazione.</span><span class="sxs-lookup"><span data-stu-id="c732e-413">Because of this, F# code that is exposing a vanilla .NET API should check parameters for null at the API boundary, and prevent these values from flowing deeper into the F# implementation code.</span></span> <span data-ttu-id="c732e-414">Il `isNull` funzione o criteri di ricerca nel `null` modello può essere usato.</span><span class="sxs-lookup"><span data-stu-id="c732e-414">The `isNull` function or pattern matching on the `null` pattern can be used.</span></span>

```fsharp
let checkNonNull argName (arg: obj) =
    match arg with
    | null -> nullArg argName
    | _ -> ()

let checkNonNull` argName (arg: obj) =
    if isNull arg then nullArg argName
    else ()
```

#### <a name="avoid-using-tuples-as-return-values"></a><span data-ttu-id="c732e-415">Evitare di usare le tuple come valori restituiti</span><span class="sxs-lookup"><span data-stu-id="c732e-415">Avoid using tuples as return values</span></span>

<span data-ttu-id="c732e-416">Preferire invece la restituzione di un tipo denominato che contiene i dati aggregati o tramite i parametri out per restituire più valori.</span><span class="sxs-lookup"><span data-stu-id="c732e-416">Instead, prefer returning a named type holding the aggregate data, or using out parameters to return multiple values.</span></span> <span data-ttu-id="c732e-417">Anche se esistono le tuple e le tuple struct in .NET, incluso supporto del linguaggio c# per le tuple struct, vengono in genere non fornirà l'API ideale e previsto per gli sviluppatori .NET.</span><span class="sxs-lookup"><span data-stu-id="c732e-417">Although tuples and struct tuples exist in .NET (including C# language support for struct tuples), they will most often not provide the ideal and expected API for .NET developers.</span></span>

#### <a name="avoid-the-use-of-currying-of-parameters"></a><span data-ttu-id="c732e-418">Evitare l'uso di currying dei parametri</span><span class="sxs-lookup"><span data-stu-id="c732e-418">Avoid the use of currying of parameters</span></span>

<span data-ttu-id="c732e-419">Usare invece le convenzioni di chiamata .NET ``Method(arg1,arg2,…,argN)``.</span><span class="sxs-lookup"><span data-stu-id="c732e-419">Instead, use .NET calling conventions ``Method(arg1,arg2,…,argN)``.</span></span>

```fsharp
member this.TupledArguments(str, num) = String.replicate num str
```

<span data-ttu-id="c732e-420">Suggerimento: Se si sta progettando le librerie per l'utilizzo in qualsiasi linguaggio .NET, quindi non resta altro per effettivamente eseguite alcune sperimentale C# e per garantire che le librerie "aspetto destra" da questi linguaggi di programmazione Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="c732e-420">Tip: If you’re designing libraries for use from any .NET language, then there’s no substitute for actually doing some experimental C# and Visual Basic programming to ensure that your libraries "feel right" from these languages.</span></span> <span data-ttu-id="c732e-421">È anche possibile usare strumenti, ad esempio .NET Reflector e il Visualizzatore oggetti di Visual Studio per garantire che le librerie e la relativa documentazione vengono visualizzati come previsto per gli sviluppatori.</span><span class="sxs-lookup"><span data-stu-id="c732e-421">You can also use tools such as .NET Reflector and the Visual Studio Object Browser to ensure that libraries and their documentation appear as expected to developers.</span></span>

## <a name="appendix"></a><span data-ttu-id="c732e-422">Appendice</span><span class="sxs-lookup"><span data-stu-id="c732e-422">Appendix</span></span>

### <a name="end-to-end-example-of-designing-f-code-for-use-by-other-net-languages"></a><span data-ttu-id="c732e-423">Esempio end-to-end di progettazione F# codice per l'uso da altri linguaggi .NET</span><span class="sxs-lookup"><span data-stu-id="c732e-423">End-to-end example of designing F# code for use by other .NET languages</span></span>

<span data-ttu-id="c732e-424">Si consideri la classe seguente:</span><span class="sxs-lookup"><span data-stu-id="c732e-424">Consider the following class:</span></span>

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

<span data-ttu-id="c732e-425">Il derivato F# tipo di questa classe è il seguente:</span><span class="sxs-lookup"><span data-stu-id="c732e-425">The inferred F# type of this class is as follows:</span></span>

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

<span data-ttu-id="c732e-426">Diamo un'occhiata a come questo F# tipo viene visualizzato a un programmatore che utilizza un altro linguaggio .NET.</span><span class="sxs-lookup"><span data-stu-id="c732e-426">Let’s take a look at how this F# type appears to a programmer using another .NET language.</span></span> <span data-ttu-id="c732e-427">Ad esempio, approssimativo c# "firma" è come segue:</span><span class="sxs-lookup"><span data-stu-id="c732e-427">For example, the approximate C# “signature” is as follows:</span></span>

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

<span data-ttu-id="c732e-428">Esistono alcuni aspetti importanti da notare su come F# costrutti di rappresenta qui.</span><span class="sxs-lookup"><span data-stu-id="c732e-428">There are some important points to notice about how F# represents constructs here.</span></span> <span data-ttu-id="c732e-429">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="c732e-429">For example:</span></span>

* <span data-ttu-id="c732e-430">I metadati, ad esempio i nomi degli argomenti sono stato mantenuto.</span><span class="sxs-lookup"><span data-stu-id="c732e-430">Metadata such as argument names has been preserved.</span></span>

* <span data-ttu-id="c732e-431">F#i metodi che accettano due argomenti diventi C# i metodi che accettano due argomenti.</span><span class="sxs-lookup"><span data-stu-id="c732e-431">F# methods that take two arguments become C# methods that take two arguments.</span></span>

* <span data-ttu-id="c732e-432">Funzioni e gli elenchi diventano i riferimenti ai tipi corrispondenti di F# library.</span><span class="sxs-lookup"><span data-stu-id="c732e-432">Functions and lists become references to corresponding types in the F# library.</span></span>

<span data-ttu-id="c732e-433">Il codice seguente viene illustrato come modificare il codice per tenere conto di queste operazioni.</span><span class="sxs-lookup"><span data-stu-id="c732e-433">The following code shows how to adjust this code to take these things into account.</span></span>

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

<span data-ttu-id="c732e-434">Il derivato F# è di tipo del codice come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="c732e-434">The inferred F# type of the code is as follows:</span></span>

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

<span data-ttu-id="c732e-435">La firma c# è ora come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="c732e-435">The C# signature is now as follows:</span></span>

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

<span data-ttu-id="c732e-436">Le correzioni apportate per preparare questo tipo per l'uso come parte di una libreria .NET "vanilla" sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="c732e-436">The fixes made to prepare this type for use as part of a vanilla .NET library are as follows:</span></span>

* <span data-ttu-id="c732e-437">Regolato diversi nomi: `Point1`, `n`, `l`, e `f` è diventato `RadialPoint`, `count`, `factor`, e `transform`, rispettivamente.</span><span class="sxs-lookup"><span data-stu-id="c732e-437">Adjusted several names: `Point1`, `n`, `l`, and `f` became `RadialPoint`, `count`, `factor`, and `transform`, respectively.</span></span>

* <span data-ttu-id="c732e-438">Utilizzato un tipo restituito `seq<RadialPoint>` invece di `RadialPoint list` modificando una costruzione elenco utilizzando `[ ... ]` a una sequenza di costruzione utilizzando `IEnumerable<RadialPoint>`.</span><span class="sxs-lookup"><span data-stu-id="c732e-438">Used a return type of `seq<RadialPoint>` instead of `RadialPoint list` by changing a list construction using `[ ... ]` to a sequence construction using `IEnumerable<RadialPoint>`.</span></span>

* <span data-ttu-id="c732e-439">Il tipo di delegato di .NET usata `System.Func` anziché un F# tipo di funzione.</span><span class="sxs-lookup"><span data-stu-id="c732e-439">Used the .NET delegate type `System.Func` instead of an F# function type.</span></span>

<span data-ttu-id="c732e-440">Questo rende molto accattivante utilizzare nel codice c#.</span><span class="sxs-lookup"><span data-stu-id="c732e-440">This makes it far nicer to consume in C# code.</span></span>

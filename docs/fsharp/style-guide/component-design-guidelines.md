---
title: 'Indicazioni per la progettazione di componenti F #'
description: 'Altre linee guida per la scrittura di F # componenti destinati al consumo ad altri chiamanti.'
ms.date: 05/14/2018
ms.openlocfilehash: 7e71710b1bc2fe3e8d7a5a091513a1432650dc04
ms.sourcegitcommit: 43924acbdbb3981d103e11049bbe460457d42073
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/23/2018
---
# <a name="f-component-design-guidelines"></a><span data-ttu-id="50949-103">Indicazioni per la progettazione di componenti F #</span><span class="sxs-lookup"><span data-stu-id="50949-103">F# component design guidelines</span></span>

<span data-ttu-id="50949-104">Questo documento è un set di linee guida di progettazione di componenti per F # di programmazione, in base a F # componente linee guida di progettazione, v14, Microsoft Research, e [un'altra versione](https://fsharp.org/specs/component-design-guidelines/) originariamente risposta curata relativa e gestiti da F # Software Foundation.</span><span class="sxs-lookup"><span data-stu-id="50949-104">This document is a set of component design guidelines for F# programming, based on the F# Component Design Guidelines, v14, Microsoft Research, and [another version](https://fsharp.org/specs/component-design-guidelines/) originally curated and maintained by the F# Software Foundation.</span></span>

<span data-ttu-id="50949-105">Questo documento presuppone che si ha familiarità con la programmazione F #.</span><span class="sxs-lookup"><span data-stu-id="50949-105">This document assumes you are familiar with F# programming.</span></span> <span data-ttu-id="50949-106">Un ringraziamento community F # per i relativi contributi e commenti e suggerimenti utili su varie versioni di questa Guida.</span><span class="sxs-lookup"><span data-stu-id="50949-106">Many thanks to the F# community for their contributions and helpful feedback on various versions of this guide.</span></span>

## <a name="overview"></a><span data-ttu-id="50949-107">Panoramica</span><span class="sxs-lookup"><span data-stu-id="50949-107">Overview</span></span>

<span data-ttu-id="50949-108">Questo documento vengono esaminati alcuni dei problemi relativi alla progettazione di componenti di F # e di codifica.</span><span class="sxs-lookup"><span data-stu-id="50949-108">This document looks at some of the issues related to F# component design and coding.</span></span> <span data-ttu-id="50949-109">Un componente può significare degli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="50949-109">A component can mean any of the following:</span></span>

* <span data-ttu-id="50949-110">Un livello nel progetto F # con utenti esterni all'interno di tale progetto.</span><span class="sxs-lookup"><span data-stu-id="50949-110">A layer in your F# project that has external consumers within that project.</span></span>
* <span data-ttu-id="50949-111">Una libreria destinata all'utilizzo tra limiti di assembly da codice F #.</span><span class="sxs-lookup"><span data-stu-id="50949-111">A library intended for consumption by F# code across assembly boundaries.</span></span>
* <span data-ttu-id="50949-112">Una libreria destinata all'utilizzo da qualsiasi linguaggio .NET tra limiti di assembly.</span><span class="sxs-lookup"><span data-stu-id="50949-112">A library intended for consumption by any .NET language across assembly boundaries.</span></span>
* <span data-ttu-id="50949-113">Una libreria destinata alla distribuzione tramite un repository di pacchetti, ad esempio [NuGet](https://nuget.org).</span><span class="sxs-lookup"><span data-stu-id="50949-113">A library intended for distribution via a package repository, such as [NuGet](https://nuget.org).</span></span>

<span data-ttu-id="50949-114">Seguono le tecniche descritte in questo articolo il [cinque principi di codice F # buona](index.md#five-principles-of-good-f-code)e utilizzano entrambi funzionale e programmazione come appropriato dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="50949-114">Techniques described in this article follow the [Five principles of good F# code](index.md#five-principles-of-good-f-code), and thus utilize both functional and object programming as appropriate.</span></span>

<span data-ttu-id="50949-115">Indipendentemente dalla metodologia, la finestra di progettazione di componenti e la libreria è rivolto numerosi problemi pratici e semplice quando si prova a creare un'API che è più facilmente utilizzabile dagli sviluppatori.</span><span class="sxs-lookup"><span data-stu-id="50949-115">Regardless of the methodology, the component and library designer faces a number of practical and prosaic issues when trying to craft an API that is most easily usable by developers.</span></span> <span data-ttu-id="50949-116">Applicazione attenta del [indicazioni per la progettazione di librerie .NET](../../standard/design-guidelines/index.md) verrà guidare è per la creazione di un set coerente di API che sono piacevole utilizzare.</span><span class="sxs-lookup"><span data-stu-id="50949-116">Conscientious application of the [.NET Library Design Guidelines](../../standard/design-guidelines/index.md) will steer you towards creating a consistent set of APIs that are pleasant to consume.</span></span>

## <a name="general-guidelines"></a><span data-ttu-id="50949-117">Indicazioni generali</span><span class="sxs-lookup"><span data-stu-id="50949-117">General guidelines</span></span>

<span data-ttu-id="50949-118">Vi sono alcune linee guida universale che si applicano a librerie F #, indipendentemente dai destinatari per la libreria.</span><span class="sxs-lookup"><span data-stu-id="50949-118">There are a few universal guidelines that apply to F# libraries, regardless of the intended audience for the library.</span></span>

### <a name="learn-the-net-library-design-guidelines"></a><span data-ttu-id="50949-119">Altre linee guida di progettazione di libreria .NET</span><span class="sxs-lookup"><span data-stu-id="50949-119">Learn the .NET Library Design Guidelines</span></span>

<span data-ttu-id="50949-120">Indipendentemente dal tipo di F # la generazione di codice vengono eseguite, è utile per avere una conoscenza del [indicazioni per la progettazione di librerie .NET](../../standard/design-guidelines/index.md).</span><span class="sxs-lookup"><span data-stu-id="50949-120">Regardless of the kind of F# coding you are doing, it is valuable to have a working knowledge of the [.NET Library Design Guidelines](../../standard/design-guidelines/index.md).</span></span> <span data-ttu-id="50949-121">La maggior parte delle altre F # programmatori di .NET verranno avere familiarità con queste linee guida e prevede che il codice .NET sia conforme a essi.</span><span class="sxs-lookup"><span data-stu-id="50949-121">Most other F# and .NET programmers will be familiar with these guidelines, and expect .NET code to conform to them.</span></span>

<span data-ttu-id="50949-122">La finestra di progettazione libreria .NET indicazioni generali relative alla denominazione, Progettazione classi e interfacce, progettazione di membri (proprietà, metodi, eventi, e così via) e altro ancora e sono un utile punto di riferimento per un'ampia gamma di indicazioni di progettazione.</span><span class="sxs-lookup"><span data-stu-id="50949-122">The .NET Library Design Guidelines provide general guidance regarding naming, designing classes and interfaces, member design (properties, methods, events, etc.) and more, and are a useful first point of reference for a variety of design guidance.</span></span>

### <a name="add-xml-documentation-comments-to-your-code"></a><span data-ttu-id="50949-123">Aggiungere commenti di documentazione XML al codice</span><span class="sxs-lookup"><span data-stu-id="50949-123">Add XML documentation comments to your code</span></span>

<span data-ttu-id="50949-124">Documentazione XML nelle API pubbliche assicurarsi che gli utenti possono ottenere Intellisense e informazioni rapide quando utilizzando questi tipi e membri e la documentazione di compilazione enable file per la libreria.</span><span class="sxs-lookup"><span data-stu-id="50949-124">XML documentation on public APIs ensure that users can get great Intellisense and Quickinfo when using these types and members, and enable building documentation files for the library.</span></span> <span data-ttu-id="50949-125">Vedere la [documentazione XML](../language-reference/xml-documentation.md) sui vari tag xml che può essere utilizzato per il markup aggiuntive all'interno di commenti xmldoc.</span><span class="sxs-lookup"><span data-stu-id="50949-125">See the [XML Documentation](../language-reference/xml-documentation.md) about various xml tags that can be used for additional markup within xmldoc comments.</span></span>

```fsharp
/// A class for representing (x,y) coordinates
type Point =

    /// Computes the distance between this point and another
    member DistanceTo : otherPoint:Point -> float
```

<span data-ttu-id="50949-126">È possibile utilizzare i commenti XML forma breve (`/// comment`), o commenti XML standard (`///<summary>comment</summary>`).</span><span class="sxs-lookup"><span data-stu-id="50949-126">You can use either the short form XML comments (`/// comment`), or standard XML comments (`///<summary>comment</summary>`).</span></span>

### <a name="consider-using-explicit-signature-files-fsi-for-stable-library-and-component-apis"></a><span data-ttu-id="50949-127">Provare a utilizzare file di firma esplicita (. fsi) per la libreria stabile e componente API</span><span class="sxs-lookup"><span data-stu-id="50949-127">Consider using explicit signature files (.fsi) for stable library and component APIs</span></span>

<span data-ttu-id="50949-128">Utilizzo dei file di firme esplicita in una libreria F # viene fornito un riepilogo conciso dell'API pubblica, che contribuisce a garantire che si conosce la superficie pubblica completa della libreria, nonché fornisce una netta separazione tra documentazione pubblica e interni dettagli di implementazione.</span><span class="sxs-lookup"><span data-stu-id="50949-128">Using explicit signatures files in an F# library provides a succinct summary of public API, which both helps to ensure that you know the full public surface of your library, as well as provides a clean separation between public documentation and internal implementation details.</span></span> <span data-ttu-id="50949-129">Si noti che i file di firma aggiungono attrito alla modifica dell'API pubblica, tramite la richiesta di modifiche da apportare nei file di implementazione e la firma.</span><span class="sxs-lookup"><span data-stu-id="50949-129">Note that signature files add friction to changing the public API, by requiring changes to be made in both the implementation and signature files.</span></span> <span data-ttu-id="50949-130">Di conseguenza, i file di firma devono in genere essere introdotto solo quando un'API ha diventano solidificata e non è più previsto per modificare in modo significativo.</span><span class="sxs-lookup"><span data-stu-id="50949-130">As a result, signature files should typically only be introduced when an API has become solidified and is no longer expected to change significantly.</span></span>

### <a name="always-follow-best-practices-for-using-strings-in-net"></a><span data-ttu-id="50949-131">Sempre seguire le procedure consigliate per l'utilizzo di stringhe in .NET</span><span class="sxs-lookup"><span data-stu-id="50949-131">Always follow best practices for using strings in .NET</span></span>

<span data-ttu-id="50949-132">Seguire [procedure consigliate per l'uso di stringhe in .NET](../../standard/base-types/best-practices-strings.md) informazioni aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="50949-132">Follow [Best Practices for Using Strings in .NET](../../standard/base-types/best-practices-strings.md) guidance.</span></span> <span data-ttu-id="50949-133">In particolare, sempre esplicitamente *finalità relative alla lingua* nella conversione e confronto di stringhe (dove applicabile).</span><span class="sxs-lookup"><span data-stu-id="50949-133">In particular, always explicitly state *cultural intent* in the conversion and comparison of strings (where applicable).</span></span>

## <a name="guidelines-for-f-facing-libraries"></a><span data-ttu-id="50949-134">Linee guida per F #-rivolti verso librerie</span><span class="sxs-lookup"><span data-stu-id="50949-134">Guidelines for F#-facing libraries</span></span>

<span data-ttu-id="50949-135">In questa sezione vengono offerti suggerimenti per lo sviluppo di F # pubblico-affiancate alle librerie. vale a dire, le librerie che espone le API pubbliche che devono essere utilizzati dagli sviluppatori di F #.</span><span class="sxs-lookup"><span data-stu-id="50949-135">This section presents recommendations for developing public F#-facing libraries; that is, libraries exposing public APIs that are intended to be consumed by F# developers.</span></span> <span data-ttu-id="50949-136">Sono disponibili numerosi consigli di progettazione di librerie applicabile in particolare a F #.</span><span class="sxs-lookup"><span data-stu-id="50949-136">There are a variety of library-design recommendations applicable specifically to F#.</span></span> <span data-ttu-id="50949-137">In mancanza di indicazioni specifiche che seguono, la finestra di progettazione libreria .NET sono le linee guida di fallback.</span><span class="sxs-lookup"><span data-stu-id="50949-137">In the absence of the specific recommendations that follow, the .NET Library Design Guidelines are the fallback guidance.</span></span>

### <a name="naming-conventions"></a><span data-ttu-id="50949-138">Convenzioni di denominazione</span><span class="sxs-lookup"><span data-stu-id="50949-138">Naming conventions</span></span>

#### <a name="use-net-naming-and-capitalization-conventions"></a><span data-ttu-id="50949-139">Utilizzare le convenzioni di denominazione e l'uso delle maiuscole .NET</span><span class="sxs-lookup"><span data-stu-id="50949-139">Use .NET naming and capitalization conventions</span></span>

<span data-ttu-id="50949-140">Nella tabella seguente è conforme alle convenzioni di denominazione e l'uso delle maiuscole .NET.</span><span class="sxs-lookup"><span data-stu-id="50949-140">The following table follows .NET naming and capitalization conventions.</span></span> <span data-ttu-id="50949-141">Esistono piccole aggiunte includere inoltre costrutti di F #.</span><span class="sxs-lookup"><span data-stu-id="50949-141">There are small additions to also include F# constructs.</span></span>

| <span data-ttu-id="50949-142">Costrutto</span><span class="sxs-lookup"><span data-stu-id="50949-142">Construct</span></span> | <span data-ttu-id="50949-143">Case</span><span class="sxs-lookup"><span data-stu-id="50949-143">Case</span></span> | <span data-ttu-id="50949-144">Parte</span><span class="sxs-lookup"><span data-stu-id="50949-144">Part</span></span> | <span data-ttu-id="50949-145">Esempi</span><span class="sxs-lookup"><span data-stu-id="50949-145">Examples</span></span> | <span data-ttu-id="50949-146">Note</span><span class="sxs-lookup"><span data-stu-id="50949-146">Notes</span></span> |
|-----------|------|------|----------|-------|
| <span data-ttu-id="50949-147">Tipi concreti</span><span class="sxs-lookup"><span data-stu-id="50949-147">Concrete types</span></span> | <span data-ttu-id="50949-148">PascalCase</span><span class="sxs-lookup"><span data-stu-id="50949-148">PascalCase</span></span> | <span data-ttu-id="50949-149">Sostantivo / frasario</span><span class="sxs-lookup"><span data-stu-id="50949-149">Noun/ adjective</span></span> | <span data-ttu-id="50949-150">Elenco, Double, complesso</span><span class="sxs-lookup"><span data-stu-id="50949-150">List, Double, Complex</span></span> | <span data-ttu-id="50949-151">Tipi concreti sono strutture, classi, enumerazioni, delegati, i record e unioni.</span><span class="sxs-lookup"><span data-stu-id="50949-151">Concrete types are structs, classes, enumerations, delegates, records, and unions.</span></span> <span data-ttu-id="50949-152">Anche se i nomi dei tipi sono in genere in lettere minuscole in OCaml, F # ha adottato lo schema di denominazione per i tipi .NET.</span><span class="sxs-lookup"><span data-stu-id="50949-152">Though type names are traditionally lowercase in OCaml, F# has adopted the .NET naming scheme for types.</span></span>
| <span data-ttu-id="50949-153">DLL</span><span class="sxs-lookup"><span data-stu-id="50949-153">DLLs</span></span>           | <span data-ttu-id="50949-154">PascalCase</span><span class="sxs-lookup"><span data-stu-id="50949-154">PascalCase</span></span> |                 | <span data-ttu-id="50949-155">Fabrikam.Core.dll</span><span class="sxs-lookup"><span data-stu-id="50949-155">Fabrikam.Core.dll</span></span> |  |
| <span data-ttu-id="50949-156">Tag di unione</span><span class="sxs-lookup"><span data-stu-id="50949-156">Union tags</span></span>     | <span data-ttu-id="50949-157">PascalCase</span><span class="sxs-lookup"><span data-stu-id="50949-157">PascalCase</span></span> | <span data-ttu-id="50949-158">sostantivo</span><span class="sxs-lookup"><span data-stu-id="50949-158">Noun</span></span> | <span data-ttu-id="50949-159">In alcuni casi, aggiungere, operazione riuscita</span><span class="sxs-lookup"><span data-stu-id="50949-159">Some, Add, Success</span></span> | <span data-ttu-id="50949-160">Non utilizzare un prefisso nelle API pubbliche.</span><span class="sxs-lookup"><span data-stu-id="50949-160">Do not use a prefix in public APIs.</span></span> <span data-ttu-id="50949-161">Se lo si desidera utilizzare un prefisso interno, ad esempio ' ' digitare team = TAlpha</span><span class="sxs-lookup"><span data-stu-id="50949-161">Optionally use a prefix when internal, such as \`\`\`type Teams = TAlpha</span></span> | <span data-ttu-id="50949-162">TBeta</span><span class="sxs-lookup"><span data-stu-id="50949-162">TBeta</span></span> | <span data-ttu-id="50949-163">TDelta. ' '</span><span class="sxs-lookup"><span data-stu-id="50949-163">TDelta.\`\`\`</span></span> |
| <span data-ttu-id="50949-164">event</span><span class="sxs-lookup"><span data-stu-id="50949-164">Event</span></span>          | <span data-ttu-id="50949-165">PascalCase</span><span class="sxs-lookup"><span data-stu-id="50949-165">PascalCase</span></span> | <span data-ttu-id="50949-166">Verbo</span><span class="sxs-lookup"><span data-stu-id="50949-166">Verb</span></span> | <span data-ttu-id="50949-167">ValueChanged / ValueChanging</span><span class="sxs-lookup"><span data-stu-id="50949-167">ValueChanged / ValueChanging</span></span> |  |
| <span data-ttu-id="50949-168">Eccezioni</span><span class="sxs-lookup"><span data-stu-id="50949-168">Exceptions</span></span>     | <span data-ttu-id="50949-169">PascalCase</span><span class="sxs-lookup"><span data-stu-id="50949-169">PascalCase</span></span> |      | <span data-ttu-id="50949-170">WebException</span><span class="sxs-lookup"><span data-stu-id="50949-170">WebException</span></span> | <span data-ttu-id="50949-171">Nome deve terminare con "Exception".</span><span class="sxs-lookup"><span data-stu-id="50949-171">Name should end with “Exception”.</span></span> |
| <span data-ttu-id="50949-172">Campo</span><span class="sxs-lookup"><span data-stu-id="50949-172">Field</span></span>          | <span data-ttu-id="50949-173">PascalCase</span><span class="sxs-lookup"><span data-stu-id="50949-173">PascalCase</span></span> | <span data-ttu-id="50949-174">sostantivo</span><span class="sxs-lookup"><span data-stu-id="50949-174">Noun</span></span> | <span data-ttu-id="50949-175">CurrentName</span><span class="sxs-lookup"><span data-stu-id="50949-175">CurrentName</span></span>  | |
| <span data-ttu-id="50949-176">Tipi interfaccia</span><span class="sxs-lookup"><span data-stu-id="50949-176">Interface types</span></span> |  <span data-ttu-id="50949-177">PascalCase</span><span class="sxs-lookup"><span data-stu-id="50949-177">PascalCase</span></span> | <span data-ttu-id="50949-178">Sostantivo / frasario</span><span class="sxs-lookup"><span data-stu-id="50949-178">Noun/ adjective</span></span> | <span data-ttu-id="50949-179">IDisposable</span><span class="sxs-lookup"><span data-stu-id="50949-179">IDisposable</span></span> | <span data-ttu-id="50949-180">Nome deve iniziare con "I".</span><span class="sxs-lookup"><span data-stu-id="50949-180">Name should start with “I”.</span></span> |
| <span data-ttu-id="50949-181">Metodo</span><span class="sxs-lookup"><span data-stu-id="50949-181">Method</span></span> |  <span data-ttu-id="50949-182">PascalCase</span><span class="sxs-lookup"><span data-stu-id="50949-182">PascalCase</span></span> |  <span data-ttu-id="50949-183">Verbo</span><span class="sxs-lookup"><span data-stu-id="50949-183">Verb</span></span> | <span data-ttu-id="50949-184">ToString</span><span class="sxs-lookup"><span data-stu-id="50949-184">ToString</span></span> | |
| <span data-ttu-id="50949-185">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="50949-185">Namespace</span></span> | <span data-ttu-id="50949-186">PascalCase</span><span class="sxs-lookup"><span data-stu-id="50949-186">PascalCase</span></span> | | <span data-ttu-id="50949-187">Microsoft.FSharp.Core</span><span class="sxs-lookup"><span data-stu-id="50949-187">Microsoft.FSharp.Core</span></span> | <span data-ttu-id="50949-188">In genere utilizzare `<Organization>.<Technology>[.<Subnamespace>]`, eliminare anche se l'organizzazione se la tecnologia è indipendente dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="50949-188">Generally use `<Organization>.<Technology>[.<Subnamespace>]`, though drop the organization if the technology is independent of organization.</span></span> |
| <span data-ttu-id="50949-189">Parametri</span><span class="sxs-lookup"><span data-stu-id="50949-189">Parameters</span></span> | <span data-ttu-id="50949-190">camelCase</span><span class="sxs-lookup"><span data-stu-id="50949-190">camelCase</span></span> | <span data-ttu-id="50949-191">sostantivo</span><span class="sxs-lookup"><span data-stu-id="50949-191">Noun</span></span> |  <span data-ttu-id="50949-192">typeName, trasformazione, intervallo</span><span class="sxs-lookup"><span data-stu-id="50949-192">typeName, transform, range</span></span> | |
| <span data-ttu-id="50949-193">consentire i valori (interni)</span><span class="sxs-lookup"><span data-stu-id="50949-193">let values (internal)</span></span> | <span data-ttu-id="50949-194">camelCase o PascalCase</span><span class="sxs-lookup"><span data-stu-id="50949-194">camelCase or PascalCase</span></span> | <span data-ttu-id="50949-195">Sostantivo / verbo</span><span class="sxs-lookup"><span data-stu-id="50949-195">Noun/ verb</span></span> |  <span data-ttu-id="50949-196">getValue, myTable</span><span class="sxs-lookup"><span data-stu-id="50949-196">getValue, myTable</span></span> |
| <span data-ttu-id="50949-197">consentire i valori (esterna)</span><span class="sxs-lookup"><span data-stu-id="50949-197">let values (external)</span></span> | <span data-ttu-id="50949-198">camelCase o PascalCase</span><span class="sxs-lookup"><span data-stu-id="50949-198">camelCase or PascalCase</span></span> | <span data-ttu-id="50949-199">Sostantivo/verbo</span><span class="sxs-lookup"><span data-stu-id="50949-199">Noun/verb</span></span>  | <span data-ttu-id="50949-200">List. map, Dates.Today</span><span class="sxs-lookup"><span data-stu-id="50949-200">List.map, Dates.Today</span></span> | <span data-ttu-id="50949-201">i valori associati a let sono pubblici spesso quando segue i modelli di progettazione funzionale tradizionale.</span><span class="sxs-lookup"><span data-stu-id="50949-201">let-bound values are often public when following traditional functional design patterns.</span></span> <span data-ttu-id="50949-202">Tuttavia, in genere PascalCase quando usare l'identificatore può essere utilizzato da altri linguaggi .NET.</span><span class="sxs-lookup"><span data-stu-id="50949-202">However, generally use PascalCase when the identifier can be used from other .NET languages.</span></span> |
| <span data-ttu-id="50949-203">Proprietà</span><span class="sxs-lookup"><span data-stu-id="50949-203">Property</span></span>  | <span data-ttu-id="50949-204">PascalCase</span><span class="sxs-lookup"><span data-stu-id="50949-204">PascalCase</span></span>  | <span data-ttu-id="50949-205">Sostantivo / frasario</span><span class="sxs-lookup"><span data-stu-id="50949-205">Noun/ adjective</span></span>  | <span data-ttu-id="50949-206">IsEndOfFile, colore di sfondo</span><span class="sxs-lookup"><span data-stu-id="50949-206">IsEndOfFile, BackColor</span></span>  | <span data-ttu-id="50949-207">Le proprietà booleane in genere l'utilizzo è e può e deve essere affermativa perché, come in IsEndOfFile, non IsNotEndOfFile.</span><span class="sxs-lookup"><span data-stu-id="50949-207">Boolean properties generally use Is and Can and should be affirmative, as in IsEndOfFile, not IsNotEndOfFile.</span></span>

#### <a name="avoid-abbreviations"></a><span data-ttu-id="50949-208">Evitare le abbreviazioni</span><span class="sxs-lookup"><span data-stu-id="50949-208">Avoid abbreviations</span></span>

<span data-ttu-id="50949-209">Linee guida di .NET se ne sconsiglia l'utilizzo di abbreviazioni (ad esempio, "usare `OnButtonClick` anziché `OnBtnClick`").</span><span class="sxs-lookup"><span data-stu-id="50949-209">The .NET guidelines discourage the use of abbreviations (for example, “use `OnButtonClick` rather than `OnBtnClick`”).</span></span> <span data-ttu-id="50949-210">Le abbreviazioni comuni, ad esempio `Async` per "Asincrono", sono tollerata.</span><span class="sxs-lookup"><span data-stu-id="50949-210">Common abbreviations, such as `Async` for “Asynchronous”, are tolerated.</span></span> <span data-ttu-id="50949-211">Questa linea guida viene ignorata in alcuni casi per la programmazione funzionale; ad esempio, `List.iter` Usa un'abbreviazione per "eseguire l'iterazione".</span><span class="sxs-lookup"><span data-stu-id="50949-211">This guideline is sometimes ignored for functional programming; for example, `List.iter` uses an abbreviation for “iterate”.</span></span> <span data-ttu-id="50949-212">Per questo motivo, tramite le abbreviazioni tende a essere espresso con maggiore precisione in F #-a-programmazione F #, ma ancora in genere sconsigliato nella progettazione di componenti pubblici.</span><span class="sxs-lookup"><span data-stu-id="50949-212">For this reason, using abbreviations tends to be tolerated to a greater degree in F#-to-F# programming, but should still generally be avoided in public component design.</span></span>

#### <a name="avoid-casing-name-collisions"></a><span data-ttu-id="50949-213">Evitare conflitti di nomi di maiuscole/minuscole</span><span class="sxs-lookup"><span data-stu-id="50949-213">Avoid casing name collisions</span></span>

<span data-ttu-id="50949-214">Linee guida di .NET sostengono maiuscole e minuscole da solo non può essere utilizzato per risolvere l'ambiguità conflitti di nomi, poiché alcune lingue client (ad esempio, Visual Basic) sono tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="50949-214">The .NET guidelines say that casing alone cannot be used to disambiguate name collisions, since some client languages (for example, Visual Basic) are case-insensitive.</span></span>

#### <a name="use-acronyms-where-appropriate"></a><span data-ttu-id="50949-215">Gli acronimi dove appropriato</span><span class="sxs-lookup"><span data-stu-id="50949-215">Use acronyms where appropriate</span></span>

<span data-ttu-id="50949-216">Gli acronimi, ad esempio XML non sono abbreviazioni e vengono ampiamente utilizzati nelle librerie .NET nel formato minuscolo (Xml).</span><span class="sxs-lookup"><span data-stu-id="50949-216">Acronyms such as XML are not abbreviations and are widely used in .NET libraries in uncapitalized form (Xml).</span></span> <span data-ttu-id="50949-217">Devono essere utilizzati solo acronimi noti, ampiamente riconosciuti.</span><span class="sxs-lookup"><span data-stu-id="50949-217">Only well-known, widely recognized acronyms should be used.</span></span>

#### <a name="use-pascalcase-for-generic-parameter-names"></a><span data-ttu-id="50949-218">Utilizzare PascalCase per i nomi di parametro generico</span><span class="sxs-lookup"><span data-stu-id="50949-218">Use PascalCase for generic parameter names</span></span>

<span data-ttu-id="50949-219">Utilizzare PascalCase per i nomi di parametro generico nelle API pubbliche, tra cui per F #-rivolti verso librerie.</span><span class="sxs-lookup"><span data-stu-id="50949-219">Do use PascalCase for generic parameter names in public APIs, including for F#-facing libraries.</span></span> <span data-ttu-id="50949-220">In particolare, utilizzare nomi quale `T`, `U`, `T1`, `T2` per i parametri generici arbitrari e nomi specifici ha senso, quindi per F #-librerie affiancate utilizzano nomi quale `Key`, `Value`, `Arg`(ma non ad esempio, `TKey`).</span><span class="sxs-lookup"><span data-stu-id="50949-220">In particular, use names like `T`, `U`, `T1`, `T2` for arbitrary generic parameters, and when specific names make sense, then for F#-facing libraries use names like `Key`, `Value`, `Arg` (but not for example, `TKey`).</span></span>

#### <a name="use-either-pascalcase-or-camelcase-for-public-functions-and-values-in-f-modules"></a><span data-ttu-id="50949-221">Utilizzare PascalCase o camelCase per le funzioni pubbliche e i valori nei moduli di F #</span><span class="sxs-lookup"><span data-stu-id="50949-221">Use either PascalCase or camelCase for public functions and values in F# modules</span></span>

<span data-ttu-id="50949-222">camelCase viene utilizzato per le funzioni pubbliche che sono progettate per essere usati non qualificato (ad esempio, `invalidArg`) e per le funzioni"raccolta standard" (ad esempio, List. Map).</span><span class="sxs-lookup"><span data-stu-id="50949-222">camelCase is used for public functions that are designed to be used unqualified (for example, `invalidArg`), and for the “standard collection functions” (for example, List.map).</span></span> <span data-ttu-id="50949-223">In entrambi questi casi, i nomi delle funzioni si comportano molto come parole chiave del linguaggio.</span><span class="sxs-lookup"><span data-stu-id="50949-223">In both these cases, the function names act much like keywords in the language.</span></span>

### <a name="object-type-and-module-design"></a><span data-ttu-id="50949-224">Progettazione di oggetto, tipo e modulo</span><span class="sxs-lookup"><span data-stu-id="50949-224">Object, Type, and Module design</span></span>

#### <a name="use-namespaces-or-modules-to-contain-your-types-and-modules"></a><span data-ttu-id="50949-225">Usare gli spazi dei nomi o i moduli per includere i tipi e i moduli</span><span class="sxs-lookup"><span data-stu-id="50949-225">Use namespaces or modules to contain your types and modules</span></span>

<span data-ttu-id="50949-226">Ogni file F # in un componente deve iniziare con una dichiarazione dello spazio dei nomi o in una dichiarazione di modulo.</span><span class="sxs-lookup"><span data-stu-id="50949-226">Each F# file in a component should begin with either a namespace declaration or a module declaration.</span></span>

```fsharp
namespace Fabrikam.BasicOperationsAndTypes

type ObjectType1() =
    ...

type ObjectType2() =
     ...

module CommonOperations =
    ...
```

<span data-ttu-id="50949-227">oppure</span><span class="sxs-lookup"><span data-stu-id="50949-227">or</span></span>

```fsharp
module Fabrikam.BasicOperationsAndTypes

type ObjectType1() =
    ...

type ObjectType2() =
    ...

module CommonOperations =
    ...
```

<span data-ttu-id="50949-228">Le differenze tra l'utilizzo di moduli e gli spazi dei nomi per organizzare il codice al livello superiore sono come segue:</span><span class="sxs-lookup"><span data-stu-id="50949-228">The differences between using modules and namespaces to organize code at the top level are as follows:</span></span>

* <span data-ttu-id="50949-229">Spazi dei nomi può estendersi su più file</span><span class="sxs-lookup"><span data-stu-id="50949-229">Namespaces can span multiple files</span></span>
* <span data-ttu-id="50949-230">Spazi dei nomi non può contenere funzioni F # a meno che non siano all'interno di un modulo interno</span><span class="sxs-lookup"><span data-stu-id="50949-230">Namespaces cannot contain F# functions unless they are within an inner module</span></span>
* <span data-ttu-id="50949-231">Il codice di qualsiasi modulo specificato deve essere contenuto in un singolo file</span><span class="sxs-lookup"><span data-stu-id="50949-231">The code for any given module must be contained within a single file</span></span>
* <span data-ttu-id="50949-232">Moduli di primo livello possono contenere funzioni F # senza la necessità di un modulo interno</span><span class="sxs-lookup"><span data-stu-id="50949-232">Top-level modules can contain F# functions without the need for an inner module</span></span>

<span data-ttu-id="50949-233">La scelta tra un livello superiore dello spazio dei nomi o modulo riguarda il form compilato del codice e pertanto verrà la visualizzazione da parte di altri linguaggi .NET devono dell'API infine essere utilizzata all'esterno del codice F #.</span><span class="sxs-lookup"><span data-stu-id="50949-233">The choice between a top-level namespace or module affects the compiled form of the code, and thus will affect the view from other .NET languages should your API eventually be consumed outside of F# code.</span></span>

#### <a name="use-methods-and-properties-for-operations-intrinsic-to-object-types"></a><span data-ttu-id="50949-234">Utilizzare i metodi e proprietà per le operazioni intrinseche per i tipi di oggetto</span><span class="sxs-lookup"><span data-stu-id="50949-234">Use methods and properties for operations intrinsic to object types</span></span>

<span data-ttu-id="50949-235">Quando si lavora con gli oggetti, è consigliabile verificare che la funzionalità può essere utilizzata viene implementata come metodi e proprietà per quel tipo.</span><span class="sxs-lookup"><span data-stu-id="50949-235">When working with objects, it is best to ensure that consumable functionality is implemented as methods and properties on that type.</span></span>

```fsharp
type HardwareDevice() =

    member this.ID = ...

    member this.SupportedProtocols = ...

type HashTable<'Key,'Value>(comparer: IEqualityComparer<'Key>) =

    member this.Add(key, value) = ...

    member this.ContainsKey(key) = ...

    member this.ContainsValue(value) = ...
```

<span data-ttu-id="50949-236">La maggior parte delle funzionalità per un determinato membro non debba necessariamente essere implementata in tale membro, ma deve essere parte del consumo di tali funzionalità.</span><span class="sxs-lookup"><span data-stu-id="50949-236">The bulk of functionality for a given member need not necessarily be implemented in that member, but the consumable piece of that functionality should be.</span></span>

#### <a name="use-classes-to-encapsulate-mutable-state"></a><span data-ttu-id="50949-237">Usare le classi per incapsulare lo stato modificabile</span><span class="sxs-lookup"><span data-stu-id="50949-237">Use classes to encapsulate mutable state</span></span>

<span data-ttu-id="50949-238">In F #, solo deve essere eseguita in cui che lo stato non è già incapsulato da un altro costrutto di linguaggio, ad esempio una chiusura, l'espressione di sequenza o calcolo asincrono.</span><span class="sxs-lookup"><span data-stu-id="50949-238">In F#, this only needs to be done where that state is not already encapsulated by another language construct, such as a closure, sequence expression, or asynchronous computation.</span></span>

```fsharp
type Counter() =
    // let-bound values are private in classes.
    let mutable count = 0

    member this.Next() =
        count <- count + 1
        count
```

#### <a name="use-interfaces-to-group-related-operations"></a><span data-ttu-id="50949-239">Utilizzare le interfacce per raggruppare le operazioni correlate</span><span class="sxs-lookup"><span data-stu-id="50949-239">Use interfaces to group related operations</span></span>

<span data-ttu-id="50949-240">Per rappresentare un set di operazioni, utilizzare i tipi di interfaccia.</span><span class="sxs-lookup"><span data-stu-id="50949-240">Use interface types to represent a set of operations.</span></span> <span data-ttu-id="50949-241">Si tratta di Preferiti ad altre opzioni, ad esempio le tuple di funzioni o i record delle funzioni.</span><span class="sxs-lookup"><span data-stu-id="50949-241">This is preferred to other options, such as tuples of functions or records of functions.</span></span>

```fsharp
type Serializer =
    abstract Serialize<'T> : preserveRefEq: bool -> value: 'T -> string
    abstract Deserialize<'T> : preserveRefEq: bool -> pickle: string -> 'T
```

<span data-ttu-id="50949-242">A:</span><span class="sxs-lookup"><span data-stu-id="50949-242">In preference to:</span></span>

```fsharp
type Serializer<'T> = {
    Serialize : bool -> 'T -> string
    Deserialize : bool -> string -> 'T
}
```

<span data-ttu-id="50949-243">Le interfacce sono concetti di primaria importanza in .NET, è possibile utilizzare per ottenere ciò che Funtori verrebbero normalmente fornito è.</span><span class="sxs-lookup"><span data-stu-id="50949-243">Interfaces are first-class concepts in .NET, which you can use to achieve what Functors would normally give you.</span></span> <span data-ttu-id="50949-244">Inoltre, possono essere utilizzati per codificare tipi esistenziali nel programma, che non può essere record delle funzioni.</span><span class="sxs-lookup"><span data-stu-id="50949-244">Additionally, they can be used to encode existential types into your program, which records of functions cannot.</span></span>

#### <a name="use-a-module-to-group-functions-which-act-on-collections"></a><span data-ttu-id="50949-245">Usa un modulo alle funzioni di gruppo che agiscono sulle raccolte</span><span class="sxs-lookup"><span data-stu-id="50949-245">Use a module to group functions which act on collections</span></span>

<span data-ttu-id="50949-246">Quando si definisce un tipo di raccolta, si consiglia di fornire un set standard di operazioni come `CollectionType.map` e `CollectionType.iter`) per i nuovi tipi di raccolta.</span><span class="sxs-lookup"><span data-stu-id="50949-246">When you define a collection type, consider providing a standard set of operations like `CollectionType.map` and `CollectionType.iter`) for new collection types.</span></span>

```fsharp
module CollectionType =
    let map f c =
        ...
    let iter f c =
        ...
```

<span data-ttu-id="50949-247">Se si include un modulo di questo tipo, seguire le convenzioni di denominazione standard per le funzioni trovate in FSharp. Core.</span><span class="sxs-lookup"><span data-stu-id="50949-247">If you include such a module, follow the standard naming conventions for functions found in FSharp.Core.</span></span>

#### <a name="use-a-module-to-group-functions-for-common-canonical-functions-especially-in-math-and-dsl-libraries"></a><span data-ttu-id="50949-248">Usa un modulo alle funzioni di gruppo per le funzioni comuni e canoniche, soprattutto nelle librerie DSL e matematiche</span><span class="sxs-lookup"><span data-stu-id="50949-248">Use a module to group functions for common, canonical functions, especially in math and DSL libraries</span></span>

<span data-ttu-id="50949-249">Ad esempio `Microsoft.FSharp.Core.Operators` è una raccolta di funzioni di primo livello aperta automaticamente (ad esempio `abs` e `sin`) fornite da FSharp.</span><span class="sxs-lookup"><span data-stu-id="50949-249">For example, `Microsoft.FSharp.Core.Operators` is an automatically opened collection of top-level functions (like `abs` and `sin`) provided by FSharp.Core.dll.</span></span>

<span data-ttu-id="50949-250">Analogamente, una raccolta di statistiche potrebbe includere un modulo con funzioni `erf` e `erfc`, in cui questo modulo è progettato per essere in modo esplicito o automaticamente aperto.</span><span class="sxs-lookup"><span data-stu-id="50949-250">Likewise, a statistics library might include a module with functions `erf` and `erfc`, where this module is designed to be explicitly or automatically opened.</span></span>

#### <a name="consider-using-requirequalifiedaccess-and-carefully-apply-autoopen-attributes"></a><span data-ttu-id="50949-251">È consigliabile usare RequireQualifiedAccess e attentamente applicare attributi AutoOpen</span><span class="sxs-lookup"><span data-stu-id="50949-251">Consider using RequireQualifiedAccess and carefully apply AutoOpen attributes</span></span>

<span data-ttu-id="50949-252">Aggiunta di `[<RequireQualifiedAccess>]` attributo a un modulo indica che il modulo non può essere aperta e che i riferimenti agli elementi del modulo richiedono esplicita qualificato l'accesso.</span><span class="sxs-lookup"><span data-stu-id="50949-252">Adding the `[<RequireQualifiedAccess>]` attribute to a module indicates that the module may not be opened and that references to the elements of the module require explicit qualified access.</span></span> <span data-ttu-id="50949-253">Ad esempio, il `Microsoft.FSharp.Collections.List` modulo dispone di questo attributo.</span><span class="sxs-lookup"><span data-stu-id="50949-253">For example, the `Microsoft.FSharp.Collections.List` module has this attribute.</span></span>

<span data-ttu-id="50949-254">Ciò è utile quando le funzioni e valori nel modulo hanno nomi che sono probabile che sia in conflitto con i nomi di altri moduli.</span><span class="sxs-lookup"><span data-stu-id="50949-254">This is useful when functions and values in the module have names that are likely to conflict with names in other modules.</span></span> <span data-ttu-id="50949-255">Che richiedono l'accesso completo può aumentare notevolmente la facilità di gestione a lungo termine ed evolvability di una libreria.</span><span class="sxs-lookup"><span data-stu-id="50949-255">Requiring qualified access can greatly increase the long-term maintainability and evolvability of a library.</span></span>

<span data-ttu-id="50949-256">Aggiunta di `[<AutoOpen>]` attributo su un modulo, il modulo verrà aperto quando viene aperto lo spazio dei nomi che lo contiene.</span><span class="sxs-lookup"><span data-stu-id="50949-256">Adding the `[<AutoOpen>]` attribute to a module means the module will be opened when the containing namespace is opened.</span></span> <span data-ttu-id="50949-257">Il `[<AutoOpen>]` attributo può anche essere applicato a un assembly per indicare un modulo che viene aperto automaticamente quando l'assembly viene fatto riferimento.</span><span class="sxs-lookup"><span data-stu-id="50949-257">The `[<AutoOpen>]` attribute may also be applied to an assembly to indicate a module that is automatically opened when the assembly is referenced.</span></span>

<span data-ttu-id="50949-258">Ad esempio, una raccolta di statistiche **MathsHeaven.Statistics** potrebbe contenere un `module MathsHeaven.Statistics.Operators` contenenti funzioni `erf` e `erfc`.</span><span class="sxs-lookup"><span data-stu-id="50949-258">For example, a statistics library **MathsHeaven.Statistics** might contain a `module MathsHeaven.Statistics.Operators` containing functions `erf` and `erfc`.</span></span> <span data-ttu-id="50949-259">È ragionevole contrassegnare questo modulo come `[<AutoOpen>]`.</span><span class="sxs-lookup"><span data-stu-id="50949-259">It is reasonable to mark this module as `[<AutoOpen>]`.</span></span> <span data-ttu-id="50949-260">Ciò significa `open MathsHeaven.Statistics` inoltre, verranno aprire questo modulo e visualizzare i nomi `erf` e `erfc` nell'ambito.</span><span class="sxs-lookup"><span data-stu-id="50949-260">This means `open MathsHeaven.Statistics` will also open this module and bring the names `erf` and `erfc` into scope.</span></span> <span data-ttu-id="50949-261">Buona un altro uso di `[<AutoOpen>]` è per i moduli che contiene i metodi di estensione.</span><span class="sxs-lookup"><span data-stu-id="50949-261">Another good use of `[<AutoOpen>]` is for modules containing extension methods.</span></span>

<span data-ttu-id="50949-262">Utilizzo eccessivo di `[<AutoOpen>]` lead inquinati gli spazi dei nomi e l'attributo deve essere utilizzata con cautela.</span><span class="sxs-lookup"><span data-stu-id="50949-262">Overuse of `[<AutoOpen>]` leads to polluted namespaces, and the attribute should be used with care.</span></span> <span data-ttu-id="50949-263">Per raccolte specifiche in domini specifici, l'utilizzo razionale di `[<AutoOpen>]` può portare a una migliore utilizzabilità.</span><span class="sxs-lookup"><span data-stu-id="50949-263">For specific libraries in specific domains, judicious use of `[<AutoOpen>]` can lead to better usability.</span></span>

#### <a name="consider-defining-operator-members-on-classes-where-using-well-known-operators-is-appropriate"></a><span data-ttu-id="50949-264">Si consiglia di definire i membri di operatore sulle classi in cui è appropriata utilizzando operatori noti</span><span class="sxs-lookup"><span data-stu-id="50949-264">Consider defining operator members on classes where using well-known operators is appropriate</span></span>

<span data-ttu-id="50949-265">In alcuni casi classi vengono utilizzate per la modellazione matematici costrutti come vettori.</span><span class="sxs-lookup"><span data-stu-id="50949-265">Sometimes classes are used to model mathematical constructs such as Vectors.</span></span> <span data-ttu-id="50949-266">Quando il dominio da modellare dispone di operatori noti, è utile definendole come membri intrinseci alla classe.</span><span class="sxs-lookup"><span data-stu-id="50949-266">When the domain being modeled has well-known operators, defining them as members intrinsic to the class is helpful.</span></span>

```fsharp
type Vector(x:float) =

    member v.X = x

    static member (*) (vector:Vector, scalar:float) = Vector(vector.X * scalar)

    static member (+) (vector1:Vector, vector2:Vector) = Vector(vector1.X + vector2.X)

let v = Vector(5.0)

let u = v * 10.0
```

<span data-ttu-id="50949-267">Questo materiale sussidiario corrisponde a informazioni aggiuntive generali .NET per questi tipi.</span><span class="sxs-lookup"><span data-stu-id="50949-267">This guidance corresponds to general .NET guidance for these types.</span></span> <span data-ttu-id="50949-268">Tuttavia, può essere inoltre importante in F # di codifica poiché in questo modo questi tipi da utilizzare in combinazione con le funzioni F # e i metodi con vincoli di membro, ad esempio List. sumBy.</span><span class="sxs-lookup"><span data-stu-id="50949-268">However, it can be additionally important in F# coding as this allows these types to be used in conjunction with F# functions and methods with member constraints, such as List.sumBy.</span></span>

#### <a name="consider-using-compiledname-to-provide-a-net-friendly-name-for-other-net-language-consumers"></a><span data-ttu-id="50949-269">Provare a usare CompiledName per fornire una. Nome descrittivo di rete per altri consumer di linguaggio .NET</span><span class="sxs-lookup"><span data-stu-id="50949-269">Consider using CompiledName to provide a .NET-friendly name for other .NET language consumers</span></span>

<span data-ttu-id="50949-270">In alcuni casi potrebbe essere necessario specificare un nome significativo in uno stile per i consumer di F # (ad esempio un membro statico in lettere minuscole, in modo che venga visualizzato come se fosse una funzione associata a modulo), ma hanno uno stile diverso per il nome quando viene compilato in un assembly.</span><span class="sxs-lookup"><span data-stu-id="50949-270">Sometimes you may wish to name something in one style for F# consumers (such as a static member in lower case so that it appears as if it were a module-bound function), but have a different style for the name when it is compiled into an assembly.</span></span> <span data-ttu-id="50949-271">È possibile utilizzare il `[<CompiledName>]` attributo per fornire uno stile diverso per il codice F # non utilizzano l'assembly.</span><span class="sxs-lookup"><span data-stu-id="50949-271">You can use the `[<CompiledName>]` attribute to provide a different style for non F# code consuming the assembly.</span></span>

```fsharp
type Vector(x:float, y:float) =

    member v.X = x
    member v.Y = y

    [<CompiledName("Create")>]
    static member create x y = Vector (x, y)

let v = Vector.create 5.0 3.0
```

<span data-ttu-id="50949-272">Tramite `[<CompiledName>]`, è possibile utilizzare le convenzioni di denominazione .NET per F # non consumer dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="50949-272">By using `[<CompiledName>]`, you can use .NET naming conventions for non F# consumers of the assembly.</span></span>

#### <a name="use-method-overloading-for-member-functions-if-doing-so-provides-a-simpler-api"></a><span data-ttu-id="50949-273">Utilizzare metodi (overload) per le funzioni membro, se in questo modo viene fornita un'API semplice</span><span class="sxs-lookup"><span data-stu-id="50949-273">Use method overloading for member functions, if doing so provides a simpler API</span></span>

<span data-ttu-id="50949-274">L'overload di metodo è un potente strumento per la semplificazione di un'API che potrebbe essere necessario eseguire una funzionalità simile, ma con diverse opzioni o argomenti.</span><span class="sxs-lookup"><span data-stu-id="50949-274">Method overloading is a powerful tool for simplifying an API that may need to perform similar functionality, but with different options or arguments.</span></span>

```fsharp
type Logger() =

    member this.Log(message) =
        ...
    member this.Log(message, retryPolicy) =
        ...
```

<span data-ttu-id="50949-275">In F #, è più comune per eseguire l'overload di un numero di argomenti anziché tipi di argomenti.</span><span class="sxs-lookup"><span data-stu-id="50949-275">In F#, it is more common to overload on number of arguments rather than types of arguments.</span></span>

#### <a name="hide-the-representations-of-record-and-union-types-if-the-design-of-these-types-is-likely-to-evolve"></a><span data-ttu-id="50949-276">Se la progettazione di questi tipi è probabile che si evolvono nascondere le rappresentazioni di record e i tipi di unione</span><span class="sxs-lookup"><span data-stu-id="50949-276">Hide the representations of record and union types if the design of these types is likely to evolve</span></span>

<span data-ttu-id="50949-277">Evitare di rivelare concrete rappresentazioni di oggetti.</span><span class="sxs-lookup"><span data-stu-id="50949-277">Avoid revealing concrete representations of objects.</span></span> <span data-ttu-id="50949-278">Ad esempio, la rappresentazione concreta di <xref:System.DateTime> valori non venga rivelata dall'API di pubblico, esterno del progetto di libreria .NET.</span><span class="sxs-lookup"><span data-stu-id="50949-278">For example, the concrete representation of <xref:System.DateTime> values is not revealed by the external, public API of the .NET library design.</span></span> <span data-ttu-id="50949-279">In fase di esecuzione, Common Language Runtime sa l'implementazione del commit che verrà utilizzato in tutta l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="50949-279">At run time, the Common Language Runtime knows the committed implementation that will be used throughout execution.</span></span> <span data-ttu-id="50949-280">Tuttavia, codice compilato non stesso prelevare le dipendenze sulla rappresentazione concreta.</span><span class="sxs-lookup"><span data-stu-id="50949-280">However, compiled code doesn't itself pick up dependencies on the concrete representation.</span></span>

#### <a name="avoid-the-use-of-implementation-inheritance-for-extensibility"></a><span data-ttu-id="50949-281">Evitare l'utilizzo dell'ereditarietà dell'implementazione per l'estensibilità</span><span class="sxs-lookup"><span data-stu-id="50949-281">Avoid the use of implementation inheritance for extensibility</span></span>

<span data-ttu-id="50949-282">In F #, viene raramente utilizzata l'implementazione dell'ereditarietà.</span><span class="sxs-lookup"><span data-stu-id="50949-282">In F#, implementation inheritance is rarely used.</span></span> <span data-ttu-id="50949-283">Inoltre, le gerarchie di ereditarietà sono spesso complessi e difficili da modificare all'arrivano di nuovi requisiti.</span><span class="sxs-lookup"><span data-stu-id="50949-283">Furthermore, inheritance hierarchies are often complex and difficult to change when new requirements arrive.</span></span> <span data-ttu-id="50949-284">Implementazione dell'ereditarietà continua a esistere in F # per la compatibilità e rari casi in cui è la soluzione migliore per risolvere un problema, ma tecniche alternative devono essere cercate nei programmi F # quando si progetta il polimorfismo, ad esempio l'implementazione dell'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="50949-284">Inheritance implementation still exists in F# for compatibility and rare cases where it is the best solution to a problem, but alternative techniques should be sought in your F# programs when designing for polymorphism, such as interface implementation.</span></span>

### <a name="function-and-member-signatures"></a><span data-ttu-id="50949-285">Firme di funzione e membro</span><span class="sxs-lookup"><span data-stu-id="50949-285">Function and member signatures</span></span>

#### <a name="use-tuples-for-return-values-when-returning-a-small-number-of-multiple-unrelated-values"></a><span data-ttu-id="50949-286">Utilizzano le tuple per i valori restituiti quando viene restituito un numero ridotto di più valori non correlati</span><span class="sxs-lookup"><span data-stu-id="50949-286">Use tuples for return values when returning a small number of multiple unrelated values</span></span>

<span data-ttu-id="50949-287">Di seguito è un buon esempio dell'utilizzo di una tupla in un tipo restituito:</span><span class="sxs-lookup"><span data-stu-id="50949-287">Here is a good example of using a tuple in a return type:</span></span>

```fsharp
val divrem : BigInteger -> BigInteger -> BigInteger * BigInteger
```

<span data-ttu-id="50949-288">Per restituire i tipi che contengono molti componenti o in cui i componenti sono correlati a una singola entità personali, è consigliabile usare un tipo denominato anziché una tupla.</span><span class="sxs-lookup"><span data-stu-id="50949-288">For return types containing many components, or where the components are related to a single identifiable entity, consider using a named type instead of a tuple.</span></span>

#### <a name="use-asynct-for-async-programming-at-f-api-boundaries"></a><span data-ttu-id="50949-289">Utilizzare `Async<T>` per la programmazione asincrona in base ai limiti API F #</span><span class="sxs-lookup"><span data-stu-id="50949-289">Use `Async<T>` for async programming at F# API boundaries</span></span>

<span data-ttu-id="50949-290">Se vi è un'operazione sincrona corrispondente denominata `Operation` che restituisce un `T`, l'operazione asincrona deve essere denominata `AsyncOperation` se non viene restituita `Async<T>` oppure `OperationAsync` se restituisce `Task<T>`.</span><span class="sxs-lookup"><span data-stu-id="50949-290">If there is a corresponding synchronous operation named `Operation` that returns a `T`, then the async operation should be named `AsyncOperation` if it returns `Async<T>` or `OperationAsync` if it returns `Task<T>`.</span></span> <span data-ttu-id="50949-291">Per i tipi .NET comunemente utilizzati che espongono metodi Begin/End, è consigliabile utilizzare `Async.FromBeginEnd` scrivere metodi di estensione come facciata per fornire il F # async modello di programmazione per le API .NET.</span><span class="sxs-lookup"><span data-stu-id="50949-291">For commonly used .NET types that expose Begin/End methods, consider using `Async.FromBeginEnd` to write extension methods as a façade to provide the F# async programming model to those .NET APIs.</span></span>

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

### <a name="exceptions"></a><span data-ttu-id="50949-292">Eccezioni</span><span class="sxs-lookup"><span data-stu-id="50949-292">Exceptions</span></span>

<span data-ttu-id="50949-293">Eccezioni sono costituite dalle eccezionali in .NET. vale a dire, essi non viene eseguito spesso in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="50949-293">Exceptions are exceptional in .NET; that is, they should not occur frequently at runtime.</span></span> <span data-ttu-id="50949-294">In questo caso, le informazioni che contengono sono importanti.</span><span class="sxs-lookup"><span data-stu-id="50949-294">When they do, the information they contain is valuable.</span></span> <span data-ttu-id="50949-295">Le eccezioni sono un concetto di prima classe di .NET; core IT pertanto indicato di seguito che appropriato l'applicazione delle eccezioni deve essere utilizzati come parte della progettazione dell'interfaccia di un componente.</span><span class="sxs-lookup"><span data-stu-id="50949-295">Exceptions are a core first class concept of .NET; it hence follows that appropriate application of the Exceptions should be used as part of the design of the interface of a component.</span></span>

#### <a name="follow-the-net-guidelines-for-exceptions"></a><span data-ttu-id="50949-296">Seguire le linee guida di .NET per le eccezioni</span><span class="sxs-lookup"><span data-stu-id="50949-296">Follow the .NET guidelines for exceptions</span></span>

<span data-ttu-id="50949-297">Il [indicazioni per la progettazione di librerie .NET](../../standard/design-guidelines/exceptions.md) consulenza eccellente sull'utilizzo delle eccezioni nel contesto della programmazione .NET.</span><span class="sxs-lookup"><span data-stu-id="50949-297">The [.NET Library Design Guidelines](../../standard/design-guidelines/exceptions.md) give excellent advice on the use of exceptions in the context of all .NET programming.</span></span> <span data-ttu-id="50949-298">Alcune di queste istruzioni sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="50949-298">Some of these guidelines are as follows:</span></span>

* <span data-ttu-id="50949-299">Non utilizzare le eccezioni per il normale flusso di controllo.</span><span class="sxs-lookup"><span data-stu-id="50949-299">Do not use exceptions for normal flow of control.</span></span> <span data-ttu-id="50949-300">Sebbene questa tecnica viene spesso utilizzata in lingue quali OCaml, è soggetta a bug e può risultare inefficiente su .NET.</span><span class="sxs-lookup"><span data-stu-id="50949-300">Although this technique is often used in languages such as OCaml, it is bug-prone and can be inefficient on .NET.</span></span> <span data-ttu-id="50949-301">Al contrario, provare a restituire un `None` valore per indicare un errore che è un problema comune o previsto dell'opzione.</span><span class="sxs-lookup"><span data-stu-id="50949-301">Instead, consider returning a `None` option value to indicate a failure that is a common or expected occurrence.</span></span>

* <span data-ttu-id="50949-302">Documentare le eccezioni generate dai componenti quando viene utilizzata una funzione in modo non corretto.</span><span class="sxs-lookup"><span data-stu-id="50949-302">Document exceptions thrown by your components when a function is used incorrectly.</span></span>

* <span data-ttu-id="50949-303">Dove possibile, utilizzare eccezioni esistenti degli spazi dei nomi System.</span><span class="sxs-lookup"><span data-stu-id="50949-303">Where possible, employ existing exceptions from the System namespaces.</span></span> <span data-ttu-id="50949-304">Evitare <xref:System.ApplicationException>, anche se.</span><span class="sxs-lookup"><span data-stu-id="50949-304">Avoid <xref:System.ApplicationException>, though.</span></span>

* <span data-ttu-id="50949-305">Non generare <xref:System.Exception> quando lo sarà escluse per il codice utente.</span><span class="sxs-lookup"><span data-stu-id="50949-305">Do not throw <xref:System.Exception> when it will escape to user code.</span></span> <span data-ttu-id="50949-306">Ciò include evitare l'uso di `failwith`, `failwithf`, che sono funzioni utili per l'utilizzo in script e per il codice in fase di sviluppo, ma deve essere rimossa dal codice di libreria F # a favore di generazione di un tipo di eccezione più specifico.</span><span class="sxs-lookup"><span data-stu-id="50949-306">This includes avoiding the use of `failwith`, `failwithf`, which are handy functions for use in scripting and for code under development, but should be removed from F# library code in favor of throwing a more specific exception type.</span></span>

* <span data-ttu-id="50949-307">Uso `nullArg`, `invalidArg`, e `invalidOp` come meccanismo di generare <xref:System.ArgumentNullException>, <xref:System.ArgumentException>, e <xref:System.InvalidOperationException> quando appropriato.</span><span class="sxs-lookup"><span data-stu-id="50949-307">Use `nullArg`, `invalidArg`, and `invalidOp` as the mechanism to throw <xref:System.ArgumentNullException>, <xref:System.ArgumentException>, and <xref:System.InvalidOperationException> when appropriate.</span></span>

#### <a name="consider-using-option-values-for-return-types-when-failure-is-not-an-exceptional-scenario"></a><span data-ttu-id="50949-308">Provare a utilizzare i valori delle opzioni per i tipi restituiti quando un errore non è uno scenario eccezionale</span><span class="sxs-lookup"><span data-stu-id="50949-308">Consider using option values for return types when failure is not an exceptional scenario</span></span>

<span data-ttu-id="50949-309">L'approccio di .NET per le eccezioni è che deve essere "eccezioni". vale a dire, dovranno essere eseguite raramente.</span><span class="sxs-lookup"><span data-stu-id="50949-309">The .NET approach to exceptions is that they should be “exceptional”; that is, they should occur relatively infrequently.</span></span> <span data-ttu-id="50949-310">Tuttavia, alcune operazioni (ad esempio, la ricerca di una tabella) potrebbero non riuscire con frequenza.</span><span class="sxs-lookup"><span data-stu-id="50949-310">However, some operations (for example, searching a table) may fail frequently.</span></span> <span data-ttu-id="50949-311">I valori delle opzioni F # sono un ottimo modo per rappresentare i tipi restituiti di queste operazioni.</span><span class="sxs-lookup"><span data-stu-id="50949-311">F# option values are an excellent way to represent the return types of these operations.</span></span> <span data-ttu-id="50949-312">Queste operazioni tradizionalmente iniziano con il prefisso di nome "try":</span><span class="sxs-lookup"><span data-stu-id="50949-312">These operations conventionally start with the name prefix “try”:</span></span>

```fsharp
// bad: throws exception if no element meets criteria
member this.FindFirstIndex(pred : 'T -> bool) : int =
    ...

// bad: returns -1 if no element meets criteria
member this.FindFirstIndex(pred : 'T -> bool) : int =
    ...

// good: returns None if no element meets criteria
member this.TryFindFirstIndex(pred : 'T -> bool) : int option =
    ...
```

### <a name="extension-members"></a><span data-ttu-id="50949-313">Membri di estensione</span><span class="sxs-lookup"><span data-stu-id="50949-313">Extension Members</span></span>

#### <a name="carefully-apply-f-extension-members-in-f-to-f-components"></a><span data-ttu-id="50949-314">Applicare con attenzione i membri di estensione F # in F #-a-F # componenti</span><span class="sxs-lookup"><span data-stu-id="50949-314">Carefully apply F# extension members in F#-to-F# components</span></span>

<span data-ttu-id="50949-315">Membri di estensione F # in genere esclusivamente per operazioni che trovano nella chiusura di operazioni intrinseche associate a un tipo nella maggior parte delle relative modalità d'uso.</span><span class="sxs-lookup"><span data-stu-id="50949-315">F# extension members should generally only be used for operations that are in the closure of intrinsic operations associated with a type in the majority of its modes of use.</span></span> <span data-ttu-id="50949-316">Un utilizzo comune consiste nel fornire le API che sono più idiomatiche a F # per vari tipi di .NET:</span><span class="sxs-lookup"><span data-stu-id="50949-316">One common use is to provide APIs that are more idiomatic to F# for various .NET types:</span></span>

```fsharp
type System.ServiceModel.Channels.IInputChannel with
    member this.AsyncReceive() =
        Async.FromBeginEnd(this.BeginReceive, this.EndReceive)

type System.Collections.Generic.IDictionary<'Key,'Value> with
    member this.TryGet key =
        let ok, v = this.TryGetValue key
        if ok then Some v else None
```

### <a name="union-types"></a><span data-ttu-id="50949-317">Tipi di unione</span><span class="sxs-lookup"><span data-stu-id="50949-317">Union Types</span></span>

#### <a name="use-discriminated-unions-instead-of-class-hierarchies-for-tree-structured-data"></a><span data-ttu-id="50949-318">Utilizzare le unioni discriminate anziché gerarchie di classi per i dati di struttura ad albero</span><span class="sxs-lookup"><span data-stu-id="50949-318">Use discriminated unions instead of class hierarchies for tree-structured data</span></span>

<span data-ttu-id="50949-319">Strutture ad albero sono definiti in modo ricorsivo.</span><span class="sxs-lookup"><span data-stu-id="50949-319">Tree-like structures are recursively defined.</span></span> <span data-ttu-id="50949-320">È difficile con ereditarietà ma elegante con unioni discriminate.</span><span class="sxs-lookup"><span data-stu-id="50949-320">This is awkward with inheritance, but elegant with Discriminated Unions.</span></span>

```fsharp
type BST<'T> =
    | Empty
    | Node of 'T * BST<'T> * BST<'T>
```

<span data-ttu-id="50949-321">Rappresentazione ad albero dei dati con le unioni discriminate consente inoltre di trarre vantaggio da exhaustiveness nei criteri di ricerca.</span><span class="sxs-lookup"><span data-stu-id="50949-321">Representing tree-like data with Discriminated Unions also allows you to benefit from exhaustiveness in pattern matching.</span></span>

#### <a name="use-requirequalifiedaccess-on-union-types-whose-case-names-are-not-sufficiently-unique"></a><span data-ttu-id="50949-322">Utilizzare `[<RequireQualifiedAccess>]` sui tipi di unione i cui nomi case non sono sufficientemente univoci</span><span class="sxs-lookup"><span data-stu-id="50949-322">Use `[<RequireQualifiedAccess>]` on union types whose case names are not sufficiently unique</span></span>

<span data-ttu-id="50949-323">Potrebbe essere necessario in un dominio in cui lo stesso nome è il nome migliore per scopi diversi, ad esempio case di unione discriminata.</span><span class="sxs-lookup"><span data-stu-id="50949-323">You may find yourself in a domain where the same name is the best name for different things, such as Discriminated Union cases.</span></span> <span data-ttu-id="50949-324">È possibile utilizzare `[<RequireQualifiedAccess>]` per risolvere le ambiguità nei nomi dei casi per evitare di causare confusi errori a causa di shadowing dipendente da ordine della `open` istruzioni</span><span class="sxs-lookup"><span data-stu-id="50949-324">You can use `[<RequireQualifiedAccess>]` to disambiguate case names in order to avoid triggering confusing errors due to shadowing dependent on the ordering of `open` statements</span></span>

#### <a name="hide-the-representations-of-discriminated-unions-for-binary-compatible-apis-if-the-design-of-these-types-is-likely-to-evolve"></a><span data-ttu-id="50949-325">Consente di nascondere le rappresentazioni delle unioni discriminate per le API compatibile binarie se la progettazione di questi tipi è probabile che si evolvono</span><span class="sxs-lookup"><span data-stu-id="50949-325">Hide the representations of discriminated unions for binary compatible APIs if the design of these types is likely to evolve</span></span>

<span data-ttu-id="50949-326">Tipi di unioni si basano su F # corrispondenza form per un modello di programmazione conciso.</span><span class="sxs-lookup"><span data-stu-id="50949-326">Unions types rely on F# pattern-matching forms for a succinct programming model.</span></span> <span data-ttu-id="50949-327">Come accennato in precedenza, è consigliabile evitare di rivelare le rappresentazioni di dati concreti se la progettazione di questi tipi è probabile che si evolvono.</span><span class="sxs-lookup"><span data-stu-id="50949-327">As mentioned previously, you should avoid revealing concrete data representations if the design of these types is likely to evolve.</span></span>

<span data-ttu-id="50949-328">Ad esempio, la rappresentazione di un'unione discriminata può essere nascosto utilizzando una dichiarazione privata o interna, oppure utilizzando un file della firma.</span><span class="sxs-lookup"><span data-stu-id="50949-328">For example, the representation of a discriminated union can be hidden using a private or internal declaration, or by using a signature file.</span></span>

```fsharp
type Union =
    private
    | CaseA of int
    | CaseB of string
```

<span data-ttu-id="50949-329">Se si rivelano le unioni discriminate indiscriminatamente, può risultare difficile versione libreria senza interrompere il codice utente.</span><span class="sxs-lookup"><span data-stu-id="50949-329">If you reveal discriminated unions indiscriminately, you may find it hard to version your library without breaking user code.</span></span> <span data-ttu-id="50949-330">Si consiglia di rivelare uno o più criteri attivi per consentire la corrispondenza dei valori del tipo in uso.</span><span class="sxs-lookup"><span data-stu-id="50949-330">Instead, consider revealing one or more active patterns to permit pattern matching over values of your type.</span></span>

<span data-ttu-id="50949-331">Criteri attivi forniscono un modo alternativo per fornire i consumer di F # con criteri di ricerca si evita di esporre direttamente i tipi di unione F #.</span><span class="sxs-lookup"><span data-stu-id="50949-331">Active patterns provide an alternate way to provide F# consumers with pattern matching while avoiding exposing F# Union Types directly.</span></span>

### <a name="inline-functions-and-member-constraints"></a><span data-ttu-id="50949-332">Funzioni inline e vincoli di membro</span><span class="sxs-lookup"><span data-stu-id="50949-332">Inline Functions and Member Constraints</span></span>

#### <a name="define-generic-numeric-algorithms-using-inline-functions-with-implied-member-constraints-and-statically-resolved-generic-types"></a><span data-ttu-id="50949-333">Definire algoritmi generici numerici utilizzando le funzioni inline con vincoli di membro implicito e i tipi generici risolti staticamente</span><span class="sxs-lookup"><span data-stu-id="50949-333">Define generic numeric algorithms using inline functions with implied member constraints and statically resolved generic types</span></span>

<span data-ttu-id="50949-334">Membro aritmetico i vincoli e F # confronto sono standard per la programmazione F #.</span><span class="sxs-lookup"><span data-stu-id="50949-334">Arithmetic member constraints and F# comparison constraints are a standard for F# programming.</span></span> <span data-ttu-id="50949-335">Si consideri il codice di esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="50949-335">For example, consider the following code:</span></span>

```fsharp
let inline highestCommonFactor a b =
    let rec loop a b =
        if a = LanguagePrimitives.GenericZero<_> then b
        elif a < b then loop a (b - a)
        else loop (a - b) b
    loop a b
```

<span data-ttu-id="50949-336">Il tipo di questa funzione è come segue:</span><span class="sxs-lookup"><span data-stu-id="50949-336">The type of this function is as follows:</span></span>

```fsharp
val inline highestCommonFactor : ^T -> ^T -> ^T
                when ^T : (static member Zero : ^T)
                and ^T : (static member ( - ) : ^T * ^T -> ^T)
                and ^T : equality
                and ^T : comparison
```

<span data-ttu-id="50949-337">Si tratta di una funzione appropriata per un'API pubblica in una libreria matematica.</span><span class="sxs-lookup"><span data-stu-id="50949-337">This is a suitable function for a public API in a mathematical library.</span></span>

#### <a name="avoid-using-member-constraints-to-simulate-type-classes-and-duck-typing"></a><span data-ttu-id="50949-338">Evitare di utilizzare i vincoli di membro per simulare le classi di tipo e duck digitando</span><span class="sxs-lookup"><span data-stu-id="50949-338">Avoid using member constraints to simulate type classes and duck typing</span></span>

<span data-ttu-id="50949-339">È possibile simulare "siete digitando" usando i vincoli di membro F #.</span><span class="sxs-lookup"><span data-stu-id="50949-339">It is possible to simulate “duck typing” using F# member constraints.</span></span> <span data-ttu-id="50949-340">Tuttavia, i membri che rendono l'utilizzo di questo generale in non deve essere usato in F #-a-progettazioni libreria F #.</span><span class="sxs-lookup"><span data-stu-id="50949-340">However, members that make use of this should not in general be used in F#-to-F# library designs.</span></span> <span data-ttu-id="50949-341">Questo avviene perché le progettazioni di libreria in base a vincoli impliciti sconosciuti o non standard tendono a causare problemi nel codice utente diventano flessibile e collegati al modello di un particolare framework.</span><span class="sxs-lookup"><span data-stu-id="50949-341">This is because library designs based on unfamiliar or non-standard implicit constraints tend to cause user code to become inflexible and tied to one particular framework pattern.</span></span>

<span data-ttu-id="50949-342">Inoltre, è probabile che un uso massiccio di vincoli di membro in questo modo può comportare tempi di compilazione molto lunghi.</span><span class="sxs-lookup"><span data-stu-id="50949-342">Additionally, there is a good chance that heavy use of member constraints in this manner can result in very long compile times.</span></span>

### <a name="operator-definitions"></a><span data-ttu-id="50949-343">Definizioni di operatore</span><span class="sxs-lookup"><span data-stu-id="50949-343">Operator Definitions</span></span>

#### <a name="avoid-defining-custom-symbolic-operators"></a><span data-ttu-id="50949-344">Evitare di definire gli operatori simbolici personalizzati</span><span class="sxs-lookup"><span data-stu-id="50949-344">Avoid defining custom symbolic operators</span></span>

<span data-ttu-id="50949-345">Gli operatori personalizzati sono essenziali in alcune situazioni e sono estremamente utili dispositivi notazionale in gran parte del codice di implementazione.</span><span class="sxs-lookup"><span data-stu-id="50949-345">Custom operators are essential in some situations and are highly useful notational devices within a large body of implementation code.</span></span> <span data-ttu-id="50949-346">Per i nuovi utenti di una libreria, denominate funzioni sono spesso più facile da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="50949-346">For new users of a library, named functions are often easier to use.</span></span> <span data-ttu-id="50949-347">Inoltre, gli operatori simbolici personalizzati possono essere difficili da documento e gli utenti riscontrano più difficile per la ricerca della Guida sugli operatori, a causa di limitazioni esistenti nei motori di ricerca e IDE.</span><span class="sxs-lookup"><span data-stu-id="50949-347">In addition, custom symbolic operators can be hard to document, and users find it more difficult to look up help on operators, due to existing limitations in IDE and search engines.</span></span>

<span data-ttu-id="50949-348">Di conseguenza, si consiglia di pubblicare la funzionalità come funzioni denominate e i membri e inoltre esporre operatori per questa funzionalità solo se i vantaggi di annotazione che superano la documentazione e costo cognitivo contenente vincoli.</span><span class="sxs-lookup"><span data-stu-id="50949-348">As a result, it is best to publish your functionality as named functions and members, and additionally expose operators for this functionality only if the notational benefits outweigh the documentation and cognitive cost of having them.</span></span>

### <a name="units-of-measure"></a><span data-ttu-id="50949-349">Unità di misura</span><span class="sxs-lookup"><span data-stu-id="50949-349">Units of Measure</span></span>

#### <a name="carefully-use-units-of-measure-for-added-type-safety-in-f-code"></a><span data-ttu-id="50949-350">Attentamente utilizzare unità di misura per motivi di sicurezza di tipo aggiunto nel codice F #</span><span class="sxs-lookup"><span data-stu-id="50949-350">Carefully use units of measure for added type safety in F# code</span></span>

<span data-ttu-id="50949-351">Informazioni di tipizzazione aggiuntive per le unità di misura viene cancellate quando visualizzati da altri linguaggi .NET.</span><span class="sxs-lookup"><span data-stu-id="50949-351">Additional typing information for units of measure is erased when viewed by other .NET languages.</span></span> <span data-ttu-id="50949-352">Tenere presente che la reflection, strumenti e componenti .NET verranno visualizzati i tipi di reti SAN unità.</span><span class="sxs-lookup"><span data-stu-id="50949-352">Be aware that .NET components, tools, and reflection will see types-sans-units.</span></span> <span data-ttu-id="50949-353">Ad esempio, verrà visualizzato c# consumer `float` anziché `float<kg>`.</span><span class="sxs-lookup"><span data-stu-id="50949-353">For example, C# consumers will see `float` rather than `float<kg>`.</span></span>

### <a name="type-abbreviations"></a><span data-ttu-id="50949-354">Abbreviazioni dei tipi</span><span class="sxs-lookup"><span data-stu-id="50949-354">Type Abbreviations</span></span>

#### <a name="carefully-use-type-abbreviations-to-simplify-f-code"></a><span data-ttu-id="50949-355">Usare con attenzione le abbreviazioni di tipo per semplificare il codice F #</span><span class="sxs-lookup"><span data-stu-id="50949-355">Carefully use type abbreviations to simplify F# code</span></span>

<span data-ttu-id="50949-356">La reflection, strumenti e componenti .NET non visualizzeranno i nomi abbreviati per i tipi.</span><span class="sxs-lookup"><span data-stu-id="50949-356">.NET components, tools, and reflection will not see abbreviated names for types.</span></span> <span data-ttu-id="50949-357">Utilizzo significativo di abbreviazioni dei tipi può inoltre effettuare un dominio vengono visualizzati più complessa di quanto effettivamente, che potrebbe confondere i consumer.</span><span class="sxs-lookup"><span data-stu-id="50949-357">Significant usage of type abbreviations can also make a domain appear more complex than it actually is, which could confuse consumers.</span></span>

#### <a name="avoid-type-abbreviations-for-public-types-whose-members-and-properties-should-be-intrinsically-different-to-those-available-on-the-type-being-abbreviated"></a><span data-ttu-id="50949-358">Evitare le abbreviazioni di tipo per cui i membri e le proprietà devono essere intrinsecamente diversi a quelli disponibili in tipo da abbreviare i tipi pubblici</span><span class="sxs-lookup"><span data-stu-id="50949-358">Avoid type abbreviations for public types whose members and properties should be intrinsically different to those available on the type being abbreviated</span></span>

<span data-ttu-id="50949-359">In questo caso, il tipo da abbreviare rivela troppo sulla rappresentazione del tipo effettivo in fase di definizione.</span><span class="sxs-lookup"><span data-stu-id="50949-359">In this case, the type being abbreviated reveals too much about the representation of the actual type being defined.</span></span> <span data-ttu-id="50949-360">Al contrario, provare a disposizione l'abbreviazione in un tipo di classe o un'unione discriminata case singolo (oppure, quando le prestazioni sono essenziali, provare a usare un tipo di struct per eseguire il wrapping l'abbreviazione).</span><span class="sxs-lookup"><span data-stu-id="50949-360">Instead, consider wrapping the abbreviation in a class type or a single-case discriminated union (or, when performance is essential, consider using a struct type to wrap the abbreviation).</span></span>

<span data-ttu-id="50949-361">Ad esempio, risulta vantaggioso per definire una multi-mappa come un caso speciale di una mappa di F #, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="50949-361">For example, it is tempting to define a multi-map as a special case of an F# map, for example:</span></span>

```fsharp
type MultiMap<'Key,'Value> = Map<'Key,'Value list>
```

<span data-ttu-id="50949-362">Tuttavia, le operazioni di notazione con punto logico per questo tipo non sono le stesse operazioni su una mappa, ad esempio, è ragionevole che l'operatore di ricerca siano mappati. [chiave] restituito l'elenco vuoto se la chiave non è presente nel dizionario, anziché generare un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="50949-362">However, the logical dot-notation operations on this type are not the same as the operations on a Map – for example, it is reasonable that the lookup operator map.[key] return the empty list if the key is not in the dictionary, rather than raising an exception.</span></span>

## <a name="guidelines-for-libraries-for-use-from-other-net-languages"></a><span data-ttu-id="50949-363">Linee guida per le librerie per usarle da altri linguaggi .NET</span><span class="sxs-lookup"><span data-stu-id="50949-363">Guidelines for libraries for Use from other .NET Languages</span></span>

<span data-ttu-id="50949-364">Quando si progettano le librerie per usarle da altri linguaggi .NET, è importante rispettare la [indicazioni per la progettazione di librerie .NET](../../standard/design-guidelines/index.md).</span><span class="sxs-lookup"><span data-stu-id="50949-364">When designing libraries for use from other .NET languages, it is important to adhere to the [.NET Library Design Guidelines](../../standard/design-guidelines/index.md).</span></span> <span data-ttu-id="50949-365">In questo documento, queste librerie sono contrassegnate come vaniglia librerie .NET, a differenza di F #-rivolti verso librerie che utilizzano F # costruisce senza alcuna restrizione.</span><span class="sxs-lookup"><span data-stu-id="50949-365">In this document, these libraries are labeled as vanilla .NET libraries, as opposed to F#-facing libraries that use F# constructs without restriction.</span></span> <span data-ttu-id="50949-366">Progettazione di librerie .NET vaniglia significa che fornisce le API di acquisire familiare e idiomatiche coerente con il resto di .NET Framework riducendo al minimo l'utilizzo di F #-costrutti specifici nell'API pubblica.</span><span class="sxs-lookup"><span data-stu-id="50949-366">Designing vanilla .NET libraries means providing familiar and idiomatic APIs consistent with the rest of the .NET Framework by minimizing the use of F#-specific constructs in the public API.</span></span> <span data-ttu-id="50949-367">Le regole sono illustrate nelle sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="50949-367">The rules are explained in the following sections.</span></span>

### <a name="namespace-and-type-design-for-libraries-for-use-from-other-net-languages"></a><span data-ttu-id="50949-368">Progettazione Namespace e tipo (per le librerie per l'utilizzo da parte di altri linguaggi .NET)</span><span class="sxs-lookup"><span data-stu-id="50949-368">Namespace and Type design (for libraries for use from other .NET Languages)</span></span>

#### <a name="apply-the-net-naming-conventions-to-the-public-api-of-your-components"></a><span data-ttu-id="50949-369">Applicare le convenzioni di denominazione .NET per l'API pubblica i componenti di</span><span class="sxs-lookup"><span data-stu-id="50949-369">Apply the .NET naming conventions to the public API of your components</span></span>

<span data-ttu-id="50949-370">Prestare particolare attenzione all'uso di nomi abbreviati e linee guida di maiuscole/minuscole di .NET.</span><span class="sxs-lookup"><span data-stu-id="50949-370">Pay special attention to the use of abbreviated names and the .NET capitalization guidelines.</span></span>

```fsharp
type pCoord = ...
    member this.theta = ...

type PolarCoordinate = ...
    member this.Theta = ...
```

#### <a name="use-namespaces-types-and-members-as-the-primary-organizational-structure-for-your-components"></a><span data-ttu-id="50949-371">Usare gli spazi dei nomi, tipi e membri come la struttura organizzativa primaria per i componenti</span><span class="sxs-lookup"><span data-stu-id="50949-371">Use namespaces, types, and members as the primary organizational structure for your components</span></span>

<span data-ttu-id="50949-372">Tutti i file che contiene la funzionalità pubblica devono iniziare con un `namespace` dichiarazione e l'unica entità pubblici negli spazi dei nomi devono essere tipi.</span><span class="sxs-lookup"><span data-stu-id="50949-372">All files containing public functionality should begin with a `namespace` declaration, and the only public-facing entities in namespaces should be types.</span></span> <span data-ttu-id="50949-373">Non usare i moduli di F #.</span><span class="sxs-lookup"><span data-stu-id="50949-373">Do not use F# modules.</span></span>

<span data-ttu-id="50949-374">Usare i moduli non pubblici per contenere il codice di implementazione, tipi di utilità e funzioni di utilità.</span><span class="sxs-lookup"><span data-stu-id="50949-374">Use non-public modules to hold implementation code, utility types, and utility functions.</span></span>

<span data-ttu-id="50949-375">I tipi statici devono essere Preferiti moduli, quanto in questo modo per future evoluzione dell'API per utilizzare l'overload e altri concetti di progettazione di API .NET che non possono essere utilizzati all'interno di moduli di F #.</span><span class="sxs-lookup"><span data-stu-id="50949-375">Static types should be preferred over modules, as they allow for future evolution of the API to use overloading and other .NET API design concepts that may not be used within F# modules.</span></span>

<span data-ttu-id="50949-376">Ad esempio, al posto dell'API pubblica seguente:</span><span class="sxs-lookup"><span data-stu-id="50949-376">For example, in place of the following public API:</span></span>

```fsharp
module Fabrikam

module Utilities =
    let Name = "Bob"
    let Add2 x y = x + y
    let Add3 x y z = x + y + z
```

<span data-ttu-id="50949-377">Si consideri invece:</span><span class="sxs-lookup"><span data-stu-id="50949-377">Consider instead:</span></span>

```fsharp
namespace Fabrikam

[<AbstractClass; Sealed>]
type Utilities =
    static member Name = "Bob"
    static member Add(x,y) = x + y
    static member Add(x,y,z) = x + y + z
```

#### <a name="use-f-record-types-in-vanilla-net-apis-if-the-design-of-the-types-wont-evolve"></a><span data-ttu-id="50949-378">Utilizzare i tipi di record F # in vaniglia API .NET se la progettazione dei tipi non evolvere</span><span class="sxs-lookup"><span data-stu-id="50949-378">Use F# record types in vanilla .NET APIs if the design of the types won't evolve</span></span>

<span data-ttu-id="50949-379">I tipi di record F # possono essere compilate in una classe .NET semplice.</span><span class="sxs-lookup"><span data-stu-id="50949-379">F# record types compile to a simple .NET class.</span></span> <span data-ttu-id="50949-380">Questi sono adatti per alcuni tipi semplici, stabili per le API.</span><span class="sxs-lookup"><span data-stu-id="50949-380">These are suitable for some simple, stable types in APIs.</span></span> <span data-ttu-id="50949-381">È consigliabile usare la `[<NoEquality>]` e `[<NoComparison>]` gli attributi per eliminare la generazione automatica di interfacce.</span><span class="sxs-lookup"><span data-stu-id="50949-381">You should consider using the `[<NoEquality>]` and `[<NoComparison>]` attributes to suppress the automatic generation of interfaces.</span></span> <span data-ttu-id="50949-382">Evitare anche i campi modificabili record vaniglia API .NET come questi espone un campo pubblico.</span><span class="sxs-lookup"><span data-stu-id="50949-382">Also avoid using mutable record fields in vanilla .NET APIs as these exposes a public field.</span></span> <span data-ttu-id="50949-383">Considerare sempre se una classe fornisce un'opzione più flessibile per evoluzione futura dell'API.</span><span class="sxs-lookup"><span data-stu-id="50949-383">Always consider whether a class would provide a more flexible option for future evolution of the API.</span></span>

<span data-ttu-id="50949-384">Ad esempio, il seguente codice F # espone l'API pubblica a un consumer in c#:</span><span class="sxs-lookup"><span data-stu-id="50949-384">For example, the following F# code exposes the public API to a C# consumer:</span></span>

<span data-ttu-id="50949-385">F #:</span><span class="sxs-lookup"><span data-stu-id="50949-385">F#:</span></span>

```fsharp
[<NoEquality; NoComparison>]
type MyRecord =
    { FirstThing : int
        SecondThing : string }
```

<span data-ttu-id="50949-386">C#:</span><span class="sxs-lookup"><span data-stu-id="50949-386">C#:</span></span>

```csharp
public sealed class MyRecord
{
    public MyRecord(int firstThing, string secondThing);
    public int FirstThing { get; }
    public string SecondThing { get; }
}
```

#### <a name="hide-the-representation-of-f-union-types-in-vanilla-net-apis"></a><span data-ttu-id="50949-387">Nascondere la rappresentazione di tipi unione F # in vaniglia API .NET</span><span class="sxs-lookup"><span data-stu-id="50949-387">Hide the representation of F# union types in vanilla .NET APIs</span></span>

<span data-ttu-id="50949-388">Tipi di unione F # non vengono comunemente utilizzati tra i limiti dei componenti, anche per F #-a-F # la generazione di codice.</span><span class="sxs-lookup"><span data-stu-id="50949-388">F# union types are not commonly used across component boundaries, even for F#-to-F# coding.</span></span> <span data-ttu-id="50949-389">Si tratta di un dispositivo di implementazione eccellente quando utilizzato internamente nell'ambito dei componenti e le librerie.</span><span class="sxs-lookup"><span data-stu-id="50949-389">They are an excellent implementation device when used internally within components and libraries.</span></span>

<span data-ttu-id="50949-390">Quando si progetta un vaniglia API .NET, è consigliabile nascondere la rappresentazione di un tipo di unione con una dichiarazione privata o un file della firma.</span><span class="sxs-lookup"><span data-stu-id="50949-390">When designing a vanilla .NET API, consider hiding the representation of a union type by using either a private declaration or a signature file.</span></span>

```fsharp
type PropLogic =
    private
    | And of PropLogic * PropLogic
    | Not of PropLogic
    | True
```

<span data-ttu-id="50949-391">È inoltre possono integrare i tipi che utilizzano internamente una rappresentazione in forma unione con i membri per fornire un desiderato. API con connessione di rete.</span><span class="sxs-lookup"><span data-stu-id="50949-391">You may also augment types that use a union representation internally with members to provide a desired .NET-facing API.</span></span>

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

#### <a name="design-gui-and-other-components-using-the-design-patterns-of-the-framework"></a><span data-ttu-id="50949-392">Progettazione grafica e altri componenti mediante i modelli di progettazione di framework</span><span class="sxs-lookup"><span data-stu-id="50949-392">Design GUI and other components using the design patterns of the framework</span></span>

<span data-ttu-id="50949-393">Sono disponibili numerosi Framework diversi all'interno di .NET, ad esempio Windows Form, WPF e ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="50949-393">There are many different frameworks available within .NET, such as WinForms, WPF, and ASP.NET.</span></span> <span data-ttu-id="50949-394">Convenzioni di denominazione e di progettazione per ogni devono essere utilizzate se si progettano i componenti per l'utilizzo di questi Framework.</span><span class="sxs-lookup"><span data-stu-id="50949-394">Naming and design conventions for each should be used if you are designing components for use in these frameworks.</span></span> <span data-ttu-id="50949-395">Ad esempio, per la programmazione WPF, adottare i modelli di progettazione WPF per le classi che si sta progettando.</span><span class="sxs-lookup"><span data-stu-id="50949-395">For example, for WPF programming, adopt WPF design patterns for the classes you are designing.</span></span> <span data-ttu-id="50949-396">Per i modelli di programmazione dell'interfaccia utente, usare i modelli di progettazione, ad esempio gli eventi e le raccolte basato sulla notifica, ad esempio quelli disponibili in <xref:System.Collections.ObjectModel>.</span><span class="sxs-lookup"><span data-stu-id="50949-396">For models in user interface programming, use design patterns such as events and notification-based collections such as those found in <xref:System.Collections.ObjectModel>.</span></span>

### <a name="object-and-member-design-for-libraries-for-use-from-other-net-languages"></a><span data-ttu-id="50949-397">Progettazione di oggetti e membri (per le librerie per l'utilizzo da parte di altri linguaggi .NET)</span><span class="sxs-lookup"><span data-stu-id="50949-397">Object and Member design (for libraries for use from other .NET Languages)</span></span>

#### <a name="use-the-clievent-attribute-to-expose-net-events"></a><span data-ttu-id="50949-398">Usare l'attributo CLIEvent per esporre gli eventi di .NET</span><span class="sxs-lookup"><span data-stu-id="50949-398">Use the CLIEvent attribute to expose .NET events</span></span>

<span data-ttu-id="50949-399">Costruire un `DelegateEvent` con una specifica di .NET tipo delegato System. che accetta un oggetto e `EventArgs` (anziché un' `Event`, che utilizza solo il `FSharpHandler` tipo per impostazione predefinita), in modo che gli eventi vengono pubblicati in modo familiare ad altri linguaggi .NET.</span><span class="sxs-lookup"><span data-stu-id="50949-399">Construct a `DelegateEvent` with a specific .NET delegate type that takes an object and `EventArgs` (rather than an `Event`, which just uses the `FSharpHandler` type by default) so that the events are published in the familiar way to other .NET languages.</span></span>

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

#### <a name="expose-asynchronous-operations-as-methods-which-return-net-tasks"></a><span data-ttu-id="50949-400">Esporre operazioni asincrone dei metodi che restituiscono le attività di .NET</span><span class="sxs-lookup"><span data-stu-id="50949-400">Expose asynchronous operations as methods which return .NET tasks</span></span>

<span data-ttu-id="50949-401">Le attività vengono utilizzate in .NET per rappresentare i calcoli asincroni attivi.</span><span class="sxs-lookup"><span data-stu-id="50949-401">Tasks are used in .NET to represent active asynchronous computations.</span></span> <span data-ttu-id="50949-402">Le attività sono in genere meno compositiva rispetto a F # `Async<T>` oggetti, poiché rappresentano le attività "già in esecuzione" e non può essere composto da insieme in modi che eseguire la composizione parallele o cui nascondere la propagazione dei segnali di annullamento e le altre parametri di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="50949-402">Tasks are in general less compositional than F# `Async<T>` objects, since they represent “already executing” tasks and can’t be composed together in ways that perform parallel composition, or which hide the propagation of cancellation signals and other contextual parameters.</span></span>

<span data-ttu-id="50949-403">Tuttavia, nonostante ciò, i metodi che restituiscono le attività sono la rappresentazione standard della programmazione asincrona in .NET.</span><span class="sxs-lookup"><span data-stu-id="50949-403">However, despite this, methods which return Tasks are the standard representation of asynchronous programming on .NET.</span></span>

```fsharp
/// A type in a component designed for use from other .NET languages
type MyType() =

    let compute (x: int) : Async<int> = async { ... }

    member this.ComputeAsync(x) = compute x |> Async.StartAsTask
```

<span data-ttu-id="50949-404">Sarà spesso si desidera anche accettare un token di annullamento esplicito:</span><span class="sxs-lookup"><span data-stu-id="50949-404">You will frequently also want to accept an explicit cancellation token:</span></span>

```fsharp
/// A type in a component designed for use from other .NET languages
type MyType() =
    let compute(x:int) : Async<int> = async { ... }
    member this.ComputeAsTask(x, cancellationToken) = Async.StartAsTask(compute x, cancellationToken)
```

#### <a name="use-net-delegate-types-instead-of-f-function-types"></a><span data-ttu-id="50949-405">Utilizzare i tipi delegati di .NET anziché i tipi F # (funzione)</span><span class="sxs-lookup"><span data-stu-id="50949-405">Use .NET delegate types instead of F# function types</span></span>

<span data-ttu-id="50949-406">Di seguito "tipi di funzione F #" indicano i tipi "freccia" quali `int -> int`.</span><span class="sxs-lookup"><span data-stu-id="50949-406">Here “F# function types” mean “arrow” types like `int -> int`.</span></span>

<span data-ttu-id="50949-407">Anziché il seguente:</span><span class="sxs-lookup"><span data-stu-id="50949-407">Instead of this:</span></span>

```fsharp
member this.Transform(f:int->int) =
    ...
```

<span data-ttu-id="50949-408">Eseguire questa operazione:</span><span class="sxs-lookup"><span data-stu-id="50949-408">Do this:</span></span>

```fsharp
member this.Transform(f:Func<int,int>) =
    ...
```

<span data-ttu-id="50949-409">Il tipo di funzione F # viene visualizzato come `class FSharpFunc<T,U>` ad altri linguaggi .NET, senza che sia meno idoneo alla funzionalità del linguaggio e gli strumenti che supportano i tipi delegati.</span><span class="sxs-lookup"><span data-stu-id="50949-409">The F# function type appears as `class FSharpFunc<T,U>` to other .NET languages, and is less suitable for language features and tooling that understand delegate types.</span></span> <span data-ttu-id="50949-410">Durante la creazione di un metodo di ordine superiore destinati a .NET Framework 3.5 o versione successiva, il `System.Func` e `System.Action` i delegati sono le API per la pubblicazione per consentire agli sviluppatori di .NET utilizzare queste API in modo semplice a destra.</span><span class="sxs-lookup"><span data-stu-id="50949-410">When authoring a higher-order method targeting .NET Framework 3.5 or higher, the `System.Func` and `System.Action` delegates are the right APIs to publish to enable .NET developers to consume these APIs in a low-friction manner.</span></span> <span data-ttu-id="50949-411">(Quando la destinazione è .NET Framework 2.0, i tipi delegati definiti dal sistema sono più limitati, provare a utilizzare i tipi delegati predefiniti, ad esempio `System.Converter<T,U>` o definizione di un tipo delegato specifico.)</span><span class="sxs-lookup"><span data-stu-id="50949-411">(When targeting .NET Framework 2.0, the system-defined delegate types are more limited; consider using predefined delegate types such as `System.Converter<T,U>` or defining a specific delegate type.)</span></span>

<span data-ttu-id="50949-412">Sul lato di scorrimento, i delegati di .NET non sono naturali per F #-rivolti verso librerie (vedere la sezione successiva in F #-rivolti verso librerie).</span><span class="sxs-lookup"><span data-stu-id="50949-412">On the flip side, .NET delegates are not natural for F#-facing libraries (see the next Section on F#-facing libraries).</span></span> <span data-ttu-id="50949-413">Di conseguenza, una strategia di implementazione comune quando si sviluppano i metodi di ordine superiore per le librerie .NET vaniglia consiste nel creare tutti l'implementazione tramite tipi di funzioni F # e quindi l'API pubblica mediante delegati come facciata thin sopra effettivo F # implementazione.</span><span class="sxs-lookup"><span data-stu-id="50949-413">As a result, a common implementation strategy when developing higher-order methods for vanilla .NET libraries is to author all the implementation using F# function types, and then create the public API using delegates as a thin façade atop the actual F# implementation.</span></span>

#### <a name="use-the-trygetvalue-pattern-instead-of-returning-f-option-values-and-prefer-method-overloading-to-taking-f-option-values-as-arguments"></a><span data-ttu-id="50949-414">Utilizzare il modello di TryGetValue anziché restituire i valori delle opzioni F # e preferisce overload ad accettare i valori dell'opzione F # come argomenti</span><span class="sxs-lookup"><span data-stu-id="50949-414">Use the TryGetValue pattern instead of returning F# option values, and prefer method overloading to taking F# option values as arguments</span></span>

<span data-ttu-id="50949-415">Modelli comuni di utilizzo per il tipo di opzione F # per le API sono migliori implementato in vaniglia tecniche di progettazione API .NET usando .NET standard.</span><span class="sxs-lookup"><span data-stu-id="50949-415">Common patterns of use for the F# option type in APIs are better implemented in vanilla .NET APIs using standard .NET design techniques.</span></span> <span data-ttu-id="50949-416">Anziché restituire un valore dell'opzione F #, provare a utilizzare il tipo restituito bool oltre a un parametro out come il modello "TryGetValue".</span><span class="sxs-lookup"><span data-stu-id="50949-416">Instead of returning an F# option value, consider using the bool return type plus an out parameter as in the "TryGetValue" pattern.</span></span> <span data-ttu-id="50949-417">E, anziché utilizzare valori di opzione F # come parametri, è consigliabile utilizzare l'overload di metodo o argomenti facoltativi.</span><span class="sxs-lookup"><span data-stu-id="50949-417">And instead of taking F# option values as parameters, consider using method overloading or optional arguments.</span></span>

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

#### <a name="use-the-net-collection-interface-types-ienumerablet-and-idictionarykeyvalue-for-parameters-and-return-values"></a><span data-ttu-id="50949-418">Utilizzare l'interfaccia di raccolta .NET tipi IEnumerable\<T\> e IDictionary\<chiave, valore\> per i parametri e valori restituiti</span><span class="sxs-lookup"><span data-stu-id="50949-418">Use the .NET collection interface types IEnumerable\<T\> and IDictionary\<Key,Value\> for parameters and return values</span></span>

<span data-ttu-id="50949-419">Evitare l'utilizzo di tipi di raccolta concreti, ad esempio matrici .NET `T[]`, i tipi F # `list<T>`, `Map<Key,Value>` e `Set<T>`, e tipi di raccolta concreta .NET come `Dictionary<Key,Value>`.</span><span class="sxs-lookup"><span data-stu-id="50949-419">Avoid the use of concrete collection types such as .NET arrays `T[]`, F# types `list<T>`, `Map<Key,Value>` and `Set<T>`, and .NET concrete collection types such as `Dictionary<Key,Value>`.</span></span> <span data-ttu-id="50949-420">La finestra di progettazione libreria .NET sono buoni consigli relative all'utilizzo di diversi tipi di raccolta, ad esempio `IEnumerable<T>`.</span><span class="sxs-lookup"><span data-stu-id="50949-420">The .NET Library Design Guidelines have good advice regarding when to use various collection types like `IEnumerable<T>`.</span></span> <span data-ttu-id="50949-421">Utilizzato per scopi di matrici (`T[]`) è accettabile in alcuni casi, per motivi di prestazioni.</span><span class="sxs-lookup"><span data-stu-id="50949-421">Some use of arrays (`T[]`) is acceptable in some circumstances, on performance grounds.</span></span> <span data-ttu-id="50949-422">Si noti che in particolare `seq<T>` è semplicemente F # alias per `IEnumerable<T>`, e pertanto seq è spesso un tipo appropriato per un vaniglia API .NET.</span><span class="sxs-lookup"><span data-stu-id="50949-422">Note especially that `seq<T>` is just the F# alias for `IEnumerable<T>`, and thus seq is often an appropriate type for a vanilla .NET API.</span></span>

<span data-ttu-id="50949-423">Invece di F # Elenca:</span><span class="sxs-lookup"><span data-stu-id="50949-423">Instead of F# lists:</span></span>

```fsharp
member this.PrintNames(names : string list) =
    ...
```

<span data-ttu-id="50949-424">Usare le sequenze di F #:</span><span class="sxs-lookup"><span data-stu-id="50949-424">Use F# sequences:</span></span>

```fsharp
member this.PrintNames(names : seq<string>) =
    ...
```

#### <a name="use-the-unit-type-as-the-only-input-type-of-a-method-to-define-a-zero-argument-method-or-as-the-only-return-type-to-define-a-void-returning-method"></a><span data-ttu-id="50949-425">Utilizzare il tipo di unità come unico tipo di input di un metodo per definire un metodo con argomenti di zero o come l'unico tipo per definire un metodo che restituisce void restituito</span><span class="sxs-lookup"><span data-stu-id="50949-425">Use the unit type as the only input type of a method to define a zero-argument method, or as the only return type to define a void-returning method</span></span>

<span data-ttu-id="50949-426">Evitare di altri utilizzi del tipo di unità.</span><span class="sxs-lookup"><span data-stu-id="50949-426">Avoid other uses of the unit type.</span></span> <span data-ttu-id="50949-427">Si tratta buona:</span><span class="sxs-lookup"><span data-stu-id="50949-427">These are good:</span></span>

```fsharp
✔ member this.NoArguments() = 3

✔ member this.ReturnVoid(x : int) = ()
```

<span data-ttu-id="50949-428">Si tratta non valida:</span><span class="sxs-lookup"><span data-stu-id="50949-428">This is bad:</span></span>

```fsharp
member this.WrongUnit( x:unit, z:int) = ((), ())
```

#### <a name="check-for-null-values-on-vanilla-net-api-boundaries"></a><span data-ttu-id="50949-429">Verificare la presenza di valori null nei limiti di vaniglia API .NET</span><span class="sxs-lookup"><span data-stu-id="50949-429">Check for null values on vanilla .NET API boundaries</span></span>

<span data-ttu-id="50949-430">Codice di implementazione di F # tenderà ad avere meno valori null, a causa di limitazioni sull'utilizzo di valori letterali null per i tipi F # e modelli di progettazione non modificabile.</span><span class="sxs-lookup"><span data-stu-id="50949-430">F# implementation code tends to have fewer null values, due to immutable design patterns and restrictions on use of null literals for F# types.</span></span> <span data-ttu-id="50949-431">Altri linguaggi .NET utilizzano null come valore molto più frequente.</span><span class="sxs-lookup"><span data-stu-id="50949-431">Other .NET languages often use null as a value much more frequently.</span></span> <span data-ttu-id="50949-432">Per questo motivo, codice F # che espone un'API .NET di vaniglia deve controllare i parametri per i valori null in corrispondenza del limite di API e impedire che questi valori pervengono più profondo il codice di implementazione di F #.</span><span class="sxs-lookup"><span data-stu-id="50949-432">Because of this, F# code that is exposing a vanilla .NET API should check parameters for null at the API boundary, and prevent these values from flowing deeper into the F# implementation code.</span></span> <span data-ttu-id="50949-433">Il `isNull` funzione o criteri di ricerca nel `null` modello può essere usato.</span><span class="sxs-lookup"><span data-stu-id="50949-433">The `isNull` function or pattern matching on the `null` pattern can be used.</span></span>

```fsharp
let checkNonNull argName (arg: obj) =
    match arg with
    | null -> nullArg argName
    | _ -> ()

let checkNonNull` argName (arg: obj) =
    if isNull arg then nullArg argName
    else ()
```

#### <a name="avoid-using-tuples-as-return-values"></a><span data-ttu-id="50949-434">Evitare di utilizzare le tuple come valori restituiti</span><span class="sxs-lookup"><span data-stu-id="50949-434">Avoid using tuples as return values</span></span>

<span data-ttu-id="50949-435">Invece, preferire la restituzione di un tipo denominato che contiene i dati aggregati o tramite i parametri out per restituire più valori.</span><span class="sxs-lookup"><span data-stu-id="50949-435">Instead, prefer returning a named type holding the aggregate data, or using out parameters to return multiple values.</span></span> <span data-ttu-id="50949-436">Anche se tuple e tuple struct esistano in .NET (incluso il supporto di linguaggio c# per le tuple struct), spesso non fornirà del ideale e previsto dell'API per gli sviluppatori di .NET.</span><span class="sxs-lookup"><span data-stu-id="50949-436">Although tuples and struct tuples exist in .NET (including C# language support for struct tuples), they will most often not provide the ideal and expected API for .NET developers.</span></span>

#### <a name="avoid-the-use-of-currying-of-parameters"></a><span data-ttu-id="50949-437">Evitare l'utilizzo di currying dei parametri</span><span class="sxs-lookup"><span data-stu-id="50949-437">Avoid the use of currying of parameters</span></span>

<span data-ttu-id="50949-438">In alternativa, utilizzare le convenzioni di chiamata .NET ``Method(arg1,arg2,…,argN)``.</span><span class="sxs-lookup"><span data-stu-id="50949-438">Instead, use .NET calling conventions ``Method(arg1,arg2,…,argN)``.</span></span>

```fsharp
member this.TupledArguments(str, num) = String.replicate num str
```

<span data-ttu-id="50949-439">Suggerimento: Se si sta progettando le librerie per usarle da qualsiasi linguaggio .NET, quindi non è alternativo pratica alcuni sperimentale in c# e Visual Basic di programmazione per garantire che le librerie "all'aspetto a destra" da questi linguaggi.</span><span class="sxs-lookup"><span data-stu-id="50949-439">Tip: If you’re designing libraries for use from any .NET language, then there’s no substitute for actually doing some experimental C# and Visual Basic programming to ensure that your libraries "feel right" from these languages.</span></span> <span data-ttu-id="50949-440">È anche possibile utilizzare strumenti quali Reflector .NET e Visual Studio Visualizzatore per garantire che le librerie e la relativa documentazione vengono visualizzati come previsto per gli sviluppatori.</span><span class="sxs-lookup"><span data-stu-id="50949-440">You can also use tools such as .NET Reflector and the Visual Studio Object Browser to ensure that libraries and their documentation appear as expected to developers.</span></span>

## <a name="appendix"></a><span data-ttu-id="50949-441">Appendice</span><span class="sxs-lookup"><span data-stu-id="50949-441">Appendix</span></span>

### <a name="end-to-end-example-of-designing-f-code-for-use-by-other-net-languages"></a><span data-ttu-id="50949-442">Esempio end-to-end di progettazione di codice F # per l'utilizzo da altri linguaggi .NET</span><span class="sxs-lookup"><span data-stu-id="50949-442">End-to-end example of designing F# code for use by other .NET languages</span></span>

<span data-ttu-id="50949-443">Si consideri la classe seguente:</span><span class="sxs-lookup"><span data-stu-id="50949-443">Consider the following class:</span></span>

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

<span data-ttu-id="50949-444">Il tipo F # derivato di questa classe è il seguente:</span><span class="sxs-lookup"><span data-stu-id="50949-444">The inferred F# type of this class is as follows:</span></span>

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

<span data-ttu-id="50949-445">Esaminiamo un aspetto di questo tipo di F # a un programmatore che utilizza un altro linguaggio .NET.</span><span class="sxs-lookup"><span data-stu-id="50949-445">Let’s take a look at how this F# type appears to a programmer using another .NET language.</span></span> <span data-ttu-id="50949-446">Ad esempio, approssimativo c# "firma" è come segue:</span><span class="sxs-lookup"><span data-stu-id="50949-446">For example, the approximate C# “signature” is as follows:</span></span>

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

<span data-ttu-id="50949-447">Esistono alcuni aspetti importanti da notare in modo F # rappresenta costrutti qui.</span><span class="sxs-lookup"><span data-stu-id="50949-447">There are some important points to notice about how F# represents constructs here.</span></span> <span data-ttu-id="50949-448">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="50949-448">For example:</span></span>

* <span data-ttu-id="50949-449">I metadati, ad esempio i nomi degli argomenti sono stato mantenuto.</span><span class="sxs-lookup"><span data-stu-id="50949-449">Metadata such as argument names has been preserved.</span></span>

* <span data-ttu-id="50949-450">Metodi di F # che accettano due argomenti diventano c# i metodi che accettano due argomenti.</span><span class="sxs-lookup"><span data-stu-id="50949-450">F# methods that take two arguments become C# methods that take two arguments.</span></span>

* <span data-ttu-id="50949-451">Funzioni e gli elenchi diventano i riferimenti ai tipi corrispondenti nella libreria F #.</span><span class="sxs-lookup"><span data-stu-id="50949-451">Functions and lists become references to corresponding types in the F# library.</span></span>

<span data-ttu-id="50949-452">Il codice seguente viene illustrato come modificare il codice per tener conto di queste operazioni.</span><span class="sxs-lookup"><span data-stu-id="50949-452">The following code shows how to adjust this code to take these things into account.</span></span>

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

<span data-ttu-id="50949-453">Il tipo F # derivato del codice è il seguente:</span><span class="sxs-lookup"><span data-stu-id="50949-453">The inferred F# type of the code is as follows:</span></span>

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

<span data-ttu-id="50949-454">La firma c# viene ora come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="50949-454">The C# signature is now as follows:</span></span>

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

<span data-ttu-id="50949-455">Le correzioni apportate preparare questo tipo per l'uso come parte di una libreria .NET vaniglia sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="50949-455">The fixes made to prepare this type for use as part of a vanilla .NET library are as follows:</span></span>

* <span data-ttu-id="50949-456">Rettificato diversi nomi: `Point1`, `n`, `l`, e `f` è diventato `RadialPoint`, `count`, `factor`, e `transform`, rispettivamente.</span><span class="sxs-lookup"><span data-stu-id="50949-456">Adjusted several names: `Point1`, `n`, `l`, and `f` became `RadialPoint`, `count`, `factor`, and `transform`, respectively.</span></span>

* <span data-ttu-id="50949-457">Utilizzato un tipo restituito `seq<RadialPoint>` invece di `RadialPoint list` modificando un elenco della costruzione utilizzando `[ ... ]` a una sequenza di costruzione utilizzando `IEnumerable<RadialPoint>`.</span><span class="sxs-lookup"><span data-stu-id="50949-457">Used a return type of `seq<RadialPoint>` instead of `RadialPoint list` by changing a list construction using `[ ... ]` to a sequence construction using `IEnumerable<RadialPoint>`.</span></span>

* <span data-ttu-id="50949-458">Utilizzare il tipo di delegato .NET `System.Func` anziché un tipo di funzione F #.</span><span class="sxs-lookup"><span data-stu-id="50949-458">Used the .NET delegate type `System.Func` instead of an F# function type.</span></span>

<span data-ttu-id="50949-459">Questo rende molto coloro utilizzare nel codice c#.</span><span class="sxs-lookup"><span data-stu-id="50949-459">This makes it far nicer to consume in C# code.</span></span>

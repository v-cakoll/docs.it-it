---
title: Linee guida per la progettazione dei componenti F#
description: "Informazioni sulle linee guida per la scrittura di componenti F # destinati all'utilizzo da parte di altri chiamanti."
ms.date: 05/14/2018
ms.openlocfilehash: 590bda0660d54ea73c590d31e694f3d499e0fd9f
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83209136"
---
# <a name="f-component-design-guidelines"></a><span data-ttu-id="8f950-103">Linee guida per la progettazione dei componenti F#</span><span class="sxs-lookup"><span data-stu-id="8f950-103">F# component design guidelines</span></span>

<span data-ttu-id="8f950-104">Questo documento è un set di linee guida di progettazione di componenti per la programmazione F #, basate sulle linee guida di progettazione dei componenti F #, V14, Microsoft Research e una versione che è stata originariamente curata e gestita da F # Software Foundation.</span><span class="sxs-lookup"><span data-stu-id="8f950-104">This document is a set of component design guidelines for F# programming, based on the F# Component Design Guidelines, v14, Microsoft Research, and a version that was originally curated and maintained by the F# Software Foundation.</span></span>

<span data-ttu-id="8f950-105">In questo documento si presuppone che l'utente abbia familiarità con la programmazione F #.</span><span class="sxs-lookup"><span data-stu-id="8f950-105">This document assumes you are familiar with F# programming.</span></span> <span data-ttu-id="8f950-106">Molti ringraziano la community di F # per i loro contributi e commenti e suggerimenti utili su diverse versioni di questa guida.</span><span class="sxs-lookup"><span data-stu-id="8f950-106">Many thanks to the F# community for their contributions and helpful feedback on various versions of this guide.</span></span>

## <a name="overview"></a><span data-ttu-id="8f950-107">Panoramica</span><span class="sxs-lookup"><span data-stu-id="8f950-107">Overview</span></span>

<span data-ttu-id="8f950-108">In questo documento vengono esaminati alcuni problemi relativi alla progettazione e alla codifica dei componenti F #.</span><span class="sxs-lookup"><span data-stu-id="8f950-108">This document looks at some of the issues related to F# component design and coding.</span></span> <span data-ttu-id="8f950-109">Un componente può indicare uno dei seguenti elementi:</span><span class="sxs-lookup"><span data-stu-id="8f950-109">A component can mean any of the following:</span></span>

* <span data-ttu-id="8f950-110">Livello nel progetto F # con consumer esterni all'interno del progetto.</span><span class="sxs-lookup"><span data-stu-id="8f950-110">A layer in your F# project that has external consumers within that project.</span></span>
* <span data-ttu-id="8f950-111">Libreria destinata all'utilizzo da parte del codice F # tra i limiti dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="8f950-111">A library intended for consumption by F# code across assembly boundaries.</span></span>
* <span data-ttu-id="8f950-112">Libreria destinata all'utilizzo da parte di qualsiasi linguaggio .NET tra i confini degli assembly.</span><span class="sxs-lookup"><span data-stu-id="8f950-112">A library intended for consumption by any .NET language across assembly boundaries.</span></span>
* <span data-ttu-id="8f950-113">Libreria destinata alla distribuzione tramite un repository di pacchetti, ad esempio [NuGet](https://nuget.org).</span><span class="sxs-lookup"><span data-stu-id="8f950-113">A library intended for distribution via a package repository, such as [NuGet](https://nuget.org).</span></span>

<span data-ttu-id="8f950-114">Le tecniche descritte in questo articolo seguono i [cinque principi del codice F # valido](index.md#five-principles-of-good-f-code)e quindi utilizzano la programmazione funzionale e di oggetti in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="8f950-114">Techniques described in this article follow the [Five principles of good F# code](index.md#five-principles-of-good-f-code), and thus utilize both functional and object programming as appropriate.</span></span>

<span data-ttu-id="8f950-115">Indipendentemente dalla metodologia, la finestra di progettazione di componenti e librerie affronta una serie di problemi pratici e prosaici quando si tenta di creare un'API più facilmente utilizzabile dagli sviluppatori.</span><span class="sxs-lookup"><span data-stu-id="8f950-115">Regardless of the methodology, the component and library designer faces a number of practical and prosaic issues when trying to craft an API that is most easily usable by developers.</span></span> <span data-ttu-id="8f950-116">L'applicazione coscienziosa delle [linee guida di progettazione della libreria .NET](../../standard/design-guidelines/index.md) consentirà di creare un set coerente di API gradevoli da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="8f950-116">Conscientious application of the [.NET Library Design Guidelines](../../standard/design-guidelines/index.md) will steer you towards creating a consistent set of APIs that are pleasant to consume.</span></span>

## <a name="general-guidelines"></a><span data-ttu-id="8f950-117">Linee guida generali</span><span class="sxs-lookup"><span data-stu-id="8f950-117">General guidelines</span></span>

<span data-ttu-id="8f950-118">Esistono alcune linee guida universali valide per le librerie F #, a prescindere dai destinatari della libreria.</span><span class="sxs-lookup"><span data-stu-id="8f950-118">There are a few universal guidelines that apply to F# libraries, regardless of the intended audience for the library.</span></span>

### <a name="learn-the-net-library-design-guidelines"></a><span data-ttu-id="8f950-119">Informazioni sulle linee guida di progettazione della libreria .NET</span><span class="sxs-lookup"><span data-stu-id="8f950-119">Learn the .NET Library Design Guidelines</span></span>

<span data-ttu-id="8f950-120">Indipendentemente dal tipo di codice F #, è importante avere una conoscenza pratica delle [linee guida di progettazione delle librerie .NET](../../standard/design-guidelines/index.md).</span><span class="sxs-lookup"><span data-stu-id="8f950-120">Regardless of the kind of F# coding you are doing, it is valuable to have a working knowledge of the [.NET Library Design Guidelines](../../standard/design-guidelines/index.md).</span></span> <span data-ttu-id="8f950-121">La maggior parte degli altri programmatori F # e .NET avrà una certa familiarità con queste linee guida e prevede che il codice .NET sia conforme.</span><span class="sxs-lookup"><span data-stu-id="8f950-121">Most other F# and .NET programmers will be familiar with these guidelines, and expect .NET code to conform to them.</span></span>

<span data-ttu-id="8f950-122">Le linee guida per la progettazione di librerie .NET forniscono indicazioni generali sulla denominazione, sulla progettazione di classi e interfacce, sulla progettazione di membri (proprietà, metodi, eventi e così via), oltre a un primo punto di riferimento utile per un'ampia gamma di linee guida di progettazione.</span><span class="sxs-lookup"><span data-stu-id="8f950-122">The .NET Library Design Guidelines provide general guidance regarding naming, designing classes and interfaces, member design (properties, methods, events, etc.) and more, and are a useful first point of reference for a variety of design guidance.</span></span>

### <a name="add-xml-documentation-comments-to-your-code"></a><span data-ttu-id="8f950-123">Aggiungere commenti alla documentazione XML al codice</span><span class="sxs-lookup"><span data-stu-id="8f950-123">Add XML documentation comments to your code</span></span>

<span data-ttu-id="8f950-124">La documentazione XML sulle API pubbliche garantisce che gli utenti possano ottenere IntelliSense e informazioni rapide eccezionali quando usano questi tipi e membri e abilitare la compilazione di file di documentazione per la libreria.</span><span class="sxs-lookup"><span data-stu-id="8f950-124">XML documentation on public APIs ensures that users can get great Intellisense and Quickinfo when using these types and members, and enable building documentation files for the library.</span></span> <span data-ttu-id="8f950-125">Vedere la [documentazione XML](../language-reference/xml-documentation.md) sui diversi tag XML che possono essere usati per markup aggiuntivi nei commenti xmldoc.</span><span class="sxs-lookup"><span data-stu-id="8f950-125">See the [XML Documentation](../language-reference/xml-documentation.md) about various xml tags that can be used for additional markup within xmldoc comments.</span></span>

```fsharp
/// A class for representing (x,y) coordinates
type Point =

    /// Computes the distance between this point and another
    member DistanceTo: otherPoint:Point -> float
```

<span data-ttu-id="8f950-126">È possibile utilizzare i commenti XML in formato breve ( `/// comment` ) o i commenti XML standard ( `///<summary>comment</summary>` ).</span><span class="sxs-lookup"><span data-stu-id="8f950-126">You can use either the short form XML comments (`/// comment`), or standard XML comments (`///<summary>comment</summary>`).</span></span>

### <a name="consider-using-explicit-signature-files-fsi-for-stable-library-and-component-apis"></a><span data-ttu-id="8f950-127">Prendere in considerazione l'uso di file di firma espliciti (con estensione FSI) per le API di librerie e componenti</span><span class="sxs-lookup"><span data-stu-id="8f950-127">Consider using explicit signature files (.fsi) for stable library and component APIs</span></span>

<span data-ttu-id="8f950-128">L'uso di file di firme esplicite in una libreria F # fornisce un riepilogo conciso dell'API pubblica, che consente di ottenere informazioni sulla superficie pubblica completa della libreria e fornisce una netta separazione tra la documentazione pubblica e i dettagli di implementazione interna.</span><span class="sxs-lookup"><span data-stu-id="8f950-128">Using explicit signatures files in an F# library provides a succinct summary of public API, which helps to ensure that you know the full public surface of your library, and provides a clean separation between public documentation and internal implementation details.</span></span> <span data-ttu-id="8f950-129">I file delle firme aggiungono un attrito alla modifica dell'API pubblica, richiedendo modifiche da apportare nei file di implementazione e di firma.</span><span class="sxs-lookup"><span data-stu-id="8f950-129">Signature files add friction to changing the public API, by requiring changes to be made in both the implementation and signature files.</span></span> <span data-ttu-id="8f950-130">Di conseguenza, i file della firma devono essere in genere introdotti solo quando un'API diventa solidificata e non è più prevista una modifica significativa.</span><span class="sxs-lookup"><span data-stu-id="8f950-130">As a result, signature files should typically only be introduced when an API has become solidified and is no longer expected to change significantly.</span></span>

### <a name="always-follow-best-practices-for-using-strings-in-net"></a><span data-ttu-id="8f950-131">Seguire sempre le procedure consigliate per l'uso di stringhe in .NET</span><span class="sxs-lookup"><span data-stu-id="8f950-131">Always follow best practices for using strings in .NET</span></span>

<span data-ttu-id="8f950-132">Seguire le procedure consigliate [per l'uso delle stringhe nelle linee guida di .NET](../../standard/base-types/best-practices-strings.md) .</span><span class="sxs-lookup"><span data-stu-id="8f950-132">Follow [Best Practices for Using Strings in .NET](../../standard/base-types/best-practices-strings.md) guidance.</span></span> <span data-ttu-id="8f950-133">In particolare, si dichiara sempre in modo esplicito *finalità culturali* nella conversione e nel confronto delle stringhe (se applicabile).</span><span class="sxs-lookup"><span data-stu-id="8f950-133">In particular, always explicitly state *cultural intent* in the conversion and comparison of strings (where applicable).</span></span>

## <a name="guidelines-for-f-facing-libraries"></a><span data-ttu-id="8f950-134">Linee guida per le librerie F #</span><span class="sxs-lookup"><span data-stu-id="8f950-134">Guidelines for F#-facing libraries</span></span>

<span data-ttu-id="8f950-135">Questa sezione presenta i consigli per lo sviluppo di librerie F # pubbliche. ovvero le librerie che espongono le API pubbliche destinate a essere utilizzate dagli sviluppatori F #.</span><span class="sxs-lookup"><span data-stu-id="8f950-135">This section presents recommendations for developing public F#-facing libraries; that is, libraries exposing public APIs that are intended to be consumed by F# developers.</span></span> <span data-ttu-id="8f950-136">Esistono diverse raccomandazioni per la progettazione di librerie applicabili in modo specifico a F #.</span><span class="sxs-lookup"><span data-stu-id="8f950-136">There are a variety of library-design recommendations applicable specifically to F#.</span></span> <span data-ttu-id="8f950-137">In assenza di raccomandazioni specifiche che seguono, le linee guida per la progettazione di librerie .NET sono le linee guida di fallback.</span><span class="sxs-lookup"><span data-stu-id="8f950-137">In the absence of the specific recommendations that follow, the .NET Library Design Guidelines are the fallback guidance.</span></span>

### <a name="naming-conventions"></a><span data-ttu-id="8f950-138">Convenzioni di denominazione</span><span class="sxs-lookup"><span data-stu-id="8f950-138">Naming conventions</span></span>

#### <a name="use-net-naming-and-capitalization-conventions"></a><span data-ttu-id="8f950-139">Usare le convenzioni di denominazione e di capitalizzazione .NET</span><span class="sxs-lookup"><span data-stu-id="8f950-139">Use .NET naming and capitalization conventions</span></span>

<span data-ttu-id="8f950-140">La tabella seguente segue le convenzioni di denominazione e di maiuscole e minuscole .NET.</span><span class="sxs-lookup"><span data-stu-id="8f950-140">The following table follows .NET naming and capitalization conventions.</span></span> <span data-ttu-id="8f950-141">Sono disponibili piccole aggiunte per includere anche costrutti F #.</span><span class="sxs-lookup"><span data-stu-id="8f950-141">There are small additions to also include F# constructs.</span></span>

| <span data-ttu-id="8f950-142">Costrutto</span><span class="sxs-lookup"><span data-stu-id="8f950-142">Construct</span></span> | <span data-ttu-id="8f950-143">Caso</span><span class="sxs-lookup"><span data-stu-id="8f950-143">Case</span></span> | <span data-ttu-id="8f950-144">Parte</span><span class="sxs-lookup"><span data-stu-id="8f950-144">Part</span></span> | <span data-ttu-id="8f950-145">Esempi</span><span class="sxs-lookup"><span data-stu-id="8f950-145">Examples</span></span> | <span data-ttu-id="8f950-146">Note</span><span class="sxs-lookup"><span data-stu-id="8f950-146">Notes</span></span> |
|-----------|------|------|----------|-------|
| <span data-ttu-id="8f950-147">Tipi concreti</span><span class="sxs-lookup"><span data-stu-id="8f950-147">Concrete types</span></span> | <span data-ttu-id="8f950-148">PascalCase</span><span class="sxs-lookup"><span data-stu-id="8f950-148">PascalCase</span></span> | <span data-ttu-id="8f950-149">Sostantivo/aggettivo</span><span class="sxs-lookup"><span data-stu-id="8f950-149">Noun/ adjective</span></span> | <span data-ttu-id="8f950-150">Elenco, doppio, complesso</span><span class="sxs-lookup"><span data-stu-id="8f950-150">List, Double, Complex</span></span> | <span data-ttu-id="8f950-151">I tipi concreti sono struct, classi, enumerazioni, delegati, record e unioni.</span><span class="sxs-lookup"><span data-stu-id="8f950-151">Concrete types are structs, classes, enumerations, delegates, records, and unions.</span></span> <span data-ttu-id="8f950-152">Anche se i nomi dei tipi sono tradizionalmente minuscoli in OCaml, F # ha adottato lo schema di denominazione .NET per i tipi.</span><span class="sxs-lookup"><span data-stu-id="8f950-152">Though type names are traditionally lowercase in OCaml, F# has adopted the .NET naming scheme for types.</span></span>
| <span data-ttu-id="8f950-153">DLL</span><span class="sxs-lookup"><span data-stu-id="8f950-153">DLLs</span></span>           | <span data-ttu-id="8f950-154">PascalCase</span><span class="sxs-lookup"><span data-stu-id="8f950-154">PascalCase</span></span> |                 | <span data-ttu-id="8f950-155">Fabrikam. Core. dll</span><span class="sxs-lookup"><span data-stu-id="8f950-155">Fabrikam.Core.dll</span></span> |  |
| <span data-ttu-id="8f950-156">Tag Union</span><span class="sxs-lookup"><span data-stu-id="8f950-156">Union tags</span></span>     | <span data-ttu-id="8f950-157">PascalCase</span><span class="sxs-lookup"><span data-stu-id="8f950-157">PascalCase</span></span> | <span data-ttu-id="8f950-158">Sostantivo</span><span class="sxs-lookup"><span data-stu-id="8f950-158">Noun</span></span> | <span data-ttu-id="8f950-159">Alcuni, Aggiungi, esito positivo</span><span class="sxs-lookup"><span data-stu-id="8f950-159">Some, Add, Success</span></span> | <span data-ttu-id="8f950-160">Non usare un prefisso nelle API pubbliche.</span><span class="sxs-lookup"><span data-stu-id="8f950-160">Do not use a prefix in public APIs.</span></span> <span data-ttu-id="8f950-161">Usare facoltativamente un prefisso quando è interno, ad esempio`type Teams = TAlpha | TBeta | TDelta.`</span><span class="sxs-lookup"><span data-stu-id="8f950-161">Optionally use a prefix when internal, such as `type Teams = TAlpha | TBeta | TDelta.`</span></span> |
| <span data-ttu-id="8f950-162">Event</span><span class="sxs-lookup"><span data-stu-id="8f950-162">Event</span></span>          | <span data-ttu-id="8f950-163">PascalCase</span><span class="sxs-lookup"><span data-stu-id="8f950-163">PascalCase</span></span> | <span data-ttu-id="8f950-164">Verbo</span><span class="sxs-lookup"><span data-stu-id="8f950-164">Verb</span></span> | <span data-ttu-id="8f950-165">ValueChanged/ValueChanging</span><span class="sxs-lookup"><span data-stu-id="8f950-165">ValueChanged / ValueChanging</span></span> |  |
| <span data-ttu-id="8f950-166">Eccezioni</span><span class="sxs-lookup"><span data-stu-id="8f950-166">Exceptions</span></span>     | <span data-ttu-id="8f950-167">PascalCase</span><span class="sxs-lookup"><span data-stu-id="8f950-167">PascalCase</span></span> |      | <span data-ttu-id="8f950-168">WebException</span><span class="sxs-lookup"><span data-stu-id="8f950-168">WebException</span></span> | <span data-ttu-id="8f950-169">Il nome deve terminare con "Exception".</span><span class="sxs-lookup"><span data-stu-id="8f950-169">Name should end with "Exception".</span></span> |
| <span data-ttu-id="8f950-170">Campo</span><span class="sxs-lookup"><span data-stu-id="8f950-170">Field</span></span>          | <span data-ttu-id="8f950-171">PascalCase</span><span class="sxs-lookup"><span data-stu-id="8f950-171">PascalCase</span></span> | <span data-ttu-id="8f950-172">Sostantivo</span><span class="sxs-lookup"><span data-stu-id="8f950-172">Noun</span></span> | <span data-ttu-id="8f950-173">Currentname</span><span class="sxs-lookup"><span data-stu-id="8f950-173">CurrentName</span></span>  | |
| <span data-ttu-id="8f950-174">Tipi interfaccia</span><span class="sxs-lookup"><span data-stu-id="8f950-174">Interface types</span></span> |  <span data-ttu-id="8f950-175">PascalCase</span><span class="sxs-lookup"><span data-stu-id="8f950-175">PascalCase</span></span> | <span data-ttu-id="8f950-176">Sostantivo/aggettivo</span><span class="sxs-lookup"><span data-stu-id="8f950-176">Noun/ adjective</span></span> | <span data-ttu-id="8f950-177">IDisposable</span><span class="sxs-lookup"><span data-stu-id="8f950-177">IDisposable</span></span> | <span data-ttu-id="8f950-178">Il nome deve iniziare con "I".</span><span class="sxs-lookup"><span data-stu-id="8f950-178">Name should start with "I".</span></span> |
| <span data-ttu-id="8f950-179">Metodo</span><span class="sxs-lookup"><span data-stu-id="8f950-179">Method</span></span> |  <span data-ttu-id="8f950-180">PascalCase</span><span class="sxs-lookup"><span data-stu-id="8f950-180">PascalCase</span></span> |  <span data-ttu-id="8f950-181">Verbo</span><span class="sxs-lookup"><span data-stu-id="8f950-181">Verb</span></span> | <span data-ttu-id="8f950-182">ToString</span><span class="sxs-lookup"><span data-stu-id="8f950-182">ToString</span></span> | |
| <span data-ttu-id="8f950-183">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="8f950-183">Namespace</span></span> | <span data-ttu-id="8f950-184">PascalCase</span><span class="sxs-lookup"><span data-stu-id="8f950-184">PascalCase</span></span> | | <span data-ttu-id="8f950-185">Microsoft. FSharp. Core</span><span class="sxs-lookup"><span data-stu-id="8f950-185">Microsoft.FSharp.Core</span></span> | <span data-ttu-id="8f950-186">Utilizzare in genere `<Organization>.<Technology>[.<Subnamespace>]` , anche se eliminare l'organizzazione se la tecnologia è indipendente dall'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="8f950-186">Generally use `<Organization>.<Technology>[.<Subnamespace>]`, though drop the organization if the technology is independent of organization.</span></span> |
| <span data-ttu-id="8f950-187">Parametri</span><span class="sxs-lookup"><span data-stu-id="8f950-187">Parameters</span></span> | <span data-ttu-id="8f950-188">camelCase</span><span class="sxs-lookup"><span data-stu-id="8f950-188">camelCase</span></span> | <span data-ttu-id="8f950-189">Sostantivo</span><span class="sxs-lookup"><span data-stu-id="8f950-189">Noun</span></span> |  <span data-ttu-id="8f950-190">typeName, Transform, intervallo</span><span class="sxs-lookup"><span data-stu-id="8f950-190">typeName, transform, range</span></span> | |
| <span data-ttu-id="8f950-191">valori Let (interni)</span><span class="sxs-lookup"><span data-stu-id="8f950-191">let values (internal)</span></span> | <span data-ttu-id="8f950-192">camelCase o PascalCase</span><span class="sxs-lookup"><span data-stu-id="8f950-192">camelCase or PascalCase</span></span> | <span data-ttu-id="8f950-193">Sostantivo/verbo</span><span class="sxs-lookup"><span data-stu-id="8f950-193">Noun/ verb</span></span> |  <span data-ttu-id="8f950-194">getValue, MyTable</span><span class="sxs-lookup"><span data-stu-id="8f950-194">getValue, myTable</span></span> |
| <span data-ttu-id="8f950-195">valori Let (External)</span><span class="sxs-lookup"><span data-stu-id="8f950-195">let values (external)</span></span> | <span data-ttu-id="8f950-196">camelCase o PascalCase</span><span class="sxs-lookup"><span data-stu-id="8f950-196">camelCase or PascalCase</span></span> | <span data-ttu-id="8f950-197">Sostantivo/verbo</span><span class="sxs-lookup"><span data-stu-id="8f950-197">Noun/verb</span></span>  | <span data-ttu-id="8f950-198">List. map, dates. Today</span><span class="sxs-lookup"><span data-stu-id="8f950-198">List.map, Dates.Today</span></span> | <span data-ttu-id="8f950-199">i valori associati a Let sono spesso pubblici quando si seguono modelli di progettazione funzionali tradizionali.</span><span class="sxs-lookup"><span data-stu-id="8f950-199">let-bound values are often public when following traditional functional design patterns.</span></span> <span data-ttu-id="8f950-200">Tuttavia, in genere si usa PascalCase quando l'identificatore può essere usato da altri linguaggi .NET.</span><span class="sxs-lookup"><span data-stu-id="8f950-200">However, generally use PascalCase when the identifier can be used from other .NET languages.</span></span> |
| <span data-ttu-id="8f950-201">Proprietà</span><span class="sxs-lookup"><span data-stu-id="8f950-201">Property</span></span>  | <span data-ttu-id="8f950-202">PascalCase</span><span class="sxs-lookup"><span data-stu-id="8f950-202">PascalCase</span></span>  | <span data-ttu-id="8f950-203">Sostantivo/aggettivo</span><span class="sxs-lookup"><span data-stu-id="8f950-203">Noun/ adjective</span></span>  | <span data-ttu-id="8f950-204">IsEndOfFile, backcolor</span><span class="sxs-lookup"><span data-stu-id="8f950-204">IsEndOfFile, BackColor</span></span>  | <span data-ttu-id="8f950-205">Le proprietà booleane in genere usano e possono e devono essere affermativa, come in IsEndOfFile, non in IsNotEndOfFile.</span><span class="sxs-lookup"><span data-stu-id="8f950-205">Boolean properties generally use Is and Can and should be affirmative, as in IsEndOfFile, not IsNotEndOfFile.</span></span>

#### <a name="avoid-abbreviations"></a><span data-ttu-id="8f950-206">Evitare abbreviazioni</span><span class="sxs-lookup"><span data-stu-id="8f950-206">Avoid abbreviations</span></span>

<span data-ttu-id="8f950-207">Le linee guida di .NET scoraggiano l'uso delle abbreviazioni (ad esempio, "use `OnButtonClick` anziché `OnBtnClick` ").</span><span class="sxs-lookup"><span data-stu-id="8f950-207">The .NET guidelines discourage the use of abbreviations (for example, "use `OnButtonClick` rather than `OnBtnClick`").</span></span> <span data-ttu-id="8f950-208">Sono tollerate abbreviazioni comuni, ad esempio `Async` per "asincrono".</span><span class="sxs-lookup"><span data-stu-id="8f950-208">Common abbreviations, such as `Async` for "Asynchronous", are tolerated.</span></span> <span data-ttu-id="8f950-209">Questa guida viene talvolta ignorata per la programmazione funzionale; USA, ad esempio, `List.iter` un'abbreviazione per "iterare".</span><span class="sxs-lookup"><span data-stu-id="8f950-209">This guideline is sometimes ignored for functional programming; for example, `List.iter` uses an abbreviation for "iterate".</span></span> <span data-ttu-id="8f950-210">Per questo motivo, l'uso delle abbreviazioni tende a essere tollerato a un livello superiore nella programmazione F #-to-F #, ma in genere dovrebbe comunque essere evitato nella progettazione di componenti pubblici.</span><span class="sxs-lookup"><span data-stu-id="8f950-210">For this reason, using abbreviations tends to be tolerated to a greater degree in F#-to-F# programming, but should still generally be avoided in public component design.</span></span>

#### <a name="avoid-casing-name-collisions"></a><span data-ttu-id="8f950-211">Evitare conflitti di nomi di maiuscole e minuscole</span><span class="sxs-lookup"><span data-stu-id="8f950-211">Avoid casing name collisions</span></span>

<span data-ttu-id="8f950-212">Le linee guida di .NET indicano che non è possibile usare solo la combinazione di maiuscole e minuscole per evitare ambiguità nei conflitti di nomi, poiché alcune lingue client, ad esempio Visual Basic, non fanno distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="8f950-212">The .NET guidelines say that casing alone cannot be used to disambiguate name collisions, since some client languages (for example, Visual Basic) are case-insensitive.</span></span>

#### <a name="use-acronyms-where-appropriate"></a><span data-ttu-id="8f950-213">Usare gli acronimi laddove appropriato</span><span class="sxs-lookup"><span data-stu-id="8f950-213">Use acronyms where appropriate</span></span>

<span data-ttu-id="8f950-214">Gli acronimi come XML non sono abbreviazioni e sono ampiamente usati nelle librerie .NET in formato senza maiuscole (XML).</span><span class="sxs-lookup"><span data-stu-id="8f950-214">Acronyms such as XML are not abbreviations and are widely used in .NET libraries in uncapitalized form (Xml).</span></span> <span data-ttu-id="8f950-215">Devono essere usati solo gli acronimi noti e ampiamente riconosciuti.</span><span class="sxs-lookup"><span data-stu-id="8f950-215">Only well-known, widely recognized acronyms should be used.</span></span>

#### <a name="use-pascalcase-for-generic-parameter-names"></a><span data-ttu-id="8f950-216">Usare PascalCase per i nomi dei parametri generici</span><span class="sxs-lookup"><span data-stu-id="8f950-216">Use PascalCase for generic parameter names</span></span>

<span data-ttu-id="8f950-217">Usare PascalCase per i nomi di parametro generici nelle API pubbliche, incluse le librerie con rivolte a F #.</span><span class="sxs-lookup"><span data-stu-id="8f950-217">Do use PascalCase for generic parameter names in public APIs, including for F#-facing libraries.</span></span> <span data-ttu-id="8f950-218">In particolare, usare nomi come `T` , `U` , `T1` , `T2` per i parametri generici arbitrari e quando i nomi specifici hanno senso, quindi per le librerie con rivolte a F # usare nomi come `Key` , `Value` , `Arg` (ma non ad esempio, `TKey` ).</span><span class="sxs-lookup"><span data-stu-id="8f950-218">In particular, use names like `T`, `U`, `T1`, `T2` for arbitrary generic parameters, and when specific names make sense, then for F#-facing libraries use names like `Key`, `Value`, `Arg` (but not for example, `TKey`).</span></span>

#### <a name="use-either-pascalcase-or-camelcase-for-public-functions-and-values-in-f-modules"></a><span data-ttu-id="8f950-219">Usare PascalCase o camelCase per le funzioni e i valori pubblici nei moduli F #</span><span class="sxs-lookup"><span data-stu-id="8f950-219">Use either PascalCase or camelCase for public functions and values in F# modules</span></span>

<span data-ttu-id="8f950-220">camelCase viene usato per le funzioni pubbliche progettate per essere usate non qualificate (ad esempio, `invalidArg` ) e per "funzioni di raccolta standard" (ad esempio, List. map).</span><span class="sxs-lookup"><span data-stu-id="8f950-220">camelCase is used for public functions that are designed to be used unqualified (for example, `invalidArg`), and for the "standard collection functions" (for example, List.map).</span></span> <span data-ttu-id="8f950-221">In entrambi i casi, i nomi di funzione agiscono in modo analogo alle parole chiave del linguaggio.</span><span class="sxs-lookup"><span data-stu-id="8f950-221">In both these cases, the function names act much like keywords in the language.</span></span>

### <a name="object-type-and-module-design"></a><span data-ttu-id="8f950-222">Progettazione di oggetti, tipi e moduli</span><span class="sxs-lookup"><span data-stu-id="8f950-222">Object, Type, and Module design</span></span>

#### <a name="use-namespaces-or-modules-to-contain-your-types-and-modules"></a><span data-ttu-id="8f950-223">Usare spazi dei nomi o moduli per contenere tipi e moduli</span><span class="sxs-lookup"><span data-stu-id="8f950-223">Use namespaces or modules to contain your types and modules</span></span>

<span data-ttu-id="8f950-224">Ogni file F # in un componente deve iniziare con una dichiarazione dello spazio dei nomi o con una dichiarazione del modulo.</span><span class="sxs-lookup"><span data-stu-id="8f950-224">Each F# file in a component should begin with either a namespace declaration or a module declaration.</span></span>

```fsharp
namespace Fabrikam.BasicOperationsAndTypes

type ObjectType1() =
    ...

type ObjectType2() =
     ...

module CommonOperations =
    ...
```

<span data-ttu-id="8f950-225">oppure</span><span class="sxs-lookup"><span data-stu-id="8f950-225">or</span></span>

```fsharp
module Fabrikam.BasicOperationsAndTypes

type ObjectType1() =
    ...

type ObjectType2() =
    ...

module CommonOperations =
    ...
```

<span data-ttu-id="8f950-226">Le differenze tra l'utilizzo di moduli e spazi dei nomi per organizzare il codice al primo livello sono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="8f950-226">The differences between using modules and namespaces to organize code at the top level are as follows:</span></span>

* <span data-ttu-id="8f950-227">Gli spazi dei nomi possono estendersi su più file</span><span class="sxs-lookup"><span data-stu-id="8f950-227">Namespaces can span multiple files</span></span>
* <span data-ttu-id="8f950-228">Gli spazi dei nomi non possono contenere funzioni F # a meno che non si trovino all'interno di un modulo interno</span><span class="sxs-lookup"><span data-stu-id="8f950-228">Namespaces cannot contain F# functions unless they are within an inner module</span></span>
* <span data-ttu-id="8f950-229">Il codice per qualsiasi modulo specificato deve essere contenuto in un singolo file</span><span class="sxs-lookup"><span data-stu-id="8f950-229">The code for any given module must be contained within a single file</span></span>
* <span data-ttu-id="8f950-230">I moduli di livello superiore possono contenere funzioni F # senza la necessità di un modulo interno</span><span class="sxs-lookup"><span data-stu-id="8f950-230">Top-level modules can contain F# functions without the need for an inner module</span></span>

<span data-ttu-id="8f950-231">La scelta tra uno spazio dei nomi o un modulo di primo livello influisce sulla forma compilata del codice e pertanto influirà sulla visualizzazione di altri linguaggi .NET se l'API viene utilizzata all'esterno del codice F #.</span><span class="sxs-lookup"><span data-stu-id="8f950-231">The choice between a top-level namespace or module affects the compiled form of the code, and thus will affect the view from other .NET languages should your API eventually be consumed outside of F# code.</span></span>

#### <a name="use-methods-and-properties-for-operations-intrinsic-to-object-types"></a><span data-ttu-id="8f950-232">Usare i metodi e le proprietà per le operazioni intrinseche ai tipi di oggetto</span><span class="sxs-lookup"><span data-stu-id="8f950-232">Use methods and properties for operations intrinsic to object types</span></span>

<span data-ttu-id="8f950-233">Quando si utilizzano gli oggetti, è consigliabile assicurarsi che la funzionalità utilizzabile venga implementata come metodi e proprietà su tale tipo.</span><span class="sxs-lookup"><span data-stu-id="8f950-233">When working with objects, it is best to ensure that consumable functionality is implemented as methods and properties on that type.</span></span>

```fsharp
type HardwareDevice() =

    member this.ID = ...

    member this.SupportedProtocols = ...

type HashTable<'Key,'Value>(comparer: IEqualityComparer<'Key>) =

    member this.Add(key, value) = ...

    member this.ContainsKey(key) = ...

    member this.ContainsValue(value) = ...
```

<span data-ttu-id="8f950-234">La maggior parte delle funzionalità per un determinato membro non deve necessariamente essere implementata in quel membro, ma la parte utilizzabile di tale funzionalità dovrebbe essere.</span><span class="sxs-lookup"><span data-stu-id="8f950-234">The bulk of functionality for a given member need not necessarily be implemented in that member, but the consumable piece of that functionality should be.</span></span>

#### <a name="use-classes-to-encapsulate-mutable-state"></a><span data-ttu-id="8f950-235">Usare classi per incapsulare lo stato modificabile</span><span class="sxs-lookup"><span data-stu-id="8f950-235">Use classes to encapsulate mutable state</span></span>

<span data-ttu-id="8f950-236">In F #, questa operazione deve essere eseguita solo se lo stato non è già incapsulato da un altro costrutto di linguaggio, ad esempio una chiusura, un'espressione di sequenza o un calcolo asincrono.</span><span class="sxs-lookup"><span data-stu-id="8f950-236">In F#, this only needs to be done where that state is not already encapsulated by another language construct, such as a closure, sequence expression, or asynchronous computation.</span></span>

```fsharp
type Counter() =
    // let-bound values are private in classes.
    let mutable count = 0

    member this.Next() =
        count <- count + 1
        count
```

#### <a name="use-interfaces-to-group-related-operations"></a><span data-ttu-id="8f950-237">Usare le interfacce per raggruppare le operazioni correlate</span><span class="sxs-lookup"><span data-stu-id="8f950-237">Use interfaces to group related operations</span></span>

<span data-ttu-id="8f950-238">Usare i tipi di interfaccia per rappresentare un set di operazioni.</span><span class="sxs-lookup"><span data-stu-id="8f950-238">Use interface types to represent a set of operations.</span></span> <span data-ttu-id="8f950-239">Questa operazione è preferibile ad altre opzioni, ad esempio tuple di funzioni o record di funzioni.</span><span class="sxs-lookup"><span data-stu-id="8f950-239">This is preferred to other options, such as tuples of functions or records of functions.</span></span>

```fsharp
type Serializer =
    abstract Serialize<'T>: preserveRefEq: bool -> value: 'T -> string
    abstract Deserialize<'T>: preserveRefEq: bool -> pickle: string -> 'T
```

<span data-ttu-id="8f950-240">Preferenza per:</span><span class="sxs-lookup"><span data-stu-id="8f950-240">In preference to:</span></span>

```fsharp
type Serializer<'T> = {
    Serialize: bool -> 'T -> string
    Deserialize: bool -> string -> 'T
}
```

<span data-ttu-id="8f950-241">Le interfacce sono concetti di primo livello in .NET, che è possibile usare per ottenere i risultati di funtori in genere.</span><span class="sxs-lookup"><span data-stu-id="8f950-241">Interfaces are first-class concepts in .NET, which you can use to achieve what Functors would normally give you.</span></span> <span data-ttu-id="8f950-242">Inoltre, possono essere usati per codificare i tipi esistenziali nel programma, che non possono essere registrati nelle funzioni.</span><span class="sxs-lookup"><span data-stu-id="8f950-242">Additionally, they can be used to encode existential types into your program, which records of functions cannot.</span></span>

#### <a name="use-a-module-to-group-functions-that-act-on-collections"></a><span data-ttu-id="8f950-243">Usare un modulo per raggruppare le funzioni che agiscono sulle raccolte</span><span class="sxs-lookup"><span data-stu-id="8f950-243">Use a module to group functions that act on collections</span></span>

<span data-ttu-id="8f950-244">Quando si definisce un tipo di raccolta, è consigliabile fornire un set standard di operazioni come `CollectionType.map` e `CollectionType.iter` ) per i nuovi tipi di raccolta.</span><span class="sxs-lookup"><span data-stu-id="8f950-244">When you define a collection type, consider providing a standard set of operations like `CollectionType.map` and `CollectionType.iter`) for new collection types.</span></span>

```fsharp
module CollectionType =
    let map f c =
        ...
    let iter f c =
        ...
```

<span data-ttu-id="8f950-245">Se si include tale modulo, seguire le convenzioni di denominazione standard per le funzioni disponibili in FSharp. Core.</span><span class="sxs-lookup"><span data-stu-id="8f950-245">If you include such a module, follow the standard naming conventions for functions found in FSharp.Core.</span></span>

#### <a name="use-a-module-to-group-functions-for-common-canonical-functions-especially-in-math-and-dsl-libraries"></a><span data-ttu-id="8f950-246">Usare un modulo per raggruppare le funzioni per funzioni canoniche comuni, soprattutto nelle librerie matematiche e DSL</span><span class="sxs-lookup"><span data-stu-id="8f950-246">Use a module to group functions for common, canonical functions, especially in math and DSL libraries</span></span>

<span data-ttu-id="8f950-247">Ad esempio, `Microsoft.FSharp.Core.Operators` è una raccolta aperta automaticamente di funzioni di primo livello (ad esempio `abs` e `sin` ) fornita da FSharp. Core. dll.</span><span class="sxs-lookup"><span data-stu-id="8f950-247">For example, `Microsoft.FSharp.Core.Operators` is an automatically opened collection of top-level functions (like `abs` and `sin`) provided by FSharp.Core.dll.</span></span>

<span data-ttu-id="8f950-248">Analogamente, una libreria di statistiche può includere un modulo con funzioni `erf` e `erfc` , in cui questo modulo è progettato per essere aperto in modo esplicito o automatico.</span><span class="sxs-lookup"><span data-stu-id="8f950-248">Likewise, a statistics library might include a module with functions `erf` and `erfc`, where this module is designed to be explicitly or automatically opened.</span></span>

#### <a name="consider-using-requirequalifiedaccess-and-carefully-apply-autoopen-attributes"></a><span data-ttu-id="8f950-249">Prendere in considerazione l'uso di RequireQualifiedAccess e applicare con attenzione gli attributi di apertura</span><span class="sxs-lookup"><span data-stu-id="8f950-249">Consider using RequireQualifiedAccess and carefully apply AutoOpen attributes</span></span>

<span data-ttu-id="8f950-250">L'aggiunta dell' `[<RequireQualifiedAccess>]` attributo a un modulo indica che il modulo potrebbe non essere aperto e che i riferimenti agli elementi del modulo richiedono un accesso qualificato esplicito.</span><span class="sxs-lookup"><span data-stu-id="8f950-250">Adding the `[<RequireQualifiedAccess>]` attribute to a module indicates that the module may not be opened and that references to the elements of the module require explicit qualified access.</span></span> <span data-ttu-id="8f950-251">Ad esempio, il `Microsoft.FSharp.Collections.List` modulo dispone di questo attributo.</span><span class="sxs-lookup"><span data-stu-id="8f950-251">For example, the `Microsoft.FSharp.Collections.List` module has this attribute.</span></span>

<span data-ttu-id="8f950-252">Questa operazione è utile quando le funzioni e i valori nel modulo hanno nomi che probabilmente sono in conflitto con i nomi in altri moduli.</span><span class="sxs-lookup"><span data-stu-id="8f950-252">This is useful when functions and values in the module have names that are likely to conflict with names in other modules.</span></span> <span data-ttu-id="8f950-253">La richiesta di accesso qualificato può aumentare significativamente la gestibilità a lungo termine e la evolvibilità di una libreria.</span><span class="sxs-lookup"><span data-stu-id="8f950-253">Requiring qualified access can greatly increase the long-term maintainability and evolvability of a library.</span></span>

<span data-ttu-id="8f950-254">L'aggiunta dell' `[<AutoOpen>]` attributo a un modulo indica che il modulo verrà aperto quando lo spazio dei nomi contenitore viene aperto.</span><span class="sxs-lookup"><span data-stu-id="8f950-254">Adding the `[<AutoOpen>]` attribute to a module means the module will be opened when the containing namespace is opened.</span></span> <span data-ttu-id="8f950-255">L' `[<AutoOpen>]` attributo può essere applicato anche a un assembly per indicare un modulo che viene aperto automaticamente quando si fa riferimento all'assembly.</span><span class="sxs-lookup"><span data-stu-id="8f950-255">The `[<AutoOpen>]` attribute may also be applied to an assembly to indicate a module that is automatically opened when the assembly is referenced.</span></span>

<span data-ttu-id="8f950-256">Una raccolta di statistiche **MathsHeaven. Statistics** , ad esempio, potrebbe contenere `module MathsHeaven.Statistics.Operators` `erf` le funzioni e `erfc` .</span><span class="sxs-lookup"><span data-stu-id="8f950-256">For example, a statistics library **MathsHeaven.Statistics** might contain a `module MathsHeaven.Statistics.Operators` containing functions `erf` and `erfc`.</span></span> <span data-ttu-id="8f950-257">È ragionevole contrassegnare questo modulo come `[<AutoOpen>]` .</span><span class="sxs-lookup"><span data-stu-id="8f950-257">It is reasonable to mark this module as `[<AutoOpen>]`.</span></span> <span data-ttu-id="8f950-258">Ciò significa `open MathsHeaven.Statistics` che aprirà anche questo modulo e riporterà i nomi `erf` e l' `erfc` ambito.</span><span class="sxs-lookup"><span data-stu-id="8f950-258">This means `open MathsHeaven.Statistics` will also open this module and bring the names `erf` and `erfc` into scope.</span></span> <span data-ttu-id="8f950-259">Un altro valido utilizzo di `[<AutoOpen>]` è per i moduli che contengono metodi di estensione.</span><span class="sxs-lookup"><span data-stu-id="8f950-259">Another good use of `[<AutoOpen>]` is for modules containing extension methods.</span></span>

<span data-ttu-id="8f950-260">L'utilizzo eccessivo di `[<AutoOpen>]` lead per gli spazi dei nomi inquinati e l'attributo deve essere utilizzato con cautela.</span><span class="sxs-lookup"><span data-stu-id="8f950-260">Overuse of `[<AutoOpen>]` leads to polluted namespaces, and the attribute should be used with care.</span></span> <span data-ttu-id="8f950-261">Per librerie specifiche in domini specifici, l'uso oculato di `[<AutoOpen>]` può condurre a una migliore usabilità.</span><span class="sxs-lookup"><span data-stu-id="8f950-261">For specific libraries in specific domains, judicious use of `[<AutoOpen>]` can lead to better usability.</span></span>

#### <a name="consider-defining-operator-members-on-classes-where-using-well-known-operators-is-appropriate"></a><span data-ttu-id="8f950-262">Prendere in considerazione la definizione dei membri dell'operatore nelle classi in cui l'utilizzo di operatori noti è appropriato</span><span class="sxs-lookup"><span data-stu-id="8f950-262">Consider defining operator members on classes where using well-known operators is appropriate</span></span>

<span data-ttu-id="8f950-263">A volte le classi vengono usate per modellare costrutti matematici, ad esempio vettori.</span><span class="sxs-lookup"><span data-stu-id="8f950-263">Sometimes classes are used to model mathematical constructs such as Vectors.</span></span> <span data-ttu-id="8f950-264">Quando il dominio da modellare dispone di operatori noti, la relativa definizione come membri intrinseci alla classe è utile.</span><span class="sxs-lookup"><span data-stu-id="8f950-264">When the domain being modeled has well-known operators, defining them as members intrinsic to the class is helpful.</span></span>

```fsharp
type Vector(x: float) =

    member v.X = x

    static member (*) (vector: Vector, scalar: float) = Vector(vector.X * scalar)

    static member (+) (vector1: Vector, vector2: Vector) = Vector(vector1.X + vector2.X)

let v = Vector(5.0)

let u = v * 10.0
```

<span data-ttu-id="8f950-265">Questa guida corrisponde alle linee guida generali di .NET per questi tipi.</span><span class="sxs-lookup"><span data-stu-id="8f950-265">This guidance corresponds to general .NET guidance for these types.</span></span> <span data-ttu-id="8f950-266">Tuttavia, può essere importante anche nel codice F # perché consente l'uso di questi tipi insieme a funzioni e metodi F # con vincoli di membro, ad esempio List. sumBy.</span><span class="sxs-lookup"><span data-stu-id="8f950-266">However, it can be additionally important in F# coding as this allows these types to be used in conjunction with F# functions and methods with member constraints, such as List.sumBy.</span></span>

#### <a name="consider-using-compiledname-to-provide-a-net-friendly-name-for-other-net-language-consumers"></a><span data-ttu-id="8f950-267">Provare a usare Compiled per fornire un oggetto. Nome descrittivo di rete per altri consumer di linguaggio .NET</span><span class="sxs-lookup"><span data-stu-id="8f950-267">Consider using CompiledName to provide a .NET-friendly name for other .NET language consumers</span></span>

<span data-ttu-id="8f950-268">In alcuni casi può essere utile assegnare un nome a un elemento in uno stile per i consumer F # (ad esempio un membro statico in lettere minuscole, in modo che venga visualizzato come se fosse una funzione associata al modulo), ma abbia uno stile diverso per il nome quando viene compilato in un assembly.</span><span class="sxs-lookup"><span data-stu-id="8f950-268">Sometimes you may wish to name something in one style for F# consumers (such as a static member in lower case so that it appears as if it were a module-bound function), but have a different style for the name when it is compiled into an assembly.</span></span> <span data-ttu-id="8f950-269">È possibile utilizzare l' `[<CompiledName>]` attributo per fornire uno stile diverso per l'utilizzo dell'assembly da parte del codice non F #.</span><span class="sxs-lookup"><span data-stu-id="8f950-269">You can use the `[<CompiledName>]` attribute to provide a different style for non F# code consuming the assembly.</span></span>

```fsharp
type Vector(x:float, y:float) =

    member v.X = x
    member v.Y = y

    [<CompiledName("Create")>]
    static member create x y = Vector (x, y)

let v = Vector.create 5.0 3.0
```

<span data-ttu-id="8f950-270">Utilizzando `[<CompiledName>]` , è possibile utilizzare le convenzioni di denominazione .NET per i consumer non F # dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="8f950-270">By using `[<CompiledName>]`, you can use .NET naming conventions for non F# consumers of the assembly.</span></span>

#### <a name="use-method-overloading-for-member-functions-if-doing-so-provides-a-simpler-api"></a><span data-ttu-id="8f950-271">Usare l'overload del metodo per le funzioni membro, se questa operazione fornisce un'API più semplice</span><span class="sxs-lookup"><span data-stu-id="8f950-271">Use method overloading for member functions, if doing so provides a simpler API</span></span>

<span data-ttu-id="8f950-272">L'overload dei metodi è uno strumento potente per semplificare un'API che potrebbe dover eseguire funzionalità simili, ma con opzioni o argomenti diversi.</span><span class="sxs-lookup"><span data-stu-id="8f950-272">Method overloading is a powerful tool for simplifying an API that may need to perform similar functionality, but with different options or arguments.</span></span>

```fsharp
type Logger() =

    member this.Log(message) =
        ...
    member this.Log(message, retryPolicy) =
        ...
```

<span data-ttu-id="8f950-273">In F # è più comune eseguire l'overload su un numero di argomenti anziché sui tipi di argomenti.</span><span class="sxs-lookup"><span data-stu-id="8f950-273">In F#, it is more common to overload on number of arguments rather than types of arguments.</span></span>

#### <a name="hide-the-representations-of-record-and-union-types-if-the-design-of-these-types-is-likely-to-evolve"></a><span data-ttu-id="8f950-274">Nascondere le rappresentazioni dei tipi di record e di Unione se è probabile che la progettazione di questi tipi evolva</span><span class="sxs-lookup"><span data-stu-id="8f950-274">Hide the representations of record and union types if the design of these types is likely to evolve</span></span>

<span data-ttu-id="8f950-275">Evitare di rivelare rappresentazioni concrete di oggetti.</span><span class="sxs-lookup"><span data-stu-id="8f950-275">Avoid revealing concrete representations of objects.</span></span> <span data-ttu-id="8f950-276">La rappresentazione concreta dei valori, ad esempio, <xref:System.DateTime> non viene rivelata dall'API esterna e pubblica della progettazione della libreria .NET.</span><span class="sxs-lookup"><span data-stu-id="8f950-276">For example, the concrete representation of <xref:System.DateTime> values is not revealed by the external, public API of the .NET library design.</span></span> <span data-ttu-id="8f950-277">In fase di esecuzione, Common Language Runtime conosce l'implementazione di cui è stato eseguito il commit che verrà usata durante l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="8f950-277">At run time, the Common Language Runtime knows the committed implementation that will be used throughout execution.</span></span> <span data-ttu-id="8f950-278">Tuttavia, il codice compilato non acquisisce dipendenze dalla rappresentazione concreta.</span><span class="sxs-lookup"><span data-stu-id="8f950-278">However, compiled code doesn't itself pick up dependencies on the concrete representation.</span></span>

#### <a name="avoid-the-use-of-implementation-inheritance-for-extensibility"></a><span data-ttu-id="8f950-279">Evitare l'utilizzo dell'ereditarietà dell'implementazione per l'estendibilità</span><span class="sxs-lookup"><span data-stu-id="8f950-279">Avoid the use of implementation inheritance for extensibility</span></span>

<span data-ttu-id="8f950-280">In F # l'ereditarietà dell'implementazione viene utilizzata raramente.</span><span class="sxs-lookup"><span data-stu-id="8f950-280">In F#, implementation inheritance is rarely used.</span></span> <span data-ttu-id="8f950-281">Inoltre, le gerarchie di ereditarietà sono spesso complesse e difficili da modificare quando arrivano nuovi requisiti.</span><span class="sxs-lookup"><span data-stu-id="8f950-281">Furthermore, inheritance hierarchies are often complex and difficult to change when new requirements arrive.</span></span> <span data-ttu-id="8f950-282">L'implementazione dell'ereditarietà è ancora presente in F # per la compatibilità e rari casi in cui è la soluzione migliore a un problema, ma è necessario cercare tecniche alternative nei programmi F # quando si progetta per il polimorfismo, ad esempio l'implementazione dell'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="8f950-282">Inheritance implementation still exists in F# for compatibility and rare cases where it is the best solution to a problem, but alternative techniques should be sought in your F# programs when designing for polymorphism, such as interface implementation.</span></span>

### <a name="function-and-member-signatures"></a><span data-ttu-id="8f950-283">Firme di funzioni e membri</span><span class="sxs-lookup"><span data-stu-id="8f950-283">Function and member signatures</span></span>

#### <a name="use-tuples-for-return-values-when-returning-a-small-number-of-multiple-unrelated-values"></a><span data-ttu-id="8f950-284">Utilizzare le tuple per i valori restituiti quando viene restituito un numero ridotto di più valori non correlati</span><span class="sxs-lookup"><span data-stu-id="8f950-284">Use tuples for return values when returning a small number of multiple unrelated values</span></span>

<span data-ttu-id="8f950-285">Di seguito è riportato un esempio di utilizzo di una tupla in un tipo restituito:</span><span class="sxs-lookup"><span data-stu-id="8f950-285">Here is a good example of using a tuple in a return type:</span></span>

```fsharp
val divrem: BigInteger -> BigInteger -> BigInteger * BigInteger
```

<span data-ttu-id="8f950-286">Per i tipi restituiti che contengono molti componenti o per i quali i componenti sono correlati a una singola entità identificabile, provare a usare un tipo denominato anziché una tupla.</span><span class="sxs-lookup"><span data-stu-id="8f950-286">For return types containing many components, or where the components are related to a single identifiable entity, consider using a named type instead of a tuple.</span></span>

#### <a name="use-asynct-for-async-programming-at-f-api-boundaries"></a><span data-ttu-id="8f950-287">Usare `Async<T>` per la programmazione asincrona nei limiti dell'API F #</span><span class="sxs-lookup"><span data-stu-id="8f950-287">Use `Async<T>` for async programming at F# API boundaries</span></span>

<span data-ttu-id="8f950-288">Se è presente un'operazione sincrona corrispondente denominata `Operation` che restituisce un `T` , l'operazione asincrona deve essere denominata `AsyncOperation` se restituisce `Async<T>` o se restituisce `OperationAsync` `Task<T>` .</span><span class="sxs-lookup"><span data-stu-id="8f950-288">If there is a corresponding synchronous operation named `Operation` that returns a `T`, then the async operation should be named `AsyncOperation` if it returns `Async<T>` or `OperationAsync` if it returns `Task<T>`.</span></span> <span data-ttu-id="8f950-289">Per i tipi .NET comunemente usati che espongono i metodi Begin/End, provare `Async.FromBeginEnd` a usare per scrivere i metodi di estensione come facciata per fornire il modello di programmazione asincrona F # alle API .NET.</span><span class="sxs-lookup"><span data-stu-id="8f950-289">For commonly used .NET types that expose Begin/End methods, consider using `Async.FromBeginEnd` to write extension methods as a façade to provide the F# async programming model to those .NET APIs.</span></span>

```fsharp
type SomeType =
    member this.Compute(x:int): int =
        ...
    member this.AsyncCompute(x:int): Async<int> =
        ...

type System.ServiceModel.Channels.IInputChannel with
    member this.AsyncReceive() =
        ...
```

### <a name="exceptions"></a><span data-ttu-id="8f950-290">Eccezioni</span><span class="sxs-lookup"><span data-stu-id="8f950-290">Exceptions</span></span>

<span data-ttu-id="8f950-291">Per informazioni sull'uso appropriato di eccezioni, risultati e opzioni, vedere [gestione degli errori](conventions.md#error-management) .</span><span class="sxs-lookup"><span data-stu-id="8f950-291">See [Error Management](conventions.md#error-management) to learn about appropriate use of exceptions, results, and options.</span></span>

### <a name="extension-members"></a><span data-ttu-id="8f950-292">Membri di estensione</span><span class="sxs-lookup"><span data-stu-id="8f950-292">Extension Members</span></span>

#### <a name="carefully-apply-f-extension-members-in-f-to-f-components"></a><span data-ttu-id="8f950-293">Applicare con attenzione i membri di estensione F # nei componenti F #-to-F #</span><span class="sxs-lookup"><span data-stu-id="8f950-293">Carefully apply F# extension members in F#-to-F# components</span></span>

<span data-ttu-id="8f950-294">I membri di estensione F # in genere devono essere usati solo per le operazioni che si trovano nella chiusura di operazioni intrinseche associate a un tipo nella maggior parte delle modalità d'uso.</span><span class="sxs-lookup"><span data-stu-id="8f950-294">F# extension members should generally only be used for operations that are in the closure of intrinsic operations associated with a type in the majority of its modes of use.</span></span> <span data-ttu-id="8f950-295">Un uso comune è quello di fornire API più idiomatiche a F # per diversi tipi .NET:</span><span class="sxs-lookup"><span data-stu-id="8f950-295">One common use is to provide APIs that are more idiomatic to F# for various .NET types:</span></span>

```fsharp
type System.ServiceModel.Channels.IInputChannel with
    member this.AsyncReceive() =
        Async.FromBeginEnd(this.BeginReceive, this.EndReceive)

type System.Collections.Generic.IDictionary<'Key,'Value> with
    member this.TryGet key =
        let ok, v = this.TryGetValue key
        if ok then Some v else None
```

### <a name="union-types"></a><span data-ttu-id="8f950-296">Tipi di Unione</span><span class="sxs-lookup"><span data-stu-id="8f950-296">Union Types</span></span>

#### <a name="use-discriminated-unions-instead-of-class-hierarchies-for-tree-structured-data"></a><span data-ttu-id="8f950-297">Usare unioni discriminate anziché gerarchie di classi per i dati strutturati ad albero</span><span class="sxs-lookup"><span data-stu-id="8f950-297">Use discriminated unions instead of class hierarchies for tree-structured data</span></span>

<span data-ttu-id="8f950-298">Le strutture di tipo albero sono definite in modo ricorsivo.</span><span class="sxs-lookup"><span data-stu-id="8f950-298">Tree-like structures are recursively defined.</span></span> <span data-ttu-id="8f950-299">Questa operazione è imbarazzante con l'ereditarietà, ma è elegante con le unioni discriminate.</span><span class="sxs-lookup"><span data-stu-id="8f950-299">This is awkward with inheritance, but elegant with Discriminated Unions.</span></span>

```fsharp
type BST<'T> =
    | Empty
    | Node of 'T * BST<'T> * BST<'T>
```

<span data-ttu-id="8f950-300">La rappresentazione di dati di tipo albero con unioni discriminate consente inoltre di trarre vantaggio dalla completezza dei criteri di ricerca.</span><span class="sxs-lookup"><span data-stu-id="8f950-300">Representing tree-like data with Discriminated Unions also allows you to benefit from exhaustiveness in pattern matching.</span></span>

#### <a name="use-requirequalifiedaccess-on-union-types-whose-case-names-are-not-sufficiently-unique"></a><span data-ttu-id="8f950-301">Utilizzare `[<RequireQualifiedAccess>]` sui tipi unione i cui nomi case non sono sufficientemente univoci</span><span class="sxs-lookup"><span data-stu-id="8f950-301">Use `[<RequireQualifiedAccess>]` on union types whose case names are not sufficiently unique</span></span>

<span data-ttu-id="8f950-302">È possibile che si trovi in un dominio in cui lo stesso nome è il nome migliore per diversi elementi, ad esempio i case di Unione discriminati.</span><span class="sxs-lookup"><span data-stu-id="8f950-302">You may find yourself in a domain where the same name is the best name for different things, such as Discriminated Union cases.</span></span> <span data-ttu-id="8f950-303">È possibile utilizzare `[<RequireQualifiedAccess>]` per evitare ambiguità nei nomi dei case al fine di evitare l'attivazione di errori di confusione dovuti all'ombreggiatura dipendente dall'ordinamento delle `open` istruzioni</span><span class="sxs-lookup"><span data-stu-id="8f950-303">You can use `[<RequireQualifiedAccess>]` to disambiguate case names in order to avoid triggering confusing errors due to shadowing dependent on the ordering of `open` statements</span></span>

#### <a name="hide-the-representations-of-discriminated-unions-for-binary-compatible-apis-if-the-design-of-these-types-is-likely-to-evolve"></a><span data-ttu-id="8f950-304">Nascondere le rappresentazioni delle unioni discriminate per le API binarie compatibili se è probabile che la progettazione di questi tipi evolva</span><span class="sxs-lookup"><span data-stu-id="8f950-304">Hide the representations of discriminated unions for binary compatible APIs if the design of these types is likely to evolve</span></span>

<span data-ttu-id="8f950-305">I tipi di Unione si basano sui moduli di corrispondenza dei modelli F # per un modello di programmazione conciso.</span><span class="sxs-lookup"><span data-stu-id="8f950-305">Unions types rely on F# pattern-matching forms for a succinct programming model.</span></span> <span data-ttu-id="8f950-306">Come indicato in precedenza, è consigliabile evitare di rivelare rappresentazioni di dati concreti se è probabile che la progettazione di questi tipi si evolva.</span><span class="sxs-lookup"><span data-stu-id="8f950-306">As mentioned previously, you should avoid revealing concrete data representations if the design of these types is likely to evolve.</span></span>

<span data-ttu-id="8f950-307">La rappresentazione di un'unione discriminata, ad esempio, può essere nascosta utilizzando una dichiarazione privata o interna oppure utilizzando un file di firma.</span><span class="sxs-lookup"><span data-stu-id="8f950-307">For example, the representation of a discriminated union can be hidden using a private or internal declaration, or by using a signature file.</span></span>

```fsharp
type Union =
    private
    | CaseA of int
    | CaseB of string
```

<span data-ttu-id="8f950-308">Se si rivelano le unioni discriminate in modo indiscriminato, potrebbe risultare difficile eseguire la versione della libreria senza interruzioni del codice utente.</span><span class="sxs-lookup"><span data-stu-id="8f950-308">If you reveal discriminated unions indiscriminately, you may find it hard to version your library without breaking user code.</span></span> <span data-ttu-id="8f950-309">In alternativa, considerare la possibilità di rivelare uno o più criteri attivi per consentire la corrispondenza dei criteri con i valori del tipo.</span><span class="sxs-lookup"><span data-stu-id="8f950-309">Instead, consider revealing one or more active patterns to permit pattern matching over values of your type.</span></span>

<span data-ttu-id="8f950-310">I criteri attivi forniscono un metodo alternativo per fornire agli utenti F # i criteri di ricerca, evitando di esporre direttamente i tipi di Unione F #.</span><span class="sxs-lookup"><span data-stu-id="8f950-310">Active patterns provide an alternate way to provide F# consumers with pattern matching while avoiding exposing F# Union Types directly.</span></span>

### <a name="inline-functions-and-member-constraints"></a><span data-ttu-id="8f950-311">Funzioni inline e vincoli del membro</span><span class="sxs-lookup"><span data-stu-id="8f950-311">Inline Functions and Member Constraints</span></span>

#### <a name="define-generic-numeric-algorithms-using-inline-functions-with-implied-member-constraints-and-statically-resolved-generic-types"></a><span data-ttu-id="8f950-312">Definire algoritmi numerici generici usando funzioni inline con vincoli di membri impliciti e tipi generici risolti in modo statico</span><span class="sxs-lookup"><span data-stu-id="8f950-312">Define generic numeric algorithms using inline functions with implied member constraints and statically resolved generic types</span></span>

<span data-ttu-id="8f950-313">I vincoli dei membri aritmetici e i vincoli di confronto F # sono uno standard per la programmazione F #.</span><span class="sxs-lookup"><span data-stu-id="8f950-313">Arithmetic member constraints and F# comparison constraints are a standard for F# programming.</span></span> <span data-ttu-id="8f950-314">Si consideri il codice di esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="8f950-314">For example, consider the following code:</span></span>

```fsharp
let inline highestCommonFactor a b =
    let rec loop a b =
        if a = LanguagePrimitives.GenericZero<_> then b
        elif a < b then loop a (b - a)
        else loop (a - b) b
    loop a b
```

<span data-ttu-id="8f950-315">Il tipo di questa funzione è il seguente:</span><span class="sxs-lookup"><span data-stu-id="8f950-315">The type of this function is as follows:</span></span>

```fsharp
val inline highestCommonFactor : ^T -> ^T -> ^T
                when ^T : (static member Zero : ^T)
                and ^T : (static member ( - ) : ^T * ^T -> ^T)
                and ^T : equality
                and ^T : comparison
```

<span data-ttu-id="8f950-316">Si tratta di una funzione adatta per un'API pubblica in una libreria matematica.</span><span class="sxs-lookup"><span data-stu-id="8f950-316">This is a suitable function for a public API in a mathematical library.</span></span>

#### <a name="avoid-using-member-constraints-to-simulate-type-classes-and-duck-typing"></a><span data-ttu-id="8f950-317">Evitare di usare vincoli di membro per simulare classi di tipi e tipi Duck</span><span class="sxs-lookup"><span data-stu-id="8f950-317">Avoid using member constraints to simulate type classes and duck typing</span></span>

<span data-ttu-id="8f950-318">È possibile simulare "Duck Typing" con i vincoli del membro F #.</span><span class="sxs-lookup"><span data-stu-id="8f950-318">It is possible to simulate "duck typing" using F# member constraints.</span></span> <span data-ttu-id="8f950-319">Tuttavia, i membri che utilizzano questa operazione non devono essere in genere utilizzati nelle progettazioni della libreria F # a F #.</span><span class="sxs-lookup"><span data-stu-id="8f950-319">However, members that make use of this should not in general be used in F#-to-F# library designs.</span></span> <span data-ttu-id="8f950-320">Ciò è dovuto al fatto che le progettazioni di librerie basate su vincoli impliciti non noti o non standard tendono a impedire che il codice utente diventi non flessibile e associato a un modello di Framework specifico.</span><span class="sxs-lookup"><span data-stu-id="8f950-320">This is because library designs based on unfamiliar or non-standard implicit constraints tend to cause user code to become inflexible and tied to one particular framework pattern.</span></span>

<span data-ttu-id="8f950-321">Inoltre, è probabile che l'utilizzo intensivo di vincoli di membri in questo modo possa causare tempi di compilazione molto lunghi.</span><span class="sxs-lookup"><span data-stu-id="8f950-321">Additionally, there is a good chance that heavy use of member constraints in this manner can result in very long compile times.</span></span>

### <a name="operator-definitions"></a><span data-ttu-id="8f950-322">Definizioni degli operatori</span><span class="sxs-lookup"><span data-stu-id="8f950-322">Operator Definitions</span></span>

#### <a name="avoid-defining-custom-symbolic-operators"></a><span data-ttu-id="8f950-323">Evitare di definire operatori simbolici personalizzati</span><span class="sxs-lookup"><span data-stu-id="8f950-323">Avoid defining custom symbolic operators</span></span>

<span data-ttu-id="8f950-324">Gli operatori personalizzati sono essenziali in alcune situazioni e sono dispositivi di notazione estremamente utili all'interno di un grande corpo di codice di implementazione.</span><span class="sxs-lookup"><span data-stu-id="8f950-324">Custom operators are essential in some situations and are highly useful notational devices within a large body of implementation code.</span></span> <span data-ttu-id="8f950-325">Per i nuovi utenti di una libreria, le funzioni denominate sono spesso più facili da usare.</span><span class="sxs-lookup"><span data-stu-id="8f950-325">For new users of a library, named functions are often easier to use.</span></span> <span data-ttu-id="8f950-326">Gli operatori simbolici personalizzati, inoltre, possono essere difficili da documentare, mentre gli utenti trovano più difficile individuare la guida sugli operatori, a causa delle limitazioni esistenti nei motori IDE e di ricerca.</span><span class="sxs-lookup"><span data-stu-id="8f950-326">In addition, custom symbolic operators can be hard to document, and users find it more difficult to look up help on operators, due to existing limitations in IDE and search engines.</span></span>

<span data-ttu-id="8f950-327">Di conseguenza, è preferibile pubblicare le funzionalità come funzioni e membri denominati, nonché esporre gli operatori per questa funzionalità solo se i vantaggi della notazione superano la documentazione e il costo cognitivo per la loro presenza.</span><span class="sxs-lookup"><span data-stu-id="8f950-327">As a result, it is best to publish your functionality as named functions and members, and additionally expose operators for this functionality only if the notational benefits outweigh the documentation and cognitive cost of having them.</span></span>

### <a name="units-of-measure"></a><span data-ttu-id="8f950-328">Unità di misura</span><span class="sxs-lookup"><span data-stu-id="8f950-328">Units of Measure</span></span>

#### <a name="carefully-use-units-of-measure-for-added-type-safety-in-f-code"></a><span data-ttu-id="8f950-329">Usare con attenzione le unità di misura per la sicurezza dei tipi aggiuntiva nel codice F #</span><span class="sxs-lookup"><span data-stu-id="8f950-329">Carefully use units of measure for added type safety in F# code</span></span>

<span data-ttu-id="8f950-330">Le informazioni di tipizzazione aggiuntive per le unità di misura vengono cancellate se visualizzate da altri linguaggi .NET.</span><span class="sxs-lookup"><span data-stu-id="8f950-330">Additional typing information for units of measure is erased when viewed by other .NET languages.</span></span> <span data-ttu-id="8f950-331">Tenere presente che i componenti, gli strumenti e la reflection .NET vedranno i tipi-sans-units.</span><span class="sxs-lookup"><span data-stu-id="8f950-331">Be aware that .NET components, tools, and reflection will see types-sans-units.</span></span> <span data-ttu-id="8f950-332">Ad esempio, i consumer C# vedranno `float` invece di `float<kg>` .</span><span class="sxs-lookup"><span data-stu-id="8f950-332">For example, C# consumers will see `float` rather than `float<kg>`.</span></span>

### <a name="type-abbreviations"></a><span data-ttu-id="8f950-333">Abbreviazioni dei tipi</span><span class="sxs-lookup"><span data-stu-id="8f950-333">Type Abbreviations</span></span>

#### <a name="carefully-use-type-abbreviations-to-simplify-f-code"></a><span data-ttu-id="8f950-334">Usare con attenzione le abbreviazioni di tipo per semplificare il codice F #</span><span class="sxs-lookup"><span data-stu-id="8f950-334">Carefully use type abbreviations to simplify F# code</span></span>

<span data-ttu-id="8f950-335">I componenti .NET, gli strumenti e la reflection non visualizzeranno nomi abbreviati per i tipi.</span><span class="sxs-lookup"><span data-stu-id="8f950-335">.NET components, tools, and reflection will not see abbreviated names for types.</span></span> <span data-ttu-id="8f950-336">Un uso significativo delle abbreviazioni di tipo può anche rendere un dominio più complesso rispetto al fatto, che può confondere i consumer.</span><span class="sxs-lookup"><span data-stu-id="8f950-336">Significant usage of type abbreviations can also make a domain appear more complex than it actually is, which could confuse consumers.</span></span>

#### <a name="avoid-type-abbreviations-for-public-types-whose-members-and-properties-should-be-intrinsically-different-to-those-available-on-the-type-being-abbreviated"></a><span data-ttu-id="8f950-337">Evitare abbreviazioni di tipo per i tipi pubblici i cui membri e proprietà devono essere intrinsecamente diversi da quelli disponibili sul tipo abbreviato</span><span class="sxs-lookup"><span data-stu-id="8f950-337">Avoid type abbreviations for public types whose members and properties should be intrinsically different to those available on the type being abbreviated</span></span>

<span data-ttu-id="8f950-338">In questo caso, il tipo abbreviato rivela troppo la rappresentazione del tipo effettivo definito.</span><span class="sxs-lookup"><span data-stu-id="8f950-338">In this case, the type being abbreviated reveals too much about the representation of the actual type being defined.</span></span> <span data-ttu-id="8f950-339">In alternativa, è consigliabile eseguire il wrapping dell'abbreviazione in un tipo di classe o in un'unione discriminata a singolo caso oppure, quando le prestazioni sono essenziali, è consigliabile usare un tipo di struct per eseguire il wrapping dell'abbreviazione.</span><span class="sxs-lookup"><span data-stu-id="8f950-339">Instead, consider wrapping the abbreviation in a class type or a single-case discriminated union (or, when performance is essential, consider using a struct type to wrap the abbreviation).</span></span>

<span data-ttu-id="8f950-340">Ad esempio, si tenta di definire una mappa multimappa come caso speciale di una mappa F #, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="8f950-340">For example, it is tempting to define a multi-map as a special case of an F# map, for example:</span></span>

```fsharp
type MultiMap<'Key,'Value> = Map<'Key,'Value list>
```

<span data-ttu-id="8f950-341">Tuttavia, le operazioni logiche per la notazione del punto su questo tipo non sono le stesse delle operazioni su una mappa. ad esempio, è ragionevole che l'operatore di ricerca esegue il mapping. [key] restituisce l'elenco vuoto se la chiave non è presente nel dizionario, anziché generare un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="8f950-341">However, the logical dot-notation operations on this type are not the same as the operations on a Map – for example, it is reasonable that the lookup operator map.[key] return the empty list if the key is not in the dictionary, rather than raising an exception.</span></span>

## <a name="guidelines-for-libraries-for-use-from-other-net-languages"></a><span data-ttu-id="8f950-342">Linee guida per le librerie da usare con altri linguaggi .NET</span><span class="sxs-lookup"><span data-stu-id="8f950-342">Guidelines for libraries for Use from other .NET Languages</span></span>

<span data-ttu-id="8f950-343">Quando si progettano le librerie per l'uso da altri linguaggi .NET, è importante attenersi alle [linee guida di progettazione della libreria .NET](../../standard/design-guidelines/index.md).</span><span class="sxs-lookup"><span data-stu-id="8f950-343">When designing libraries for use from other .NET languages, it is important to adhere to the [.NET Library Design Guidelines](../../standard/design-guidelines/index.md).</span></span> <span data-ttu-id="8f950-344">In questo documento, queste librerie sono etichettate come librerie .NET Vanilla, a differenza delle librerie con rivolte a F # che usano costrutti F # senza restrizioni.</span><span class="sxs-lookup"><span data-stu-id="8f950-344">In this document, these libraries are labeled as vanilla .NET libraries, as opposed to F#-facing libraries that use F# constructs without restriction.</span></span> <span data-ttu-id="8f950-345">La progettazione di librerie .NET Vanilla significa fornire API Note e idiomatiche coerenti con il resto del .NET Framework riducendo al minimo l'uso di costrutti specifici di F # nell'API pubblica.</span><span class="sxs-lookup"><span data-stu-id="8f950-345">Designing vanilla .NET libraries means providing familiar and idiomatic APIs consistent with the rest of the .NET Framework by minimizing the use of F#-specific constructs in the public API.</span></span> <span data-ttu-id="8f950-346">Le regole sono illustrate nelle sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="8f950-346">The rules are explained in the following sections.</span></span>

### <a name="namespace-and-type-design-for-libraries-for-use-from-other-net-languages"></a><span data-ttu-id="8f950-347">Progettazione dello spazio dei nomi e del tipo (per le librerie da usare con altri linguaggi .NET)</span><span class="sxs-lookup"><span data-stu-id="8f950-347">Namespace and Type design (for libraries for use from other .NET Languages)</span></span>

#### <a name="apply-the-net-naming-conventions-to-the-public-api-of-your-components"></a><span data-ttu-id="8f950-348">Applicare le convenzioni di denominazione .NET all'API pubblica dei componenti</span><span class="sxs-lookup"><span data-stu-id="8f950-348">Apply the .NET naming conventions to the public API of your components</span></span>

<span data-ttu-id="8f950-349">Prestare particolare attenzione all'uso di nomi abbreviati e alle linee guida per la capitalizzazione di .NET.</span><span class="sxs-lookup"><span data-stu-id="8f950-349">Pay special attention to the use of abbreviated names and the .NET capitalization guidelines.</span></span>

```fsharp
type pCoord = ...
    member this.theta = ...

type PolarCoordinate = ...
    member this.Theta = ...
```

#### <a name="use-namespaces-types-and-members-as-the-primary-organizational-structure-for-your-components"></a><span data-ttu-id="8f950-350">Usare spazi dei nomi, tipi e membri come struttura organizzativa primaria per i componenti</span><span class="sxs-lookup"><span data-stu-id="8f950-350">Use namespaces, types, and members as the primary organizational structure for your components</span></span>

<span data-ttu-id="8f950-351">Tutti i file contenenti funzionalità pubbliche devono iniziare con una `namespace` dichiarazione e le uniche entità pubbliche negli spazi dei nomi devono essere tipi.</span><span class="sxs-lookup"><span data-stu-id="8f950-351">All files containing public functionality should begin with a `namespace` declaration, and the only public-facing entities in namespaces should be types.</span></span> <span data-ttu-id="8f950-352">Non usare i moduli F #.</span><span class="sxs-lookup"><span data-stu-id="8f950-352">Do not use F# modules.</span></span>

<span data-ttu-id="8f950-353">Usare moduli non pubblici per mantenere il codice di implementazione, i tipi di utilità e le funzioni di utilità.</span><span class="sxs-lookup"><span data-stu-id="8f950-353">Use non-public modules to hold implementation code, utility types, and utility functions.</span></span>

<span data-ttu-id="8f950-354">I tipi statici dovrebbero essere preferiti rispetto ai moduli, perché consentono l'evoluzione futura dell'API per l'uso dell'overload e di altri concetti di progettazione dell'API .NET che non possono essere usati nei moduli F #.</span><span class="sxs-lookup"><span data-stu-id="8f950-354">Static types should be preferred over modules, as they allow for future evolution of the API to use overloading and other .NET API design concepts that may not be used within F# modules.</span></span>

<span data-ttu-id="8f950-355">Ad esempio, al posto della seguente API pubblica:</span><span class="sxs-lookup"><span data-stu-id="8f950-355">For example, in place of the following public API:</span></span>

```fsharp
module Fabrikam

module Utilities =
    let Name = "Bob"
    let Add2 x y = x + y
    let Add3 x y z = x + y + z
```

<span data-ttu-id="8f950-356">In alternativa, prendere in considerazione:</span><span class="sxs-lookup"><span data-stu-id="8f950-356">Consider instead:</span></span>

```fsharp
namespace Fabrikam

[<AbstractClass; Sealed>]
type Utilities =
    static member Name = "Bob"
    static member Add(x,y) = x + y
    static member Add(x,y,z) = x + y + z
```

#### <a name="use-f-record-types-in-vanilla-net-apis-if-the-design-of-the-types-wont-evolve"></a><span data-ttu-id="8f950-357">Usare i tipi di record F # nelle API Vanilla .NET se la progettazione dei tipi non evolverà</span><span class="sxs-lookup"><span data-stu-id="8f950-357">Use F# record types in vanilla .NET APIs if the design of the types won't evolve</span></span>

<span data-ttu-id="8f950-358">I tipi di record F # vengono compilati in una semplice classe .NET.</span><span class="sxs-lookup"><span data-stu-id="8f950-358">F# record types compile to a simple .NET class.</span></span> <span data-ttu-id="8f950-359">Questi sono adatti per alcuni tipi semplici e stabili nelle API.</span><span class="sxs-lookup"><span data-stu-id="8f950-359">These are suitable for some simple, stable types in APIs.</span></span> <span data-ttu-id="8f950-360">Provare a usare `[<NoEquality>]` gli `[<NoComparison>]` attributi e per disattivare la generazione automatica di interfacce.</span><span class="sxs-lookup"><span data-stu-id="8f950-360">Consider using the `[<NoEquality>]` and `[<NoComparison>]` attributes to suppress the automatic generation of interfaces.</span></span> <span data-ttu-id="8f950-361">Evitare inoltre di usare campi di record modificabili nelle API Vanilla .NET perché espongono un campo pubblico.</span><span class="sxs-lookup"><span data-stu-id="8f950-361">Also avoid using mutable record fields in vanilla .NET APIs as these expose a public field.</span></span> <span data-ttu-id="8f950-362">Considerare sempre se una classe fornisce un'opzione più flessibile per l'evoluzione futura dell'API.</span><span class="sxs-lookup"><span data-stu-id="8f950-362">Always consider whether a class would provide a more flexible option for future evolution of the API.</span></span>

<span data-ttu-id="8f950-363">Il codice F # seguente, ad esempio, espone l'API pubblica a un consumer C#:</span><span class="sxs-lookup"><span data-stu-id="8f950-363">For example, the following F# code exposes the public API to a C# consumer:</span></span>

<span data-ttu-id="8f950-364">F#:</span><span class="sxs-lookup"><span data-stu-id="8f950-364">F#:</span></span>

```fsharp
[<NoEquality; NoComparison>]
type MyRecord =
    { FirstThing: int
        SecondThing: string }
```

<span data-ttu-id="8f950-365">C#:</span><span class="sxs-lookup"><span data-stu-id="8f950-365">C#:</span></span>

```csharp
public sealed class MyRecord
{
    public MyRecord(int firstThing, string secondThing);
    public int FirstThing { get; }
    public string SecondThing { get; }
}
```

#### <a name="hide-the-representation-of-f-union-types-in-vanilla-net-apis"></a><span data-ttu-id="8f950-366">Nascondere la rappresentazione di tipi di Unione F # nelle API Vanilla .NET</span><span class="sxs-lookup"><span data-stu-id="8f950-366">Hide the representation of F# union types in vanilla .NET APIs</span></span>

<span data-ttu-id="8f950-367">I tipi di Unione f # non vengono comunemente usati tra i limiti dei componenti, anche per la codifica F #-to-F #.</span><span class="sxs-lookup"><span data-stu-id="8f950-367">F# union types are not commonly used across component boundaries, even for F#-to-F# coding.</span></span> <span data-ttu-id="8f950-368">Si tratta di un dispositivo di implementazione eccellente se usato internamente all'interno di componenti e librerie.</span><span class="sxs-lookup"><span data-stu-id="8f950-368">They are an excellent implementation device when used internally within components and libraries.</span></span>

<span data-ttu-id="8f950-369">Quando si progetta un'API Vanilla .NET, è consigliabile nascondere la rappresentazione di un tipo di Unione usando una dichiarazione privata o un file di firma.</span><span class="sxs-lookup"><span data-stu-id="8f950-369">When designing a vanilla .NET API, consider hiding the representation of a union type by using either a private declaration or a signature file.</span></span>

```fsharp
type PropLogic =
    private
    | And of PropLogic * PropLogic
    | Not of PropLogic
    | True
```

<span data-ttu-id="8f950-370">È anche possibile aumentare i tipi che usano internamente una rappresentazione di Unione con i membri per fornire un oggetto desiderato. API per il NET.</span><span class="sxs-lookup"><span data-stu-id="8f950-370">You may also augment types that use a union representation internally with members to provide a desired .NET-facing API.</span></span>

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

#### <a name="design-gui-and-other-components-using-the-design-patterns-of-the-framework"></a><span data-ttu-id="8f950-371">Progettare GUI e altri componenti usando i modelli di progettazione del Framework</span><span class="sxs-lookup"><span data-stu-id="8f950-371">Design GUI and other components using the design patterns of the framework</span></span>

<span data-ttu-id="8f950-372">In .NET sono disponibili molti Framework diversi, ad esempio WinForms, WPF e ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="8f950-372">There are many different frameworks available within .NET, such as WinForms, WPF, and ASP.NET.</span></span> <span data-ttu-id="8f950-373">Quando si progettano componenti da usare in questi Framework, è consigliabile usare le convenzioni di denominazione e progettazione per ciascuna di esse.</span><span class="sxs-lookup"><span data-stu-id="8f950-373">Naming and design conventions for each should be used if you are designing components for use in these frameworks.</span></span> <span data-ttu-id="8f950-374">Per la programmazione WPF, ad esempio, adottare modelli di progettazione WPF per le classi in corso di progettazione.</span><span class="sxs-lookup"><span data-stu-id="8f950-374">For example, for WPF programming, adopt WPF design patterns for the classes you are designing.</span></span> <span data-ttu-id="8f950-375">Per i modelli nella programmazione dell'interfaccia utente, usare modelli di progettazione quali eventi e raccolte basate su notifiche, ad esempio quelli disponibili in <xref:System.Collections.ObjectModel> .</span><span class="sxs-lookup"><span data-stu-id="8f950-375">For models in user interface programming, use design patterns such as events and notification-based collections such as those found in <xref:System.Collections.ObjectModel>.</span></span>

### <a name="object-and-member-design-for-libraries-for-use-from-other-net-languages"></a><span data-ttu-id="8f950-376">Progettazione di oggetti e membri (per le librerie da usare con altri linguaggi .NET)</span><span class="sxs-lookup"><span data-stu-id="8f950-376">Object and Member design (for libraries for use from other .NET Languages)</span></span>

#### <a name="use-the-clievent-attribute-to-expose-net-events"></a><span data-ttu-id="8f950-377">Usare l'attributo CLIEvent (per esporre gli eventi .NET</span><span class="sxs-lookup"><span data-stu-id="8f950-377">Use the CLIEvent attribute to expose .NET events</span></span>

<span data-ttu-id="8f950-378">Costruire un `DelegateEvent` oggetto con un tipo delegato .NET specifico che accetta un oggetto e `EventArgs` , anziché un oggetto `Event` , che usa semplicemente il `FSharpHandler` tipo per impostazione predefinita, in modo che gli eventi vengano pubblicati in modo familiare in altri linguaggi .NET.</span><span class="sxs-lookup"><span data-stu-id="8f950-378">Construct a `DelegateEvent` with a specific .NET delegate type that takes an object and `EventArgs` (rather than an `Event`, which just uses the `FSharpHandler` type by default) so that the events are published in the familiar way to other .NET languages.</span></span>

```fsharp
type MyBadType() =
    let myEv = new Event<int>()

    [<CLIEvent>]
    member this.MyEvent = myEv.Publish

type MyEventArgs(x: int) =
    inherit System.EventArgs()
    member this.X = x

    /// A type in a component designed for use from other .NET languages
type MyGoodType() =
    let myEv = new DelegateEvent<EventHandler<MyEventArgs>>()

    [<CLIEvent>]
    member this.MyEvent = myEv.Publish
```

#### <a name="expose-asynchronous-operations-as-methods-that-return-net-tasks"></a><span data-ttu-id="8f950-379">Esporre le operazioni asincrone come metodi che restituiscono attività .NET</span><span class="sxs-lookup"><span data-stu-id="8f950-379">Expose asynchronous operations as methods that return .NET tasks</span></span>

<span data-ttu-id="8f950-380">Le attività vengono usate in .NET per rappresentare i calcoli asincroni attivi.</span><span class="sxs-lookup"><span data-stu-id="8f950-380">Tasks are used in .NET to represent active asynchronous computations.</span></span> <span data-ttu-id="8f950-381">Le attività sono in genere meno composizionali rispetto `Async<T>` agli oggetti F #, perché rappresentano attività "già in esecuzione" e non possono essere composte insieme in modi che eseguono la composizione parallela o che nascondono la propagazione dei segnali di annullamento e altri parametri contestuali.</span><span class="sxs-lookup"><span data-stu-id="8f950-381">Tasks are in general less compositional than F# `Async<T>` objects, since they represent "already executing" tasks and can't be composed together in ways that perform parallel composition, or which hide the propagation of cancellation signals and other contextual parameters.</span></span>

<span data-ttu-id="8f950-382">Tuttavia, nonostante questo, i metodi che restituiscono attività sono la rappresentazione standard della programmazione asincrona in .NET.</span><span class="sxs-lookup"><span data-stu-id="8f950-382">However, despite this, methods that return Tasks are the standard representation of asynchronous programming on .NET.</span></span>

```fsharp
/// A type in a component designed for use from other .NET languages
type MyType() =

    let compute (x: int): Async<int> = async { ... }

    member this.ComputeAsync(x) = compute x |> Async.StartAsTask
```

<span data-ttu-id="8f950-383">Si vorrà spesso accettare anche un token di annullamento esplicito:</span><span class="sxs-lookup"><span data-stu-id="8f950-383">You will frequently also want to accept an explicit cancellation token:</span></span>

```fsharp
/// A type in a component designed for use from other .NET languages
type MyType() =
    let compute(x: int): Async<int> = async { ... }
    member this.ComputeAsTask(x, cancellationToken) = Async.StartAsTask(compute x, cancellationToken)
```

#### <a name="use-net-delegate-types-instead-of-f-function-types"></a><span data-ttu-id="8f950-384">Usare i tipi di delegato .NET anziché i tipi di funzione F #</span><span class="sxs-lookup"><span data-stu-id="8f950-384">Use .NET delegate types instead of F# function types</span></span>

<span data-ttu-id="8f950-385">Qui "i tipi di funzione F #" significano "Arrow", ad esempio `int -> int` .</span><span class="sxs-lookup"><span data-stu-id="8f950-385">Here "F# function types" mean "arrow" types like `int -> int`.</span></span>

<span data-ttu-id="8f950-386">Anziché:</span><span class="sxs-lookup"><span data-stu-id="8f950-386">Instead of this:</span></span>

```fsharp
member this.Transform(f: int->int) =
    ...
```

<span data-ttu-id="8f950-387">Eseguire questa operazione:</span><span class="sxs-lookup"><span data-stu-id="8f950-387">Do this:</span></span>

```fsharp
member this.Transform(f: Func<int,int>) =
    ...
```

<span data-ttu-id="8f950-388">Il tipo di funzione F # appare come `class FSharpFunc<T,U>` ad altri linguaggi .NET ed è meno adatto per le funzionalità del linguaggio e gli strumenti che comprendono i tipi delegati.</span><span class="sxs-lookup"><span data-stu-id="8f950-388">The F# function type appears as `class FSharpFunc<T,U>` to other .NET languages, and is less suitable for language features and tooling that understands delegate types.</span></span> <span data-ttu-id="8f950-389">Quando si crea un metodo di ordine superiore destinato a .NET Framework 3,5 o superiore, i `System.Func` `System.Action` delegati e sono le API appropriate per la pubblicazione per consentire agli sviluppatori .NET di utilizzare tali API in modo insufficiente.</span><span class="sxs-lookup"><span data-stu-id="8f950-389">When authoring a higher-order method targeting .NET Framework 3.5 or higher, the `System.Func` and `System.Action` delegates are the right APIs to publish to enable .NET developers to consume these APIs in a low-friction manner.</span></span> <span data-ttu-id="8f950-390">Quando la destinazione è .NET Framework 2,0, i tipi delegati definiti dal sistema sono più limitati. provare a usare tipi delegati predefiniti, ad esempio `System.Converter<T,U>` o a definire un tipo delegato specifico.</span><span class="sxs-lookup"><span data-stu-id="8f950-390">(When targeting .NET Framework 2.0, the system-defined delegate types are more limited; consider using predefined delegate types such as `System.Converter<T,U>` or defining a specific delegate type.)</span></span>

<span data-ttu-id="8f950-391">Sul lato flip, i delegati .NET non sono naturali per le librerie con rivolto a F # (vedere la sezione successiva sulle librerie F #).</span><span class="sxs-lookup"><span data-stu-id="8f950-391">On the flip side, .NET delegates are not natural for F#-facing libraries (see the next Section on F#-facing libraries).</span></span> <span data-ttu-id="8f950-392">Di conseguenza, una strategia di implementazione comune quando si sviluppano metodi di ordine superiore per le librerie Vanilla .NET consiste nel creare tutte le implementazioni usando i tipi di funzione F #, quindi creare l'API pubblica usando i delegati come facciata sottile sopra l'effettiva implementazione di F #.</span><span class="sxs-lookup"><span data-stu-id="8f950-392">As a result, a common implementation strategy when developing higher-order methods for vanilla .NET libraries is to author all the implementation using F# function types, and then create the public API using delegates as a thin façade atop the actual F# implementation.</span></span>

#### <a name="use-the-trygetvalue-pattern-instead-of-returning-f-option-values-and-prefer-method-overloading-to-taking-f-option-values-as-arguments"></a><span data-ttu-id="8f950-393">Usare il modello TryGetValue anziché restituire i valori delle opzioni F # e preferire l'overload del metodo per accettare i valori delle opzioni F # come argomenti</span><span class="sxs-lookup"><span data-stu-id="8f950-393">Use the TryGetValue pattern instead of returning F# option values, and prefer method overloading to taking F# option values as arguments</span></span>

<span data-ttu-id="8f950-394">I modelli comuni di utilizzo per il tipo di opzione F # nelle API sono implementati in modo migliore nelle API Vanilla .NET utilizzando le tecniche standard di progettazione .NET.</span><span class="sxs-lookup"><span data-stu-id="8f950-394">Common patterns of use for the F# option type in APIs are better implemented in vanilla .NET APIs using standard .NET design techniques.</span></span> <span data-ttu-id="8f950-395">Anziché restituire un valore di opzione F #, provare a usare il tipo restituito bool più un parametro out come nel modello "TryGetValue".</span><span class="sxs-lookup"><span data-stu-id="8f950-395">Instead of returning an F# option value, consider using the bool return type plus an out parameter as in the "TryGetValue" pattern.</span></span> <span data-ttu-id="8f950-396">Anziché accettare i valori delle opzioni F # come parametri, è consigliabile usare l'overload del metodo o gli argomenti facoltativi.</span><span class="sxs-lookup"><span data-stu-id="8f950-396">And instead of taking F# option values as parameters, consider using method overloading or optional arguments.</span></span>

```fsharp
member this.ReturnOption() = Some 3

member this.ReturnBoolAndOut(outVal: byref<int>) =
    outVal <- 3
    true

member this.ParamOption(x: int, y: int option) =
    match y with
    | Some y2 -> x + y2
    | None -> x

member this.ParamOverload(x: int) = x

member this.ParamOverload(x: int, y: int) = x + y
```

#### <a name="use-the-net-collection-interface-types-ienumerablet-and-idictionarykeyvalue-for-parameters-and-return-values"></a><span data-ttu-id="8f950-397">Usare i tipi di interfaccia di raccolta .NET della \< chiave IEnumerable T \> e IDictionary \< , il valore \> per i parametri e i valori restituiti</span><span class="sxs-lookup"><span data-stu-id="8f950-397">Use the .NET collection interface types IEnumerable\<T\> and IDictionary\<Key,Value\> for parameters and return values</span></span>

<span data-ttu-id="8f950-398">Evitare l'uso di tipi di raccolta concreti, ad esempio matrici .NET `T[]` , tipi F # `list<T>` `Map<Key,Value>` e `Set<T>` tipi di raccolta concreti .NET, ad esempio `Dictionary<Key,Value>` .</span><span class="sxs-lookup"><span data-stu-id="8f950-398">Avoid the use of concrete collection types such as .NET arrays `T[]`, F# types `list<T>`, `Map<Key,Value>` and `Set<T>`, and .NET concrete collection types such as `Dictionary<Key,Value>`.</span></span> <span data-ttu-id="8f950-399">Le linee guida per la progettazione di librerie .NET offrono consigli utili per l'utilizzo di diversi tipi di raccolta, ad esempio `IEnumerable<T>` .</span><span class="sxs-lookup"><span data-stu-id="8f950-399">The .NET Library Design Guidelines have good advice regarding when to use various collection types like `IEnumerable<T>`.</span></span> <span data-ttu-id="8f950-400">In alcune circostanze, l'utilizzo di matrici ( `T[]` ) è accettabile in base alle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="8f950-400">Some use of arrays (`T[]`) is acceptable in some circumstances, on performance grounds.</span></span> <span data-ttu-id="8f950-401">Si noti in particolare che `seq<T>` è solo l'alias F # per `IEnumerable<T>` e quindi seq è spesso un tipo appropriato per un'API Vanilla .NET.</span><span class="sxs-lookup"><span data-stu-id="8f950-401">Note especially that `seq<T>` is just the F# alias for `IEnumerable<T>`, and thus seq is often an appropriate type for a vanilla .NET API.</span></span>

<span data-ttu-id="8f950-402">Anziché gli elenchi F #:</span><span class="sxs-lookup"><span data-stu-id="8f950-402">Instead of F# lists:</span></span>

```fsharp
member this.PrintNames(names: string list) =
    ...
```

<span data-ttu-id="8f950-403">USA sequenze F #:</span><span class="sxs-lookup"><span data-stu-id="8f950-403">Use F# sequences:</span></span>

```fsharp
member this.PrintNames(names: seq<string>) =
    ...
```

#### <a name="use-the-unit-type-as-the-only-input-type-of-a-method-to-define-a-zero-argument-method-or-as-the-only-return-type-to-define-a-void-returning-method"></a><span data-ttu-id="8f950-404">Usare il tipo di unità come unico tipo di input di un metodo per definire un metodo di argomento zero o come unico tipo restituito per definire un metodo che restituisce void</span><span class="sxs-lookup"><span data-stu-id="8f950-404">Use the unit type as the only input type of a method to define a zero-argument method, or as the only return type to define a void-returning method</span></span>

<span data-ttu-id="8f950-405">Evitare altri usi del tipo di unità.</span><span class="sxs-lookup"><span data-stu-id="8f950-405">Avoid other uses of the unit type.</span></span> <span data-ttu-id="8f950-406">Questi sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="8f950-406">These are good:</span></span>

```fsharp
✔ member this.NoArguments() = 3

✔ member this.ReturnVoid(x: int) = ()
```

<span data-ttu-id="8f950-407">Questa operazione non è valida:</span><span class="sxs-lookup"><span data-stu-id="8f950-407">This is bad:</span></span>

```fsharp
member this.WrongUnit( x: unit, z: int) = ((), ())
```

#### <a name="check-for-null-values-on-vanilla-net-api-boundaries"></a><span data-ttu-id="8f950-408">Verificare la presenza di valori null nei limiti dell'API Vanilla .NET</span><span class="sxs-lookup"><span data-stu-id="8f950-408">Check for null values on vanilla .NET API boundaries</span></span>

<span data-ttu-id="8f950-409">Il codice di implementazione F # tende a avere un minor numero di valori null, a causa di modelli di progettazione non modificabili e di restrizioni sull'uso di valori letterali null per i tipi F #.</span><span class="sxs-lookup"><span data-stu-id="8f950-409">F# implementation code tends to have fewer null values, due to immutable design patterns and restrictions on use of null literals for F# types.</span></span> <span data-ttu-id="8f950-410">Altri linguaggi .NET spesso utilizzano null come valore molto più spesso.</span><span class="sxs-lookup"><span data-stu-id="8f950-410">Other .NET languages often use null as a value much more frequently.</span></span> <span data-ttu-id="8f950-411">Per questo motivo, il codice F # che sta esponendo un'API .NET Vanilla deve controllare i parametri per i valori null al limite dell'API e impedire che tali valori vengano propagati in modo più approfondito nel codice di implementazione F #.</span><span class="sxs-lookup"><span data-stu-id="8f950-411">Because of this, F# code that is exposing a vanilla .NET API should check parameters for null at the API boundary, and prevent these values from flowing deeper into the F# implementation code.</span></span> <span data-ttu-id="8f950-412">`isNull`È possibile usare la funzione o i criteri di ricerca per il `null` modello.</span><span class="sxs-lookup"><span data-stu-id="8f950-412">The `isNull` function or pattern matching on the `null` pattern can be used.</span></span>

```fsharp
let checkNonNull argName (arg: obj) =
    match arg with
    | null -> nullArg argName
    | _ -> ()

let checkNonNull` argName (arg: obj) =
    if isNull arg then nullArg argName
    else ()
```

#### <a name="avoid-using-tuples-as-return-values"></a><span data-ttu-id="8f950-413">Evitare di usare le tuple come valori restituiti</span><span class="sxs-lookup"><span data-stu-id="8f950-413">Avoid using tuples as return values</span></span>

<span data-ttu-id="8f950-414">È invece preferibile restituire un tipo denominato che contiene i dati di aggregazione oppure utilizzare parametri out per restituire più valori.</span><span class="sxs-lookup"><span data-stu-id="8f950-414">Instead, prefer returning a named type holding the aggregate data, or using out parameters to return multiple values.</span></span> <span data-ttu-id="8f950-415">Sebbene le tuple e le tuple di struct esistano in .NET (incluso il supporto del linguaggio C# per le tuple struct), spesso non forniscono l'API ideale e prevista per gli sviluppatori .NET.</span><span class="sxs-lookup"><span data-stu-id="8f950-415">Although tuples and struct tuples exist in .NET (including C# language support for struct tuples), they will most often not provide the ideal and expected API for .NET developers.</span></span>

#### <a name="avoid-the-use-of-currying-of-parameters"></a><span data-ttu-id="8f950-416">Evitare l'utilizzo del currying dei parametri</span><span class="sxs-lookup"><span data-stu-id="8f950-416">Avoid the use of currying of parameters</span></span>

<span data-ttu-id="8f950-417">Usare invece le convenzioni di chiamata .NET `Method(arg1,arg2,…,argN)` .</span><span class="sxs-lookup"><span data-stu-id="8f950-417">Instead, use .NET calling conventions `Method(arg1,arg2,…,argN)`.</span></span>

```fsharp
member this.TupledArguments(str, num) = String.replicate num str
```

<span data-ttu-id="8f950-418">Suggerimento: se si progettano le librerie per l'uso da qualsiasi linguaggio .NET, non esiste alcun sostituto per la programmazione di C# e Visual Basic sperimentale per garantire che le librerie "siano corrette" da questi linguaggi.</span><span class="sxs-lookup"><span data-stu-id="8f950-418">Tip: If you're designing libraries for use from any .NET language, then there's no substitute for actually doing some experimental C# and Visual Basic programming to ensure that your libraries "feel right" from these languages.</span></span> <span data-ttu-id="8f950-419">È anche possibile usare strumenti come .NET Reflector e Visual Studio Visualizzatore oggetti per garantire che le librerie e la relativa documentazione vengano visualizzate come previsto per gli sviluppatori.</span><span class="sxs-lookup"><span data-stu-id="8f950-419">You can also use tools such as .NET Reflector and the Visual Studio Object Browser to ensure that libraries and their documentation appear as expected to developers.</span></span>

## <a name="appendix"></a><span data-ttu-id="8f950-420">Appendice</span><span class="sxs-lookup"><span data-stu-id="8f950-420">Appendix</span></span>

### <a name="end-to-end-example-of-designing-f-code-for-use-by-other-net-languages"></a><span data-ttu-id="8f950-421">Esempio end-to-end di progettazione del codice F # per l'uso da parte di altri linguaggi .NET</span><span class="sxs-lookup"><span data-stu-id="8f950-421">End-to-end example of designing F# code for use by other .NET languages</span></span>

<span data-ttu-id="8f950-422">Si consideri la classe seguente:</span><span class="sxs-lookup"><span data-stu-id="8f950-422">Consider the following class:</span></span>

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

<span data-ttu-id="8f950-423">Il tipo F # derivato di questa classe è il seguente:</span><span class="sxs-lookup"><span data-stu-id="8f950-423">The inferred F# type of this class is as follows:</span></span>

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

<span data-ttu-id="8f950-424">Esaminiamo il modo in cui questo tipo F # viene visualizzato in un programmatore usando un altro linguaggio .NET.</span><span class="sxs-lookup"><span data-stu-id="8f950-424">Let's take a look at how this F# type appears to a programmer using another .NET language.</span></span> <span data-ttu-id="8f950-425">Ad esempio, la "firma" di C# approssimata è la seguente:</span><span class="sxs-lookup"><span data-stu-id="8f950-425">For example, the approximate C# "signature" is as follows:</span></span>

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

<span data-ttu-id="8f950-426">Ci sono alcuni aspetti importanti da notare sul modo in cui F # rappresenta i costrutti qui.</span><span class="sxs-lookup"><span data-stu-id="8f950-426">There are some important points to notice about how F# represents constructs here.</span></span> <span data-ttu-id="8f950-427">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="8f950-427">For example:</span></span>

* <span data-ttu-id="8f950-428">I metadati, ad esempio i nomi degli argomenti, sono stati conservati.</span><span class="sxs-lookup"><span data-stu-id="8f950-428">Metadata such as argument names has been preserved.</span></span>

* <span data-ttu-id="8f950-429">I metodi F # che accettano due argomenti diventano metodi C# che accettano due argomenti.</span><span class="sxs-lookup"><span data-stu-id="8f950-429">F# methods that take two arguments become C# methods that take two arguments.</span></span>

* <span data-ttu-id="8f950-430">Funzioni ed elenchi diventano riferimenti ai tipi corrispondenti nella libreria F #.</span><span class="sxs-lookup"><span data-stu-id="8f950-430">Functions and lists become references to corresponding types in the F# library.</span></span>

<span data-ttu-id="8f950-431">Il codice seguente illustra come modificare il codice per tenere conto di questi elementi.</span><span class="sxs-lookup"><span data-stu-id="8f950-431">The following code shows how to adjust this code to take these things into account.</span></span>

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

<span data-ttu-id="8f950-432">Il tipo F # derivato del codice è il seguente:</span><span class="sxs-lookup"><span data-stu-id="8f950-432">The inferred F# type of the code is as follows:</span></span>

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

<span data-ttu-id="8f950-433">La firma C# è ora la seguente:</span><span class="sxs-lookup"><span data-stu-id="8f950-433">The C# signature is now as follows:</span></span>

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

<span data-ttu-id="8f950-434">Le correzioni apportate per preparare questo tipo per l'uso come parte di una libreria Vanilla .NET sono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="8f950-434">The fixes made to prepare this type for use as part of a vanilla .NET library are as follows:</span></span>

* <span data-ttu-id="8f950-435">Sono stati modificati diversi nomi: `Point1` , `n` , `l` e `f` sono diventati `RadialPoint` rispettivamente, `count` , `factor` e `transform` .</span><span class="sxs-lookup"><span data-stu-id="8f950-435">Adjusted several names: `Point1`, `n`, `l`, and `f` became `RadialPoint`, `count`, `factor`, and `transform`, respectively.</span></span>

* <span data-ttu-id="8f950-436">È stato usato un tipo restituito di `seq<RadialPoint>` anziché `RadialPoint list` modificando una costruzione di un elenco usando `[ ... ]` la costruzione di una sequenza usando `IEnumerable<RadialPoint>` .</span><span class="sxs-lookup"><span data-stu-id="8f950-436">Used a return type of `seq<RadialPoint>` instead of `RadialPoint list` by changing a list construction using `[ ... ]` to a sequence construction using `IEnumerable<RadialPoint>`.</span></span>

* <span data-ttu-id="8f950-437">Utilizzato il tipo delegato .NET `System.Func` anziché un tipo di funzione F #.</span><span class="sxs-lookup"><span data-stu-id="8f950-437">Used the .NET delegate type `System.Func` instead of an F# function type.</span></span>

<span data-ttu-id="8f950-438">Questo rende molto più gradevole l'utilizzo nel codice C#.</span><span class="sxs-lookup"><span data-stu-id="8f950-438">This makes it far nicer to consume in C# code.</span></span>

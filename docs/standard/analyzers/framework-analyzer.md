---
title: Analizzatori di .NET Framework-.NET
description: Informazioni su come usare gli analizzatori di .NET Framework nel pacchetto .NET Framework analizzatori per individuare e risolvere i rischi per la sicurezza
author: billwagner
ms.author: wiwagn
ms.date: 01/25/2018
ms.technology: dotnet-standard
ms.openlocfilehash: dd69671e709549fe0ad0f582e4d09b43f7321df2
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2020
ms.locfileid: "78155997"
---
# <a name="the-net-framework-analyzer"></a><span data-ttu-id="5bb0d-103">.NET Framework Analyzer</span><span class="sxs-lookup"><span data-stu-id="5bb0d-103">The .NET Framework Analyzer</span></span>

<span data-ttu-id="5bb0d-104">È possibile usare .NET Framework Analyzer per individuare potenziali problemi nel codice dell'applicazione basata su .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="5bb0d-104">You can use the .NET Framework Analyzer to find potential issues in your .NET Framework-based application code.</span></span> <span data-ttu-id="5bb0d-105">L'analizzatore rileva i possibili problemi e suggerisce le relative soluzioni.</span><span class="sxs-lookup"><span data-stu-id="5bb0d-105">This analyzer finds potential issues and suggests fixes to them.</span></span>

<span data-ttu-id="5bb0d-106">Viene eseguito in modo interattivo in Visual Studio durante la scrittura del codice o come parte di una compilazione CI.</span><span class="sxs-lookup"><span data-stu-id="5bb0d-106">The analyzer runs interactively in Visual Studio as you write your code or as part of a CI build.</span></span> <span data-ttu-id="5bb0d-107">L'analizzatore deve essere aggiunto al progetto nell'ambiente di sviluppo non appena possibile.</span><span class="sxs-lookup"><span data-stu-id="5bb0d-107">You should add the analyzer to your project as early as possible in your development.</span></span> <span data-ttu-id="5bb0d-108">Prima si individuano i potenziali problemi nel codice, più facile sarà correggerli.</span><span class="sxs-lookup"><span data-stu-id="5bb0d-108">The sooner you find any potential issues in your code, the easier they are to fix.</span></span> <span data-ttu-id="5bb0d-109">Tuttavia, è possibile aggiungere l'analizzatore in qualsiasi momento nel ciclo di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="5bb0d-109">However, you can add it at any time in the development cycle.</span></span> <span data-ttu-id="5bb0d-110">Individua eventuali problemi nel codice già esistente e segnala i nuovi problemi nel corso dello sviluppo.</span><span class="sxs-lookup"><span data-stu-id="5bb0d-110">It finds any issues with the existing code and warns about new issues as you keep developing.</span></span>

## <a name="installing-and-configuring-the-net-framework-analyzer"></a><span data-ttu-id="5bb0d-111">Installazione e configurazione di .NET Framework Analyzer</span><span class="sxs-lookup"><span data-stu-id="5bb0d-111">Installing and configuring the .NET Framework Analyzer</span></span>

<span data-ttu-id="5bb0d-112">Gli analizzatori di .NET Framework devono essere installati come pacchetto NuGet in ogni progetto in cui si desidera eseguirli.</span><span class="sxs-lookup"><span data-stu-id="5bb0d-112">The .NET Framework Analyzers must be installed as a NuGet package on every project where you want them to run.</span></span> <span data-ttu-id="5bb0d-113">Solo uno sviluppatore deve aggiungerli al progetto.</span><span class="sxs-lookup"><span data-stu-id="5bb0d-113">Only one developer needs to add them to the project.</span></span> <span data-ttu-id="5bb0d-114">Il pacchetto di analizzatori è una dipendenza del progetto e verrà eseguito nel computer di ogni sviluppatore non appena è disponibile la soluzione aggiornata.</span><span class="sxs-lookup"><span data-stu-id="5bb0d-114">The analyzer package is a project dependency and will run on every developer's machine once it has the updated solution.</span></span>

<span data-ttu-id="5bb0d-115">.NET Framework Analyzer è disponibile nel pacchetto NuGet [Microsoft.NetFramework.Analyzers](https://www.nuget.org/packages/Microsoft.NetFramework.Analyzers/).</span><span class="sxs-lookup"><span data-stu-id="5bb0d-115">The .NET Framework Analyzer is delivered in the [Microsoft.NetFramework.Analyzers](https://www.nuget.org/packages/Microsoft.NetFramework.Analyzers/) NuGet package.</span></span> <span data-ttu-id="5bb0d-116">Questo pacchetto contiene solo gli analizzatori specifici di .NET Framework, inclusi gli analizzatori della sicurezza.</span><span class="sxs-lookup"><span data-stu-id="5bb0d-116">This package provides only the analyzers specific to the .NET Framework, which includes security analyzers.</span></span> <span data-ttu-id="5bb0d-117">Nella maggior parte dei casi è opportuno usare il pacchetto NuGet [Microsoft.CodeAnalysis.FxCopAnalyzers](https://www.nuget.org/packages/Microsoft.CodeAnalysis.FxCopAnalyzers).</span><span class="sxs-lookup"><span data-stu-id="5bb0d-117">In most cases, you'll want the [Microsoft.CodeAnalysis.FxCopAnalyzers](https://www.nuget.org/packages/Microsoft.CodeAnalysis.FxCopAnalyzers) NuGet package.</span></span>
<span data-ttu-id="5bb0d-118">Il pacchetto aggregato FxCopAnalyzers contiene tutti gli analizzatori di framework inclusi nel pacchetto Framework.Analyzers, nonché i seguenti analizzatori:</span><span class="sxs-lookup"><span data-stu-id="5bb0d-118">The FxCopAnalyzers aggregate package contains all the framework analyzers included in the Framework.Analyzers package as well as the following analyzers:</span></span>

- <span data-ttu-id="5bb0d-119">[Microsoft.CodeQuality.Analyzers](https://www.nuget.org/packages/Microsoft.CodeQuality.Analyzers): contiene indicazioni generali e linee guida per le API di .NET Standard</span><span class="sxs-lookup"><span data-stu-id="5bb0d-119">[Microsoft.CodeQuality.Analyzers](https://www.nuget.org/packages/Microsoft.CodeQuality.Analyzers): Provides general guidance and guidance for .NET Standard APIs</span></span>
- <span data-ttu-id="5bb0d-120">[Microsoft.NetCore.Analyzers](https://www.nuget.org/packages/Microsoft.NetCore.Analyzers): contiene gli analizzatori specifici delle API di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="5bb0d-120">[Microsoft.NetCore.Analyzers](https://www.nuget.org/packages/Microsoft.NetCore.Analyzers): Provides analyzers specific to .NET Core APIs.</span></span>
- <span data-ttu-id="5bb0d-121">[Text.Analyzers](https://www.nuget.org/packages/Text.Analyzers): contiene materiale sussidiario per il testo incluso come codice, compresi i commenti.</span><span class="sxs-lookup"><span data-stu-id="5bb0d-121">[Text.Analyzers](https://www.nuget.org/packages/Text.Analyzers): Provides guidance for text included as code, including comments.</span></span>

<span data-ttu-id="5bb0d-122">Per installarlo, fare clic con il pulsante destro del mouse sul progetto e selezionare "Gestisci dipendenze".</span><span class="sxs-lookup"><span data-stu-id="5bb0d-122">To install it, right-click on the project, and select "Manage Dependencies".</span></span>
<span data-ttu-id="5bb0d-123">In NuGet Package Explorer individuare "NetFramework Analyzer" o, se si preferisce, "Fx Cop Analyzer".</span><span class="sxs-lookup"><span data-stu-id="5bb0d-123">From the NuGet explorer, search for "NetFramework Analyzer", or if you prefer, "Fx Cop Analyzer".</span></span> <span data-ttu-id="5bb0d-124">Installare la versione stabile più recente in tutti i progetti della soluzione.</span><span class="sxs-lookup"><span data-stu-id="5bb0d-124">Install the latest stable version in all projects in your solution.</span></span>

## <a name="using-the-net-framework-analyzer"></a><span data-ttu-id="5bb0d-125">Uso di .NET Framework Analyzer</span><span class="sxs-lookup"><span data-stu-id="5bb0d-125">Using the .NET Framework Analyzer</span></span>

<span data-ttu-id="5bb0d-126">Dopo aver installato il pacchetto NuGet, compilare la soluzione.</span><span class="sxs-lookup"><span data-stu-id="5bb0d-126">Once the NuGet package is installed, build your solution.</span></span> <span data-ttu-id="5bb0d-127">L'analizzatore segnalerà eventuali problemi individuati nella base di codici.</span><span class="sxs-lookup"><span data-stu-id="5bb0d-127">The analyzer will report any issues it locates in your codebase.</span></span> <span data-ttu-id="5bb0d-128">I problemi vengono segnalati come avvisi nella finestra Elenco errori di Visual Studio, come illustrato nella figura seguente:</span><span class="sxs-lookup"><span data-stu-id="5bb0d-128">The issues are reported as warnings in the Visual Studio Error List window, as shown in the following image:</span></span>

![Problemi segnalati dall'analizzatore del framework](./media/framework-analyzers-2.png)

<span data-ttu-id="5bb0d-130">Mentre si scrive il codice, possono apparire linee a zigzag sotto i potenziali problemi nel codice.</span><span class="sxs-lookup"><span data-stu-id="5bb0d-130">As you write code, you see squiggles underneath any potential issue in your code.</span></span>
<span data-ttu-id="5bb0d-131">Passare il mouse su un problema per visualizzarne i dettagli e i suggerimenti utili per risolverlo, come illustrato nella figura seguente:</span><span class="sxs-lookup"><span data-stu-id="5bb0d-131">Hover over any issue and you see details about the issue, and suggestions for any possible fix, as shown in the following image:</span></span>

![report interattivo di problemi rilevati da framework analyzer](./media/framework-analyzers-1.png)

<span data-ttu-id="5bb0d-133">Gli analizzatori esaminano il codice nella soluzione e visualizzano un elenco di avvisi per i problemi riportati di seguito:</span><span class="sxs-lookup"><span data-stu-id="5bb0d-133">The analyzers examine the code in your solution and provide you with a list of warnings for any of these issues:</span></span>

### <a name="ca1058-types-should-not-extend-certain-base-types"></a><span data-ttu-id="5bb0d-134">CA1058: I tipi non devono estendere tipi di base specifici</span><span class="sxs-lookup"><span data-stu-id="5bb0d-134">CA1058: Types should not extend certain base types</span></span>

<span data-ttu-id="5bb0d-135">Esiste un numero limitato di tipi in .NET Framework da cui non è consigliabile derivare direttamente.</span><span class="sxs-lookup"><span data-stu-id="5bb0d-135">There are a small number of types in the .NET Framework that you should not derived from directly.</span></span>

<span data-ttu-id="5bb0d-136">**Categoria:** Progettazione</span><span class="sxs-lookup"><span data-stu-id="5bb0d-136">**Category:** Design</span></span>

<span data-ttu-id="5bb0d-137">**Gravità:** Avviso</span><span class="sxs-lookup"><span data-stu-id="5bb0d-137">**Severity:** Warning</span></span>

<span data-ttu-id="5bb0d-138">Informazioni aggiuntive: [CA1058: I tipi non devono estendere tipi di base specifici](/visualstudio/code-quality/ca1058-types-should-not-extend-certain-base-types)</span><span class="sxs-lookup"><span data-stu-id="5bb0d-138">Additional information: [CA:1058: Types should not extend certain base types](/visualstudio/code-quality/ca1058-types-should-not-extend-certain-base-types)</span></span>

### <a name="ca2153-do-not-catch-corrupted-state-exceptions"></a><span data-ttu-id="5bb0d-139">CA2153: Evitare la gestione delle eccezioni stato danneggiato</span><span class="sxs-lookup"><span data-stu-id="5bb0d-139">CA2153: Do not catch corrupted state exceptions</span></span>

<span data-ttu-id="5bb0d-140">Usare le eccezioni stato danneggiato potrebbe mascherare gli errori, ad esempio le violazioni dell'accesso, e causare uno stato incoerente dell'esecuzione o rendere più semplice per gli utenti malintenzionati compromettere un sistema.</span><span class="sxs-lookup"><span data-stu-id="5bb0d-140">Catching corrupted state exceptions could mask errors (such as access violations), resulting in an inconsistent state of execution or making it easier for attackers to compromise a system.</span></span> <span data-ttu-id="5bb0d-141">In alternativa, gestire un set più specifico di tipi di eccezioni o generare di nuovo l'eccezione</span><span class="sxs-lookup"><span data-stu-id="5bb0d-141">Instead, catch and handle a more specific set of exception type(s) or re-throw the exception</span></span>

<span data-ttu-id="5bb0d-142">**Categoria:** Sicurezza</span><span class="sxs-lookup"><span data-stu-id="5bb0d-142">**Category:** Security</span></span>

<span data-ttu-id="5bb0d-143">**Gravità:** Avviso</span><span class="sxs-lookup"><span data-stu-id="5bb0d-143">**Severity:** Warning</span></span>

<span data-ttu-id="5bb0d-144">Informazioni aggiuntive: [CA2153: Evitare la gestione delle eccezioni stato danneggiato](/visualstudio/code-quality/ca2153-avoid-handling-corrupted-state-exceptions)</span><span class="sxs-lookup"><span data-stu-id="5bb0d-144">Additional information: [## CA2153: Do not catch corrupted state exceptions](/visualstudio/code-quality/ca2153-avoid-handling-corrupted-state-exceptions)</span></span>

### <a name="ca2229-implement-serialization-constructors"></a><span data-ttu-id="5bb0d-145">CA2229: Implementare costruttori di serializzazione</span><span class="sxs-lookup"><span data-stu-id="5bb0d-145">CA2229: Implement serialization constructors</span></span>

<span data-ttu-id="5bb0d-146">L'analizzatore genera questo avviso quando si crea un tipo che implementa l'interfaccia <xref:System.Runtime.Serialization.ISerializable> ma non definisce il costruttore di serializzazione necessario.</span><span class="sxs-lookup"><span data-stu-id="5bb0d-146">The analyzer generates this warning when you create a type that implements the <xref:System.Runtime.Serialization.ISerializable> interface but does not define the required serialization constructor.</span></span> <span data-ttu-id="5bb0d-147">Per correggere una violazione di questa regola, implementare il costruttore di serializzazione.</span><span class="sxs-lookup"><span data-stu-id="5bb0d-147">To fix a violation of this rule, implement the serialization constructor.</span></span> <span data-ttu-id="5bb0d-148">Per una classe sealed, rendere il costruttore privato; in caso contrario renderlo protetto.</span><span class="sxs-lookup"><span data-stu-id="5bb0d-148">For a sealed class, make the constructor private; otherwise, make it protected.</span></span> <span data-ttu-id="5bb0d-149">Il costruttore di serializzazione ha la firma seguente:</span><span class="sxs-lookup"><span data-stu-id="5bb0d-149">The serialization constructor has the following signature:</span></span>

```csharp
public class MyItemType
{
    // The special constructor is used to deserialize values.
    public MyItemType(SerializationInfo info, StreamingContext context)
    {
        // implementation removed.
    }
}
```

<span data-ttu-id="5bb0d-150">**Categoria:** Uso</span><span class="sxs-lookup"><span data-stu-id="5bb0d-150">**Category:** Usage</span></span>

<span data-ttu-id="5bb0d-151">**Gravità:** Avviso</span><span class="sxs-lookup"><span data-stu-id="5bb0d-151">**Severity:** Warning</span></span>

<span data-ttu-id="5bb0d-152">Informazioni aggiuntive: [CA2229: Implementare costruttori di serializzazione](/visualstudio/code-quality/ca2229-implement-serialization-constructors)</span><span class="sxs-lookup"><span data-stu-id="5bb0d-152">Additional information: [CA2229: Implement serialization constructors](/visualstudio/code-quality/ca2229-implement-serialization-constructors)</span></span>

### <a name="ca2235-mark-all-non-serializable-fields"></a><span data-ttu-id="5bb0d-153">CA2235: Contrassegnare tutti i campi non serializzabili</span><span class="sxs-lookup"><span data-stu-id="5bb0d-153">CA2235: Mark all non-serializable fields</span></span>

<span data-ttu-id="5bb0d-154">Un campo di istanza di un tipo non serializzabile viene dichiarato in un tipo serializzabile.</span><span class="sxs-lookup"><span data-stu-id="5bb0d-154">An instance field of a type that is not serializable is declared in a type that is serializable.</span></span> <span data-ttu-id="5bb0d-155">È necessario contrassegnare in modo esplicito tale campo con <xref:System.NonSerializedAttribute> per risolvere il problema.</span><span class="sxs-lookup"><span data-stu-id="5bb0d-155">You must explicitly mark that field with the <xref:System.NonSerializedAttribute> to fix this warning.</span></span>

<span data-ttu-id="5bb0d-156">**Categoria:** Uso</span><span class="sxs-lookup"><span data-stu-id="5bb0d-156">**Category:** Usage</span></span>

<span data-ttu-id="5bb0d-157">**Gravità:** Avviso</span><span class="sxs-lookup"><span data-stu-id="5bb0d-157">**Severity:** Warning</span></span>

<span data-ttu-id="5bb0d-158">Informazioni aggiuntive: [CA2235: Contrassegnare tutti i campi non serializzabili](/visualstudio/code-quality/ca2235-mark-all-non-serializable-fields)</span><span class="sxs-lookup"><span data-stu-id="5bb0d-158">Additional information: [CA2235: Mark all non-serializable fields](/visualstudio/code-quality/ca2235-mark-all-non-serializable-fields)</span></span>

### <a name="ca2237-mark-iserializable-types-with-serializable"></a><span data-ttu-id="5bb0d-159">CA2237: Contrassegnare i tipi ISerializable con SerializableAttribute</span><span class="sxs-lookup"><span data-stu-id="5bb0d-159">CA2237: Mark ISerializable types with serializable</span></span>

<span data-ttu-id="5bb0d-160">Per essere riconosciuti come serializzabili in Common Language Runtime, i tipi devono essere contrassegnati usando l'attributo <xref:System.SerializableAttribute> anche quando il tipo usa una routine di serializzazione personalizzata implementando l'interfaccia <xref:System.Runtime.Serialization.ISerializable>.</span><span class="sxs-lookup"><span data-stu-id="5bb0d-160">To be recognized by the common language runtime as serializable, types must be marked by using the <xref:System.SerializableAttribute> attribute even when the type uses a custom serialization routine by implementing the <xref:System.Runtime.Serialization.ISerializable> interface.</span></span>

<span data-ttu-id="5bb0d-161">**Categoria:** Uso</span><span class="sxs-lookup"><span data-stu-id="5bb0d-161">**Category:** Usage</span></span>

<span data-ttu-id="5bb0d-162">**Gravità:** Avviso</span><span class="sxs-lookup"><span data-stu-id="5bb0d-162">**Severity:** Warning</span></span>

<span data-ttu-id="5bb0d-163">Informazioni aggiuntive: [CA2237: Contrassegnare i tipi ISerializable con SerializableAttribute](/visualstudio/code-quality/ca2237-mark-iserializable-types-with-serializableattribute)</span><span class="sxs-lookup"><span data-stu-id="5bb0d-163">Additional information: [CA2237: Mark ISerializable types with serializable](/visualstudio/code-quality/ca2237-mark-iserializable-types-with-serializableattribute)</span></span>

### <a name="ca3075-insecure-dtd-processing-in-xml"></a><span data-ttu-id="5bb0d-164">CA3075: Elaborazione DTD non protetta in XML</span><span class="sxs-lookup"><span data-stu-id="5bb0d-164">CA3075: Insecure DTD processing in XML</span></span>

<span data-ttu-id="5bb0d-165">Se si usano istanze di <xref:System.Xml.XmlReaderSettings.DtdProcessing%2A> non protette o si fa riferimento a origini di entità esterne, il parser può accettare un input non attendibile e divulgare informazioni riservate a utenti malintenzionati.</span><span class="sxs-lookup"><span data-stu-id="5bb0d-165">If you use insecure <xref:System.Xml.XmlReaderSettings.DtdProcessing%2A> instances or reference external entity sources, the parser may accept untrusted input and disclose sensitive information to attackers.</span></span>  

<span data-ttu-id="5bb0d-166">**Categoria:** Sicurezza</span><span class="sxs-lookup"><span data-stu-id="5bb0d-166">**Category:** Security</span></span>

<span data-ttu-id="5bb0d-167">**Gravità:** Avviso</span><span class="sxs-lookup"><span data-stu-id="5bb0d-167">**Severity:** Warning</span></span>

<span data-ttu-id="5bb0d-168">Informazioni aggiuntive: [A3075: Elaborazione DTD non protetta in XML](/visualstudio/code-quality/ca2237-mark-iserializable-types-with-serializableattribute)</span><span class="sxs-lookup"><span data-stu-id="5bb0d-168">Additional information: [A3075: Insecure DTD processing in XML](/visualstudio/code-quality/ca2237-mark-iserializable-types-with-serializableattribute)</span></span>

### <a name="ca5350-do-not-use-weak-cryptographic-algorithms"></a><span data-ttu-id="5bb0d-169">CA5350: non usare algoritmi di crittografia vulnerabili</span><span class="sxs-lookup"><span data-stu-id="5bb0d-169">CA5350: Do not use weak cryptographic algorithms</span></span>

<span data-ttu-id="5bb0d-170">Gli algoritmi di crittografia si danneggiano nel tempo man mano che gli attacchi diventano più evoluti.</span><span class="sxs-lookup"><span data-stu-id="5bb0d-170">Cryptographic algorithms degrade over time as attacks become more advanced.</span></span> <span data-ttu-id="5bb0d-171">In base al tipo e all'applicazione di questo algoritmo di crittografia, un'ulteriore riduzione dell'efficacia della crittografia può consentire agli utenti malintenzionati di leggere e manomettere i messaggi cifrati, falsificare le firme digitali, alterare il contenuto con hash o danneggiare in altro modo qualsiasi sistema crittografico basato su questo algoritmo.</span><span class="sxs-lookup"><span data-stu-id="5bb0d-171">Depending on the type and application of this cryptographic algorithm, further degradation of its cryptographic strength may allow attackers to read enciphered messages, tamper with enciphered messages, forge digital signatures, tamper with hashed content, or otherwise compromise any cryptosystem based on this algorithm.</span></span> <span data-ttu-id="5bb0d-172">Per la crittografia, usare un algoritmo AES (AES-256, AES 192 e AES-128 sono accettabili) con una lunghezza di chiave maggiore di o uguale a 128 bit.</span><span class="sxs-lookup"><span data-stu-id="5bb0d-172">For encryption, use an AES algorithm (AES-256, AES-192 and AES-128 are acceptable) with a key length greater than or equal to 128 bits.</span></span> <span data-ttu-id="5bb0d-173">Per l'hash, usare una funzione hash della famiglia SHA-2, ad esempio SHA-2 512, SHA-2 384 o SHA-2 256.</span><span class="sxs-lookup"><span data-stu-id="5bb0d-173">For hashing, use a hashing function in the SHA-2 family, such as SHA-2 512, SHA-2 384, or SHA-2 256.</span></span>

<span data-ttu-id="5bb0d-174">**Categoria:** Sicurezza</span><span class="sxs-lookup"><span data-stu-id="5bb0d-174">**Category:** Security</span></span>

<span data-ttu-id="5bb0d-175">**Gravità:** Avviso</span><span class="sxs-lookup"><span data-stu-id="5bb0d-175">**Severity:** Warning</span></span>

<span data-ttu-id="5bb0d-176">Informazioni aggiuntive: [CA5350: non usare algoritmi di crittografia vulnerabili](/visualstudio/code-quality/ca5350-do-not-use-weak-cryptographic-algorithms)</span><span class="sxs-lookup"><span data-stu-id="5bb0d-176">Additional information: [CA5350: Do not use weak cryptographic algorithms](/visualstudio/code-quality/ca5350-do-not-use-weak-cryptographic-algorithms)</span></span>

### <a name="ca5351-do-not-use-broken-cryptographic-algorithms"></a><span data-ttu-id="5bb0d-177">CA5351: non usare algoritmi di crittografia interrotti</span><span class="sxs-lookup"><span data-stu-id="5bb0d-177">CA5351: Do not use broken cryptographic algorithms</span></span>

<span data-ttu-id="5bb0d-178">Esiste un attacco che rende fattibile a livello di calcolo l'interruzione di questo algoritmo.</span><span class="sxs-lookup"><span data-stu-id="5bb0d-178">An attack making it computationally feasible to break this algorithm exists.</span></span> <span data-ttu-id="5bb0d-179">Ciò consente agli utenti malintenzionati di interrompere le garanzie di crittografia che per cui è stato progettato l'algoritmo.</span><span class="sxs-lookup"><span data-stu-id="5bb0d-179">This allows attackers to break the cryptographic guarantees it is designed to provide.</span></span> <span data-ttu-id="5bb0d-180">In base al tipo e all'applicazione di questo algoritmo di crittografia, in questo modo gli utenti malintenzionati possono leggere e manomettere i messaggi cifrati, falsificare le firme digitali, alterare il contenuto con hash o danneggiare in altro modo qualsiasi sistema crittografico basato su questo algoritmo.</span><span class="sxs-lookup"><span data-stu-id="5bb0d-180">Depending on the type and application of this cryptographic algorithm, this may allow attackers to read enciphered messages, tamper with enciphered messages, forge digital signatures, tamper with hashed content, or otherwise compromise any cryptosystem based on this algorithm.</span></span> <span data-ttu-id="5bb0d-181">Per la crittografia, usare un algoritmo AES (AES-256, AES 192 e AES-128 sono accettabili) con una lunghezza di chiave maggiore di o uguale a 128 bit.</span><span class="sxs-lookup"><span data-stu-id="5bb0d-181">For encryption, use an AES algorithm (AES-256, AES-192 and AES-128 are acceptable) with a key length greater than or equal to 128 bits.</span></span> <span data-ttu-id="5bb0d-182">Per l'hash, usare una funzione hash della famiglia SHA-2, ad esempio SHA512, SHA384 o SHA256.</span><span class="sxs-lookup"><span data-stu-id="5bb0d-182">For hashing, use a hashing function in the SHA-2 family, such as SHA512, SHA384, or SHA256.</span></span> <span data-ttu-id="5bb0d-183">Per le firme digitali, usare RSA con una lunghezza di chiave maggiore di o uguale a 2048 bit o ECDSA con una lunghezza di chiave maggiore di o uguale a 256 bit.</span><span class="sxs-lookup"><span data-stu-id="5bb0d-183">For digital signatures, use RSA with a key length greater than or equal to 2048-bits, or ECDSA with a key length greater than or equal to 256 bits.</span></span>

<span data-ttu-id="5bb0d-184">**Categoria:** Sicurezza</span><span class="sxs-lookup"><span data-stu-id="5bb0d-184">**Category:** Security</span></span>

<span data-ttu-id="5bb0d-185">**Gravità:** Avviso</span><span class="sxs-lookup"><span data-stu-id="5bb0d-185">**Severity:** Warning</span></span>

<span data-ttu-id="5bb0d-186">Informazioni aggiuntive: [CA5351: non usare algoritmi di crittografia interrotti](/visualstudio/code-quality/ca5351)</span><span class="sxs-lookup"><span data-stu-id="5bb0d-186">Additional Information: [CA5351: Do not use broken cryptographic algorithms](/visualstudio/code-quality/ca5351)</span></span>

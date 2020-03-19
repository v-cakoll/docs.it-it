---
title: 'Esercitazione: Creare un provider di tipiTutorial: Create a Type Provider'
description: Informazioni su come creare provider di tipi F , in F , 3.0 esaminando diversi provider di tipi semplici per illustrare i concetti di base.
ms.date: 11/04/2019
ms.openlocfilehash: 3b8145d4c2d8bf96b6dcf66de02e9f2d83927d74
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186115"
---
# <a name="tutorial-create-a-type-provider"></a><span data-ttu-id="8ec42-103">Esercitazione: Creare un provider di tipiTutorial: Create a Type Provider</span><span class="sxs-lookup"><span data-stu-id="8ec42-103">Tutorial: Create a Type Provider</span></span>

<span data-ttu-id="8ec42-104">Il meccanismo del provider di tipi in F è una parte significativa del supporto per la programmazione ricca di informazioni.</span><span class="sxs-lookup"><span data-stu-id="8ec42-104">The type provider mechanism in F# is a significant part of its support for information rich programming.</span></span> <span data-ttu-id="8ec42-105">In questa esercitazione viene illustrato come creare provider di tipi personalizzati illustrando lo sviluppo di diversi provider di tipi semplici per illustrare i concetti di base.</span><span class="sxs-lookup"><span data-stu-id="8ec42-105">This tutorial explains how to create your own type providers by walking you through the development of several simple type providers to illustrate the basic concepts.</span></span> <span data-ttu-id="8ec42-106">Per ulteriori informazioni sul meccanismo del provider di tipi in F , vedere [Provider](index.md)di tipi .</span><span class="sxs-lookup"><span data-stu-id="8ec42-106">For more information about the type provider mechanism in F#, see [Type Providers](index.md).</span></span>

<span data-ttu-id="8ec42-107">L'ecosistema F , contiene una gamma di provider di tipi per Internet di uso comune e servizi dati aziendali.</span><span class="sxs-lookup"><span data-stu-id="8ec42-107">The F# ecosystem contains a range of type providers for commonly used Internet and enterprise data services.</span></span> <span data-ttu-id="8ec42-108">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="8ec42-108">For example:</span></span>

- <span data-ttu-id="8ec42-109">[FSharp.Data](https://fsharp.github.io/FSharp.Data/) include provider di tipi per i formati di documento JSON, XML, CSV e HTML.</span><span class="sxs-lookup"><span data-stu-id="8ec42-109">[FSharp.Data](https://fsharp.github.io/FSharp.Data/) includes type providers for JSON, XML, CSV and HTML document formats.</span></span>

- <span data-ttu-id="8ec42-110">[SQLProvider](https://fsprojects.github.io/SQLProvider/) fornisce l'accesso fortemente tipizzato ai database SQL tramite un mapping di oggetti e query LINQ F , su queste origini dati.</span><span class="sxs-lookup"><span data-stu-id="8ec42-110">[SQLProvider](https://fsprojects.github.io/SQLProvider/) provides strongly-typed access to SQL databases through a object mapping and F# LINQ queries against these data sources.</span></span>

- <span data-ttu-id="8ec42-111">[FSharp.Data.SqlClient](https://fsprojects.github.io/FSharp.Data.SqlClient/) dispone di un set di provider di tipi per l'incorporamento controllato in fase di compilazione di T-SQL in F.</span><span class="sxs-lookup"><span data-stu-id="8ec42-111">[FSharp.Data.SqlClient](https://fsprojects.github.io/FSharp.Data.SqlClient/) has a set of type providers for compile-time checked embedding of T-SQL in F#.</span></span>

- <span data-ttu-id="8ec42-112">[FSharp.Data.TypeProviders](https://fsprojects.github.io/FSharp.Data.TypeProviders/) è un set precedente di provider di tipi da utilizzare solo con la programmazione .NET Framework per l'accesso ai servizi dati SQL, Entity Framework, OData e WSDL.</span><span class="sxs-lookup"><span data-stu-id="8ec42-112">[FSharp.Data.TypeProviders](https://fsprojects.github.io/FSharp.Data.TypeProviders/) is an older set of type providers for use only with .NET Framework programming for accessing SQL, Entity Framework, OData and WSDL data services.</span></span>

<span data-ttu-id="8ec42-113">Se necessario, è possibile creare provider di tipi personalizzati oppure fare riferimento a provider di tipi creati da altri utenti.</span><span class="sxs-lookup"><span data-stu-id="8ec42-113">Where necessary, you can create custom type providers, or you can reference type providers that others have created.</span></span> <span data-ttu-id="8ec42-114">Ad esempio, l'organizzazione potrebbe disporre di un servizio dati che fornisce un numero elevato e crescente di set di dati denominati, ognuno con il proprio schema di dati stabile.</span><span class="sxs-lookup"><span data-stu-id="8ec42-114">For example, your organization could have a data service that provides a large and growing number of named data sets, each with its own stable data schema.</span></span> <span data-ttu-id="8ec42-115">È possibile creare un provider di tipi che legge gli schemi e presenta i set di dati correnti al programmatore in modo fortemente tipizzato.</span><span class="sxs-lookup"><span data-stu-id="8ec42-115">You can create a type provider that reads the schemas and presents the current data sets to the programmer in a strongly typed way.</span></span>

## <a name="before-you-start"></a><span data-ttu-id="8ec42-116">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="8ec42-116">Before You Start</span></span>

<span data-ttu-id="8ec42-117">Il meccanismo del provider di tipi è progettato principalmente per l'inserimento di spazi di informazioni sui dati e sui servizi stabili nell'esperienza di programmazione di F.</span><span class="sxs-lookup"><span data-stu-id="8ec42-117">The type provider mechanism is primarily designed for injecting stable data and service information spaces into the F# programming experience.</span></span>

<span data-ttu-id="8ec42-118">Questo meccanismo non è progettato per l'inserimento di spazi informazioni il cui schema cambia durante l'esecuzione del programma in modi rilevanti per la logica del programma.</span><span class="sxs-lookup"><span data-stu-id="8ec42-118">This mechanism isn’t designed for injecting information spaces whose schema changes during program execution in ways that are relevant to program logic.</span></span> <span data-ttu-id="8ec42-119">Inoltre, il meccanismo non è progettato per la metaprogrammazione all'intra-linguaggio, anche se tale dominio contiene alcuni usi validi.</span><span class="sxs-lookup"><span data-stu-id="8ec42-119">Also, the mechanism isn't designed for intra-language meta-programming, even though that domain contains some valid uses.</span></span> <span data-ttu-id="8ec42-120">È consigliabile utilizzare questo meccanismo solo se necessario e in cui lo sviluppo di un provider di tipi produce un valore molto elevato.</span><span class="sxs-lookup"><span data-stu-id="8ec42-120">You should use this mechanism only where necessary and where the development of a type provider yields very high value.</span></span>

<span data-ttu-id="8ec42-121">È consigliabile evitare di scrivere un provider di tipi in cui uno schema non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="8ec42-121">You should avoid writing a type provider where a schema isn't available.</span></span> <span data-ttu-id="8ec42-122">Analogamente, è consigliabile evitare di scrivere un provider di tipi in cui sarebbe sufficiente una libreria .NET ordinaria (o anche una esistente).</span><span class="sxs-lookup"><span data-stu-id="8ec42-122">Likewise, you should avoid writing a type provider where an ordinary (or even an existing) .NET library would suffice.</span></span>

<span data-ttu-id="8ec42-123">Prima di iniziare, è possibile porre le seguenti domande:</span><span class="sxs-lookup"><span data-stu-id="8ec42-123">Before you start, you might ask the following questions:</span></span>

- <span data-ttu-id="8ec42-124">Si dispone di uno schema per l'origine delle informazioni?</span><span class="sxs-lookup"><span data-stu-id="8ec42-124">Do you have a schema for your information source?</span></span> <span data-ttu-id="8ec42-125">In caso affermativo, qual è il mapping nel sistema di tipi F e .NET?</span><span class="sxs-lookup"><span data-stu-id="8ec42-125">If so, what’s the mapping into the F# and .NET type system?</span></span>

- <span data-ttu-id="8ec42-126">È possibile usare un'API esistente (tipizzata in modo dinamico) come punto di partenza per l'implementazione?</span><span class="sxs-lookup"><span data-stu-id="8ec42-126">Can you use an existing (dynamically typed) API as a starting point for your implementation?</span></span>

- <span data-ttu-id="8ec42-127">L'utente e l'organizzazione avranno un utilizzo sufficiente del provider di tipi per rendere utile la scrittura?</span><span class="sxs-lookup"><span data-stu-id="8ec42-127">Will you and your organization have enough uses of the type provider to make writing it worthwhile?</span></span> <span data-ttu-id="8ec42-128">Una normale libreria .NET soddisfa le proprie esigenze?</span><span class="sxs-lookup"><span data-stu-id="8ec42-128">Would a normal .NET library meet your needs?</span></span>

- <span data-ttu-id="8ec42-129">Quanto verrà modificato lo schema?</span><span class="sxs-lookup"><span data-stu-id="8ec42-129">How much will your schema change?</span></span>

- <span data-ttu-id="8ec42-130">Cambierà durante la codifica?</span><span class="sxs-lookup"><span data-stu-id="8ec42-130">Will it change during coding?</span></span>

- <span data-ttu-id="8ec42-131">Cambierà tra le sessioni di codifica?</span><span class="sxs-lookup"><span data-stu-id="8ec42-131">Will it change between coding sessions?</span></span>

- <span data-ttu-id="8ec42-132">Cambierà durante l'esecuzione del programma?</span><span class="sxs-lookup"><span data-stu-id="8ec42-132">Will it change during program execution?</span></span>

<span data-ttu-id="8ec42-133">I provider di tipi sono più adatti alle situazioni in cui lo schema è stabile in fase di esecuzione e durante la durata del codice compilato.</span><span class="sxs-lookup"><span data-stu-id="8ec42-133">Type providers are best suited to situations where the schema is stable at runtime and during the lifetime of compiled code.</span></span>

## <a name="a-simple-type-provider"></a><span data-ttu-id="8ec42-134">Un provider di tipi sempliceA Simple Type Provider</span><span class="sxs-lookup"><span data-stu-id="8ec42-134">A Simple Type Provider</span></span>

<span data-ttu-id="8ec42-135">L'esempio è Samples.HelloWorldTypeProvider, simile `examples` agli esempi nella directory dell'SDK del [provider di tipi F .](https://github.com/fsprojects/FSharp.TypeProviders.SDK/)</span><span class="sxs-lookup"><span data-stu-id="8ec42-135">This sample is Samples.HelloWorldTypeProvider, similar to the samples in the `examples` directory of the [F# Type Provider SDK](https://github.com/fsprojects/FSharp.TypeProviders.SDK/).</span></span> <span data-ttu-id="8ec42-136">Il provider rende disponibile uno "spazio dei tipi" che contiene 100 tipi cancellati, come illustrato nel `Type1`codice seguente utilizzando la sintassi della firma F e omettendo i dettagli per tutti tranne .</span><span class="sxs-lookup"><span data-stu-id="8ec42-136">The provider makes available a "type space" that contains 100 erased types, as the following code shows by using F# signature syntax and omitting the details for all except `Type1`.</span></span> <span data-ttu-id="8ec42-137">Per ulteriori informazioni sui tipi cancellati, vedere [Dettagli sui tipi forniti cancellati](#details-about-erased-provided-types) più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="8ec42-137">For more information about erased types, see [Details About Erased Provided Types](#details-about-erased-provided-types) later in this topic.</span></span>

```fsharp
namespace Samples.HelloWorldTypeProvider

type Type1 =
    /// This is a static property.
    static member StaticProperty : string

    /// This constructor takes no arguments.
    new : unit -> Type1

    /// This constructor takes one argument.
    new : data:string -> Type1

    /// This is an instance property.
    member InstanceProperty : int

    /// This is an instance method.
    member InstanceMethod : x:int -> char

    nested type NestedType =
        /// This is StaticProperty1 on NestedType.
        static member StaticProperty1 : string
        …
        /// This is StaticProperty100 on NestedType.
        static member StaticProperty100 : string

type Type2 =
…
…

type Type100 =
…
```

<span data-ttu-id="8ec42-138">Si noti che il set di tipi e membri forniti è noto in modo statico.</span><span class="sxs-lookup"><span data-stu-id="8ec42-138">Note that the set of types and members provided is statically known.</span></span> <span data-ttu-id="8ec42-139">In questo esempio non viene sfruttata la capacità dei provider di fornire tipi che dipendono da uno schema.</span><span class="sxs-lookup"><span data-stu-id="8ec42-139">This example doesn't leverage the ability of providers to provide types that depend on a schema.</span></span> <span data-ttu-id="8ec42-140">L'implementazione del provider di tipi è descritta nel codice seguente e i dettagli sono illustrati nelle sezioni successive di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="8ec42-140">The implementation of the type provider is outlined in the following code, and the details are covered in later sections of this topic.</span></span>

> [!WARNING]
> <span data-ttu-id="8ec42-141">Potrebbero esserci differenze tra questo codice e gli esempi online.</span><span class="sxs-lookup"><span data-stu-id="8ec42-141">There may be differences between this code and the online samples.</span></span>

```fsharp
namespace Samples.FSharp.HelloWorldTypeProvider

open System
open System.Reflection
open ProviderImplementation.ProvidedTypes
open FSharp.Core.CompilerServices
open FSharp.Quotations

// This type defines the type provider. When compiled to a DLL, it can be added
// as a reference to an F# command-line compilation, script, or project.
[<TypeProvider>]
type SampleTypeProvider(config: TypeProviderConfig) as this =

  // Inheriting from this type provides implementations of ITypeProvider
  // in terms of the provided types below.
  inherit TypeProviderForNamespaces(config)

  let namespaceName = "Samples.HelloWorldTypeProvider"
  let thisAssembly = Assembly.GetExecutingAssembly()

  // Make one provided type, called TypeN.
  let makeOneProvidedType (n:int) =
  …
  // Now generate 100 types
  let types = [ for i in 1 .. 100 -> makeOneProvidedType i ]

  // And add them to the namespace
  do this.AddNamespace(namespaceName, types)

[<assembly:TypeProviderAssembly>]
do()
```

<span data-ttu-id="8ec42-142">Per utilizzare questo provider, aprire un'istanza separata di Visual Studio, creare uno script F , quindi aggiungere un riferimento al provider dallo script utilizzando #r come illustrato nel codice seguente:To use this provider, open a separate instance of Visual Studio, create an F' script, and then add a reference to the provider from your script by using #r as the following code shows:</span><span class="sxs-lookup"><span data-stu-id="8ec42-142">To use this provider, open a separate instance of Visual Studio, create an F# script, and then add a reference to the provider from your script by using #r as the following code shows:</span></span>

```fsharp
#r @".\bin\Debug\Samples.HelloWorldTypeProvider.dll"

let obj1 = Samples.HelloWorldTypeProvider.Type1("some data")

let obj2 = Samples.HelloWorldTypeProvider.Type1("some other data")

obj1.InstanceProperty
obj2.InstanceProperty

[ for index in 0 .. obj1.InstanceProperty-1 -> obj1.InstanceMethod(index) ]
[ for index in 0 .. obj2.InstanceProperty-1 -> obj2.InstanceMethod(index) ]

let data1 = Samples.HelloWorldTypeProvider.Type1.NestedType.StaticProperty35
```

<span data-ttu-id="8ec42-143">Cercare quindi i tipi `Samples.HelloWorldTypeProvider` nello spazio dei nomi generato dal provider di tipi.</span><span class="sxs-lookup"><span data-stu-id="8ec42-143">Then look for the types under the `Samples.HelloWorldTypeProvider` namespace that the type provider generated.</span></span>

<span data-ttu-id="8ec42-144">Prima di ricompilare il provider, assicurarsi di aver chiuso tutte le istanze di Visual Studio e F Interactive che utilizzano la DLL del provider.</span><span class="sxs-lookup"><span data-stu-id="8ec42-144">Before you recompile the provider, make sure that you have closed all instances of Visual Studio and F# Interactive that are using the provider DLL.</span></span> <span data-ttu-id="8ec42-145">In caso contrario, si verificherà un errore di compilazione perché la DLL di output verrà bloccata.</span><span class="sxs-lookup"><span data-stu-id="8ec42-145">Otherwise, a build error will occur because the output DLL will be locked.</span></span>

<span data-ttu-id="8ec42-146">Per eseguire il debug di questo provider utilizzando le istruzioni print, creare uno script che espone un problema con il provider e quindi utilizzare il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="8ec42-146">To debug this provider by using print statements, make a script that exposes a problem with the provider, and then use the following code:</span></span>

```console
fsc.exe -r:bin\Debug\HelloWorldTypeProvider.dll script.fsx
```

<span data-ttu-id="8ec42-147">Per eseguire il debug di questo provider utilizzando Visual Studio, aprire il prompt dei comandi per sviluppatori per Visual Studio con credenziali amministrative ed eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="8ec42-147">To debug this provider by using Visual Studio, open the Developer Command Prompt for Visual Studio with administrative credentials, and run the following command:</span></span>

```console
devenv.exe /debugexe fsc.exe -r:bin\Debug\HelloWorldTypeProvider.dll script.fsx
```

<span data-ttu-id="8ec42-148">In alternativa, aprire Visual Studio, aprire `Debug/Attach to process…`il menu Debug, scegliere e connettersi a un altro `devenv` processo in cui si sta modificando lo script.</span><span class="sxs-lookup"><span data-stu-id="8ec42-148">As an alternative, open Visual Studio, open the Debug menu, choose `Debug/Attach to process…`, and attach to another `devenv` process where you’re editing your script.</span></span> <span data-ttu-id="8ec42-149">Utilizzando questo metodo, è possibile indirizzare più facilmente la logica specifica nel provider di tipi digitando in modo interattivo le espressioni nella seconda istanza (con IntelliSense completo e altre funzionalità).</span><span class="sxs-lookup"><span data-stu-id="8ec42-149">By using this method, you can more easily target particular logic in the type provider by interactively typing expressions into the second instance (with full IntelliSense and other features).</span></span>

<span data-ttu-id="8ec42-150">È possibile disabilitare il debug Just My Code per identificare meglio gli errori nel codice generato.</span><span class="sxs-lookup"><span data-stu-id="8ec42-150">You can disable Just My Code debugging to better identify errors in generated code.</span></span> <span data-ttu-id="8ec42-151">Per informazioni su come abilitare o disabilitare questa funzionalità, vedere [Spostamento all'interno](/visualstudio/debugger/navigating-through-code-with-the-debugger)del codice con il debugger .</span><span class="sxs-lookup"><span data-stu-id="8ec42-151">For information about how to enable or disable this feature, see [Navigating through Code with the Debugger](/visualstudio/debugger/navigating-through-code-with-the-debugger).</span></span> <span data-ttu-id="8ec42-152">Inoltre, è anche possibile impostare la `Debug` intercettazione delle `Exceptions` eccezioni first-chance aprendo il `Exceptions` menu e scegliendo o scegliendo i tasti Ctrl , Alt e E per aprire la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="8ec42-152">Also, you can also set first-chance exception catching by opening the `Debug` menu and then choosing `Exceptions` or by choosing the Ctrl+Alt+E keys to open the `Exceptions` dialog box.</span></span> <span data-ttu-id="8ec42-153">Nella finestra di `Common Language Runtime Exceptions`dialogo, `Thrown` in , selezionare la casella di controllo.</span><span class="sxs-lookup"><span data-stu-id="8ec42-153">In that dialog box, under `Common Language Runtime Exceptions`, select the `Thrown` check box.</span></span>

### <a name="implementation-of-the-type-provider"></a><span data-ttu-id="8ec42-154">Implementazione del provider di tipi</span><span class="sxs-lookup"><span data-stu-id="8ec42-154">Implementation of the Type Provider</span></span>

<span data-ttu-id="8ec42-155">In questa sezione vengono illustrate le sezioni principali dell'implementazione del provider di tipi.</span><span class="sxs-lookup"><span data-stu-id="8ec42-155">This section walks you through the principal sections of the type provider implementation.</span></span> <span data-ttu-id="8ec42-156">In primo luogo, si definisce il tipo per il provider di tipi personalizzato stesso:</span><span class="sxs-lookup"><span data-stu-id="8ec42-156">First, you define the type for the custom type provider itself:</span></span>

```fsharp
[<TypeProvider>]
type SampleTypeProvider(config: TypeProviderConfig) as this =
```

<span data-ttu-id="8ec42-157">Questo tipo deve essere pubblico ed è necessario contrassegnarlo con il [TypeProvider](https://msdn.microsoft.com/library/bdf7b036-7490-4ace-b79f-c5f1b1b37947) attributo in modo che il compilatore riconoscerà il provider di tipi quando un progetto F , separato fa riferimento all'assembly che contiene il tipo.</span><span class="sxs-lookup"><span data-stu-id="8ec42-157">This type must be public, and you must mark it with the [TypeProvider](https://msdn.microsoft.com/library/bdf7b036-7490-4ace-b79f-c5f1b1b37947) attribute so that the compiler will recognize the type provider when a separate F# project references the assembly that contains the type.</span></span> <span data-ttu-id="8ec42-158">Il *config* config parametro è facoltativo e, se presente, contiene informazioni di configurazione contestuali per l'istanza del provider di tipi che crea il compilatore F.</span><span class="sxs-lookup"><span data-stu-id="8ec42-158">The *config* parameter is optional, and, if present, contains contextual configuration information for the type provider instance that the F# compiler creates.</span></span>

<span data-ttu-id="8ec42-159">Successivamente, implementare il [ITypeProvider](https://msdn.microsoft.com/library/2c2b0571-843d-4a7d-95d4-0a7510ed5e2f) interfaccia.</span><span class="sxs-lookup"><span data-stu-id="8ec42-159">Next, you implement the [ITypeProvider](https://msdn.microsoft.com/library/2c2b0571-843d-4a7d-95d4-0a7510ed5e2f) interface.</span></span> <span data-ttu-id="8ec42-160">In questo caso, `TypeProviderForNamespaces` si utilizza `ProvidedTypes` il tipo dall'API come tipo di base.</span><span class="sxs-lookup"><span data-stu-id="8ec42-160">In this case, you use the `TypeProviderForNamespaces` type from the `ProvidedTypes` API as a base type.</span></span> <span data-ttu-id="8ec42-161">Questo tipo di helper può fornire una raccolta finita di spazi dei nomi forniti con entusiasmo, ognuno dei quali contiene direttamente un numero finito di tipi fissi e forniti con entusiasmo.</span><span class="sxs-lookup"><span data-stu-id="8ec42-161">This helper type can provide a finite collection of eagerly provided namespaces, each of which directly contains a finite number of fixed, eagerly provided types.</span></span> <span data-ttu-id="8ec42-162">In questo contesto, il provider genera i tipi *anche* se non sono necessari o utilizzati.</span><span class="sxs-lookup"><span data-stu-id="8ec42-162">In this context, the provider *eagerly* generates types even if they aren't needed or used.</span></span>

```fsharp
inherit TypeProviderForNamespaces(config)
```

<span data-ttu-id="8ec42-163">Definire quindi i valori privati locali che specificano lo spazio dei nomi per i tipi forniti e trovare l'assembly del provider di tipi stesso.</span><span class="sxs-lookup"><span data-stu-id="8ec42-163">Next, define local private values that specify the namespace for the provided types, and find the type provider assembly itself.</span></span> <span data-ttu-id="8ec42-164">Questo assembly viene utilizzato in un secondo momento come tipo padre logico dei tipi cancellati forniti.</span><span class="sxs-lookup"><span data-stu-id="8ec42-164">This assembly is used later as the logical parent type of the erased types that are provided.</span></span>

```fsharp
let namespaceName = "Samples.HelloWorldTypeProvider"
let thisAssembly = Assembly.GetExecutingAssembly()
```

<span data-ttu-id="8ec42-165">Successivamente, creare una funzione per fornire ognuno dei tipi Type1... Tipo100.</span><span class="sxs-lookup"><span data-stu-id="8ec42-165">Next, create a function to provide each of the types Type1…Type100.</span></span> <span data-ttu-id="8ec42-166">Questa funzione viene illustrata in modo più dettagliato più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="8ec42-166">This function is explained in more detail later in this topic.</span></span>

```fsharp
let makeOneProvidedType (n:int) = …
```

<span data-ttu-id="8ec42-167">Successivamente, generare i 100 tipi forniti:Next, generate the 100 provided types:</span><span class="sxs-lookup"><span data-stu-id="8ec42-167">Next, generate the 100 provided types:</span></span>

```fsharp
let types = [ for i in 1 .. 100 -> makeOneProvidedType i ]
```

<span data-ttu-id="8ec42-168">Successivamente, aggiungere i tipi come spazio dei nomi fornito:Next, add the types as a provided namespace:</span><span class="sxs-lookup"><span data-stu-id="8ec42-168">Next, add the types as a provided namespace:</span></span>

```fsharp
do this.AddNamespace(namespaceName, types)
```

<span data-ttu-id="8ec42-169">Infine, aggiungere un attributo di assembly che indica che si sta creando una DLL del provider di tipi:Finally, add an assembly attribute that indicates that you are creating a type provider DLL:</span><span class="sxs-lookup"><span data-stu-id="8ec42-169">Finally, add an assembly attribute that indicates that you are creating a type provider DLL:</span></span>

```fsharp
[<assembly:TypeProviderAssembly>]
do()
```

### <a name="providing-one-type-and-its-members"></a><span data-ttu-id="8ec42-170">Fornire un tipo e i relativi membri</span><span class="sxs-lookup"><span data-stu-id="8ec42-170">Providing One Type And Its Members</span></span>

<span data-ttu-id="8ec42-171">La `makeOneProvidedType` funzione fa il vero lavoro di fornire uno dei tipi.</span><span class="sxs-lookup"><span data-stu-id="8ec42-171">The `makeOneProvidedType` function does the real work of providing one of the types.</span></span>

```fsharp
let makeOneProvidedType (n:int) =
…
```

<span data-ttu-id="8ec42-172">In questo passaggio viene illustrata l'implementazione di questa funzione.</span><span class="sxs-lookup"><span data-stu-id="8ec42-172">This step explains the implementation of this function.</span></span> <span data-ttu-id="8ec42-173">In primo luogo, creare il tipo fornito (ad esempio, Tipo1, quando n è 1 o Tipo57, quando n è 57).</span><span class="sxs-lookup"><span data-stu-id="8ec42-173">First, create the provided type (for example, Type1, when n = 1, or Type57, when n = 57).</span></span>

```fsharp
// This is the provided type. It is an erased provided type and, in compiled code,
// will appear as type 'obj'.
let t = ProvidedTypeDefinition(thisAssembly, namespaceName,
                               "Type" + string n,
                               baseType = Some typeof<obj>)
```

<span data-ttu-id="8ec42-174">È necessario notare i seguenti punti:</span><span class="sxs-lookup"><span data-stu-id="8ec42-174">You should note the following points:</span></span>

- <span data-ttu-id="8ec42-175">Questo tipo fornito viene cancellato.</span><span class="sxs-lookup"><span data-stu-id="8ec42-175">This provided type is erased.</span></span>  <span data-ttu-id="8ec42-176">Poiché si indica che `obj`il tipo di base è , le istanze verranno visualizzate come valori di tipo [obj](https://msdn.microsoft.com/library/dcf2430f-702b-40e5-a0a1-97518bf137f7) nel codice compilato.</span><span class="sxs-lookup"><span data-stu-id="8ec42-176">Because you indicate that the base type is `obj`, instances will appear as values of type [obj](https://msdn.microsoft.com/library/dcf2430f-702b-40e5-a0a1-97518bf137f7) in compiled code.</span></span>

- <span data-ttu-id="8ec42-177">Quando si specifica un tipo non annidato, è necessario specificare l'assembly e lo spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="8ec42-177">When you specify a non-nested type, you must specify the assembly and namespace.</span></span> <span data-ttu-id="8ec42-178">Per i tipi cancellati, l'assembly deve essere l'assembly del provider di tipi stesso.</span><span class="sxs-lookup"><span data-stu-id="8ec42-178">For erased types, the assembly should be the type provider assembly itself.</span></span>

<span data-ttu-id="8ec42-179">Aggiungere quindi la documentazione XML al tipo.</span><span class="sxs-lookup"><span data-stu-id="8ec42-179">Next, add XML documentation to the type.</span></span> <span data-ttu-id="8ec42-180">Questa documentazione viene ritardata, ovvero calcolata su richiesta se il compilatore host ne ha bisogno.</span><span class="sxs-lookup"><span data-stu-id="8ec42-180">This documentation is delayed, that is, computed on-demand if the host compiler needs it.</span></span>

```fsharp
t.AddXmlDocDelayed (fun () -> sprintf "This provided type %s" ("Type" + string n))
```

<span data-ttu-id="8ec42-181">Successivamente si aggiunge una proprietà statica fornita al tipo:Next you add a provided static property to the type:</span><span class="sxs-lookup"><span data-stu-id="8ec42-181">Next you add a provided static property to the type:</span></span>

```fsharp
let staticProp = ProvidedProperty(propertyName = "StaticProperty",
                                  propertyType = typeof<string>,
                                  isStatic = true,
                                  getterCode = (fun args -> <@@ "Hello!" @@>))
```

<span data-ttu-id="8ec42-182">Ottenere questa proprietà restituirà sempre la stringa "Hello!".</span><span class="sxs-lookup"><span data-stu-id="8ec42-182">Getting this property will always evaluate to the string "Hello!".</span></span> <span data-ttu-id="8ec42-183">Il `GetterCode` per la proprietà utilizza una citazione di F , che rappresenta il codice generato dal compilatore host per ottenere la proprietà.</span><span class="sxs-lookup"><span data-stu-id="8ec42-183">The `GetterCode` for the property uses an F# quotation, which represents the code that the host compiler generates for getting the property.</span></span> <span data-ttu-id="8ec42-184">Per ulteriori informazioni sulle offerte, vedere Citazioni di codice [(F )](https://msdn.microsoft.com/library/6f055397-a1f0-4f9a-927c-f0d7c6951155).</span><span class="sxs-lookup"><span data-stu-id="8ec42-184">For more information about quotations, see [Code Quotations (F#)](https://msdn.microsoft.com/library/6f055397-a1f0-4f9a-927c-f0d7c6951155).</span></span>

<span data-ttu-id="8ec42-185">Aggiungere la documentazione XML alla proprietà.</span><span class="sxs-lookup"><span data-stu-id="8ec42-185">Add XML documentation to the property.</span></span>

```fsharp
staticProp.AddXmlDocDelayed(fun () -> "This is a static property")
```

<span data-ttu-id="8ec42-186">Associare ora la proprietà fornita al tipo fornito.</span><span class="sxs-lookup"><span data-stu-id="8ec42-186">Now attach the provided property to the provided type.</span></span> <span data-ttu-id="8ec42-187">È necessario associare un membro fornito a un solo tipo.</span><span class="sxs-lookup"><span data-stu-id="8ec42-187">You must attach a provided member to one and only one type.</span></span> <span data-ttu-id="8ec42-188">In caso contrario, il membro non sarà mai accessibile.</span><span class="sxs-lookup"><span data-stu-id="8ec42-188">Otherwise, the member will never be accessible.</span></span>

```fsharp
t.AddMember staticProp
```

<span data-ttu-id="8ec42-189">Creare ora un costruttore fornito che non accetta parametri.</span><span class="sxs-lookup"><span data-stu-id="8ec42-189">Now create a provided constructor that takes no parameters.</span></span>

```fsharp
let ctor = ProvidedConstructor(parameters = [ ],
                               invokeCode = (fun args -> <@@ "The object data" :> obj @@>))
```

<span data-ttu-id="8ec42-190">Il `InvokeCode` per il costruttore restituisce un'offerta di F , che rappresenta il codice generato dal compilatore host quando viene chiamato il costruttore.</span><span class="sxs-lookup"><span data-stu-id="8ec42-190">The `InvokeCode` for the constructor returns an F# quotation, which represents the code that the host compiler generates when the constructor is called.</span></span> <span data-ttu-id="8ec42-191">Ad esempio, è possibile utilizzare il seguente costruttore:</span><span class="sxs-lookup"><span data-stu-id="8ec42-191">For example, you can use the following constructor:</span></span>

```fsharp
new Type10()
```

<span data-ttu-id="8ec42-192">Verrà creata un'istanza del tipo fornito con i dati sottostanti "I dati dell'oggetto".</span><span class="sxs-lookup"><span data-stu-id="8ec42-192">An instance of the provided type will be created with underlying data "The object data".</span></span> <span data-ttu-id="8ec42-193">Il codice citato include una conversione in [obj](https://msdn.microsoft.com/library/dcf2430f-702b-40e5-a0a1-97518bf137f7) perché tale tipo è la cancellazione di questo tipo fornito (come specificato al momento della creazione del tipo fornito).</span><span class="sxs-lookup"><span data-stu-id="8ec42-193">The quoted code includes a conversion to [obj](https://msdn.microsoft.com/library/dcf2430f-702b-40e5-a0a1-97518bf137f7) because that type is the erasure of this provided type (as you specified when you declared the provided type).</span></span>

<span data-ttu-id="8ec42-194">Aggiungere la documentazione XML al costruttore e aggiungere il costruttore fornito al tipo fornito:Add XML documentation to the constructor, and add the provided constructor to the provided type:</span><span class="sxs-lookup"><span data-stu-id="8ec42-194">Add XML documentation to the constructor, and add the provided constructor to the provided type:</span></span>

```fsharp
ctor.AddXmlDocDelayed(fun () -> "This is a constructor")

t.AddMember ctor
```

<span data-ttu-id="8ec42-195">Creare un secondo costruttore fornito che accetta un parametro:Create a second provided constructor that takes one parameter:</span><span class="sxs-lookup"><span data-stu-id="8ec42-195">Create a second provided constructor that takes one parameter:</span></span>

```fsharp
let ctor2 =
ProvidedConstructor(parameters = [ ProvidedParameter("data",typeof<string>) ],
                    invokeCode = (fun args -> <@@ (%%(args.[0]) : string) :> obj @@>))
```

<span data-ttu-id="8ec42-196">Il `InvokeCode` per il costruttore restituisce nuovamente un'offerta di F , che rappresenta il codice generato dal compilatore host per una chiamata al metodo.</span><span class="sxs-lookup"><span data-stu-id="8ec42-196">The `InvokeCode` for the constructor again returns an F# quotation, which represents the code that the host compiler generated for a call to the method.</span></span> <span data-ttu-id="8ec42-197">Ad esempio, è possibile utilizzare il seguente costruttore:</span><span class="sxs-lookup"><span data-stu-id="8ec42-197">For example, you can use the following constructor:</span></span>

```fsharp
new Type10("ten")
```

<span data-ttu-id="8ec42-198">Un'istanza del tipo fornito viene creata con i dati sottostanti "dieci".</span><span class="sxs-lookup"><span data-stu-id="8ec42-198">An instance of the provided type is created with underlying data "ten".</span></span> <span data-ttu-id="8ec42-199">Potresti aver già `InvokeCode` notato che la funzione restituisce un'offerta.</span><span class="sxs-lookup"><span data-stu-id="8ec42-199">You may have already noticed that the `InvokeCode` function returns a quotation.</span></span> <span data-ttu-id="8ec42-200">L'input di questa funzione è un elenco di espressioni, una per ogni parametro del costruttore.</span><span class="sxs-lookup"><span data-stu-id="8ec42-200">The input to this function is a list of expressions, one per constructor parameter.</span></span> <span data-ttu-id="8ec42-201">In questo caso, un'espressione che rappresenta `args.[0]`il valore del singolo parametro è disponibile in .</span><span class="sxs-lookup"><span data-stu-id="8ec42-201">In this case, an expression that represents the single parameter value is available in `args.[0]`.</span></span> <span data-ttu-id="8ec42-202">Il codice per una chiamata al costruttore forza il valore `obj`restituito al tipo cancellato.</span><span class="sxs-lookup"><span data-stu-id="8ec42-202">The code for a call to the constructor coerces the return value to the erased type `obj`.</span></span> <span data-ttu-id="8ec42-203">Dopo aver aggiunto il secondo costruttore fornito al tipo, creare una proprietà di istanza fornita:After you add the second provided constructor to the type, you create a provided instance property:</span><span class="sxs-lookup"><span data-stu-id="8ec42-203">After you add the second provided constructor to the type, you create a provided instance property:</span></span>

```fsharp
let instanceProp =
    ProvidedProperty(propertyName = "InstanceProperty",
                     propertyType = typeof<int>,
                     getterCode= (fun args ->
                        <@@ ((%%(args.[0]) : obj) :?> string).Length @@>))
instanceProp.AddXmlDocDelayed(fun () -> "This is an instance property")
t.AddMember instanceProp
```

<span data-ttu-id="8ec42-204">Ottenere questa proprietà restituirà la lunghezza della stringa, ovvero l'oggetto rappresentazione.</span><span class="sxs-lookup"><span data-stu-id="8ec42-204">Getting this property will return the length of the string, which is the representation object.</span></span> <span data-ttu-id="8ec42-205">La `GetterCode` proprietà restituisce un'offerta di F, che specifica il codice generato dal compilatore host per ottenere la proprietà.</span><span class="sxs-lookup"><span data-stu-id="8ec42-205">The `GetterCode` property returns an F# quotation that specifies the code that the host compiler generates to get the property.</span></span> <span data-ttu-id="8ec42-206">Come `InvokeCode`, `GetterCode` la funzione restituisce un'offerta.</span><span class="sxs-lookup"><span data-stu-id="8ec42-206">Like `InvokeCode`, the `GetterCode` function returns a quotation.</span></span> <span data-ttu-id="8ec42-207">Il compilatore host chiama questa funzione con un elenco di argomenti.</span><span class="sxs-lookup"><span data-stu-id="8ec42-207">The host compiler calls this function with a list of arguments.</span></span> <span data-ttu-id="8ec42-208">In questo caso, gli argomenti includono solo la singola espressione che rappresenta l'istanza su `args.[0]`cui viene chiamato il metodo di chiamata, a cui è possibile accedere utilizzando .</span><span class="sxs-lookup"><span data-stu-id="8ec42-208">In this case, the arguments include just the single expression that represents the instance upon which the getter is being called, which you can access by using `args.[0]`.</span></span> <span data-ttu-id="8ec42-209">L'implementazione di quindi giunzioni nell'offerta di `obj`risultato in corrispondenza del tipo cancellato e un cast viene utilizzato per soddisfare il meccanismo del compilatore per il controllo dei `GetterCode` tipi che l'oggetto è una stringa.</span><span class="sxs-lookup"><span data-stu-id="8ec42-209">The implementation of `GetterCode` then splices into the result quotation at the erased type `obj`, and a cast is used to satisfy the compiler's mechanism for checking types that the object is a string.</span></span> <span data-ttu-id="8ec42-210">La parte `makeOneProvidedType` successiva di fornisce un metodo di istanza con un parametro.</span><span class="sxs-lookup"><span data-stu-id="8ec42-210">The next part of `makeOneProvidedType` provides an instance method with one parameter.</span></span>

```fsharp
let instanceMeth =
    ProvidedMethod(methodName = "InstanceMethod",
                   parameters = [ProvidedParameter("x",typeof<int>)],
                   returnType = typeof<char>,
                   invokeCode = (fun args ->
                       <@@ ((%%(args.[0]) : obj) :?> string).Chars(%%(args.[1]) : int) @@>))

instanceMeth.AddXmlDocDelayed(fun () -> "This is an instance method")
// Add the instance method to the type.
t.AddMember instanceMeth
```

<span data-ttu-id="8ec42-211">Infine, creare un tipo annidato che contiene 100 proprietà annidate.</span><span class="sxs-lookup"><span data-stu-id="8ec42-211">Finally, create a nested type that contains 100 nested properties.</span></span> <span data-ttu-id="8ec42-212">La creazione di questo tipo annidato e delle relative proprietà viene ritardata, ovvero calcolata su richiesta.</span><span class="sxs-lookup"><span data-stu-id="8ec42-212">The creation of this nested type and its properties is delayed, that is, computed on-demand.</span></span>

```fsharp
t.AddMembersDelayed(fun () ->
  let nestedType = ProvidedTypeDefinition("NestedType", Some typeof<obj>)

  nestedType.AddMembersDelayed (fun () ->
    let staticPropsInNestedType =
      [
          for i in 1 .. 100 ->
              let valueOfTheProperty = "I am string "  + string i

              let p =
                ProvidedProperty(propertyName = "StaticProperty" + string i,
                  propertyType = typeof<string>,
                  isStatic = true,
                  getterCode= (fun args -> <@@ valueOfTheProperty @@>))

              p.AddXmlDocDelayed(fun () ->
                  sprintf "This is StaticProperty%d on NestedType" i)

              p
      ]

    staticPropsInNestedType)

  [nestedType])
```

### <a name="details-about-erased-provided-types"></a><span data-ttu-id="8ec42-213">Dettagli sui tipi forniti cancellati</span><span class="sxs-lookup"><span data-stu-id="8ec42-213">Details about Erased Provided Types</span></span>

<span data-ttu-id="8ec42-214">Nell'esempio riportato in questa sezione vengono forniti solo *i tipi forniti cancellati,* particolarmente utili nelle situazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="8ec42-214">The example in this section provides only *erased provided types*, which are particularly useful in the following situations:</span></span>

- <span data-ttu-id="8ec42-215">Quando si scrive un provider per uno spazio informazioni che contiene solo dati e metodi.</span><span class="sxs-lookup"><span data-stu-id="8ec42-215">When you are writing a provider for an information space that contains only data and methods.</span></span>

- <span data-ttu-id="8ec42-216">Quando si scrive un provider in cui una semantica accurata del tipo di runtime non è fondamentale per l'uso pratico dello spazio informazioni.</span><span class="sxs-lookup"><span data-stu-id="8ec42-216">When you are writing a provider where accurate runtime-type semantics aren't critical for practical use of the information space.</span></span>

- <span data-ttu-id="8ec42-217">Quando si scrive un provider per uno spazio informazioni così grande e interconnesso che non è tecnicamente possibile generare tipi .NET reali per lo spazio informazioni.</span><span class="sxs-lookup"><span data-stu-id="8ec42-217">When you are writing a provider for an information space that is so large and interconnected that it isn’t technically feasible to generate real .NET types for the information space.</span></span>

<span data-ttu-id="8ec42-218">In questo esempio, ogni tipo fornito `obj`viene cancellato in type e `obj` tutti gli utilizzi del tipo verranno visualizzati come tipo nel codice compilato.</span><span class="sxs-lookup"><span data-stu-id="8ec42-218">In this example, each provided type is erased to type `obj`, and all uses of the type will appear as type `obj` in compiled code.</span></span> <span data-ttu-id="8ec42-219">Infatti, gli oggetti sottostanti in questi esempi sono `System.Object` stringhe, ma il tipo verrà visualizzato come nel codice compilato .NET.</span><span class="sxs-lookup"><span data-stu-id="8ec42-219">In fact, the underlying objects in these examples are strings, but the type will appear as `System.Object` in .NET compiled code.</span></span> <span data-ttu-id="8ec42-220">Come per tutti gli usi della cancellazione del tipo, è possibile utilizzare il boxing esplicito, l'unboxing e il cast ai tipi cancellati sovvertiti.</span><span class="sxs-lookup"><span data-stu-id="8ec42-220">As with all uses of type erasure, you can use explicit boxing, unboxing, and casting to subvert erased types.</span></span> <span data-ttu-id="8ec42-221">In questo caso, un'eccezione cast non valida può generare quando viene utilizzato l'oggetto.</span><span class="sxs-lookup"><span data-stu-id="8ec42-221">In this case, a cast exception that isn’t valid may result when the object is used.</span></span> <span data-ttu-id="8ec42-222">Un runtime del provider può definire il proprio tipo di rappresentazione privata per la protezione da false rappresentazioni.</span><span class="sxs-lookup"><span data-stu-id="8ec42-222">A provider runtime can define its own private representation type to help protect against false representations.</span></span> <span data-ttu-id="8ec42-223">Non è possibile definire i tipi cancellati in F .</span><span class="sxs-lookup"><span data-stu-id="8ec42-223">You can’t define erased types in F# itself.</span></span> <span data-ttu-id="8ec42-224">Solo i tipi forniti possono essere cancellati.</span><span class="sxs-lookup"><span data-stu-id="8ec42-224">Only provided types may be erased.</span></span> <span data-ttu-id="8ec42-225">È necessario comprendere le ramificazioni, sia pratiche che semantiche, dell'utilizzo di tipi cancellati per il provider di tipi o di un provider che fornisce tipi cancellati.</span><span class="sxs-lookup"><span data-stu-id="8ec42-225">You must understand the ramifications, both practical and semantic, of using either erased types for your type provider or a provider that provides erased types.</span></span> <span data-ttu-id="8ec42-226">Un tipo cancellato non ha un tipo .NET reale.</span><span class="sxs-lookup"><span data-stu-id="8ec42-226">An erased type has no real .NET type.</span></span> <span data-ttu-id="8ec42-227">Pertanto, non è possibile eseguire una reflection accurata sul tipo ed è possibile sovvertire i tipi cancellati se si utilizzano cast di runtime e altre tecniche che si basano sulla semantica esatta dei tipi di runtime.</span><span class="sxs-lookup"><span data-stu-id="8ec42-227">Therefore, you cannot do accurate reflection over the type, and you might subvert erased types if you use runtime casts and other techniques that rely on exact runtime type semantics.</span></span> <span data-ttu-id="8ec42-228">La sottoversione dei tipi cancellati spesso genera eccezioni di cast dei tipi in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="8ec42-228">Subversion of erased types frequently results in type cast exceptions at runtime.</span></span>

### <a name="choosing-representations-for-erased-provided-types"></a><span data-ttu-id="8ec42-229">Scelta delle rappresentazioni per i tipi forniti cancellatiChoosing Representations for Erased Provided Types</span><span class="sxs-lookup"><span data-stu-id="8ec42-229">Choosing Representations for Erased Provided Types</span></span>

<span data-ttu-id="8ec42-230">Per alcuni utilizzi dei tipi forniti cancellati, non è necessaria alcuna rappresentazione.</span><span class="sxs-lookup"><span data-stu-id="8ec42-230">For some uses of erased provided types, no representation is required.</span></span> <span data-ttu-id="8ec42-231">Ad esempio, il tipo fornito cancellato potrebbe contenere solo proprietà statiche e membri e nessun costruttore e nessun metodo o proprietà restituirebbe un'istanza del tipo.</span><span class="sxs-lookup"><span data-stu-id="8ec42-231">For example, the erased provided type might contain only static properties and members and no constructors, and no methods or properties would return an instance of the type.</span></span> <span data-ttu-id="8ec42-232">Se è possibile raggiungere istanze di un tipo fornito cancellato, è necessario considerare le domande seguenti:If you can reach instances of an erased provided type, you must consider the following questions:</span><span class="sxs-lookup"><span data-stu-id="8ec42-232">If you can reach instances of an erased provided type, you must consider the following questions:</span></span>

<span data-ttu-id="8ec42-233">**Qual è la cancellazione di un tipo fornito?**</span><span class="sxs-lookup"><span data-stu-id="8ec42-233">**What is the erasure of a provided type?**</span></span>

- <span data-ttu-id="8ec42-234">La cancellazione di un tipo fornito è il modo in cui il tipo viene visualizzato nel codice .NET compilato.</span><span class="sxs-lookup"><span data-stu-id="8ec42-234">The erasure of a provided type is how the type appears in compiled .NET code.</span></span>

- <span data-ttu-id="8ec42-235">La cancellazione di un tipo di classe cancellato fornito è sempre il primo tipo di base non cancellato nella catena di ereditarietà del tipo.</span><span class="sxs-lookup"><span data-stu-id="8ec42-235">The erasure of a provided erased class type is always the first non-erased base type in the inheritance chain of the type.</span></span>

- <span data-ttu-id="8ec42-236">La cancellazione di un tipo di `System.Object`interfaccia cancellata fornita è sempre .</span><span class="sxs-lookup"><span data-stu-id="8ec42-236">The erasure of a provided erased interface type is always `System.Object`.</span></span>

<span data-ttu-id="8ec42-237">**Quali sono le rappresentazioni di un tipo fornito?**</span><span class="sxs-lookup"><span data-stu-id="8ec42-237">**What are the representations of a provided type?**</span></span>

- <span data-ttu-id="8ec42-238">L'insieme di oggetti possibili per un tipo fornito cancellato sono chiamati le relative rappresentazioni.</span><span class="sxs-lookup"><span data-stu-id="8ec42-238">The set of possible objects for an erased provided type are called its representations.</span></span> <span data-ttu-id="8ec42-239">Nell'esempio in questo documento, le rappresentazioni di `Type1..Type100` tutti i tipi forniti cancellati sono sempre oggetti stringa.</span><span class="sxs-lookup"><span data-stu-id="8ec42-239">In the example in this document, the representations of all the erased provided types `Type1..Type100` are always string objects.</span></span>

<span data-ttu-id="8ec42-240">Tutte le rappresentazioni di un tipo fornito devono essere compatibili con la cancellazione del tipo fornito.</span><span class="sxs-lookup"><span data-stu-id="8ec42-240">All representations of a provided type must be compatible with the erasure of the provided type.</span></span> <span data-ttu-id="8ec42-241">(In caso contrario, il compilatore F , verrà generato un errore per un utilizzo del provider di tipi o non verificabile verrà generato codice .NET non valido.</span><span class="sxs-lookup"><span data-stu-id="8ec42-241">(Otherwise, either the F# compiler will give an error for a use of the type provider, or unverifiable .NET code that isn't valid will be generated.</span></span> <span data-ttu-id="8ec42-242">Un provider di tipi non è valido se restituisce un codice che fornisce una rappresentazione non valida.</span><span class="sxs-lookup"><span data-stu-id="8ec42-242">A type provider isn’t valid if it returns code that gives a  representation that isn't valid.)</span></span>

<span data-ttu-id="8ec42-243">È possibile scegliere una rappresentazione per gli oggetti forniti utilizzando uno dei seguenti approcci, entrambi molto comuni:</span><span class="sxs-lookup"><span data-stu-id="8ec42-243">You can choose a representation for provided objects by using either of the following approaches, both of which are very common:</span></span>

- <span data-ttu-id="8ec42-244">Se si fornisce semplicemente un wrapper fortemente tipizzato su un tipo .NET esistente, è spesso opportuno che il tipo cancelli a tale tipo, utilizzi istanze di tale tipo come rappresentazioni o entrambi.</span><span class="sxs-lookup"><span data-stu-id="8ec42-244">If you're simply providing a strongly typed wrapper over an existing .NET type, it often makes sense for your type to erase to that type, use instances of that type as representations, or both.</span></span> <span data-ttu-id="8ec42-245">Questo approccio è appropriato quando la maggior parte dei metodi esistenti su tale tipo ha ancora senso quando si utilizza la versione fortemente tipizzata.</span><span class="sxs-lookup"><span data-stu-id="8ec42-245">This approach is appropriate when most of the existing methods on that type still make sense when using the strongly typed version.</span></span>

- <span data-ttu-id="8ec42-246">Se si desidera creare un'API che differisce in modo significativo da qualsiasi API .NET esistente, è opportuno creare tipi di runtime che saranno la cancellazione dei tipi e le rappresentazioni per i tipi forniti.</span><span class="sxs-lookup"><span data-stu-id="8ec42-246">If you want to create an API that differs significantly from any existing .NET API, it makes sense to create runtime types that will be the type erasure and representations for the provided types.</span></span>

<span data-ttu-id="8ec42-247">L'esempio in questo documento usa le stringhe come rappresentazioni di oggetti forniti.</span><span class="sxs-lookup"><span data-stu-id="8ec42-247">The example in this document uses strings as representations of provided objects.</span></span> <span data-ttu-id="8ec42-248">Spesso, può essere opportuno utilizzare altri oggetti per le rappresentazioni.</span><span class="sxs-lookup"><span data-stu-id="8ec42-248">Frequently, it may be appropriate to use other objects for representations.</span></span> <span data-ttu-id="8ec42-249">Ad esempio, è possibile utilizzare un dizionario come contenitore delle proprietà:For example, you may use a dictionary as a property bag:</span><span class="sxs-lookup"><span data-stu-id="8ec42-249">For example, you may use a dictionary as a property bag:</span></span>

```fsharp
ProvidedConstructor(parameters = [],
    invokeCode= (fun args -> <@@ (new Dictionary<string,obj>()) :> obj @@>))
```

<span data-ttu-id="8ec42-250">In alternativa, è possibile definire un tipo nel provider di tipi che verrà utilizzato in fase di esecuzione per formare la rappresentazione, insieme a una o più operazioni di runtime:Alternative, you may define a type in your type provider that will be used at runtime to form the representation, along with one or more runtime operations:</span><span class="sxs-lookup"><span data-stu-id="8ec42-250">As an alternative, you may define a type in your type provider that will be used at runtime to form the representation, along with one or more runtime operations:</span></span>

```fsharp
type DataObject() =
    let data = Dictionary<string,obj>()
    member x.RuntimeOperation() = data.Count
```

<span data-ttu-id="8ec42-251">I membri forniti possono quindi costruire istanze di questo tipo di oggetto:Provided members can then construct instances of this object type:</span><span class="sxs-lookup"><span data-stu-id="8ec42-251">Provided members can then construct instances of this object type:</span></span>

```fsharp
ProvidedConstructor(parameters = [],
    invokeCode= (fun args -> <@@ (new DataObject()) :> obj @@>))
```

<span data-ttu-id="8ec42-252">In questo caso, è possibile (facoltativamente) utilizzare questo tipo come tipo `baseType` di cancellazione specificando questo tipo come quando si costruisce il `ProvidedTypeDefinition`:</span><span class="sxs-lookup"><span data-stu-id="8ec42-252">In this case, you may (optionally) use this type as the type erasure by specifying this type as the `baseType` when constructing the `ProvidedTypeDefinition`:</span></span>

```fsharp
ProvidedTypeDefinition(…, baseType = Some typeof<DataObject> )
…
ProvidedConstructor(…, InvokeCode = (fun args -> <@@ new DataObject() @@>), …)
```

### <a name="key-lessons"></a><span data-ttu-id="8ec42-253">Lezioni chiave</span><span class="sxs-lookup"><span data-stu-id="8ec42-253">Key Lessons</span></span>

<span data-ttu-id="8ec42-254">Nella sezione precedente è stato illustrato come creare un provider di tipi di cancellazione semplice che fornisce una gamma di tipi, proprietà e metodi.</span><span class="sxs-lookup"><span data-stu-id="8ec42-254">The previous section explained how to create a simple erasing type provider that provides a range of types, properties, and methods.</span></span> <span data-ttu-id="8ec42-255">In questa sezione è stato inoltre illustrato il concetto di cancellazione dei tipi, inclusi alcuni dei vantaggi e degli svantaggi di fornire tipi cancellati da un provider di tipi e sono state discusse le rappresentazioni dei tipi cancellati.</span><span class="sxs-lookup"><span data-stu-id="8ec42-255">This section also explained the concept of type erasure, including some of the advantages and disadvantages of providing erased types from a type provider, and discussed representations of erased types.</span></span>

## <a name="a-type-provider-that-uses-static-parameters"></a><span data-ttu-id="8ec42-256">Un provider di tipi che utilizza parametri staticiA Type Provider That Uses Static Parameters</span><span class="sxs-lookup"><span data-stu-id="8ec42-256">A Type Provider That Uses Static Parameters</span></span>

<span data-ttu-id="8ec42-257">La possibilità di parametrizzare i provider di tipi in base ai dati statici consente molti scenari interessanti, anche nei casi in cui il provider non deve accedere a dati locali o remoti.</span><span class="sxs-lookup"><span data-stu-id="8ec42-257">The ability to parameterize type providers by static data enables many interesting scenarios, even in cases when the provider doesn't need to access any local or remote data.</span></span> <span data-ttu-id="8ec42-258">In questa sezione, imparerai alcune tecniche di base per mettere insieme un provider di questo tipo.</span><span class="sxs-lookup"><span data-stu-id="8ec42-258">In this section, you’ll learn some basic techniques for putting together such a provider.</span></span>

### <a name="type-checked-regex-provider"></a><span data-ttu-id="8ec42-259">Tipo Checked Regex Provider</span><span class="sxs-lookup"><span data-stu-id="8ec42-259">Type Checked Regex Provider</span></span>

<span data-ttu-id="8ec42-260">Si supponga di voler implementare un provider di tipi <xref:System.Text.RegularExpressions.Regex> per le espressioni regolari che esegue il wrapping delle librerie .NET in un'interfaccia che fornisce le seguenti garanzie in fase di compilazione:</span><span class="sxs-lookup"><span data-stu-id="8ec42-260">Imagine that you want to implement a type provider for regular expressions that wraps the .NET <xref:System.Text.RegularExpressions.Regex> libraries in an interface that provides the following compile-time guarantees:</span></span>

- <span data-ttu-id="8ec42-261">Verifica della validità di un'espressione regolare.</span><span class="sxs-lookup"><span data-stu-id="8ec42-261">Verifying whether a regular expression is valid.</span></span>

- <span data-ttu-id="8ec42-262">Fornire proprietà denominate per le corrispondenze basate su qualsiasi nome di gruppo nell'espressione regolare.</span><span class="sxs-lookup"><span data-stu-id="8ec42-262">Providing named properties on matches that are based on any group names in the regular expression.</span></span>

<span data-ttu-id="8ec42-263">In questa sezione viene illustrato come `RegexTyped` utilizzare i provider di tipi per creare un tipo che il modello di espressione regolare parametrizza per fornire questi vantaggi.</span><span class="sxs-lookup"><span data-stu-id="8ec42-263">This section shows you how to use type providers to create a `RegexTyped` type that the regular expression pattern parameterizes to provide these benefits.</span></span> <span data-ttu-id="8ec42-264">Il compilatore segnalerà un errore se il modello fornito non è valido e il provider di tipi può estrarre i gruppi dal modello in modo che sia possibile accedervi usando le proprietà denominate nelle corrispondenze.</span><span class="sxs-lookup"><span data-stu-id="8ec42-264">The compiler will report an error if the supplied pattern isn't valid, and the type provider can extract the groups from the pattern so that you can access them by using named properties on matches.</span></span> <span data-ttu-id="8ec42-265">Quando si progetta un provider di tipi, è necessario considerare come l'API esposta deve essere per gli utenti finali e come questa progettazione verrà convertita in codice .NET.</span><span class="sxs-lookup"><span data-stu-id="8ec42-265">When you design a type provider, you should consider how its exposed API should look to end users and how this design will translate to .NET code.</span></span> <span data-ttu-id="8ec42-266">L'esempio seguente mostra come usare un'API di questo tipo per ottenere i componenti del prefisso:</span><span class="sxs-lookup"><span data-stu-id="8ec42-266">The following example shows how to use such an API to get the components of the area code:</span></span>

```fsharp
type T = RegexTyped< @"(?<AreaCode>^\d{3})-(?<PhoneNumber>\d{3}-\d{4}$)">
let reg = T()
let result = T.IsMatch("425-555-2345")
let r = reg.Match("425-555-2345").Group_AreaCode.Value //r equals "425"
```

<span data-ttu-id="8ec42-267">Nell'esempio seguente viene illustrato come il provider di tipi converte queste chiamate:The following example shows how the type provider translates these calls:</span><span class="sxs-lookup"><span data-stu-id="8ec42-267">The following example shows how the type provider translates these calls:</span></span>

```fsharp
let reg = new Regex(@"(?<AreaCode>^\d{3})-(?<PhoneNumber>\d{3}-\d{4}$)")
let result = reg.IsMatch("425-123-2345")
let r = reg.Match("425-123-2345").Groups.["AreaCode"].Value //r equals "425"
```

<span data-ttu-id="8ec42-268">Tenere presente quanto segue:</span><span class="sxs-lookup"><span data-stu-id="8ec42-268">Note the following points:</span></span>

- <span data-ttu-id="8ec42-269">Il tipo Regex standard `RegexTyped` rappresenta il tipo con parametri.</span><span class="sxs-lookup"><span data-stu-id="8ec42-269">The standard Regex type represents the parameterized `RegexTyped` type.</span></span>

- <span data-ttu-id="8ec42-270">Il `RegexTyped` costruttore genera una chiamata al costruttore Regex, passando l'argomento di tipo statico per il modello.</span><span class="sxs-lookup"><span data-stu-id="8ec42-270">The `RegexTyped` constructor results in a call to the Regex constructor, passing in the static type argument for the pattern.</span></span>

- <span data-ttu-id="8ec42-271">I risultati `Match` del metodo sono <xref:System.Text.RegularExpressions.Match> rappresentati dal tipo standard.</span><span class="sxs-lookup"><span data-stu-id="8ec42-271">The results of the `Match` method are represented by the standard <xref:System.Text.RegularExpressions.Match> type.</span></span>

- <span data-ttu-id="8ec42-272">Ogni gruppo denominato genera una proprietà fornita e l'accesso alla proprietà comporta l'utilizzo di un indicizzatore nella raccolta di `Groups` una corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="8ec42-272">Each named group results in a provided property, and accessing the property results in a use of an indexer on a match’s `Groups` collection.</span></span>

<span data-ttu-id="8ec42-273">Il codice seguente è il nucleo della logica per implementare tale provider e in questo esempio viene omalsa l'aggiunta di tutti i membri al tipo fornito.</span><span class="sxs-lookup"><span data-stu-id="8ec42-273">The following code is the core of the logic to implement such a provider, and this example omits the addition of all members to the provided type.</span></span> <span data-ttu-id="8ec42-274">Per informazioni su ogni membro aggiunto, vedere la sezione appropriata più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="8ec42-274">For information about each added member, see the appropriate section later in this topic.</span></span> <span data-ttu-id="8ec42-275">Per il codice completo, scaricare l'esempio dal pacchetto di [esempio di F . 3.0](https://archive.codeplex.com/?p=fsharp3sample) sul sito Web CodePlex.</span><span class="sxs-lookup"><span data-stu-id="8ec42-275">For the full code, download the sample from the [F# 3.0 Sample Pack](https://archive.codeplex.com/?p=fsharp3sample) on the CodePlex website.</span></span>

```fsharp
namespace Samples.FSharp.RegexTypeProvider

open System.Reflection
open Microsoft.FSharp.Core.CompilerServices
open Samples.FSharp.ProvidedTypes
open System.Text.RegularExpressions

[<TypeProvider>]
type public CheckedRegexProvider() as this =
    inherit TypeProviderForNamespaces()

    // Get the assembly and namespace used to house the provided types
    let thisAssembly = Assembly.GetExecutingAssembly()
    let rootNamespace = "Samples.FSharp.RegexTypeProvider"
    let baseTy = typeof<obj>
    let staticParams = [ProvidedStaticParameter("pattern", typeof<string>)]

    let regexTy = ProvidedTypeDefinition(thisAssembly, rootNamespace, "RegexTyped", Some baseTy)

    do regexTy.DefineStaticParameters(
        parameters=staticParams,
        instantiationFunction=(fun typeName parameterValues ->

          match parameterValues with
          | [| :? string as pattern|] ->

            // Create an instance of the regular expression.
            //
            // This will fail with System.ArgumentException if the regular expression is not valid.
            // The exception will escape the type provider and be reported in client code.
            let r = System.Text.RegularExpressions.Regex(pattern)

            // Declare the typed regex provided type.
            // The type erasure of this type is 'obj', even though the representation will always be a Regex
            // This, combined with hiding the object methods, makes the IntelliSense experience simpler.
            let ty =
              ProvidedTypeDefinition(
                thisAssembly,
                rootNamespace,
                typeName,
                baseType = Some baseTy)

            ...

            ty
          | _ -> failwith "unexpected parameter values"))

    do this.AddNamespace(rootNamespace, [regexTy])

[<TypeProviderAssembly>]
do ()
```

<span data-ttu-id="8ec42-276">Tenere presente quanto segue:</span><span class="sxs-lookup"><span data-stu-id="8ec42-276">Note the following points:</span></span>

- <span data-ttu-id="8ec42-277">Il provider di tipi accetta `pattern`due parametri statici: , che è obbligatorio, e `options`, che sono facoltativi (perché viene fornito un valore predefinito).</span><span class="sxs-lookup"><span data-stu-id="8ec42-277">The type provider takes two static parameters: the `pattern`, which is mandatory, and the `options`, which are optional (because a default value is provided).</span></span>

- <span data-ttu-id="8ec42-278">Dopo aver fornito gli argomenti statici, si crea un'istanza dell'espressione regolare.</span><span class="sxs-lookup"><span data-stu-id="8ec42-278">After the static arguments are supplied, you create an instance of the regular expression.</span></span> <span data-ttu-id="8ec42-279">Questa istanza genererà un'eccezione se il Regex non è valido e questo errore verrà segnalato agli utenti.</span><span class="sxs-lookup"><span data-stu-id="8ec42-279">This instance will throw an exception if the Regex is malformed, and this error will be reported to users.</span></span>

- <span data-ttu-id="8ec42-280">All'interno del `DefineStaticParameters` callback, si definisce il tipo che verrà restituito dopo che gli argomenti vengono forniti.</span><span class="sxs-lookup"><span data-stu-id="8ec42-280">Within the `DefineStaticParameters` callback, you define the type that will be returned after the arguments are supplied.</span></span>

- <span data-ttu-id="8ec42-281">Questo codice `HideObjectMethods` viene impostato su true in modo che l'esperienza IntelliSense rimarrà semplificata.</span><span class="sxs-lookup"><span data-stu-id="8ec42-281">This code sets `HideObjectMethods` to true so that the IntelliSense experience will remain streamlined.</span></span> <span data-ttu-id="8ec42-282">Questo attributo `Equals` `GetHashCode`fa `Finalize`sì `GetType` che i membri , , e vengano eliminati dagli elenchi IntelliSense per un oggetto fornito.</span><span class="sxs-lookup"><span data-stu-id="8ec42-282">This attribute causes the `Equals`, `GetHashCode`, `Finalize`, and `GetType` members to be suppressed from IntelliSense lists for a provided object.</span></span>

- <span data-ttu-id="8ec42-283">Utilizzare `obj` come tipo di base del metodo, ma `Regex` si utilizzerà un oggetto come rappresentazione di runtime di questo tipo, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="8ec42-283">You use `obj` as the base type of the method, but you’ll use a `Regex` object as the runtime representation of this type, as the next example shows.</span></span>

- <span data-ttu-id="8ec42-284">La chiamata `Regex` al costruttore <xref:System.ArgumentException> genera un quando un'espressione regolare non è valida.</span><span class="sxs-lookup"><span data-stu-id="8ec42-284">The call to the `Regex` constructor throws a <xref:System.ArgumentException> when a regular expression isn’t valid.</span></span> <span data-ttu-id="8ec42-285">Il compilatore intercetta questa eccezione e segnala un messaggio di errore all'utente in fase di compilazione o nell'editor di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="8ec42-285">The compiler catches this exception and reports an error message to the user at compile time or in the Visual Studio editor.</span></span> <span data-ttu-id="8ec42-286">Questa eccezione consente la convalida delle espressioni regolari senza eseguire un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="8ec42-286">This exception enables regular expressions to be validated without running an application.</span></span>

<span data-ttu-id="8ec42-287">Il tipo definito in precedenza non è ancora utile perché non contiene proprietà o metodi significativi.</span><span class="sxs-lookup"><span data-stu-id="8ec42-287">The type defined above isn't useful yet because it doesn’t contain any meaningful methods or properties.</span></span> <span data-ttu-id="8ec42-288">Aggiungere innanzitutto `IsMatch` un metodo statico:First, add a static method:</span><span class="sxs-lookup"><span data-stu-id="8ec42-288">First, add a static `IsMatch` method:</span></span>

```fsharp
let isMatch =
    ProvidedMethod(
        methodName = "IsMatch",
        parameters = [ProvidedParameter("input", typeof<string>)],
        returnType = typeof<bool>,
        isStatic = true,
        invokeCode = fun args -> <@@ Regex.IsMatch(%%args.[0], pattern) @@>)

isMatch.AddXmlDoc "Indicates whether the regular expression finds a match in the specified input string."
ty.AddMember isMatch
```

<span data-ttu-id="8ec42-289">Il codice precedente definisce un metodo , che `bool`accetta una stringa come input e restituisce un oggetto `IsMatch`.</span><span class="sxs-lookup"><span data-stu-id="8ec42-289">The previous code defines a method `IsMatch`, which takes a string as input and returns a `bool`.</span></span> <span data-ttu-id="8ec42-290">L'unica parte difficile è `args` l'uso `InvokeCode` dell'argomento all'interno della definizione.</span><span class="sxs-lookup"><span data-stu-id="8ec42-290">The only tricky part is the use of the `args` argument within the `InvokeCode` definition.</span></span> <span data-ttu-id="8ec42-291">In questo `args` esempio, è un elenco di citazioni che rappresenta gli argomenti di questo metodo.</span><span class="sxs-lookup"><span data-stu-id="8ec42-291">In this example, `args` is a list of quotations that represents the arguments to this method.</span></span> <span data-ttu-id="8ec42-292">Se il metodo è un metodo di `this` istanza, il primo argomento rappresenta l'argomento.</span><span class="sxs-lookup"><span data-stu-id="8ec42-292">If the method is an instance method, the first argument represents the `this` argument.</span></span> <span data-ttu-id="8ec42-293">Tuttavia, per un metodo statico, gli argomenti sono tutti solo gli argomenti espliciti per il metodo.</span><span class="sxs-lookup"><span data-stu-id="8ec42-293">However, for a static method, the arguments are all just the explicit arguments to the method.</span></span> <span data-ttu-id="8ec42-294">Si noti che il tipo del valore tra virgolette `bool`deve corrispondere al tipo restituito specificato (in questo caso, ).</span><span class="sxs-lookup"><span data-stu-id="8ec42-294">Note that the type of the quoted value should match the specified return type (in this case, `bool`).</span></span> <span data-ttu-id="8ec42-295">Si noti inoltre `AddXmlDoc` che questo codice utilizza il metodo per assicurarsi che il metodo fornito disponga anche di documentazione utile, che è possibile fornire tramite IntelliSense.Also note that this code uses the method to make sure that the provided method also has useful documentation, which you can supply through IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="8ec42-295">Also note that this code uses the `AddXmlDoc` method to make sure that the provided method also has useful documentation, which you can supply through IntelliSense.</span></span>

<span data-ttu-id="8ec42-296">Successivamente, aggiungere un'istanza Match metodo.</span><span class="sxs-lookup"><span data-stu-id="8ec42-296">Next, add an instance Match method.</span></span> <span data-ttu-id="8ec42-297">Tuttavia, questo metodo deve restituire `Match` un valore di un tipo fornito in modo che i gruppi sono accessibili in modo fortemente tipizzato.</span><span class="sxs-lookup"><span data-stu-id="8ec42-297">However, this method should return a value of a provided `Match` type so that the groups can be accessed in a strongly typed fashion.</span></span> <span data-ttu-id="8ec42-298">Pertanto, è `Match` innanzitutto dichiarato il tipo.</span><span class="sxs-lookup"><span data-stu-id="8ec42-298">Thus, you first declare the `Match` type.</span></span> <span data-ttu-id="8ec42-299">Poiché questo tipo dipende dal modello fornito come argomento statico, questo tipo deve essere annidato all'interno della definizione del tipo con parametri:Because this type depends on the pattern that was supplied as a static argument, this type must be nested within the parameterized type definition:</span><span class="sxs-lookup"><span data-stu-id="8ec42-299">Because this type depends on the pattern that was supplied as a static argument, this type must be nested within the parameterized type definition:</span></span>

```fsharp
let matchTy =
    ProvidedTypeDefinition(
        "MatchType",
        baseType = Some baseTy,
        hideObjectMethods = true)

ty.AddMember matchTy
```

<span data-ttu-id="8ec42-300">Aggiungere quindi una proprietà al tipo di corrispondenza per ogni gruppo.</span><span class="sxs-lookup"><span data-stu-id="8ec42-300">You then add one property to the Match type for each group.</span></span> <span data-ttu-id="8ec42-301">In fase di esecuzione, <xref:System.Text.RegularExpressions.Match> una corrispondenza viene rappresentata come valore, pertanto l'offerta che definisce la proprietà deve utilizzare la <xref:System.Text.RegularExpressions.Match.Groups> proprietà indicizzata per ottenere il gruppo pertinente.</span><span class="sxs-lookup"><span data-stu-id="8ec42-301">At runtime, a match is represented as a <xref:System.Text.RegularExpressions.Match> value, so the quotation that defines the property must use the <xref:System.Text.RegularExpressions.Match.Groups> indexed property to get the relevant group.</span></span>

```fsharp
for group in r.GetGroupNames() do
    // Ignore the group named 0, which represents all input.
    if group <> "0" then
    let prop =
      ProvidedProperty(
        propertyName = group,
        propertyType = typeof<Group>,
        getterCode = fun args -> <@@ ((%%args.[0]:obj) :?> Match).Groups.[group] @@>)
        prop.AddXmlDoc(sprintf @"Gets the ""%s"" group from this match" group)
    matchTy.AddMember prop
```

<span data-ttu-id="8ec42-302">Anche in questo caso, si noti che si sta aggiungendo la documentazione XML alla proprietà fornita.</span><span class="sxs-lookup"><span data-stu-id="8ec42-302">Again, note that you’re adding XML documentation to the provided property.</span></span> <span data-ttu-id="8ec42-303">Si noti inoltre che una `GetterCode` proprietà può essere letta se viene `SetterCode` fornita una funzione e la proprietà può essere scritta se viene fornita una funzione, pertanto la proprietà risultante è di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="8ec42-303">Also note that a property can be read if a `GetterCode` function is provided, and the property can be written if a `SetterCode` function is provided, so the resulting property is read only.</span></span>

<span data-ttu-id="8ec42-304">A questo punto è possibile creare un `Match` metodo di istanza che restituisce un valore di questo tipo:Now you can create an instance method that returns a value of this type:</span><span class="sxs-lookup"><span data-stu-id="8ec42-304">Now you can create an instance method that returns a value of this `Match` type:</span></span>

```fsharp
let matchMethod =
    ProvidedMethod(
        methodName = "Match",
        parameters = [ProvidedParameter("input", typeof<string>)],
        returnType = matchTy,
        invokeCode = fun args -> <@@ ((%%args.[0]:obj) :?> Regex).Match(%%args.[1]) :> obj @@>)

matchMeth.AddXmlDoc "Searches the specified input string for the first occurrence of this regular expression"

ty.AddMember matchMeth
```

<span data-ttu-id="8ec42-305">Poiché si sta creando `args.[0]` un `RegexTyped` metodo di istanza, rappresenta `args.[1]` l'istanza in cui viene chiamato il metodo ed è l'argomento di input.</span><span class="sxs-lookup"><span data-stu-id="8ec42-305">Because you are creating an instance method, `args.[0]` represents the `RegexTyped` instance on which the method is being called, and `args.[1]` is the input argument.</span></span>

<span data-ttu-id="8ec42-306">Infine, fornire un costruttore in modo che le istanze del tipo fornito possono essere create.</span><span class="sxs-lookup"><span data-stu-id="8ec42-306">Finally, provide a constructor so that instances of the provided type can be created.</span></span>

```fsharp
let ctor =
    ProvidedConstructor(
        parameters = [],
        invokeCode = fun args -> <@@ Regex(pattern, options) :> obj @@>)

ctor.AddXmlDoc("Initializes a regular expression instance.")

ty.AddMember ctor
```

<span data-ttu-id="8ec42-307">Il costruttore si limita a cancellare la creazione di un'istanza Regex .NET standard, che viene nuovamente sottoposta a boxing in un oggetto perché `obj` è la cancellazione del tipo fornito.</span><span class="sxs-lookup"><span data-stu-id="8ec42-307">The constructor merely erases to the creation of a standard .NET Regex instance, which is again boxed to an object because `obj` is the erasure of the provided type.</span></span> <span data-ttu-id="8ec42-308">Con tale modifica, l'utilizzo dell'API di esempio specificato in precedenza nell'argomento funziona come previsto.</span><span class="sxs-lookup"><span data-stu-id="8ec42-308">With that change, the sample API usage that specified earlier in the topic works as expected.</span></span> <span data-ttu-id="8ec42-309">Il codice seguente è completo e finale:The following code is complete and final:</span><span class="sxs-lookup"><span data-stu-id="8ec42-309">The following code is complete and final:</span></span>

```fsharp
namespace Samples.FSharp.RegexTypeProvider

open System.Reflection
open Microsoft.FSharp.Core.CompilerServices
open Samples.FSharp.ProvidedTypes
open System.Text.RegularExpressions

[<TypeProvider>]
type public CheckedRegexProvider() as this =
    inherit TypeProviderForNamespaces()

    // Get the assembly and namespace used to house the provided types.
    let thisAssembly = Assembly.GetExecutingAssembly()
    let rootNamespace = "Samples.FSharp.RegexTypeProvider"
    let baseTy = typeof<obj>
    let staticParams = [ProvidedStaticParameter("pattern", typeof<string>)]

    let regexTy = ProvidedTypeDefinition(thisAssembly, rootNamespace, "RegexTyped", Some baseTy)

    do regexTy.DefineStaticParameters(
        parameters=staticParams,
        instantiationFunction=(fun typeName parameterValues ->

            match parameterValues with
            | [| :? string as pattern|] ->

                // Create an instance of the regular expression.

                let r = System.Text.RegularExpressions.Regex(pattern)

                // Declare the typed regex provided type.

                let ty =
                    ProvidedTypeDefinition(
                        thisAssembly,
                        rootNamespace,
                        typeName,
                        baseType = Some baseTy)

                ty.AddXmlDoc "A strongly typed interface to the regular expression '%s'"

                // Provide strongly typed version of Regex.IsMatch static method.
                let isMatch =
                    ProvidedMethod(
                        methodName = "IsMatch",
                        parameters = [ProvidedParameter("input", typeof<string>)],
                        returnType = typeof<bool>,
                        isStatic = true,
                        invokeCode = fun args -> <@@ Regex.IsMatch(%%args.[0], pattern) @@>)

                isMatch.AddXmlDoc "Indicates whether the regular expression finds a match in the specified input string"

                ty.AddMember isMatch

                // Provided type for matches
                // Again, erase to obj even though the representation will always be a Match
                let matchTy =
                    ProvidedTypeDefinition(
                        "MatchType",
                        baseType = Some baseTy,
                        hideObjectMethods = true)

                // Nest the match type within parameterized Regex type.
                ty.AddMember matchTy

                // Add group properties to match type
                for group in r.GetGroupNames() do
                    // Ignore the group named 0, which represents all input.
                    if group <> "0" then
                        let prop =
                          ProvidedProperty(
                            propertyName = group,
                            propertyType = typeof<Group>,
                            getterCode = fun args -> <@@ ((%%args.[0]:obj) :?> Match).Groups.[group] @@>)
                        prop.AddXmlDoc(sprintf @"Gets the ""%s"" group from this match" group)
                        matchTy.AddMember(prop)

                // Provide strongly typed version of Regex.Match instance method.
                let matchMeth =
                  ProvidedMethod(
                    methodName = "Match",
                    parameters = [ProvidedParameter("input", typeof<string>)],
                    returnType = matchTy,
                    invokeCode = fun args -> <@@ ((%%args.[0]:obj) :?> Regex).Match(%%args.[1]) :> obj @@>)
                matchMeth.AddXmlDoc "Searches the specified input string for the first occurrence of this regular expression"

                ty.AddMember matchMeth

                // Declare a constructor.
                let ctor =
                  ProvidedConstructor(
                    parameters = [],
                    invokeCode = fun args -> <@@ Regex(pattern) :> obj @@>)

                // Add documentation to the constructor.
                ctor.AddXmlDoc "Initializes a regular expression instance"

                ty.AddMember ctor

                ty
            | _ -> failwith "unexpected parameter values"))

    do this.AddNamespace(rootNamespace, [regexTy])

[<TypeProviderAssembly>]
do ()
```

### <a name="key-lessons"></a><span data-ttu-id="8ec42-310">Lezioni chiave</span><span class="sxs-lookup"><span data-stu-id="8ec42-310">Key Lessons</span></span>

<span data-ttu-id="8ec42-311">In questa sezione è stato illustrato come creare un provider di tipi che opera sui relativi parametri statici.</span><span class="sxs-lookup"><span data-stu-id="8ec42-311">This section explained how to create a type provider that operates on its static parameters.</span></span> <span data-ttu-id="8ec42-312">Il provider controlla il parametro statico e fornisce le operazioni in base al relativo valore.</span><span class="sxs-lookup"><span data-stu-id="8ec42-312">The provider checks the static parameter and provides operations based on its value.</span></span>

## <a name="a-type-provider-that-is-backed-by-local-data"></a><span data-ttu-id="8ec42-313">Un provider di tipi supportato da dati localiA Type Provider That Is Backed by Local Data</span><span class="sxs-lookup"><span data-stu-id="8ec42-313">A Type Provider That Is Backed By Local Data</span></span>

<span data-ttu-id="8ec42-314">Spesso si desidera che i provider di tipi presentino API basate non solo su parametri statici, ma anche informazioni provenienti da sistemi locali o remoti.</span><span class="sxs-lookup"><span data-stu-id="8ec42-314">Frequently you might want type providers to present APIs based on not only static parameters but also information from local or remote systems.</span></span> <span data-ttu-id="8ec42-315">In questa sezione vengono illustrati i provider di tipi basati su dati locali, ad esempio i file di dati locali.</span><span class="sxs-lookup"><span data-stu-id="8ec42-315">This section discusses type providers that are based on local data, such as local data files.</span></span>

### <a name="simple-csv-file-provider"></a><span data-ttu-id="8ec42-316">Provider di file CSV semplice</span><span class="sxs-lookup"><span data-stu-id="8ec42-316">Simple CSV File Provider</span></span>

<span data-ttu-id="8ec42-317">Come semplice esempio, si consideri un provider di tipi per l'accesso ai dati scientifici in formato CSV (Comma Separated Value).</span><span class="sxs-lookup"><span data-stu-id="8ec42-317">As a simple example, consider a type provider for accessing scientific data in Comma Separated Value (CSV) format.</span></span> <span data-ttu-id="8ec42-318">In questa sezione si presuppone che i file CSV contengano una riga di intestazione seguita da dati a virgola mobile, come illustrato nella tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="8ec42-318">This section assumes that the CSV files contain a header row followed by floating point data, as the following table illustrates:</span></span>

|<span data-ttu-id="8ec42-319">Distanza (metro)</span><span class="sxs-lookup"><span data-stu-id="8ec42-319">Distance (meter)</span></span>|<span data-ttu-id="8ec42-320">Tempo (secondo)</span><span class="sxs-lookup"><span data-stu-id="8ec42-320">Time (second)</span></span>|
|----------------|-------------|
|<span data-ttu-id="8ec42-321">50.0</span><span class="sxs-lookup"><span data-stu-id="8ec42-321">50.0</span></span>|<span data-ttu-id="8ec42-322">3,7</span><span class="sxs-lookup"><span data-stu-id="8ec42-322">3.7</span></span>|
|<span data-ttu-id="8ec42-323">100.0</span><span class="sxs-lookup"><span data-stu-id="8ec42-323">100.0</span></span>|<span data-ttu-id="8ec42-324">5,2</span><span class="sxs-lookup"><span data-stu-id="8ec42-324">5.2</span></span>|
|<span data-ttu-id="8ec42-325">150.0</span><span class="sxs-lookup"><span data-stu-id="8ec42-325">150.0</span></span>|<span data-ttu-id="8ec42-326">6.4</span><span class="sxs-lookup"><span data-stu-id="8ec42-326">6.4</span></span>|

<span data-ttu-id="8ec42-327">In questa sezione viene illustrato come fornire un tipo `Distance` che `float<meter>` è `Time` possibile utilizzare `float<second>`per ottenere righe con una proprietà di tipo e una proprietà di tipo .</span><span class="sxs-lookup"><span data-stu-id="8ec42-327">This section shows how to provide a type that you can use to get rows with a `Distance` property of type `float<meter>` and a `Time` property of type `float<second>`.</span></span> <span data-ttu-id="8ec42-328">Per semplicità, vengono formulati i seguenti presupposti:</span><span class="sxs-lookup"><span data-stu-id="8ec42-328">For simplicity, the following assumptions are made:</span></span>

- <span data-ttu-id="8ec42-329">I nomi delle intestazioni sono senza unità o hanno il formato "Nome (unità)" e non contengono virgole.</span><span class="sxs-lookup"><span data-stu-id="8ec42-329">Header names are either unit-less or have the form "Name (unit)" and don't contain commas.</span></span>

- <span data-ttu-id="8ec42-330">Le unità sono tutte unità di System International (SI) come definito dal modulo [Microsoft.FSharp.Data.UnitSystems.SI.UnitNames Module (F )](https://msdn.microsoft.com/library/3cb43485-11f5-4aa7-a779-558f19d4013b) .</span><span class="sxs-lookup"><span data-stu-id="8ec42-330">Units are all System International (SI) units as the [Microsoft.FSharp.Data.UnitSystems.SI.UnitNames Module (F#)](https://msdn.microsoft.com/library/3cb43485-11f5-4aa7-a779-558f19d4013b) module defines.</span></span>

- <span data-ttu-id="8ec42-331">Le unità sono tutte semplici (ad esempio, metro) anziché composte (ad esempio, metro/secondo).</span><span class="sxs-lookup"><span data-stu-id="8ec42-331">Units are all simple (for example, meter) rather than compound (for example, meter/second).</span></span>

- <span data-ttu-id="8ec42-332">Tutte le colonne contengono dati a virgola mobile.</span><span class="sxs-lookup"><span data-stu-id="8ec42-332">All columns contain floating point data.</span></span>

<span data-ttu-id="8ec42-333">Un fornitore più completo allenterebbe queste restrizioni.</span><span class="sxs-lookup"><span data-stu-id="8ec42-333">A more complete provider would loosen these restrictions.</span></span>

<span data-ttu-id="8ec42-334">Anche in questo caso il primo passaggio consiste nel considerare l'aspetto dell'API.</span><span class="sxs-lookup"><span data-stu-id="8ec42-334">Again the first step is to consider how the API should look.</span></span> <span data-ttu-id="8ec42-335">Dato un file `info.csv` con i contenuti della tabella precedente (nel formato delimitato da virgole), gli utenti del provider possono scrivere codice simile all'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="8ec42-335">Given an `info.csv` file with the contents from the previous table (in comma-separated format), users of the provider should be able to write code that resembles the following example:</span></span>

```fsharp
let info = new MiniCsv<"info.csv">()
for row in info.Data do
let time = row.Time
printfn "%f" (float time)
```

<span data-ttu-id="8ec42-336">In questo caso, il compilatore deve convertire queste chiamate in qualcosa di simile all'esempio seguente:In this case, the compiler should convert these calls into something like the following example:</span><span class="sxs-lookup"><span data-stu-id="8ec42-336">In this case, the compiler should convert these calls into something like the following example:</span></span>

```fsharp
let info = new CsvFile("info.csv")
for row in info.Data do
let (time:float) = row.[1]
printfn "%f" (float time)
```

<span data-ttu-id="8ec42-337">La conversione ottimale richiederà al `CsvFile` provider di tipi di definire un tipo reale nell'assembly del provider di tipi.</span><span class="sxs-lookup"><span data-stu-id="8ec42-337">The optimal translation will require the type provider to define a real `CsvFile` type in the type provider's assembly.</span></span> <span data-ttu-id="8ec42-338">I provider di tipi spesso si basano su alcuni tipi di supporto e metodi per eseguire il wrapping di logica importante.</span><span class="sxs-lookup"><span data-stu-id="8ec42-338">Type providers often rely on a few helper types and methods to wrap important logic.</span></span> <span data-ttu-id="8ec42-339">Poiché le misure vengono cancellate in `float[]` fase di esecuzione, è possibile utilizzare un tipo come tipo cancellato per una riga.</span><span class="sxs-lookup"><span data-stu-id="8ec42-339">Because measures are erased at runtime, you can use a `float[]` as the erased type for a row.</span></span> <span data-ttu-id="8ec42-340">Il compilatore considererà colonne diverse come con tipi di misura diversi.</span><span class="sxs-lookup"><span data-stu-id="8ec42-340">The compiler will treat different columns as having different measure types.</span></span> <span data-ttu-id="8ec42-341">Ad esempio, la prima colonna `float<meter>`dell'esempio include `float<second>`type e la seconda con .</span><span class="sxs-lookup"><span data-stu-id="8ec42-341">For example, the first column in our example has type `float<meter>`, and the second has `float<second>`.</span></span> <span data-ttu-id="8ec42-342">Tuttavia, la rappresentazione cancellata può rimanere abbastanza semplice.</span><span class="sxs-lookup"><span data-stu-id="8ec42-342">However, the erased representation can remain quite simple.</span></span>

<span data-ttu-id="8ec42-343">Il codice seguente mostra il nucleo dell'implementazione.</span><span class="sxs-lookup"><span data-stu-id="8ec42-343">The following code shows the core of the implementation.</span></span>

```fsharp
// Simple type wrapping CSV data
type CsvFile(filename) =
    // Cache the sequence of all data lines (all lines but the first)
    let data =
        seq {
            for line in File.ReadAllLines(filename) |> Seq.skip 1 ->
                line.Split(',') |> Array.map float
        }
        |> Seq.cache
    member _.Data = data

[<TypeProvider>]
type public MiniCsvProvider(cfg:TypeProviderConfig) as this =
    inherit TypeProviderForNamespaces(cfg)

    // Get the assembly and namespace used to house the provided types.
    let asm = System.Reflection.Assembly.GetExecutingAssembly()
    let ns = "Samples.FSharp.MiniCsvProvider"

    // Create the main provided type.
    let csvTy = ProvidedTypeDefinition(asm, ns, "MiniCsv", Some(typeof<obj>))

    // Parameterize the type by the file to use as a template.
    let filename = ProvidedStaticParameter("filename", typeof<string>)
    do csvTy.DefineStaticParameters([filename], fun tyName [| :? string as filename |] ->

        // Resolve the filename relative to the resolution folder.
        let resolvedFilename = Path.Combine(cfg.ResolutionFolder, filename)

        // Get the first line from the file.
        let headerLine = File.ReadLines(resolvedFilename) |> Seq.head

        // Define a provided type for each row, erasing to a float[].
        let rowTy = ProvidedTypeDefinition("Row", Some(typeof<float[]>))

        // Extract header names from the file, splitting on commas.
        // use Regex matching to get the position in the row at which the field occurs
        let headers = Regex.Matches(headerLine, "[^,]+")

        // Add one property per CSV field.
        for i in 0 .. headers.Count - 1 do
            let headerText = headers.[i].Value

            // Try to decompose this header into a name and unit.
            let fieldName, fieldTy =
                let m = Regex.Match(headerText, @"(?<field>.+) \((?<unit>.+)\)")
                if m.Success then

                    let unitName = m.Groups.["unit"].Value
                    let units = ProvidedMeasureBuilder.Default.SI unitName
                    m.Groups.["field"].Value, ProvidedMeasureBuilder.Default.AnnotateType(typeof<float>,[units])

                else
                    // no units, just treat it as a normal float
                    headerText, typeof<float>

            let prop =
                ProvidedProperty(fieldName, fieldTy,
                    getterCode = fun [row] -> <@@ (%%row:float[]).[i] @@>)

            // Add metadata that defines the property's location in the referenced file.
            prop.AddDefinitionLocation(1, headers.[i].Index + 1, filename)
            rowTy.AddMember(prop)

        // Define the provided type, erasing to CsvFile.
        let ty = ProvidedTypeDefinition(asm, ns, tyName, Some(typeof<CsvFile>))

        // Add a parameterless constructor that loads the file that was used to define the schema.
        let ctor0 =
            ProvidedConstructor([],
                invokeCode = fun [] -> <@@ CsvFile(resolvedFilename) @@>)
        ty.AddMember ctor0

        // Add a constructor that takes the file name to load.
        let ctor1 = ProvidedConstructor([ProvidedParameter("filename", typeof<string>)],
            invokeCode = fun [filename] -> <@@ CsvFile(%%filename) @@>)
        ty.AddMember ctor1

        // Add a more strongly typed Data property, which uses the existing property at runtime.
        let prop =
            ProvidedProperty("Data", typedefof<seq<_>>.MakeGenericType(rowTy),
                getterCode = fun [csvFile] -> <@@ (%%csvFile:CsvFile).Data @@>)
        ty.AddMember prop

        // Add the row type as a nested type.
        ty.AddMember rowTy
        ty)

    // Add the type to the namespace.
    do this.AddNamespace(ns, [csvTy])
```

<span data-ttu-id="8ec42-344">Tenere presente i punti seguenti sull'implementazione:Note the following points about the implementation:</span><span class="sxs-lookup"><span data-stu-id="8ec42-344">Note the following points about the implementation:</span></span>

- <span data-ttu-id="8ec42-345">I costruttori di overload consentono di leggere il file originale o uno con uno schema identico.</span><span class="sxs-lookup"><span data-stu-id="8ec42-345">Overloaded constructors allow either the original file or one that has an identical schema to be read.</span></span> <span data-ttu-id="8ec42-346">Questo modello è comune quando si scrive un provider di tipi per origini dati locali o remote e questo modello consente di usare un file locale come modello per i dati remoti.</span><span class="sxs-lookup"><span data-stu-id="8ec42-346">This pattern is common when you write a type provider for local or remote data sources, and this pattern allows a local file to be used as the template for remote data.</span></span>

- <span data-ttu-id="8ec42-347">È possibile utilizzare il valore [TypeProviderConfig](https://msdn.microsoft.com/library/1cda7b9a-3d07-475d-9315-d65e1c97eb44) passato al costruttore del provider di tipi per risolvere i nomi di file relativi.</span><span class="sxs-lookup"><span data-stu-id="8ec42-347">You can use the [TypeProviderConfig](https://msdn.microsoft.com/library/1cda7b9a-3d07-475d-9315-d65e1c97eb44) value that’s passed in to the type provider constructor to resolve relative file names.</span></span>

- <span data-ttu-id="8ec42-348">È possibile `AddDefinitionLocation` utilizzare il metodo per definire la posizione delle proprietà fornite.</span><span class="sxs-lookup"><span data-stu-id="8ec42-348">You can use the `AddDefinitionLocation` method to define the location of the provided properties.</span></span> <span data-ttu-id="8ec42-349">Pertanto, se `Go To Definition` si utilizza su una proprietà fornita, il file CSV verrà aperto in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="8ec42-349">Therefore, if you use `Go To Definition` on a provided property, the CSV file will open in Visual Studio.</span></span>

- <span data-ttu-id="8ec42-350">È possibile `ProvidedMeasureBuilder` utilizzare il tipo per cercare le `float<_>` unità SI e per generare i tipi pertinenti.</span><span class="sxs-lookup"><span data-stu-id="8ec42-350">You can use the `ProvidedMeasureBuilder` type to look up the SI units and to generate the relevant `float<_>` types.</span></span>

### <a name="key-lessons"></a><span data-ttu-id="8ec42-351">Lezioni chiave</span><span class="sxs-lookup"><span data-stu-id="8ec42-351">Key Lessons</span></span>

<span data-ttu-id="8ec42-352">In questa sezione è stato illustrato come creare un provider di tipi per un'origine dati locale con uno schema semplice contenuto nell'origine dati stessa.</span><span class="sxs-lookup"><span data-stu-id="8ec42-352">This section explained how to create a type provider for a local data source with a simple schema that's contained in the data source itself.</span></span>

## <a name="going-further"></a><span data-ttu-id="8ec42-353">Approfondimenti</span><span class="sxs-lookup"><span data-stu-id="8ec42-353">Going Further</span></span>

<span data-ttu-id="8ec42-354">Le sezioni seguenti includono suggerimenti per ulteriori studi.</span><span class="sxs-lookup"><span data-stu-id="8ec42-354">The following sections include suggestions for further study.</span></span>

### <a name="a-look-at-the-compiled-code-for-erased-types"></a><span data-ttu-id="8ec42-355">Uno sguardo al codice compilato per i tipi cancellati</span><span class="sxs-lookup"><span data-stu-id="8ec42-355">A Look at the Compiled Code for Erased Types</span></span>

<span data-ttu-id="8ec42-356">Per fornire un'idea di come l'utilizzo del provider di tipi corrisponde al codice generato, esaminare la funzione seguente utilizzando l'oggetto `HelloWorldTypeProvider` utilizzato in precedenza in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="8ec42-356">To give you some idea of how the use of the type provider corresponds to the code that's emitted, look at the following function by using the `HelloWorldTypeProvider` that's used earlier in this topic.</span></span>

```fsharp
let function1 () =
    let obj1 = Samples.HelloWorldTypeProvider.Type1("some data")
    obj1.InstanceProperty
```

<span data-ttu-id="8ec42-357">Di seguito è riportata un'immagine del codice risultante decompilato utilizzando ildasm.exe:</span><span class="sxs-lookup"><span data-stu-id="8ec42-357">Here’s an image of the resulting code decompiled by using ildasm.exe:</span></span>

```il
.class public abstract auto ansi sealed Module1
extends [mscorlib]System.Object
{
.custom instance void [FSharp.Core]Microsoft.FSharp.Core.CompilationMappingAtt
ribute::.ctor(valuetype [FSharp.Core]Microsoft.FSharp.Core.SourceConstructFlags)
= ( 01 00 07 00 00 00 00 00 )
.method public static int32  function1() cil managed
{
// Code size       24 (0x18)
.maxstack  3
.locals init ([0] object obj1)
IL_0000:  nop
IL_0001:  ldstr      "some data"
IL_0006:  unbox.any  [mscorlib]System.Object
IL_000b:  stloc.0
IL_000c:  ldloc.0
IL_000d:  call       !!0 [FSharp.Core_2]Microsoft.FSharp.Core.LanguagePrimit
ives/IntrinsicFunctions::UnboxGeneric<string>(object)
IL_0012:  callvirt   instance int32 [mscorlib_3]System.String::get_Length()
IL_0017:  ret
} // end of method Module1::function1

} // end of class Module1
```

<span data-ttu-id="8ec42-358">Come illustrato nell'esempio, tutte `Type1` le `InstanceProperty` menzioni del tipo e della proprietà sono state cancellate, lasciando solo le operazioni sui tipi di runtime coinvolti.</span><span class="sxs-lookup"><span data-stu-id="8ec42-358">As the example shows, all mentions of the type `Type1` and the `InstanceProperty` property have been erased, leaving only operations on the runtime types involved.</span></span>

### <a name="design-and-naming-conventions-for-type-providers"></a><span data-ttu-id="8ec42-359">Convenzioni di progettazione e denominazione per i provider di tipiDesign and Naming Conventions for Type Providers</span><span class="sxs-lookup"><span data-stu-id="8ec42-359">Design and Naming Conventions for Type Providers</span></span>

<span data-ttu-id="8ec42-360">Quando si creano provider di tipi, osservare le convenzioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="8ec42-360">Observe the following conventions when authoring type providers.</span></span>

<span data-ttu-id="8ec42-361">**Provider per protocolli di connettività** In generale, i nomi della maggior parte delle DLL del provider per i protocolli `TypeProvider` di `TypeProviders`connettività dei dati e dei servizi, ad esempio le connessioni OData o SQL, devono terminare con o .</span><span class="sxs-lookup"><span data-stu-id="8ec42-361">**Providers for Connectivity Protocols** In general, names of most provider DLLs for data and service connectivity protocols, such as OData or SQL connections, should end in `TypeProvider` or `TypeProviders`.</span></span> <span data-ttu-id="8ec42-362">Ad esempio, utilizzare un nome di DLL analogo alla stringa seguente:</span><span class="sxs-lookup"><span data-stu-id="8ec42-362">For example, use a DLL name that resembles the following string:</span></span>

`Fabrikam.Management.BasicTypeProviders.dll`

<span data-ttu-id="8ec42-363">Assicurarsi che i tipi forniti siano membri dello spazio dei nomi corrispondente e indicare il protocollo di connettività implementato:</span><span class="sxs-lookup"><span data-stu-id="8ec42-363">Ensure that your provided types are members of the corresponding namespace, and indicate the connectivity protocol that you implemented:</span></span>

```fsharp
  Fabrikam.Management.BasicTypeProviders.WmiConnection<…>
  Fabrikam.Management.BasicTypeProviders.DataProtocolConnection<…>
```

<span data-ttu-id="8ec42-364">**Fornitori di utilità per la codifica generale**.</span><span class="sxs-lookup"><span data-stu-id="8ec42-364">**Utility Providers for General Coding**.</span></span>  <span data-ttu-id="8ec42-365">Per un provider di tipi di utilità come quello per le espressioni regolari, il provider di tipi può far parte di una libreria di base, come illustrato nell'esempio seguente:For a utility type provider such as that for regular expressions, the type provider may be part of a base library, as the following example shows:</span><span class="sxs-lookup"><span data-stu-id="8ec42-365">For a utility type provider such as that for regular expressions, the type provider may be part of a base library, as the following example shows:</span></span>

```fsharp
#r "Fabrikam.Core.Text.Utilities.dll"
```

<span data-ttu-id="8ec42-366">In questo caso, il tipo fornito verrà visualizzato in un punto appropriato in base alle normali convenzioni di progettazione .NET:In this case, the provided type would appear at an appropriate point according to normal .NET design conventions:</span><span class="sxs-lookup"><span data-stu-id="8ec42-366">In this case, the provided type would appear at an appropriate point according to normal .NET design conventions:</span></span>

```fsharp
  open Fabrikam.Core.Text.RegexTyped

  let regex = new RegexTyped<"a+b+a+b+">()
```

<span data-ttu-id="8ec42-367">**Origini dati Singleton**.</span><span class="sxs-lookup"><span data-stu-id="8ec42-367">**Singleton Data Sources**.</span></span> <span data-ttu-id="8ec42-368">Alcuni provider di tipi si connettono a una singola origine dati dedicata e forniscono solo dati.</span><span class="sxs-lookup"><span data-stu-id="8ec42-368">Some type providers connect to a single dedicated data source and provide only data.</span></span> <span data-ttu-id="8ec42-369">In questo caso, è `TypeProvider` necessario eliminare il suffisso e utilizzare le normali convenzioni per la denominazione .NET:In this case, you should drop the suffix and use normal conventions for .NET naming:</span><span class="sxs-lookup"><span data-stu-id="8ec42-369">In this case, you should drop the `TypeProvider` suffix and use normal conventions for .NET naming:</span></span>

```fsharp
#r "Fabrikam.Data.Freebase.dll"

let data = Fabrikam.Data.Freebase.Astronomy.Asteroids
```

<span data-ttu-id="8ec42-370">Per altre informazioni, `GetConnection` vedere la convenzione di progettazione descritta più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="8ec42-370">For more information, see the `GetConnection` design convention that's described later in this topic.</span></span>

### <a name="design-patterns-for-type-providers"></a><span data-ttu-id="8ec42-371">Modelli di progettazione per i provider di tipiDesign Patterns for Type Providers</span><span class="sxs-lookup"><span data-stu-id="8ec42-371">Design Patterns for Type Providers</span></span>

<span data-ttu-id="8ec42-372">Nelle sezioni seguenti vengono descritti i modelli di progettazione che è possibile utilizzare per la creazione di provider di tipi.</span><span class="sxs-lookup"><span data-stu-id="8ec42-372">The following sections describe design patterns you can use when authoring type providers.</span></span>

#### <a name="the-getconnection-design-pattern"></a><span data-ttu-id="8ec42-373">Il modello di progettazione GetConnectionThe GetConnection Design Pattern</span><span class="sxs-lookup"><span data-stu-id="8ec42-373">The GetConnection Design Pattern</span></span>

<span data-ttu-id="8ec42-374">La maggior parte dei provider `GetConnection` di tipi deve essere scritta per utilizzare il modello utilizzato dai provider di tipi in FSharp.Data.TypeProviders.dll, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="8ec42-374">Most type providers should be written to use the `GetConnection` pattern that's used by the type providers in FSharp.Data.TypeProviders.dll, as the following example shows:</span></span>

```fsharp
#r "Fabrikam.Data.WebDataStore.dll"

type Service = Fabrikam.Data.WebDataStore<…static connection parameters…>

let connection = Service.GetConnection(…dynamic connection parameters…)

let data = connection.Astronomy.Asteroids
```

#### <a name="type-providers-backed-by-remote-data-and-services"></a><span data-ttu-id="8ec42-375">Provider di tipi supportati da servizi e dati remotiType Providers Backed By Remote Data and Services</span><span class="sxs-lookup"><span data-stu-id="8ec42-375">Type Providers Backed By Remote Data and Services</span></span>

<span data-ttu-id="8ec42-376">Prima di creare un provider di tipi supportato da dati e servizi remoti, è necessario considerare una serie di problemi inerenti alla programmazione connessa.</span><span class="sxs-lookup"><span data-stu-id="8ec42-376">Before you create a type provider that's backed by remote data and services, you must consider a range of issues that are inherent in connected programming.</span></span> <span data-ttu-id="8ec42-377">Questi problemi includono le considerazioni seguenti:These issues include the following considerations:</span><span class="sxs-lookup"><span data-stu-id="8ec42-377">These issues include the following considerations:</span></span>

- <span data-ttu-id="8ec42-378">mapping dello schema</span><span class="sxs-lookup"><span data-stu-id="8ec42-378">schema mapping</span></span>

- <span data-ttu-id="8ec42-379">liveness e invalidazione in presenza di modifica dello schema</span><span class="sxs-lookup"><span data-stu-id="8ec42-379">liveness and invalidation in the presence of schema change</span></span>

- <span data-ttu-id="8ec42-380">memorizzazione nella cache dello schema</span><span class="sxs-lookup"><span data-stu-id="8ec42-380">schema caching</span></span>

- <span data-ttu-id="8ec42-381">implementazioni asincrone delle operazioni di accesso ai dati</span><span class="sxs-lookup"><span data-stu-id="8ec42-381">asynchronous implementations of data access operations</span></span>

- <span data-ttu-id="8ec42-382">query di supporto, incluse le query LINQSupporting queries, including LINQ queries</span><span class="sxs-lookup"><span data-stu-id="8ec42-382">supporting queries, including LINQ queries</span></span>

- <span data-ttu-id="8ec42-383">credenziali e autenticazione</span><span class="sxs-lookup"><span data-stu-id="8ec42-383">credentials and authentication</span></span>

<span data-ttu-id="8ec42-384">In questo argomento non vengono esaminati ulteriormente questi problemi.</span><span class="sxs-lookup"><span data-stu-id="8ec42-384">This topic doesn't explore these issues further.</span></span>

### <a name="additional-authoring-techniques"></a><span data-ttu-id="8ec42-385">Tecniche di creazione aggiuntiveAdditional Authoring Techniques</span><span class="sxs-lookup"><span data-stu-id="8ec42-385">Additional Authoring Techniques</span></span>

<span data-ttu-id="8ec42-386">Quando si scrivono provider di tipi personalizzati, è possibile utilizzare le tecniche aggiuntive seguenti.</span><span class="sxs-lookup"><span data-stu-id="8ec42-386">When you write your own type providers, you might want to use the following additional techniques.</span></span>

### <a name="creating-types-and-members-on-demand"></a><span data-ttu-id="8ec42-387">Creazione di tipi e membri su richiestaCreating Types and Members On-Demand</span><span class="sxs-lookup"><span data-stu-id="8ec42-387">Creating Types and Members On-Demand</span></span>

<span data-ttu-id="8ec42-388">L'API ProvidedType ha ritardato le versioni di AddMember.</span><span class="sxs-lookup"><span data-stu-id="8ec42-388">The ProvidedType API has delayed versions of AddMember.</span></span>

```fsharp
  type ProvidedType =
      member AddMemberDelayed  : (unit -> MemberInfo)      -> unit
      member AddMembersDelayed : (unit -> MemberInfo list) -> unit
```

<span data-ttu-id="8ec42-389">Queste versioni vengono utilizzate per creare spazi su richiesta di tipi.</span><span class="sxs-lookup"><span data-stu-id="8ec42-389">These versions are used to create on-demand spaces of types.</span></span>

### <a name="providing-array-types-and-generic-type-instantiations"></a><span data-ttu-id="8ec42-390">Fornitura di tipi di matrice e istanze di tipi genericiProviding Array types and Generic Type Instantiations</span><span class="sxs-lookup"><span data-stu-id="8ec42-390">Providing Array types and Generic Type Instantiations</span></span>

<span data-ttu-id="8ec42-391">I membri forniti vengono forniti (le cui firme includono tipi di matrice, tipi `MakeArrayType` `MakePointerType`byref `MakeGenericType` e istanze di tipi generici) utilizzando le normali , , e in qualsiasi istanza di <xref:System.Type>, tra cui `ProvidedTypeDefinitions`.</span><span class="sxs-lookup"><span data-stu-id="8ec42-391">You make provided members (whose signatures include array types, byref types, and instantiations of generic types) by using the normal `MakeArrayType`, `MakePointerType`, and `MakeGenericType` on any instance of <xref:System.Type>, including `ProvidedTypeDefinitions`.</span></span>

> [!NOTE]
> <span data-ttu-id="8ec42-392">In alcuni casi potrebbe essere necessario `ProvidedTypeBuilder.MakeGenericType`utilizzare l'helper in .</span><span class="sxs-lookup"><span data-stu-id="8ec42-392">In some cases you may have to use the helper in `ProvidedTypeBuilder.MakeGenericType`.</span></span>  <span data-ttu-id="8ec42-393">Per ulteriori informazioni, vedere la [documentazione di Type Provider SDK.](https://github.com/fsprojects/FSharp.TypeProviders.SDK/blob/master/README.md#explicit-construction-of-code-makegenerictype-makegenericmethod-and-uncheckedquotations)</span><span class="sxs-lookup"><span data-stu-id="8ec42-393">See the [Type Provider SDK documentation](https://github.com/fsprojects/FSharp.TypeProviders.SDK/blob/master/README.md#explicit-construction-of-code-makegenerictype-makegenericmethod-and-uncheckedquotations) for more details.</span></span>

### <a name="providing-unit-of-measure-annotations"></a><span data-ttu-id="8ec42-394">Fornire annotazioni di unità di misura</span><span class="sxs-lookup"><span data-stu-id="8ec42-394">Providing Unit of Measure Annotations</span></span>

<span data-ttu-id="8ec42-395">L'API ProvidedTypes fornisce helper per fornire annotazioni di misura.</span><span class="sxs-lookup"><span data-stu-id="8ec42-395">The ProvidedTypes API provides helpers for providing measure annotations.</span></span> <span data-ttu-id="8ec42-396">Ad esempio, per `float<kg>`fornire il tipo , utilizzare il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="8ec42-396">For example, to provide the type `float<kg>`, use the following code:</span></span>

```fsharp
  let measures = ProvidedMeasureBuilder.Default
  let kg = measures.SI "kilogram"
  let m = measures.SI "meter"
  let float_kg = measures.AnnotateType(typeof<float>,[kg])
```

  <span data-ttu-id="8ec42-397">Per fornire `Nullable<decimal<kg/m^2>>`il tipo , utilizzare il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="8ec42-397">To provide the type `Nullable<decimal<kg/m^2>>`, use the following code:</span></span>

```fsharp
  let kgpm2 = measures.Ratio(kg, measures.Square m)
  let dkgpm2 = measures.AnnotateType(typeof<decimal>,[kgpm2])
  let nullableDecimal_kgpm2 = typedefof<System.Nullable<_>>.MakeGenericType [|dkgpm2 |]
```

### <a name="accessing-project-local-or-script-local-resources"></a><span data-ttu-id="8ec42-398">Accesso alle risorse locali o locali per gli script</span><span class="sxs-lookup"><span data-stu-id="8ec42-398">Accessing Project-Local or Script-Local Resources</span></span>

<span data-ttu-id="8ec42-399">A ogni istanza di un `TypeProviderConfig` provider di tipi può essere assegnato un valore durante la costruzione.</span><span class="sxs-lookup"><span data-stu-id="8ec42-399">Each instance of a type provider can be given a `TypeProviderConfig` value during construction.</span></span> <span data-ttu-id="8ec42-400">Questo valore contiene la "cartella di risoluzione" per il provider, ovvero la cartella del progetto per la compilazione o la directory che contiene uno script, l'elenco degli assembly a cui si fa riferimento e altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="8ec42-400">This value contains the "resolution folder" for the provider (that is, the project folder for the compilation or the directory that contains a script), the list of referenced assemblies, and other information.</span></span>

### <a name="invalidation"></a><span data-ttu-id="8ec42-401">Invalidazione</span><span class="sxs-lookup"><span data-stu-id="8ec42-401">Invalidation</span></span>

<span data-ttu-id="8ec42-402">I provider possono generare segnali di invalidamento per notificare al servizio di linguaggio F , che i presupposti dello schema potrebbero essere stati modificati.</span><span class="sxs-lookup"><span data-stu-id="8ec42-402">Providers can raise invalidation signals to notify the F# language service that the schema assumptions may have changed.</span></span> <span data-ttu-id="8ec42-403">Quando si verifica l'invalidazione, un controllo dei tipi viene rifatto se il provider è ospitato in Visual Studio.When invalidation occurs, a typecheck is redone if the provider is being hosted in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="8ec42-403">When invalidation occurs, a typecheck is redone if the provider is being hosted in Visual Studio.</span></span> <span data-ttu-id="8ec42-404">Questo segnale verrà ignorato quando il provider è ospitato in F , Interactive o dal compilatore F , fsc.exe .</span><span class="sxs-lookup"><span data-stu-id="8ec42-404">This signal will be ignored when the provider is hosted in F# Interactive or by the F# Compiler (fsc.exe).</span></span>

### <a name="caching-schema-information"></a><span data-ttu-id="8ec42-405">Memorizzazione nella cache delle informazioni sullo schemaCaching Schema Information</span><span class="sxs-lookup"><span data-stu-id="8ec42-405">Caching Schema Information</span></span>

<span data-ttu-id="8ec42-406">I provider devono spesso memorizzare nella cache l'accesso alle informazioni sullo schema.</span><span class="sxs-lookup"><span data-stu-id="8ec42-406">Providers must often cache access to schema information.</span></span> <span data-ttu-id="8ec42-407">I dati memorizzati nella cache devono essere archiviati utilizzando un nome di file specificato come parametro statico o come dati utente.</span><span class="sxs-lookup"><span data-stu-id="8ec42-407">The cached data should be stored by using a file name that's given as a static parameter or as user data.</span></span> <span data-ttu-id="8ec42-408">Un esempio di memorizzazione `LocalSchemaFile` nella cache dello `FSharp.Data.TypeProviders` schema è il parametro nei provider di tipi nell'assembly.</span><span class="sxs-lookup"><span data-stu-id="8ec42-408">An example of schema caching is the `LocalSchemaFile` parameter in the type providers in the `FSharp.Data.TypeProviders` assembly.</span></span> <span data-ttu-id="8ec42-409">Nell'implementazione di questi provider, questo parametro statico indica al provider di tipi di utilizzare le informazioni sullo schema nel file locale specificato anziché accedere all'origine dati in rete.</span><span class="sxs-lookup"><span data-stu-id="8ec42-409">In the implementation of these providers, this static parameter directs the type provider to use the schema information in the specified local file instead of accessing the data source over the network.</span></span> <span data-ttu-id="8ec42-410">Per utilizzare le informazioni sullo schema memorizzate nella cache, è inoltre necessario impostare il parametro `ForceUpdate` static su `false`.</span><span class="sxs-lookup"><span data-stu-id="8ec42-410">To use cached schema information, you must also set the static parameter `ForceUpdate` to `false`.</span></span> <span data-ttu-id="8ec42-411">È possibile utilizzare una tecnica simile per abilitare l'accesso ai dati online e offline.</span><span class="sxs-lookup"><span data-stu-id="8ec42-411">You could use a similar technique to enable online and offline data access.</span></span>

### <a name="backing-assembly"></a><span data-ttu-id="8ec42-412">Assemblaggio di backup</span><span class="sxs-lookup"><span data-stu-id="8ec42-412">Backing Assembly</span></span>

<span data-ttu-id="8ec42-413">Quando si `.dll` compila `.exe` un file o , il file DLL di backup per i tipi generati viene collegato in modo statico all'assembly risultante.</span><span class="sxs-lookup"><span data-stu-id="8ec42-413">When you compile a `.dll` or `.exe` file, the backing .dll file for generated types is statically linked into the resulting assembly.</span></span> <span data-ttu-id="8ec42-414">Questo collegamento viene creato copiando le definizioni di tipo IL (Intermediate Language) e tutte le risorse gestite dall'assembly di backup nell'assembly finale.</span><span class="sxs-lookup"><span data-stu-id="8ec42-414">This link is created by copying the Intermediate Language (IL) type definitions and any managed resources from the backing assembly into the final assembly.</span></span> <span data-ttu-id="8ec42-415">Quando si utilizza f , il file DLL di backup non viene copiato e viene invece caricato direttamente nel processo interattivo di F.</span><span class="sxs-lookup"><span data-stu-id="8ec42-415">When you use F# Interactive, the backing .dll file isn't copied and is instead loaded directly into the F# Interactive process.</span></span>

### <a name="exceptions-and-diagnostics-from-type-providers"></a><span data-ttu-id="8ec42-416">Eccezioni e diagnostica dai provider di tipiExceptions and Diagnostics from Type Providers</span><span class="sxs-lookup"><span data-stu-id="8ec42-416">Exceptions and Diagnostics from Type Providers</span></span>

<span data-ttu-id="8ec42-417">Tutti gli utilizzi di tutti i membri dai tipi forniti possono generare eccezioni.</span><span class="sxs-lookup"><span data-stu-id="8ec42-417">All uses of all members from provided types may throw exceptions.</span></span> <span data-ttu-id="8ec42-418">In tutti i casi, se un provider di tipi genera un'eccezione, il compilatore host attribuisce l'errore a un provider di tipi specifico.</span><span class="sxs-lookup"><span data-stu-id="8ec42-418">In all cases, if a type provider throws an exception, the host compiler attributes the error to a specific type provider.</span></span>

- <span data-ttu-id="8ec42-419">Le eccezioni del provider di tipi non devono mai generare errori interni del compilatore.</span><span class="sxs-lookup"><span data-stu-id="8ec42-419">Type provider exceptions should never result in internal compiler errors.</span></span>

- <span data-ttu-id="8ec42-420">I provider di tipi non possono segnalare avvisi.</span><span class="sxs-lookup"><span data-stu-id="8ec42-420">Type providers can't report warnings.</span></span>

- <span data-ttu-id="8ec42-421">Quando un provider di tipi è ospitato nel compilatore F , in un ambiente di sviluppo F , o interattivo F , vengono rilevate tutte le eccezioni da tale provider.</span><span class="sxs-lookup"><span data-stu-id="8ec42-421">When a type provider is hosted in the F# compiler, an F# development environment, or F# Interactive, all exceptions from that provider are caught.</span></span> <span data-ttu-id="8ec42-422">Il Message proprietà è sempre il testo dell'errore e non viene visualizzata alcuna traccia dello stack.</span><span class="sxs-lookup"><span data-stu-id="8ec42-422">The Message property is always the error text, and no stack trace appears.</span></span> <span data-ttu-id="8ec42-423">Se si intende generare un'eccezione, è `System.NotSupportedException`possibile `System.IO.IOException` `System.Exception`generare gli esempi seguenti: , , .</span><span class="sxs-lookup"><span data-stu-id="8ec42-423">If you’re going to throw an exception, you can throw the following examples: `System.NotSupportedException`, `System.IO.IOException`, `System.Exception`.</span></span>

#### <a name="providing-generated-types"></a><span data-ttu-id="8ec42-424">Fornire tipi generati</span><span class="sxs-lookup"><span data-stu-id="8ec42-424">Providing Generated Types</span></span>

<span data-ttu-id="8ec42-425">Finora, questo documento ha spiegato come fornire i tipi cancellati.</span><span class="sxs-lookup"><span data-stu-id="8ec42-425">So far, this document has explained how to provide erased types.</span></span> <span data-ttu-id="8ec42-426">È anche possibile usare il meccanismo del provider di tipi in F , per fornire i tipi generati, che vengono aggiunti come definizioni di tipo .NET reali nel programma degli utenti.</span><span class="sxs-lookup"><span data-stu-id="8ec42-426">You can also use the type provider mechanism in F# to provide generated types, which are added as real .NET type definitions into the users' program.</span></span> <span data-ttu-id="8ec42-427">È necessario fare riferimento ai tipi forniti generati utilizzando una definizione di tipo.</span><span class="sxs-lookup"><span data-stu-id="8ec42-427">You must refer to generated provided types by using a type definition.</span></span>

```fsharp
open Microsoft.FSharp.TypeProviders

type Service = ODataService<"http://services.odata.org/Northwind/Northwind.svc/">
```

<span data-ttu-id="8ec42-428">Il codice helper ProvidedTypes-0.2 che fa parte della versione di F .</span><span class="sxs-lookup"><span data-stu-id="8ec42-428">The ProvidedTypes-0.2 helper code that is part of the F# 3.0 release has only limited support for providing generated types.</span></span> <span data-ttu-id="8ec42-429">Le istruzioni seguenti devono essere true per una definizione di tipo generata:The following statements must be true for a generated type definition:</span><span class="sxs-lookup"><span data-stu-id="8ec42-429">The following statements must be true for a generated type definition:</span></span>

- <span data-ttu-id="8ec42-430">`isErased` deve essere impostato su `false`.</span><span class="sxs-lookup"><span data-stu-id="8ec42-430">`isErased` must be set to `false`.</span></span>

- <span data-ttu-id="8ec42-431">Il tipo generato deve essere `ProvidedAssembly()`aggiunto a un oggetto appena costruito, che rappresenta un contenitore per i frammenti di codice generati.</span><span class="sxs-lookup"><span data-stu-id="8ec42-431">The generated type must be added to a newly constructed `ProvidedAssembly()`, which represents a container for generated code fragments.</span></span>

- <span data-ttu-id="8ec42-432">Il provider deve disporre di un assembly che dispone di un file .dll .NET di backup effettivo con un file DLL corrispondente su disco.</span><span class="sxs-lookup"><span data-stu-id="8ec42-432">The provider must have an assembly that has an actual backing .NET .dll file with a matching .dll file on disk.</span></span>

## <a name="rules-and-limitations"></a><span data-ttu-id="8ec42-433">Regole e limitazioni</span><span class="sxs-lookup"><span data-stu-id="8ec42-433">Rules and Limitations</span></span>

<span data-ttu-id="8ec42-434">Quando si scrivono provider di tipi, tenere presenti le regole e le limitazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="8ec42-434">When you write type providers, keep the following rules and limitations in mind.</span></span>

### <a name="provided-types-must-be-reachable"></a><span data-ttu-id="8ec42-435">I tipi forniti devono essere raggiungibili</span><span class="sxs-lookup"><span data-stu-id="8ec42-435">Provided types must be reachable</span></span>

<span data-ttu-id="8ec42-436">Tutti i tipi forniti devono essere raggiungibili dai tipi non annidati.</span><span class="sxs-lookup"><span data-stu-id="8ec42-436">All provided types should be reachable from the non-nested types.</span></span> <span data-ttu-id="8ec42-437">I tipi non annidati vengono forniti `TypeProviderForNamespaces` nella chiamata `AddNamespace`al costruttore o in una chiamata a .</span><span class="sxs-lookup"><span data-stu-id="8ec42-437">The non-nested types are given in the call to the `TypeProviderForNamespaces` constructor or a call to `AddNamespace`.</span></span> <span data-ttu-id="8ec42-438">Ad esempio, se il `StaticClass.P : T`provider fornisce un tipo , è necessario assicurarsi che T sia un tipo non annidato o annidato sotto uno.</span><span class="sxs-lookup"><span data-stu-id="8ec42-438">For example, if the provider provides a type `StaticClass.P : T`, you must ensure that T is either a non-nested type or nested under one.</span></span>

<span data-ttu-id="8ec42-439">Ad esempio, alcuni provider hanno `DataTypes` una classe `T1, T2, T3, ...` statica, ad esempio che contengono questi tipi.</span><span class="sxs-lookup"><span data-stu-id="8ec42-439">For example, some providers have a static class such as `DataTypes` that contain these `T1, T2, T3, ...` types.</span></span> <span data-ttu-id="8ec42-440">In caso contrario, l'errore indica che è stato trovato un riferimento al tipo T nell'assembly A, ma il tipo non è stato trovato in tale assembly.</span><span class="sxs-lookup"><span data-stu-id="8ec42-440">Otherwise, the error says that a reference to type T in assembly A was found, but the type couldn't be found in that assembly.</span></span> <span data-ttu-id="8ec42-441">Se viene visualizzato questo errore, verificare che tutti i sottotipi siano raggiungibili dai tipi di provider.</span><span class="sxs-lookup"><span data-stu-id="8ec42-441">If this error appears, verify that all your subtypes can be reached from the provider types.</span></span> <span data-ttu-id="8ec42-442">Nota: `T1, T2, T3...` questi tipi sono indicati come tipi *al volo.*</span><span class="sxs-lookup"><span data-stu-id="8ec42-442">Note: These `T1, T2, T3...` types are referred to as the *on-the-fly* types.</span></span> <span data-ttu-id="8ec42-443">Ricordarsi di inserirli in uno spazio dei nomi accessibile o in un tipo padre.</span><span class="sxs-lookup"><span data-stu-id="8ec42-443">Remember to put them in an accessible namespace or a parent type.</span></span>

### <a name="limitations-of-the-type-provider-mechanism"></a><span data-ttu-id="8ec42-444">Limitazioni del meccanismo del provider di tipi</span><span class="sxs-lookup"><span data-stu-id="8ec42-444">Limitations of the Type Provider Mechanism</span></span>

<span data-ttu-id="8ec42-445">Il meccanismo del provider di tipi in F , presenta le limitazioni seguenti:The type provider mechanism in F' has the following limitations:</span><span class="sxs-lookup"><span data-stu-id="8ec42-445">The type provider mechanism in F# has the following limitations:</span></span>

- <span data-ttu-id="8ec42-446">L'infrastruttura sottostante per i provider di tipi in F , non supporta i tipi generici forniti o i metodi generici forniti.</span><span class="sxs-lookup"><span data-stu-id="8ec42-446">The underlying infrastructure for type providers in F# doesn't support provided generic types or provided generic methods.</span></span>

- <span data-ttu-id="8ec42-447">Il meccanismo non supporta i tipi annidati con parametri statici.</span><span class="sxs-lookup"><span data-stu-id="8ec42-447">The mechanism doesn't support nested types with static parameters.</span></span>

## <a name="development-tips"></a><span data-ttu-id="8ec42-448">Suggerimenti per lo sviluppo</span><span class="sxs-lookup"><span data-stu-id="8ec42-448">Development Tips</span></span>

<span data-ttu-id="8ec42-449">Durante il processo di sviluppo, è possibile trovare utili i suggerimenti seguenti:You might find the following tips helpful during the development process:</span><span class="sxs-lookup"><span data-stu-id="8ec42-449">You might find the following tips helpful during the development process:</span></span>

### <a name="run-two-instances-of-visual-studio"></a><span data-ttu-id="8ec42-450">Eseguire due istanze di Visual StudioRun two instances of Visual Studio</span><span class="sxs-lookup"><span data-stu-id="8ec42-450">Run two instances of Visual Studio</span></span>

<span data-ttu-id="8ec42-451">È possibile sviluppare il provider di tipi in un'istanza e testare il provider nell'altra perché l'IDE di test accetta un blocco sul file DLL che impedisce la ricompilazione del provider di tipi.</span><span class="sxs-lookup"><span data-stu-id="8ec42-451">You can develop the type provider in one instance and test the provider in the other because the test IDE will take a lock on the .dll file that prevents the type provider from being rebuilt.</span></span> <span data-ttu-id="8ec42-452">Pertanto, è necessario chiudere la seconda istanza di Visual Studio mentre il provider è compilato nella prima istanza e quindi è necessario riaprire la seconda istanza dopo la compilazione del provider.</span><span class="sxs-lookup"><span data-stu-id="8ec42-452">Thus, you must close the second instance of Visual Studio while the provider is built in the first instance, and then you must reopen the second instance after the provider is built.</span></span>

### <a name="debug-type-providers-by-using-invocations-of-fscexe"></a><span data-ttu-id="8ec42-453">Eseguire il debug dei provider di tipi utilizzando le chiamate di fsc.exe</span><span class="sxs-lookup"><span data-stu-id="8ec42-453">Debug type providers by using invocations of fsc.exe</span></span>

<span data-ttu-id="8ec42-454">È possibile richiamare i provider di tipi utilizzando gli strumenti seguenti:You can invoke type providers by using the following tools:</span><span class="sxs-lookup"><span data-stu-id="8ec42-454">You can invoke type providers by using the following tools:</span></span>

- <span data-ttu-id="8ec42-455">fsc.exe (Compilatore da riga di comando F)</span><span class="sxs-lookup"><span data-stu-id="8ec42-455">fsc.exe (The F# command line compiler)</span></span>

- <span data-ttu-id="8ec42-456">fsi.exe (Compilatore interattivo F)</span><span class="sxs-lookup"><span data-stu-id="8ec42-456">fsi.exe (The F# Interactive compiler)</span></span>

- <span data-ttu-id="8ec42-457">devenv.exe (Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="8ec42-457">devenv.exe (Visual Studio)</span></span>

<span data-ttu-id="8ec42-458">È spesso possibile eseguire il debug dei provider di tipi più facilmente utilizzando fsc.exe in un file script di test, ad esempio script.fsx.</span><span class="sxs-lookup"><span data-stu-id="8ec42-458">You can often debug type providers most easily by using fsc.exe on a test script file (for example, script.fsx).</span></span> <span data-ttu-id="8ec42-459">È possibile avviare un debugger da un prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="8ec42-459">You can launch a debugger from a command prompt.</span></span>

```console
devenv /debugexe fsc.exe script.fsx
```

  <span data-ttu-id="8ec42-460">È possibile utilizzare la registrazione da stampa a stdout.</span><span class="sxs-lookup"><span data-stu-id="8ec42-460">You can use print-to-stdout logging.</span></span>

## <a name="see-also"></a><span data-ttu-id="8ec42-461">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8ec42-461">See also</span></span>

- [<span data-ttu-id="8ec42-462">Provider di tipi</span><span class="sxs-lookup"><span data-stu-id="8ec42-462">Type Providers</span></span>](index.md)
- [<span data-ttu-id="8ec42-463">SDK del provider di tipi</span><span class="sxs-lookup"><span data-stu-id="8ec42-463">The Type Provider SDK</span></span>](https://github.com/fsprojects/FSharp.TypeProviders.SDK)

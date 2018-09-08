---
title: 'Esercitazione: Creare un Provider di tipi (F #)'
description: 'Informazioni su come creare il proprio provider di tipi F # in F # 3.0 esaminando i diversi provider di tipo semplice per illustrare i concetti di base.'
ms.date: 05/16/2016
ms.openlocfilehash: 3c998377b2c3a408d536ef416f3799bf7f04b6bd
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/08/2018
ms.locfileid: "44212321"
---
# <a name="tutorial-create-a-type-provider"></a><span data-ttu-id="d58bc-103">Esercitazione: Creare un Provider di tipi</span><span class="sxs-lookup"><span data-stu-id="d58bc-103">Tutorial: Create a Type Provider</span></span>

<span data-ttu-id="d58bc-104">Il meccanismo di provider in F # è una parte significativa del supporto per la programmazione avanzata di informazioni.</span><span class="sxs-lookup"><span data-stu-id="d58bc-104">The type provider mechanism in F# is a significant part of its support for information rich programming.</span></span> <span data-ttu-id="d58bc-105">Questa esercitazione illustra come creare il proprio provider di tipi attraverso lo sviluppo di diversi provider di tipo semplice per illustrare i concetti di base.</span><span class="sxs-lookup"><span data-stu-id="d58bc-105">This tutorial explains how to create your own type providers by walking you through the development of several simple type providers to illustrate the basic concepts.</span></span> <span data-ttu-id="d58bc-106">Per altre informazioni sul meccanismo di provider di tipo in F #, vedere [provider di tipi](index.md).</span><span class="sxs-lookup"><span data-stu-id="d58bc-106">For more information about the type provider mechanism in F#, see [Type Providers](index.md).</span></span>

<span data-ttu-id="d58bc-107">L'ecosistema di F # contiene una gamma di provider di tipi per uso comune Internet e enterprise data services.</span><span class="sxs-lookup"><span data-stu-id="d58bc-107">The F# ecosystem contains a range of type providers for commonly used Internet and enterprise data services.</span></span> <span data-ttu-id="d58bc-108">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="d58bc-108">For example:</span></span>

- <span data-ttu-id="d58bc-109">[FSharp](https://fsharp.github.io/FSharp.Data/) include il provider di tipi per formati di documenti JSON, XML, CSV e HTML.</span><span class="sxs-lookup"><span data-stu-id="d58bc-109">[FSharp.Data](https://fsharp.github.io/FSharp.Data/) includes type providers for JSON, XML, CSV and HTML document formats.</span></span>

- <span data-ttu-id="d58bc-110">[SQLProvider](https://fsprojects.github.io/SQLProvider/) fornisce accesso fortemente tipizzato ai database SQL tramite un mapping degli oggetti e LINQ F # le query su tali origini dati.</span><span class="sxs-lookup"><span data-stu-id="d58bc-110">[SQLProvider](https://fsprojects.github.io/SQLProvider/) provides strongly-typed access to SQL databases through a object mapping and F# LINQ queries against these data sources.</span></span>

- <span data-ttu-id="d58bc-111">[FSharp.Data.SqlClient](https://fsprojects.github.io/FSharp.Data.SqlClient/) dispone di un set di provider di tipi per la fase di compilazione selezionata incorporamento di T-SQL in F #.</span><span class="sxs-lookup"><span data-stu-id="d58bc-111">[FSharp.Data.SqlClient](https://fsprojects.github.io/FSharp.Data.SqlClient/) has a set of type providers for compile-time checked embedding of T-SQL in F#.</span></span>

- <span data-ttu-id="d58bc-112">[Typeproviders](https://fsprojects.github.io/FSharp.Data.TypeProviders/) è un precedente set di provider di tipi per l'uso solo con la programmazione di .NET Framework per l'accesso ai servizi di dati SQL, Entity Framework, OData e WSDL.</span><span class="sxs-lookup"><span data-stu-id="d58bc-112">[FSharp.Data.TypeProviders](https://fsprojects.github.io/FSharp.Data.TypeProviders/) is an older set of type providers for use only with .NET Framework programming for accessing SQL, Entity Framework, OData and WSDL data services.</span></span>

<span data-ttu-id="d58bc-113">Se necessario, è possibile creare provider di tipi personalizzati, oppure è possibile fare riferimento a provider di tipi creati da altri.</span><span class="sxs-lookup"><span data-stu-id="d58bc-113">Where necessary, you can create custom type providers, or you can reference type providers that others have created.</span></span> <span data-ttu-id="d58bc-114">Ad esempio, l'organizzazione potrebbe avere un servizio dati che fornisce un numero elevato e continuamente crescente di set di dati denominati, ciascuno con il proprio schema dati stabile.</span><span class="sxs-lookup"><span data-stu-id="d58bc-114">For example, your organization could have a data service that provides a large and growing number of named data sets, each with its own stable data schema.</span></span> <span data-ttu-id="d58bc-115">È possibile creare un provider di tipi che legge gli schemi e presenta i set di dati correnti per il programmatore in una modalità fortemente tipizzata.</span><span class="sxs-lookup"><span data-stu-id="d58bc-115">You can create a type provider that reads the schemas and presents the current data sets to the programmer in a strongly typed way.</span></span>

## <a name="before-you-start"></a><span data-ttu-id="d58bc-116">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="d58bc-116">Before You Start</span></span>

<span data-ttu-id="d58bc-117">Il meccanismo di provider è progettato principalmente per l'inserimento di dati stabili e spazi di informazioni del servizio nell'esperienza di programmazione F #.</span><span class="sxs-lookup"><span data-stu-id="d58bc-117">The type provider mechanism is primarily designed for injecting stable data and service information spaces into the F# programming experience.</span></span>

<span data-ttu-id="d58bc-118">Questo meccanismo non è progettato per l'inserimento di spazi di informazioni cui lo schema cambia durante l'esecuzione del programma in modi che sono rilevanti per la logica del programma.</span><span class="sxs-lookup"><span data-stu-id="d58bc-118">This mechanism isn’t designed for injecting information spaces whose schema changes during program execution in ways that are relevant to program logic.</span></span> <span data-ttu-id="d58bc-119">Inoltre, il meccanismo non è progettato per intra-language metaprogrammazione, anche se tale dominio contiene alcuni utilizzi validi.</span><span class="sxs-lookup"><span data-stu-id="d58bc-119">Also, the mechanism isn't designed for intra-language meta-programming, even though that domain contains some valid uses.</span></span> <span data-ttu-id="d58bc-120">È consigliabile usare questo meccanismo solo laddove necessario e in cui lo sviluppo di un provider di tipi produce un valore molto elevato.</span><span class="sxs-lookup"><span data-stu-id="d58bc-120">You should use this mechanism only where necessary and where the development of a type provider yields very high value.</span></span>

<span data-ttu-id="d58bc-121">È consigliabile evitare la scrittura di un provider di tipi in uno schema non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="d58bc-121">You should avoid writing a type provider where a schema isn't available.</span></span> <span data-ttu-id="d58bc-122">Analogamente, è consigliabile evitare la scrittura di un provider di tipi in cui un normale (o persino esistente) basterebbe libreria .NET.</span><span class="sxs-lookup"><span data-stu-id="d58bc-122">Likewise, you should avoid writing a type provider where an ordinary (or even an existing) .NET library would suffice.</span></span>

<span data-ttu-id="d58bc-123">Prima di iniziare, si potrebbero chiedere alle domande seguenti:</span><span class="sxs-lookup"><span data-stu-id="d58bc-123">Before you start, you might ask the following questions:</span></span>

- <span data-ttu-id="d58bc-124">Si hanno uno schema per l'origine di informazioni?</span><span class="sxs-lookup"><span data-stu-id="d58bc-124">Do you have a schema for your information source?</span></span> <span data-ttu-id="d58bc-125">In questo caso, qual è il mapping a F # e sistema di tipi .NET?</span><span class="sxs-lookup"><span data-stu-id="d58bc-125">If so, what’s the mapping into the F# and .NET type system?</span></span>

- <span data-ttu-id="d58bc-126">È possibile utilizzare un'API (tipizzata in modo dinamico) esistente come punto di partenza per l'implementazione?</span><span class="sxs-lookup"><span data-stu-id="d58bc-126">Can you use an existing (dynamically typed) API as a starting point for your implementation?</span></span>

- <span data-ttu-id="d58bc-127">E l'organizzazione avrà sufficiente utilizzi del provider del tipo per rendere la scrittura possono essere utili?</span><span class="sxs-lookup"><span data-stu-id="d58bc-127">Will you and your organization have enough uses of the type provider to make writing it worthwhile?</span></span> <span data-ttu-id="d58bc-128">Sarebbe una libreria.NET normale soddisfa le proprie esigenze?</span><span class="sxs-lookup"><span data-stu-id="d58bc-128">Would a normal .NET library meet your needs?</span></span>

- <span data-ttu-id="d58bc-129">Quanto verrà modificato lo schema?</span><span class="sxs-lookup"><span data-stu-id="d58bc-129">How much will your schema change?</span></span>

- <span data-ttu-id="d58bc-130">Verrà modificato durante la scrittura di codice?</span><span class="sxs-lookup"><span data-stu-id="d58bc-130">Will it change during coding?</span></span>

- <span data-ttu-id="d58bc-131">Verrà modificato tra le sessioni di codifica?</span><span class="sxs-lookup"><span data-stu-id="d58bc-131">Will it change between coding sessions?</span></span>

- <span data-ttu-id="d58bc-132">Verrà modificato durante l'esecuzione del programma?</span><span class="sxs-lookup"><span data-stu-id="d58bc-132">Will it change during program execution?</span></span>

<span data-ttu-id="d58bc-133">Provider di tipi sono particolarmente adatti alle situazioni in cui lo schema è stabile in fase di esecuzione e nel corso della durata del codice compilato.</span><span class="sxs-lookup"><span data-stu-id="d58bc-133">Type providers are best suited to situations where the schema is stable at runtime and during the lifetime of compiled code.</span></span>

## <a name="a-simple-type-provider"></a><span data-ttu-id="d58bc-134">Un Provider di tipi semplici</span><span class="sxs-lookup"><span data-stu-id="d58bc-134">A Simple Type Provider</span></span>

<span data-ttu-id="d58bc-135">Questo esempio è Samples. helloworldtypeprovider, simili agli esempi nel `examples` directory del [F # tipo Provider SDK](https://github.com/fsprojects/FSharp.TypeProviders.SDK/).</span><span class="sxs-lookup"><span data-stu-id="d58bc-135">This sample is Samples.HelloWorldTypeProvider, similar to the samples in the `examples` directory of the [F# Type Provider SDK](https://github.com/fsprojects/FSharp.TypeProviders.SDK/).</span></span> <span data-ttu-id="d58bc-136">Il provider rende disponibile un "spazio di tipo" che contiene 100 tipi cancellati, come illustrato nel codice seguente utilizzando sintassi della firma F # e omettendo i dettagli per tutti tranne `Type1`.</span><span class="sxs-lookup"><span data-stu-id="d58bc-136">The provider makes available a "type space" that contains 100 erased types, as the following code shows by using F# signature syntax and omitting the details for all except `Type1`.</span></span> <span data-ttu-id="d58bc-137">Per altre informazioni sui tipi cancellati, vedere [informazioni dettagliate sulle cancellati forniti tipi](#details-about-erased-provided-types) più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="d58bc-137">For more information about erased types, see [Details About Erased Provided Types](#details-about-erased-provided-types) later in this topic.</span></span>

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

<span data-ttu-id="d58bc-138">Si noti che il set di tipi e membri forniti sia noto staticamente.</span><span class="sxs-lookup"><span data-stu-id="d58bc-138">Note that the set of types and members provided is statically known.</span></span> <span data-ttu-id="d58bc-139">In questo esempio non sfrutta la possibilità di provider forniscono i tipi che dipendono da uno schema.</span><span class="sxs-lookup"><span data-stu-id="d58bc-139">This example doesn't leverage the ability of providers to provide types that depend on a schema.</span></span> <span data-ttu-id="d58bc-140">Nel codice seguente viene descritta l'implementazione del provider del tipo e i dettagli sono descritti nelle sezioni successive di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="d58bc-140">The implementation of the type provider is outlined in the following code, and the details are covered in later sections of this topic.</span></span>

>[!WARNING]
<span data-ttu-id="d58bc-141">Possono essere presenti differenze tra il codice e gli esempi online.</span><span class="sxs-lookup"><span data-stu-id="d58bc-141">There may be differences between this code and the online samples.</span></span>

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

<span data-ttu-id="d58bc-142">Per usare questo provider, aprire un'istanza separata di Visual Studio, creare uno script F # e quindi aggiungere un riferimento al provider dallo script utilizzando #r come illustrato nel codice seguente:</span><span class="sxs-lookup"><span data-stu-id="d58bc-142">To use this provider, open a separate instance of Visual Studio, create an F# script, and then add a reference to the provider from your script by using #r as the following code shows:</span></span>

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

<span data-ttu-id="d58bc-143">Cercare quindi i tipi nel `Samples.HelloWorldTypeProvider` dello spazio dei nomi che ha generato il provider di tipi.</span><span class="sxs-lookup"><span data-stu-id="d58bc-143">Then look for the types under the `Samples.HelloWorldTypeProvider` namespace that the type provider generated.</span></span>

<span data-ttu-id="d58bc-144">Prima di ricompilare il provider, assicurarsi che siano state chiuse tutte le istanze di Visual Studio e F # Interactive che usano la DLL del provider.</span><span class="sxs-lookup"><span data-stu-id="d58bc-144">Before you recompile the provider, make sure that you have closed all instances of Visual Studio and F# Interactive that are using the provider DLL.</span></span> <span data-ttu-id="d58bc-145">In caso contrario, viene visualizzato un errore di compilazione perché l'output DLL verrà bloccata.</span><span class="sxs-lookup"><span data-stu-id="d58bc-145">Otherwise, a build error will occur because the output DLL will be locked.</span></span>

<span data-ttu-id="d58bc-146">Per eseguire il debug di questo provider con istruzioni print, creare script che espone un problema con il provider e quindi usare il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="d58bc-146">To debug this provider by using print statements, make a script that exposes a problem with the provider, and then use the following code:</span></span>

```fsharp
fsc.exe -r:bin\Debug\HelloWorldTypeProvider.dll script.fsx
```

<span data-ttu-id="d58bc-147">Per eseguire il debug di questo provider con Visual Studio, aprire il prompt dei comandi di Visual Studio con credenziali amministrative ed eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="d58bc-147">To debug this provider by using Visual Studio, open the Visual Studio command prompt with administrative credentials, and run the following command:</span></span>

```fsharp
devenv.exe /debugexe fsc.exe -r:bin\Debug\HelloWorldTypeProvider.dll script.fsx
```

<span data-ttu-id="d58bc-148">In alternativa, aprire Visual Studio, aprire il menu di Debug, scegli `Debug/Attach to process…`e associare a un altro `devenv` processo in cui si sta modificando lo script.</span><span class="sxs-lookup"><span data-stu-id="d58bc-148">As an alternative, open Visual Studio, open the Debug menu, choose `Debug/Attach to process…`, and attach to another `devenv` process where you’re editing your script.</span></span> <span data-ttu-id="d58bc-149">Con questo metodo, è possibile assegnare più facilmente particolare per la logica nel provider di tipi, in modo interattivo digitando le espressioni nella seconda istanza (con funzionalità complete di IntelliSense e altre funzionalità).</span><span class="sxs-lookup"><span data-stu-id="d58bc-149">By using this method, you can more easily target particular logic in the type provider by interactively typing expressions into the second instance (with full IntelliSense and other features).</span></span>

<span data-ttu-id="d58bc-150">È possibile disabilitare Just My Code per identificare più facilmente gli errori nel codice generato del debug.</span><span class="sxs-lookup"><span data-stu-id="d58bc-150">You can disable Just My Code debugging to better identify errors in generated code.</span></span> <span data-ttu-id="d58bc-151">Per informazioni su come abilitare o disabilitare questa funzionalità, vedere [spostarsi nel codice con il Debugger](/visualstudio/debugger/navigating-through-code-with-the-debugger).</span><span class="sxs-lookup"><span data-stu-id="d58bc-151">For information about how to enable or disable this feature, see [Navigating through Code with the Debugger](/visualstudio/debugger/navigating-through-code-with-the-debugger).</span></span> <span data-ttu-id="d58bc-152">Inoltre, è anche possibile impostare le eccezioni first-chance rilevamento, aprire il `Debug` menu e scegliendo `Exceptions` oppure scegliendo i tasti Ctrl + Alt + E aprire il `Exceptions` nella finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="d58bc-152">Also, you can also set first-chance exception catching by opening the `Debug` menu and then choosing `Exceptions` or by choosing the Ctrl+Alt+E keys to open the `Exceptions` dialog box.</span></span> <span data-ttu-id="d58bc-153">Nella finestra di dialogo, sotto `Common Language Runtime Exceptions`, selezionare il `Thrown` casella di controllo.</span><span class="sxs-lookup"><span data-stu-id="d58bc-153">In that dialog box, under `Common Language Runtime Exceptions`, select the `Thrown` check box.</span></span>

### <a name="implementation-of-the-type-provider"></a><span data-ttu-id="d58bc-154">Implementazione del Provider di tipo</span><span class="sxs-lookup"><span data-stu-id="d58bc-154">Implementation of the Type Provider</span></span>

<span data-ttu-id="d58bc-155">In questa sezione illustra le sezioni principali dell'implementazione del provider di tipo.</span><span class="sxs-lookup"><span data-stu-id="d58bc-155">This section walks you through the principal sections of the type provider implementation.</span></span> <span data-ttu-id="d58bc-156">È in primo luogo, definire il tipo per il provider di tipi personalizzato se stessa:</span><span class="sxs-lookup"><span data-stu-id="d58bc-156">First, you define the type for the custom type provider itself:</span></span>

```fsharp
[<TypeProvider>]
type SampleTypeProvider(config: TypeProviderConfig) as this =
```

<span data-ttu-id="d58bc-157">Questo tipo deve essere pubblico ed è necessario contrassegnarla con il [TypeProvider](https://msdn.microsoft.com/library/bdf7b036-7490-4ace-b79f-c5f1b1b37947) in modo che il compilatore riconoscerà il provider di tipi quando un progetto F # separato fa riferimento all'assembly che contiene il tipo di attributo.</span><span class="sxs-lookup"><span data-stu-id="d58bc-157">This type must be public, and you must mark it with the [TypeProvider](https://msdn.microsoft.com/library/bdf7b036-7490-4ace-b79f-c5f1b1b37947) attribute so that the compiler will recognize the type provider when a separate F# project references the assembly that contains the type.</span></span> <span data-ttu-id="d58bc-158">Il *config* parametro è facoltativo e, se presente, contiene le informazioni di configurazione di scelta rapida per l'istanza del provider di tipi che consente di creare il compilatore F #.</span><span class="sxs-lookup"><span data-stu-id="d58bc-158">The *config* parameter is optional, and, if present, contains contextual configuration information for the type provider instance that the F# compiler creates.</span></span>

<span data-ttu-id="d58bc-159">Successivamente, si implementa il [ITypeProvider](https://msdn.microsoft.com/library/2c2b0571-843d-4a7d-95d4-0a7510ed5e2f) interfaccia.</span><span class="sxs-lookup"><span data-stu-id="d58bc-159">Next, you implement the [ITypeProvider](https://msdn.microsoft.com/library/2c2b0571-843d-4a7d-95d4-0a7510ed5e2f) interface.</span></span> <span data-ttu-id="d58bc-160">In questo caso, si utilizza il `TypeProviderForNamespaces` digitare dal `ProvidedTypes` API come tipo di base.</span><span class="sxs-lookup"><span data-stu-id="d58bc-160">In this case, you use the `TypeProviderForNamespaces` type from the `ProvidedTypes` API as a base type.</span></span> <span data-ttu-id="d58bc-161">Questo tipo di helper può indicare una raccolta finita di accuratamente fornita spazi dei nomi, ognuno dei quali direttamente contiene un numero finito di correzione, accuratamente i tipi forniti.</span><span class="sxs-lookup"><span data-stu-id="d58bc-161">This helper type can provide a finite collection of eagerly provided namespaces, each of which directly contains a finite number of fixed, eagerly provided types.</span></span> <span data-ttu-id="d58bc-162">In questo contesto, il provider *accuratamente* genera tipi anche se essi non sono necessari o usati.</span><span class="sxs-lookup"><span data-stu-id="d58bc-162">In this context, the provider *eagerly* generates types even if they aren't needed or used.</span></span>

```fsharp
inherit TypeProviderForNamespaces(config)
```

<span data-ttu-id="d58bc-163">Successivamente, definire i valori privati locali che specificano lo spazio dei nomi per i tipi specificati e trovare l'assembly di provider di tipo stesso.</span><span class="sxs-lookup"><span data-stu-id="d58bc-163">Next, define local private values that specify the namespace for the provided types, and find the type provider assembly itself.</span></span> <span data-ttu-id="d58bc-164">Questo assembly viene usato in un secondo momento come il tipo di elemento padre logico dei tipi cancellati forniti.</span><span class="sxs-lookup"><span data-stu-id="d58bc-164">This assembly is used later as the logical parent type of the erased types that are provided.</span></span>

```fsharp
let namespaceName = "Samples.HelloWorldTypeProvider"
let thisAssembly = Assembly.GetExecutingAssembly()
```

<span data-ttu-id="d58bc-165">Successivamente, creare una funzione per specificare ognuno dei tipi Type1... Type100.</span><span class="sxs-lookup"><span data-stu-id="d58bc-165">Next, create a function to provide each of the types Type1…Type100.</span></span> <span data-ttu-id="d58bc-166">Questa funzione è illustrata più dettagliatamente più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="d58bc-166">This function is explained in more detail later in this topic.</span></span>

```fsharp
let makeOneProvidedType (n:int) = …
```

<span data-ttu-id="d58bc-167">Generare quindi i tipi specificati 100:</span><span class="sxs-lookup"><span data-stu-id="d58bc-167">Next, generate the 100 provided types:</span></span>

```fsharp
let types = [ for i in 1 .. 100 -> makeOneProvidedType i ]
```

<span data-ttu-id="d58bc-168">Successivamente, aggiungere i tipi come uno spazio dei nomi specificato:</span><span class="sxs-lookup"><span data-stu-id="d58bc-168">Next, add the types as a provided namespace:</span></span>

```fsharp
do this.AddNamespace(namespaceName, types)
```

<span data-ttu-id="d58bc-169">Aggiungere infine un attributo dell'assembly che indica che si sta creando una DLL del provider di tipo:</span><span class="sxs-lookup"><span data-stu-id="d58bc-169">Finally, add an assembly attribute that indicates that you are creating a type provider DLL:</span></span>

```fsharp
[<assembly:TypeProviderAssembly>] 
do()
```

### <a name="providing-one-type-and-its-members"></a><span data-ttu-id="d58bc-170">Che fornisce un tipo e i relativi membri</span><span class="sxs-lookup"><span data-stu-id="d58bc-170">Providing One Type And Its Members</span></span>

<span data-ttu-id="d58bc-171">Il `makeOneProvidedType` funzione esegue il lavoro effettivo di fornire uno dei tipi.</span><span class="sxs-lookup"><span data-stu-id="d58bc-171">The `makeOneProvidedType` function does the real work of providing one of the types.</span></span>

```fsharp
let makeOneProvidedType (n:int) = 
…
```

<span data-ttu-id="d58bc-172">Questo passaggio spiega l'implementazione di questa funzione.</span><span class="sxs-lookup"><span data-stu-id="d58bc-172">This step explains the implementation of this function.</span></span> <span data-ttu-id="d58bc-173">Creare innanzitutto il tipo fornito (ad esempio, Type1, quando n = 1 o Type57, quando n = 57).</span><span class="sxs-lookup"><span data-stu-id="d58bc-173">First, create the provided type (for example, Type1, when n = 1, or Type57, when n = 57).</span></span>

```fsharp
// This is the provided type. It is an erased provided type and, in compiled code, 
// will appear as type 'obj'.
let t = ProvidedTypeDefinition(thisAssembly, namespaceName,
                               "Type" + string n,
                               baseType = Some typeof<obj>)
```

<span data-ttu-id="d58bc-174">Si noti quanto riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="d58bc-174">You should note the following points:</span></span>

- <span data-ttu-id="d58bc-175">Queste informazioni specificate tipo verrà cancellato.</span><span class="sxs-lookup"><span data-stu-id="d58bc-175">This provided type is erased.</span></span>  <span data-ttu-id="d58bc-176">Poiché si indica che è il tipo di base `obj`, le istanze verranno visualizzati come valori di tipo [obj](https://msdn.microsoft.com/library/dcf2430f-702b-40e5-a0a1-97518bf137f7) nel codice compilato.</span><span class="sxs-lookup"><span data-stu-id="d58bc-176">Because you indicate that the base type is `obj`, instances will appear as values of type [obj](https://msdn.microsoft.com/library/dcf2430f-702b-40e5-a0a1-97518bf137f7) in compiled code.</span></span>

- <span data-ttu-id="d58bc-177">Quando si specifica un tipo non annidato, è necessario specificare l'assembly e dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="d58bc-177">When you specify a non-nested type, you must specify the assembly and namespace.</span></span> <span data-ttu-id="d58bc-178">Per i tipi cancellati, l'assembly deve essere l'assembly di provider di tipo stesso.</span><span class="sxs-lookup"><span data-stu-id="d58bc-178">For erased types, the assembly should be the type provider assembly itself.</span></span>

<span data-ttu-id="d58bc-179">Aggiungere quindi la documentazione XML per il tipo.</span><span class="sxs-lookup"><span data-stu-id="d58bc-179">Next, add XML documentation to the type.</span></span> <span data-ttu-id="d58bc-180">Questa documentazione viene ritardato, vale a dire, calcolate su richiesta se ne ha bisogno il compilatore host.</span><span class="sxs-lookup"><span data-stu-id="d58bc-180">This documentation is delayed, that is, computed on-demand if the host compiler needs it.</span></span>

```fsharp
t.AddXmlDocDelayed (fun () -> sprintf "This provided type %s" ("Type" + string n))
```

<span data-ttu-id="d58bc-181">Aggiungere una proprietà statica fornita al tipo:</span><span class="sxs-lookup"><span data-stu-id="d58bc-181">Next you add a provided static property to the type:</span></span>

```fsharp
let staticProp = ProvidedProperty(propertyName = "StaticProperty", 
                                  propertyType = typeof<string>, 
                                  isStatic = true,
                                  getterCode = (fun args -> <@@ "Hello!" @@>))
```

<span data-ttu-id="d58bc-182">Ottiene questa proprietà restituisce sempre la stringa "Hello!".</span><span class="sxs-lookup"><span data-stu-id="d58bc-182">Getting this property will always evaluate to the string "Hello!".</span></span> <span data-ttu-id="d58bc-183">Il `GetterCode` per la proprietà viene utilizzata una quotation F #, che rappresenta il codice che genera il compilatore host per il recupero della proprietà.</span><span class="sxs-lookup"><span data-stu-id="d58bc-183">The `GetterCode` for the property uses an F# quotation, which represents the code that the host compiler generates for getting the property.</span></span> <span data-ttu-id="d58bc-184">Per altre informazioni sulle offerte, vedere [citazioni di codice (F #)](https://msdn.microsoft.com/library/6f055397-a1f0-4f9a-927c-f0d7c6951155).</span><span class="sxs-lookup"><span data-stu-id="d58bc-184">For more information about quotations, see [Code Quotations (F#)](https://msdn.microsoft.com/library/6f055397-a1f0-4f9a-927c-f0d7c6951155).</span></span>

<span data-ttu-id="d58bc-185">Aggiungere la documentazione XML per la proprietà.</span><span class="sxs-lookup"><span data-stu-id="d58bc-185">Add XML documentation to the property.</span></span>

```fsharp
staticProp.AddXmlDocDelayed(fun () -> "This is a static property")
```

<span data-ttu-id="d58bc-186">Ora è possibile associare proprietà fornita per il tipo specificato.</span><span class="sxs-lookup"><span data-stu-id="d58bc-186">Now attach the provided property to the provided type.</span></span> <span data-ttu-id="d58bc-187">È necessario associare un membro specificato in un unico tipo.</span><span class="sxs-lookup"><span data-stu-id="d58bc-187">You must attach a provided member to one and only one type.</span></span> <span data-ttu-id="d58bc-188">In caso contrario, il membro non potranno mai essere accessibile.</span><span class="sxs-lookup"><span data-stu-id="d58bc-188">Otherwise, the member will never be accessible.</span></span>

```fsharp
t.AddMember staticProp
```

<span data-ttu-id="d58bc-189">Creare ora un costruttore specificato che non accetta parametri.</span><span class="sxs-lookup"><span data-stu-id="d58bc-189">Now create a provided constructor that takes no parameters.</span></span>

```fsharp
let ctor = ProvidedConstructor(parameters = [ ], 
                               invokeCode = (fun args -> <@@ "The object data" :> obj @@>))
```

<span data-ttu-id="d58bc-190">Il `InvokeCode` per il costruttore restituisce un quotation F #, che rappresenta il codice che il compilatore host genera l'errore quando viene chiamato il costruttore.</span><span class="sxs-lookup"><span data-stu-id="d58bc-190">The `InvokeCode` for the constructor returns an F# quotation, which represents the code that the host compiler generates when the constructor is called.</span></span> <span data-ttu-id="d58bc-191">Ad esempio, è possibile usare il costruttore seguente:</span><span class="sxs-lookup"><span data-stu-id="d58bc-191">For example, you can use the following constructor:</span></span>

```fsharp
new Type10()
```

<span data-ttu-id="d58bc-192">Verrà creata un'istanza del tipo fornito con i dati sottostanti "I dati dell'oggetto".</span><span class="sxs-lookup"><span data-stu-id="d58bc-192">An instance of the provided type will be created with underlying data "The object data".</span></span> <span data-ttu-id="d58bc-193">Il codice tra virgolette include una conversione [obj](https://msdn.microsoft.com/library/dcf2430f-702b-40e5-a0a1-97518bf137f7) perché tale tipo è la cancellazione di questo fornito di tipo (come specificato quando è dichiarato il tipo specificato).</span><span class="sxs-lookup"><span data-stu-id="d58bc-193">The quoted code includes a conversion to [obj](https://msdn.microsoft.com/library/dcf2430f-702b-40e5-a0a1-97518bf137f7) because that type is the erasure of this provided type (as you specified when you declared the provided type).</span></span>

<span data-ttu-id="d58bc-194">Aggiungere la documentazione XML per il costruttore e aggiungere il costruttore fornito per il tipo specificato:</span><span class="sxs-lookup"><span data-stu-id="d58bc-194">Add XML documentation to the constructor, and add the provided constructor to the provided type:</span></span>

```fsharp
ctor.AddXmlDocDelayed(fun () -> "This is a constructor")

t.AddMember ctor
```

<span data-ttu-id="d58bc-195">Creare un secondo costruttore specificato che accetta un parametro:</span><span class="sxs-lookup"><span data-stu-id="d58bc-195">Create a second provided constructor that takes one parameter:</span></span>

```fsharp
let ctor2 = 
ProvidedConstructor(parameters = [ ProvidedParameter("data",typeof<string>) ], 
                    invokeCode = (fun args -> <@@ (%%(args.[0]) : string) :> obj @@>))
```

<span data-ttu-id="d58bc-196">Il `InvokeCode` per il costruttore restituisce nuovamente una quotation F #, che rappresenta il codice che ha generato il compilatore host per una chiamata al metodo.</span><span class="sxs-lookup"><span data-stu-id="d58bc-196">The `InvokeCode` for the constructor again returns an F# quotation, which represents the code that the host compiler generated for a call to the method.</span></span> <span data-ttu-id="d58bc-197">Ad esempio, è possibile usare il costruttore seguente:</span><span class="sxs-lookup"><span data-stu-id="d58bc-197">For example, you can use the following constructor:</span></span>

```fsharp
new Type10("ten")
```

<span data-ttu-id="d58bc-198">Viene creata un'istanza del tipo fornito con i dati sottostanti "10".</span><span class="sxs-lookup"><span data-stu-id="d58bc-198">An instance of the provided type is created with underlying data "ten".</span></span> <span data-ttu-id="d58bc-199">Si è già notato che la `InvokeCode` funzione restituisce una citazione.</span><span class="sxs-lookup"><span data-stu-id="d58bc-199">You may have already noticed that the `InvokeCode` function returns a quotation.</span></span> <span data-ttu-id="d58bc-200">L'input a questa funzione è un elenco di espressioni, uno per ogni parametro del costruttore.</span><span class="sxs-lookup"><span data-stu-id="d58bc-200">The input to this function is a list of expressions, one per constructor parameter.</span></span> <span data-ttu-id="d58bc-201">In questo caso, è disponibile in un'espressione che rappresenta il valore del parametro singolo `args.[0]`.</span><span class="sxs-lookup"><span data-stu-id="d58bc-201">In this case, an expression that represents the single parameter value is available in `args.[0]`.</span></span> <span data-ttu-id="d58bc-202">Il codice per una chiamata al costruttore assegna il valore restituito nel tipo cancellato `obj`.</span><span class="sxs-lookup"><span data-stu-id="d58bc-202">The code for a call to the constructor coerces the return value to the erased type `obj`.</span></span> <span data-ttu-id="d58bc-203">Dopo aver aggiunto il secondo costruttore fornito al tipo, si crea una proprietà di istanza fornita:</span><span class="sxs-lookup"><span data-stu-id="d58bc-203">After you add the second provided constructor to the type, you create a provided instance property:</span></span>

```fsharp
let instanceProp = 
    ProvidedProperty(propertyName = "InstanceProperty", 
                     propertyType = typeof<int>, 
                     getterCode= (fun args -> 
                        <@@ ((%%(args.[0]) : obj) :?> string).Length @@>))
instanceProp.AddXmlDocDelayed(fun () -> "This is an instance property")
t.AddMember instanceProp
```

<span data-ttu-id="d58bc-204">Ottiene questa proprietà verrà restituita la lunghezza della stringa, ovvero l'oggetto di rappresentazione.</span><span class="sxs-lookup"><span data-stu-id="d58bc-204">Getting this property will return the length of the string, which is the representation object.</span></span> <span data-ttu-id="d58bc-205">Il `GetterCode` proprietà restituisce una quotation F # che specifica il codice per ottenere la proprietà generata dal compilatore host.</span><span class="sxs-lookup"><span data-stu-id="d58bc-205">The `GetterCode` property returns an F# quotation that specifies the code that the host compiler generates to get the property.</span></span> <span data-ttu-id="d58bc-206">Ad esempio `InvokeCode`, il `GetterCode` funzione restituisce una citazione.</span><span class="sxs-lookup"><span data-stu-id="d58bc-206">Like `InvokeCode`, the `GetterCode` function returns a quotation.</span></span> <span data-ttu-id="d58bc-207">Il compilatore host chiama questa funzione con un elenco di argomenti.</span><span class="sxs-lookup"><span data-stu-id="d58bc-207">The host compiler calls this function with a list of arguments.</span></span> <span data-ttu-id="d58bc-208">In questo caso, gli argomenti includono solo la singola espressione che rappresenta l'istanza sulla quale viene chiamato il metodo Get, che è possibile accedere usando `args.[0]`. L'implementazione di `GetterCode` quindi sottopone a splicing nell'offerta di risultato in corrispondenza del tipo cancellato `obj`, e viene utilizzato un cast per soddisfare il meccanismo del compilatore per il controllo dei tipi che l'oggetto è una stringa.</span><span class="sxs-lookup"><span data-stu-id="d58bc-208">In this case, the arguments include just the single expression that represents the instance upon which the getter is being called, which you can access by using `args.[0]`.The implementation of `GetterCode` then splices into the result quotation at the erased type `obj`, and a cast is used to satisfy the compiler's mechanism for checking types that the object is a string.</span></span> <span data-ttu-id="d58bc-209">La parte successiva della `makeOneProvidedType` fornisce un metodo di istanza con un parametro.</span><span class="sxs-lookup"><span data-stu-id="d58bc-209">The next part of `makeOneProvidedType` provides an instance method with one parameter.</span></span>

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

<span data-ttu-id="d58bc-210">Infine, creare un tipo annidato che contiene 100 proprietà annidate.</span><span class="sxs-lookup"><span data-stu-id="d58bc-210">Finally, create a nested type that contains 100 nested properties.</span></span> <span data-ttu-id="d58bc-211">La creazione di questo tipo e le relative proprietà annidati viene ritardato, vale a dire, calcolate su richiesta.</span><span class="sxs-lookup"><span data-stu-id="d58bc-211">The creation of this nested type and its properties is delayed, that is, computed on-demand.</span></span>

```fsharp
t.AddMembersDelayed(fun () -> 
  let nestedType = ProvidedTypeDefinition("NestedType", Some typeof<obj>)

  nestedType.AddMembersDelayed (fun () -> 
    let staticPropsInNestedType = 
      [ for i in 1 .. 100 do
          let valueOfTheProperty = "I am string "  + string i

          let p = 
            ProvidedProperty(propertyName = "StaticProperty" + string i, 
              propertyType = typeof<string>, 
              isStatic = true,
              getterCode= (fun args -> <@@ valueOfTheProperty @@>))

          p.AddXmlDocDelayed(fun () -> 
              sprintf "This is StaticProperty%d on NestedType" i)

          yield p ]

    staticPropsInNestedType)

  [nestedType])
```

### <a name="details-about-erased-provided-types"></a><span data-ttu-id="d58bc-212">Informazioni dettagliate sui tipi forniti cancellati</span><span class="sxs-lookup"><span data-stu-id="d58bc-212">Details about Erased Provided Types</span></span>

<span data-ttu-id="d58bc-213">L'esempio in questa sezione vengono fornite solo *cancellati tipi specificati*, che sono particolarmente utili nelle situazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="d58bc-213">The example in this section provides only *erased provided types*, which are particularly useful in the following situations:</span></span>

- <span data-ttu-id="d58bc-214">Quando si scrive un provider per uno spazio di informazioni che contiene solo i dati e metodi.</span><span class="sxs-lookup"><span data-stu-id="d58bc-214">When you are writing a provider for an information space that contains only data and methods.</span></span>

- <span data-ttu-id="d58bc-215">Quando si scrive un provider in cui una semantica tipo-runtime accurate non è critica per l'uso pratico dello spazio di informazioni.</span><span class="sxs-lookup"><span data-stu-id="d58bc-215">When you are writing a provider where accurate runtime-type semantics aren't critical for practical use of the information space.</span></span>

- <span data-ttu-id="d58bc-216">Quando si scrive un provider per uno spazio di informazioni che è così grande e interconnessi che non è tecnicamente possibile per generare i tipi .NET reali per lo spazio di informazioni.</span><span class="sxs-lookup"><span data-stu-id="d58bc-216">When you are writing a provider for an information space that is so large and interconnected that it isn’t technically feasible to generate real .NET types for the information space.</span></span>

<span data-ttu-id="d58bc-217">In questo esempio, ogni fornito di tipo verrà cancellato al tipo `obj`, e tutti gli usi del tipo verranno visualizzato come tipo `obj` nel codice compilato.</span><span class="sxs-lookup"><span data-stu-id="d58bc-217">In this example, each provided type is erased to type `obj`, and all uses of the type will appear as type `obj` in compiled code.</span></span> <span data-ttu-id="d58bc-218">In effetti, gli oggetti sottostanti in questi esempi sono stringhe, ma il tipo verrà visualizzato come `System.Object` in .NET codice compilato.</span><span class="sxs-lookup"><span data-stu-id="d58bc-218">In fact, the underlying objects in these examples are strings, but the type will appear as `System.Object` in .NET compiled code.</span></span> <span data-ttu-id="d58bc-219">Come con tutti gli usi di cancellazione di tipo, è possibile usare la conversione boxing esplicito, conversione unboxing ed eseguendo il cast a compromettere cancellati i tipi.</span><span class="sxs-lookup"><span data-stu-id="d58bc-219">As with all uses of type erasure, you can use explicit boxing, unboxing, and casting to subvert erased types.</span></span> <span data-ttu-id="d58bc-220">In questo caso, un'eccezione di cast non valida potrebbe quando l'oggetto viene usato.</span><span class="sxs-lookup"><span data-stu-id="d58bc-220">In this case, a cast exception that isn’t valid may result when the object is used.</span></span> <span data-ttu-id="d58bc-221">Un provider runtime è possibile definire un proprio tipo di rappresentazione privata per proteggersi da rappresentazioni false.</span><span class="sxs-lookup"><span data-stu-id="d58bc-221">A provider runtime can define its own private representation type to help protect against false representations.</span></span> <span data-ttu-id="d58bc-222">Non è possibile definire i tipi cancellati in F # se stesso.</span><span class="sxs-lookup"><span data-stu-id="d58bc-222">You can’t define erased types in F# itself.</span></span> <span data-ttu-id="d58bc-223">Solo i tipi specificati possono essere cancellati.</span><span class="sxs-lookup"><span data-stu-id="d58bc-223">Only provided types may be erased.</span></span> <span data-ttu-id="d58bc-224">È necessario comprendere le ramificazioni, entrambi pratici e semantici, di usare uno tipi cancellati per il provider di tipo o un provider che fornisce cancellati tipi.</span><span class="sxs-lookup"><span data-stu-id="d58bc-224">You must understand the ramifications, both practical and semantic, of using either erased types for your type provider or a provider that provides erased types.</span></span> <span data-ttu-id="d58bc-225">Un tipo cancellato non dispone di alcun tipo .NET reale.</span><span class="sxs-lookup"><span data-stu-id="d58bc-225">An erased type has no real .NET type.</span></span> <span data-ttu-id="d58bc-226">Pertanto, non è possibile eseguire sul tipo di reflection accurata e si potrebbero compromettere i tipi cancellati se si usano i cast di runtime e altre tecniche che si basano sulla semantica del tipo esatto di runtime.</span><span class="sxs-lookup"><span data-stu-id="d58bc-226">Therefore, you cannot do accurate reflection over the type, and you might subvert erased types if you use runtime casts and other techniques that rely on exact runtime type semantics.</span></span> <span data-ttu-id="d58bc-227">Subversion dei tipi cancellati spesso comporta eccezioni di cast di tipo in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="d58bc-227">Subversion of erased types frequently results in type cast exceptions at runtime.</span></span>

### <a name="choosing-representations-for-erased-provided-types"></a><span data-ttu-id="d58bc-228">Scelta di rappresentazioni per cancellare i tipi forniti</span><span class="sxs-lookup"><span data-stu-id="d58bc-228">Choosing Representations for Erased Provided Types</span></span>

<span data-ttu-id="d58bc-229">Per alcuni casi di utilizzo dei tipi forniti cancellati, non è necessaria alcuna rappresentazione.</span><span class="sxs-lookup"><span data-stu-id="d58bc-229">For some uses of erased provided types, no representation is required.</span></span> <span data-ttu-id="d58bc-230">Ad esempio, è il cancellato fornito tipo potrebbe contenere solo le proprietà statiche e membri e alcun costruttore, e nessuna proprietà o metodi restituisce un'istanza del tipo.</span><span class="sxs-lookup"><span data-stu-id="d58bc-230">For example, the erased provided type might contain only static properties and members and no constructors, and no methods or properties would return an instance of the type.</span></span> <span data-ttu-id="d58bc-231">Se è possibile raggiungere le istanze di un cancellato fornito di tipo, è necessario considerare le domande seguenti:</span><span class="sxs-lookup"><span data-stu-id="d58bc-231">If you can reach instances of an erased provided type, you must consider the following questions:</span></span>

<span data-ttu-id="d58bc-232">**Che cos'è la cancellazione di un tipo fornito?**</span><span class="sxs-lookup"><span data-stu-id="d58bc-232">**What is the erasure of a provided type?**</span></span>

- <span data-ttu-id="d58bc-233">La cancellazione di un tipo fornito è come il tipo viene visualizzato nel codice .NET compilato.</span><span class="sxs-lookup"><span data-stu-id="d58bc-233">The erasure of a provided type is how the type appears in compiled .NET code.</span></span>

- <span data-ttu-id="d58bc-234">La cancellazione di un tipo di classe cancellato fornita è sempre il primo non cancellati tipo di base nella catena di ereditarietà del tipo.</span><span class="sxs-lookup"><span data-stu-id="d58bc-234">The erasure of a provided erased class type is always the first non-erased base type in the inheritance chain of the type.</span></span>

- <span data-ttu-id="d58bc-235">La cancellazione di un tipo di interfaccia cancellato fornita è sempre `System.Object`.</span><span class="sxs-lookup"><span data-stu-id="d58bc-235">The erasure of a provided erased interface type is always `System.Object`.</span></span>

<span data-ttu-id="d58bc-236">**Quali sono le rappresentazioni di un tipo fornito?**</span><span class="sxs-lookup"><span data-stu-id="d58bc-236">**What are the representations of a provided type?**</span></span>

- <span data-ttu-id="d58bc-237">Il set di oggetti possibili per un tipo fornito cancellati vengono chiamati relative rappresentazioni.</span><span class="sxs-lookup"><span data-stu-id="d58bc-237">The set of possible objects for an erased provided type are called its representations.</span></span> <span data-ttu-id="d58bc-238">Nell'esempio in questo documento, le rappresentazioni di tutti il cancellato fornito tipi `Type1..Type100` sono sempre oggetti stringa.</span><span class="sxs-lookup"><span data-stu-id="d58bc-238">In the example in this document, the representations of all the erased provided types `Type1..Type100` are always string objects.</span></span>

<span data-ttu-id="d58bc-239">Tutte le rappresentazioni di un tipo fornito devono essere compatibile con la cancellazione del tipo fornito.</span><span class="sxs-lookup"><span data-stu-id="d58bc-239">All representations of a provided type must be compatible with the erasure of the provided type.</span></span> <span data-ttu-id="d58bc-240">(In caso contrario, il compilatore F # genererà un errore per un utilizzo del provider del tipo, o verrà generato codice .NET non verificabile che non è valido.</span><span class="sxs-lookup"><span data-stu-id="d58bc-240">(Otherwise, either the F# compiler will give an error for a use of the type provider, or unverifiable .NET code that isn't valid will be generated.</span></span> <span data-ttu-id="d58bc-241">Un provider di tipi non è valido se restituisce un codice che fornisce una rappresentazione non valida.</span><span class="sxs-lookup"><span data-stu-id="d58bc-241">A type provider isn’t valid if it returns code that gives a  representation that isn't valid.)</span></span>

<span data-ttu-id="d58bc-242">È possibile scegliere una rappresentazione per gli oggetti forniti utilizzando uno degli approcci seguenti, che sono molto comuni:</span><span class="sxs-lookup"><span data-stu-id="d58bc-242">You can choose a representation for provided objects by using either of the following approaches, both of which are very common:</span></span>

- <span data-ttu-id="d58bc-243">Se si forniscono un wrapper fortemente tipizzato semplicemente su un tipo .NET esistente, è spesso opportuno per il tipo cancellare a quel tipo, usare le istanze di tale tipo come rappresentazioni o entrambi.</span><span class="sxs-lookup"><span data-stu-id="d58bc-243">If you're simply providing a strongly typed wrapper over an existing .NET type, it often makes sense for your type to erase to that type, use instances of that type as representations, or both.</span></span> <span data-ttu-id="d58bc-244">Questo approccio è appropriato quando la maggior parte dei metodi esistenti su tale tipo siano comunque valide quando si usa la versione fortemente tipizzata.</span><span class="sxs-lookup"><span data-stu-id="d58bc-244">This approach is appropriate when most of the existing methods on that type still make sense when using the strongly typed version.</span></span>

- <span data-ttu-id="d58bc-245">Se si desidera creare un'API che differisce significativamente da tutte API .NET esistente, è opportuno creare i tipi di runtime che saranno la cancellazione di tipo e rappresentazioni per i tipi specificati.</span><span class="sxs-lookup"><span data-stu-id="d58bc-245">If you want to create an API that differs significantly from any existing .NET API, it makes sense to create runtime types that will be the type erasure and representations for the provided types.</span></span>

<span data-ttu-id="d58bc-246">L'esempio in questo documento usa le stringhe come rappresentazioni di oggetti specificati.</span><span class="sxs-lookup"><span data-stu-id="d58bc-246">The example in this document uses strings as representations of provided objects.</span></span> <span data-ttu-id="d58bc-247">Spesso, potrebbe essere opportuno usare altri oggetti per le rappresentazioni.</span><span class="sxs-lookup"><span data-stu-id="d58bc-247">Frequently, it may be appropriate to use other objects for representations.</span></span> <span data-ttu-id="d58bc-248">Ad esempio, è possibile utilizzare un dizionario come un contenitore di proprietà:</span><span class="sxs-lookup"><span data-stu-id="d58bc-248">For example, you may use a dictionary as a property bag:</span></span>

```fsharp
ProvidedConstructor(parameters = [], 
    invokeCode= (fun args -> <@@ (new Dictionary<string,obj>()) :> obj @@>))
```

<span data-ttu-id="d58bc-249">In alternativa, è possibile definire un tipo nel provider di tipo che verrà usato in fase di esecuzione per formare la rappresentazione, insieme a uno o più operazioni di runtime:</span><span class="sxs-lookup"><span data-stu-id="d58bc-249">As an alternative, you may define a type in your type provider that will be used at runtime to form the representation, along with one or more runtime operations:</span></span>

```fsharp
type DataObject() =
    let data = Dictionary<string,obj>()
    member x.RuntimeOperation() = data.Count
```

<span data-ttu-id="d58bc-250">I membri specificati possono quindi costruire le istanze di questo tipo di oggetto:</span><span class="sxs-lookup"><span data-stu-id="d58bc-250">Provided members can then construct instances of this object type:</span></span>

```fsharp
ProvidedConstructor(parameters = [], 
    invokeCode= (fun args -> <@@ (new DataObject()) :> obj @@>))
```

<span data-ttu-id="d58bc-251">In questo caso, si potrebbe (facoltativamente) usare questo tipo come la cancellazione di tipo specificando questo tipo come le `baseType` durante la costruzione di `ProvidedTypeDefinition`:</span><span class="sxs-lookup"><span data-stu-id="d58bc-251">In this case, you may (optionally) use this type as the type erasure by specifying this type as the `baseType` when constructing the `ProvidedTypeDefinition`:</span></span>

```fsharp
ProvidedTypeDefinition(…, baseType = Some typeof<DataObject> )
…
ProvidedConstructor(…, InvokeCode = (fun args -> <@@ new DataObject() @@>), …)
```

### <a name="key-lessons"></a><span data-ttu-id="d58bc-252">Lezioni principali</span><span class="sxs-lookup"><span data-stu-id="d58bc-252">Key Lessons</span></span>

<span data-ttu-id="d58bc-253">La sezione precedente è stato spiegato come creare un provider di tipi cancellazione semplice che offre una gamma di tipi, proprietà e metodi.</span><span class="sxs-lookup"><span data-stu-id="d58bc-253">The previous section explained how to create a simple erasing type provider that provides a range of types, properties, and methods.</span></span> <span data-ttu-id="d58bc-254">In questa sezione viene inoltre illustrato il concetto di cancellazione di tipo, tra cui alcuni dei vantaggi e svantaggi di fornire i tipi cancellati da un provider di tipi e illustrate rappresentazioni di tipi cancellati.</span><span class="sxs-lookup"><span data-stu-id="d58bc-254">This section also explained the concept of type erasure, including some of the advantages and disadvantages of providing erased types from a type provider, and discussed representations of erased types.</span></span>

## <a name="a-type-provider-that-uses-static-parameters"></a><span data-ttu-id="d58bc-255">Un Provider di tipi che utilizza parametri statici</span><span class="sxs-lookup"><span data-stu-id="d58bc-255">A Type Provider That Uses Static Parameters</span></span>

<span data-ttu-id="d58bc-256">La possibilità di impostare i parametri provider di tipi da dati statici consente molti scenari interessanti, anche in casi in cui il provider non è necessario accedere ai dati locali o remoti.</span><span class="sxs-lookup"><span data-stu-id="d58bc-256">The ability to parameterize type providers by static data enables many interesting scenarios, even in cases when the provider doesn't need to access any local or remote data.</span></span> <span data-ttu-id="d58bc-257">In questa sezione si apprenderà alcune tecniche di base per la creazione di un provider di questo tipo.</span><span class="sxs-lookup"><span data-stu-id="d58bc-257">In this section, you’ll learn some basic techniques for putting together such a provider.</span></span>

### <a name="type-checked-regex-provider"></a><span data-ttu-id="d58bc-258">Tipo controllato Provider Regex</span><span class="sxs-lookup"><span data-stu-id="d58bc-258">Type Checked Regex Provider</span></span>

<span data-ttu-id="d58bc-259">Si supponga che si desidera implementare un provider di tipi per le espressioni regolari che esegue il wrapping di .NET <xref:System.Text.RegularExpressions.Regex> librerie in un'interfaccia che fornisce le seguenti garanzie in fase di compilazione:</span><span class="sxs-lookup"><span data-stu-id="d58bc-259">Imagine that you want to implement a type provider for regular expressions that wraps the .NET <xref:System.Text.RegularExpressions.Regex> libraries in an interface that provides the following compile-time guarantees:</span></span>

- <span data-ttu-id="d58bc-260">Verifica se un'espressione regolare è valida.</span><span class="sxs-lookup"><span data-stu-id="d58bc-260">Verifying whether a regular expression is valid.</span></span>

- <span data-ttu-id="d58bc-261">Fornendo proprietà denominate corrispondenze basate su tutti i nomi dei gruppi nell'espressione regolare.</span><span class="sxs-lookup"><span data-stu-id="d58bc-261">Providing named properties on matches that are based on any group names in the regular expression.</span></span>

<span data-ttu-id="d58bc-262">Questa sezione illustra come usare i provider di tipi per creare un `RegexTyped` digitare che Parametrizza il criterio di espressione regolare per fornire tali vantaggi.</span><span class="sxs-lookup"><span data-stu-id="d58bc-262">This section shows you how to use type providers to create a `RegexTyped` type that the regular expression pattern parameterizes to provide these benefits.</span></span> <span data-ttu-id="d58bc-263">Il compilatore segnalerà un errore se il modello fornito non è valido e il provider di tipi può estrarre i gruppi nel criterio in modo che è possibile accedervi usando le proprietà sulle corrispondenze denominate.</span><span class="sxs-lookup"><span data-stu-id="d58bc-263">The compiler will report an error if the supplied pattern isn't valid, and the type provider can extract the groups from the pattern so that you can access them by using named properties on matches.</span></span> <span data-ttu-id="d58bc-264">Quando si progetta un provider di tipi, è necessario considerare come dovrebbe apparire relative API esposta agli utenti finali e modo in cui questo progetto verrà convertito in codice .NET.</span><span class="sxs-lookup"><span data-stu-id="d58bc-264">When you design a type provider, you should consider how its exposed API should look to end users and how this design will translate to .NET code.</span></span> <span data-ttu-id="d58bc-265">Nell'esempio seguente viene illustrato come utilizzare questo tipo di API per ottenere i componenti del codice area:</span><span class="sxs-lookup"><span data-stu-id="d58bc-265">The following example shows how to use such an API to get the components of the area code:</span></span>

```fsharp
type T = RegexTyped< @"(?<AreaCode>^\d{3})-(?<PhoneNumber>\d{3}-\d{4}$)">
let reg = T()
let result = T.IsMatch("425-555-2345")
let r = reg.Match("425-555-2345").Group_AreaCode.Value //r equals "425"
```

<span data-ttu-id="d58bc-266">Nell'esempio seguente viene illustrato come il provider di tipi converte queste chiamate:</span><span class="sxs-lookup"><span data-stu-id="d58bc-266">The following example shows how the type provider translates these calls:</span></span>

```fsharp
let reg = new Regex(@"(?<AreaCode>^\d{3})-(?<PhoneNumber>\d{3}-\d{4}$)")
let result = reg.IsMatch("425-123-2345")
let r = reg.Match("425-123-2345").Groups.["AreaCode"].Value //r equals "425"
```

<span data-ttu-id="d58bc-267">Tenere presente quanto segue:</span><span class="sxs-lookup"><span data-stu-id="d58bc-267">Note the following points:</span></span>

- <span data-ttu-id="d58bc-268">Il tipo di espressione regolare standard rappresenta i parametri `RegexTyped` tipo.</span><span class="sxs-lookup"><span data-stu-id="d58bc-268">The standard Regex type represents the parameterized `RegexTyped` type.</span></span>

- <span data-ttu-id="d58bc-269">Il `RegexTyped` costruttore comporta una chiamata al costruttore di espressioni regolari, passando l'argomento di tipo statico per il modello.</span><span class="sxs-lookup"><span data-stu-id="d58bc-269">The `RegexTyped` constructor results in a call to the Regex constructor, passing in the static type argument for the pattern.</span></span>

- <span data-ttu-id="d58bc-270">I risultati del `Match` metodo sono rappresentati dallo standard <xref:System.Text.RegularExpressions.Match> tipo.</span><span class="sxs-lookup"><span data-stu-id="d58bc-270">The results of the `Match` method are represented by the standard <xref:System.Text.RegularExpressions.Match> type.</span></span>

- <span data-ttu-id="d58bc-271">Ogni gruppo denominato comporta una proprietà specificata e l'accesso alla proprietà comporta un uso di un indicizzatore in caso di corrispondenza `Groups` raccolta.</span><span class="sxs-lookup"><span data-stu-id="d58bc-271">Each named group results in a provided property, and accessing the property results in a use of an indexer on a match’s `Groups` collection.</span></span>

<span data-ttu-id="d58bc-272">Il codice seguente è il nucleo della logica per implementare un provider di questo tipo, e questo esempio viene omesso l'aggiunta di tutti i membri per il tipo specificato.</span><span class="sxs-lookup"><span data-stu-id="d58bc-272">The following code is the core of the logic to implement such a provider, and this example omits the addition of all members to the provided type.</span></span> <span data-ttu-id="d58bc-273">Per informazioni su ogni membro aggiunto, vedere la sezione appropriata più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="d58bc-273">For information about each added member, see the appropriate section later in this topic.</span></span> <span data-ttu-id="d58bc-274">Per il codice completo, scaricare l'esempio dal [pacchetto di esempio F # 3.0](https://fsharp3sample.codeplex.com) sul sito Web Codeplex.</span><span class="sxs-lookup"><span data-stu-id="d58bc-274">For the full code, download the sample from the [F# 3.0 Sample Pack](https://fsharp3sample.codeplex.com) on the Codeplex website.</span></span>

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

<span data-ttu-id="d58bc-275">Tenere presente quanto segue:</span><span class="sxs-lookup"><span data-stu-id="d58bc-275">Note the following points:</span></span>

- <span data-ttu-id="d58bc-276">Il provider di tipi accetta due parametri statici: il `pattern`, che è obbligatorio e il `options`, quali sono facoltativi (perché è stato specificato un valore predefinito).</span><span class="sxs-lookup"><span data-stu-id="d58bc-276">The type provider takes two static parameters: the `pattern`, which is mandatory, and the `options`, which are optional (because a default value is provided).</span></span>

- <span data-ttu-id="d58bc-277">Dopo che vengono forniti gli argomenti statici, si crea un'istanza dell'espressione regolare.</span><span class="sxs-lookup"><span data-stu-id="d58bc-277">After the static arguments are supplied, you create an instance of the regular expression.</span></span> <span data-ttu-id="d58bc-278">L'istanza genererà un'eccezione se l'espressione regolare non è valido e questo errore verrà segnalato agli utenti.</span><span class="sxs-lookup"><span data-stu-id="d58bc-278">This instance will throw an exception if the Regex is malformed, and this error will be reported to users.</span></span>

- <span data-ttu-id="d58bc-279">All'interno di `DefineStaticParameters` callback, si definisce il tipo che verrà restituito dopo che gli argomenti vengono forniti.</span><span class="sxs-lookup"><span data-stu-id="d58bc-279">Within the `DefineStaticParameters` callback, you define the type that will be returned after the arguments are supplied.</span></span>

- <span data-ttu-id="d58bc-280">Questo codice imposta `HideObjectMethods` su true in modo che l'esperienza IntelliSense rimarrà semplificata.</span><span class="sxs-lookup"><span data-stu-id="d58bc-280">This code sets `HideObjectMethods` to true so that the IntelliSense experience will remain streamlined.</span></span> <span data-ttu-id="d58bc-281">Questo attributo determina il `Equals`, `GetHashCode`, `Finalize`, e `GetType` membri da eliminare da elenchi di IntelliSense per un oggetto specificato.</span><span class="sxs-lookup"><span data-stu-id="d58bc-281">This attribute causes the `Equals`, `GetHashCode`, `Finalize`, and `GetType` members to be suppressed from IntelliSense lists for a provided object.</span></span>

- <span data-ttu-id="d58bc-282">Si utilizza `obj` come tipo di base del metodo, ma si userà un `Regex` oggetto come rappresentazione di runtime di questo tipo, come illustrato nell'esempio successivo.</span><span class="sxs-lookup"><span data-stu-id="d58bc-282">You use `obj` as the base type of the method, but you’ll use a `Regex` object as the runtime representation of this type, as the next example shows.</span></span>

- <span data-ttu-id="d58bc-283">La chiamata per il `Regex` costruttore genera un <xref:System.ArgumentException> quando un'espressione regolare non è valida.</span><span class="sxs-lookup"><span data-stu-id="d58bc-283">The call to the `Regex` constructor throws a <xref:System.ArgumentException> when a regular expression isn’t valid.</span></span> <span data-ttu-id="d58bc-284">Il compilatore intercetta questa eccezione e segnala all'utente un messaggio di errore in fase di compilazione o nell'editor di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="d58bc-284">The compiler catches this exception and reports an error message to the user at compile time or in the Visual Studio editor.</span></span> <span data-ttu-id="d58bc-285">Questa eccezione consente le espressioni regolari per essere convalidato ma non in esecuzione un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="d58bc-285">This exception enables regular expressions to be validated without running an application.</span></span>

<span data-ttu-id="d58bc-286">Il tipo definito in precedenza non è ancora utile poiché non contiene qualsiasi proprietà o metodi significativi.</span><span class="sxs-lookup"><span data-stu-id="d58bc-286">The type defined above isn't useful yet because it doesn’t contain any meaningful methods or properties.</span></span> <span data-ttu-id="d58bc-287">In primo luogo, aggiungere un valore statico `IsMatch` metodo:</span><span class="sxs-lookup"><span data-stu-id="d58bc-287">First, add a static `IsMatch` method:</span></span>

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

<span data-ttu-id="d58bc-288">Il codice precedente definisce un metodo `IsMatch`, che accetta come input una stringa e restituisce un `bool`.</span><span class="sxs-lookup"><span data-stu-id="d58bc-288">The previous code defines a method `IsMatch`, which takes a string as input and returns a `bool`.</span></span> <span data-ttu-id="d58bc-289">L'unica parte complicata consiste nell'utilizzare il `args` argomento all'interno di `InvokeCode` definizione.</span><span class="sxs-lookup"><span data-stu-id="d58bc-289">The only tricky part is the use of the `args` argument within the `InvokeCode` definition.</span></span> <span data-ttu-id="d58bc-290">In questo esempio `args` è riportato un elenco di offerte che rappresenta gli argomenti per questo metodo.</span><span class="sxs-lookup"><span data-stu-id="d58bc-290">In this example, `args` is a list of quotations that represents the arguments to this method.</span></span> <span data-ttu-id="d58bc-291">Se il metodo è un metodo di istanza, il primo argomento rappresenta il `this` argomento.</span><span class="sxs-lookup"><span data-stu-id="d58bc-291">If the method is an instance method, the first argument represents the `this` argument.</span></span> <span data-ttu-id="d58bc-292">Tuttavia, per un metodo statico, gli argomenti sono tutto senza l'esplicita al metodo.</span><span class="sxs-lookup"><span data-stu-id="d58bc-292">However, for a static method, the arguments are all just the explicit arguments to the method.</span></span> <span data-ttu-id="d58bc-293">Si noti che il tipo del valore tra virgolette deve corrispondere al tipo restituito specificato (in questo caso, `bool`).</span><span class="sxs-lookup"><span data-stu-id="d58bc-293">Note that the type of the quoted value should match the specified return type (in this case, `bool`).</span></span> <span data-ttu-id="d58bc-294">Si noti inoltre che questo codice Usa il `AddXmlDoc` metodo per assicurarsi che il metodo specificato è inoltre utile documentazione, che è possibile fornire IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="d58bc-294">Also note that this code uses the `AddXmlDoc` method to make sure that the provided method also has useful documentation, which you can supply through IntelliSense.</span></span>

<span data-ttu-id="d58bc-295">Successivamente, aggiungere un'istanza del metodo di corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="d58bc-295">Next, add an instance Match method.</span></span> <span data-ttu-id="d58bc-296">Tuttavia, questo metodo deve restituire un valore di un oggetto fornito `Match` tipo in modo che i gruppi sono accessibili in modo fortemente tipizzato.</span><span class="sxs-lookup"><span data-stu-id="d58bc-296">However, this method should return a value of a provided `Match` type so that the groups can be accessed in a strongly typed fashion.</span></span> <span data-ttu-id="d58bc-297">In questo modo, si dichiara prima di tutto la `Match` tipo.</span><span class="sxs-lookup"><span data-stu-id="d58bc-297">Thus, you first declare the `Match` type.</span></span> <span data-ttu-id="d58bc-298">Poiché questo tipo dipende il criterio è stato fornito come argomento statico, questo tipo deve essere annidato all'interno della definizione di tipo con parametri:</span><span class="sxs-lookup"><span data-stu-id="d58bc-298">Because this type depends on the pattern that was supplied as a static argument, this type must be nested within the parameterized type definition:</span></span>

```fsharp
let matchTy = 
    ProvidedTypeDefinition(
        "MatchType", 
        baseType = Some baseTy, 
        hideObjectMethods = true)

ty.AddMember matchTy
```

<span data-ttu-id="d58bc-299">È quindi possibile aggiungere una proprietà al tipo di corrispondenza per ogni gruppo.</span><span class="sxs-lookup"><span data-stu-id="d58bc-299">You then add one property to the Match type for each group.</span></span> <span data-ttu-id="d58bc-300">In fase di esecuzione, una corrispondenza è rappresentata come un <xref:System.Text.RegularExpressions.Match> valore, pertanto la quotation che definisce la proprietà è necessario usare il <xref:System.Text.RegularExpressions.Match.Groups> indicizzato per ottenere il gruppo pertinente.</span><span class="sxs-lookup"><span data-stu-id="d58bc-300">At runtime, a match is represented as a <xref:System.Text.RegularExpressions.Match> value, so the quotation that defines the property must use the <xref:System.Text.RegularExpressions.Match.Groups> indexed property to get the relevant group.</span></span>

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

<span data-ttu-id="d58bc-301">Anche in questo caso, si noti che si aggiunge la documentazione XML per la proprietà fornita.</span><span class="sxs-lookup"><span data-stu-id="d58bc-301">Again, note that you’re adding XML documentation to the provided property.</span></span> <span data-ttu-id="d58bc-302">Si noti inoltre che una proprietà può essere letti se un `GetterCode` vengono fornite funzioni e le proprietà possono essere scritti se un `SetterCode` vengono fornite funzioni, in modo che la proprietà risulta è di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="d58bc-302">Also note that a property can be read if a `GetterCode` function is provided, and the property can be written if a `SetterCode` function is provided, so the resulting property is read only.</span></span>

<span data-ttu-id="d58bc-303">Ora è possibile creare un metodo di istanza che restituisce un valore di questo `Match` tipo:</span><span class="sxs-lookup"><span data-stu-id="d58bc-303">Now you can create an instance method that returns a value of this `Match` type:</span></span>

```fsharp
let matchMethod = 
    ProvidedMethod(
        methodName = "Match", 
        parameters = [ProvidedParameter("input", typeof<string>)], 
        returnType = matchTy, 
        invokeCode = fun args -> <@@ ((%%args.[0]:obj) :?> Regex).Match(%%args.[1]) :> obj @@>)

matchMeth.AddXmlDoc "Searches the specified input string for the first ocurrence of this regular expression" 

ty.AddMember matchMeth
```

<span data-ttu-id="d58bc-304">Poiché si sta creando un metodo di istanza `args.[0]` rappresenta il `RegexTyped` istanza su cui viene chiamato il metodo, e `args.[1]` è l'argomento di input.</span><span class="sxs-lookup"><span data-stu-id="d58bc-304">Because you are creating an instance method, `args.[0]` represents the `RegexTyped` instance on which the method is being called, and `args.[1]` is the input argument.</span></span>

<span data-ttu-id="d58bc-305">Infine, fornire un costruttore in modo che è possibile creare istanze del tipo fornito.</span><span class="sxs-lookup"><span data-stu-id="d58bc-305">Finally, provide a constructor so that instances of the provided type can be created.</span></span>

```fsharp
let ctor = 
    ProvidedConstructor(
        parameters = [], 
        invokeCode = fun args -> <@@ Regex(pattern, options) :> obj @@>)

ctor.AddXmlDoc("Initializes a regular expression instance.")

ty.AddMember ctor
```

<span data-ttu-id="d58bc-306">Il costruttore Cancella semplicemente per la creazione di un'istanza di espressioni regolari di .NET standard, che è nuovamente sottoposto a boxing a un oggetto perché `obj` è la cancellazione del tipo fornito.</span><span class="sxs-lookup"><span data-stu-id="d58bc-306">The constructor merely erases to the creation of a standard .NET Regex instance, which is again boxed to an object because `obj` is the erasure of the provided type.</span></span> <span data-ttu-id="d58bc-307">Con questa modifica, l'esempio di utilizzo di API che specificata in precedenza nell'argomento funziona come previsto.</span><span class="sxs-lookup"><span data-stu-id="d58bc-307">With that change, the sample API usage that specified earlier in the topic works as expected.</span></span> <span data-ttu-id="d58bc-308">Il codice seguente è completo e finale:</span><span class="sxs-lookup"><span data-stu-id="d58bc-308">The following code is complete and final:</span></span>

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
                matchMeth.AddXmlDoc "Searches the specified input string for the first occurence of this regular expression"

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

### <a name="key-lessons"></a><span data-ttu-id="d58bc-309">Lezioni principali</span><span class="sxs-lookup"><span data-stu-id="d58bc-309">Key Lessons</span></span>

<span data-ttu-id="d58bc-310">In questa sezione viene spiegato come creare un provider di tipi che agisce sui relativi parametri statici.</span><span class="sxs-lookup"><span data-stu-id="d58bc-310">This section explained how to create a type provider that operates on its static parameters.</span></span> <span data-ttu-id="d58bc-311">Il provider controlla il parametro static e offre operazioni in base al relativo valore.</span><span class="sxs-lookup"><span data-stu-id="d58bc-311">The provider checks the static parameter and provides operations based on its value.</span></span>

## <a name="a-type-provider-that-is-backed-by-local-data"></a><span data-ttu-id="d58bc-312">Un Provider di tipi supportato da dati locali</span><span class="sxs-lookup"><span data-stu-id="d58bc-312">A Type Provider That Is Backed By Local Data</span></span>

<span data-ttu-id="d58bc-313">Spesso è possibile che il provider di tipi per presentare le API basate su non solo parametri statici, ma anche informazioni provenienti da sistemi locali o remoti.</span><span class="sxs-lookup"><span data-stu-id="d58bc-313">Frequently you might want type providers to present APIs based on not only static parameters but also information from local or remote systems.</span></span> <span data-ttu-id="d58bc-314">Questa sezione vengono illustrati i provider di tipi che si basano sui dati locali, ad esempio file di dati locali.</span><span class="sxs-lookup"><span data-stu-id="d58bc-314">This section discusses type providers that are based on local data, such as local data files.</span></span>

### <a name="simple-csv-file-provider"></a><span data-ttu-id="d58bc-315">Provider di File CSV semplice</span><span class="sxs-lookup"><span data-stu-id="d58bc-315">Simple CSV File Provider</span></span>

<span data-ttu-id="d58bc-316">Un esempio semplice, prendere in considerazione un provider di tipi per l'accesso ai dati scientifici in formato CSV (Comma Separated Value).</span><span class="sxs-lookup"><span data-stu-id="d58bc-316">As a simple example, consider a type provider for accessing scientific data in Comma Separated Value (CSV) format.</span></span> <span data-ttu-id="d58bc-317">In questa sezione si presuppone che i file CSV deve contenere una riga di intestazione seguita da dati a virgola mobile, come illustrato nella tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="d58bc-317">This section assumes that the CSV files contain a header row followed by floating point data, as the following table illustrates:</span></span>

|<span data-ttu-id="d58bc-318">Distanza (misurazione)</span><span class="sxs-lookup"><span data-stu-id="d58bc-318">Distance (meter)</span></span>|<span data-ttu-id="d58bc-319">Tempo (secondo)</span><span class="sxs-lookup"><span data-stu-id="d58bc-319">Time (second)</span></span>|
|----------------|-------------|
|<span data-ttu-id="d58bc-320">50.0</span><span class="sxs-lookup"><span data-stu-id="d58bc-320">50.0</span></span>|<span data-ttu-id="d58bc-321">3.7</span><span class="sxs-lookup"><span data-stu-id="d58bc-321">3.7</span></span>|
|<span data-ttu-id="d58bc-322">100.0</span><span class="sxs-lookup"><span data-stu-id="d58bc-322">100.0</span></span>|<span data-ttu-id="d58bc-323">5.2</span><span class="sxs-lookup"><span data-stu-id="d58bc-323">5.2</span></span>|
|<span data-ttu-id="d58bc-324">150.0</span><span class="sxs-lookup"><span data-stu-id="d58bc-324">150.0</span></span>|<span data-ttu-id="d58bc-325">6.4</span><span class="sxs-lookup"><span data-stu-id="d58bc-325">6.4</span></span>|

<span data-ttu-id="d58bc-326">In questa sezione viene illustrato come fornire un tipo che è possibile usare per ottenere le righe con un `Distance` vlastnosti typu `float<meter>` e una `Time` vlastnosti typu `float<second>`.</span><span class="sxs-lookup"><span data-stu-id="d58bc-326">This section shows how to provide a type that you can use to get rows with a `Distance` property of type `float<meter>` and a `Time` property of type `float<second>`.</span></span> <span data-ttu-id="d58bc-327">Per semplicità, i presupposti seguenti:</span><span class="sxs-lookup"><span data-stu-id="d58bc-327">For simplicity, the following assumptions are made:</span></span>

- <span data-ttu-id="d58bc-328">I nomi di intestazione sono un'unità di misura o avere il formato "Nome (unità)" e non contengono virgole.</span><span class="sxs-lookup"><span data-stu-id="d58bc-328">Header names are either unit-less or have the form "Name (unit)" and don't contain commas.</span></span>

- <span data-ttu-id="d58bc-329">Le unità sono tutte le unità Systeme International (SI) come le [Microsoft.FSharp.Data.UnitSystems.SI.UnitNames (modulo) (F #)](https://msdn.microsoft.com/library/3cb43485-11f5-4aa7-a779-558f19d4013b) modulo definisce.</span><span class="sxs-lookup"><span data-stu-id="d58bc-329">Units are all Systeme International (SI) units as the [Microsoft.FSharp.Data.UnitSystems.SI.UnitNames Module (F#)](https://msdn.microsoft.com/library/3cb43485-11f5-4aa7-a779-558f19d4013b) module defines.</span></span>

- <span data-ttu-id="d58bc-330">Le unità sono tutti semplice (ad esempio, controllare) piuttosto che composta (ad esempio, misuratore/secondo).</span><span class="sxs-lookup"><span data-stu-id="d58bc-330">Units are all simple (for example, meter) rather than compound (for example, meter/second).</span></span>

- <span data-ttu-id="d58bc-331">Tutte le colonne contengono dati a virgola mobile.</span><span class="sxs-lookup"><span data-stu-id="d58bc-331">All columns contain floating point data.</span></span>

<span data-ttu-id="d58bc-332">Un provider di più completo sarebbe Allentare queste restrizioni.</span><span class="sxs-lookup"><span data-stu-id="d58bc-332">A more complete provider would loosen these restrictions.</span></span>

<span data-ttu-id="d58bc-333">Anche in questo caso il primo passaggio è da considerare come dovrebbe apparire l'API.</span><span class="sxs-lookup"><span data-stu-id="d58bc-333">Again the first step is to consider how the API should look.</span></span> <span data-ttu-id="d58bc-334">Dato un file `info.csv` con i contenuti della tabella precedente (nel formato delimitato da virgole), gli utenti del provider possono scrivere codice simile all'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="d58bc-334">Given an `info.csv` file with the contents from the previous table (in comma-separated format), users of the provider should be able to write code that resembles the following example:</span></span>

```fsharp
let info = new MiniCsv<"info.csv">()
for row in info.Data do
let time = row.Time
printfn "%f" (float time)
```

<span data-ttu-id="d58bc-335">In questo caso, il compilatore deve convertire queste chiamate in qualcosa di simile all'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="d58bc-335">In this case, the compiler should convert these calls into something like the following example:</span></span>

```fsharp
let info = new CsvFile("info.csv")
for row in info.Data do
let (time:float) = row.[1]
printfn "%f" (float time)
```

<span data-ttu-id="d58bc-336">La traduzione ottima richiederà il provider di tipi definire un reale `CsvFile` tipo nell'assembly del provider di tipi.</span><span class="sxs-lookup"><span data-stu-id="d58bc-336">The optimal translation will require the type provider to define a real `CsvFile` type in the type provider's assembly.</span></span> <span data-ttu-id="d58bc-337">Provider di tipi si basano spesso su alcuni tipi di helper e metodi per eseguire il wrapping importanti per la logica.</span><span class="sxs-lookup"><span data-stu-id="d58bc-337">Type providers often rely on a few helper types and methods to wrap important logic.</span></span> <span data-ttu-id="d58bc-338">Poiché le misure vengono cancellate in fase di esecuzione, è possibile usare un `float[]` come tipo cancellato per una riga.</span><span class="sxs-lookup"><span data-stu-id="d58bc-338">Because measures are erased at runtime, you can use a `float[]` as the erased type for a row.</span></span> <span data-ttu-id="d58bc-339">Il compilatore considererà come se avessero tipi differenti misura colonne diverse.</span><span class="sxs-lookup"><span data-stu-id="d58bc-339">The compiler will treat different columns as having different measure types.</span></span> <span data-ttu-id="d58bc-340">Ad esempio, la prima colonna nel nostro esempio dispone di tipo `float<meter>`, mentre la seconda è `float<second>`.</span><span class="sxs-lookup"><span data-stu-id="d58bc-340">For example, the first column in our example has type `float<meter>`, and the second has `float<second>`.</span></span> <span data-ttu-id="d58bc-341">Tuttavia, la rappresentazione cancellata può rimanere piuttosto semplice.</span><span class="sxs-lookup"><span data-stu-id="d58bc-341">However, the erased representation can remain quite simple.</span></span>

<span data-ttu-id="d58bc-342">Il codice seguente illustra le principali dell'implementazione.</span><span class="sxs-lookup"><span data-stu-id="d58bc-342">The following code shows the core of the implementation.</span></span>

```fsharp
// Simple type wrapping CSV data
type CsvFile(filename) =
    // Cache the sequence of all data lines (all lines but the first)
    let data = 
        seq { for line in File.ReadAllLines(filename) |> Seq.skip 1 do
                 yield line.Split(',') |> Array.map float }
        |> Seq.cache
    member __.Data = data

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

<span data-ttu-id="d58bc-343">Tenere presente i punti seguenti circa l'implementazione:</span><span class="sxs-lookup"><span data-stu-id="d58bc-343">Note the following points about the implementation:</span></span>

- <span data-ttu-id="d58bc-344">Costruttori di overload consentono il file originale o uno che dispone di uno schema identico da leggere.</span><span class="sxs-lookup"><span data-stu-id="d58bc-344">Overloaded constructors allow either the original file or one that has an identical schema to be read.</span></span> <span data-ttu-id="d58bc-345">Questo modello è comune quando si scrive un provider di tipi per le origini dati locali o remoti, e questo modello consente a un file locale da utilizzare come modello per i dati remoti.</span><span class="sxs-lookup"><span data-stu-id="d58bc-345">This pattern is common when you write a type provider for local or remote data sources, and this pattern allows a local file to be used as the template for remote data.</span></span>

- <span data-ttu-id="d58bc-346">È possibile usare la [TypeProviderConfig](https://msdn.microsoft.com/library/1cda7b9a-3d07-475d-9315-d65e1c97eb44) valore che viene passato al costruttore del provider di tipo per risolvere i nomi di file relativo.</span><span class="sxs-lookup"><span data-stu-id="d58bc-346">You can use the [TypeProviderConfig](https://msdn.microsoft.com/library/1cda7b9a-3d07-475d-9315-d65e1c97eb44) value that’s passed in to the type provider constructor to resolve relative file names.</span></span>

- <span data-ttu-id="d58bc-347">È possibile usare il `AddDefinitionLocation` metodo per definire la posizione delle proprietà specificata.</span><span class="sxs-lookup"><span data-stu-id="d58bc-347">You can use the `AddDefinitionLocation` method to define the location of the provided properties.</span></span> <span data-ttu-id="d58bc-348">Pertanto, se si usa `Go To Definition` su una proprietà specificata, il file CSV verrà aperto in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="d58bc-348">Therefore, if you use `Go To Definition` on a provided property, the CSV file will open in Visual Studio.</span></span>

- <span data-ttu-id="d58bc-349">È possibile usare la `ProvidedMeasureBuilder` tipo per cercare le unità del sistema internazionale di misura e generare il relativo `float<_>` tipi.</span><span class="sxs-lookup"><span data-stu-id="d58bc-349">You can use the `ProvidedMeasureBuilder` type to look up the SI units and to generate the relevant `float<_>` types.</span></span>

### <a name="key-lessons"></a><span data-ttu-id="d58bc-350">Lezioni principali</span><span class="sxs-lookup"><span data-stu-id="d58bc-350">Key Lessons</span></span>

<span data-ttu-id="d58bc-351">In questa sezione viene spiegato come creare un provider di tipi per un'origine dati locale con un semplice schema contenuta nell'origine dati stessa.</span><span class="sxs-lookup"><span data-stu-id="d58bc-351">This section explained how to create a type provider for a local data source with a simple schema that's contained in the data source itself.</span></span>

## <a name="going-further"></a><span data-ttu-id="d58bc-352">Approfondimenti</span><span class="sxs-lookup"><span data-stu-id="d58bc-352">Going Further</span></span>

<span data-ttu-id="d58bc-353">Le sezioni seguenti includono alcuni suggerimenti per approfondire l'argomento.</span><span class="sxs-lookup"><span data-stu-id="d58bc-353">The following sections include suggestions for further study.</span></span>

### <a name="a-look-at-the-compiled-code-for-erased-types"></a><span data-ttu-id="d58bc-354">Esaminare il codice compilato per i tipi cancellati</span><span class="sxs-lookup"><span data-stu-id="d58bc-354">A Look at the Compiled Code for Erased Types</span></span>

<span data-ttu-id="d58bc-355">Per avere un'idea di come l'utilizzo del provider del tipo corrispondente al codice che viene generato, esaminare la funzione seguente usando il `HelloWorldTypeProvider` utilizzato in precedenza in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="d58bc-355">To give you some idea of how the use of the type provider corresponds to the code that's emitted, look at the following function by using the `HelloWorldTypeProvider` that's used earlier in this topic.</span></span>

```fsharp
let function1 () = 
    let obj1 = Samples.HelloWorldTypeProvider.Type1("some data")
    obj1.InstanceProperty
```

<span data-ttu-id="d58bc-356">Ecco un'immagine del codice decompilato usando ildasm.exe risulta:</span><span class="sxs-lookup"><span data-stu-id="d58bc-356">Here’s an image of the resulting code decompiled by using ildasm.exe:</span></span>

```
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

<span data-ttu-id="d58bc-357">Come illustrato nell'esempio, tutti i riferimenti di tipo `Type1` e il `InstanceProperty` proprietà sono state cancellate, lasciando solo le operazioni sui tipi di runtime coinvolti.</span><span class="sxs-lookup"><span data-stu-id="d58bc-357">As the example shows, all mentions of the type `Type1` and the `InstanceProperty` property have been erased, leaving only operations on the runtime types involved.</span></span>

### <a name="design-and-naming-conventions-for-type-providers"></a><span data-ttu-id="d58bc-358">Progettazione e convenzioni di denominazione per i provider di tipi</span><span class="sxs-lookup"><span data-stu-id="d58bc-358">Design and Naming Conventions for Type Providers</span></span>

<span data-ttu-id="d58bc-359">Osservare le convenzioni seguenti durante la creazione di provider di tipi.</span><span class="sxs-lookup"><span data-stu-id="d58bc-359">Observe the following conventions when authoring type providers.</span></span>

<span data-ttu-id="d58bc-360">**Provider per i protocolli di connettività** In generale, i nomi del provider la maggior parte delle DLL per i protocolli di connettività dei dati e il servizio, ad esempio le connessioni di OData o SQL, devono terminare `TypeProvider` o `TypeProviders`.</span><span class="sxs-lookup"><span data-stu-id="d58bc-360">**Providers for Connectivity Protocols** In general, names of most provider DLLs for data and service connectivity protocols, such as OData or SQL connections, should end in `TypeProvider` or `TypeProviders`.</span></span> <span data-ttu-id="d58bc-361">Ad esempio, usare un nome DLL che è simile alla stringa seguente:</span><span class="sxs-lookup"><span data-stu-id="d58bc-361">For example, use a DLL name that resembles the following string:</span></span>

```
  Fabrikam.Management.BasicTypeProviders.dll
```

<span data-ttu-id="d58bc-362">Assicurarsi che i tipi forniti sono membri dello spazio dei nomi corrispondenti e indicano il protocollo di connettività che è stata implementata:</span><span class="sxs-lookup"><span data-stu-id="d58bc-362">Ensure that your provided types are members of the corresponding namespace, and indicate the connectivity protocol that you implemented:</span></span>

```
  Fabrikam.Management.BasicTypeProviders.WmiConnection<…>
  Fabrikam.Management.BasicTypeProviders.DataProtocolConnection<…>
```

<span data-ttu-id="d58bc-363">**I provider di utilità per la scrittura di codice generale**.</span><span class="sxs-lookup"><span data-stu-id="d58bc-363">**Utility Providers for General Coding**.</span></span>  <span data-ttu-id="d58bc-364">Per un'utilità provider di tipi, ad esempio che per le espressioni regolari, il provider di tipi può essere parte di una libreria di base, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="d58bc-364">For a utility type provider such as that for regular expressions, the type provider may be part of a base library, as the following example shows:</span></span>

```fsharp
  #r "Fabrikam.Core.Text.Utilities.dll"
```

<span data-ttu-id="d58bc-365">In questo caso, il tipo fornito apparirebbe in un momento appropriato in base alle convenzioni di progettazione .NET normale:</span><span class="sxs-lookup"><span data-stu-id="d58bc-365">In this case, the provided type would appear at an appropriate point according to normal .NET design conventions:</span></span>

```fsharp
  open Fabrikam.Core.Text.RegexTyped
  
  let regex = new RegexTyped<"a+b+a+b+">()
```

<span data-ttu-id="d58bc-366">**Zdroje dat singleton**.</span><span class="sxs-lookup"><span data-stu-id="d58bc-366">**Singleton Data Sources**.</span></span> <span data-ttu-id="d58bc-367">Alcuni provider di tipi connettersi a un'origine dati dedicato e fornire solo i dati.</span><span class="sxs-lookup"><span data-stu-id="d58bc-367">Some type providers connect to a single dedicated data source and provide only data.</span></span> <span data-ttu-id="d58bc-368">In questo caso, è necessario eliminare il `TypeProvider` suffisso e usare le normali convenzioni di denominazione .NET:</span><span class="sxs-lookup"><span data-stu-id="d58bc-368">In this case, you should drop the `TypeProvider` suffix and use normal conventions for .NET naming:</span></span>

```fsharp
#r "Fabrikam.Data.Freebase.dll"
  
let data = Fabrikam.Data.Freebase.Astronomy.Asteroids
```

<span data-ttu-id="d58bc-369">Per altre informazioni, vedere il `GetConnection` progettare convenzione che è descritti più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="d58bc-369">For more information, see the `GetConnection` design convention that's described later in this topic.</span></span>

### <a name="design-patterns-for-type-providers"></a><span data-ttu-id="d58bc-370">Schemi progettuali per provider di tipi</span><span class="sxs-lookup"><span data-stu-id="d58bc-370">Design Patterns for Type Providers</span></span>

<span data-ttu-id="d58bc-371">Le sezioni seguenti descrivono i modelli di progettazione che è possibile usare durante la creazione di provider di tipi.</span><span class="sxs-lookup"><span data-stu-id="d58bc-371">The following sections describe design patterns you can use when authoring type providers.</span></span>

#### <a name="the-getconnection-design-pattern"></a><span data-ttu-id="d58bc-372">Lo schema progettuale GetConnection</span><span class="sxs-lookup"><span data-stu-id="d58bc-372">The GetConnection Design Pattern</span></span>

<span data-ttu-id="d58bc-373">La maggior parte dei provider di tipi deve essere scritto per utilizzare il `GetConnection` modello viene usato per il provider di tipi in FSharp.Data.TypeProviders.dll, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="d58bc-373">Most type providers should be written to use the `GetConnection` pattern that's used by the type providers in FSharp.Data.TypeProviders.dll, as the following example shows:</span></span>

```fsharp
#r "Fabrikam.Data.WebDataStore.dll"

type Service = Fabrikam.Data.WebDataStore<…static connection parameters…>

let connection = Service.GetConnection(…dynamic connection parameters…)

let data = connection.Astronomy.Asteroids
```

#### <a name="type-providers-backed-by-remote-data-and-services"></a><span data-ttu-id="d58bc-374">Provider di tipi supportati da servizi e dei dati remota</span><span class="sxs-lookup"><span data-stu-id="d58bc-374">Type Providers Backed By Remote Data and Services</span></span>

<span data-ttu-id="d58bc-375">Prima di creare un provider di tipi supportato da servizi e dei dati remota, è necessario considerare una gamma di problemi che vengono svolte nella programmazione connesso.</span><span class="sxs-lookup"><span data-stu-id="d58bc-375">Before you create a type provider that's backed by remote data and services, you must consider a range of issues that are inherent in connected programming.</span></span> <span data-ttu-id="d58bc-376">Tali problemi riguardano le considerazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="d58bc-376">These issues include the following considerations:</span></span>

- <span data-ttu-id="d58bc-377">mapping dello schema</span><span class="sxs-lookup"><span data-stu-id="d58bc-377">schema mapping</span></span>

- <span data-ttu-id="d58bc-378">attività e invalidamento in presenza di modifica dello schema</span><span class="sxs-lookup"><span data-stu-id="d58bc-378">liveness and invalidation in the presence of schema change</span></span>

- <span data-ttu-id="d58bc-379">la memorizzazione nella cache dello schema</span><span class="sxs-lookup"><span data-stu-id="d58bc-379">schema caching</span></span>

- <span data-ttu-id="d58bc-380">implementazioni asincrone di operazioni di accesso ai dati</span><span class="sxs-lookup"><span data-stu-id="d58bc-380">asynchronous implementations of data access operations</span></span>

- <span data-ttu-id="d58bc-381">supporto delle query, incluse le query LINQ</span><span class="sxs-lookup"><span data-stu-id="d58bc-381">supporting queries, including LINQ queries</span></span>

- <span data-ttu-id="d58bc-382">le credenziali e autenticazione</span><span class="sxs-lookup"><span data-stu-id="d58bc-382">credentials and authentication</span></span>

<span data-ttu-id="d58bc-383">In questo argomento non Esplora ulteriormente questi problemi.</span><span class="sxs-lookup"><span data-stu-id="d58bc-383">This topic doesn't explore these issues further.</span></span>

### <a name="additional-authoring-techniques"></a><span data-ttu-id="d58bc-384">Ulteriori informazioni sulle tecniche di creazione e modifica</span><span class="sxs-lookup"><span data-stu-id="d58bc-384">Additional Authoring Techniques</span></span>

<span data-ttu-id="d58bc-385">Quando si scrive il proprio provider di tipi, si potrebbe voler usare le seguenti tecniche aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="d58bc-385">When you write your own type providers, you might want to use the following additional techniques.</span></span>

### <a name="creating-types-and-members-on-demand"></a><span data-ttu-id="d58bc-386">Creazione di tipi e membri On Demand</span><span class="sxs-lookup"><span data-stu-id="d58bc-386">Creating Types and Members On-Demand</span></span>

<span data-ttu-id="d58bc-387">L'API ProvidedType è posticipata le versioni di AddMember.</span><span class="sxs-lookup"><span data-stu-id="d58bc-387">The ProvidedType API has delayed versions of AddMember.</span></span>

```fsharp
  type ProvidedType =
      member AddMemberDelayed  : (unit -> MemberInfo)      -> unit
      member AddMembersDelayed : (unit -> MemberInfo list) -> unit
```

<span data-ttu-id="d58bc-388">Queste versioni consentono di creare spazi on demand di tipi.</span><span class="sxs-lookup"><span data-stu-id="d58bc-388">These versions are used to create on-demand spaces of types.</span></span>

### <a name="providing-array-types-and-generic-type-instantiations"></a><span data-ttu-id="d58bc-389">Che fornisce i tipi di matrice e le creazioni di istanze di tipo generico</span><span class="sxs-lookup"><span data-stu-id="d58bc-389">Providing Array types and Generic Type Instantiations</span></span>

<span data-ttu-id="d58bc-390">Come specificato di membri (le cui firme includono i tipi di matrice, tipi byref e le creazioni di istanze di tipi generici) usando il normale `MakeArrayType`, `MakePointerType`, e `MakeGenericType` in qualsiasi istanza di <xref:System.Type>, tra cui `ProvidedTypeDefinitions`.</span><span class="sxs-lookup"><span data-stu-id="d58bc-390">You make provided members (whose signatures include array types, byref types, and instantiations of generic types) by using the normal `MakeArrayType`, `MakePointerType`, and `MakeGenericType` on any instance of <xref:System.Type>, including `ProvidedTypeDefinitions`.</span></span>

> [!NOTE]
> <span data-ttu-id="d58bc-391">In alcuni casi potrebbe essere necessario usare l'helper in `ProvidedTypeBuilder.MakeGenericType`.</span><span class="sxs-lookup"><span data-stu-id="d58bc-391">In some cases you may have to use the helper in `ProvidedTypeBuilder.MakeGenericType`.</span></span>  <span data-ttu-id="d58bc-392">Vedere le [documentazione del SDK del Provider di tipo](https://github.com/fsprojects/FSharp.TypeProviders.SDK/blob/master/README.md#explicit-construction-of-code-makegenerictype-makegenericmethod-and-uncheckedquotations) per altri dettagli.</span><span class="sxs-lookup"><span data-stu-id="d58bc-392">See the [Type Provider SDK documentation](https://github.com/fsprojects/FSharp.TypeProviders.SDK/blob/master/README.md#explicit-construction-of-code-makegenerictype-makegenericmethod-and-uncheckedquotations) for more details.</span></span>

### <a name="providing-unit-of-measure-annotations"></a><span data-ttu-id="d58bc-393">Fornendo l'unità di misura annotazioni</span><span class="sxs-lookup"><span data-stu-id="d58bc-393">Providing Unit of Measure Annotations</span></span>

<span data-ttu-id="d58bc-394">L'API ProvidedTypes fornisce gli helper per fornire le annotazioni di misure.</span><span class="sxs-lookup"><span data-stu-id="d58bc-394">The ProvidedTypes API provides helpers for providing measure annotations.</span></span> <span data-ttu-id="d58bc-395">Ad esempio, specificare il tipo `float<kg>`, usare il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="d58bc-395">For example, to provide the type `float<kg>`, use the following code:</span></span>

```fsharp
  let measures = ProvidedMeasureBuilder.Default
  let kg = measures.SI "kilogram"
  let m = measures.SI "meter"
  let float_kg = measures.AnnotateType(typeof<float>,[kg])
```

  <span data-ttu-id="d58bc-396">Specificare il tipo `Nullable<decimal<kg/m^2>>`, usare il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="d58bc-396">To provide the type `Nullable<decimal<kg/m^2>>`, use the following code:</span></span>

```fsharp
  let kgpm2 = measures.Ratio(kg, measures.Square m)
  let dkgpm2 = measures.AnnotateType(typeof<decimal>,[kgpm2])
  let nullableDecimal_kgpm2 = typedefof<System.Nullable<_>>.MakeGenericType [|dkgpm2 |]
```

### <a name="accessing-project-local-or-script-local-resources"></a><span data-ttu-id="d58bc-397">L'accesso alle risorse locali del progetto o Script locali</span><span class="sxs-lookup"><span data-stu-id="d58bc-397">Accessing Project-Local or Script-Local Resources</span></span>

<span data-ttu-id="d58bc-398">Ogni istanza di un provider di tipi può essere assegnato un `TypeProviderConfig` valore durante la costruzione.</span><span class="sxs-lookup"><span data-stu-id="d58bc-398">Each instance of a type provider can be given a `TypeProviderConfig` value during construction.</span></span> <span data-ttu-id="d58bc-399">Questo valore contiene la "cartella di risoluzione" per il provider (vale a dire, la cartella di progetto per la compilazione o la directory che contiene uno script), l'elenco di assembly di riferimento e altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="d58bc-399">This value contains the "resolution folder" for the provider (that is, the project folder for the compilation or the directory that contains a script), the list of referenced assemblies, and other information.</span></span>

### <a name="invalidation"></a><span data-ttu-id="d58bc-400">Invalidamento</span><span class="sxs-lookup"><span data-stu-id="d58bc-400">Invalidation</span></span>

<span data-ttu-id="d58bc-401">I provider possono generare segnali di invalidamento per notificare al servizio di linguaggio F # che hanno modificato i presupposti dello schema.</span><span class="sxs-lookup"><span data-stu-id="d58bc-401">Providers can raise invalidation signals to notify the F# language service that the schema assumptions may have changed.</span></span> <span data-ttu-id="d58bc-402">Quando si verifica l'invalidamento, viene eseguito il rollforward un typecheck se il provider è ospitato in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="d58bc-402">When invalidation occurs, a typecheck is redone if the provider is being hosted in Visual Studio.</span></span> <span data-ttu-id="d58bc-403">Questo segnale verrà ignorato quando il provider è ospitato in F # Interactive o dal compilatore F # (fsc.exe).</span><span class="sxs-lookup"><span data-stu-id="d58bc-403">This signal will be ignored when the provider is hosted in F# Interactive or by the F# Compiler (fsc.exe).</span></span>

### <a name="caching-schema-information"></a><span data-ttu-id="d58bc-404">La memorizzazione nella cache le informazioni sullo Schema</span><span class="sxs-lookup"><span data-stu-id="d58bc-404">Caching Schema Information</span></span>

<span data-ttu-id="d58bc-405">I provider devono spesso memorizzare nella cache di accesso alle informazioni sullo schema.</span><span class="sxs-lookup"><span data-stu-id="d58bc-405">Providers must often cache access to schema information.</span></span> <span data-ttu-id="d58bc-406">I dati memorizzati nella cache devono essere archiviati tramite un nome file che viene fornito come parametro statico o come dati utente.</span><span class="sxs-lookup"><span data-stu-id="d58bc-406">The cached data should be stored by using a file name that's given as a static parameter or as user data.</span></span> <span data-ttu-id="d58bc-407">Un esempio di memorizzazione nella cache dello schema è il `LocalSchemaFile` parametro nel provider di tipi nel `FSharp.Data.TypeProviders` assembly.</span><span class="sxs-lookup"><span data-stu-id="d58bc-407">An example of schema caching is the `LocalSchemaFile` parameter in the type providers in the `FSharp.Data.TypeProviders` assembly.</span></span> <span data-ttu-id="d58bc-408">Nell'implementazione di questi provider, questo parametro statico indirizza il provider di tipi da utilizzare le informazioni dello schema nel file locale specificato anziché l'accesso all'origine dati in rete.</span><span class="sxs-lookup"><span data-stu-id="d58bc-408">In the implementation of these providers, this static parameter directs the type provider to use the schema information in the specified local file instead of accessing the data source over the network.</span></span> <span data-ttu-id="d58bc-409">Per usare le informazioni sullo schema memorizzato nella cache, è necessario impostare anche il parametro static `ForceUpdate` a `false`.</span><span class="sxs-lookup"><span data-stu-id="d58bc-409">To use cached schema information, you must also set the static parameter `ForceUpdate` to `false`.</span></span> <span data-ttu-id="d58bc-410">È possibile utilizzare una tecnica simile per consentire l'accesso ai dati online e offline.</span><span class="sxs-lookup"><span data-stu-id="d58bc-410">You could use a similar technique to enable online and offline data access.</span></span>

### <a name="backing-assembly"></a><span data-ttu-id="d58bc-411">Assembly di supporto</span><span class="sxs-lookup"><span data-stu-id="d58bc-411">Backing Assembly</span></span>

<span data-ttu-id="d58bc-412">Quando si compila un `.dll` o `.exe` file, il file con estensione DLL di supporto per i tipi generati viene collegato staticamente all'assembly risultante.</span><span class="sxs-lookup"><span data-stu-id="d58bc-412">When you compile a `.dll` or `.exe` file, the backing .dll file for generated types is statically linked into the resulting assembly.</span></span> <span data-ttu-id="d58bc-413">Questo collegamento viene creato copiando le definizioni dei tipi di linguaggio intermedio (IL) e le risorse gestite dall'assembly sottostante nell'assembly finale.</span><span class="sxs-lookup"><span data-stu-id="d58bc-413">This link is created by copying the Intermediate Language (IL) type definitions and any managed resources from the backing assembly into the final assembly.</span></span> <span data-ttu-id="d58bc-414">Quando si usa F # Interactive, il file con estensione DLL di backup non vengono copiato e invece viene caricato direttamente nel processo di F # Interactive.</span><span class="sxs-lookup"><span data-stu-id="d58bc-414">When you use F# Interactive, the backing .dll file isn't copied and is instead loaded directly into the F# Interactive process.</span></span>

### <a name="exceptions-and-diagnostics-from-type-providers"></a><span data-ttu-id="d58bc-415">Le eccezioni e diagnostica dal provider di tipi</span><span class="sxs-lookup"><span data-stu-id="d58bc-415">Exceptions and Diagnostics from Type Providers</span></span>

<span data-ttu-id="d58bc-416">Tutti gli usi di tutti i membri di tipi specificati possono generare eccezioni.</span><span class="sxs-lookup"><span data-stu-id="d58bc-416">All uses of all members from provided types may throw exceptions.</span></span> <span data-ttu-id="d58bc-417">In tutti i casi, se un provider di tipi genera un'eccezione, il compilatore host attributi l'errore per un provider di tipi specifici.</span><span class="sxs-lookup"><span data-stu-id="d58bc-417">In all cases, if a type provider throws an exception, the host compiler attributes the error to a specific type provider.</span></span>

- <span data-ttu-id="d58bc-418">Le eccezioni di tipo provider non devono mai comportare errori interni del compilatore.</span><span class="sxs-lookup"><span data-stu-id="d58bc-418">Type provider exceptions should never result in internal compiler errors.</span></span>

- <span data-ttu-id="d58bc-419">Provider di tipi non possono segnalare gli avvisi.</span><span class="sxs-lookup"><span data-stu-id="d58bc-419">Type providers can't report warnings.</span></span>

- <span data-ttu-id="d58bc-420">Quando un provider di tipi è ospitato nel compilatore F #, un ambiente di sviluppo F # o F # Interactive, vengono rilevate tutte le eccezioni da tale provider.</span><span class="sxs-lookup"><span data-stu-id="d58bc-420">When a type provider is hosted in the F# compiler, an F# development environment, or F# Interactive, all exceptions from that provider are caught.</span></span> <span data-ttu-id="d58bc-421">La proprietà del messaggio è sempre il testo dell'errore e viene visualizzata nessuna analisi dello stack.</span><span class="sxs-lookup"><span data-stu-id="d58bc-421">The Message property is always the error text, and no stack trace appears.</span></span> <span data-ttu-id="d58bc-422">Se si intende generare un'eccezione, è possibile generare gli esempi seguenti: `System.NotSupportedException`, `System.IO.IOException`, `System.Exception`.</span><span class="sxs-lookup"><span data-stu-id="d58bc-422">If you’re going to throw an exception, you can throw the following examples: `System.NotSupportedException`, `System.IO.IOException`, `System.Exception`.</span></span>

#### <a name="providing-generated-types"></a><span data-ttu-id="d58bc-423">Che fornisce i tipi generati</span><span class="sxs-lookup"><span data-stu-id="d58bc-423">Providing Generated Types</span></span>

<span data-ttu-id="d58bc-424">Finora, questo documento ha descritto come specificare i tipi cancellati.</span><span class="sxs-lookup"><span data-stu-id="d58bc-424">So far, this document has explained how to provide erased types.</span></span> <span data-ttu-id="d58bc-425">È anche possibile usare il meccanismo di provider in F # per fornire tipi generati, che vengono aggiunti come definizioni di tipi .NET reali in programma degli utenti.</span><span class="sxs-lookup"><span data-stu-id="d58bc-425">You can also use the type provider mechanism in F# to provide generated types, which are added as real .NET type definitions into the users' program.</span></span> <span data-ttu-id="d58bc-426">È necessario farvi riferimento generato tipi forniti tramite una definizione di tipo.</span><span class="sxs-lookup"><span data-stu-id="d58bc-426">You must refer to generated provided types by using a type definition.</span></span>

```fsharp
open Microsoft.FSharp.TypeProviders 

type Service = ODataService<"http://services.odata.org/Northwind/Northwind.svc/">
```

<span data-ttu-id="d58bc-427">Il codice helper ProvidedTypes-0.2 che fa parte della versione F # 3.0 offre solo supporto limitato per fornire tipi generati.</span><span class="sxs-lookup"><span data-stu-id="d58bc-427">The ProvidedTypes-0.2 helper code that is part of the F# 3.0 release has only limited support for providing generated types.</span></span> <span data-ttu-id="d58bc-428">Le istruzioni seguenti devono essere soddisfatte per una definizione di tipo generato:</span><span class="sxs-lookup"><span data-stu-id="d58bc-428">The following statements must be true for a generated type definition:</span></span>

- <span data-ttu-id="d58bc-429">`isErased` deve essere impostata su `false`.</span><span class="sxs-lookup"><span data-stu-id="d58bc-429">`isErased` must be set to `false`.</span></span>

- <span data-ttu-id="d58bc-430">Il tipo generato deve essere aggiunto a un oggetto appena costruito `ProvidedAssembly()`, che rappresenta un contenitore per i frammenti di codice generato.</span><span class="sxs-lookup"><span data-stu-id="d58bc-430">The generated type must be added to a newly constructed `ProvidedAssembly()`, which represents a container for generated code fragments.</span></span>

- <span data-ttu-id="d58bc-431">Il provider deve disporre di un assembly con un file con estensione dll .NET sottostante effettiva con un file con estensione DLL corrispondente sul disco.</span><span class="sxs-lookup"><span data-stu-id="d58bc-431">The provider must have an assembly that has an actual backing .NET .dll file with a matching .dll file on disk.</span></span>

## <a name="rules-and-limitations"></a><span data-ttu-id="d58bc-432">Regole e limitazioni</span><span class="sxs-lookup"><span data-stu-id="d58bc-432">Rules and Limitations</span></span>

<span data-ttu-id="d58bc-433">Quando si scrivono i provider di tipi, tenere le seguenti regole e le limitazioni presenti.</span><span class="sxs-lookup"><span data-stu-id="d58bc-433">When you write type providers, keep the following rules and limitations in mind.</span></span>

### <a name="provided-types-must-be-reachable"></a><span data-ttu-id="d58bc-434">Tipi forniti devono essere raggiungibili</span><span class="sxs-lookup"><span data-stu-id="d58bc-434">Provided types must be reachable</span></span>

<span data-ttu-id="d58bc-435">Tutti forniti tipi devono essere raggiungibili dai tipi non annidata.</span><span class="sxs-lookup"><span data-stu-id="d58bc-435">All provided types should be reachable from the non-nested types.</span></span> <span data-ttu-id="d58bc-436">I tipi annidati non vengono forniti nella chiamata ai `TypeProviderForNamespaces` costruttore o una chiamata a `AddNamespace`.</span><span class="sxs-lookup"><span data-stu-id="d58bc-436">The non-nested types are given in the call to the `TypeProviderForNamespaces` constructor or a call to `AddNamespace`.</span></span> <span data-ttu-id="d58bc-437">Ad esempio, se il provider fornisce un tipo `StaticClass.P : T`, è necessario assicurarsi che T è un tipo non annidato o annidati in uno.</span><span class="sxs-lookup"><span data-stu-id="d58bc-437">For example, if the provider provides a type `StaticClass.P : T`, you must ensure that T is either a non-nested type or nested under one.</span></span>

<span data-ttu-id="d58bc-438">Ad esempio, per alcuni provider esistono una classe statica, ad esempio `DataTypes` che contengono questi `T1, T2, T3, ...` tipi.</span><span class="sxs-lookup"><span data-stu-id="d58bc-438">For example, some providers have a static class such as `DataTypes` that contain these `T1, T2, T3, ...` types.</span></span> <span data-ttu-id="d58bc-439">In caso contrario, l'errore indica che è stato trovato un riferimento al tipo T in un assembly, ma non è stato possibile trovare il tipo in tale assembly.</span><span class="sxs-lookup"><span data-stu-id="d58bc-439">Otherwise, the error says that a reference to type T in assembly A was found, but the type couldn't be found in that assembly.</span></span> <span data-ttu-id="d58bc-440">Se viene visualizzato questo errore, verificare che tutti i sottotipi possono essere raggiunto dai tipi di provider.</span><span class="sxs-lookup"><span data-stu-id="d58bc-440">If this error appears, verify that all your subtypes can be reached from the provider types.</span></span> <span data-ttu-id="d58bc-441">Nota: Queste `T1, T2, T3...` tipi sono definiti i *in tempo reale* tipi.</span><span class="sxs-lookup"><span data-stu-id="d58bc-441">Note: These `T1, T2, T3...` types are referred to as the *on-the-fly* types.</span></span> <span data-ttu-id="d58bc-442">Ricordarsi di inserirle in uno spazio dei nomi accessibile o un tipo di elemento padre.</span><span class="sxs-lookup"><span data-stu-id="d58bc-442">Remember to put them in an accessible namespace or a parent type.</span></span>

### <a name="limitations-of-the-type-provider-mechanism"></a><span data-ttu-id="d58bc-443">Limitazioni del meccanismo di Provider di tipo</span><span class="sxs-lookup"><span data-stu-id="d58bc-443">Limitations of the Type Provider Mechanism</span></span>

<span data-ttu-id="d58bc-444">Il meccanismo di provider in F # presenta le limitazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="d58bc-444">The type provider mechanism in F# has the following limitations:</span></span>

- <span data-ttu-id="d58bc-445">L'infrastruttura sottostante per il provider di tipi in F # non supporta la condizione generica tipi o metodi generici forniti.</span><span class="sxs-lookup"><span data-stu-id="d58bc-445">The underlying infrastructure for type providers in F# doesn't support provided generic types or provided generic methods.</span></span>

- <span data-ttu-id="d58bc-446">Il meccanismo non supporta i tipi annidati con parametri statici.</span><span class="sxs-lookup"><span data-stu-id="d58bc-446">The mechanism doesn't support nested types with static parameters.</span></span>

## <a name="development-tips"></a><span data-ttu-id="d58bc-447">Suggerimenti per lo sviluppo</span><span class="sxs-lookup"><span data-stu-id="d58bc-447">Development Tips</span></span>

<span data-ttu-id="d58bc-448">Si potrebbero risultare utili i suggerimenti seguenti durante il processo di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="d58bc-448">You might find the following tips helpful during the development process.</span></span>

### <a name="run-two-instances-of-visual-studio"></a><span data-ttu-id="d58bc-449">Eseguire due istanze di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="d58bc-449">Run Two Instances of Visual Studio</span></span>

<span data-ttu-id="d58bc-450">È possibile sviluppare il provider di tipi in un'unica istanza e testare il provider negli altri perché il test dell'IDE richiederà un blocco sul file con estensione dll che impedisce il provider di tipi di ricompilazione.</span><span class="sxs-lookup"><span data-stu-id="d58bc-450">You can develop the type provider in one instance and test the provider in the other because the test IDE will take a lock on the .dll file that prevents the type provider from being rebuilt.</span></span> <span data-ttu-id="d58bc-451">Di conseguenza, è necessario chiudere la seconda istanza di Visual Studio mentre il provider è incorporato nella prima istanza e quindi è necessario aprire nuovamente la seconda istanza dopo il provider di compilazione.</span><span class="sxs-lookup"><span data-stu-id="d58bc-451">Thus, you must close the second instance of Visual Studio while the provider is built in the first instance, and then you must reopen the second instance after the provider is built.</span></span>

### <a name="debug-type-providers-by-using-invocations-of-fscexe"></a><span data-ttu-id="d58bc-452">Eseguire il debug di provider di tipi utilizzando le chiamate di fsc.exe</span><span class="sxs-lookup"><span data-stu-id="d58bc-452">Debug type providers by using invocations of fsc.exe</span></span>

<span data-ttu-id="d58bc-453">È possibile richiamare i provider di tipi utilizzando gli strumenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="d58bc-453">You can invoke type providers by using the following tools:</span></span>

- <span data-ttu-id="d58bc-454">FSC.exe (compilatore della riga di comando di F #)</span><span class="sxs-lookup"><span data-stu-id="d58bc-454">fsc.exe (The F# command line compiler)</span></span>

- <span data-ttu-id="d58bc-455">fsi.exe (compilatore The F # Interactive)</span><span class="sxs-lookup"><span data-stu-id="d58bc-455">fsi.exe (The F# Interactive compiler)</span></span>

- <span data-ttu-id="d58bc-456">devenv.exe (Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="d58bc-456">devenv.exe (Visual Studio)</span></span>

<span data-ttu-id="d58bc-457">Si possono spesso il debug di provider di tipi più facilmente usando fsc.exe in un file di script di test (ad esempio, script. fsx).</span><span class="sxs-lookup"><span data-stu-id="d58bc-457">You can often debug type providers most easily by using fsc.exe on a test script file (for example, script.fsx).</span></span> <span data-ttu-id="d58bc-458">È possibile avviare un debugger al prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="d58bc-458">You can launch a debugger from a command prompt.</span></span>

```
  devenv /debugexe fsc.exe script.fsx
```

  <span data-ttu-id="d58bc-459">È possibile usare la registrazione di stampa-a-stdout.</span><span class="sxs-lookup"><span data-stu-id="d58bc-459">You can use print-to-stdout logging.</span></span>

## <a name="see-also"></a><span data-ttu-id="d58bc-460">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d58bc-460">See also</span></span>

- [<span data-ttu-id="d58bc-461">Provider di tipi</span><span class="sxs-lookup"><span data-stu-id="d58bc-461">Type Providers</span></span>](index.md)
- [<span data-ttu-id="d58bc-462">il SDK del Provider di tipo</span><span class="sxs-lookup"><span data-stu-id="d58bc-462">The Type Provider SDK</span></span>](https://github.com/fsprojects/FSharp.TypeProviders.SDK)

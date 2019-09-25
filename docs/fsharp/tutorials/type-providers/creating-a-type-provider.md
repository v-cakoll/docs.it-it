---
title: 'Esercitazione: Creare un provider di tipi'
description: Informazioni su come creare provider di F# tipi personalizzati in F# 3,0 esaminando diversi provider di tipi semplici per illustrare i concetti di base.
ms.date: 02/02/2019
ms.openlocfilehash: 8d1a1fedf03437ccbacd40616cc7dc3e1da435b2
ms.sourcegitcommit: 56f1d1203d0075a461a10a301459d3aa452f4f47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/24/2019
ms.locfileid: "71214267"
---
# <a name="tutorial-create-a-type-provider"></a><span data-ttu-id="4b6d7-103">Esercitazione: Creare un provider di tipi</span><span class="sxs-lookup"><span data-stu-id="4b6d7-103">Tutorial: Create a Type Provider</span></span>

<span data-ttu-id="4b6d7-104">Il meccanismo del provider di F# tipi in è una parte significativa del supporto per la programmazione avanzata delle informazioni.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-104">The type provider mechanism in F# is a significant part of its support for information rich programming.</span></span> <span data-ttu-id="4b6d7-105">Questa esercitazione illustra come creare provider di tipi personalizzati grazie allo sviluppo di diversi provider di tipi semplici per illustrare i concetti di base.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-105">This tutorial explains how to create your own type providers by walking you through the development of several simple type providers to illustrate the basic concepts.</span></span> <span data-ttu-id="4b6d7-106">Per ulteriori informazioni sul meccanismo del provider di tipi F#in, vedere [provider di tipi](index.md).</span><span class="sxs-lookup"><span data-stu-id="4b6d7-106">For more information about the type provider mechanism in F#, see [Type Providers](index.md).</span></span>

<span data-ttu-id="4b6d7-107">L' F# ecosistema contiene una gamma di provider di tipi per i servizi dati Internet e aziendali di uso comune.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-107">The F# ecosystem contains a range of type providers for commonly used Internet and enterprise data services.</span></span> <span data-ttu-id="4b6d7-108">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="4b6d7-108">For example:</span></span>

- <span data-ttu-id="4b6d7-109">[FSharp. Data](https://fsharp.github.io/FSharp.Data/) include provider di tipi per i formati di documenti JSON, XML, CSV e HTML.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-109">[FSharp.Data](https://fsharp.github.io/FSharp.Data/) includes type providers for JSON, XML, CSV and HTML document formats.</span></span>

- <span data-ttu-id="4b6d7-110">[Sqlfornitor](https://fsprojects.github.io/SQLProvider/) fornisce un accesso fortemente tipizzato ai database SQL tramite un mapping di F# oggetti e query LINQ su tali origini dati.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-110">[SQLProvider](https://fsprojects.github.io/SQLProvider/) provides strongly-typed access to SQL databases through a object mapping and F# LINQ queries against these data sources.</span></span>

- <span data-ttu-id="4b6d7-111">[FSharp. Data. SqlClient](https://fsprojects.github.io/FSharp.Data.SqlClient/) include un set di provider di tipi per l'incorporamento di T-SQL selezionato in F#fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-111">[FSharp.Data.SqlClient](https://fsprojects.github.io/FSharp.Data.SqlClient/) has a set of type providers for compile-time checked embedding of T-SQL in F#.</span></span>

- <span data-ttu-id="4b6d7-112">[FSharp. Data. TypeProviders](https://fsprojects.github.io/FSharp.Data.TypeProviders/) è un set di provider di tipi obsoleto che può essere utilizzato solo con la programmazione .NET Framework per l'accesso a SQL, Entity Framework, OData e WSDL Data Services.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-112">[FSharp.Data.TypeProviders](https://fsprojects.github.io/FSharp.Data.TypeProviders/) is an older set of type providers for use only with .NET Framework programming for accessing SQL, Entity Framework, OData and WSDL data services.</span></span>

<span data-ttu-id="4b6d7-113">Se necessario, è possibile creare provider di tipi personalizzati o fare riferimento a provider di tipi creati da altri.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-113">Where necessary, you can create custom type providers, or you can reference type providers that others have created.</span></span> <span data-ttu-id="4b6d7-114">Ad esempio, l'organizzazione potrebbe disporre di un servizio dati che fornisce un numero elevato e crescente di set di dati denominati, ognuno con un proprio schema di dati stabile.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-114">For example, your organization could have a data service that provides a large and growing number of named data sets, each with its own stable data schema.</span></span> <span data-ttu-id="4b6d7-115">È possibile creare un provider di tipi che legge gli schemi e presenta i set di dati correnti al programmatore in modo fortemente tipizzato.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-115">You can create a type provider that reads the schemas and presents the current data sets to the programmer in a strongly typed way.</span></span>

## <a name="before-you-start"></a><span data-ttu-id="4b6d7-116">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="4b6d7-116">Before You Start</span></span>

<span data-ttu-id="4b6d7-117">Il meccanismo del provider di tipi è progettato principalmente per inserire dati stabili e spazi di informazioni sui F# servizi nell'esperienza di programmazione.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-117">The type provider mechanism is primarily designed for injecting stable data and service information spaces into the F# programming experience.</span></span>

<span data-ttu-id="4b6d7-118">Questo meccanismo non è progettato per l'inserimento di spazi di informazioni con modifiche dello schema durante l'esecuzione del programma in modi rilevanti per la logica del programma.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-118">This mechanism isn’t designed for injecting information spaces whose schema changes during program execution in ways that are relevant to program logic.</span></span> <span data-ttu-id="4b6d7-119">Inoltre, il meccanismo non è progettato per la metaprogrammazione intra-linguaggio, anche se tale dominio contiene alcuni usi validi.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-119">Also, the mechanism isn't designed for intra-language meta-programming, even though that domain contains some valid uses.</span></span> <span data-ttu-id="4b6d7-120">È consigliabile utilizzare questo meccanismo solo laddove necessario e in cui lo sviluppo di un provider di tipi restituisce un valore molto elevato.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-120">You should use this mechanism only where necessary and where the development of a type provider yields very high value.</span></span>

<span data-ttu-id="4b6d7-121">È consigliabile evitare di scrivere un provider di tipi in cui uno schema non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-121">You should avoid writing a type provider where a schema isn't available.</span></span> <span data-ttu-id="4b6d7-122">Analogamente, è consigliabile evitare di scrivere un provider di tipi in cui sarebbe sufficiente una libreria .NET ordinaria (o persino una esistente).</span><span class="sxs-lookup"><span data-stu-id="4b6d7-122">Likewise, you should avoid writing a type provider where an ordinary (or even an existing) .NET library would suffice.</span></span>

<span data-ttu-id="4b6d7-123">Prima di iniziare, è possibile porre le domande seguenti:</span><span class="sxs-lookup"><span data-stu-id="4b6d7-123">Before you start, you might ask the following questions:</span></span>

- <span data-ttu-id="4b6d7-124">Si dispone di uno schema per l'origine informazioni?</span><span class="sxs-lookup"><span data-stu-id="4b6d7-124">Do you have a schema for your information source?</span></span> <span data-ttu-id="4b6d7-125">In tal caso, qual è il mapping al F# sistema di tipi .NET?</span><span class="sxs-lookup"><span data-stu-id="4b6d7-125">If so, what’s the mapping into the F# and .NET type system?</span></span>

- <span data-ttu-id="4b6d7-126">È possibile usare un'API esistente (tipizzata in modo dinamico) come punto di partenza per l'implementazione?</span><span class="sxs-lookup"><span data-stu-id="4b6d7-126">Can you use an existing (dynamically typed) API as a starting point for your implementation?</span></span>

- <span data-ttu-id="4b6d7-127">L'utente e l'organizzazione hanno a disposizione un utilizzo sufficiente del provider di tipi per fare in modo che la scrittura valga?</span><span class="sxs-lookup"><span data-stu-id="4b6d7-127">Will you and your organization have enough uses of the type provider to make writing it worthwhile?</span></span> <span data-ttu-id="4b6d7-128">Una normale libreria .NET soddisfa le tue esigenze?</span><span class="sxs-lookup"><span data-stu-id="4b6d7-128">Would a normal .NET library meet your needs?</span></span>

- <span data-ttu-id="4b6d7-129">Quanto cambierà lo schema?</span><span class="sxs-lookup"><span data-stu-id="4b6d7-129">How much will your schema change?</span></span>

- <span data-ttu-id="4b6d7-130">Il cambiamento verrà modificato durante la codifica?</span><span class="sxs-lookup"><span data-stu-id="4b6d7-130">Will it change during coding?</span></span>

- <span data-ttu-id="4b6d7-131">Cambierà tra le sessioni di codifica?</span><span class="sxs-lookup"><span data-stu-id="4b6d7-131">Will it change between coding sessions?</span></span>

- <span data-ttu-id="4b6d7-132">Il cambiamento verrà modificato durante l'esecuzione del programma?</span><span class="sxs-lookup"><span data-stu-id="4b6d7-132">Will it change during program execution?</span></span>

<span data-ttu-id="4b6d7-133">I provider di tipi sono ideali per le situazioni in cui lo schema è stabile in fase di esecuzione e durante il ciclo di vita del codice compilato.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-133">Type providers are best suited to situations where the schema is stable at runtime and during the lifetime of compiled code.</span></span>

## <a name="a-simple-type-provider"></a><span data-ttu-id="4b6d7-134">Provider di tipi semplici</span><span class="sxs-lookup"><span data-stu-id="4b6d7-134">A Simple Type Provider</span></span>

<span data-ttu-id="4b6d7-135">Questo esempio è Samples. HelloWorldTypeProvider, simile agli esempi nella `examples` directory di [ F# Type provider SDK](https://github.com/fsprojects/FSharp.TypeProviders.SDK/).</span><span class="sxs-lookup"><span data-stu-id="4b6d7-135">This sample is Samples.HelloWorldTypeProvider, similar to the samples in the `examples` directory of the [F# Type Provider SDK](https://github.com/fsprojects/FSharp.TypeProviders.SDK/).</span></span> <span data-ttu-id="4b6d7-136">Il provider rende disponibile uno "spazio di tipo" che contiene 100 tipi cancellati, come illustrato nel codice seguente usando F# la sintassi della firma e omettendo i dettagli per tutti `Type1`gli elementi eccetto.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-136">The provider makes available a "type space" that contains 100 erased types, as the following code shows by using F# signature syntax and omitting the details for all except `Type1`.</span></span> <span data-ttu-id="4b6d7-137">Per ulteriori informazioni sui tipi cancellati, vedere [Dettagli sui tipi specificati cancellati](#details-about-erased-provided-types) più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-137">For more information about erased types, see [Details About Erased Provided Types](#details-about-erased-provided-types) later in this topic.</span></span>

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

<span data-ttu-id="4b6d7-138">Si noti che il set di tipi e membri forniti è stato noto in modo statico.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-138">Note that the set of types and members provided is statically known.</span></span> <span data-ttu-id="4b6d7-139">Questo esempio non sfrutta la capacità dei provider di fornire tipi che dipendono da uno schema.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-139">This example doesn't leverage the ability of providers to provide types that depend on a schema.</span></span> <span data-ttu-id="4b6d7-140">L'implementazione del provider di tipi è illustrata nel codice seguente e i dettagli sono descritti nelle sezioni successive di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-140">The implementation of the type provider is outlined in the following code, and the details are covered in later sections of this topic.</span></span>

> [!WARNING]
> <span data-ttu-id="4b6d7-141">Potrebbero esserci differenze tra questo codice e gli esempi online.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-141">There may be differences between this code and the online samples.</span></span>

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

<span data-ttu-id="4b6d7-142">Per usare questo provider, aprire un'istanza separata di Visual Studio, creare uno F# script, quindi aggiungere un riferimento al provider dallo script usando #r come illustrato nel codice seguente:</span><span class="sxs-lookup"><span data-stu-id="4b6d7-142">To use this provider, open a separate instance of Visual Studio, create an F# script, and then add a reference to the provider from your script by using #r as the following code shows:</span></span>

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

<span data-ttu-id="4b6d7-143">Cercare quindi i tipi `Samples.HelloWorldTypeProvider` nello spazio dei nomi generato dal provider di tipi.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-143">Then look for the types under the `Samples.HelloWorldTypeProvider` namespace that the type provider generated.</span></span>

<span data-ttu-id="4b6d7-144">Prima di ricompilare il provider, assicurarsi di avere chiuso tutte le istanze di Visual Studio e F# Interactive che usano la dll del provider.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-144">Before you recompile the provider, make sure that you have closed all instances of Visual Studio and F# Interactive that are using the provider DLL.</span></span> <span data-ttu-id="4b6d7-145">In caso contrario, si verificherà un errore di compilazione perché la DLL di output sarà bloccata.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-145">Otherwise, a build error will occur because the output DLL will be locked.</span></span>

<span data-ttu-id="4b6d7-146">Per eseguire il debug di questo provider utilizzando le istruzioni Print, creare uno script che espone un problema con il provider e quindi utilizzare il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="4b6d7-146">To debug this provider by using print statements, make a script that exposes a problem with the provider, and then use the following code:</span></span>

```console
fsc.exe -r:bin\Debug\HelloWorldTypeProvider.dll script.fsx
```

<span data-ttu-id="4b6d7-147">Per eseguire il debug di questo provider con Visual Studio, aprire il Prompt dei comandi per gli sviluppatori per Visual Studio con credenziali amministrative ed eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="4b6d7-147">To debug this provider by using Visual Studio, open the Developer Command Prompt for Visual Studio with administrative credentials, and run the following command:</span></span>

```console
devenv.exe /debugexe fsc.exe -r:bin\Debug\HelloWorldTypeProvider.dll script.fsx
```

<span data-ttu-id="4b6d7-148">In alternativa, aprire Visual Studio, aprire il menu debug, scegliere `Debug/Attach to process…`e connettersi a un altro `devenv` processo in cui si sta modificando lo script.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-148">As an alternative, open Visual Studio, open the Debug menu, choose `Debug/Attach to process…`, and attach to another `devenv` process where you’re editing your script.</span></span> <span data-ttu-id="4b6d7-149">Utilizzando questo metodo, è possibile indirizzare più facilmente la logica specifica nel provider di tipi digitando in modo interattivo le espressioni nella seconda istanza (con IntelliSense completo e altre funzionalità).</span><span class="sxs-lookup"><span data-stu-id="4b6d7-149">By using this method, you can more easily target particular logic in the type provider by interactively typing expressions into the second instance (with full IntelliSense and other features).</span></span>

<span data-ttu-id="4b6d7-150">È possibile disabilitare Just My Code debug per identificare meglio gli errori nel codice generato.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-150">You can disable Just My Code debugging to better identify errors in generated code.</span></span> <span data-ttu-id="4b6d7-151">Per informazioni su come abilitare o disabilitare questa funzionalità, vedere [esplorazione del codice con il debugger](/visualstudio/debugger/navigating-through-code-with-the-debugger).</span><span class="sxs-lookup"><span data-stu-id="4b6d7-151">For information about how to enable or disable this feature, see [Navigating through Code with the Debugger](/visualstudio/debugger/navigating-through-code-with-the-debugger).</span></span> <span data-ttu-id="4b6d7-152">Inoltre, è possibile impostare l'individuazione delle eccezioni first-chance aprendo il `Debug` menu e scegliendo `Exceptions` o scegliendo i tasti CTRL + ALT + E per `Exceptions` aprire la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-152">Also, you can also set first-chance exception catching by opening the `Debug` menu and then choosing `Exceptions` or by choosing the Ctrl+Alt+E keys to open the `Exceptions` dialog box.</span></span> <span data-ttu-id="4b6d7-153">In tale finestra di dialogo, `Common Language Runtime Exceptions`in selezionare la `Thrown` casella di controllo.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-153">In that dialog box, under `Common Language Runtime Exceptions`, select the `Thrown` check box.</span></span>

### <a name="implementation-of-the-type-provider"></a><span data-ttu-id="4b6d7-154">Implementazione del provider di tipi</span><span class="sxs-lookup"><span data-stu-id="4b6d7-154">Implementation of the Type Provider</span></span>

<span data-ttu-id="4b6d7-155">Questa sezione illustra le sezioni principali dell'implementazione del provider di tipi.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-155">This section walks you through the principal sections of the type provider implementation.</span></span> <span data-ttu-id="4b6d7-156">In primo luogo, si definisce il tipo per il provider di tipi personalizzato:</span><span class="sxs-lookup"><span data-stu-id="4b6d7-156">First, you define the type for the custom type provider itself:</span></span>

```fsharp
[<TypeProvider>]
type SampleTypeProvider(config: TypeProviderConfig) as this =
```

<span data-ttu-id="4b6d7-157">Questo tipo deve essere pubblico ed è necessario contrassegnarlo con l'attributo [TypeProvider](https://msdn.microsoft.com/library/bdf7b036-7490-4ace-b79f-c5f1b1b37947) in modo che il compilatore riconosca il provider di tipi quando F# un progetto separato fa riferimento all'assembly che contiene il tipo.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-157">This type must be public, and you must mark it with the [TypeProvider](https://msdn.microsoft.com/library/bdf7b036-7490-4ace-b79f-c5f1b1b37947) attribute so that the compiler will recognize the type provider when a separate F# project references the assembly that contains the type.</span></span> <span data-ttu-id="4b6d7-158">Il parametro *config* è facoltativo e, se presente, contiene le informazioni di configurazione contestuali per l'istanza del provider di F# tipi creata dal compilatore.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-158">The *config* parameter is optional, and, if present, contains contextual configuration information for the type provider instance that the F# compiler creates.</span></span>

<span data-ttu-id="4b6d7-159">Successivamente, si implementa l'interfaccia [ITypeProvider](https://msdn.microsoft.com/library/2c2b0571-843d-4a7d-95d4-0a7510ed5e2f) .</span><span class="sxs-lookup"><span data-stu-id="4b6d7-159">Next, you implement the [ITypeProvider](https://msdn.microsoft.com/library/2c2b0571-843d-4a7d-95d4-0a7510ed5e2f) interface.</span></span> <span data-ttu-id="4b6d7-160">In questo caso, il `TypeProviderForNamespaces` tipo viene usato `ProvidedTypes` dall'API come tipo di base.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-160">In this case, you use the `TypeProviderForNamespaces` type from the `ProvidedTypes` API as a base type.</span></span> <span data-ttu-id="4b6d7-161">Questo tipo di helper può fornire una raccolta limitata di spazi dei nomi forniti in modo eager, ognuno dei quali contiene direttamente un numero finito di tipi fissi e con supporto eager.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-161">This helper type can provide a finite collection of eagerly provided namespaces, each of which directly contains a finite number of fixed, eagerly provided types.</span></span> <span data-ttu-id="4b6d7-162">In questo contesto, il provider genera con *entusiasmo* i tipi anche se non sono necessari o usati.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-162">In this context, the provider *eagerly* generates types even if they aren't needed or used.</span></span>

```fsharp
inherit TypeProviderForNamespaces(config)
```

<span data-ttu-id="4b6d7-163">Definire quindi i valori privati locali che specificano lo spazio dei nomi per i tipi forniti e trovare l'assembly del provider di tipi.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-163">Next, define local private values that specify the namespace for the provided types, and find the type provider assembly itself.</span></span> <span data-ttu-id="4b6d7-164">Questo assembly viene utilizzato in seguito come tipo padre logico dei tipi cancellati forniti.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-164">This assembly is used later as the logical parent type of the erased types that are provided.</span></span>

```fsharp
let namespaceName = "Samples.HelloWorldTypeProvider"
let thisAssembly = Assembly.GetExecutingAssembly()
```

<span data-ttu-id="4b6d7-165">Successivamente, creare una funzione per fornire ogni tipo di tipo1... Type100.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-165">Next, create a function to provide each of the types Type1…Type100.</span></span> <span data-ttu-id="4b6d7-166">Questa funzione è illustrata in modo più dettagliato più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-166">This function is explained in more detail later in this topic.</span></span>

```fsharp
let makeOneProvidedType (n:int) = …
```

<span data-ttu-id="4b6d7-167">Generare quindi i tipi forniti 100:</span><span class="sxs-lookup"><span data-stu-id="4b6d7-167">Next, generate the 100 provided types:</span></span>

```fsharp
let types = [ for i in 1 .. 100 -> makeOneProvidedType i ]
```

<span data-ttu-id="4b6d7-168">Aggiungere quindi i tipi come uno spazio dei nomi specificato:</span><span class="sxs-lookup"><span data-stu-id="4b6d7-168">Next, add the types as a provided namespace:</span></span>

```fsharp
do this.AddNamespace(namespaceName, types)
```

<span data-ttu-id="4b6d7-169">Infine, aggiungere un attributo dell'assembly che indichi che si sta creando una DLL del provider di tipi:</span><span class="sxs-lookup"><span data-stu-id="4b6d7-169">Finally, add an assembly attribute that indicates that you are creating a type provider DLL:</span></span>

```fsharp
[<assembly:TypeProviderAssembly>]
do()
```

### <a name="providing-one-type-and-its-members"></a><span data-ttu-id="4b6d7-170">Fornire un tipo e i relativi membri</span><span class="sxs-lookup"><span data-stu-id="4b6d7-170">Providing One Type And Its Members</span></span>

<span data-ttu-id="4b6d7-171">La `makeOneProvidedType` funzione esegue il lavoro effettivo di fornire uno dei tipi.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-171">The `makeOneProvidedType` function does the real work of providing one of the types.</span></span>

```fsharp
let makeOneProvidedType (n:int) =
…
```

<span data-ttu-id="4b6d7-172">Questo passaggio illustra l'implementazione di questa funzione.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-172">This step explains the implementation of this function.</span></span> <span data-ttu-id="4b6d7-173">Per prima cosa, creare il tipo specificato (ad esempio, tipo1, quando n = 1, o Type57, quando n = 57).</span><span class="sxs-lookup"><span data-stu-id="4b6d7-173">First, create the provided type (for example, Type1, when n = 1, or Type57, when n = 57).</span></span>

```fsharp
// This is the provided type. It is an erased provided type and, in compiled code,
// will appear as type 'obj'.
let t = ProvidedTypeDefinition(thisAssembly, namespaceName,
                               "Type" + string n,
                               baseType = Some typeof<obj>)
```

<span data-ttu-id="4b6d7-174">Tenere presente quanto segue:</span><span class="sxs-lookup"><span data-stu-id="4b6d7-174">You should note the following points:</span></span>

- <span data-ttu-id="4b6d7-175">Questo tipo specificato è stato cancellato.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-175">This provided type is erased.</span></span>  <span data-ttu-id="4b6d7-176">Poiché si indica che il tipo di base `obj`è, le istanze verranno visualizzate come valori di tipo [obj](https://msdn.microsoft.com/library/dcf2430f-702b-40e5-a0a1-97518bf137f7) nel codice compilato.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-176">Because you indicate that the base type is `obj`, instances will appear as values of type [obj](https://msdn.microsoft.com/library/dcf2430f-702b-40e5-a0a1-97518bf137f7) in compiled code.</span></span>

- <span data-ttu-id="4b6d7-177">Quando si specifica un tipo non annidato, è necessario specificare l'assembly e lo spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-177">When you specify a non-nested type, you must specify the assembly and namespace.</span></span> <span data-ttu-id="4b6d7-178">Per i tipi cancellati, l'assembly deve essere l'assembly del provider di tipi.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-178">For erased types, the assembly should be the type provider assembly itself.</span></span>

<span data-ttu-id="4b6d7-179">Successivamente, aggiungere la documentazione XML al tipo.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-179">Next, add XML documentation to the type.</span></span> <span data-ttu-id="4b6d7-180">Questa documentazione viene ritardata, ovvero calcolata su richiesta se il compilatore host lo richiede.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-180">This documentation is delayed, that is, computed on-demand if the host compiler needs it.</span></span>

```fsharp
t.AddXmlDocDelayed (fun () -> sprintf "This provided type %s" ("Type" + string n))
```

<span data-ttu-id="4b6d7-181">Aggiungere quindi una proprietà statica specificata al tipo:</span><span class="sxs-lookup"><span data-stu-id="4b6d7-181">Next you add a provided static property to the type:</span></span>

```fsharp
let staticProp = ProvidedProperty(propertyName = "StaticProperty",
                                  propertyType = typeof<string>,
                                  isStatic = true,
                                  getterCode = (fun args -> <@@ "Hello!" @@>))
```

<span data-ttu-id="4b6d7-182">Il recupero di questa proprietà restituirà sempre la stringa "Hello!".</span><span class="sxs-lookup"><span data-stu-id="4b6d7-182">Getting this property will always evaluate to the string "Hello!".</span></span> <span data-ttu-id="4b6d7-183">Per la proprietà viene utilizzata una F# virgoletta, che rappresenta il codice generato dal compilatore host per ottenere la proprietà. `GetterCode`</span><span class="sxs-lookup"><span data-stu-id="4b6d7-183">The `GetterCode` for the property uses an F# quotation, which represents the code that the host compiler generates for getting the property.</span></span> <span data-ttu-id="4b6d7-184">Per ulteriori informazioni sulle quotazioni, vedere [citazioni di codice (F#)](https://msdn.microsoft.com/library/6f055397-a1f0-4f9a-927c-f0d7c6951155).</span><span class="sxs-lookup"><span data-stu-id="4b6d7-184">For more information about quotations, see [Code Quotations (F#)](https://msdn.microsoft.com/library/6f055397-a1f0-4f9a-927c-f0d7c6951155).</span></span>

<span data-ttu-id="4b6d7-185">Aggiungere la documentazione XML alla proprietà.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-185">Add XML documentation to the property.</span></span>

```fsharp
staticProp.AddXmlDocDelayed(fun () -> "This is a static property")
```

<span data-ttu-id="4b6d7-186">A questo punto, alleghi la proprietà specificata al tipo fornito.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-186">Now attach the provided property to the provided type.</span></span> <span data-ttu-id="4b6d7-187">È necessario alleghi un membro fornito a un solo tipo.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-187">You must attach a provided member to one and only one type.</span></span> <span data-ttu-id="4b6d7-188">In caso contrario, il membro non sarà mai accessibile.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-188">Otherwise, the member will never be accessible.</span></span>

```fsharp
t.AddMember staticProp
```

<span data-ttu-id="4b6d7-189">Creare ora un costruttore fornito che non accetta parametri.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-189">Now create a provided constructor that takes no parameters.</span></span>

```fsharp
let ctor = ProvidedConstructor(parameters = [ ],
                               invokeCode = (fun args -> <@@ "The object data" :> obj @@>))
```

<span data-ttu-id="4b6d7-190">Per il costruttore viene restituita F# una quotation, che rappresenta il codice generato dal compilatore host quando viene chiamato il costruttore. `InvokeCode`</span><span class="sxs-lookup"><span data-stu-id="4b6d7-190">The `InvokeCode` for the constructor returns an F# quotation, which represents the code that the host compiler generates when the constructor is called.</span></span> <span data-ttu-id="4b6d7-191">Ad esempio, è possibile usare il costruttore seguente:</span><span class="sxs-lookup"><span data-stu-id="4b6d7-191">For example, you can use the following constructor:</span></span>

```fsharp
new Type10()
```

<span data-ttu-id="4b6d7-192">Verrà creata un'istanza del tipo fornito con i dati sottostanti "i dati dell'oggetto".</span><span class="sxs-lookup"><span data-stu-id="4b6d7-192">An instance of the provided type will be created with underlying data "The object data".</span></span> <span data-ttu-id="4b6d7-193">Il codice tra virgolette include una conversione in [obj](https://msdn.microsoft.com/library/dcf2430f-702b-40e5-a0a1-97518bf137f7) perché tale tipo è la cancellazione di questo tipo specificato (come specificato quando è stato dichiarato il tipo fornito).</span><span class="sxs-lookup"><span data-stu-id="4b6d7-193">The quoted code includes a conversion to [obj](https://msdn.microsoft.com/library/dcf2430f-702b-40e5-a0a1-97518bf137f7) because that type is the erasure of this provided type (as you specified when you declared the provided type).</span></span>

<span data-ttu-id="4b6d7-194">Aggiungere la documentazione XML al costruttore e aggiungere il costruttore fornito al tipo fornito:</span><span class="sxs-lookup"><span data-stu-id="4b6d7-194">Add XML documentation to the constructor, and add the provided constructor to the provided type:</span></span>

```fsharp
ctor.AddXmlDocDelayed(fun () -> "This is a constructor")

t.AddMember ctor
```

<span data-ttu-id="4b6d7-195">Creare un secondo costruttore fornito che accetti un parametro:</span><span class="sxs-lookup"><span data-stu-id="4b6d7-195">Create a second provided constructor that takes one parameter:</span></span>

```fsharp
let ctor2 =
ProvidedConstructor(parameters = [ ProvidedParameter("data",typeof<string>) ],
                    invokeCode = (fun args -> <@@ (%%(args.[0]) : string) :> obj @@>))
```

<span data-ttu-id="4b6d7-196">Per il costruttore viene nuovamente restituita F# una quotation, che rappresenta il codice generato dal compilatore host per una chiamata al metodo. `InvokeCode`</span><span class="sxs-lookup"><span data-stu-id="4b6d7-196">The `InvokeCode` for the constructor again returns an F# quotation, which represents the code that the host compiler generated for a call to the method.</span></span> <span data-ttu-id="4b6d7-197">Ad esempio, è possibile usare il costruttore seguente:</span><span class="sxs-lookup"><span data-stu-id="4b6d7-197">For example, you can use the following constructor:</span></span>

```fsharp
new Type10("ten")
```

<span data-ttu-id="4b6d7-198">Viene creata un'istanza del tipo fornito con i dati sottostanti "dieci".</span><span class="sxs-lookup"><span data-stu-id="4b6d7-198">An instance of the provided type is created with underlying data "ten".</span></span> <span data-ttu-id="4b6d7-199">È possibile che sia già stato notato `InvokeCode` che la funzione restituisce una quotation.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-199">You may have already noticed that the `InvokeCode` function returns a quotation.</span></span> <span data-ttu-id="4b6d7-200">L'input per questa funzione è un elenco di espressioni, una per ogni parametro del costruttore.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-200">The input to this function is a list of expressions, one per constructor parameter.</span></span> <span data-ttu-id="4b6d7-201">In questo caso, un'espressione che rappresenta il valore del singolo parametro è disponibile `args.[0]`in.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-201">In this case, an expression that represents the single parameter value is available in `args.[0]`.</span></span> <span data-ttu-id="4b6d7-202">Il codice per una chiamata al costruttore assegna il valore restituito al tipo `obj`cancellato.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-202">The code for a call to the constructor coerces the return value to the erased type `obj`.</span></span> <span data-ttu-id="4b6d7-203">Dopo aver aggiunto il secondo costruttore fornito al tipo, si crea una proprietà di istanza specificata:</span><span class="sxs-lookup"><span data-stu-id="4b6d7-203">After you add the second provided constructor to the type, you create a provided instance property:</span></span>

```fsharp
let instanceProp =
    ProvidedProperty(propertyName = "InstanceProperty",
                     propertyType = typeof<int>,
                     getterCode= (fun args ->
                        <@@ ((%%(args.[0]) : obj) :?> string).Length @@>))
instanceProp.AddXmlDocDelayed(fun () -> "This is an instance property")
t.AddMember instanceProp
```

<span data-ttu-id="4b6d7-204">Ottenendo questa proprietà, viene restituita la lunghezza della stringa, ovvero l'oggetto rappresentazione.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-204">Getting this property will return the length of the string, which is the representation object.</span></span> <span data-ttu-id="4b6d7-205">La `GetterCode` proprietà restituisce una F# virgoletta che specifica il codice generato dal compilatore host per ottenere la proprietà.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-205">The `GetterCode` property returns an F# quotation that specifies the code that the host compiler generates to get the property.</span></span> <span data-ttu-id="4b6d7-206">Analogamente `InvokeCode`a `GetterCode` , la funzione restituisce una quotation.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-206">Like `InvokeCode`, the `GetterCode` function returns a quotation.</span></span> <span data-ttu-id="4b6d7-207">Il compilatore host chiama questa funzione con un elenco di argomenti.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-207">The host compiler calls this function with a list of arguments.</span></span> <span data-ttu-id="4b6d7-208">In questo caso, gli argomenti includono solo l'espressione singola che rappresenta l'istanza sulla quale viene chiamato il metodo Get, a cui è possibile accedere `args.[0]`tramite.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-208">In this case, the arguments include just the single expression that represents the instance upon which the getter is being called, which you can access by using `args.[0]`.</span></span> <span data-ttu-id="4b6d7-209">L'implementazione di `GetterCode` viene quindi contenuta nella quotazione dei risultati in corrispondenza del `obj`tipo cancellato e viene utilizzato un cast per soddisfare il meccanismo del compilatore per verificare i tipi che l'oggetto è una stringa.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-209">The implementation of `GetterCode` then splices into the result quotation at the erased type `obj`, and a cast is used to satisfy the compiler's mechanism for checking types that the object is a string.</span></span> <span data-ttu-id="4b6d7-210">La parte successiva di `makeOneProvidedType` fornisce un metodo di istanza con un parametro.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-210">The next part of `makeOneProvidedType` provides an instance method with one parameter.</span></span>

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

<span data-ttu-id="4b6d7-211">Infine, creare un tipo annidato che contiene 100 proprietà nidificate.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-211">Finally, create a nested type that contains 100 nested properties.</span></span> <span data-ttu-id="4b6d7-212">La creazione di questo tipo annidato e delle relative proprietà viene ritardata, ovvero calcolata su richiesta.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-212">The creation of this nested type and its properties is delayed, that is, computed on-demand.</span></span>

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

### <a name="details-about-erased-provided-types"></a><span data-ttu-id="4b6d7-213">Dettagli sui tipi specificati cancellati</span><span class="sxs-lookup"><span data-stu-id="4b6d7-213">Details about Erased Provided Types</span></span>

<span data-ttu-id="4b6d7-214">Nell'esempio riportato in questa sezione vengono forniti solo i *tipi forniti cancellati*, che risultano particolarmente utili nelle situazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="4b6d7-214">The example in this section provides only *erased provided types*, which are particularly useful in the following situations:</span></span>

- <span data-ttu-id="4b6d7-215">Quando si scrive un provider per uno spazio informazioni che contiene solo dati e metodi.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-215">When you are writing a provider for an information space that contains only data and methods.</span></span>

- <span data-ttu-id="4b6d7-216">Quando si scrive un provider in cui la semantica di tipo runtime accurato non è fondamentale per l'uso pratico dello spazio informativo.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-216">When you are writing a provider where accurate runtime-type semantics aren't critical for practical use of the information space.</span></span>

- <span data-ttu-id="4b6d7-217">Quando si scrive un provider per uno spazio informativo molto grande e interconnesso, non è tecnicamente possibile generare tipi .NET reali per lo spazio informativo.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-217">When you are writing a provider for an information space that is so large and interconnected that it isn’t technically feasible to generate real .NET types for the information space.</span></span>

<span data-ttu-id="4b6d7-218">In questo esempio, ogni tipo fornito viene cancellato nel tipo `obj`e tutti gli utilizzi del tipo verranno visualizzati come tipo `obj` nel codice compilato.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-218">In this example, each provided type is erased to type `obj`, and all uses of the type will appear as type `obj` in compiled code.</span></span> <span data-ttu-id="4b6d7-219">Infatti, gli oggetti sottostanti in questi esempi sono stringhe, ma il tipo verrà visualizzato come `System.Object` nel codice compilato .NET.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-219">In fact, the underlying objects in these examples are strings, but the type will appear as `System.Object` in .NET compiled code.</span></span> <span data-ttu-id="4b6d7-220">Come per tutti gli usi della cancellazione dei tipi, è possibile usare la conversione boxing esplicita, unboxing e cast per sovvertire i tipi cancellati.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-220">As with all uses of type erasure, you can use explicit boxing, unboxing, and casting to subvert erased types.</span></span> <span data-ttu-id="4b6d7-221">In questo caso, è possibile che venga generata un'eccezione cast non valida quando si usa l'oggetto.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-221">In this case, a cast exception that isn’t valid may result when the object is used.</span></span> <span data-ttu-id="4b6d7-222">Un runtime del provider può definire il proprio tipo di rappresentazione privata per facilitare la protezione da false rappresentazioni.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-222">A provider runtime can define its own private representation type to help protect against false representations.</span></span> <span data-ttu-id="4b6d7-223">Non è possibile definire i tipi cancellati in F# se stesso.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-223">You can’t define erased types in F# itself.</span></span> <span data-ttu-id="4b6d7-224">Solo i tipi specificati possono essere cancellati.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-224">Only provided types may be erased.</span></span> <span data-ttu-id="4b6d7-225">È necessario comprendere le ramificazioni, sia pratiche che semantiche, di usare i tipi cancellati per il provider di tipi o un provider che fornisce tipi cancellati.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-225">You must understand the ramifications, both practical and semantic, of using either erased types for your type provider or a provider that provides erased types.</span></span> <span data-ttu-id="4b6d7-226">Un tipo cancellato non ha un tipo .NET reale.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-226">An erased type has no real .NET type.</span></span> <span data-ttu-id="4b6d7-227">Pertanto, non è possibile eseguire una reflection accurata sul tipo ed è possibile sovvertire i tipi cancellati se si usano i cast di runtime e altre tecniche che si basano sulla semantica esatta del tipo di Runtime.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-227">Therefore, you cannot do accurate reflection over the type, and you might subvert erased types if you use runtime casts and other techniques that rely on exact runtime type semantics.</span></span> <span data-ttu-id="4b6d7-228">La sovversione dei tipi cancellati spesso genera eccezioni di cast di tipo in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-228">Subversion of erased types frequently results in type cast exceptions at runtime.</span></span>

### <a name="choosing-representations-for-erased-provided-types"></a><span data-ttu-id="4b6d7-229">Scelta di rappresentazioni per i tipi specificati cancellati</span><span class="sxs-lookup"><span data-stu-id="4b6d7-229">Choosing Representations for Erased Provided Types</span></span>

<span data-ttu-id="4b6d7-230">Per alcuni usi dei tipi specificati cancellati, non è necessaria alcuna rappresentazione.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-230">For some uses of erased provided types, no representation is required.</span></span> <span data-ttu-id="4b6d7-231">Ad esempio, il tipo fornito cancellato potrebbe contenere solo proprietà statiche e membri e nessun costruttore, né metodi o proprietà restituiscono un'istanza del tipo.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-231">For example, the erased provided type might contain only static properties and members and no constructors, and no methods or properties would return an instance of the type.</span></span> <span data-ttu-id="4b6d7-232">Se è possibile raggiungere istanze di un tipo fornito cancellato, è necessario prendere in considerazione le domande seguenti:</span><span class="sxs-lookup"><span data-stu-id="4b6d7-232">If you can reach instances of an erased provided type, you must consider the following questions:</span></span>

<span data-ttu-id="4b6d7-233">**Qual è la cancellazione di un tipo fornito?**</span><span class="sxs-lookup"><span data-stu-id="4b6d7-233">**What is the erasure of a provided type?**</span></span>

- <span data-ttu-id="4b6d7-234">La cancellazione di un tipo fornito è il modo in cui il tipo viene visualizzato nel codice .NET compilato.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-234">The erasure of a provided type is how the type appears in compiled .NET code.</span></span>

- <span data-ttu-id="4b6d7-235">La cancellazione di un tipo di classe cancellato specificato è sempre il primo tipo di base non cancellato nella catena di ereditarietà del tipo.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-235">The erasure of a provided erased class type is always the first non-erased base type in the inheritance chain of the type.</span></span>

- <span data-ttu-id="4b6d7-236">La cancellazione di un tipo di interfaccia cancellato specificato è sempre `System.Object`.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-236">The erasure of a provided erased interface type is always `System.Object`.</span></span>

<span data-ttu-id="4b6d7-237">**Quali sono le rappresentazioni di un tipo fornito?**</span><span class="sxs-lookup"><span data-stu-id="4b6d7-237">**What are the representations of a provided type?**</span></span>

- <span data-ttu-id="4b6d7-238">Il set di oggetti possibili per un tipo fornito cancellato è denominato rappresentazioni.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-238">The set of possible objects for an erased provided type are called its representations.</span></span> <span data-ttu-id="4b6d7-239">Nell'esempio di questo documento, le rappresentazioni di tutti i tipi `Type1..Type100` forniti cancellati sono sempre oggetti stringa.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-239">In the example in this document, the representations of all the erased provided types `Type1..Type100` are always string objects.</span></span>

<span data-ttu-id="4b6d7-240">Tutte le rappresentazioni di un tipo fornito devono essere compatibili con la cancellazione del tipo fornito.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-240">All representations of a provided type must be compatible with the erasure of the provided type.</span></span> <span data-ttu-id="4b6d7-241">In caso contrario, il F# compilatore genererà un errore per l'uso del provider di tipi oppure verrà generato un codice .NET non verificabile che non è valido.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-241">(Otherwise, either the F# compiler will give an error for a use of the type provider, or unverifiable .NET code that isn't valid will be generated.</span></span> <span data-ttu-id="4b6d7-242">Un provider di tipi non è valido se restituisce un codice che fornisce una rappresentazione non valida.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-242">A type provider isn’t valid if it returns code that gives a  representation that isn't valid.)</span></span>

<span data-ttu-id="4b6d7-243">È possibile scegliere una rappresentazione per gli oggetti forniti usando uno degli approcci seguenti, entrambi molto comuni:</span><span class="sxs-lookup"><span data-stu-id="4b6d7-243">You can choose a representation for provided objects by using either of the following approaches, both of which are very common:</span></span>

- <span data-ttu-id="4b6d7-244">Se si fornisce semplicemente un wrapper fortemente tipizzato su un tipo .NET esistente, è spesso consigliabile cancellare il tipo in tale tipo, utilizzare istanze di quel tipo come rappresentazioni o entrambe.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-244">If you're simply providing a strongly typed wrapper over an existing .NET type, it often makes sense for your type to erase to that type, use instances of that type as representations, or both.</span></span> <span data-ttu-id="4b6d7-245">Questo approccio è appropriato quando la maggior parte dei metodi esistenti su quel tipo è ancora utile quando si usa la versione fortemente tipizzata.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-245">This approach is appropriate when most of the existing methods on that type still make sense when using the strongly typed version.</span></span>

- <span data-ttu-id="4b6d7-246">Se si vuole creare un'API che differisce in modo significativo da qualsiasi API .NET esistente, è opportuno creare tipi di runtime che saranno la cancellazione e le rappresentazioni del tipo per i tipi forniti.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-246">If you want to create an API that differs significantly from any existing .NET API, it makes sense to create runtime types that will be the type erasure and representations for the provided types.</span></span>

<span data-ttu-id="4b6d7-247">Nell'esempio riportato in questo documento vengono utilizzate stringhe come rappresentazioni degli oggetti forniti.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-247">The example in this document uses strings as representations of provided objects.</span></span> <span data-ttu-id="4b6d7-248">Spesso può essere opportuno usare altri oggetti per le rappresentazioni.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-248">Frequently, it may be appropriate to use other objects for representations.</span></span> <span data-ttu-id="4b6d7-249">Ad esempio, è possibile usare un dizionario come contenitore delle proprietà:</span><span class="sxs-lookup"><span data-stu-id="4b6d7-249">For example, you may use a dictionary as a property bag:</span></span>

```fsharp
ProvidedConstructor(parameters = [],
    invokeCode= (fun args -> <@@ (new Dictionary<string,obj>()) :> obj @@>))
```

<span data-ttu-id="4b6d7-250">In alternativa, è possibile definire un tipo nel provider di tipi che verrà utilizzato in fase di esecuzione per formare la rappresentazione, insieme a una o più operazioni di runtime:</span><span class="sxs-lookup"><span data-stu-id="4b6d7-250">As an alternative, you may define a type in your type provider that will be used at runtime to form the representation, along with one or more runtime operations:</span></span>

```fsharp
type DataObject() =
    let data = Dictionary<string,obj>()
    member x.RuntimeOperation() = data.Count
```

<span data-ttu-id="4b6d7-251">I membri forniti possono quindi creare istanze di questo tipo di oggetto:</span><span class="sxs-lookup"><span data-stu-id="4b6d7-251">Provided members can then construct instances of this object type:</span></span>

```fsharp
ProvidedConstructor(parameters = [],
    invokeCode= (fun args -> <@@ (new DataObject()) :> obj @@>))
```

<span data-ttu-id="4b6d7-252">In questo caso, è possibile (facoltativamente) usare questo tipo come cancellazione del tipo specificando questo tipo come `baseType` quando si costruisce l'oggetto: `ProvidedTypeDefinition`</span><span class="sxs-lookup"><span data-stu-id="4b6d7-252">In this case, you may (optionally) use this type as the type erasure by specifying this type as the `baseType` when constructing the `ProvidedTypeDefinition`:</span></span>

```fsharp
ProvidedTypeDefinition(…, baseType = Some typeof<DataObject> )
…
ProvidedConstructor(…, InvokeCode = (fun args -> <@@ new DataObject() @@>), …)
```

### <a name="key-lessons"></a><span data-ttu-id="4b6d7-253">Lezioni chiave</span><span class="sxs-lookup"><span data-stu-id="4b6d7-253">Key Lessons</span></span>

<span data-ttu-id="4b6d7-254">Nella sezione precedente è stato illustrato come creare un semplice provider di tipi di cancellazione che fornisce un intervallo di tipi, proprietà e metodi.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-254">The previous section explained how to create a simple erasing type provider that provides a range of types, properties, and methods.</span></span> <span data-ttu-id="4b6d7-255">In questa sezione viene anche illustrato il concetto di cancellazione dei tipi, inclusi alcuni dei vantaggi e degli svantaggi di fornire tipi cancellati da un provider di tipi e le rappresentazioni di tipi cancellati.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-255">This section also explained the concept of type erasure, including some of the advantages and disadvantages of providing erased types from a type provider, and discussed representations of erased types.</span></span>

## <a name="a-type-provider-that-uses-static-parameters"></a><span data-ttu-id="4b6d7-256">Provider di tipi che utilizza parametri statici</span><span class="sxs-lookup"><span data-stu-id="4b6d7-256">A Type Provider That Uses Static Parameters</span></span>

<span data-ttu-id="4b6d7-257">La possibilità di parametrizzare i provider di tipi in base ai dati statici Abilita molti scenari interessanti, anche nei casi in cui il provider non debba accedere a dati locali o remoti.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-257">The ability to parameterize type providers by static data enables many interesting scenarios, even in cases when the provider doesn't need to access any local or remote data.</span></span> <span data-ttu-id="4b6d7-258">In questa sezione verranno illustrate alcune tecniche di base per riunire un provider di questo tipo.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-258">In this section, you’ll learn some basic techniques for putting together such a provider.</span></span>

### <a name="type-checked-regex-provider"></a><span data-ttu-id="4b6d7-259">Digitare il provider Regex selezionato</span><span class="sxs-lookup"><span data-stu-id="4b6d7-259">Type Checked Regex Provider</span></span>

<span data-ttu-id="4b6d7-260">Si supponga di voler implementare un provider di tipi per le espressioni regolari che esegue il wrapping <xref:System.Text.RegularExpressions.Regex> delle librerie .NET in un'interfaccia che fornisce le garanzie della fase di compilazione seguenti:</span><span class="sxs-lookup"><span data-stu-id="4b6d7-260">Imagine that you want to implement a type provider for regular expressions that wraps the .NET <xref:System.Text.RegularExpressions.Regex> libraries in an interface that provides the following compile-time guarantees:</span></span>

- <span data-ttu-id="4b6d7-261">Verifica per determinare se un'espressione regolare è valida.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-261">Verifying whether a regular expression is valid.</span></span>

- <span data-ttu-id="4b6d7-262">Fornire proprietà denominate sulle corrispondenze basate su qualsiasi nome di gruppo nell'espressione regolare.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-262">Providing named properties on matches that are based on any group names in the regular expression.</span></span>

<span data-ttu-id="4b6d7-263">Questa sezione illustra come usare i provider di tipi per creare un `RegexTyped` tipo che il modello di espressione regolare parametrizza per fornire questi vantaggi.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-263">This section shows you how to use type providers to create a `RegexTyped` type that the regular expression pattern parameterizes to provide these benefits.</span></span> <span data-ttu-id="4b6d7-264">Il compilatore segnalerà un errore se il modello fornito non è valido e il provider di tipi può estrarre i gruppi dal modello in modo che sia possibile accedervi usando proprietà denominate sulle corrispondenze.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-264">The compiler will report an error if the supplied pattern isn't valid, and the type provider can extract the groups from the pattern so that you can access them by using named properties on matches.</span></span> <span data-ttu-id="4b6d7-265">Quando si progetta un provider di tipi, è necessario prendere in considerazione il modo in cui l'API esposta deve esaminare gli utenti finali e il modo in cui questa progettazione verrà convertita nel codice .NET.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-265">When you design a type provider, you should consider how its exposed API should look to end users and how this design will translate to .NET code.</span></span> <span data-ttu-id="4b6d7-266">Nell'esempio seguente viene illustrato come utilizzare tale API per ottenere i componenti del codice area:</span><span class="sxs-lookup"><span data-stu-id="4b6d7-266">The following example shows how to use such an API to get the components of the area code:</span></span>

```fsharp
type T = RegexTyped< @"(?<AreaCode>^\d{3})-(?<PhoneNumber>\d{3}-\d{4}$)">
let reg = T()
let result = T.IsMatch("425-555-2345")
let r = reg.Match("425-555-2345").Group_AreaCode.Value //r equals "425"
```

<span data-ttu-id="4b6d7-267">Nell'esempio seguente viene illustrato il modo in cui il provider di tipi converte queste chiamate:</span><span class="sxs-lookup"><span data-stu-id="4b6d7-267">The following example shows how the type provider translates these calls:</span></span>

```fsharp
let reg = new Regex(@"(?<AreaCode>^\d{3})-(?<PhoneNumber>\d{3}-\d{4}$)")
let result = reg.IsMatch("425-123-2345")
let r = reg.Match("425-123-2345").Groups.["AreaCode"].Value //r equals "425"
```

<span data-ttu-id="4b6d7-268">Tenere presente quanto segue:</span><span class="sxs-lookup"><span data-stu-id="4b6d7-268">Note the following points:</span></span>

- <span data-ttu-id="4b6d7-269">Il tipo Regex standard rappresenta il tipo `RegexTyped` con parametri.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-269">The standard Regex type represents the parameterized `RegexTyped` type.</span></span>

- <span data-ttu-id="4b6d7-270">Il `RegexTyped` costruttore genera una chiamata al costruttore Regex, passando l'argomento di tipo statico per il modello.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-270">The `RegexTyped` constructor results in a call to the Regex constructor, passing in the static type argument for the pattern.</span></span>

- <span data-ttu-id="4b6d7-271">I risultati del `Match` metodo sono rappresentati dal tipo standard <xref:System.Text.RegularExpressions.Match> .</span><span class="sxs-lookup"><span data-stu-id="4b6d7-271">The results of the `Match` method are represented by the standard <xref:System.Text.RegularExpressions.Match> type.</span></span>

- <span data-ttu-id="4b6d7-272">Ogni gruppo denominato restituisce una proprietà fornita e l'accesso alla proprietà comporta l'utilizzo di un indicizzatore in una raccolta di `Groups` corrispondenze.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-272">Each named group results in a provided property, and accessing the property results in a use of an indexer on a match’s `Groups` collection.</span></span>

<span data-ttu-id="4b6d7-273">Il codice seguente è il nucleo della logica per implementare tale provider e in questo esempio viene omessa l'aggiunta di tutti i membri al tipo fornito.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-273">The following code is the core of the logic to implement such a provider, and this example omits the addition of all members to the provided type.</span></span> <span data-ttu-id="4b6d7-274">Per informazioni su ogni membro aggiunto, vedere la sezione appropriata più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-274">For information about each added member, see the appropriate section later in this topic.</span></span> <span data-ttu-id="4b6d7-275">Per il codice completo, scaricare l'esempio dal [ F# pacchetto di esempio 3,0](https://archive.codeplex.com/?p=fsharp3sample) sul sito Web CodePlex.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-275">For the full code, download the sample from the [F# 3.0 Sample Pack](https://archive.codeplex.com/?p=fsharp3sample) on the CodePlex website.</span></span>

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

<span data-ttu-id="4b6d7-276">Tenere presente quanto segue:</span><span class="sxs-lookup"><span data-stu-id="4b6d7-276">Note the following points:</span></span>

- <span data-ttu-id="4b6d7-277">Il provider di tipi accetta due parametri statici: `pattern`, che è obbligatorio, `options`e, che sono facoltativi (poiché viene fornito un valore predefinito).</span><span class="sxs-lookup"><span data-stu-id="4b6d7-277">The type provider takes two static parameters: the `pattern`, which is mandatory, and the `options`, which are optional (because a default value is provided).</span></span>

- <span data-ttu-id="4b6d7-278">Dopo aver fornito gli argomenti statici, creare un'istanza dell'espressione regolare.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-278">After the static arguments are supplied, you create an instance of the regular expression.</span></span> <span data-ttu-id="4b6d7-279">Questa istanza genererà un'eccezione se l'espressione regolare non è in formato corretto e questo errore verrà segnalato agli utenti.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-279">This instance will throw an exception if the Regex is malformed, and this error will be reported to users.</span></span>

- <span data-ttu-id="4b6d7-280">All'interno `DefineStaticParameters` del callback, è necessario definire il tipo che verrà restituito dopo che gli argomenti sono stati specificati.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-280">Within the `DefineStaticParameters` callback, you define the type that will be returned after the arguments are supplied.</span></span>

- <span data-ttu-id="4b6d7-281">Questo codice imposta `HideObjectMethods` su true in modo che l'esperienza IntelliSense rimanga semplificata.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-281">This code sets `HideObjectMethods` to true so that the IntelliSense experience will remain streamlined.</span></span> <span data-ttu-id="4b6d7-282">Questo attributo fa in `Equals`modo `GetHashCode`che `Finalize`i membri `GetType` ,, e vengano eliminati dagli elenchi IntelliSense per un oggetto fornito.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-282">This attribute causes the `Equals`, `GetHashCode`, `Finalize`, and `GetType` members to be suppressed from IntelliSense lists for a provided object.</span></span>

- <span data-ttu-id="4b6d7-283">Usare `obj` come tipo di base del metodo, ma si userà un `Regex` oggetto come rappresentazione di runtime di questo tipo, come illustrato nell'esempio successivo.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-283">You use `obj` as the base type of the method, but you’ll use a `Regex` object as the runtime representation of this type, as the next example shows.</span></span>

- <span data-ttu-id="4b6d7-284">La chiamata al `Regex` costruttore genera un' <xref:System.ArgumentException> eccezione quando un'espressione regolare non è valida.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-284">The call to the `Regex` constructor throws a <xref:System.ArgumentException> when a regular expression isn’t valid.</span></span> <span data-ttu-id="4b6d7-285">Il compilatore rileva questa eccezione e segnala un messaggio di errore all'utente in fase di compilazione o nell'editor di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-285">The compiler catches this exception and reports an error message to the user at compile time or in the Visual Studio editor.</span></span> <span data-ttu-id="4b6d7-286">Questa eccezione consente la convalida delle espressioni regolari senza eseguire un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-286">This exception enables regular expressions to be validated without running an application.</span></span>

<span data-ttu-id="4b6d7-287">Il tipo definito sopra non è ancora utile perché non contiene metodi o proprietà significative.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-287">The type defined above isn't useful yet because it doesn’t contain any meaningful methods or properties.</span></span> <span data-ttu-id="4b6d7-288">Aggiungere prima di tutto un `IsMatch` metodo statico:</span><span class="sxs-lookup"><span data-stu-id="4b6d7-288">First, add a static `IsMatch` method:</span></span>

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

<span data-ttu-id="4b6d7-289">Il codice precedente definisce un metodo `IsMatch`che accetta una stringa come input e restituisce un oggetto `bool`.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-289">The previous code defines a method `IsMatch`, which takes a string as input and returns a `bool`.</span></span> <span data-ttu-id="4b6d7-290">L'unica parte complessa è l'uso dell' `args` argomento all'interno della `InvokeCode` definizione.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-290">The only tricky part is the use of the `args` argument within the `InvokeCode` definition.</span></span> <span data-ttu-id="4b6d7-291">In questo esempio, `args` è un elenco di citazioni che rappresenta gli argomenti di questo metodo.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-291">In this example, `args` is a list of quotations that represents the arguments to this method.</span></span> <span data-ttu-id="4b6d7-292">Se il metodo è un metodo di istanza, il primo argomento rappresenta `this` l'argomento.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-292">If the method is an instance method, the first argument represents the `this` argument.</span></span> <span data-ttu-id="4b6d7-293">Tuttavia, per un metodo statico, gli argomenti sono solo gli argomenti espliciti del metodo.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-293">However, for a static method, the arguments are all just the explicit arguments to the method.</span></span> <span data-ttu-id="4b6d7-294">Si noti che il tipo del valore tra virgolette deve corrispondere al tipo restituito specificato (in questo caso `bool`,).</span><span class="sxs-lookup"><span data-stu-id="4b6d7-294">Note that the type of the quoted value should match the specified return type (in this case, `bool`).</span></span> <span data-ttu-id="4b6d7-295">Si noti inoltre che questo codice usa `AddXmlDoc` il metodo per assicurarsi che il metodo fornito includa anche una documentazione utile, che può essere fornita tramite IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-295">Also note that this code uses the `AddXmlDoc` method to make sure that the provided method also has useful documentation, which you can supply through IntelliSense.</span></span>

<span data-ttu-id="4b6d7-296">Aggiungere quindi un metodo di corrispondenza dell'istanza.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-296">Next, add an instance Match method.</span></span> <span data-ttu-id="4b6d7-297">Tuttavia, questo metodo deve restituire un valore di un tipo `Match` specificato in modo che sia possibile accedere ai gruppi in modo fortemente tipizzato.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-297">However, this method should return a value of a provided `Match` type so that the groups can be accessed in a strongly typed fashion.</span></span> <span data-ttu-id="4b6d7-298">Quindi, si dichiara innanzitutto il `Match` tipo.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-298">Thus, you first declare the `Match` type.</span></span> <span data-ttu-id="4b6d7-299">Poiché questo tipo dipende dal modello fornito come argomento statico, questo tipo deve essere annidato all'interno della definizione del tipo con parametri:</span><span class="sxs-lookup"><span data-stu-id="4b6d7-299">Because this type depends on the pattern that was supplied as a static argument, this type must be nested within the parameterized type definition:</span></span>

```fsharp
let matchTy =
    ProvidedTypeDefinition(
        "MatchType",
        baseType = Some baseTy,
        hideObjectMethods = true)

ty.AddMember matchTy
```

<span data-ttu-id="4b6d7-300">Viene quindi aggiunta una proprietà al tipo di corrispondenza per ogni gruppo.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-300">You then add one property to the Match type for each group.</span></span> <span data-ttu-id="4b6d7-301">In fase di esecuzione, una corrispondenza viene rappresentata come <xref:System.Text.RegularExpressions.Match> valore, quindi la citazione che definisce la proprietà deve utilizzare la <xref:System.Text.RegularExpressions.Match.Groups> proprietà indicizzata per ottenere il gruppo pertinente.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-301">At runtime, a match is represented as a <xref:System.Text.RegularExpressions.Match> value, so the quotation that defines the property must use the <xref:System.Text.RegularExpressions.Match.Groups> indexed property to get the relevant group.</span></span>

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

<span data-ttu-id="4b6d7-302">Si noti anche che si sta aggiungendo la documentazione XML alla proprietà specificata.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-302">Again, note that you’re adding XML documentation to the provided property.</span></span> <span data-ttu-id="4b6d7-303">Si noti inoltre che una proprietà può essere letta se `GetterCode` viene fornita una funzione e la proprietà può essere scritta se viene `SetterCode` fornita una funzione, quindi la proprietà risultante è di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-303">Also note that a property can be read if a `GetterCode` function is provided, and the property can be written if a `SetterCode` function is provided, so the resulting property is read only.</span></span>

<span data-ttu-id="4b6d7-304">A questo punto è possibile creare un metodo di istanza che restituisce un `Match` valore di questo tipo:</span><span class="sxs-lookup"><span data-stu-id="4b6d7-304">Now you can create an instance method that returns a value of this `Match` type:</span></span>

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

<span data-ttu-id="4b6d7-305">Poiché si sta creando un metodo di istanza `args.[0]` , rappresenta `RegexTyped` l'istanza sulla quale viene chiamato il metodo e `args.[1]` è l'argomento di input.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-305">Because you are creating an instance method, `args.[0]` represents the `RegexTyped` instance on which the method is being called, and `args.[1]` is the input argument.</span></span>

<span data-ttu-id="4b6d7-306">Infine, fornire un costruttore in modo che sia possibile creare istanze del tipo fornito.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-306">Finally, provide a constructor so that instances of the provided type can be created.</span></span>

```fsharp
let ctor =
    ProvidedConstructor(
        parameters = [],
        invokeCode = fun args -> <@@ Regex(pattern, options) :> obj @@>)

ctor.AddXmlDoc("Initializes a regular expression instance.")

ty.AddMember ctor
```

<span data-ttu-id="4b6d7-307">Il costruttore cancella semplicemente la creazione di un'istanza di Regex .NET standard, che viene nuovamente sottoposti a Boxing in un `obj` oggetto perché è la cancellazione del tipo fornito.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-307">The constructor merely erases to the creation of a standard .NET Regex instance, which is again boxed to an object because `obj` is the erasure of the provided type.</span></span> <span data-ttu-id="4b6d7-308">Con questa modifica, l'utilizzo dell'API di esempio specificato in precedenza nell'argomento funziona come previsto.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-308">With that change, the sample API usage that specified earlier in the topic works as expected.</span></span> <span data-ttu-id="4b6d7-309">Il codice seguente è completo e finale:</span><span class="sxs-lookup"><span data-stu-id="4b6d7-309">The following code is complete and final:</span></span>

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

### <a name="key-lessons"></a><span data-ttu-id="4b6d7-310">Lezioni chiave</span><span class="sxs-lookup"><span data-stu-id="4b6d7-310">Key Lessons</span></span>

<span data-ttu-id="4b6d7-311">In questa sezione è stato illustrato come creare un provider di tipi che opera sui parametri statici.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-311">This section explained how to create a type provider that operates on its static parameters.</span></span> <span data-ttu-id="4b6d7-312">Il provider controlla il parametro statico e fornisce operazioni in base al relativo valore.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-312">The provider checks the static parameter and provides operations based on its value.</span></span>

## <a name="a-type-provider-that-is-backed-by-local-data"></a><span data-ttu-id="4b6d7-313">Provider di tipi supportato da dati locali</span><span class="sxs-lookup"><span data-stu-id="4b6d7-313">A Type Provider That Is Backed By Local Data</span></span>

<span data-ttu-id="4b6d7-314">Spesso è consigliabile che i provider di tipi presentino API basate solo su parametri statici, ma anche su informazioni provenienti da sistemi locali o remoti.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-314">Frequently you might want type providers to present APIs based on not only static parameters but also information from local or remote systems.</span></span> <span data-ttu-id="4b6d7-315">In questa sezione vengono illustrati i provider di tipi basati su dati locali, ad esempio i file di dati locali.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-315">This section discusses type providers that are based on local data, such as local data files.</span></span>

### <a name="simple-csv-file-provider"></a><span data-ttu-id="4b6d7-316">Provider di file CSV semplice</span><span class="sxs-lookup"><span data-stu-id="4b6d7-316">Simple CSV File Provider</span></span>

<span data-ttu-id="4b6d7-317">Come esempio semplice, si consideri un provider di tipi per l'accesso ai dati scientifici nel formato con valori delimitati da virgole (CSV).</span><span class="sxs-lookup"><span data-stu-id="4b6d7-317">As a simple example, consider a type provider for accessing scientific data in Comma Separated Value (CSV) format.</span></span> <span data-ttu-id="4b6d7-318">In questa sezione si presuppone che i file CSV contengano una riga di intestazione seguita da dati a virgola mobile, come illustrato nella tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="4b6d7-318">This section assumes that the CSV files contain a header row followed by floating point data, as the following table illustrates:</span></span>

|<span data-ttu-id="4b6d7-319">Distanza (contatore)</span><span class="sxs-lookup"><span data-stu-id="4b6d7-319">Distance (meter)</span></span>|<span data-ttu-id="4b6d7-320">Ora (secondo)</span><span class="sxs-lookup"><span data-stu-id="4b6d7-320">Time (second)</span></span>|
|----------------|-------------|
|<span data-ttu-id="4b6d7-321">50.0</span><span class="sxs-lookup"><span data-stu-id="4b6d7-321">50.0</span></span>|<span data-ttu-id="4b6d7-322">3.7</span><span class="sxs-lookup"><span data-stu-id="4b6d7-322">3.7</span></span>|
|<span data-ttu-id="4b6d7-323">100.0</span><span class="sxs-lookup"><span data-stu-id="4b6d7-323">100.0</span></span>|<span data-ttu-id="4b6d7-324">5.2</span><span class="sxs-lookup"><span data-stu-id="4b6d7-324">5.2</span></span>|
|<span data-ttu-id="4b6d7-325">150.0</span><span class="sxs-lookup"><span data-stu-id="4b6d7-325">150.0</span></span>|<span data-ttu-id="4b6d7-326">6.4</span><span class="sxs-lookup"><span data-stu-id="4b6d7-326">6.4</span></span>|

<span data-ttu-id="4b6d7-327">In questa sezione viene illustrato come fornire un tipo che è possibile utilizzare per ottenere le righe `Distance` con una proprietà `float<meter>` di tipo `Time` e una proprietà `float<second>`di tipo.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-327">This section shows how to provide a type that you can use to get rows with a `Distance` property of type `float<meter>` and a `Time` property of type `float<second>`.</span></span> <span data-ttu-id="4b6d7-328">Per semplicità, vengono eseguiti i presupposti seguenti:</span><span class="sxs-lookup"><span data-stu-id="4b6d7-328">For simplicity, the following assumptions are made:</span></span>

- <span data-ttu-id="4b6d7-329">I nomi di intestazione sono senza unità o hanno il formato "nome (unità)" e non contengono virgole.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-329">Header names are either unit-less or have the form "Name (unit)" and don't contain commas.</span></span>

- <span data-ttu-id="4b6d7-330">Le unità sono tutte unità di sistema internazionale (si) come definito dal modulo [Microsoft. FSharp. Data. UnitSystems. siF#. UnitNames Module ()](https://msdn.microsoft.com/library/3cb43485-11f5-4aa7-a779-558f19d4013b) .</span><span class="sxs-lookup"><span data-stu-id="4b6d7-330">Units are all System International (SI) units as the [Microsoft.FSharp.Data.UnitSystems.SI.UnitNames Module (F#)](https://msdn.microsoft.com/library/3cb43485-11f5-4aa7-a779-558f19d4013b) module defines.</span></span>

- <span data-ttu-id="4b6d7-331">Le unità sono tutte semplici (ad esempio, il contatore) invece del composto (ad esempio, il contatore/secondo).</span><span class="sxs-lookup"><span data-stu-id="4b6d7-331">Units are all simple (for example, meter) rather than compound (for example, meter/second).</span></span>

- <span data-ttu-id="4b6d7-332">Tutte le colonne contengono dati a virgola mobile.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-332">All columns contain floating point data.</span></span>

<span data-ttu-id="4b6d7-333">Un provider più completo potrebbe allentare queste restrizioni.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-333">A more complete provider would loosen these restrictions.</span></span>

<span data-ttu-id="4b6d7-334">Anche in questo caso, il primo passaggio consiste nel considerare l'aspetto dell'API.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-334">Again the first step is to consider how the API should look.</span></span> <span data-ttu-id="4b6d7-335">Dato un file `info.csv` con i contenuti della tabella precedente (nel formato delimitato da virgole), gli utenti del provider possono scrivere codice simile all'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="4b6d7-335">Given an `info.csv` file with the contents from the previous table (in comma-separated format), users of the provider should be able to write code that resembles the following example:</span></span>

```fsharp
let info = new MiniCsv<"info.csv">()
for row in info.Data do
let time = row.Time
printfn "%f" (float time)
```

<span data-ttu-id="4b6d7-336">In questo caso, il compilatore deve convertire queste chiamate in qualcosa di simile all'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="4b6d7-336">In this case, the compiler should convert these calls into something like the following example:</span></span>

```fsharp
let info = new CsvFile("info.csv")
for row in info.Data do
let (time:float) = row.[1]
printfn "%f" (float time)
```

<span data-ttu-id="4b6d7-337">La conversione ottimale richiederà al provider di tipi di definire un `CsvFile` tipo reale nell'assembly del provider di tipi.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-337">The optimal translation will require the type provider to define a real `CsvFile` type in the type provider's assembly.</span></span> <span data-ttu-id="4b6d7-338">I provider di tipi spesso si basano su alcuni tipi di helper e metodi per eseguire il wrapping di logica importante.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-338">Type providers often rely on a few helper types and methods to wrap important logic.</span></span> <span data-ttu-id="4b6d7-339">Poiché le misure vengono cancellate in fase di esecuzione, è `float[]` possibile usare come tipo cancellato per una riga.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-339">Because measures are erased at runtime, you can use a `float[]` as the erased type for a row.</span></span> <span data-ttu-id="4b6d7-340">Il compilatore considererà colonne diverse con tipi di misure diversi.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-340">The compiler will treat different columns as having different measure types.</span></span> <span data-ttu-id="4b6d7-341">Ad esempio, la prima colonna dell'esempio è di tipo `float<meter>`, mentre la seconda è `float<second>`.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-341">For example, the first column in our example has type `float<meter>`, and the second has `float<second>`.</span></span> <span data-ttu-id="4b6d7-342">Tuttavia, la rappresentazione cancellata può rimanere piuttosto semplice.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-342">However, the erased representation can remain quite simple.</span></span>

<span data-ttu-id="4b6d7-343">Il codice seguente illustra il nucleo dell'implementazione.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-343">The following code shows the core of the implementation.</span></span>

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

<span data-ttu-id="4b6d7-344">Si notino i seguenti punti sull'implementazione:</span><span class="sxs-lookup"><span data-stu-id="4b6d7-344">Note the following points about the implementation:</span></span>

- <span data-ttu-id="4b6d7-345">I costruttori di overload consentono di leggere il file originale o uno con lo stesso schema.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-345">Overloaded constructors allow either the original file or one that has an identical schema to be read.</span></span> <span data-ttu-id="4b6d7-346">Questo modello è comune quando si scrive un provider di tipi per le origini dati locali o remote e questo modello consente di usare un file locale come modello per i dati remoti.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-346">This pattern is common when you write a type provider for local or remote data sources, and this pattern allows a local file to be used as the template for remote data.</span></span>

- <span data-ttu-id="4b6d7-347">È possibile usare il valore [TypeProviderConfig](https://msdn.microsoft.com/library/1cda7b9a-3d07-475d-9315-d65e1c97eb44) passato al costruttore del provider di tipi per risolvere i nomi di file relativi.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-347">You can use the [TypeProviderConfig](https://msdn.microsoft.com/library/1cda7b9a-3d07-475d-9315-d65e1c97eb44) value that’s passed in to the type provider constructor to resolve relative file names.</span></span>

- <span data-ttu-id="4b6d7-348">È possibile utilizzare il `AddDefinitionLocation` metodo per definire il percorso delle proprietà specificate.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-348">You can use the `AddDefinitionLocation` method to define the location of the provided properties.</span></span> <span data-ttu-id="4b6d7-349">Se pertanto si utilizza `Go To Definition` in una proprietà fornita, il file CSV viene aperto in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-349">Therefore, if you use `Go To Definition` on a provided property, the CSV file will open in Visual Studio.</span></span>

- <span data-ttu-id="4b6d7-350">È possibile usare il `ProvidedMeasureBuilder` tipo per cercare le unità di misura e per generare i tipi `float<_>` pertinenti.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-350">You can use the `ProvidedMeasureBuilder` type to look up the SI units and to generate the relevant `float<_>` types.</span></span>

### <a name="key-lessons"></a><span data-ttu-id="4b6d7-351">Lezioni chiave</span><span class="sxs-lookup"><span data-stu-id="4b6d7-351">Key Lessons</span></span>

<span data-ttu-id="4b6d7-352">In questa sezione è stato illustrato come creare un provider di tipi per un'origine dati locale con uno schema semplice contenuto nell'origine dati stessa.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-352">This section explained how to create a type provider for a local data source with a simple schema that's contained in the data source itself.</span></span>

## <a name="going-further"></a><span data-ttu-id="4b6d7-353">Più avanti</span><span class="sxs-lookup"><span data-stu-id="4b6d7-353">Going Further</span></span>

<span data-ttu-id="4b6d7-354">Le sezioni seguenti includono suggerimenti per un'ulteriore analisi.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-354">The following sections include suggestions for further study.</span></span>

### <a name="a-look-at-the-compiled-code-for-erased-types"></a><span data-ttu-id="4b6d7-355">Esaminare il codice compilato per i tipi cancellati</span><span class="sxs-lookup"><span data-stu-id="4b6d7-355">A Look at the Compiled Code for Erased Types</span></span>

<span data-ttu-id="4b6d7-356">Per avere un'idea di come l'uso del provider di tipi corrisponda al codice emesso, esaminare la funzione seguente usando l'oggetto `HelloWorldTypeProvider` usato in precedenza in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-356">To give you some idea of how the use of the type provider corresponds to the code that's emitted, look at the following function by using the `HelloWorldTypeProvider` that's used earlier in this topic.</span></span>

```fsharp
let function1 () =
    let obj1 = Samples.HelloWorldTypeProvider.Type1("some data")
    obj1.InstanceProperty
```

<span data-ttu-id="4b6d7-357">Ecco un'immagine del codice risultante decompilato usando Ildasm. exe:</span><span class="sxs-lookup"><span data-stu-id="4b6d7-357">Here’s an image of the resulting code decompiled by using ildasm.exe:</span></span>

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

<span data-ttu-id="4b6d7-358">Come illustrato nell'esempio, tutte le menzioni del tipo `Type1` e della `InstanceProperty` proprietà sono state cancellate, lasciando solo le operazioni sui tipi di runtime necessari.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-358">As the example shows, all mentions of the type `Type1` and the `InstanceProperty` property have been erased, leaving only operations on the runtime types involved.</span></span>

### <a name="design-and-naming-conventions-for-type-providers"></a><span data-ttu-id="4b6d7-359">Convenzioni di progettazione e denominazione per i provider di tipi</span><span class="sxs-lookup"><span data-stu-id="4b6d7-359">Design and Naming Conventions for Type Providers</span></span>

<span data-ttu-id="4b6d7-360">Quando si creano provider di tipi, osservare le convenzioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-360">Observe the following conventions when authoring type providers.</span></span>

<span data-ttu-id="4b6d7-361">**Provider per i protocolli di connettività** In generale, i nomi della maggior parte delle dll del provider per i protocolli di connettività di dati e servizi, ad esempio le `TypeProvider` connessioni `TypeProviders`OData o SQL, devono terminare con o.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-361">**Providers for Connectivity Protocols** In general, names of most provider DLLs for data and service connectivity protocols, such as OData or SQL connections, should end in `TypeProvider` or `TypeProviders`.</span></span> <span data-ttu-id="4b6d7-362">Usare, ad esempio, un nome di DLL simile alla stringa seguente:</span><span class="sxs-lookup"><span data-stu-id="4b6d7-362">For example, use a DLL name that resembles the following string:</span></span>

`Fabrikam.Management.BasicTypeProviders.dll`

<span data-ttu-id="4b6d7-363">Verificare che i tipi forniti siano membri dello spazio dei nomi corrispondente e indicare il protocollo di connettività implementato:</span><span class="sxs-lookup"><span data-stu-id="4b6d7-363">Ensure that your provided types are members of the corresponding namespace, and indicate the connectivity protocol that you implemented:</span></span>

```fsharp
  Fabrikam.Management.BasicTypeProviders.WmiConnection<…>
  Fabrikam.Management.BasicTypeProviders.DataProtocolConnection<…>
```

<span data-ttu-id="4b6d7-364">**Provider di utilità per la codifica generale**.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-364">**Utility Providers for General Coding**.</span></span>  <span data-ttu-id="4b6d7-365">Per un provider del tipo di utilità, ad esempio per le espressioni regolari, il provider di tipi può fare parte di una libreria di base, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="4b6d7-365">For a utility type provider such as that for regular expressions, the type provider may be part of a base library, as the following example shows:</span></span>

```fsharp
#r "Fabrikam.Core.Text.Utilities.dll"
```

<span data-ttu-id="4b6d7-366">In questo caso, il tipo fornito viene visualizzato in un punto appropriato secondo le normali convenzioni di progettazione .NET:</span><span class="sxs-lookup"><span data-stu-id="4b6d7-366">In this case, the provided type would appear at an appropriate point according to normal .NET design conventions:</span></span>

```fsharp
  open Fabrikam.Core.Text.RegexTyped

  let regex = new RegexTyped<"a+b+a+b+">()
```

<span data-ttu-id="4b6d7-367">**Origini dati singleton**.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-367">**Singleton Data Sources**.</span></span> <span data-ttu-id="4b6d7-368">Alcuni provider di tipi si connettono a una singola origine dati dedicata e forniscono solo i dati.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-368">Some type providers connect to a single dedicated data source and provide only data.</span></span> <span data-ttu-id="4b6d7-369">In questo caso, è necessario eliminare il `TypeProvider` suffisso e usare le convenzioni normali per la denominazione .NET:</span><span class="sxs-lookup"><span data-stu-id="4b6d7-369">In this case, you should drop the `TypeProvider` suffix and use normal conventions for .NET naming:</span></span>

```fsharp
#r "Fabrikam.Data.Freebase.dll"

let data = Fabrikam.Data.Freebase.Astronomy.Asteroids
```

<span data-ttu-id="4b6d7-370">Per ulteriori informazioni, vedere la `GetConnection` convenzione di progettazione descritta più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-370">For more information, see the `GetConnection` design convention that's described later in this topic.</span></span>

### <a name="design-patterns-for-type-providers"></a><span data-ttu-id="4b6d7-371">Modelli di progettazione per i provider di tipi</span><span class="sxs-lookup"><span data-stu-id="4b6d7-371">Design Patterns for Type Providers</span></span>

<span data-ttu-id="4b6d7-372">Le sezioni seguenti descrivono i modelli di progettazione che è possibile usare per la creazione di provider di tipi.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-372">The following sections describe design patterns you can use when authoring type providers.</span></span>

#### <a name="the-getconnection-design-pattern"></a><span data-ttu-id="4b6d7-373">Modello di Progettazione GetConnection</span><span class="sxs-lookup"><span data-stu-id="4b6d7-373">The GetConnection Design Pattern</span></span>

<span data-ttu-id="4b6d7-374">La maggior parte dei provider di tipi deve essere `GetConnection` scritta in modo da usare il modello usato dai provider di tipi in FSharp. Data. TypeProviders. dll, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="4b6d7-374">Most type providers should be written to use the `GetConnection` pattern that's used by the type providers in FSharp.Data.TypeProviders.dll, as the following example shows:</span></span>

```fsharp
#r "Fabrikam.Data.WebDataStore.dll"

type Service = Fabrikam.Data.WebDataStore<…static connection parameters…>

let connection = Service.GetConnection(…dynamic connection parameters…)

let data = connection.Astronomy.Asteroids
```

#### <a name="type-providers-backed-by-remote-data-and-services"></a><span data-ttu-id="4b6d7-375">Provider di tipi supportati da servizi e dati remoti</span><span class="sxs-lookup"><span data-stu-id="4b6d7-375">Type Providers Backed By Remote Data and Services</span></span>

<span data-ttu-id="4b6d7-376">Prima di creare un provider di tipi supportato da servizi e dati remoti, è necessario considerare una serie di problemi inerenti alla programmazione connessa.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-376">Before you create a type provider that's backed by remote data and services, you must consider a range of issues that are inherent in connected programming.</span></span> <span data-ttu-id="4b6d7-377">Questi problemi includono le considerazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="4b6d7-377">These issues include the following considerations:</span></span>

- <span data-ttu-id="4b6d7-378">mapping dello schema</span><span class="sxs-lookup"><span data-stu-id="4b6d7-378">schema mapping</span></span>

- <span data-ttu-id="4b6d7-379">Livezza e invalidamento in presenza di modifiche dello schema</span><span class="sxs-lookup"><span data-stu-id="4b6d7-379">liveness and invalidation in the presence of schema change</span></span>

- <span data-ttu-id="4b6d7-380">Caching dello schema</span><span class="sxs-lookup"><span data-stu-id="4b6d7-380">schema caching</span></span>

- <span data-ttu-id="4b6d7-381">implementazioni asincrone di operazioni di accesso ai dati</span><span class="sxs-lookup"><span data-stu-id="4b6d7-381">asynchronous implementations of data access operations</span></span>

- <span data-ttu-id="4b6d7-382">supporto delle query, incluse le query LINQ</span><span class="sxs-lookup"><span data-stu-id="4b6d7-382">supporting queries, including LINQ queries</span></span>

- <span data-ttu-id="4b6d7-383">credenziali e autenticazione</span><span class="sxs-lookup"><span data-stu-id="4b6d7-383">credentials and authentication</span></span>

<span data-ttu-id="4b6d7-384">Questo argomento non Esplora ulteriormente questi problemi.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-384">This topic doesn't explore these issues further.</span></span>

### <a name="additional-authoring-techniques"></a><span data-ttu-id="4b6d7-385">Tecniche di creazione aggiuntive</span><span class="sxs-lookup"><span data-stu-id="4b6d7-385">Additional Authoring Techniques</span></span>

<span data-ttu-id="4b6d7-386">Quando si scrivono provider di tipi personalizzati, è consigliabile usare le tecniche aggiuntive seguenti.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-386">When you write your own type providers, you might want to use the following additional techniques.</span></span>

### <a name="creating-types-and-members-on-demand"></a><span data-ttu-id="4b6d7-387">Creazione di tipi e membri su richiesta</span><span class="sxs-lookup"><span data-stu-id="4b6d7-387">Creating Types and Members On-Demand</span></span>

<span data-ttu-id="4b6d7-388">L'API ProvidedType ha versioni ritardate di AddMember.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-388">The ProvidedType API has delayed versions of AddMember.</span></span>

```fsharp
  type ProvidedType =
      member AddMemberDelayed  : (unit -> MemberInfo)      -> unit
      member AddMembersDelayed : (unit -> MemberInfo list) -> unit
```

<span data-ttu-id="4b6d7-389">Queste versioni vengono usate per creare spazi su richiesta di tipi.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-389">These versions are used to create on-demand spaces of types.</span></span>

### <a name="providing-array-types-and-generic-type-instantiations"></a><span data-ttu-id="4b6d7-390">Fornire tipi di matrici e creazioni di istanze di tipi generici</span><span class="sxs-lookup"><span data-stu-id="4b6d7-390">Providing Array types and Generic Type Instantiations</span></span>

<span data-ttu-id="4b6d7-391">I membri forniti, le cui firme includono i tipi di matrice, i tipi ByRef e le creazioni di istanze di tipi generici `MakeArrayType`, `MakePointerType`usano i `MakeGenericType` normali, e in <xref:System.Type>qualsiasi istanza `ProvidedTypeDefinitions`di, incluso.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-391">You make provided members (whose signatures include array types, byref types, and instantiations of generic types) by using the normal `MakeArrayType`, `MakePointerType`, and `MakeGenericType` on any instance of <xref:System.Type>, including `ProvidedTypeDefinitions`.</span></span>

> [!NOTE]
> <span data-ttu-id="4b6d7-392">In alcuni casi potrebbe essere necessario utilizzare l'helper in `ProvidedTypeBuilder.MakeGenericType`.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-392">In some cases you may have to use the helper in `ProvidedTypeBuilder.MakeGenericType`.</span></span>  <span data-ttu-id="4b6d7-393">Per altri dettagli, vedere la [documentazione relativa all'SDK del provider di tipi](https://github.com/fsprojects/FSharp.TypeProviders.SDK/blob/master/README.md#explicit-construction-of-code-makegenerictype-makegenericmethod-and-uncheckedquotations) .</span><span class="sxs-lookup"><span data-stu-id="4b6d7-393">See the [Type Provider SDK documentation](https://github.com/fsprojects/FSharp.TypeProviders.SDK/blob/master/README.md#explicit-construction-of-code-makegenerictype-makegenericmethod-and-uncheckedquotations) for more details.</span></span>

### <a name="providing-unit-of-measure-annotations"></a><span data-ttu-id="4b6d7-394">Specifica di un'unità di annotazioni di misura</span><span class="sxs-lookup"><span data-stu-id="4b6d7-394">Providing Unit of Measure Annotations</span></span>

<span data-ttu-id="4b6d7-395">L'API ProvidedTypes fornisce helper per fornire annotazioni di misura.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-395">The ProvidedTypes API provides helpers for providing measure annotations.</span></span> <span data-ttu-id="4b6d7-396">Per fornire il tipo `float<kg>`, ad esempio, usare il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="4b6d7-396">For example, to provide the type `float<kg>`, use the following code:</span></span>

```fsharp
  let measures = ProvidedMeasureBuilder.Default
  let kg = measures.SI "kilogram"
  let m = measures.SI "meter"
  let float_kg = measures.AnnotateType(typeof<float>,[kg])
```

  <span data-ttu-id="4b6d7-397">Per fornire il tipo `Nullable<decimal<kg/m^2>>`, usare il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="4b6d7-397">To provide the type `Nullable<decimal<kg/m^2>>`, use the following code:</span></span>

```fsharp
  let kgpm2 = measures.Ratio(kg, measures.Square m)
  let dkgpm2 = measures.AnnotateType(typeof<decimal>,[kgpm2])
  let nullableDecimal_kgpm2 = typedefof<System.Nullable<_>>.MakeGenericType [|dkgpm2 |]
```

### <a name="accessing-project-local-or-script-local-resources"></a><span data-ttu-id="4b6d7-398">Accesso alle risorse locali del progetto o dello script</span><span class="sxs-lookup"><span data-stu-id="4b6d7-398">Accessing Project-Local or Script-Local Resources</span></span>

<span data-ttu-id="4b6d7-399">A ogni istanza di un provider di tipi può essere `TypeProviderConfig` assegnato un valore durante la costruzione.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-399">Each instance of a type provider can be given a `TypeProviderConfig` value during construction.</span></span> <span data-ttu-id="4b6d7-400">Questo valore contiene la "cartella di risoluzione" per il provider, ovvero la cartella di progetto per la compilazione o la directory che contiene uno script, l'elenco degli assembly a cui si fa riferimento e altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-400">This value contains the "resolution folder" for the provider (that is, the project folder for the compilation or the directory that contains a script), the list of referenced assemblies, and other information.</span></span>

### <a name="invalidation"></a><span data-ttu-id="4b6d7-401">Invalidamento</span><span class="sxs-lookup"><span data-stu-id="4b6d7-401">Invalidation</span></span>

<span data-ttu-id="4b6d7-402">I provider possono generare segnali di invalidazione per F# notificare al servizio di linguaggio che è possibile che si siano modificati i presupposti dello schema.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-402">Providers can raise invalidation signals to notify the F# language service that the schema assumptions may have changed.</span></span> <span data-ttu-id="4b6d7-403">Quando si verifica l'invalidamento, viene eseguito il riesecuzione di un typecheck se il provider è ospitato in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-403">When invalidation occurs, a typecheck is redone if the provider is being hosted in Visual Studio.</span></span> <span data-ttu-id="4b6d7-404">Questo segnale verrà ignorato quando il provider è ospitato in F# Interactive o dal F# compilatore (FSC. exe).</span><span class="sxs-lookup"><span data-stu-id="4b6d7-404">This signal will be ignored when the provider is hosted in F# Interactive or by the F# Compiler (fsc.exe).</span></span>

### <a name="caching-schema-information"></a><span data-ttu-id="4b6d7-405">Memorizzazione nella cache delle informazioni sullo schema</span><span class="sxs-lookup"><span data-stu-id="4b6d7-405">Caching Schema Information</span></span>

<span data-ttu-id="4b6d7-406">I provider devono spesso memorizzare nella cache l'accesso alle informazioni dello schema.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-406">Providers must often cache access to schema information.</span></span> <span data-ttu-id="4b6d7-407">I dati memorizzati nella cache devono essere archiviati usando un nome file specificato come parametro statico o come dati utente.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-407">The cached data should be stored by using a file name that's given as a static parameter or as user data.</span></span> <span data-ttu-id="4b6d7-408">Un esempio di memorizzazione nella cache degli schemi `LocalSchemaFile` è il parametro nei provider di tipi `FSharp.Data.TypeProviders` nell'assembly.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-408">An example of schema caching is the `LocalSchemaFile` parameter in the type providers in the `FSharp.Data.TypeProviders` assembly.</span></span> <span data-ttu-id="4b6d7-409">Nell'implementazione di questi provider, questo parametro statico indica al provider di tipi di utilizzare le informazioni sullo schema nel file locale specificato anziché accedere all'origine dati tramite la rete.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-409">In the implementation of these providers, this static parameter directs the type provider to use the schema information in the specified local file instead of accessing the data source over the network.</span></span> <span data-ttu-id="4b6d7-410">Per utilizzare le informazioni dello schema memorizzate nella cache, è necessario `ForceUpdate` impostare `false`anche il parametro statico su.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-410">To use cached schema information, you must also set the static parameter `ForceUpdate` to `false`.</span></span> <span data-ttu-id="4b6d7-411">È possibile usare una tecnica simile per abilitare l'accesso ai dati online e offline.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-411">You could use a similar technique to enable online and offline data access.</span></span>

### <a name="backing-assembly"></a><span data-ttu-id="4b6d7-412">Assembly di backup</span><span class="sxs-lookup"><span data-stu-id="4b6d7-412">Backing Assembly</span></span>

<span data-ttu-id="4b6d7-413">Quando si compila un `.dll` file `.exe` o, il file dll sottostante per i tipi generati viene collegato in modo statico nell'assembly risultante.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-413">When you compile a `.dll` or `.exe` file, the backing .dll file for generated types is statically linked into the resulting assembly.</span></span> <span data-ttu-id="4b6d7-414">Questo collegamento viene creato copiando le definizioni del tipo Intermediate Language (IL) e tutte le risorse gestite dall'assembly di supporto nell'assembly finale.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-414">This link is created by copying the Intermediate Language (IL) type definitions and any managed resources from the backing assembly into the final assembly.</span></span> <span data-ttu-id="4b6d7-415">Quando si usa F# Interactive, il file con estensione dll di backup non viene copiato e viene invece caricato F# direttamente nel processo interattivo.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-415">When you use F# Interactive, the backing .dll file isn't copied and is instead loaded directly into the F# Interactive process.</span></span>

### <a name="exceptions-and-diagnostics-from-type-providers"></a><span data-ttu-id="4b6d7-416">Eccezioni e diagnostica dai provider di tipi</span><span class="sxs-lookup"><span data-stu-id="4b6d7-416">Exceptions and Diagnostics from Type Providers</span></span>

<span data-ttu-id="4b6d7-417">Tutti gli utilizzi di tutti i membri dei tipi specificati possono generare eccezioni.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-417">All uses of all members from provided types may throw exceptions.</span></span> <span data-ttu-id="4b6d7-418">In tutti i casi, se un provider di tipi genera un'eccezione, il compilatore host attribuisce l'errore a un provider di tipi specifico.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-418">In all cases, if a type provider throws an exception, the host compiler attributes the error to a specific type provider.</span></span>

- <span data-ttu-id="4b6d7-419">Le eccezioni del provider di tipi non devono mai causare errori interni del compilatore.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-419">Type provider exceptions should never result in internal compiler errors.</span></span>

- <span data-ttu-id="4b6d7-420">I provider di tipi non possono segnalare avvisi.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-420">Type providers can't report warnings.</span></span>

- <span data-ttu-id="4b6d7-421">Quando un provider di tipi è ospitato nel F# compilatore, un F# ambiente di sviluppo o F# interattivo, vengono rilevate tutte le eccezioni del provider.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-421">When a type provider is hosted in the F# compiler, an F# development environment, or F# Interactive, all exceptions from that provider are caught.</span></span> <span data-ttu-id="4b6d7-422">La proprietà Message è sempre il testo dell'errore e non viene visualizzata alcuna traccia dello stack.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-422">The Message property is always the error text, and no stack trace appears.</span></span> <span data-ttu-id="4b6d7-423">Se si sta per generare un'eccezione, è possibile generare gli esempi seguenti: `System.NotSupportedException`, `System.IO.IOException`, `System.Exception`.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-423">If you’re going to throw an exception, you can throw the following examples: `System.NotSupportedException`, `System.IO.IOException`, `System.Exception`.</span></span>

#### <a name="providing-generated-types"></a><span data-ttu-id="4b6d7-424">Fornire tipi generati</span><span class="sxs-lookup"><span data-stu-id="4b6d7-424">Providing Generated Types</span></span>

<span data-ttu-id="4b6d7-425">Fino a questo punto, questo documento ha illustrato come fornire tipi cancellati.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-425">So far, this document has explained how to provide erased types.</span></span> <span data-ttu-id="4b6d7-426">È anche possibile usare il meccanismo del provider di F# tipi in per fornire i tipi generati, che vengono aggiunti come definizioni di tipo .NET reali al programma degli utenti.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-426">You can also use the type provider mechanism in F# to provide generated types, which are added as real .NET type definitions into the users' program.</span></span> <span data-ttu-id="4b6d7-427">È necessario fare riferimento ai tipi forniti generati utilizzando una definizione di tipo.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-427">You must refer to generated provided types by using a type definition.</span></span>

```fsharp
open Microsoft.FSharp.TypeProviders

type Service = ODataService<"http://services.odata.org/Northwind/Northwind.svc/">
```

<span data-ttu-id="4b6d7-428">Il codice helper ProvidedTypes-0,2 che fa parte della versione F# 3,0 ha solo un supporto limitato per la fornitura di tipi generati.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-428">The ProvidedTypes-0.2 helper code that is part of the F# 3.0 release has only limited support for providing generated types.</span></span> <span data-ttu-id="4b6d7-429">Per una definizione di tipo generata è necessario che siano soddisfatte le istruzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="4b6d7-429">The following statements must be true for a generated type definition:</span></span>

- <span data-ttu-id="4b6d7-430">`isErased`deve essere impostato su `false`.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-430">`isErased` must be set to `false`.</span></span>

- <span data-ttu-id="4b6d7-431">Il tipo generato deve essere aggiunto a un oggetto appena `ProvidedAssembly()`costruito, che rappresenta un contenitore per i frammenti di codice generati.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-431">The generated type must be added to a newly constructed `ProvidedAssembly()`, which represents a container for generated code fragments.</span></span>

- <span data-ttu-id="4b6d7-432">Il provider deve disporre di un assembly con un file con estensione dll .NET che esegue il backup con un file dll corrispondente su disco.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-432">The provider must have an assembly that has an actual backing .NET .dll file with a matching .dll file on disk.</span></span>

## <a name="rules-and-limitations"></a><span data-ttu-id="4b6d7-433">Regole e limitazioni</span><span class="sxs-lookup"><span data-stu-id="4b6d7-433">Rules and Limitations</span></span>

<span data-ttu-id="4b6d7-434">Quando si scrivono provider di tipi, tenere presenti le regole e le limitazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-434">When you write type providers, keep the following rules and limitations in mind.</span></span>

### <a name="provided-types-must-be-reachable"></a><span data-ttu-id="4b6d7-435">I tipi specificati devono essere raggiungibili</span><span class="sxs-lookup"><span data-stu-id="4b6d7-435">Provided types must be reachable</span></span>

<span data-ttu-id="4b6d7-436">Tutti i tipi forniti devono essere raggiungibili dai tipi non annidati.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-436">All provided types should be reachable from the non-nested types.</span></span> <span data-ttu-id="4b6d7-437">I tipi non annidati sono specificati nella chiamata al `TypeProviderForNamespaces` costruttore o a una chiamata a. `AddNamespace`</span><span class="sxs-lookup"><span data-stu-id="4b6d7-437">The non-nested types are given in the call to the `TypeProviderForNamespaces` constructor or a call to `AddNamespace`.</span></span> <span data-ttu-id="4b6d7-438">Se, ad esempio, il provider fornisce un `StaticClass.P : T`tipo, è necessario assicurarsi che T sia un tipo non annidato o annidato sotto uno.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-438">For example, if the provider provides a type `StaticClass.P : T`, you must ensure that T is either a non-nested type or nested under one.</span></span>

<span data-ttu-id="4b6d7-439">Alcuni provider, ad esempio, hanno una classe statica, `DataTypes` ad esempio, `T1, T2, T3, ...` che contengono questi tipi.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-439">For example, some providers have a static class such as `DataTypes` that contain these `T1, T2, T3, ...` types.</span></span> <span data-ttu-id="4b6d7-440">In caso contrario, l'errore indica che è stato trovato un riferimento al tipo T nell'assembly A, ma non è stato possibile trovare il tipo nell'assembly.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-440">Otherwise, the error says that a reference to type T in assembly A was found, but the type couldn't be found in that assembly.</span></span> <span data-ttu-id="4b6d7-441">Se viene visualizzato questo errore, verificare che tutti i sottotipi possano essere raggiunti dai tipi di provider.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-441">If this error appears, verify that all your subtypes can be reached from the provider types.</span></span> <span data-ttu-id="4b6d7-442">Nota: Questi `T1, T2, T3...` tipi sono definiti tipi in tempo *reale* .</span><span class="sxs-lookup"><span data-stu-id="4b6d7-442">Note: These `T1, T2, T3...` types are referred to as the *on-the-fly* types.</span></span> <span data-ttu-id="4b6d7-443">Ricordarsi di inserirli in uno spazio dei nomi accessibile o in un tipo padre.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-443">Remember to put them in an accessible namespace or a parent type.</span></span>

### <a name="limitations-of-the-type-provider-mechanism"></a><span data-ttu-id="4b6d7-444">Limitazioni del meccanismo del provider di tipi</span><span class="sxs-lookup"><span data-stu-id="4b6d7-444">Limitations of the Type Provider Mechanism</span></span>

<span data-ttu-id="4b6d7-445">Il meccanismo del provider di F# tipi in presenta le limitazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="4b6d7-445">The type provider mechanism in F# has the following limitations:</span></span>

- <span data-ttu-id="4b6d7-446">L'infrastruttura sottostante per i provider di F# tipi in non supporta i tipi generici forniti o i metodi generici forniti.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-446">The underlying infrastructure for type providers in F# doesn't support provided generic types or provided generic methods.</span></span>

- <span data-ttu-id="4b6d7-447">Il meccanismo non supporta i tipi annidati con parametri statici.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-447">The mechanism doesn't support nested types with static parameters.</span></span>

## <a name="development-tips"></a><span data-ttu-id="4b6d7-448">Suggerimenti per lo sviluppo</span><span class="sxs-lookup"><span data-stu-id="4b6d7-448">Development Tips</span></span>

<span data-ttu-id="4b6d7-449">I suggerimenti seguenti potrebbero risultare utili durante il processo di sviluppo:</span><span class="sxs-lookup"><span data-stu-id="4b6d7-449">You might find the following tips helpful during the development process:</span></span>

### <a name="run-two-instances-of-visual-studio"></a><span data-ttu-id="4b6d7-450">Eseguire due istanze di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="4b6d7-450">Run two instances of Visual Studio</span></span>

<span data-ttu-id="4b6d7-451">È possibile sviluppare il provider di tipi in un'istanza e testare il provider nell'altro perché l'IDE di test accetterà un blocco sul file con estensione dll che impedisce la ricompilazione del provider di tipi.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-451">You can develop the type provider in one instance and test the provider in the other because the test IDE will take a lock on the .dll file that prevents the type provider from being rebuilt.</span></span> <span data-ttu-id="4b6d7-452">Pertanto, è necessario chiudere la seconda istanza di Visual Studio mentre il provider viene compilato nella prima istanza, quindi è necessario riaprire la seconda istanza dopo la compilazione del provider.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-452">Thus, you must close the second instance of Visual Studio while the provider is built in the first instance, and then you must reopen the second instance after the provider is built.</span></span>

### <a name="debug-type-providers-by-using-invocations-of-fscexe"></a><span data-ttu-id="4b6d7-453">Eseguire il debug di provider di tipi usando le chiamate di FSC. exe</span><span class="sxs-lookup"><span data-stu-id="4b6d7-453">Debug type providers by using invocations of fsc.exe</span></span>

<span data-ttu-id="4b6d7-454">È possibile richiamare i provider di tipi utilizzando gli strumenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="4b6d7-454">You can invoke type providers by using the following tools:</span></span>

- <span data-ttu-id="4b6d7-455">FSC. exe (compilatore F# della riga di comando)</span><span class="sxs-lookup"><span data-stu-id="4b6d7-455">fsc.exe (The F# command line compiler)</span></span>

- <span data-ttu-id="4b6d7-456">FSI. exe (compilatore F# interattivo)</span><span class="sxs-lookup"><span data-stu-id="4b6d7-456">fsi.exe (The F# Interactive compiler)</span></span>

- <span data-ttu-id="4b6d7-457">devenv.exe (Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="4b6d7-457">devenv.exe (Visual Studio)</span></span>

<span data-ttu-id="4b6d7-458">Spesso è possibile eseguire il debug dei provider di tipi usando FSC. exe in un file script di test, ad esempio script. FSX.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-458">You can often debug type providers most easily by using fsc.exe on a test script file (for example, script.fsx).</span></span> <span data-ttu-id="4b6d7-459">È possibile avviare un debugger da un prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-459">You can launch a debugger from a command prompt.</span></span>

```console
devenv /debugexe fsc.exe script.fsx
```

  <span data-ttu-id="4b6d7-460">È possibile usare la registrazione da stampa a stdout.</span><span class="sxs-lookup"><span data-stu-id="4b6d7-460">You can use print-to-stdout logging.</span></span>

## <a name="see-also"></a><span data-ttu-id="4b6d7-461">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4b6d7-461">See also</span></span>

- [<span data-ttu-id="4b6d7-462">Provider di tipi</span><span class="sxs-lookup"><span data-stu-id="4b6d7-462">Type Providers</span></span>](index.md)
- [<span data-ttu-id="4b6d7-463">SDK del provider di tipi</span><span class="sxs-lookup"><span data-stu-id="4b6d7-463">The Type Provider SDK</span></span>](https://github.com/fsprojects/FSharp.TypeProviders.SDK)

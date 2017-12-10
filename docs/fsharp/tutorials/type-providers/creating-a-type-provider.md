---
title: 'Esercitazione: Creazione di un provider di tipi (F#)'
description: 'Informazioni su come creare propri provider di tipi F # in F # 3.0 esaminando i diversi provider di tipo semplice per illustrare i concetti di base.'
keywords: visual f#, f#, programmazione funzionale
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 82bec076-19d4-470c-979f-6c3a14b7c70a
ms.openlocfilehash: 58003c88baf0f8aeea1a511334b99bd0295f8bf1
ms.sourcegitcommit: 685143b62385500f59bc36274b8adb191f573a16
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2017
---
# <a name="tutorial-creating-a-type-provider"></a><span data-ttu-id="37784-104">Esercitazione: Creazione di un Provider di tipi</span><span class="sxs-lookup"><span data-stu-id="37784-104">Tutorial: Creating a Type Provider</span></span>

> [!NOTE]
<span data-ttu-id="37784-105">Questa guida è stata scritta per F # 3.0 e verrà aggiornata.</span><span class="sxs-lookup"><span data-stu-id="37784-105">This guide was written for F# 3.0 and will be updated.</span></span>

<span data-ttu-id="37784-106">Il meccanismo di provider F # 3.0 è una parte significativa del supporto per la programmazione avanzata di informazioni.</span><span class="sxs-lookup"><span data-stu-id="37784-106">The type provider mechanism in F# 3.0 is a significant part of its support for information rich programming.</span></span> <span data-ttu-id="37784-107">In questa esercitazione viene illustrato come creare i propri provider di tipo con lo sviluppo di diversi provider di tipo semplice per illustrare i concetti di base.</span><span class="sxs-lookup"><span data-stu-id="37784-107">This tutorial explains how to create your own type providers by walking you through the development of several simple type providers to illustrate the basic concepts.</span></span> <span data-ttu-id="37784-108">Per ulteriori informazioni sul meccanismo di provider di tipo in F #, vedere [provider di tipi](index.md).</span><span class="sxs-lookup"><span data-stu-id="37784-108">For more information about the type provider mechanism in F#, see [Type Providers](index.md).</span></span>

<span data-ttu-id="37784-109">F # 3.0 contiene diversi provider di tipi incorporati per servizi dati Internet e aziendali uso comune.</span><span class="sxs-lookup"><span data-stu-id="37784-109">F# 3.0 contains several built-in type providers for commonly used Internet and enterprise data services.</span></span> <span data-ttu-id="37784-110">Questi provider di tipo forniscono un accesso semplice e regolare a database relazionali SQL e i servizi OData e WSDL basati sulla rete.</span><span class="sxs-lookup"><span data-stu-id="37784-110">These type providers give simple and regular access to SQL relational databases and network-based OData and WSDL services.</span></span> <span data-ttu-id="37784-111">Questi provider supportano inoltre l'utilizzo di query LINQ F # rispetto a tali origini dati.</span><span class="sxs-lookup"><span data-stu-id="37784-111">These providers also support the use of F# LINQ queries against these data sources.</span></span>

<span data-ttu-id="37784-112">Se necessario, è possibile creare provider di tipi personalizzati o è possibile fare riferimento a provider di tipi creati da altri.</span><span class="sxs-lookup"><span data-stu-id="37784-112">Where necessary, you can create custom type providers, or you can reference type providers that others have created.</span></span> <span data-ttu-id="37784-113">Ad esempio, l'organizzazione potrebbe avere un servizio dati che fornisce un numero elevato e crescente di set di dati denominati, ciascuno con il proprio schema dati stabile.</span><span class="sxs-lookup"><span data-stu-id="37784-113">For example, your organization could have a data service that provides a large and growing number of named data sets, each with its own stable data schema.</span></span> <span data-ttu-id="37784-114">È possibile creare un provider di tipi che legge gli schemi ed elenca i set di dati correnti per il programmatore in una modalità fortemente tipizzata.</span><span class="sxs-lookup"><span data-stu-id="37784-114">You can create a type provider that reads the schemas and presents the current data sets to the programmer in a strongly typed way.</span></span>


## <a name="before-you-start"></a><span data-ttu-id="37784-115">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="37784-115">Before You Start</span></span>
<span data-ttu-id="37784-116">Il meccanismo di provider è stato progettato principalmente per inserire dati stabili e informazioni di servizio in F # esperienza di programmazione.</span><span class="sxs-lookup"><span data-stu-id="37784-116">The type provider mechanism is primarily designed for injecting stable data and service information spaces into the F# programming experience.</span></span>

<span data-ttu-id="37784-117">Questo meccanismo non è progettato per l'inserimento di spazi di informazioni il cui schema cambia durante l'esecuzione del programma in modo tale che riguardano la logica del programma.</span><span class="sxs-lookup"><span data-stu-id="37784-117">This mechanism isn’t designed for injecting information spaces whose schema changes during program execution in ways that are relevant to program logic.</span></span> <span data-ttu-id="37784-118">Inoltre, il meccanismo non è progettato per intra-language metaprogrammazione, anche se tale dominio contiene alcuni utilizzi validi.</span><span class="sxs-lookup"><span data-stu-id="37784-118">Also, the mechanism isn't designed for intra-language meta-programming, even though that domain contains some valid uses.</span></span> <span data-ttu-id="37784-119">Solo se necessario, è consigliabile utilizzare questo meccanismo di e in cui lo sviluppo di un provider di tipi restituisce un valore molto elevato.</span><span class="sxs-lookup"><span data-stu-id="37784-119">You should use this mechanism only where necessary and where the development of a type provider yields very high value.</span></span>

<span data-ttu-id="37784-120">È consigliabile evitare la scrittura di un provider di tipi in cui non è disponibile uno schema.</span><span class="sxs-lookup"><span data-stu-id="37784-120">You should avoid writing a type provider where a schema isn't available.</span></span> <span data-ttu-id="37784-121">Analogamente, è consigliabile evitare di scrivere un provider di tipi in un normale (o anche un oggetto esistente) basterebbe libreria .NET.</span><span class="sxs-lookup"><span data-stu-id="37784-121">Likewise, you should avoid writing a type provider where an ordinary (or even an existing) .NET library would suffice.</span></span>

<span data-ttu-id="37784-122">Prima di iniziare, è possibile porre le domande seguenti:</span><span class="sxs-lookup"><span data-stu-id="37784-122">Before you start, you might ask the following questions:</span></span>


- <span data-ttu-id="37784-123">È necessario uno schema per l'origine di informazioni?</span><span class="sxs-lookup"><span data-stu-id="37784-123">Do you have a schema for your information source?</span></span> <span data-ttu-id="37784-124">In questo caso, qual è il mapping in F # e sistema di tipi di .NET?</span><span class="sxs-lookup"><span data-stu-id="37784-124">If so, what’s the mapping into the F# and .NET type system?</span></span>

- <span data-ttu-id="37784-125">È possibile utilizzare un'API (tipizzata in modo dinamico) esistente come punto di partenza per l'implementazione?</span><span class="sxs-lookup"><span data-stu-id="37784-125">Can you use an existing (dynamically typed) API as a starting point for your implementation?</span></span>

- <span data-ttu-id="37784-126">La propria organizzazione avranno sufficiente utilizza del provider di tipi a scrivere utile?</span><span class="sxs-lookup"><span data-stu-id="37784-126">Will you and your organization have enough uses of the type provider to make writing it worthwhile?</span></span> <span data-ttu-id="37784-127">Sarebbe una normale libreria .NET alle proprie esigenze?</span><span class="sxs-lookup"><span data-stu-id="37784-127">Would a normal .NET library meet your needs?</span></span>

- <span data-ttu-id="37784-128">La quantità modificherà lo schema?</span><span class="sxs-lookup"><span data-stu-id="37784-128">How much will your schema change?</span></span>

- <span data-ttu-id="37784-129">Verrà modificato durante la generazione di codice?</span><span class="sxs-lookup"><span data-stu-id="37784-129">Will it change during coding?</span></span>

- <span data-ttu-id="37784-130">Verrà modificato tra le sessioni di codifica?</span><span class="sxs-lookup"><span data-stu-id="37784-130">Will it change between coding sessions?</span></span>

- <span data-ttu-id="37784-131">Verrà modificato durante l'esecuzione del programma?</span><span class="sxs-lookup"><span data-stu-id="37784-131">Will it change during program execution?</span></span>

<span data-ttu-id="37784-132">Provider di tipi sono particolarmente adatti per situazioni in cui lo schema è stabile in fase di esecuzione e durante il ciclo di vita del codice compilato.</span><span class="sxs-lookup"><span data-stu-id="37784-132">Type providers are best suited to situations where the schema is stable at runtime and during the lifetime of compiled code.</span></span>


## <a name="a-simple-type-provider"></a><span data-ttu-id="37784-133">Un Provider di tipi semplici</span><span class="sxs-lookup"><span data-stu-id="37784-133">A Simple Type Provider</span></span>
<span data-ttu-id="37784-134">Questo esempio è Samples.HelloWorldTypeProvider nel `SampleProviders\Providers` directory del [pacchetto di esempio F # 3.0](http://fsharp3sample.codeplex.com) nel sito Web Codeplex.</span><span class="sxs-lookup"><span data-stu-id="37784-134">This sample is Samples.HelloWorldTypeProvider in the `SampleProviders\Providers` directory of the [F# 3.0 Sample Pack](http://fsharp3sample.codeplex.com) on the Codeplex website.</span></span> <span data-ttu-id="37784-135">Il provider rende disponibili un "spazio di tipo" che contiene i tipi cancellati 100, come illustrato nel codice seguente utilizzando la sintassi di firma F # e omettendo i dettagli per tutti tranne quelli `Type1`.</span><span class="sxs-lookup"><span data-stu-id="37784-135">The provider makes available a "type space" that contains 100 erased types, as the following code shows by using F# signature syntax and omitting the details for all except `Type1`.</span></span> <span data-ttu-id="37784-136">Per ulteriori informazioni sui tipi cancellati, vedere [dettagli sulle cancellati forniti tipi](#details-about-erased-provided-types) più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="37784-136">For more information about erased types, see [Details About Erased Provided Types](#details-about-erased-provided-types) later in this topic.</span></span>

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

    /// This is an instance property.
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

<span data-ttu-id="37784-137">Si noti che il set di tipi e membri forniti è noto in modo statico.</span><span class="sxs-lookup"><span data-stu-id="37784-137">Note that the set of types and members provided is statically known.</span></span> <span data-ttu-id="37784-138">In questo esempio non sfruttare la possibilità di provider per fornire tipi che dipendono da uno schema.</span><span class="sxs-lookup"><span data-stu-id="37784-138">This example doesn't leverage the ability of providers to provide types that depend on a schema.</span></span> <span data-ttu-id="37784-139">Il codice seguente viene descritto l'implementazione del provider di tipi e i dettagli sono descritti nelle sezioni successive di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="37784-139">The implementation of the type provider is outlined in the following code, and the details are covered in later sections of this topic.</span></span>


>[!WARNING] 
<span data-ttu-id="37784-140">Potrebbero essere presenti alcune piccole differenze di denominazione tra il codice e gli esempi online.</span><span class="sxs-lookup"><span data-stu-id="37784-140">There may be some small naming differences between this code and the online samples.</span></span>

```fsharp
namespace Samples.FSharp.HelloWorldTypeProvider

open System
open System.Reflection
open Samples.FSharp.ProvidedTypes
open Microsoft.FSharp.Core.CompilerServices
open Microsoft.FSharp.Quotations

// This type defines the type provider. When compiled to a DLL, it can be added
// as a reference to an F# command-line compilation, script, or project.
[<TypeProvider>]
type SampleTypeProvider(config: TypeProviderConfig) as this = 

  // Inheriting from this type provides implementations of ITypeProvider 
  // in terms of the provided types below.
  inherit TypeProviderForNamespaces()

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

<span data-ttu-id="37784-141">Per utilizzare questo provider, aprire un'istanza separata di Visual Studio 2012, creare uno script F # e quindi aggiungere un riferimento al provider dallo script utilizzando #r come illustrato nel codice seguente:</span><span class="sxs-lookup"><span data-stu-id="37784-141">To use this provider, open a separate instance of Visual Studio 2012, create an F# script, and then add a reference to the provider from your script by using #r as the following code shows:</span></span>

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

<span data-ttu-id="37784-142">Cercare i tipi di sotto di `Samples.HelloWorldTypeProvider` dello spazio dei nomi che ha generato il provider di tipi.</span><span class="sxs-lookup"><span data-stu-id="37784-142">Then look for the types under the `Samples.HelloWorldTypeProvider` namespace that the type provider generated.</span></span>

<span data-ttu-id="37784-143">Prima di ricompilare il provider, assicurarsi che siano state chiuse tutte le istanze di Visual Studio e F # Interactive che utilizzano la DLL del provider.</span><span class="sxs-lookup"><span data-stu-id="37784-143">Before you recompile the provider, make sure that you have closed all instances of Visual Studio and F# Interactive that are using the provider DLL.</span></span> <span data-ttu-id="37784-144">In caso contrario, verrà generato un errore di compilazione perché la DLL di output verranno bloccate.</span><span class="sxs-lookup"><span data-stu-id="37784-144">Otherwise, a build error will occur because the output DLL will be locked.</span></span>

<span data-ttu-id="37784-145">Per eseguire il debug di questo provider utilizzando istruzioni print, effettuare uno script che espone un problema con il provider e quindi usare il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="37784-145">To debug this provider by using print statements, make a script that exposes a problem with the provider, and then use the following code:</span></span>

```fsharp
fsc.exe -r:bin\Debug\HelloWorldTypeProvider.dll script.fsx
```

<span data-ttu-id="37784-146">Per eseguire il debug di questo provider tramite Visual Studio, aprire il prompt dei comandi di Visual Studio con credenziali amministrative ed eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="37784-146">To debug this provider by using Visual Studio, open the Visual Studio command prompt with administrative credentials, and run the following command:</span></span>

```fsharp
devenv.exe /debugexe fsc.exe -r:bin\Debug\HelloWorldTypeProvider.dll script.fsx
```

<span data-ttu-id="37784-147">In alternativa, aprire Visual Studio, aprire il menu Debug, scegli `Debug/Attach to process…`e associare a un altro `devenv` processo in cui si sta modificando lo script.</span><span class="sxs-lookup"><span data-stu-id="37784-147">As an alternative, open Visual Studio, open the Debug menu, choose `Debug/Attach to process…`, and attach to another `devenv` process where you’re editing your script.</span></span> <span data-ttu-id="37784-148">Tramite questo metodo, è possibile assegnare più facilmente particolare logica nel provider di tipi digitando in modo interattivo le espressioni nella seconda istanza (con e altre funzionalità di IntelliSense completo).</span><span class="sxs-lookup"><span data-stu-id="37784-148">By using this method, you can more easily target particular logic in the type provider by interactively typing expressions into the second instance (with full IntelliSense and other features).</span></span>

<span data-ttu-id="37784-149">È possibile disattivare Just My Code di debug per meglio identificare gli errori nel codice generato.</span><span class="sxs-lookup"><span data-stu-id="37784-149">You can disable Just My Code debugging to better identify errors in generated code.</span></span> <span data-ttu-id="37784-150">Per informazioni su come abilitare o disabilitare questa funzionalità, vedere [spostarsi nel codice con il Debugger](/visualstudio/debugger/navigating-through-code-with-the-debugger).</span><span class="sxs-lookup"><span data-stu-id="37784-150">For information about how to enable or disable this feature, see [Navigating through Code with the Debugger](/visualstudio/debugger/navigating-through-code-with-the-debugger).</span></span> <span data-ttu-id="37784-151">Inoltre, è inoltre possibile impostare le eccezioni first-chance intercettazione aprendo il `Debug` menu e scegliendo `Exceptions` oppure scegliendo i tasti Ctrl + Alt + E aprire il `Exceptions` la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="37784-151">Also, you can also set first-chance exception catching by opening the `Debug` menu and then choosing `Exceptions` or by choosing the Ctrl+Alt+E keys to open the `Exceptions` dialog box.</span></span> <span data-ttu-id="37784-152">Nella finestra di dialogo, in `Common Language Runtime Exceptions`, selezionare il `Thrown` casella di controllo.</span><span class="sxs-lookup"><span data-stu-id="37784-152">In that dialog box, under `Common Language Runtime Exceptions`, select the `Thrown` check box.</span></span>


### <a name="implementation-of-the-type-provider"></a><span data-ttu-id="37784-153">Implementazione del Provider di tipi</span><span class="sxs-lookup"><span data-stu-id="37784-153">Implementation of the Type Provider</span></span>
<span data-ttu-id="37784-154">In questa sezione illustra le sezioni principali dell'implementazione del provider di tipo.</span><span class="sxs-lookup"><span data-stu-id="37784-154">This section walks you through the principal sections of the type provider implementation.</span></span> <span data-ttu-id="37784-155">Innanzitutto, definire il tipo per il provider di tipi personalizzato se stesso:</span><span class="sxs-lookup"><span data-stu-id="37784-155">First, you define the type for the custom type provider itself:</span></span>

```fsharp
[<TypeProvider>]
type SampleTypeProvider(config: TypeProviderConfig) as this =
```

<span data-ttu-id="37784-156">Questo tipo deve essere pubblico e che è necessario contrassegnarlo con il [TypeProvider](https://msdn.microsoft.com/library/bdf7b036-7490-4ace-b79f-c5f1b1b37947) in modo che il compilatore riconosce il provider di tipi quando un progetto F # separato fa riferimento all'assembly che contiene il tipo di attributo.</span><span class="sxs-lookup"><span data-stu-id="37784-156">This type must be public, and you must mark it with the [TypeProvider](https://msdn.microsoft.com/library/bdf7b036-7490-4ace-b79f-c5f1b1b37947) attribute so that the compiler will recognize the type provider when a separate F# project references the assembly that contains the type.</span></span> <span data-ttu-id="37784-157">Il *config* parametro è facoltativo e, se presente, contiene informazioni di configurazione di scelta rapida per l'istanza del tipo di provider che crea il compilatore F #.</span><span class="sxs-lookup"><span data-stu-id="37784-157">The *config* parameter is optional, and, if present, contains contextual configuration information for the type provider instance that the F# compiler creates.</span></span>

<span data-ttu-id="37784-158">Viene implementato il [ITypeProvider](https://msdn.microsoft.com/library/2c2b0571-843d-4a7d-95d4-0a7510ed5e2f) interfaccia.</span><span class="sxs-lookup"><span data-stu-id="37784-158">Next, you implement the [ITypeProvider](https://msdn.microsoft.com/library/2c2b0571-843d-4a7d-95d4-0a7510ed5e2f) interface.</span></span> <span data-ttu-id="37784-159">In questo caso, utilizzare il `TypeProviderForNamespaces` digitare dal `ProvidedTypes` API come tipo di base.</span><span class="sxs-lookup"><span data-stu-id="37784-159">In this case, you use the `TypeProviderForNamespaces` type from the `ProvidedTypes` API as a base type.</span></span> <span data-ttu-id="37784-160">Questo tipo di supporto possa fornire una raccolta finita di rapidamente fornito spazi dei nomi, ognuno dei quali direttamente contiene un numero finito di fissa, fornito in blocco i tipi.</span><span class="sxs-lookup"><span data-stu-id="37784-160">This helper type can provide a finite collection of eagerly provided namespaces, each of which directly contains a finite number of fixed, eagerly provided types.</span></span> <span data-ttu-id="37784-161">In questo contesto, il provider *rapidamente* genera tipi, anche se non sono necessari o utilizzati.</span><span class="sxs-lookup"><span data-stu-id="37784-161">In this context, the provider *eagerly* generates types even if they aren't needed or used.</span></span>

```fsharp
inherit TypeProviderForNamespaces()
```

<span data-ttu-id="37784-162">Successivamente, definire i valori privati locali che specificano lo spazio dei nomi per i tipi forniti e trovare l'assembly di provider di tipo stesso.</span><span class="sxs-lookup"><span data-stu-id="37784-162">Next, define local private values that specify the namespace for the provided types, and find the type provider assembly itself.</span></span> <span data-ttu-id="37784-163">L'assembly è usato in un secondo momento come tipo di elemento padre logico dei tipi forniti cancellati.</span><span class="sxs-lookup"><span data-stu-id="37784-163">This assembly is used later as the logical parent type of the erased types that are provided.</span></span>

```fsharp
let namespaceName = "Samples.HelloWorldTypeProvider"
let thisAssembly = Assembly.GetExecutingAssembly()
```

<span data-ttu-id="37784-164">Successivamente, creare una funzione per specificare tutti i tipi Type1... Type100.</span><span class="sxs-lookup"><span data-stu-id="37784-164">Next, create a function to provide each of the types Type1…Type100.</span></span> <span data-ttu-id="37784-165">Questa funzione è illustrata in dettaglio più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="37784-165">This function is explained in more detail later in this topic.</span></span>

```fsharp
let makeOneProvidedType (n:int) = …
```

<span data-ttu-id="37784-166">Successivamente, generare i tipi forniti 100:</span><span class="sxs-lookup"><span data-stu-id="37784-166">Next, generate the 100 provided types:</span></span>

```fsharp
let types = [ for i in 1 .. 100 -> makeOneProvidedType i ]
```

<span data-ttu-id="37784-167">Successivamente, aggiungere i tipi come uno spazio dei nomi specificato:</span><span class="sxs-lookup"><span data-stu-id="37784-167">Next, add the types as a provided namespace:</span></span>

```fsharp
do this.AddNamespace(namespaceName, types)
```

<span data-ttu-id="37784-168">Infine, aggiungere un attributo di assembly che indica che si sta creando un provider di tipi DLL:</span><span class="sxs-lookup"><span data-stu-id="37784-168">Finally, add an assembly attribute that indicates that you are creating a type provider DLL:</span></span>

```fsharp
[<assembly:TypeProviderAssembly>] 
do()
```

### <a name="providing-one-type-and-its-members"></a><span data-ttu-id="37784-169">Fornisce un tipo e i relativi membri</span><span class="sxs-lookup"><span data-stu-id="37784-169">Providing One Type And Its Members</span></span>
<span data-ttu-id="37784-170">Il `makeOneProvidedType` funzione esegue il lavoro effettivo di fornire uno dei tipi.</span><span class="sxs-lookup"><span data-stu-id="37784-170">The `makeOneProvidedType` function does the real work of providing one of the types.</span></span>

```fsharp
let makeOneProvidedType (n:int) = 
…
```

<span data-ttu-id="37784-171">Questo passaggio spiega l'implementazione di questa funzione.</span><span class="sxs-lookup"><span data-stu-id="37784-171">This step explains the implementation of this function.</span></span> <span data-ttu-id="37784-172">Creare innanzitutto il tipo specificato (ad esempio, Type1, quando n = 1 o Type57, quando n = 57).</span><span class="sxs-lookup"><span data-stu-id="37784-172">First, create the provided type (for example, Type1, when n = 1, or Type57, when n = 57).</span></span>

```fsharp
// This is the provided type. It is an erased provided type and, in compiled code, 
// will appear as type 'obj'.
let t = ProvidedTypeDefinition(thisAssembly,namespaceName,
"Type" + string n,
baseType = Some typeof<obj>)
```

<span data-ttu-id="37784-173">Si noti quanto segue:</span><span class="sxs-lookup"><span data-stu-id="37784-173">You should note the following points:</span></span>


- <span data-ttu-id="37784-174">Questo fornito di tipo verrà cancellato.</span><span class="sxs-lookup"><span data-stu-id="37784-174">This provided type is erased.</span></span>  <span data-ttu-id="37784-175">Poiché si indica che il tipo di base è `obj`, le istanze verranno visualizzati come valori di tipo [obj](https://msdn.microsoft.com/library/dcf2430f-702b-40e5-a0a1-97518bf137f7) nel codice compilato.</span><span class="sxs-lookup"><span data-stu-id="37784-175">Because you indicate that the base type is `obj`, instances will appear as values of type [obj](https://msdn.microsoft.com/library/dcf2430f-702b-40e5-a0a1-97518bf137f7) in compiled code.</span></span>
<br />

- <span data-ttu-id="37784-176">Quando si specifica un tipo non annidato, è necessario specificare l'assembly e dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="37784-176">When you specify a non-nested type, you must specify the assembly and namespace.</span></span> <span data-ttu-id="37784-177">Per i tipi cancellati, l'assembly deve essere l'assembly di provider di tipo stesso.</span><span class="sxs-lookup"><span data-stu-id="37784-177">For erased types, the assembly should be the type provider assembly itself.</span></span>
<br />

<span data-ttu-id="37784-178">Successivamente, aggiungere la documentazione XML per il tipo.</span><span class="sxs-lookup"><span data-stu-id="37784-178">Next, add XML documentation to the type.</span></span> <span data-ttu-id="37784-179">Questa documentazione viene ritardata, vale a dire, calcolata su richiesta, se ne ha bisogno il compilatore host.</span><span class="sxs-lookup"><span data-stu-id="37784-179">This documentation is delayed, that is, computed on-demand if the host compiler needs it.</span></span>

```fsharp
t.AddXmlDocDelayed (fun () -> sprintf "This provided type %s" ("Type" + string n))
```

<span data-ttu-id="37784-180">Aggiungere una proprietà statica fornita per il tipo:</span><span class="sxs-lookup"><span data-stu-id="37784-180">Next you add a provided static property to the type:</span></span>

```fsharp
let staticProp = ProvidedProperty(propertyName = "StaticProperty", 
propertyType = typeof<string>, 
IsStatic=true,
GetterCode= (fun args -> <@@ "Hello!" @@>))
```

<span data-ttu-id="37784-181">Impostazione di questa proprietà restituirà sempre la stringa "Hello!".</span><span class="sxs-lookup"><span data-stu-id="37784-181">Getting this property will always evaluate to the string "Hello!".</span></span> <span data-ttu-id="37784-182">Il `GetterCode` per la proprietà viene impostata un'offerta F #, che rappresenta il codice che genera il compilatore host per il recupero della proprietà.</span><span class="sxs-lookup"><span data-stu-id="37784-182">The `GetterCode` for the property uses an F# quotation, which represents the code that the host compiler generates for getting the property.</span></span> <span data-ttu-id="37784-183">Per ulteriori informazioni sulle offerte, vedere [citazioni di codice (F #)](https://msdn.microsoft.com/library/6f055397-a1f0-4f9a-927c-f0d7c6951155).</span><span class="sxs-lookup"><span data-stu-id="37784-183">For more information about quotations, see [Code Quotations (F#)](https://msdn.microsoft.com/library/6f055397-a1f0-4f9a-927c-f0d7c6951155).</span></span>

<span data-ttu-id="37784-184">Aggiungere la documentazione XML per la proprietà.</span><span class="sxs-lookup"><span data-stu-id="37784-184">Add XML documentation to the property.</span></span>

```fsharp
staticProp.AddXmlDocDelayed(fun () -> "This is a static property")
```

<span data-ttu-id="37784-185">Ora è possibile associare la proprietà fornita per il tipo specificato.</span><span class="sxs-lookup"><span data-stu-id="37784-185">Now attach the provided property to the provided type.</span></span> <span data-ttu-id="37784-186">È necessario collegare un membro specificato in un solo tipo.</span><span class="sxs-lookup"><span data-stu-id="37784-186">You must attach a provided member to one and only one type.</span></span> <span data-ttu-id="37784-187">In caso contrario, il membro non è accessibile.</span><span class="sxs-lookup"><span data-stu-id="37784-187">Otherwise, the member will never be accessible.</span></span>

```fsharp
t.AddMember staticProp
```

<span data-ttu-id="37784-188">Creare ora un costruttore specificato che non accetta parametri.</span><span class="sxs-lookup"><span data-stu-id="37784-188">Now create a provided constructor that takes no parameters.</span></span>

```fsharp
let ctor = ProvidedConstructor(parameters = [ ], 
InvokeCode= (fun args -> <@@ "The object data" :> obj @@>))
```

<span data-ttu-id="37784-189">Il `InvokeCode` per il costruttore restituisce un'offerta F #, che rappresenta il codice che il compilatore host genera quando viene chiamato il costruttore.</span><span class="sxs-lookup"><span data-stu-id="37784-189">The `InvokeCode` for the constructor returns an F# quotation, which represents the code that the host compiler generates when the constructor is called.</span></span> <span data-ttu-id="37784-190">Ad esempio, è possibile utilizzare il costruttore seguente:</span><span class="sxs-lookup"><span data-stu-id="37784-190">For example, you can use the following constructor:</span></span>

```fsharp
new Type10()
```

<span data-ttu-id="37784-191">Verrà creata un'istanza del tipo fornito con i dati sottostanti "I dati dell'oggetto".</span><span class="sxs-lookup"><span data-stu-id="37784-191">An instance of the provided type will be created with underlying data "The object data".</span></span> <span data-ttu-id="37784-192">Il codice tra virgolette include una conversione [obj](https://msdn.microsoft.com/library/dcf2430f-702b-40e5-a0a1-97518bf137f7) perché tale tipo è la cancellazione di purché questo tipo (come specificato quando è stato dichiarato il tipo specificato).</span><span class="sxs-lookup"><span data-stu-id="37784-192">The quoted code includes a conversion to [obj](https://msdn.microsoft.com/library/dcf2430f-702b-40e5-a0a1-97518bf137f7) because that type is the erasure of this provided type (as you specified when you declared the provided type).</span></span>

<span data-ttu-id="37784-193">Aggiungere la documentazione XML per il costruttore e aggiungere il costruttore fornito per il tipo specificato:</span><span class="sxs-lookup"><span data-stu-id="37784-193">Add XML documentation to the constructor, and add the provided constructor to the provided type:</span></span>

```fsharp
ctor.AddXmlDocDelayed(fun () -> "This is a constructor")

t.AddMember ctor
```

<span data-ttu-id="37784-194">Creare un secondo costruttore specificato che accetta un parametro:</span><span class="sxs-lookup"><span data-stu-id="37784-194">Create a second provided constructor that takes one parameter:</span></span>

```fsharp
let ctor2 = 
ProvidedConstructor(parameters = [ ProvidedParameter("data",typeof<string>) ], 
InvokeCode= (fun args -> <@@ (%%(args.[0]) : string) :> obj @@>))
```

<span data-ttu-id="37784-195">Il `InvokeCode` per il costruttore restituisce nuovamente un'offerta F #, che rappresenta il codice che il compilatore host generato per una chiamata al metodo.</span><span class="sxs-lookup"><span data-stu-id="37784-195">The `InvokeCode` for the constructor again returns an F# quotation, which represents the code that the host compiler generated for a call to the method.</span></span> <span data-ttu-id="37784-196">Ad esempio, è possibile utilizzare il costruttore seguente:</span><span class="sxs-lookup"><span data-stu-id="37784-196">For example, you can use the following constructor:</span></span>

```fsharp
new Type10("ten")
```

<span data-ttu-id="37784-197">Viene creata un'istanza del tipo fornito con i dati sottostanti "10".</span><span class="sxs-lookup"><span data-stu-id="37784-197">An instance of the provided type is created with underlying data "ten".</span></span> <span data-ttu-id="37784-198">Si è già notato che il `InvokeCode` funzione restituisce una citazione.</span><span class="sxs-lookup"><span data-stu-id="37784-198">You may have already noticed that the `InvokeCode` function returns a quotation.</span></span> <span data-ttu-id="37784-199">L'input a questa funzione è un elenco di espressioni, uno per ogni parametro di costruttore.</span><span class="sxs-lookup"><span data-stu-id="37784-199">The input to this function is a list of expressions, one per constructor parameter.</span></span> <span data-ttu-id="37784-200">In questo caso, un'espressione che rappresenta il valore del parametro singolo è disponibile in `args.[0]`.</span><span class="sxs-lookup"><span data-stu-id="37784-200">In this case, an expression that represents the single parameter value is available in `args.[0]`.</span></span> <span data-ttu-id="37784-201">Il codice per una chiamata al costruttore assegna il valore restituito nel tipo cancellato `obj`.</span><span class="sxs-lookup"><span data-stu-id="37784-201">The code for a call to the constructor coerces the return value to the erased type `obj`.</span></span> <span data-ttu-id="37784-202">Dopo aver aggiunto il secondo costruttore fornito per il tipo, si crea una proprietà di istanza specificato:</span><span class="sxs-lookup"><span data-stu-id="37784-202">After you add the second provided constructor to the type, you create a provided instance property:</span></span>

```fsharp
let instanceProp = 
ProvidedProperty(propertyName = "InstanceProperty", 
propertyType = typeof<int>, 
GetterCode= (fun args -> 
<@@ ((%%(args.[0]) : obj) :?> string).Length @@>))
instanceProp.AddXmlDocDelayed(fun () -> "This is an instance property")
t.AddMember instanceProp
```

<span data-ttu-id="37784-203">Se questa proprietà, verrà restituito la lunghezza della stringa, che corrisponde all'oggetto di rappresentazione.</span><span class="sxs-lookup"><span data-stu-id="37784-203">Getting this property will return the length of the string, which is the representation object.</span></span> <span data-ttu-id="37784-204">Il `GetterCode` restituirà un'offerta di F # che specifica il codice che genera il compilatore host per ottenere la proprietà.</span><span class="sxs-lookup"><span data-stu-id="37784-204">The `GetterCode` property returns an F# quotation that specifies the code that the host compiler generates to get the property.</span></span> <span data-ttu-id="37784-205">Ad esempio `InvokeCode`, `GetterCode` funzione restituisce una citazione.</span><span class="sxs-lookup"><span data-stu-id="37784-205">Like `InvokeCode`, the `GetterCode` function returns a quotation.</span></span> <span data-ttu-id="37784-206">Il compilatore host chiama questa funzione con un elenco di argomenti.</span><span class="sxs-lookup"><span data-stu-id="37784-206">The host compiler calls this function with a list of arguments.</span></span> <span data-ttu-id="37784-207">In questo caso, gli argomenti includono solo la singola espressione che rappresenta l'istanza sulla quale viene chiamato il metodo Get, che è possibile accedere tramite `args.[0]`. L'implementazione di `GetterCode` quindi sottopone a splicing in quotation il risultato nel tipo cancellato `obj`, e un cast viene utilizzato per soddisfare il meccanismo del compilatore per il controllo dei tipi che l'oggetto è una stringa.</span><span class="sxs-lookup"><span data-stu-id="37784-207">In this case, the arguments include just the single expression that represents the instance upon which the getter is being called, which you can access by using `args.[0]`.The implementation of `GetterCode` then splices into the result quotation at the erased type `obj`, and a cast is used to satisfy the compiler's mechanism for checking types that the object is a string.</span></span> <span data-ttu-id="37784-208">La parte successiva del `makeOneProvidedType` fornisce un metodo di istanza con un parametro.</span><span class="sxs-lookup"><span data-stu-id="37784-208">The next part of `makeOneProvidedType` provides an instance method with one parameter.</span></span>

```fsharp
let instanceMeth = 
ProvidedMethod(methodName = "InstanceMethod", 
parameters = [ProvidedParameter("x",typeof<int>)], 
returnType = typeof<char>, 
InvokeCode = (fun args -> 
<@@ ((%%(args.[0]) : obj) :?> string).Chars(%%(args.[1]) : int) @@>))

instanceMeth.AddXmlDocDelayed(fun () -> "This is an instance method")
// Add the instance method to the type.
t.AddMember instanceMeth
```

<span data-ttu-id="37784-209">Infine, creare un tipo annidato che contiene 100 proprietà annidate.</span><span class="sxs-lookup"><span data-stu-id="37784-209">Finally, create a nested type that contains 100 nested properties.</span></span> <span data-ttu-id="37784-210">La creazione di questo annidati di tipo e le relative proprietà viene ritardata, vale a dire, calcolata su richiesta.</span><span class="sxs-lookup"><span data-stu-id="37784-210">The creation of this nested type and its properties is delayed, that is, computed on-demand.</span></span>

```fsharp
t.AddMembersDelayed(fun () -> 
let nestedType = ProvidedTypeDefinition("NestedType",
Some typeof<obj>

)

nestedType.AddMembersDelayed (fun () -> 
let staticPropsInNestedType = 
[ for i in 1 .. 100 do
let valueOfTheProperty = "I am string "  + string i

let p = ProvidedProperty(propertyName = "StaticProperty" + string i, 
propertyType = typeof<string>, 
IsStatic=true,
GetterCode= (fun args -> <@@ valueOfTheProperty @@>))

p.AddXmlDocDelayed(fun () -> 
sprintf "This is StaticProperty%d on NestedType" i)

yield p ]
staticPropsInNestedType)

[nestedType])

// The result of makeOneProvidedType is the type.
t
```

### <a name="details-about-erased-provided-types"></a><span data-ttu-id="37784-211">Dettagli sui tipi forniti cancellati</span><span class="sxs-lookup"><span data-stu-id="37784-211">Details about Erased Provided Types</span></span>
<span data-ttu-id="37784-212">Nell'esempio riportato in questa sezione vengono fornite solo *tipi forniti cancellati*, che sono particolarmente utili nelle situazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="37784-212">The example in this section provides only *erased provided types*, which are particularly useful in the following situations:</span></span>


- <span data-ttu-id="37784-213">Quando si scrive un provider per uno spazio di informazioni che contiene solo i dati e i metodi.</span><span class="sxs-lookup"><span data-stu-id="37784-213">When you are writing a provider for an information space that contains only data and methods.</span></span>
<br />

- <span data-ttu-id="37784-214">Quando si scrive un provider in cui la semantica precisa del tipo di runtime non è critica per l'utilizzo pratico dello spazio di informazioni.</span><span class="sxs-lookup"><span data-stu-id="37784-214">When you are writing a provider where accurate runtime-type semantics aren't critical for practical use of the information space.</span></span>
<br />

- <span data-ttu-id="37784-215">Quando si scrive un provider per uno spazio di informazioni che è così grande e interconnessi che non è tecnicamente possibile generare tipi .NET reali per lo spazio di informazioni.</span><span class="sxs-lookup"><span data-stu-id="37784-215">When you are writing a provider for an information space that is so large and interconnected that it isn’t technically feasible to generate real .NET types for the information space.</span></span>
<br />

<span data-ttu-id="37784-216">In questo esempio, ogni fornito di tipo verrà cancellato al tipo `obj`, e tutte le occorrenze del tipo verranno visualizzato come tipo `obj` nel codice compilato.</span><span class="sxs-lookup"><span data-stu-id="37784-216">In this example, each provided type is erased to type `obj`, and all uses of the type will appear as type `obj` in compiled code.</span></span> <span data-ttu-id="37784-217">In realtà, gli oggetti sottostanti in questi esempi sono stringhe, ma il tipo verrà visualizzato come `System.Object` in .NET codice compilato.</span><span class="sxs-lookup"><span data-stu-id="37784-217">In fact, the underlying objects in these examples are strings, but the type will appear as `System.Object` in .NET compiled code.</span></span> <span data-ttu-id="37784-218">Come con tutte le occorrenze di cancellazione di tipo, è possibile usare boxing esplicito, unboxing e il cast a possa compromettere cancellati tipi.</span><span class="sxs-lookup"><span data-stu-id="37784-218">As with all uses of type erasure, you can use explicit boxing, unboxing, and casting to subvert erased types.</span></span> <span data-ttu-id="37784-219">In questo caso, un'eccezione di cast non valida potrebbe quando viene utilizzato l'oggetto.</span><span class="sxs-lookup"><span data-stu-id="37784-219">In this case, a cast exception that isn’t valid may result when the object is used.</span></span> <span data-ttu-id="37784-220">Un provider runtime è possibile definire un proprio tipo di rappresentazione privata per proteggersi da rappresentazioni false.</span><span class="sxs-lookup"><span data-stu-id="37784-220">A provider runtime can define its own private representation type to help protect against false representations.</span></span> <span data-ttu-id="37784-221">È possibile definire tipi cancellati in F # stesso.</span><span class="sxs-lookup"><span data-stu-id="37784-221">You can’t define erased types in F# itself.</span></span> <span data-ttu-id="37784-222">Solo i tipi forniti possono essere cancellati.</span><span class="sxs-lookup"><span data-stu-id="37784-222">Only provided types may be erased.</span></span> <span data-ttu-id="37784-223">È necessario comprendere le implicazioni, entrambi pratici e cancellati semantica, di utilizzare tipi cancellati per il provider di tipo o un provider che fornisce tipi.</span><span class="sxs-lookup"><span data-stu-id="37784-223">You must understand the ramifications, both practical and semantic, of using either erased types for your type provider or a provider that provides erased types.</span></span> <span data-ttu-id="37784-224">Un tipo cancellato non dispone di alcun tipo .NET reale.</span><span class="sxs-lookup"><span data-stu-id="37784-224">An erased type has no real .NET type.</span></span> <span data-ttu-id="37784-225">Pertanto, non è possibile eseguire sul tipo di immagine accurata e si potrebbero compromettere tipi cancellati se si utilizza il cast di runtime e di altre tecniche che si basano sulla semantica di tipo esatto di runtime.</span><span class="sxs-lookup"><span data-stu-id="37784-225">Therefore, you cannot do accurate reflection over the type, and you might subvert erased types if you use runtime casts and other techniques that rely on exact runtime type semantics.</span></span> <span data-ttu-id="37784-226">Subversion dei tipi cancellati spesso comporta eccezioni di cast di tipo in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="37784-226">Subversion of erased types frequently results in type cast exceptions at runtime.</span></span>


### <a name="choosing-representations-for-erased-provided-types"></a><span data-ttu-id="37784-227">Scelta di rappresentazioni per cancellati forniti tipi</span><span class="sxs-lookup"><span data-stu-id="37784-227">Choosing Representations for Erased Provided Types</span></span>
<span data-ttu-id="37784-228">Per alcuni utilizzi dei tipi forniti cancellati, alcuna rappresentazione non è necessaria.</span><span class="sxs-lookup"><span data-stu-id="37784-228">For some uses of erased provided types, no representation is required.</span></span> <span data-ttu-id="37784-229">Ad esempio, è il cancellato fornita tipo potrebbe contenere solo le proprietà statiche e membri e non sono costruttori e metodi o alle proprietà non restituisce un'istanza del tipo.</span><span class="sxs-lookup"><span data-stu-id="37784-229">For example, the erased provided type might contain only static properties and members and no constructors, and no methods or properties would return an instance of the type.</span></span> <span data-ttu-id="37784-230">Se è possibile raggiungere le istanze di un elemento cancellato tipo fornito, è necessario considerare le domande seguenti:</span><span class="sxs-lookup"><span data-stu-id="37784-230">If you can reach instances of an erased provided type, you must consider the following questions:</span></span>


- <span data-ttu-id="37784-231">Che cos'è la cancellazione di un tipo fornito?</span><span class="sxs-lookup"><span data-stu-id="37784-231">What is the erasure of a provided type?</span></span>
<br />
  - <span data-ttu-id="37784-232">La cancellazione di un tipo fornito è come il tipo viene visualizzato nel codice .NET compilato.</span><span class="sxs-lookup"><span data-stu-id="37784-232">The erasure of a provided type is how the type appears in compiled .NET code.</span></span>
<br />

  - <span data-ttu-id="37784-233">La cancellazione di un tipo di classe cancellato fornita è sempre il primo non cancellati tipo di base nella catena di ereditarietà del tipo.</span><span class="sxs-lookup"><span data-stu-id="37784-233">The erasure of a provided erased class type is always the first non-erased base type in the inheritance chain of the type.</span></span>
<br />

  - <span data-ttu-id="37784-234">La cancellazione di un tipo di interfaccia cancellato fornita è sempre `System.Object`.</span><span class="sxs-lookup"><span data-stu-id="37784-234">The erasure of a provided erased interface type is always `System.Object`.</span></span>
<br />

- <span data-ttu-id="37784-235">Quali sono le rappresentazioni di un tipo fornito?</span><span class="sxs-lookup"><span data-stu-id="37784-235">What are the representations of a provided type?</span></span>
<br />
  - <span data-ttu-id="37784-236">Il set di oggetti per un tipo fornito cancellato vengono chiamati relative rappresentazioni.</span><span class="sxs-lookup"><span data-stu-id="37784-236">The set of possible objects for an erased provided type are called its representations.</span></span> <span data-ttu-id="37784-237">Nell'esempio in questo documento, le rappresentazioni di tutti di cancellato fornito tipi `Type1..Type100` sono sempre oggetti stringa.</span><span class="sxs-lookup"><span data-stu-id="37784-237">In the example in this document, the representations of all the erased provided types `Type1..Type100` are always string objects.</span></span>
<br />

<span data-ttu-id="37784-238">Tutte le rappresentazioni di un tipo fornito devono essere compatibile con la cancellazione del tipo fornito.</span><span class="sxs-lookup"><span data-stu-id="37784-238">All representations of a provided type must be compatible with the erasure of the provided type.</span></span> <span data-ttu-id="37784-239">(In caso contrario, il compilatore F # genererà un errore per un utilizzo del provider di tipi, o verrà generato il codice .NET non verificabile non è valido.</span><span class="sxs-lookup"><span data-stu-id="37784-239">(Otherwise, either the F# compiler will give an error for a use of the type provider, or unverifiable .NET code that isn't valid will be generated.</span></span> <span data-ttu-id="37784-240">Un provider di tipi non è valido se restituisce un codice che fornisce una rappresentazione non valida.</span><span class="sxs-lookup"><span data-stu-id="37784-240">A type provider isn’t valid if it returns code that gives a  representation that isn't valid.)</span></span>

<span data-ttu-id="37784-241">È possibile scegliere una rappresentazione per gli oggetti forniti utilizzando uno degli approcci seguenti, che sono molto comuni:</span><span class="sxs-lookup"><span data-stu-id="37784-241">You can choose a representation for provided objects by using either of the following approaches, both of which are very common:</span></span>


- <span data-ttu-id="37784-242">Se si fornisce un wrapper fortemente tipizzato semplicemente su un tipo .NET esistente, è spesso consigliabile per il tipo cancellare a quel tipo, utilizzare le istanze di tale tipo come rappresentazioni o entrambi.</span><span class="sxs-lookup"><span data-stu-id="37784-242">If you're simply providing a strongly typed wrapper over an existing .NET type, it often makes sense for your type to erase to that type, use instances of that type as representations, or both.</span></span> <span data-ttu-id="37784-243">Questo approccio è appropriato quando la maggior parte dei metodi su tale tipo comunque essere utile quando si utilizza la versione fortemente tipizzata.</span><span class="sxs-lookup"><span data-stu-id="37784-243">This approach is appropriate when most of the existing methods on that type still make sense when using the strongly typed version.</span></span>
<br />

- <span data-ttu-id="37784-244">Se si desidera creare un'API che differisce notevolmente da qualsiasi API .NET esistente, è consigliabile creare tipi di runtime che saranno la cancellazione di tipo e rappresentazioni per i tipi forniti.</span><span class="sxs-lookup"><span data-stu-id="37784-244">If you want to create an API that differs significantly from any existing .NET API, it makes sense to create runtime types that will be the type erasure and representations for the provided types.</span></span>
<br />

<span data-ttu-id="37784-245">Nell'esempio riportato in questo documento utilizza stringhe come rappresentazioni di oggetti specificati.</span><span class="sxs-lookup"><span data-stu-id="37784-245">The example in this document uses strings as representations of provided objects.</span></span> <span data-ttu-id="37784-246">Spesso, potrebbe essere opportuno utilizzare altri oggetti per le rappresentazioni.</span><span class="sxs-lookup"><span data-stu-id="37784-246">Frequently, it may be appropriate to use other objects for representations.</span></span> <span data-ttu-id="37784-247">Ad esempio, è possibile utilizzare un dizionario come un contenitore di proprietà:</span><span class="sxs-lookup"><span data-stu-id="37784-247">For example, you may use a dictionary as a property bag:</span></span>

```fsharp
ProvidedConstructor(parameters = [], 
InvokeCode= (fun args -> <@@ (new Dictionary<string,obj>()) :> obj @@>))
```

<span data-ttu-id="37784-248">In alternativa, è possibile definire un tipo in un provider di tipo che verrà utilizzato in fase di esecuzione per formare la rappresentazione, insieme a uno o più operazioni di runtime:</span><span class="sxs-lookup"><span data-stu-id="37784-248">As an alternative, you may define a type in your type provider that will be used at runtime to form the representation, along with one or more runtime operations:</span></span>

```fsharp
type DataObject() =
let data = Dictionary<string,obj>()
member x.RuntimeOperation() = data.Count
```

<span data-ttu-id="37784-249">I membri forniti quindi possono costruire istanze di questo tipo di oggetto:</span><span class="sxs-lookup"><span data-stu-id="37784-249">Provided members can then construct instances of this object type:</span></span>

```fsharp
ProvidedConstructor(parameters = [], 
InvokeCode= (fun args -> <@@ (new DataObject()) :> obj @@>))
```

<span data-ttu-id="37784-250">In questo caso, è possibile (facoltativamente) utilizzare questo tipo come la cancellazione di tipo specificando questo tipo come il `baseType` durante la costruzione di `ProvidedTypeDefinition`:</span><span class="sxs-lookup"><span data-stu-id="37784-250">In this case, you may (optionally) use this type as the type erasure by specifying this type as the `baseType` when constructing the `ProvidedTypeDefinition`:</span></span>

```fsharp
ProvidedTypeDefinition(…, baseType = Some typeof<DataObject> )
…
ProvidedConstructor(…, InvokeCode = (fun args -> <@@ new DataObject() @@>), …)
```

`Key Lessons`

<span data-ttu-id="37784-251">La precedente sezione viene spiegato come creare un provider di tipo cancellazione semplice che fornisce una gamma di tipi, proprietà e metodi.</span><span class="sxs-lookup"><span data-stu-id="37784-251">The previous section explained how to create a simple erasing type provider that provides a range of types, properties, and methods.</span></span> <span data-ttu-id="37784-252">In questa sezione viene anche illustrato il concetto di cancellazione di tipo, inclusi alcuni dei vantaggi e svantaggi fornisce tipi cancellati da un provider di tipi e illustrati rappresentazioni dei tipi cancellati.</span><span class="sxs-lookup"><span data-stu-id="37784-252">This section also explained the concept of type erasure, including some of the advantages and disadvantages of providing erased types from a type provider, and discussed representations of erased types.</span></span>


## <a name="a-type-provider-that-uses-static-parameters"></a><span data-ttu-id="37784-253">Un Provider di tipi che utilizza parametri statici</span><span class="sxs-lookup"><span data-stu-id="37784-253">A Type Provider That Uses Static Parameters</span></span>
<span data-ttu-id="37784-254">La possibilità di parametrizzare i provider di tipi da dati statici consente molti scenari interessanti, anche nei casi in cui il provider non è necessario accedere ai dati locali o remoti.</span><span class="sxs-lookup"><span data-stu-id="37784-254">The ability to parameterize type providers by static data enables many interesting scenarios, even in cases when the provider doesn't need to access any local or remote data.</span></span> <span data-ttu-id="37784-255">In questa sezione si apprenderà alcune tecniche di base per la creazione di un provider di questo tipo.</span><span class="sxs-lookup"><span data-stu-id="37784-255">In this section, you’ll learn some basic techniques for putting together such a provider.</span></span>


### <a name="type-checked-regex-provider"></a><span data-ttu-id="37784-256">Tipo controllato Regex Provider</span><span class="sxs-lookup"><span data-stu-id="37784-256">Type Checked Regex Provider</span></span>
<span data-ttu-id="37784-257">Si supponga che si desidera implementare un provider di tipi per le espressioni regolari che esegue il wrapping di .NET `System.Text.RegularExpressions.Regex` librerie in un'interfaccia che fornisce le seguenti garanzie in fase di compilazione:</span><span class="sxs-lookup"><span data-stu-id="37784-257">Imagine that you want to implement a type provider for regular expressions that wraps the .NET `System.Text.RegularExpressions.Regex` libraries in an interface that provides the following compile-time guarantees:</span></span>


- <span data-ttu-id="37784-258">Verifica se un'espressione regolare è valida.</span><span class="sxs-lookup"><span data-stu-id="37784-258">Verifying whether a regular expression is valid.</span></span>
<br />

- <span data-ttu-id="37784-259">Fornisce proprietà denominate su corrispondenze che si basano su qualsiasi gruppo di nomi nell'espressione regolare.</span><span class="sxs-lookup"><span data-stu-id="37784-259">Providing named properties on matches that are based on any group names in the regular expression.</span></span>
<br />

<span data-ttu-id="37784-260">In questa sezione viene illustrato come utilizzare i provider di tipi per creare un `RegExProviderType` digitare che il criterio di espressione regolare Parametrizza per fornire tali vantaggi.</span><span class="sxs-lookup"><span data-stu-id="37784-260">This section shows you how to use type providers to create a `RegExProviderType` type that the regular expression pattern parameterizes to provide these benefits.</span></span> <span data-ttu-id="37784-261">Il compilatore segnalerà un errore se il modello fornito non è valido e il provider di tipi può estrarre i gruppi dal modello in modo che è possibile accedervi tramite denominato proprietà corrispondenze.</span><span class="sxs-lookup"><span data-stu-id="37784-261">The compiler will report an error if the supplied pattern isn't valid, and the type provider can extract the groups from the pattern so that you can access them by using named properties on matches.</span></span> <span data-ttu-id="37784-262">Quando si progetta un provider di tipi, è necessario considerare l'aspetto relativo API esposta per gli utenti finali e come questa progettazione convertirà al codice .NET.</span><span class="sxs-lookup"><span data-stu-id="37784-262">When you design a type provider, you should consider how its exposed API should look to end users and how this design will translate to .NET code.</span></span> <span data-ttu-id="37784-263">Nell'esempio seguente viene illustrato come utilizzare questo tipo un'API per ottenere i componenti dell'indicativo di località:</span><span class="sxs-lookup"><span data-stu-id="37784-263">The following example shows how to use such an API to get the components of the area code:</span></span>

```fsharp
type T = RegexTyped< @"(?<AreaCode>^\d{3})-(?<PhoneNumber>\d{3}-\d{4}$)">
let reg = T()
let result = T.IsMatch("425-555-2345")
let r = reg.Match("425-555-2345").Group_AreaCode.Value //r equals "425"
```

<span data-ttu-id="37784-264">Nell'esempio seguente viene illustrato come il provider di tipi converte queste chiamate:</span><span class="sxs-lookup"><span data-stu-id="37784-264">The following example shows how the type provider translates these calls:</span></span>

```fsharp
let reg = new Regex(@"(?<AreaCode>^\d{3})-(?<PhoneNumber>\d{3}-\d{4}$)")
let result = reg.IsMatch("425-123-2345")
let r = reg.Match("425-123-2345").Groups.["AreaCode"].Value //r equals "425"
```

<span data-ttu-id="37784-265">Si noti quanto segue:</span><span class="sxs-lookup"><span data-stu-id="37784-265">Note the following points:</span></span>


- <span data-ttu-id="37784-266">Il tipo di espressione regolare standard rappresenta i parametri `RegexTyped` tipo.</span><span class="sxs-lookup"><span data-stu-id="37784-266">The standard Regex type represents the parameterized `RegexTyped` type.</span></span>
<br />

- <span data-ttu-id="37784-267">Il `RegexTyped` costruttore produce una chiamata al costruttore Regex, passando l'argomento di tipo statico per il modello.</span><span class="sxs-lookup"><span data-stu-id="37784-267">The `RegexTyped` constructor results in a call to the Regex constructor, passing in the static type argument for the pattern.</span></span>
<br />

- <span data-ttu-id="37784-268">Il risultato di `Match` metodo sono rappresentati dallo standard `System.Text.RegularExpressions.Match` tipo.</span><span class="sxs-lookup"><span data-stu-id="37784-268">The results of the `Match` method are represented by the standard `System.Text.RegularExpressions.Match` type.</span></span>
<br />

- <span data-ttu-id="37784-269">Risultati di ogni gruppo denominato in una proprietà specificata e l'accesso alla proprietà comporta un utilizzo di un indicizzatore in caso di corrispondenza `Groups` insieme.</span><span class="sxs-lookup"><span data-stu-id="37784-269">Each named group results in a provided property, and accessing the property results in a use of an indexer on a match’s `Groups` collection.</span></span>
<br />

<span data-ttu-id="37784-270">Il codice seguente rappresenta il nucleo della logica di implementare un provider di questo tipo, e in questo esempio vengono omessi l'aggiunta di tutti i membri per il tipo specificato.</span><span class="sxs-lookup"><span data-stu-id="37784-270">The following code is the core of the logic to implement such a provider, and this example omits the addition of all members to the provided type.</span></span> <span data-ttu-id="37784-271">Per informazioni su ogni membro aggiunto, vedere la sezione appropriata più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="37784-271">For information about each added member, see the appropriate section later in this topic.</span></span> <span data-ttu-id="37784-272">Per il codice completo, scaricare l'esempio dal [pacchetto di esempio F # 3.0](http://fsharp3sample.codeplex.com) nel sito Web Codeplex.</span><span class="sxs-lookup"><span data-stu-id="37784-272">For the full code, download the sample from the [F# 3.0 Sample Pack](http://fsharp3sample.codeplex.com) on the Codeplex website.</span></span>

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
let ty = ProvidedTypeDefinition(
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

<span data-ttu-id="37784-273">Si noti quanto segue:</span><span class="sxs-lookup"><span data-stu-id="37784-273">Note the following points:</span></span>


- <span data-ttu-id="37784-274">Il provider di tipi accetta due parametri statici: il `pattern`, che è obbligatorio e `options`, che sono facoltativi (perché è stato specificato un valore predefinito).</span><span class="sxs-lookup"><span data-stu-id="37784-274">The type provider takes two static parameters: the `pattern`, which is mandatory, and the `options`, which are optional (because a default value is provided).</span></span>
<br />

- <span data-ttu-id="37784-275">Dopo che vengono forniti gli argomenti statici, si crea un'istanza dell'espressione regolare.</span><span class="sxs-lookup"><span data-stu-id="37784-275">After the static arguments are supplied, you create an instance of the regular expression.</span></span> <span data-ttu-id="37784-276">Questa istanza genererà un'eccezione se l'espressione regolare non è valido e verrà segnalato questo errore per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="37784-276">This instance will throw an exception if the Regex is malformed, and this error will be reported to users.</span></span>
<br />

- <span data-ttu-id="37784-277">All'interno di `DefineStaticParameters` callback, definire il tipo che verrà restituito dopo che gli argomenti vengono forniti.</span><span class="sxs-lookup"><span data-stu-id="37784-277">Within the `DefineStaticParameters` callback, you define the type that will be returned after the arguments are supplied.</span></span>
<br />

- <span data-ttu-id="37784-278">Questo codice imposta `HideObjectMethods` su true in modo che l'esperienza IntelliSense rimarrà semplificata.</span><span class="sxs-lookup"><span data-stu-id="37784-278">This code sets `HideObjectMethods` to true so that the IntelliSense experience will remain streamlined.</span></span> <span data-ttu-id="37784-279">Questo attributo determina il `Equals`, `GetHashCode`, `Finalize`, e `GetType` membri da eliminare da elenchi di IntelliSense per un oggetto specificato.</span><span class="sxs-lookup"><span data-stu-id="37784-279">This attribute causes the `Equals`, `GetHashCode`, `Finalize`, and `GetType` members to be suppressed from IntelliSense lists for a provided object.</span></span>
<br />

- <span data-ttu-id="37784-280">Utilizzare `obj` come il tipo di base del metodo, ma verrà utilizzato un `Regex` oggetto come rappresentazione di runtime di questo tipo, come illustrato nell'esempio successivo.</span><span class="sxs-lookup"><span data-stu-id="37784-280">You use `obj` as the base type of the method, but you’ll use a `Regex` object as the runtime representation of this type, as the next example shows.</span></span>
<br />

- <span data-ttu-id="37784-281">La chiamata al `Regex` costruttore genera un `System.ArgumentException` quando un'espressione regolare non è valida.</span><span class="sxs-lookup"><span data-stu-id="37784-281">The call to the `Regex` constructor throws a `System.ArgumentException` when a regular expression isn’t valid.</span></span> <span data-ttu-id="37784-282">Il compilatore rileva questa eccezione e segnala all'utente un messaggio di errore in fase di compilazione o nell'editor di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="37784-282">The compiler catches this exception and reports an error message to the user at compile time or in the Visual Studio editor.</span></span> <span data-ttu-id="37784-283">Questa eccezione consente espressioni regolari di essere convalidati senza l'esecuzione di un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="37784-283">This exception enables regular expressions to be validated without running an application.</span></span>
<br />

<span data-ttu-id="37784-284">Il tipo definito in precedenza non è ancora utile perché non contiene tutti i metodi significativi o proprietà.</span><span class="sxs-lookup"><span data-stu-id="37784-284">The type defined above isn't useful yet because it doesn’t contain any meaningful methods or properties.</span></span> <span data-ttu-id="37784-285">Innanzitutto, aggiungere un valore statico `IsMatch` metodo:</span><span class="sxs-lookup"><span data-stu-id="37784-285">First, add a static `IsMatch` method:</span></span>

```fsharp
let isMatch = ProvidedMethod(
methodName = "IsMatch", 
parameters = [ProvidedParameter("input", typeof<string>)], 
returnType = typeof<bool>, 
IsStaticMethod = true,
InvokeCode = fun args -> <@@ Regex.IsMatch(%%args.[0], pattern) @@>) 

isMatch.AddXmlDoc "Indicates whether the regular expression finds a match in the specified input string." 
ty.AddMember isMatch
```

<span data-ttu-id="37784-286">Il codice precedente definisce un metodo `IsMatch`, che accetta una stringa come input e restituisce un `bool`.</span><span class="sxs-lookup"><span data-stu-id="37784-286">The previous code defines a method `IsMatch`, which takes a string as input and returns a `bool`.</span></span> <span data-ttu-id="37784-287">L'unica parte complicata è l'utilizzo del `args` argomento all'interno di `InvokeCode` definizione.</span><span class="sxs-lookup"><span data-stu-id="37784-287">The only tricky part is the use of the `args` argument within the `InvokeCode` definition.</span></span> <span data-ttu-id="37784-288">In questo esempio, `args` è un elenco di offerte che rappresenta gli argomenti per questo metodo.</span><span class="sxs-lookup"><span data-stu-id="37784-288">In this example, `args` is a list of quotations that represents the arguments to this method.</span></span> <span data-ttu-id="37784-289">Se il metodo è un metodo di istanza, il primo argomento rappresenta il `this` argomento.</span><span class="sxs-lookup"><span data-stu-id="37784-289">If the method is an instance method, the first argument represents the `this` argument.</span></span> <span data-ttu-id="37784-290">Per un metodo statico, tuttavia, gli argomenti sono tutti gli argomenti espliciti al metodo.</span><span class="sxs-lookup"><span data-stu-id="37784-290">However, for a static method, the arguments are all just the explicit arguments to the method.</span></span> <span data-ttu-id="37784-291">Si noti che il tipo del valore tra virgolette deve corrispondere il tipo restituito specificato (in questo caso, `bool`).</span><span class="sxs-lookup"><span data-stu-id="37784-291">Note that the type of the quoted value should match the specified return type (in this case, `bool`).</span></span> <span data-ttu-id="37784-292">Si noti inoltre che questo codice Usa il `AddXmlDoc` per verificare che il metodo fornito è inoltre utile documentazione, che è possibile specificare tramite IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="37784-292">Also note that this code uses the `AddXmlDoc` method to make sure that the provided method also has useful documentation, which you can supply through IntelliSense.</span></span>

<span data-ttu-id="37784-293">Successivamente, aggiungere un'istanza di metodo di corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="37784-293">Next, add an instance Match method.</span></span> <span data-ttu-id="37784-294">Tuttavia, questo metodo deve restituire un valore di una classe `Match` tipo in modo che i gruppi è possibile accedere in modo fortemente tipizzato.</span><span class="sxs-lookup"><span data-stu-id="37784-294">However, this method should return a value of a provided `Match` type so that the groups can be accessed in a strongly typed fashion.</span></span> <span data-ttu-id="37784-295">Di conseguenza, dichiarare prima il `Match` tipo.</span><span class="sxs-lookup"><span data-stu-id="37784-295">Thus, you first declare the `Match` type.</span></span> <span data-ttu-id="37784-296">Poiché questo tipo dipende dal modello che è stato fornito come argomento statico, questo tipo deve essere annidato all'interno della definizione di tipo con parametri:</span><span class="sxs-lookup"><span data-stu-id="37784-296">Because this type depends on the pattern that was supplied as a static argument, this type must be nested within the parameterized type definition:</span></span>

```fsharp
let matchTy = ProvidedTypeDefinition(
"MatchType", 
baseType = Some baseTy, 
HideObjectMethods = true)

ty.AddMember matchTy
```

<span data-ttu-id="37784-297">È quindi possibile aggiungere una proprietà al tipo di corrispondenza per ogni gruppo.</span><span class="sxs-lookup"><span data-stu-id="37784-297">You then add one property to the Match type for each group.</span></span> <span data-ttu-id="37784-298">In fase di esecuzione, una corrispondenza è rappresentata come un `System.Text.RegularExpressions.Match` valore, pertanto l'offerta che definisce la proprietà è necessario utilizzare il `System.Text.RegularExpressions.Match.Groups` proprietà per ottenere il gruppo rilevante indicizzata.</span><span class="sxs-lookup"><span data-stu-id="37784-298">At runtime, a match is represented as a `System.Text.RegularExpressions.Match` value, so the quotation that defines the property must use the `System.Text.RegularExpressions.Match.Groups` indexed property to get the relevant group.</span></span>

```fsharp
for group in r.GetGroupNames() do
// Ignore the group named 0, which represents all input.
if group <> "0" then
let prop = ProvidedProperty(
propertyName = group, 
propertyType = typeof<Group>, 
GetterCode = fun args -> <@@ ((%%args.[0]:obj) :?> Match).Groups.[group] @@>)
prop.AddXmlDoc(sprintf @"Gets the ""%s"" group from this match" group)
matchTy.AddMember prop
```

<span data-ttu-id="37784-299">Si noti che si sta aggiungendo documentazione XML per la proprietà specificata.</span><span class="sxs-lookup"><span data-stu-id="37784-299">Again, note that you’re adding XML documentation to the provided property.</span></span> <span data-ttu-id="37784-300">Si noti inoltre che se è possibile leggere una proprietà di un `GetterCode` funzione viene fornita e la proprietà può essere scritto se un `SetterCode` funzione viene fornita la proprietà risultante è di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="37784-300">Also note that a property can be read if a `GetterCode` function is provided, and the property can be written if a `SetterCode` function is provided, so the resulting property is read only.</span></span>

<span data-ttu-id="37784-301">Ora è possibile creare un metodo di istanza che restituisce un valore di questo `Match` tipo:</span><span class="sxs-lookup"><span data-stu-id="37784-301">Now you can create an instance method that returns a value of this `Match` type:</span></span>

```fsharp
let matchMethod = 
ProvidedMethod(
methodName = "Match", 
parameters = [ProvidedParameter("input", typeof<string>)], 
returnType = matchTy, 
InvokeCode = fun args -> <@@ ((%%args.[0]:obj) :?> Regex).Match(%%args.[1]) :> obj @@>)
matchMeth.AddXmlDoc "Searches the specified input string for the first ocurrence of this regular expression" 

ty.AddMember matchMeth
```

<span data-ttu-id="37784-302">Poiché si sta creando un metodo di istanza, `args.[0]` rappresenta il `RegexTyped` istanza in cui il metodo viene chiamato, e `args.[1]` è l'argomento di input.</span><span class="sxs-lookup"><span data-stu-id="37784-302">Because you are creating an instance method, `args.[0]` represents the `RegexTyped` instance on which the method is being called, and `args.[1]` is the input argument.</span></span>

<span data-ttu-id="37784-303">Infine, fornisce un costruttore in modo che sia possibile creare istanze del tipo fornito.</span><span class="sxs-lookup"><span data-stu-id="37784-303">Finally, provide a constructor so that instances of the provided type can be created.</span></span>

```fsharp
let ctor = ProvidedConstructor(
parameters = [], 
InvokeCode = fun args -> <@@ Regex(pattern, options) :> obj @@>)
ctor.AddXmlDoc("Initializes a regular expression instance.")

ty.AddMember ctor
```

<span data-ttu-id="37784-304">Il costruttore Cancella semplicemente per la creazione di un'istanza di Regex .NET standard, che viene nuovamente sottoposto a boxing a un oggetto perché `obj` è la cancellazione del tipo fornito.</span><span class="sxs-lookup"><span data-stu-id="37784-304">The constructor merely erases to the creation of a standard .NET Regex instance, which is again boxed to an object because `obj` is the erasure of the provided type.</span></span> <span data-ttu-id="37784-305">Con tale modifica, l'utilizzo di API di esempio che è specificata in precedenza nell'argomento funziona come previsto.</span><span class="sxs-lookup"><span data-stu-id="37784-305">With that change, the sample API usage that specified earlier in the topic works as expected.</span></span> <span data-ttu-id="37784-306">Il codice seguente è completo e finale:</span><span class="sxs-lookup"><span data-stu-id="37784-306">The following code is complete and final:</span></span>

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



let ty = ProvidedTypeDefinition(
thisAssembly, 
rootNamespace, 
typeName, 
baseType = Some baseTy)

ty.AddXmlDoc "A strongly typed interface to the regular expression '%s'"

// Provide strongly typed version of Regex.IsMatch static method.
let isMatch = ProvidedMethod(
methodName = "IsMatch", 
parameters = [ProvidedParameter("input", typeof<string>)], 
returnType = typeof<bool>, 
IsStaticMethod = true,
InvokeCode = fun args -> <@@ Regex.IsMatch(%%args.[0], pattern) @@>) 

isMatch.AddXmlDoc "Indicates whether the regular expression finds a match in the specified input string"

ty.AddMember isMatch

// Provided type for matches
// Again, erase to obj even though the representation will always be a Match
let matchTy = ProvidedTypeDefinition(
"MatchType", 
baseType = Some baseTy, 
HideObjectMethods = true)

// Nest the match type within parameterized Regex type.
ty.AddMember matchTy

// Add group properties to match type
for group in r.GetGroupNames() do
// Ignore the group named 0, which represents all input.
if group <> "0" then
let prop = ProvidedProperty(
propertyName = group, 
propertyType = typeof<Group>, 
GetterCode = fun args -> <@@ ((%%args.[0]:obj) :?> Match).Groups.[group] @@>)
prop.AddXmlDoc(sprintf @"Gets the ""%s"" group from this match" group)
matchTy.AddMember(prop)

// Provide strongly typed version of Regex.Match instance method.
let matchMeth = ProvidedMethod(
methodName = "Match", 
parameters = [ProvidedParameter("input", typeof<string>)], 
returnType = matchTy, 
InvokeCode = fun args -> <@@ ((%%args.[0]:obj) :?> Regex).Match(%%args.[1]) :> obj @@>)
matchMeth.AddXmlDoc "Searches the specified input string for the first occurence of this regular expression"

ty.AddMember matchMeth

// Declare a constructor.
let ctor = ProvidedConstructor(
parameters = [], 
InvokeCode = fun args -> <@@ Regex(pattern) :> obj @@>)

// Add documentation to the constructor.
ctor.AddXmlDoc "Initializes a regular expression instance"

ty.AddMember ctor

ty
| _ -> failwith "unexpected parameter values")) 

do this.AddNamespace(rootNamespace, [regexTy])

[<TypeProviderAssembly>]
do ()
```

`Key Lessons`

<span data-ttu-id="37784-307">In questa sezione viene spiegato come creare un provider di tipi che agisce sui relativi parametri statici.</span><span class="sxs-lookup"><span data-stu-id="37784-307">This section explained how to create a type provider that operates on its static parameters.</span></span> <span data-ttu-id="37784-308">Il provider controlla il parametro static e fornisce le operazioni in base al relativo valore.</span><span class="sxs-lookup"><span data-stu-id="37784-308">The provider checks the static parameter and provides operations based on its value.</span></span>


## <a name="a-type-provider-that-is-backed-by-local-data"></a><span data-ttu-id="37784-309">Un Provider di tipo supportato da dati locali</span><span class="sxs-lookup"><span data-stu-id="37784-309">A Type Provider That Is Backed By Local Data</span></span>
<span data-ttu-id="37784-310">Spesso è possibile che i provider di tipi per presentare le API basate su non solo parametri statici, ma anche le informazioni di sistema locale o remoto.</span><span class="sxs-lookup"><span data-stu-id="37784-310">Frequently you might want type providers to present APIs based on not only static parameters but also information from local or remote systems.</span></span> <span data-ttu-id="37784-311">Questa sezione descrive i provider di tipi che si basano sui dati locali, ad esempio i file di dati locali.</span><span class="sxs-lookup"><span data-stu-id="37784-311">This section discusses type providers that are based on local data, such as local data files.</span></span>


### <a name="simple-csv-file-provider"></a><span data-ttu-id="37784-312">Provider di File CSV semplice</span><span class="sxs-lookup"><span data-stu-id="37784-312">Simple CSV File Provider</span></span>
<span data-ttu-id="37784-313">Un esempio semplice, considerare un provider di tipi per l'accesso ai dati di scientifici in formato CSV (Comma Separated Value).</span><span class="sxs-lookup"><span data-stu-id="37784-313">As a simple example, consider a type provider for accessing scientific data in Comma Separated Value (CSV) format.</span></span> <span data-ttu-id="37784-314">Questa sezione si presuppone che i file CSV deve contenere una riga di intestazione seguita da dati a virgola mobile, come illustrato nella tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="37784-314">This section assumes that the CSV files contain a header row followed by floating point data, as the following table illustrates:</span></span>



|<span data-ttu-id="37784-315">Distanza (controllo)</span><span class="sxs-lookup"><span data-stu-id="37784-315">Distance (meter)</span></span>|<span data-ttu-id="37784-316">Tempo (secondo)</span><span class="sxs-lookup"><span data-stu-id="37784-316">Time (second)</span></span>|
|----------------|-------------|
|<span data-ttu-id="37784-317">50.0</span><span class="sxs-lookup"><span data-stu-id="37784-317">50.0</span></span>|<span data-ttu-id="37784-318">3.7</span><span class="sxs-lookup"><span data-stu-id="37784-318">3.7</span></span>|
|<span data-ttu-id="37784-319">100.0</span><span class="sxs-lookup"><span data-stu-id="37784-319">100.0</span></span>|<span data-ttu-id="37784-320">5.2</span><span class="sxs-lookup"><span data-stu-id="37784-320">5.2</span></span>|
|<span data-ttu-id="37784-321">150.0</span><span class="sxs-lookup"><span data-stu-id="37784-321">150.0</span></span>|<span data-ttu-id="37784-322">6.4</span><span class="sxs-lookup"><span data-stu-id="37784-322">6.4</span></span>|
<span data-ttu-id="37784-323">In questa sezione viene illustrato come fornire un tipo che è possibile utilizzare per ottenere le righe con un `Distance` proprietà di tipo `float<meter>` e `Time` proprietà di tipo `float<second>`.</span><span class="sxs-lookup"><span data-stu-id="37784-323">This section shows how to provide a type that you can use to get rows with a `Distance` property of type `float<meter>` and a `Time` property of type `float<second>`.</span></span> <span data-ttu-id="37784-324">Per semplicità, i presupposti seguenti:</span><span class="sxs-lookup"><span data-stu-id="37784-324">For simplicity, the following assumptions are made:</span></span>


- <span data-ttu-id="37784-325">I nomi di intestazione sono un'unità di misura o avere il formato "Nome (unità)" e non possono contenere virgole.</span><span class="sxs-lookup"><span data-stu-id="37784-325">Header names are either unit-less or have the form "Name (unit)" and don't contain commas.</span></span>
<br />

- <span data-ttu-id="37784-326">Le unità sono tutte le unità Systeme internazionali (SI) come il [Microsoft.FSharp.Data.UnitSystems.SI.UnitNames (modulo) (F #)](https://msdn.microsoft.com/library/3cb43485-11f5-4aa7-a779-558f19d4013b) modulo definisce.</span><span class="sxs-lookup"><span data-stu-id="37784-326">Units are all Systeme International (SI) units as the [Microsoft.FSharp.Data.UnitSystems.SI.UnitNames Module (F#)](https://msdn.microsoft.com/library/3cb43485-11f5-4aa7-a779-558f19d4013b) module defines.</span></span>
<br />

- <span data-ttu-id="37784-327">Le unità sono tutti semplice (ad esempio, controllare) piuttosto che composta (ad esempio, misuratore/secondo).</span><span class="sxs-lookup"><span data-stu-id="37784-327">Units are all simple (for example, meter) rather than compound (for example, meter/second).</span></span>
<br />

- <span data-ttu-id="37784-328">Tutte le colonne contengono dati a virgola mobile.</span><span class="sxs-lookup"><span data-stu-id="37784-328">All columns contain floating point data.</span></span>
<br />

<span data-ttu-id="37784-329">Un provider più completo sarebbe Allentare queste restrizioni.</span><span class="sxs-lookup"><span data-stu-id="37784-329">A more complete provider would loosen these restrictions.</span></span>

<span data-ttu-id="37784-330">Caso il primo passaggio consiste nel prendere in considerazione l'aspetto dell'API.</span><span class="sxs-lookup"><span data-stu-id="37784-330">Again the first step is to consider how the API should look.</span></span> <span data-ttu-id="37784-331">Dato un file `info.csv` con i contenuti della tabella precedente (nel formato delimitato da virgole), gli utenti del provider possono scrivere codice simile all'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="37784-331">Given an `info.csv` file with the contents from the previous table (in comma-separated format), users of the provider should be able to write code that resembles the following example:</span></span>

```fsharp
let info = new MiniCsv<"info.csv">()
for row in info.Data do
let time = row.Time
printfn "%f" (float time)
```

<span data-ttu-id="37784-332">In questo caso, il compilatore deve convertire queste chiamate in modo analogo al seguente:</span><span class="sxs-lookup"><span data-stu-id="37784-332">In this case, the compiler should convert these calls into something like the following example:</span></span>

```fsharp
let info = new MiniCsvFile("info.csv")
for row in info.Data do
let (time:float) = row.[1]
printfn "%f" (float time)
```

<span data-ttu-id="37784-333">La traduzione ottimale richiede il provider di tipi definire un reale `CsvFile` tipo nell'assembly del provider di tipi.</span><span class="sxs-lookup"><span data-stu-id="37784-333">The optimal translation will require the type provider to define a real `CsvFile` type in the type provider's assembly.</span></span> <span data-ttu-id="37784-334">Provider di tipi spesso basano su alcuni tipi di supporto e metodi per eseguire il wrapping logica importanti.</span><span class="sxs-lookup"><span data-stu-id="37784-334">Type providers often rely on a few helper types and methods to wrap important logic.</span></span> <span data-ttu-id="37784-335">Poiché le misure vengono cancellate in fase di esecuzione, è possibile utilizzare un `float[]` come tipo cancellato per una riga.</span><span class="sxs-lookup"><span data-stu-id="37784-335">Because measures are erased at runtime, you can use a `float[]` as the erased type for a row.</span></span> <span data-ttu-id="37784-336">Il compilatore considera diverse colonne con tipi di misure diversi.</span><span class="sxs-lookup"><span data-stu-id="37784-336">The compiler will treat different columns as having different measure types.</span></span> <span data-ttu-id="37784-337">Ad esempio, la prima colonna in questo esempio ha tipo `float<meter>`, mentre la seconda è `float<second>`.</span><span class="sxs-lookup"><span data-stu-id="37784-337">For example, the first column in our example has type `float<meter>`, and the second has `float<second>`.</span></span> <span data-ttu-id="37784-338">Tuttavia, la rappresentazione cancellata può rimanere piuttosto semplice.</span><span class="sxs-lookup"><span data-stu-id="37784-338">However, the erased representation can remain quite simple.</span></span>

<span data-ttu-id="37784-339">Il codice seguente illustra le principali dell'implementazione.</span><span class="sxs-lookup"><span data-stu-id="37784-339">The following code shows the core of the implementation.</span></span>

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
inherit TypeProviderForNamespaces()

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

let prop = ProvidedProperty(fieldName, fieldTy, 
GetterCode = fun [row] -> <@@ (%%row:float[]).[i] @@>)

// Add metadata that defines the property's location in the referenced file.
prop.AddDefinitionLocation(1, headers.[i].Index + 1, filename)
rowTy.AddMember(prop) 

// Define the provided type, erasing to CsvFile.
let ty = ProvidedTypeDefinition(asm, ns, tyName, Some(typeof<CsvFile>))

// Add a parameterless constructor that loads the file that was used to define the schema.
let ctor0 = ProvidedConstructor([], 
InvokeCode = fun [] -> <@@ CsvFile(resolvedFilename) @@>)
ty.AddMember ctor0

// Add a constructor that takes the file name to load.
let ctor1 = ProvidedConstructor([ProvidedParameter("filename", typeof<string>)], 
InvokeCode = fun [filename] -> <@@ CsvFile(%%filename) @@>)
ty.AddMember ctor1

// Add a more strongly typed Data property, which uses the existing property at runtime.
let prop = ProvidedProperty("Data", typedefof<seq<_>>.MakeGenericType(rowTy), 
GetterCode = fun [csvFile] -> <@@ (%%csvFile:CsvFile).Data @@>)
ty.AddMember prop

// Add the row type as a nested type.
ty.AddMember rowTy
ty)

// Add the type to the namespace.
do this.AddNamespace(ns, [csvTy])
```

<span data-ttu-id="37784-340">Tenere presente i punti seguenti circa l'implementazione:</span><span class="sxs-lookup"><span data-stu-id="37784-340">Note the following points about the implementation:</span></span>


- <span data-ttu-id="37784-341">I costruttori di overload consentono il file originale o uno che dispone di uno schema identico da leggere.</span><span class="sxs-lookup"><span data-stu-id="37784-341">Overloaded constructors allow either the original file or one that has an identical schema to be read.</span></span> <span data-ttu-id="37784-342">Questo modello è comune quando si scrive un provider di tipi per le origini dati locali o remote, e questo modello consente a un file locale da utilizzare come modello per i dati remoti.</span><span class="sxs-lookup"><span data-stu-id="37784-342">This pattern is common when you write a type provider for local or remote data sources, and this pattern allows a local file to be used as the template for remote data.</span></span>
<br />  <span data-ttu-id="37784-343">È possibile utilizzare il [TypeProviderConfig](https://msdn.microsoft.com/library/1cda7b9a-3d07-475d-9315-d65e1c97eb44) valore passato al costruttore del provider di tipo per risolvere i nomi di file relativo.</span><span class="sxs-lookup"><span data-stu-id="37784-343">You can use the [TypeProviderConfig](https://msdn.microsoft.com/library/1cda7b9a-3d07-475d-9315-d65e1c97eb44) value that’s passed in to the type provider constructor to resolve relative file names.</span></span>
<br />

- <span data-ttu-id="37784-344">È possibile utilizzare il `AddDefinitionLocation` metodo per definire il percorso della proprietà specificate.</span><span class="sxs-lookup"><span data-stu-id="37784-344">You can use the `AddDefinitionLocation` method to define the location of the provided properties.</span></span> <span data-ttu-id="37784-345">Pertanto, se si utilizza `Go To Definition` su una proprietà specificata, il file CSV verrà aperto in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="37784-345">Therefore, if you use `Go To Definition` on a provided property, the CSV file will open in Visual Studio.</span></span>
<br />

- <span data-ttu-id="37784-346">È possibile utilizzare il `ProvidedMeasureBuilder` tipo per cercare le unità di isolamento e per generare pertinente `float<_>` tipi.</span><span class="sxs-lookup"><span data-stu-id="37784-346">You can use the `ProvidedMeasureBuilder` type to look up the SI units and to generate the relevant `float<_>` types.</span></span>
<br />

`Key Lessons`

<span data-ttu-id="37784-347">In questa sezione viene spiegato come creare un provider di tipi per un'origine dati locale con un semplice schema contenuto nell'origine dati stessa.</span><span class="sxs-lookup"><span data-stu-id="37784-347">This section explained how to create a type provider for a local data source with a simple schema that's contained in the data source itself.</span></span>


## <a name="going-further"></a><span data-ttu-id="37784-348">Continua</span><span class="sxs-lookup"><span data-stu-id="37784-348">Going Further</span></span>
<span data-ttu-id="37784-349">Nelle sezioni seguenti includono i suggerimenti per approfondire l'argomento.</span><span class="sxs-lookup"><span data-stu-id="37784-349">The following sections include suggestions for further study.</span></span>


### <a name="a-look-at-the-compiled-code-for-erased-types"></a><span data-ttu-id="37784-350">Esaminare il codice compilato per i tipi cancellati</span><span class="sxs-lookup"><span data-stu-id="37784-350">A Look at the Compiled Code for Erased Types</span></span>
<span data-ttu-id="37784-351">Per avere un'idea di come l'utilizzo del provider di tipo corrisponde al codice che viene generato, esaminare la funzione seguente utilizzando il `HelloWorldTypeProvider` utilizzato in precedenza in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="37784-351">To give you some idea of how the use of the type provider corresponds to the code that's emitted, look at the following function by using the `HelloWorldTypeProvider` that's used earlier in this topic.</span></span>

```fsharp
let function1 () = 
let obj1 = Samples.HelloWorldTypeProvider.Type1("some data")
obj1.InstanceProperty
```

<span data-ttu-id="37784-352">Di seguito è riportata un'immagine del codice risulta decompilato tramite ildasm.exe:</span><span class="sxs-lookup"><span data-stu-id="37784-352">Here’s an image of the resulting code decompiled by using ildasm.exe:</span></span>

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

<span data-ttu-id="37784-353">Come illustrato nell'esempio, tutti i riferimenti del tipo `Type1` e `InstanceProperty` proprietà sono stati cancellati, lasciando solo le operazioni sui tipi di runtime coinvolti.</span><span class="sxs-lookup"><span data-stu-id="37784-353">As the example shows, all mentions of the type `Type1` and the `InstanceProperty` property have been erased, leaving only operations on the runtime types involved.</span></span>


### <a name="design-and-naming-conventions-for-type-providers"></a><span data-ttu-id="37784-354">Progettazione e convenzioni di denominazione per i provider di tipi</span><span class="sxs-lookup"><span data-stu-id="37784-354">Design and Naming Conventions for Type Providers</span></span>
<span data-ttu-id="37784-355">Osservare le seguenti convenzioni durante la creazione di provider di tipi.</span><span class="sxs-lookup"><span data-stu-id="37784-355">Observe the following conventions when authoring type providers.</span></span>


- `Providers for Connectivity Protocols`
<br />  <span data-ttu-id="37784-356">In generale, nomi di provider la maggior parte delle DLL per i protocolli di connettività dei dati e il servizio, ad esempio le connessioni di OData o SQL, devono terminare `TypeProvider` o `TypeProviders`.</span><span class="sxs-lookup"><span data-stu-id="37784-356">In general, names of most provider DLLs for data and service connectivity protocols, such as OData or SQL connections, should end in `TypeProvider` or `TypeProviders`.</span></span> <span data-ttu-id="37784-357">Ad esempio, utilizzare un nome DLL che è simile alla stringa seguente:</span><span class="sxs-lookup"><span data-stu-id="37784-357">For example, use a DLL name that resembles the following string:</span></span>
<br />

```
  Fabrikam.Management.BasicTypeProviders.dll
```

  <span data-ttu-id="37784-358">Verificare che i tipi forniti sono membri dello spazio dei nomi corrispondenti e indicano il protocollo di connettività che è implementato:</span><span class="sxs-lookup"><span data-stu-id="37784-358">Ensure that your provided types are members of the corresponding namespace, and indicate the connectivity protocol that you implemented:</span></span>
<br />

```
  Fabrikam.Management.BasicTypeProviders.WmiConnection<…>
  Fabrikam.Management.BasicTypeProviders.DataProtocolConnection<…>
```

- `Utility Providers for General Coding`
<br />  <span data-ttu-id="37784-359">Per un utilità provider di tipi, ad esempio per le espressioni regolari, il provider di tipi può essere parte di una libreria di base, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="37784-359">For a utility type provider such as that for regular expressions, the type provider may be part of a base library, as the following example shows:</span></span>
<br />

```fsharp
  #r "Fabrikam.Core.Text.Utilities.dll"
```

  <span data-ttu-id="37784-360">In questo caso, il tipo fornito appariranno in un momento appropriato in base alle convenzioni di progettazione .NET normale:</span><span class="sxs-lookup"><span data-stu-id="37784-360">In this case, the provided type would appear at an appropriate point according to normal .NET design conventions:</span></span>
<br />

```fsharp
  open Fabrikam.Core.Text.RegexTyped
  
  let regex = new RegexTyped<"a+b+a+b+">()
```

- `Singleton Data Sources`
<br />  <span data-ttu-id="37784-361">Alcuni provider di tipo connettersi a un'origine dati dedicato e fornire solo i dati.</span><span class="sxs-lookup"><span data-stu-id="37784-361">Some type providers connect to a single dedicated data source and provide only data.</span></span> <span data-ttu-id="37784-362">In questo caso, è necessario eliminare il `TypeProvider` suffisso e utilizzare normale convenzioni di denominazione .NET:</span><span class="sxs-lookup"><span data-stu-id="37784-362">In this case, you should drop the `TypeProvider` suffix and use normal conventions for .NET naming:</span></span>
<br />

```fsharp
  #r "Fabrikam.Data.Freebase.dll"
  
  let data = Fabrikam.Data.Freebase.Astronomy.Asteroids
```

  <span data-ttu-id="37784-363">Per ulteriori informazioni, vedere il `GetConnection` progettare convenzione descritto più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="37784-363">For more information, see the `GetConnection` design convention that's described later in this topic.</span></span>
<br />


### <a name="design-patterns-for-type-providers"></a><span data-ttu-id="37784-364">Modelli di progettazione per i provider di tipi</span><span class="sxs-lookup"><span data-stu-id="37784-364">Design Patterns for Type Providers</span></span>
<span data-ttu-id="37784-365">Nelle sezioni seguenti vengono descritti i modelli di progettazione che è possibile utilizzare durante la creazione di provider di tipi.</span><span class="sxs-lookup"><span data-stu-id="37784-365">The following sections describe design patterns you can use when authoring type providers.</span></span>


#### <a name="the-getconnection-design-pattern"></a><span data-ttu-id="37784-366">Il modello di struttura GetConnection</span><span class="sxs-lookup"><span data-stu-id="37784-366">The GetConnection Design Pattern</span></span>
<span data-ttu-id="37784-367">La maggior parte dei provider di tipi deve essere scritto per utilizzare il `GetConnection` modello utilizzato dal provider di tipi in FSharp.Data.TypeProviders.dll, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="37784-367">Most type providers should be written to use the `GetConnection` pattern that's used by the type providers in FSharp.Data.TypeProviders.dll, as the following example shows:</span></span>

```fsharp
#r "Fabrikam.Data.WebDataStore.dll"

type Service = Fabrikam.Data.WebDataStore<…static connection parameters…>

let connection = Service.GetConnection(…dynamic connection parameters…)

let data = connection.Astronomy.Asteroids
```

#### <a name="type-providers-backed-by-remote-data-and-services"></a><span data-ttu-id="37784-368">Provider di tipo supportato da servizi e i dati remoti</span><span class="sxs-lookup"><span data-stu-id="37784-368">Type Providers Backed By Remote Data and Services</span></span>
<span data-ttu-id="37784-369">Prima di creare un provider di tipo supportato da servizi e dei dati remoti, è necessario considerare una gamma di problemi che vengono svolte nella programmazione connessa.</span><span class="sxs-lookup"><span data-stu-id="37784-369">Before you create a type provider that's backed by remote data and services, you must consider a range of issues that are inherent in connected programming.</span></span> <span data-ttu-id="37784-370">Questi problemi sono le considerazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="37784-370">These issues include the following considerations:</span></span>


- <span data-ttu-id="37784-371">Mapping dello schema</span><span class="sxs-lookup"><span data-stu-id="37784-371">schema mapping</span></span>
<br />

- <span data-ttu-id="37784-372">liveness e invalidamento in presenza di modifica dello schema</span><span class="sxs-lookup"><span data-stu-id="37784-372">liveness and invalidation in the presence of schema change</span></span>
<br />

- <span data-ttu-id="37784-373">la memorizzazione nella cache di schema</span><span class="sxs-lookup"><span data-stu-id="37784-373">schema caching</span></span>
<br />

- <span data-ttu-id="37784-374">implementazioni asincrone di operazioni di accesso ai dati</span><span class="sxs-lookup"><span data-stu-id="37784-374">asynchronous implementations of data access operations</span></span>
<br />

- <span data-ttu-id="37784-375">supporto di query, incluse le query LINQ</span><span class="sxs-lookup"><span data-stu-id="37784-375">supporting queries, including LINQ queries</span></span>
<br />

- <span data-ttu-id="37784-376">le credenziali e autenticazione</span><span class="sxs-lookup"><span data-stu-id="37784-376">credentials and authentication</span></span>
<br />

<span data-ttu-id="37784-377">In questo argomento non Esplora ulteriormente questi problemi.</span><span class="sxs-lookup"><span data-stu-id="37784-377">This topic doesn't explore these issues further.</span></span>


### <a name="additional-authoring-techniques"></a><span data-ttu-id="37784-378">Ulteriori informazioni sulle tecniche di creazione e modifica</span><span class="sxs-lookup"><span data-stu-id="37784-378">Additional Authoring Techniques</span></span>
<span data-ttu-id="37784-379">Quando si scrivono i propri provider di tipo, si potrebbe voler usare le seguenti tecniche aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="37784-379">When you write your own type providers, you might want to use the following additional techniques.</span></span>


- `Creating Types and Members On-Demand`
<br />  <span data-ttu-id="37784-380">L'API ProvidedType è posticipata versioni AddMember.</span><span class="sxs-lookup"><span data-stu-id="37784-380">The ProvidedType API has delayed versions of AddMember.</span></span>
<br />

```fsharp
  type ProvidedType =
  member AddMemberDelayed  : (unit -> MemberInfo)      -> unit
  member AddMembersDelayed : (unit -> MemberInfo list) -> unit
```

  <span data-ttu-id="37784-381">Queste versioni vengono utilizzate per creare spazi su richiesta dei tipi.</span><span class="sxs-lookup"><span data-stu-id="37784-381">These versions are used to create on-demand spaces of types.</span></span>
<br />

- `Providing Array, ByRef, and Pointer types`
<br />  <span data-ttu-id="37784-382">Rendere i membri forniti (le cui firme includono tipi di matrice, tipi byref e creazioni di istanze di tipi generici) usando la normale `MakeArrayType`, `MakePointerType`, e `MakeGenericType` in qualsiasi istanza di System. Type, tra cui `ProvidedTypeDefinitions`.</span><span class="sxs-lookup"><span data-stu-id="37784-382">You make provided members (whose signatures include array types, byref types, and instantiations of generic types) by using the normal `MakeArrayType`, `MakePointerType`, and `MakeGenericType` on any instance of System.Type, including `ProvidedTypeDefinitions`.</span></span>
<br />

- `Providing Unit of Measure Annotations`
<br />  <span data-ttu-id="37784-383">L'API ProvidedTypes fornisce gli helper per fornire le annotazioni di misura.</span><span class="sxs-lookup"><span data-stu-id="37784-383">The ProvidedTypes API provides helpers for providing measure annotations.</span></span> <span data-ttu-id="37784-384">Ad esempio, per fornire il tipo `float<kg>`, utilizzare il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="37784-384">For example, to provide the type `float<kg>`, use the following code:</span></span>
<br />

```fsharp
  let measures = ProvidedMeasureBuilder.Default
  let kg = measures.SI "kilogram"
  let m = measures.SI "meter"
  let float_kg = measures.AnnotateType(typeof<float>,[kg])
```

  <span data-ttu-id="37784-385">Per fornire il tipo `Nullable<decimal<kg/m^2>>`, utilizzare il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="37784-385">To provide the type `Nullable<decimal<kg/m^2>>`, use the following code:</span></span>
<br />

```fsharp
  let kgpm2 = measures.Ratio(kg, measures.Square m)
  let dkgpm2 = measures.AnnotateType(typeof<decimal>,[kgpm2])
  let nullableDecimal_kgpm2 = typedefof<System.Nullable<_>>.MakeGenericType [|dkgpm2 |]
```

- `Accessing Project-Local or Script-Local Resources`
<br />  <span data-ttu-id="37784-386">Ogni istanza di un provider di tipi può essere assegnato un `TypeProviderConfig` valore durante la costruzione.</span><span class="sxs-lookup"><span data-stu-id="37784-386">Each instance of a type provider can be given a `TypeProviderConfig` value during construction.</span></span> <span data-ttu-id="37784-387">Questo valore contiene la cartella"Risoluzione" per il provider (vale a dire la cartella di progetto per la compilazione o la directory che contiene uno script), l'elenco di assembly di riferimento e altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="37784-387">This value contains the "resolution folder" for the provider (that is, the project folder for the compilation or the directory that contains a script), the list of referenced assemblies, and other information.</span></span>
<br />

- `Invalidation`
<br />  <span data-ttu-id="37784-388">I provider possono generare segnali di invalidamento per informare il servizio di linguaggio F # che i presupposti di schema sia stato modificato.</span><span class="sxs-lookup"><span data-stu-id="37784-388">Providers can raise invalidation signals to notify the F# language service that the schema assumptions may have changed.</span></span> <span data-ttu-id="37784-389">Quando si verifica l'invalidamento, un typecheck viene eseguito il rollforward se il provider è ospitato in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="37784-389">When invalidation occurs, a typecheck is redone if the provider is being hosted in Visual Studio.</span></span> <span data-ttu-id="37784-390">Questo segnale verrà ignorato quando il provider è ospitato in F # Interactive o dal compilatore F # (fsc.exe).</span><span class="sxs-lookup"><span data-stu-id="37784-390">This signal will be ignored when the provider is hosted in F# Interactive or by the F# Compiler (fsc.exe).</span></span>
<br />

- `Caching Schema Information`
<br />  <span data-ttu-id="37784-391">Provider spesso necessario memorizzare nella cache di accesso alle informazioni sullo schema.</span><span class="sxs-lookup"><span data-stu-id="37784-391">Providers must often cache access to schema information.</span></span> <span data-ttu-id="37784-392">I dati memorizzati nella cache devono essere archiviati utilizzando un nome di file che viene fornito come parametro statico o come dati utente.</span><span class="sxs-lookup"><span data-stu-id="37784-392">The cached data should be stored by using a file name that's given as a static parameter or as user data.</span></span> <span data-ttu-id="37784-393">Un esempio di memorizzazione nella cache dello schema è il `LocalSchemaFile` nei provider di tipo nel parametro di `FSharp.Data.TypeProviders` assembly.</span><span class="sxs-lookup"><span data-stu-id="37784-393">An example of schema caching is the `LocalSchemaFile` parameter in the type providers in the `FSharp.Data.TypeProviders` assembly.</span></span> <span data-ttu-id="37784-394">Nell'implementazione di questi provider, questo parametro statico indirizza il provider di tipi da utilizzare le informazioni sullo schema nel file specificato anziché l'accesso all'origine di dati attraverso la rete locale.</span><span class="sxs-lookup"><span data-stu-id="37784-394">In the implementation of these providers, this static parameter directs the type provider to use the schema information in the specified local file instead of accessing the data source over the network.</span></span> <span data-ttu-id="37784-395">Per utilizzare le informazioni memorizzate nella cache dello schema, è necessario impostare anche il parametro static `ForceUpdate` a `false`.</span><span class="sxs-lookup"><span data-stu-id="37784-395">To use cached schema information, you must also set the static parameter `ForceUpdate` to `false`.</span></span> <span data-ttu-id="37784-396">È possibile utilizzare una tecnica simile per consentire l'accesso ai dati online e offline.</span><span class="sxs-lookup"><span data-stu-id="37784-396">You could use a similar technique to enable online and offline data access.</span></span>
<br />

- `Backing Assembly`
<br />  <span data-ttu-id="37784-397">Quando si compila un file con estensione dll o .exe, il file DLL di supporto per i tipi generati è collegato in modo statico l'assembly risultante.</span><span class="sxs-lookup"><span data-stu-id="37784-397">When you compile a .dll or .exe file, the backing .dll file for generated types is statically linked into the resulting assembly.</span></span> <span data-ttu-id="37784-398">Questo collegamento viene creato copiando le definizioni dei tipi di linguaggio intermedio (IL) e le risorse gestite da assembly di supporto nell'assembly finale.</span><span class="sxs-lookup"><span data-stu-id="37784-398">This link is created by copying the Intermediate Language (IL) type definitions and any managed resources from the backing assembly into the final assembly.</span></span> <span data-ttu-id="37784-399">Quando si usa F # Interactive, il file DLL di supporto non vengono copiato e verrà invece caricato direttamente nel processo di F # Interactive.</span><span class="sxs-lookup"><span data-stu-id="37784-399">When you use F# Interactive, the backing .dll file isn't copied and is instead loaded directly into the F# Interactive process.</span></span>
<br />

- `Exceptions and Diagnostics from Type Providers`
<br />  <span data-ttu-id="37784-400">Tutte le occorrenze di tutti i membri di tipi forniti possono generare eccezioni.</span><span class="sxs-lookup"><span data-stu-id="37784-400">All uses of all members from provided types may throw exceptions.</span></span> <span data-ttu-id="37784-401">In tutti i casi, se un provider di tipi genera un'eccezione, il compilatore host attributi l'errore a un provider di tipo specifico.</span><span class="sxs-lookup"><span data-stu-id="37784-401">In all cases, if a type provider throws an exception, the host compiler attributes the error to a specific type provider.</span></span>
<br />
  - <span data-ttu-id="37784-402">Le eccezioni di tipo provider non dovrebbero restituire errori interni del compilatore.</span><span class="sxs-lookup"><span data-stu-id="37784-402">Type provider exceptions should never result in internal compiler errors.</span></span>
<br />

  - <span data-ttu-id="37784-403">Provider di tipi non è possibile segnalare gli avvisi.</span><span class="sxs-lookup"><span data-stu-id="37784-403">Type providers can't report warnings.</span></span>
<br />

  - <span data-ttu-id="37784-404">Quando un provider di tipi è ospitato il compilatore F #, un ambiente di sviluppo di F # o F # Interactive, vengono rilevate tutte le eccezioni da tale provider.</span><span class="sxs-lookup"><span data-stu-id="37784-404">When a type provider is hosted in the F# compiler, an F# development environment, or F# Interactive, all exceptions from that provider are caught.</span></span> <span data-ttu-id="37784-405">La proprietà del messaggio è sempre il testo dell'errore e viene visualizzato senza la traccia dello stack.</span><span class="sxs-lookup"><span data-stu-id="37784-405">The Message property is always the error text, and no stack trace appears.</span></span> <span data-ttu-id="37784-406">Se si desidera generare un'eccezione, è possibile generare gli esempi seguenti:</span><span class="sxs-lookup"><span data-stu-id="37784-406">If you’re going to throw an exception, you can throw the following examples:</span></span>
<br />
    - `System.NotSupportedException`
<br />

    - `System.IO.IOException`
<br />

    - `System.Exception`
<br />


#### <a name="providing-generated-types"></a><span data-ttu-id="37784-407">Fornisce i tipi generati</span><span class="sxs-lookup"><span data-stu-id="37784-407">Providing Generated Types</span></span>
<span data-ttu-id="37784-408">Finora, cui è illustrato in questo documento come fornire tipi cancellati.</span><span class="sxs-lookup"><span data-stu-id="37784-408">So far, this document has explained how provide erased types.</span></span> <span data-ttu-id="37784-409">È inoltre possibile utilizzare il meccanismo di provider in F # per fornire tipi generati, che vengono aggiunti come definizioni di tipi .NET reali in programma degli utenti.</span><span class="sxs-lookup"><span data-stu-id="37784-409">You can also use the type provider mechanism in F# to provide generated types, which are added as real .NET type definitions into the users' program.</span></span> <span data-ttu-id="37784-410">È necessario fare riferimento generato forniti tipi utilizzando una definizione di tipo.</span><span class="sxs-lookup"><span data-stu-id="37784-410">You must refer to generated provided types by using a type definition.</span></span>

```fsharp
open Microsoft.FSharp.TypeProviders 

type Service = ODataService<" http://services.odata.org/Northwind/Northwind.svc/">
```

<span data-ttu-id="37784-411">Il codice helper ProvidedTypes 0,2 che fa parte della versione di F # 3.0 offre solo supporto limitato per fornire tipi generati.</span><span class="sxs-lookup"><span data-stu-id="37784-411">The ProvidedTypes-0.2 helper code that is part of the F# 3.0 release has only limited support for providing generated types.</span></span> <span data-ttu-id="37784-412">Le istruzioni seguenti devono essere soddisfatte per una definizione di tipo generato:</span><span class="sxs-lookup"><span data-stu-id="37784-412">The following statements must be true for a generated type definition:</span></span>


- <span data-ttu-id="37784-413">IsErased deve essere impostato su `false`.</span><span class="sxs-lookup"><span data-stu-id="37784-413">IsErased must be set to `false`.</span></span>
<br />

- <span data-ttu-id="37784-414">Il provider deve disporre di un assembly con un file. dll di supporto effettivo .NET con un file DLL corrispondente sul disco.</span><span class="sxs-lookup"><span data-stu-id="37784-414">The provider must have an assembly that has an actual backing .NET .dll file with a matching .dll file on disk.</span></span>
<br />

<span data-ttu-id="37784-415">È inoltre necessario chiamare `ConvertToGenerated` su un tipo radice specificato i cui tipi annidati formano un set chiuso di tipi generati.</span><span class="sxs-lookup"><span data-stu-id="37784-415">You must also call `ConvertToGenerated` on a root provided type whose nested types form a closed set of generated types.</span></span> <span data-ttu-id="37784-416">Questa chiamata genera la definizione di tipo fornito specificato e le relative definizioni di tipo annidato in un assembly e consente di regolare il `Assembly` proprietà di tutte le definizioni di tipo fornito per restituire tale assembly.</span><span class="sxs-lookup"><span data-stu-id="37784-416">This call emits the given provided type definition and its nested type definitions into an assembly and adjusts the `Assembly` property of all provided type definitions to return that assembly.</span></span> <span data-ttu-id="37784-417">L'assembly viene generato solo quando si accede alla proprietà di Assembly del tipo radice per la prima volta.</span><span class="sxs-lookup"><span data-stu-id="37784-417">The assembly is emitted only when the Assembly property on the root type is accessed for the first time.</span></span> <span data-ttu-id="37784-418">Il compilatore F # host accedere a questa proprietà durante l'elaborazione di una dichiarazione di tipo vedere generative per il tipo.</span><span class="sxs-lookup"><span data-stu-id="37784-418">The host F# compiler does access this property when it processes a generative type declaration for the type.</span></span>


## <a name="rules-and-limitations"></a><span data-ttu-id="37784-419">Regole e limitazioni</span><span class="sxs-lookup"><span data-stu-id="37784-419">Rules and Limitations</span></span>
<span data-ttu-id="37784-420">Quando si scrivono i provider di tipi, tenere le seguenti regole e limitazioni presenti.</span><span class="sxs-lookup"><span data-stu-id="37784-420">When you write type providers, keep the following rules and limitations in mind.</span></span>


- `Provided types must be reachable.`
<br />  <span data-ttu-id="37784-421">Tutti forniti tipi devono essere raggiungibili dai tipi non annidati.</span><span class="sxs-lookup"><span data-stu-id="37784-421">All provided types should be reachable from the non-nested types.</span></span> <span data-ttu-id="37784-422">I tipi annidati non sono indicati nella chiamata al `TypeProviderForNamespaces` costruttore o una chiamata a `AddNamespace`.</span><span class="sxs-lookup"><span data-stu-id="37784-422">The non-nested types are given in the call to the `TypeProviderForNamespaces` constructor or a call to `AddNamespace`.</span></span> <span data-ttu-id="37784-423">Ad esempio, se il provider fornisce un tipo `StaticClass.P : T`, è necessario assicurarsi che T è un tipo non annidato o annidati in uno.</span><span class="sxs-lookup"><span data-stu-id="37784-423">For example, if the provider provides a type `StaticClass.P : T`, you must ensure that T is either a non-nested type or nested under one.</span></span>
<br />  <span data-ttu-id="37784-424">Ad esempio, alcuni provider hanno una classe statica, ad esempio `DataTypes` che contengono questi `T1, T2, T3, ...` tipi.</span><span class="sxs-lookup"><span data-stu-id="37784-424">For example, some providers have a static class such as `DataTypes` that contain these `T1, T2, T3, ...` types.</span></span> <span data-ttu-id="37784-425">In caso contrario, l'errore indica che è stato trovato un riferimento al tipo T nell'assembly, ma non è stato possibile trovare il tipo nell'assembly in questione.</span><span class="sxs-lookup"><span data-stu-id="37784-425">Otherwise, the error says that a reference to type T in assembly A was found, but the type couldn't be found in that assembly.</span></span> <span data-ttu-id="37784-426">Se viene visualizzato questo errore, verificare che tutti i sottotipi siano raggiungibili dai tipi di provider.</span><span class="sxs-lookup"><span data-stu-id="37784-426">If this error appears, verify that all your subtypes can be reached from the provider types.</span></span> <span data-ttu-id="37784-427">Nota: Queste `T1, T2, T3...` tipi sono definiti come il *al volo* tipi.</span><span class="sxs-lookup"><span data-stu-id="37784-427">Note: These `T1, T2, T3...` types are referred to as the *on-the-fly* types.</span></span> <span data-ttu-id="37784-428">È necessario inserirli in uno spazio dei nomi accessibile o un tipo padre.</span><span class="sxs-lookup"><span data-stu-id="37784-428">Remember to put them in an accessible namespace or a parent type.</span></span>
<br />

- `Limitations of the Type Provider Mechanism`
<br />  <span data-ttu-id="37784-429">Il meccanismo di provider in F # presenta le limitazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="37784-429">The type provider mechanism in F# has the following limitations:</span></span>
<br />
  - <span data-ttu-id="37784-430">Non supporta l'infrastruttura per il provider di tipi in F # fornita generico tipi o metodi generici forniti.</span><span class="sxs-lookup"><span data-stu-id="37784-430">The underlying infrastructure for type providers in F# doesn't support provided generic types or provided generic methods.</span></span>
<br />

  - <span data-ttu-id="37784-431">Il meccanismo non supporta i tipi annidati con parametri statici.</span><span class="sxs-lookup"><span data-stu-id="37784-431">The mechanism doesn't support nested types with static parameters.</span></span>
<br />

- `Limitations of the ProvidedTypes Support Code`
<br />  <span data-ttu-id="37784-432">Il `ProvidedTypes` codice di supporto ha le seguenti regole e limitazioni:</span><span class="sxs-lookup"><span data-stu-id="37784-432">The `ProvidedTypes` support code has the following rules and limitations:</span></span>
<br />
  1. <span data-ttu-id="37784-433">Le proprietà fornite con indicizzata getter e setter non sono implementate.</span><span class="sxs-lookup"><span data-stu-id="37784-433">Provided properties with indexed getters and setters aren't implemented.</span></span>
<br />

  2. <span data-ttu-id="37784-434">Eventi forniti non sono implementati.</span><span class="sxs-lookup"><span data-stu-id="37784-434">Provided events aren't implemented.</span></span>
<br />

  3. <span data-ttu-id="37784-435">I tipi forniti e informazioni sugli oggetti deve essere utilizzato solo per il meccanismo di provider in F #.</span><span class="sxs-lookup"><span data-stu-id="37784-435">The provided types and information objects should be used only for the type provider mechanism in F#.</span></span> <span data-ttu-id="37784-436">Non sono più in generale utilizzabile come oggetti System. Type.</span><span class="sxs-lookup"><span data-stu-id="37784-436">They aren't more generally usable as System.Type objects.</span></span>
<br />

  4. <span data-ttu-id="37784-437">I costrutti che è possibile utilizzare nelle offerte che definiscono le implementazioni del metodo presentano diverse limitazioni.</span><span class="sxs-lookup"><span data-stu-id="37784-437">The constructs that you can use in quotations that define method implementations have several limitations.</span></span> <span data-ttu-id="37784-438">È possibile fare riferimento al codice sorgente per ProvidedTypes -*versione* per vedere quali costrutti sono supportati nelle offerte.</span><span class="sxs-lookup"><span data-stu-id="37784-438">You can refer to the source code for ProvidedTypes-*Version* to see which constructs are supported in quotations.</span></span>
<br />

- `Type providers must generate output assemblies that are .dll files, not .exe files.`
<br />


## <a name="development-tips"></a><span data-ttu-id="37784-439">Suggerimenti per lo sviluppo</span><span class="sxs-lookup"><span data-stu-id="37784-439">Development Tips</span></span>
<span data-ttu-id="37784-440">I suggerimenti seguenti potrebbero risultare utili durante il processo di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="37784-440">You might find the following tips helpful during the development process.</span></span>


- <span data-ttu-id="37784-441">`Run Two Instances of Visual Studio.`È possibile sviluppare il provider di tipi in un'istanza e testare il provider negli altri perché il test IDE assumerà un blocco file DLL che impedisce il provider di tipi di ricompilazione.</span><span class="sxs-lookup"><span data-stu-id="37784-441">`Run Two Instances of Visual Studio.` You can develop the type provider in one instance and test the provider in the other because the test IDE will take a lock on the .dll file that prevents the type provider from being rebuilt.</span></span> <span data-ttu-id="37784-442">Di conseguenza, è necessario chiudere la seconda istanza di Visual Studio mentre il provider viene compilato nella prima istanza e quindi è necessario aprire nuovamente la seconda istanza dopo il provider di compilazione.</span><span class="sxs-lookup"><span data-stu-id="37784-442">Thus, you must close the second instance of Visual Studio while the provider is built in the first instance, and then you must reopen the second instance after the provider is built.</span></span>
<br />

- <span data-ttu-id="37784-443">`Debug type providers by using invocations of fsc.exe.`È possibile richiamare i provider di tipi con gli strumenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="37784-443">`Debug type providers by using invocations of fsc.exe.` You can invoke type providers by using the following tools:</span></span>
<br />
  - <span data-ttu-id="37784-444">FSC.exe (compilatore della riga di comando di F #)</span><span class="sxs-lookup"><span data-stu-id="37784-444">fsc.exe (The F# command line compiler)</span></span>
<br />

  - <span data-ttu-id="37784-445">fsi.exe (F # Interactive del compilatore)</span><span class="sxs-lookup"><span data-stu-id="37784-445">fsi.exe (The F# Interactive compiler)</span></span>
<br />

  - <span data-ttu-id="37784-446">devenv.exe (Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="37784-446">devenv.exe (Visual Studio)</span></span>
<br />

  <span data-ttu-id="37784-447">È possibile spesso eseguire il debug provider di tipi più facilmente utilizzando fsc.exe su un file di script di test (ad esempio script. fsx).</span><span class="sxs-lookup"><span data-stu-id="37784-447">You can often debug type providers most easily by using fsc.exe on a test script file (for example, script.fsx).</span></span> <span data-ttu-id="37784-448">È possibile avviare un debugger da un prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="37784-448">You can launch a debugger from a command prompt.</span></span>
<br />

```
  devenv /debugexe fsc.exe script.fsx
```

  <span data-ttu-id="37784-449">È possibile utilizzare la registrazione di stampa-stdout.</span><span class="sxs-lookup"><span data-stu-id="37784-449">You can use print-to-stdout logging.</span></span>
<br />


## <a name="see-also"></a><span data-ttu-id="37784-450">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="37784-450">See Also</span></span>
[<span data-ttu-id="37784-451">Provider di tipi</span><span class="sxs-lookup"><span data-stu-id="37784-451">Type Providers</span></span>](index.md)

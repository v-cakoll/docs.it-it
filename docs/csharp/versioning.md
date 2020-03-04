---
title: Controllo delle versioni di C# - Guida a C#
description: Informazioni sul funzionamento del controllo delle versioni in C# e .NET
ms.date: 01/08/2017
ms.technology: csharp-advanced-concepts
ms.assetid: aa8732d7-5cd0-46e1-994a-78017f20d861
ms.openlocfilehash: ee123893ac8baa0a55bdf69ce49fb6fcb87601b4
ms.sourcegitcommit: 43d10ef65f0f1fd6c3b515e363bde11a3fcd8d6d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/03/2020
ms.locfileid: "78240002"
---
# <a name="versioning-in-c"></a><span data-ttu-id="59515-103">Controllo delle versioni in C\#</span><span class="sxs-lookup"><span data-stu-id="59515-103">Versioning in C\#</span></span>

<span data-ttu-id="59515-104">In questa esercitazione si apprenderà il significato del controllo delle versioni in .NET.</span><span class="sxs-lookup"><span data-stu-id="59515-104">In this tutorial you'll learn what versioning means in .NET.</span></span> <span data-ttu-id="59515-105">Verranno anche presentati i fattori da considerare durante il controllo delle versioni della libreria e verrà descritto l'aggiornamento a una nuova versione di una libreria.</span><span class="sxs-lookup"><span data-stu-id="59515-105">You'll also learn the factors to consider when versioning your library as well as upgrading to a new version of a library.</span></span>

## <a name="authoring-libraries"></a><span data-ttu-id="59515-106">Creazione di librerie</span><span class="sxs-lookup"><span data-stu-id="59515-106">Authoring Libraries</span></span>

<span data-ttu-id="59515-107">Gli sviluppatori che hanno creato le librerie .NET per uso pubblico probabilmente si sono trovati in situazioni in cui è necessario distribuire i nuovi aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="59515-107">As a developer who has created .NET libraries for public use, you've most likely been in situations where you have to roll out new updates.</span></span> <span data-ttu-id="59515-108">Le modalità di gestione di questo processo sono molto importanti poiché è necessario garantire che non si verifichino problemi durante la transizione del codice esistente alla nuova versione della libreria.</span><span class="sxs-lookup"><span data-stu-id="59515-108">How you go about this process matters a lot as you need to ensure that there's a seamless transition of existing code to the new version of your library.</span></span> <span data-ttu-id="59515-109">Ecco alcuni aspetti da considerare quando si crea una nuova versione:</span><span class="sxs-lookup"><span data-stu-id="59515-109">Here are several things to consider when creating a new release:</span></span>

### <a name="semantic-versioning"></a><span data-ttu-id="59515-110">Versionamento Semantico</span><span class="sxs-lookup"><span data-stu-id="59515-110">Semantic Versioning</span></span>

<span data-ttu-id="59515-111">[Versionamento Semantico](https://semver.org/) (SemVer per brevità) è una convenzione di denominazione applicata alle versioni della libreria per indicare cardine specifici.</span><span class="sxs-lookup"><span data-stu-id="59515-111">[Semantic versioning](https://semver.org/) (SemVer for short) is a naming convention applied to versions of your library to signify specific milestone events.</span></span>
<span data-ttu-id="59515-112">In teoria, le informazioni sulla versione applicate alla libreria consentono agli sviluppatori di determinare la compatibilità con i progetti che usano versioni precedenti di quella libreria.</span><span class="sxs-lookup"><span data-stu-id="59515-112">Ideally, the version information you give your library should help developers determine the compatibility with their projects that make use of older versions of that same library.</span></span>

<span data-ttu-id="59515-113">L'approccio di base a SemVer è il formato a 3 componenti `MAJOR.MINOR.PATCH`, dove:</span><span class="sxs-lookup"><span data-stu-id="59515-113">The most basic approach to SemVer is the 3 component format `MAJOR.MINOR.PATCH`, where:</span></span>

- <span data-ttu-id="59515-114">`MAJOR` viene incrementato quando si apportano modifiche incompatibili all'API</span><span class="sxs-lookup"><span data-stu-id="59515-114">`MAJOR` is incremented when you make incompatible API changes</span></span>
- <span data-ttu-id="59515-115">`MINOR` viene incrementato quando si aggiungono funzionalità compatibili con le versioni precedenti</span><span class="sxs-lookup"><span data-stu-id="59515-115">`MINOR` is incremented when you add functionality in a backwards-compatible manner</span></span>
- <span data-ttu-id="59515-116">`PATCH` viene incrementato quando si apportano correzioni dei bug compatibili con le versioni precedenti</span><span class="sxs-lookup"><span data-stu-id="59515-116">`PATCH` is incremented when you make backwards-compatible bug fixes</span></span>

<span data-ttu-id="59515-117">Esistono anche dei modi per specificare altri scenari, ad esempio le versioni non definitive, quando si applicano le informazioni sulla versione alla libreria .NET.</span><span class="sxs-lookup"><span data-stu-id="59515-117">There are also ways to specify other scenarios like pre-release versions etc. when applying version information to your .NET library.</span></span>

### <a name="backwards-compatibility"></a><span data-ttu-id="59515-118">Compatibilità con le versioni precedenti</span><span class="sxs-lookup"><span data-stu-id="59515-118">Backwards Compatibility</span></span>

<span data-ttu-id="59515-119">Quando si rilasciano nuove versioni della libreria, la compatibilità con le versioni precedenti probabilmente è una delle principali preoccupazioni.</span><span class="sxs-lookup"><span data-stu-id="59515-119">As you release new versions of your library, backwards compatibility with previous versions will most likely be one of your major concerns.</span></span>
<span data-ttu-id="59515-120">Una nuova versione della libreria è compatibile a livello di codice sorgente con una versione precedente se il codice che dipende dalla versione precedente, quando viene ricompilato, funziona con la nuova versione.</span><span class="sxs-lookup"><span data-stu-id="59515-120">A new version of your library is source compatible with a previous version if code that depends on the previous version can, when recompiled, work with the new version.</span></span> <span data-ttu-id="59515-121">Una nuova versione della libreria è compatibile a livello binario se un'applicazione che dipende dalla versione precedente funziona, senza ricompilazione, con la nuova versione.</span><span class="sxs-lookup"><span data-stu-id="59515-121">A new version of your library is binary compatible if an application that depended on the old version can, without recompilation, work with the new version.</span></span>

<span data-ttu-id="59515-122">Di seguito sono riportati alcuni aspetti da considerare quando si tenta di gestire la compatibilità della libreria con le versioni precedenti:</span><span class="sxs-lookup"><span data-stu-id="59515-122">Here are some things to consider when trying to maintain backwards compatibility with older versions of your library:</span></span>

- <span data-ttu-id="59515-123">Metodi virtuali: quando si trasforma un metodo virtuale in non virtuale nella nuova versione, sarà necessario aggiornare i progetti che eseguono l'override di tale metodo.</span><span class="sxs-lookup"><span data-stu-id="59515-123">Virtual methods: When you make a virtual method non-virtual in your new version it means that projects that override that method will have to be updated.</span></span> <span data-ttu-id="59515-124">Questa è una modifica sostanziale di grande impatto ed è fortemente sconsigliata.</span><span class="sxs-lookup"><span data-stu-id="59515-124">This is a huge breaking change and is strongly discouraged.</span></span>
- <span data-ttu-id="59515-125">Firme del metodo: quando si aggiorna il comportamento di un metodo è necessario modificare anche la firma, è necessario creare un overload in modo tale che il codice che chiama il metodo continuerà a funzionare.</span><span class="sxs-lookup"><span data-stu-id="59515-125">Method signatures: When updating a method behavior requires you to change its signature as well, you should instead create an overload so that code calling into that method will still work.</span></span>
<span data-ttu-id="59515-126">È sempre possibile modificare la firma del metodo precedente per chiamare la firma del nuovo metodo in modo che l'implementazione resti coerente.</span><span class="sxs-lookup"><span data-stu-id="59515-126">You can always manipulate the old method signature to call into the new method signature so that implementation remains consistent.</span></span>
- <span data-ttu-id="59515-127">[Attributo Obsolete](programming-guide/concepts/attributes/common-attributes.md#Obsolete): è possibile usare questo attributo nel codice per specificare le classi o i membri di classe deprecati che potrebbero essere rimossi nelle versioni future.</span><span class="sxs-lookup"><span data-stu-id="59515-127">[Obsolete attribute](programming-guide/concepts/attributes/common-attributes.md#Obsolete): You can use this attribute in your code to specify classes or class members that are deprecated and likely to be removed in future versions.</span></span> <span data-ttu-id="59515-128">Ciò consente di predisporre meglio gli sviluppatori che usano la libreria a eventuali modifiche di rilievo.</span><span class="sxs-lookup"><span data-stu-id="59515-128">This ensures developers utilizing your library are better prepared for breaking changes.</span></span>
- <span data-ttu-id="59515-129">Argomenti di metodo facoltativi: se si rendono obbligatori argomenti di metodo che in precedenza erano facoltativi o si modifica il valore predefinito degli argomenti, tutto il codice che non specifica tali argomenti dovrà essere aggiornato.</span><span class="sxs-lookup"><span data-stu-id="59515-129">Optional Method Arguments: When you make previously optional method arguments compulsory or change their default value then all code that does not supply those arguments will need to be updated.</span></span>

> [!NOTE]
> <span data-ttu-id="59515-130">L'esecuzione di argomenti obbligatori facoltativi dovrebbe avere un effetto minimo, soprattutto se il comportamento del metodo non viene modificato.</span><span class="sxs-lookup"><span data-stu-id="59515-130">Making compulsory arguments optional should have very little effect especially if it doesn't change the method's behavior.</span></span>

<span data-ttu-id="59515-131">Più è facile per gli utenti eseguire l'aggiornamento alla nuova versione della libreria, più rapido sarà l'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="59515-131">The easier you make it for your users to upgrade to the new version of your library, the more likely that they will upgrade sooner.</span></span>

### <a name="application-configuration-file"></a><span data-ttu-id="59515-132">File di configurazione dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="59515-132">Application Configuration File</span></span>

<span data-ttu-id="59515-133">Gli sviluppatori .NET molto probabilmente hanno trovato [il file `app.config`](../framework/configure-apps/file-schema/index.md) nella maggior parte dei tipi di progetto.</span><span class="sxs-lookup"><span data-stu-id="59515-133">As a .NET developer there's a very high chance you've encountered [the `app.config` file](../framework/configure-apps/file-schema/index.md) present in most project types.</span></span>
<span data-ttu-id="59515-134">Questo semplice file di configurazione è in grado di ottimizzare la distribuzione dei nuovi aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="59515-134">This simple configuration file can go a long way into improving the rollout of new updates.</span></span> <span data-ttu-id="59515-135">In genere è consigliabile progettare le librerie in modo che le informazioni che probabilmente cambiano regolarmente vengano archiviate nel file di `app.config`, in questo modo quando tali informazioni vengono aggiornate, il file di configurazione delle versioni precedenti deve essere sostituito con quello nuovo senza la necessità di ricompilare la libreria.</span><span class="sxs-lookup"><span data-stu-id="59515-135">You should generally design your libraries in such a way that information that is likely to change regularly is stored in the `app.config` file, this way when such information is updated, the config file of older versions just needs to be replaced with the new one without the need for recompilation of the library.</span></span>

## <a name="consuming-libraries"></a><span data-ttu-id="59515-136">Elaborazione delle librerie</span><span class="sxs-lookup"><span data-stu-id="59515-136">Consuming Libraries</span></span>

<span data-ttu-id="59515-137">Uno sviluppatore che elabora librerie .NET compilate da altri sviluppatori probabilmente sa che una nuova versione di una libreria potrebbe non essere completamente compatibile con il progetto e che spesso è necessario aggiornare il codice perché funzioni con le modifiche.</span><span class="sxs-lookup"><span data-stu-id="59515-137">As a developer that consumes .NET libraries built by other developers you're most likely aware that a new version of a library might not be fully compatible with your project and you might often find yourself having to update your code to work with those changes.</span></span>

<span data-ttu-id="59515-138">Per fortuna, C# l'ecosistema .NET include funzionalità e tecniche che consentono di aggiornare facilmente l'app per lavorare con le nuove versioni delle librerie che potrebbero introdurre modifiche di rilievo.</span><span class="sxs-lookup"><span data-stu-id="59515-138">Lucky for you, C# and the .NET ecosystem comes with features and techniques that allow us to easily update our app to work with new versions of libraries that might introduce breaking changes.</span></span>

### <a name="assembly-binding-redirection"></a><span data-ttu-id="59515-139">Reindirizzamento dell'associazione di assembly</span><span class="sxs-lookup"><span data-stu-id="59515-139">Assembly Binding Redirection</span></span>

<span data-ttu-id="59515-140">È possibile usare il file *app. config* per aggiornare la versione di una libreria usata dall'app.</span><span class="sxs-lookup"><span data-stu-id="59515-140">You can use the *app.config* file to update the version of a library your app uses.</span></span> <span data-ttu-id="59515-141">Aggiungendo un elemento definito reindirizzamento dell' [*associazione*](../framework/configure-apps/redirect-assembly-versions.md), è possibile usare la nuova versione della libreria senza dover ricompilare l'app.</span><span class="sxs-lookup"><span data-stu-id="59515-141">By adding what is called a [*binding redirect*](../framework/configure-apps/redirect-assembly-versions.md), you can use the new library version without having to recompile your app.</span></span> <span data-ttu-id="59515-142">L'esempio seguente illustra come aggiornare il file *app. config* dell'app per usare la versione `1.0.1` patch di `ReferencedLibrary` invece della versione `1.0.0` in cui è stata originariamente compilata.</span><span class="sxs-lookup"><span data-stu-id="59515-142">The following example shows how you would update your app's *app.config* file to use the `1.0.1` patch version of `ReferencedLibrary` instead of the `1.0.0` version it was originally compiled with.</span></span>

```xml
<dependentAssembly>
    <assemblyIdentity name="ReferencedLibrary" publicKeyToken="32ab4ba45e0a69a1" culture="en-us" />
    <bindingRedirect oldVersion="1.0.0" newVersion="1.0.1" />
</dependentAssembly>
```

> [!NOTE]
> <span data-ttu-id="59515-143">Questo approccio funziona solo se la nuova versione di `ReferencedLibrary` è compatibile a livello binario con l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="59515-143">This approach will only work if the new version of `ReferencedLibrary` is binary compatible with your app.</span></span>
> <span data-ttu-id="59515-144">Vedere la sezione [Compatibilità con le versioni precedenti](#backwards-compatibility) per verificare quando deve essere determinata la compatibilità.</span><span class="sxs-lookup"><span data-stu-id="59515-144">See the [Backwards Compatibility](#backwards-compatibility) section above for changes to look out for when determining compatibility.</span></span>

### <a name="new"></a><span data-ttu-id="59515-145">Nuovo</span><span class="sxs-lookup"><span data-stu-id="59515-145">new</span></span>

<span data-ttu-id="59515-146">Usare il modificatore `new` per nascondere i membri ereditati di una classe di base.</span><span class="sxs-lookup"><span data-stu-id="59515-146">You use the `new` modifier to hide inherited members of a base class.</span></span> <span data-ttu-id="59515-147">In questo modo le classi derivate possono rispondere agli aggiornamenti nelle classi di base.</span><span class="sxs-lookup"><span data-stu-id="59515-147">This is one way derived classes can respond to updates in base classes.</span></span>

<span data-ttu-id="59515-148">Vedere l'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="59515-148">Take the following example:</span></span>

[!code-csharp[Sample usage of the 'new' modifier](~/samples/snippets/csharp/versioning/new/Program.cs#sample)]

<span data-ttu-id="59515-149">**Output**</span><span class="sxs-lookup"><span data-stu-id="59515-149">**Output**</span></span>

```console
A base method
A derived method
```

<span data-ttu-id="59515-150">Nell'esempio precedente si può vedere come `DerivedClass` nasconde il metodo `MyMethod` presente in `BaseClass`.</span><span class="sxs-lookup"><span data-stu-id="59515-150">From the example above you can see how `DerivedClass` hides the `MyMethod` method present in `BaseClass`.</span></span>
<span data-ttu-id="59515-151">Ciò significa che quando una classe di base nella nuova versione di una libreria aggiunge un membro già esistente nella classe derivata, è sufficiente usare il modificatore `new` per il membro della classe derivata per nascondere il membro della classe di base.</span><span class="sxs-lookup"><span data-stu-id="59515-151">This means that when a base class in the new version of a library adds a member that already exists in your derived class, you can simply use the `new` modifier on your derived class member to hide the base class member.</span></span>

<span data-ttu-id="59515-152">Se non si specifica alcun modificatore `new`, una classe derivata nasconderà per impostazione predefinita i membri in conflitto in una classe di base e il codice verrà comunque compilato anche se viene generato un avviso del compilatore.</span><span class="sxs-lookup"><span data-stu-id="59515-152">When no `new` modifier is specified, a derived class will by default hide conflicting members in a base class, although a compiler warning will be generated the code will still compile.</span></span> <span data-ttu-id="59515-153">Ciò significa che la semplice aggiunta di nuovi membri a una classe esistente rende la nuova versione della libreria compatibile sia a livello di codice sorgente che a livello binario con il codice che dipende da essa.</span><span class="sxs-lookup"><span data-stu-id="59515-153">This means that simply adding new members to an existing class makes that new version of your library both source and binary compatible with code that depends on it.</span></span>

### <a name="override"></a><span data-ttu-id="59515-154">override</span><span class="sxs-lookup"><span data-stu-id="59515-154">override</span></span>

<span data-ttu-id="59515-155">Il modificatore `override` indica che un'implementazione derivata estende l'implementazione di un membro della classe di base anziché nasconderlo.</span><span class="sxs-lookup"><span data-stu-id="59515-155">The `override` modifier means a derived implementation extends the implementation of a base class member rather than hides it.</span></span> <span data-ttu-id="59515-156">È necessario che al membro della classe di base sia applicato il modificatore `virtual`.</span><span class="sxs-lookup"><span data-stu-id="59515-156">The base class member needs to have the `virtual` modifier applied to it.</span></span>

[!code-csharp[Sample usage of the 'override' modifier](../../samples/snippets/csharp/versioning/override/Program.cs#sample)]

<span data-ttu-id="59515-157">**Output**</span><span class="sxs-lookup"><span data-stu-id="59515-157">**Output**</span></span>

```console
Base Method One: Method One
Derived Method One: Derived Method One
```

<span data-ttu-id="59515-158">Il modificatore `override` viene valutato in fase di compilazione e il compilatore genera un errore se non trova un membro virtuale di cui eseguire l'override.</span><span class="sxs-lookup"><span data-stu-id="59515-158">The `override` modifier is evaluated at compile time and the compiler will throw an error if it doesn't find a virtual member to override.</span></span>

<span data-ttu-id="59515-159">La conoscenza delle tecniche discusse e la comprensione delle situazioni in cui utilizzarle sono molto utili per facilitare la transizione tra le versioni di una libreria.</span><span class="sxs-lookup"><span data-stu-id="59515-159">Your knowledge of the discussed techniques and your understanding of the situations in which to use them, will go a long way towards easing the transition between versions of a library.</span></span>

---
title: Managed Extensibility Framework (MEF)
description: Esplorare il Managed Extensibility Framework (MEF), che consente agli sviluppatori di applicazioni di individuare e usare le estensioni senza configurazione in .NET 4 o versioni successive.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Managed Extensibility Framework, overview
- MEF, overview
ms.assetid: 6c61b4ec-c6df-4651-80f1-4854f8b14dde
ms.openlocfilehash: 00ed48f2202d4c04039ac264b1fe71474a02432e
ms.sourcegitcommit: 97ce5363efa88179dd76e09de0103a500ca9b659
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/13/2020
ms.locfileid: "86281251"
---
# <a name="managed-extensibility-framework-mef"></a><span data-ttu-id="e9a06-103">Managed Extensibility Framework (MEF)</span><span class="sxs-lookup"><span data-stu-id="e9a06-103">Managed Extensibility Framework (MEF)</span></span>

<span data-ttu-id="e9a06-104">In questo argomento viene fornita una panoramica di Managed Extensibility Framework, introdotto in .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="e9a06-104">This topic provides an overview of the Managed Extensibility Framework that was introduced in the .NET Framework 4.</span></span>

## <a name="what-is-mef"></a><span data-ttu-id="e9a06-105">Che cos'è MEF?</span><span class="sxs-lookup"><span data-stu-id="e9a06-105">What is MEF?</span></span>

<span data-ttu-id="e9a06-106">Il Managed Extensibility Framework o MEF è una libreria per la creazione di applicazioni leggere ed estendibili.</span><span class="sxs-lookup"><span data-stu-id="e9a06-106">The Managed Extensibility Framework or MEF is a library for creating lightweight, and extensible applications.</span></span> <span data-ttu-id="e9a06-107">Consente agli sviluppatori di applicazioni di scoprire e usare le estensioni senza alcuna configurazione.</span><span class="sxs-lookup"><span data-stu-id="e9a06-107">It allows application developers to discover and use extensions with no configuration required.</span></span> <span data-ttu-id="e9a06-108">Consente anche agli sviluppatori di estensioni di incapsulare facilmente il codice ed evitare dipendenze rigide fragili.</span><span class="sxs-lookup"><span data-stu-id="e9a06-108">It also lets extension developers easily encapsulate code and avoid fragile hard dependencies.</span></span> <span data-ttu-id="e9a06-109">Con MEF è possibile riutilizzare le estensioni non solo all'interno ma anche tra le applicazioni.</span><span class="sxs-lookup"><span data-stu-id="e9a06-109">MEF not only allows extensions to be reused within applications, but across applications as well.</span></span>

## <a name="the-problem-of-extensibility"></a><span data-ttu-id="e9a06-110">Il problema di estendibilità</span><span class="sxs-lookup"><span data-stu-id="e9a06-110">The problem of extensibility</span></span>

<span data-ttu-id="e9a06-111">Si immagini di essere l'architetto di un'applicazione di grandi dimensioni che deve fornire supporto per l'estendibilità.</span><span class="sxs-lookup"><span data-stu-id="e9a06-111">Imagine that you are the architect of a large application that must provide support for extensibility.</span></span> <span data-ttu-id="e9a06-112">L'applicazione deve includere un numero potenzialmente grande di componenti più piccoli. Inoltre, la creazione e l'esecuzione di tali componenti deve essere gestita dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="e9a06-112">Your application has to include a potentially large number of smaller components, and is responsible for creating and running them.</span></span>

<span data-ttu-id="e9a06-113">L'approccio più semplice a questo problema è includere i componenti come codice sorgente nell'applicazione e chiamarli direttamente dal codice.</span><span class="sxs-lookup"><span data-stu-id="e9a06-113">The simplest approach to the problem is to include the components as source code in your application, and call them directly from your code.</span></span> <span data-ttu-id="e9a06-114">Tuttavia, questo approccio comporta alcuni inconvenienti ovvi.</span><span class="sxs-lookup"><span data-stu-id="e9a06-114">This has a number of obvious drawbacks.</span></span> <span data-ttu-id="e9a06-115">In particolare, non è possibile aggiungere nuovi componenti senza modificare il codice sorgente. Benché ammissibile, ad esempio, in un'applicazione Web, questo limite risulta inaccettabile in un'applicazione client.</span><span class="sxs-lookup"><span data-stu-id="e9a06-115">Most importantly, you cannot add new components without modifying the source code, a restriction that might be acceptable in, for example, a Web application, but is unworkable in a client application.</span></span> <span data-ttu-id="e9a06-116">Un altro ostacolo ugualmente problematico è che in alcuni casi non si ha accesso al codice sorgente dei componenti, in quanto sviluppati da terze parti. Inoltre, per lo stesso motivo, non è possibile consentire a terze parti di accedere al codice di propria creazione.</span><span class="sxs-lookup"><span data-stu-id="e9a06-116">Equally problematic, you may not have access to the source code for the components, because they might be developed by third parties, and for the same reason you cannot allow them to access yours.</span></span>

<span data-ttu-id="e9a06-117">Un approccio leggermente più sofisticato consiste nel fornire un punto o un'interfaccia di estensione, per consentire la separazione tra l'applicazione e i relativi componenti.</span><span class="sxs-lookup"><span data-stu-id="e9a06-117">A slightly more sophisticated approach would be to provide an extension point or interface, to permit decoupling between the application and its components.</span></span> <span data-ttu-id="e9a06-118">Se si applica questo modello è possibile fornire un'interfaccia implementabile da un componente e un'API per consentire a quest'ultima di interagire con l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="e9a06-118">Under this model, you might provide an interface that a component can implement, and an API to enable it to interact with your application.</span></span> <span data-ttu-id="e9a06-119">Benché elimini l'esigenza di accedere al codice sorgente, questo approccio presenta comunque alcune difficoltà.</span><span class="sxs-lookup"><span data-stu-id="e9a06-119">This solves the problem of requiring source code access, but it still has its own difficulties.</span></span>

<span data-ttu-id="e9a06-120">Poiché l'applicazione è priva di qualsiasi capacità autonoma di individuare i componenti, è comunque necessario indicarle in modo esplicito quali sono i componenti disponibili da caricare.</span><span class="sxs-lookup"><span data-stu-id="e9a06-120">Because the application lacks any capacity for discovering components on its own, it must still be explicitly told which components are available and should be loaded.</span></span> <span data-ttu-id="e9a06-121">Questa operazione in genere viene eseguita registrando in modo esplicito i componenti disponibili in un file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="e9a06-121">This is typically accomplished by explicitly registering the available components in a configuration file.</span></span> <span data-ttu-id="e9a06-122">Ne consegue che garantire la correttezza dei componenti diventa un problema di manutenzione, in particolar modo se la responsabilità dell'esecuzione dell'aggiornamento viene assegnata all'utente finale e non allo sviluppatore.</span><span class="sxs-lookup"><span data-stu-id="e9a06-122">This means that assuring that the components are correct becomes a maintenance issue, particularly if it is the end user and not the developer who is expected to do the updating.</span></span>

<span data-ttu-id="e9a06-123">Inoltre, i componenti sono incapaci di comunicare fra loro, salvo tramite i canali definiti rigidamente appartenenti all'applicazione stessa.</span><span class="sxs-lookup"><span data-stu-id="e9a06-123">In addition, components are incapable of communicating with one another, except through the rigidly defined channels of the application itself.</span></span> <span data-ttu-id="e9a06-124">Se per una determinata esigenza di comunicazione l'architetto dell'applicazione non ha previsto un canale specifico, di solito tale comunicazione risulta impossibile.</span><span class="sxs-lookup"><span data-stu-id="e9a06-124">If the application architect has not anticipated the need for a particular communication, it is usually impossible.</span></span>

<span data-ttu-id="e9a06-125">Infine, gli sviluppatori dei componenti devono accettare una dipendenza rigida in merito all'assembly che contiene l'interfaccia che implementano.</span><span class="sxs-lookup"><span data-stu-id="e9a06-125">Finally, the component developers must accept a hard dependency on what assembly contains the interface they implement.</span></span> <span data-ttu-id="e9a06-126">Ciò ostacola l'uso di un componente in più applicazioni e può inoltre far emergere dei problemi quando si crea un framework di test per i componenti.</span><span class="sxs-lookup"><span data-stu-id="e9a06-126">This makes it difficult for a component to be used in more than one application, and can also create problems when you create a test framework for components.</span></span>

## <a name="what-mef-provides"></a><span data-ttu-id="e9a06-127">Funzionalità di MEF</span><span class="sxs-lookup"><span data-stu-id="e9a06-127">What MEF provides</span></span>

<span data-ttu-id="e9a06-128">Anziché ricorrere alla registrazione esplicita dei componenti disponibili, MEF offre una funzionalità che consente l'individuazione implicita dei componenti, tramite la *composizione*.</span><span class="sxs-lookup"><span data-stu-id="e9a06-128">Instead of this explicit registration of available components, MEF provides a way to discover them implicitly, via *composition*.</span></span> <span data-ttu-id="e9a06-129">Un componente MEF, detto *parte*, specifica in modo dichiarativo sia le proprie dipendenze (dette *importazioni*) sia le funzionalità che rende disponibili (dette *esportazioni*).</span><span class="sxs-lookup"><span data-stu-id="e9a06-129">A MEF component, called a *part*, declaratively specifies both its dependencies (known as *imports*) and what capabilities (known as *exports*) it makes available.</span></span> <span data-ttu-id="e9a06-130">Quando si crea una parte, il motore di composizione di MEF ne soddisfa le importazioni con le risorse disponibili nelle altre parti.</span><span class="sxs-lookup"><span data-stu-id="e9a06-130">When a part is created, the MEF composition engine satisfies its imports with what is available from other parts.</span></span>

<span data-ttu-id="e9a06-131">Questo approccio risolve i problemi discussi nella sezione precedente.</span><span class="sxs-lookup"><span data-stu-id="e9a06-131">This approach solves the problems discussed in the previous section.</span></span> <span data-ttu-id="e9a06-132">Poiché le parti MEF specificano in modo dichiarativo le proprie funzionalità, sono individuabili in fase di esecuzione. Ne consegue che un'applicazione può usare le parti senza dover ricorrere a riferimenti hardcoded oppure a file di configurazione fragili.</span><span class="sxs-lookup"><span data-stu-id="e9a06-132">Because MEF parts declaratively specify their capabilities, they are discoverable at runtime, which means an application can make use of parts without either hard-coded references or fragile configuration files.</span></span> <span data-ttu-id="e9a06-133">MEF consente alle applicazioni di individuare ed esaminare le parti mediante i relativi metadati, senza creare un'istanza o caricare gli assembly di tali parti.</span><span class="sxs-lookup"><span data-stu-id="e9a06-133">MEF allows applications to discover and examine parts by their metadata, without instantiating them or even loading their assemblies.</span></span> <span data-ttu-id="e9a06-134">Di conseguenza, non c'è alcun bisogno di specificare attentamente come e quando caricare le estensioni.</span><span class="sxs-lookup"><span data-stu-id="e9a06-134">As a result, there is no need to carefully specify when and how extensions should be loaded.</span></span>

<span data-ttu-id="e9a06-135">Oltre alle proprie esportazioni fornite, una parte può specificare le proprie importazioni che verranno compilate dalle altre parti.</span><span class="sxs-lookup"><span data-stu-id="e9a06-135">In addition to its provided exports, a part can specify its imports, which will be filled by other parts.</span></span> <span data-ttu-id="e9a06-136">Questo approccio rende non solo possibile ma persino facile la comunicazione fra le parti. Inoltre, consente un buon factoring del codice.</span><span class="sxs-lookup"><span data-stu-id="e9a06-136">This makes communication among parts not only possible, but easy, and allows for good factoring of code.</span></span> <span data-ttu-id="e9a06-137">Ad esempio, i servizi comuni a molti componenti possono essere organizzati in una parte distinta e quindi essere modificati o sostituiti facilmente.</span><span class="sxs-lookup"><span data-stu-id="e9a06-137">For example, services common to many components can be factored into a separate part and easily modified or replaced.</span></span>

<span data-ttu-id="e9a06-138">Poiché non è richiesta alcuna dipendenza rigida da un determinato assembly dell'applicazione, il modello MEF consente il riutilizzo delle estensioni da un'applicazione a un'altra.</span><span class="sxs-lookup"><span data-stu-id="e9a06-138">Because the MEF model requires no hard dependency on a particular application assembly, it allows extensions to be reused from application to application.</span></span> <span data-ttu-id="e9a06-139">Ciò semplifica inoltre lo sviluppo di un test harness, indipendente dell'applicazione, per testare i componenti dell'estensione.</span><span class="sxs-lookup"><span data-stu-id="e9a06-139">This also makes it easy to develop a test harness, independent of the application, to test extension components.</span></span>

<span data-ttu-id="e9a06-140">Un'applicazione estensibile scritta tramite MEF dichiara un'importazione che può essere compilata da componenti di estensione. Inoltre, può dichiarare esportazioni per esporre alle estensioni i servizi dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="e9a06-140">An extensible application written by using MEF declares an import that can be filled by extension components, and may also declare exports in order to expose application services to extensions.</span></span> <span data-ttu-id="e9a06-141">Ogni componente di estensione dichiara un'esportazione e può anche dichiarare importazioni.</span><span class="sxs-lookup"><span data-stu-id="e9a06-141">Each extension component declares an export, and may also declare imports.</span></span> <span data-ttu-id="e9a06-142">In questo modo, i componenti di estensione stessi risultano automaticamente estensibili.</span><span class="sxs-lookup"><span data-stu-id="e9a06-142">In this way, extension components themselves are automatically extensible.</span></span>

## <a name="where-mef-is-available"></a><span data-ttu-id="e9a06-143">Dove MEF è disponibile</span><span class="sxs-lookup"><span data-stu-id="e9a06-143">Where MEF is available</span></span>

<span data-ttu-id="e9a06-144">MEF è parte integrante di .NET Framework 4 ed è disponibile in tutti i contesti in cui si usa .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e9a06-144">MEF is an integral part of the .NET Framework 4, and is available wherever the .NET Framework is used.</span></span> <span data-ttu-id="e9a06-145">È possibile usare MEF nelle applicazioni client se usano Windows Form, WPF o qualsiasi altra tecnologia oppure nelle applicazioni server che usano ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="e9a06-145">You can use MEF in your client applications, whether they use Windows Forms, WPF, or any other technology, or in server applications that use ASP.NET.</span></span>

## <a name="mef-and-maf"></a><span data-ttu-id="e9a06-146">MEF e MAF</span><span class="sxs-lookup"><span data-stu-id="e9a06-146">MEF and MAF</span></span>

<span data-ttu-id="e9a06-147">Nelle versioni precedenti di .NET Framework è stato introdotto Managed Add-in Framework (MAF), progettato per consentire alle applicazioni di isolare e gestire le estensioni.</span><span class="sxs-lookup"><span data-stu-id="e9a06-147">Previous versions of the .NET Framework introduced the Managed Add-in Framework (MAF), designed to allow applications to isolate and manage extensions.</span></span> <span data-ttu-id="e9a06-148">Rispetto a MEF, MAF si concentra su un livello leggermente più elevato, in particolare sull'isolamento delle estensioni e sul caricamento e scaricamento degli assembly. MEF si concentra invece su individuazione, estensibilità e portabilità.</span><span class="sxs-lookup"><span data-stu-id="e9a06-148">The focus of MAF is slightly higher-level than MEF, concentrating on extension isolation and assembly loading and unloading, while MEF's focus is on discoverability, extensibility, and portability.</span></span> <span data-ttu-id="e9a06-149">I due framework interoperano agevolmente e una stessa applicazione può trarre vantaggio da entrambi.</span><span class="sxs-lookup"><span data-stu-id="e9a06-149">The two frameworks interoperate smoothly, and a single application can take advantage of both.</span></span>

## <a name="simplecalculator-an-example-application"></a><span data-ttu-id="e9a06-150">SimpleCalculator: applicazione di esempio</span><span class="sxs-lookup"><span data-stu-id="e9a06-150">SimpleCalculator: An example application</span></span>

<span data-ttu-id="e9a06-151">Il modo più semplice per vedere le potenzialità di MEF è compilare una semplice applicazione MEF.</span><span class="sxs-lookup"><span data-stu-id="e9a06-151">The simplest way to see what MEF can do is to build a simple MEF application.</span></span> <span data-ttu-id="e9a06-152">In questo esempio viene compilata una calcolatrice molto semplice denominata SimpleCalculator.</span><span class="sxs-lookup"><span data-stu-id="e9a06-152">In this example, you build a very simple calculator named SimpleCalculator.</span></span> <span data-ttu-id="e9a06-153">L'obiettivo di SimpleCalculator è creare un'applicazione console che accetta comandi aritmetici di base, nel formato "5+3" o "6-2", e restituisce le risposte corrette.</span><span class="sxs-lookup"><span data-stu-id="e9a06-153">The goal of SimpleCalculator is to create a console application that accepts basic arithmetic commands, in the form "5+3" or "6-2", and returns the correct answers.</span></span> <span data-ttu-id="e9a06-154">Tramite MEF sarà possibile aggiungere nuovi operatori senza modificare il codice dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="e9a06-154">Using MEF, you'll be able to add new operators without changing the application code.</span></span>

<span data-ttu-id="e9a06-155">Per scaricare il codice completo per questo esempio, vedere l' [esempio SimpleCalculator (Visual Basic)](https://docs.microsoft.com/samples/dotnet/samples/simple-calculator-vb/).</span><span class="sxs-lookup"><span data-stu-id="e9a06-155">To download the complete code for this example, see the [SimpleCalculator sample (Visual Basic)](https://docs.microsoft.com/samples/dotnet/samples/simple-calculator-vb/).</span></span>

> [!NOTE]
> <span data-ttu-id="e9a06-156">Più che fornire uno scenario di uso realistico, lo scopo di SimpleCalculator è dimostrare i concetti e la sintassi di MEF.</span><span class="sxs-lookup"><span data-stu-id="e9a06-156">The purpose of SimpleCalculator is to demonstrate the concepts and syntax of MEF, rather than to necessarily provide a realistic scenario for its use.</span></span> <span data-ttu-id="e9a06-157">Molte delle applicazioni in grado di sfruttare al meglio la potenza di MEF sono più complesse di SimpleCalculator.</span><span class="sxs-lookup"><span data-stu-id="e9a06-157">Many of the applications that would benefit most from the power of MEF are more complex than SimpleCalculator.</span></span> <span data-ttu-id="e9a06-158">Per altri esempi dettagliati, vedere [Managed Extensibility Framework](https://github.com/MicrosoftArchive/mef) su GitHub.</span><span class="sxs-lookup"><span data-stu-id="e9a06-158">For more extensive examples, see the [Managed Extensibility Framework](https://github.com/MicrosoftArchive/mef) on GitHub.</span></span>

- <span data-ttu-id="e9a06-159">Per iniziare, creare un nuovo progetto di applicazione console in Visual Studio e denominarlo `SimpleCalculator`.</span><span class="sxs-lookup"><span data-stu-id="e9a06-159">To start, in Visual Studio, create a new Console Application project and name it `SimpleCalculator`.</span></span>

- <span data-ttu-id="e9a06-160">Aggiungere un riferimento all' `System.ComponentModel.Composition` assembly in cui si trova MEF.</span><span class="sxs-lookup"><span data-stu-id="e9a06-160">Add a reference to the `System.ComponentModel.Composition` assembly, where MEF resides.</span></span>

- <span data-ttu-id="e9a06-161">Aprire *Module1. vb* o *Program.cs* e aggiungere `Imports` `using` istruzioni o per `System.ComponentModel.Composition` e `System.ComponentModel.Composition.Hosting` .</span><span class="sxs-lookup"><span data-stu-id="e9a06-161">Open *Module1.vb* or *Program.cs* and add `Imports` or `using` statements for `System.ComponentModel.Composition` and `System.ComponentModel.Composition.Hosting`.</span></span> <span data-ttu-id="e9a06-162">Questi due spazi dei nomi contengono i tipi MEF che saranno necessari per sviluppare un'applicazione estensibile.</span><span class="sxs-lookup"><span data-stu-id="e9a06-162">These two namespaces contain MEF types you will need to develop an extensible application.</span></span>

- <span data-ttu-id="e9a06-163">Se si usa Visual Basic, aggiungere la parola chiave `Public` alla riga in cui viene dichiarato il modulo `Module1`.</span><span class="sxs-lookup"><span data-stu-id="e9a06-163">If you're using Visual Basic, add the `Public` keyword to the line that declares the `Module1` module.</span></span>

## <a name="composition-container-and-catalogs"></a><span data-ttu-id="e9a06-164">Contenitore e cataloghi di composizione</span><span class="sxs-lookup"><span data-stu-id="e9a06-164">Composition container and catalogs</span></span>

<span data-ttu-id="e9a06-165">La base del modello di composizione d MEF è il *contenitore di composizione*. Questo contenitore contiene tutte le parti disponibili ed esegue la composizione,</span><span class="sxs-lookup"><span data-stu-id="e9a06-165">The core of the MEF composition model is the *composition container*, which contains all the parts available and performs composition.</span></span> <span data-ttu-id="e9a06-166">ovvero l'abbinamento tra importazioni ed esportazioni.</span><span class="sxs-lookup"><span data-stu-id="e9a06-166">Composition is the matching up of imports to exports.</span></span> <span data-ttu-id="e9a06-167">Il tipo più comune di contenitore di composizione è <xref:System.ComponentModel.Composition.Hosting.CompositionContainer>, usato anche per SimpleCalculator.</span><span class="sxs-lookup"><span data-stu-id="e9a06-167">The most common type of composition container is <xref:System.ComponentModel.Composition.Hosting.CompositionContainer>, and you'll use this for SimpleCalculator.</span></span>

<span data-ttu-id="e9a06-168">Se si usa Visual Basic, aggiungere una classe pubblica denominata `Program` in *Module1. vb*.</span><span class="sxs-lookup"><span data-stu-id="e9a06-168">If you're using Visual Basic, add a public class named `Program` in *Module1.vb*.</span></span>

<span data-ttu-id="e9a06-169">Aggiungere la riga seguente alla `Program` classe in *Module1. vb* o *Program.cs*:</span><span class="sxs-lookup"><span data-stu-id="e9a06-169">Add the following line to the `Program` class in *Module1.vb* or *Program.cs*:</span></span>

```vb
Dim _container As CompositionContainer
```

```csharp
private CompositionContainer _container;
```

<span data-ttu-id="e9a06-170">Per individuare le parti a cui possono accedere, i contenitori di composizione si avvalgono di un *catalogo*.</span><span class="sxs-lookup"><span data-stu-id="e9a06-170">In order to discover the parts available to it, the composition containers makes use of a *catalog*.</span></span> <span data-ttu-id="e9a06-171">Un catalogo è un oggetto che rende disponibili le parti individuate in un'origine.</span><span class="sxs-lookup"><span data-stu-id="e9a06-171">A catalog is an object that makes available parts discovered from some source.</span></span> <span data-ttu-id="e9a06-172">MEF fornisce cataloghi per individuare le parti disponibili in un assembly, una directory o un tipo fornito.</span><span class="sxs-lookup"><span data-stu-id="e9a06-172">MEF provides catalogs to discover parts from a provided type, an assembly, or a directory.</span></span> <span data-ttu-id="e9a06-173">Gli sviluppatori di applicazioni possono creare facilmente nuovi cataloghi per individuare parti disponibili in altre origini, ad esempio un servizio Web.</span><span class="sxs-lookup"><span data-stu-id="e9a06-173">Application developers can easily create new catalogs to discover parts from other sources, such as a Web service.</span></span>

<span data-ttu-id="e9a06-174">Aggiungere il costruttore seguente alla classe `Program`:</span><span class="sxs-lookup"><span data-stu-id="e9a06-174">Add the following constructor to the `Program` class:</span></span>

```vb
Public Sub New()
    ' An aggregate catalog that combines multiple catalogs.
     Dim catalog = New AggregateCatalog()

    ' Adds all the parts found in the same assembly as the Program class.
    catalog.Catalogs.Add(New AssemblyCatalog(GetType(Program).Assembly))

    ' Create the CompositionContainer with the parts in the catalog.
    _container = New CompositionContainer(catalog)

    ' Fill the imports of this object.
    Try
        _container.ComposeParts(Me)
    Catch ex As CompositionException
        Console.WriteLine(ex.ToString)
    End Try
End Sub
```

```csharp
private Program()
{
    // An aggregate catalog that combines multiple catalogs.
    var catalog = new AggregateCatalog();
    // Adds all the parts found in the same assembly as the Program class.
    catalog.Catalogs.Add(new AssemblyCatalog(typeof(Program).Assembly));

    // Create the CompositionContainer with the parts in the catalog.
    _container = new CompositionContainer(catalog);

    // Fill the imports of this object.
    try
    {
        this._container.ComposeParts(this);
    }
    catch (CompositionException compositionException)
    {
        Console.WriteLine(compositionException.ToString());
   }
}
```

<span data-ttu-id="e9a06-175">La chiamata a <xref:System.ComponentModel.Composition.AttributedModelServices.ComposeParts%2A> indica al contenitore di composizione di comporre un set specifico di parti, in questo caso l'istanza corrente di `Program`.</span><span class="sxs-lookup"><span data-stu-id="e9a06-175">The call to <xref:System.ComponentModel.Composition.AttributedModelServices.ComposeParts%2A> tells the composition container to compose a specific set of parts, in this case the current instance of `Program`.</span></span> <span data-ttu-id="e9a06-176">Tuttavia, a questo punto non si verificherà nulla, poiché `Program` non presenta importazioni da compilare.</span><span class="sxs-lookup"><span data-stu-id="e9a06-176">At this point, however, nothing will happen, since `Program` has no imports to fill.</span></span>

## <a name="imports-and-exports-with-attributes"></a><span data-ttu-id="e9a06-177">Importazioni ed esportazioni con attributi</span><span class="sxs-lookup"><span data-stu-id="e9a06-177">Imports and Exports with attributes</span></span>

<span data-ttu-id="e9a06-178">Prima di tutto, `Program` deve importare una calcolatrice.</span><span class="sxs-lookup"><span data-stu-id="e9a06-178">First, you have `Program` import a calculator.</span></span> <span data-ttu-id="e9a06-179">Ciò consente di separare le problematiche dell'interfaccia utente, ad esempio l'input e l'output della console che andrà in `Program`, dalla logica della calcolatrice.</span><span class="sxs-lookup"><span data-stu-id="e9a06-179">This allows the separation of user interface concerns, such as the console input and output that will go into `Program`, from the logic of the calculator.</span></span>

<span data-ttu-id="e9a06-180">Aggiungere il codice seguente alla classe `Program`:</span><span class="sxs-lookup"><span data-stu-id="e9a06-180">Add the following code to the `Program` class:</span></span>

```vb
<Import(GetType(ICalculator))>
Public Property calculator As ICalculator
```

```csharp
[Import(typeof(ICalculator))]
public ICalculator calculator;
```

<span data-ttu-id="e9a06-181">La dichiarazione dell'oggetto `calculator` non è insolita, ma è associata all'attributo <xref:System.ComponentModel.Composition.ImportAttribute>.</span><span class="sxs-lookup"><span data-stu-id="e9a06-181">Notice that the declaration of the `calculator` object is not unusual, but that it is decorated with the <xref:System.ComponentModel.Composition.ImportAttribute> attribute.</span></span> <span data-ttu-id="e9a06-182">Questo attributo dichiara un elemento di importazione, ovvero un elemento che verrà fornito dal motore di composizione quando l'oggetto viene composto.</span><span class="sxs-lookup"><span data-stu-id="e9a06-182">This attribute declares something to be an import; that is, it will be filled by the composition engine when the object is composed.</span></span>

<span data-ttu-id="e9a06-183">Ogni importazione presenta un *contratto* che determina le esportazioni a cui verrà abbinata.</span><span class="sxs-lookup"><span data-stu-id="e9a06-183">Every import has a *contract*, which determines what exports it will be matched with.</span></span> <span data-ttu-id="e9a06-184">Il contratto può essere una stringa specificata in modo esplicito oppure può essere generato automaticamente da MEF a partire da un tipo specificato, in questo caso l'interfaccia `ICalculator`.</span><span class="sxs-lookup"><span data-stu-id="e9a06-184">The contract can be an explicitly specified string, or it can be automatically generated by MEF from a given type, in this case the interface `ICalculator`.</span></span> <span data-ttu-id="e9a06-185">Qualsiasi esportazione dichiarata con un contratto corrispondente verrà usata per soddisfare questa importazione.</span><span class="sxs-lookup"><span data-stu-id="e9a06-185">Any export declared with a matching contract will fulfill this import.</span></span> <span data-ttu-id="e9a06-186">Benché il tipo dell'oggetto `calculator` sia effettivamente `ICalculator`, non si tratta di una condizione obbligatoria.</span><span class="sxs-lookup"><span data-stu-id="e9a06-186">Note that while the type of the `calculator` object is in fact `ICalculator`, this is not required.</span></span> <span data-ttu-id="e9a06-187">Il contratto è indipendente dal tipo dell'oggetto di importazione.</span><span class="sxs-lookup"><span data-stu-id="e9a06-187">The contract is independent from the type of the importing object.</span></span> <span data-ttu-id="e9a06-188">In questo caso, è possibile escludere l'oggetto `typeof(ICalculator)`.</span><span class="sxs-lookup"><span data-stu-id="e9a06-188">(In this case, you could leave out the `typeof(ICalculator)`.</span></span> <span data-ttu-id="e9a06-189">Se non specificato in modo esplicito, MEF presuppone automaticamente che il contratto si basi sul tipo di importazione.</span><span class="sxs-lookup"><span data-stu-id="e9a06-189">MEF will automatically assume the contract to be based on the type of the import unless you specify it explicitly.)</span></span>

<span data-ttu-id="e9a06-190">Aggiungere questa interfaccia molto semplice al modulo o allo spazio dei nomi `SimpleCalculator`:</span><span class="sxs-lookup"><span data-stu-id="e9a06-190">Add this very simple interface to the module or `SimpleCalculator` namespace:</span></span>

```vb
Public Interface ICalculator
    Function Calculate(input As String) As String
End Interface
```

```csharp
public interface ICalculator
{
    String Calculate(String input);
}
```

<span data-ttu-id="e9a06-191">Ora che è stato definito `ICalculator`, è necessaria una classe che lo implementi.</span><span class="sxs-lookup"><span data-stu-id="e9a06-191">Now that you have defined `ICalculator`, you need a class that implements it.</span></span> <span data-ttu-id="e9a06-192">Aggiungere la classe seguente al modulo o allo spazio dei nomi `SimpleCalculator`:</span><span class="sxs-lookup"><span data-stu-id="e9a06-192">Add the following class to the module or `SimpleCalculator` namespace:</span></span>

```vb
<Export(GetType(ICalculator))>
Public Class MySimpleCalculator
   Implements ICalculator

End Class
```

```csharp
[Export(typeof(ICalculator))]
class MySimpleCalculator : ICalculator
{

}
```

<span data-ttu-id="e9a06-193">Questa è l'esportazione che verrà abbinata all'importazione in `Program`.</span><span class="sxs-lookup"><span data-stu-id="e9a06-193">Here is the export that will match the import in `Program`.</span></span> <span data-ttu-id="e9a06-194">Affinché l'esportazione corrisponda all'importazione, è necessario che dispongano dello stesso contratto.</span><span class="sxs-lookup"><span data-stu-id="e9a06-194">In order for the export to match the import, the export must have the same contract.</span></span> <span data-ttu-id="e9a06-195">L'esportazione nel contesto di un contratto basato su `typeof(MySimpleCalculator)` darebbe luogo a una mancata corrispondenza e l'importazione non verrebbe compilata. Il contratto deve corrispondere in modo esatto.</span><span class="sxs-lookup"><span data-stu-id="e9a06-195">Exporting under a contract based on `typeof(MySimpleCalculator)` would produce a mismatch, and the import would not be filled; the contract needs to match exactly.</span></span>

<span data-ttu-id="e9a06-196">Poiché il contenitore di composizione sarà popolato con tutte le parti disponibili in questo assembly, la parte `MySimpleCalculator` sarà disponibile.</span><span class="sxs-lookup"><span data-stu-id="e9a06-196">Since the composition container will be populated with all the parts available in this assembly, the `MySimpleCalculator` part will be available.</span></span> <span data-ttu-id="e9a06-197">Quando il costruttore di `Program` esegue la composizione nell'oggetto `Program`, la relativa importazione verrà compilata con un oggetto `MySimpleCalculator` che verrà creato a tale scopo.</span><span class="sxs-lookup"><span data-stu-id="e9a06-197">When the constructor for `Program` performs composition on the `Program` object, its import will be filled with a `MySimpleCalculator` object, which will be created for that purpose.</span></span>

<span data-ttu-id="e9a06-198">Al livello dell'interfaccia utente (`Program`) non occorrono altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="e9a06-198">The user interface layer (`Program`) does not need to know anything else.</span></span> <span data-ttu-id="e9a06-199">È quindi possibile compilare il resto della logica dell'interfaccia utente nel metodo `Main`.</span><span class="sxs-lookup"><span data-stu-id="e9a06-199">You can therefore fill in the rest of the user interface logic in the `Main` method.</span></span>

<span data-ttu-id="e9a06-200">Aggiungere al metodo `Main` il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="e9a06-200">Add the following code to the `Main` method:</span></span>

```vb
Sub Main()
    ' Composition is performed in the constructor.
    Dim p As New Program()
    Dim s As String
    Console.WriteLine("Enter Command:")
    While (True)
        s = Console.ReadLine()
        Console.WriteLine(p.calculator.Calculate(s))
    End While
End Sub
```

```csharp
static void Main(string[] args)
{
    // Composition is performed in the constructor.
    var p = new Program();
    string s;
    Console.WriteLine("Enter Command:");
    while (true)
    {
        s = Console.ReadLine();
        Console.WriteLine(p.calculator.Calculate(s));
    }
}
```

 <span data-ttu-id="e9a06-201">Questo codice legge semplicemente una riga di input e chiama la funzione `Calculate` di `ICalculator` nel risultato, che quindi scrive nella console.</span><span class="sxs-lookup"><span data-stu-id="e9a06-201">This code simply reads a line of input and calls the `Calculate` function of `ICalculator` on the result, which it writes back to the console.</span></span> <span data-ttu-id="e9a06-202">Questo è tutto il codice necessario in `Program`.</span><span class="sxs-lookup"><span data-stu-id="e9a06-202">That is all the code you need in `Program`.</span></span> <span data-ttu-id="e9a06-203">Tutte le altre operazioni avranno luogo nelle parti.</span><span class="sxs-lookup"><span data-stu-id="e9a06-203">All the rest of the work will happen in the parts.</span></span>

## <a name="further-imports-and-importmany"></a><span data-ttu-id="e9a06-204">Altre importazioni e ImportMany</span><span class="sxs-lookup"><span data-stu-id="e9a06-204">Further Imports and ImportMany</span></span>

<span data-ttu-id="e9a06-205">Per essere estensibile, SimpleCalculator deve importare un elenco di operazioni.</span><span class="sxs-lookup"><span data-stu-id="e9a06-205">In order for SimpleCalculator to be extensible, it needs to import a list of operations.</span></span> <span data-ttu-id="e9a06-206">Un attributo <xref:System.ComponentModel.Composition.ImportAttribute> ordinario viene compilato da un solo <xref:System.ComponentModel.Composition.ExportAttribute>.</span><span class="sxs-lookup"><span data-stu-id="e9a06-206">An ordinary <xref:System.ComponentModel.Composition.ImportAttribute> attribute is filled by one and only one <xref:System.ComponentModel.Composition.ExportAttribute>.</span></span> <span data-ttu-id="e9a06-207">Se ne è disponibile più di uno, il motore di composizione genera un errore.</span><span class="sxs-lookup"><span data-stu-id="e9a06-207">If more than one is available, the composition engine produces an error.</span></span> <span data-ttu-id="e9a06-208">Per creare un'importazione che può essere compilata da qualsiasi numero di esportazioni, è possibile usare l'attributo <xref:System.ComponentModel.Composition.ImportManyAttribute>.</span><span class="sxs-lookup"><span data-stu-id="e9a06-208">To create an import that can be filled by any number of exports, you can use the <xref:System.ComponentModel.Composition.ImportManyAttribute> attribute.</span></span>

<span data-ttu-id="e9a06-209">Aggiungere la proprietà operations seguente alla classe `MySimpleCalculator`:</span><span class="sxs-lookup"><span data-stu-id="e9a06-209">Add the following operations property to the `MySimpleCalculator` class:</span></span>

```vb
<ImportMany()>
Public Property operations As IEnumerable(Of Lazy(Of IOperation, IOperationData))
```

```csharp
[ImportMany]
IEnumerable<Lazy<IOperation, IOperationData>> operations;
```

<span data-ttu-id="e9a06-210"><xref:System.Lazy%602> è un tipo fornito da MEF per contenere riferimenti indiretti alle esportazioni.</span><span class="sxs-lookup"><span data-stu-id="e9a06-210"><xref:System.Lazy%602> is a type provided by MEF to hold indirect references to exports.</span></span> <span data-ttu-id="e9a06-211">Qui, oltre all'oggetto esportato stesso, si ottengono anche *metadati di esportazione* ovvero informazioni che descrivono l'oggetto esportato.</span><span class="sxs-lookup"><span data-stu-id="e9a06-211">Here, in addition to the exported object itself, you also get *export metadata*, or information that describes the exported object.</span></span> <span data-ttu-id="e9a06-212">Ciascun <xref:System.Lazy%602> contiene un oggetto `IOperation` che rappresenta un'operazione effettiva e un oggetto `IOperationData` che rappresenta i relativi metadati.</span><span class="sxs-lookup"><span data-stu-id="e9a06-212">Each <xref:System.Lazy%602> contains an `IOperation` object, representing an actual operation, and an `IOperationData` object, representing its metadata.</span></span>

<span data-ttu-id="e9a06-213">Aggiungere le interfacce semplici seguenti al modulo o allo spazio dei nomi `SimpleCalculator`:</span><span class="sxs-lookup"><span data-stu-id="e9a06-213">Add the following simple interfaces to the module or `SimpleCalculator` namespace:</span></span>

```vb
Public Interface IOperation
    Function Operate(left As Integer, right As Integer) As Integer
End Interface

Public Interface IOperationData
    ReadOnly Property Symbol As Char
End Interface
```

```csharp
public interface IOperation
{
     int Operate(int left, int right);
}

public interface IOperationData
{
    Char Symbol { get; }
}
```

 <span data-ttu-id="e9a06-214">In questo caso, i metadati per ogni operazione sono il simbolo che rappresenta tale operazione, ad esempio +,-, \* e così via.</span><span class="sxs-lookup"><span data-stu-id="e9a06-214">In this case, the metadata for each operation is the symbol that represents that operation, such as +, -, \*, and so on.</span></span> <span data-ttu-id="e9a06-215">Per rendere disponibile l'operazione di addizione, aggiungere la classe seguente al modulo o allo spazio dei nomi `SimpleCalculator`:</span><span class="sxs-lookup"><span data-stu-id="e9a06-215">To make the addition operation available, add the following class to the module or `SimpleCalculator` namespace:</span></span>

```vb
<Export(GetType(IOperation))>
<ExportMetadata("Symbol", "+"c)>
Public Class Add
    Implements IOperation

    Public Function Operate(left As Integer, right As Integer) As Integer Implements IOperation.Operate
        Return left + right
    End Function
End Class
```

```csharp
[Export(typeof(IOperation))]
[ExportMetadata("Symbol", '+')]
class Add: IOperation
{
    public int Operate(int left, int right)
    {
        return left + right;
    }
}
```

<span data-ttu-id="e9a06-216">Il funzionamento dell'attributo <xref:System.ComponentModel.Composition.ExportAttribute> non è stato modificato.</span><span class="sxs-lookup"><span data-stu-id="e9a06-216">The <xref:System.ComponentModel.Composition.ExportAttribute> attribute functions as it did before.</span></span> <span data-ttu-id="e9a06-217">L'attributo <xref:System.ComponentModel.Composition.ExportMetadataAttribute> allega metadati, nel formato di una coppia nome-valore, a tale esportazione.</span><span class="sxs-lookup"><span data-stu-id="e9a06-217">The <xref:System.ComponentModel.Composition.ExportMetadataAttribute> attribute attaches metadata, in the form of a name-value pair, to that export.</span></span> <span data-ttu-id="e9a06-218">Mentre la classe `Add` implementa `IOperation`, una classe che implementa `IOperationData` non viene definita in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="e9a06-218">While the `Add` class implements `IOperation`, a class that implements `IOperationData` is not explicitly defined.</span></span> <span data-ttu-id="e9a06-219">Tale classe viene invece creata implicitamente da MEF con proprietà basate sui nomi dei metadati forniti.</span><span class="sxs-lookup"><span data-stu-id="e9a06-219">Instead, a class is implicitly created by MEF with properties based on the names of the metadata provided.</span></span> <span data-ttu-id="e9a06-220">Questo è uno dei vari modi per accedere ai metadati in MEF.</span><span class="sxs-lookup"><span data-stu-id="e9a06-220">(This is one of several ways to access metadata in MEF.)</span></span>

<span data-ttu-id="e9a06-221">La composizione in MEF è *ricorsiva*.</span><span class="sxs-lookup"><span data-stu-id="e9a06-221">Composition in MEF is *recursive*.</span></span> <span data-ttu-id="e9a06-222">L'oggetto `Program` è stato composto in modo esplicito e ha importato un oggetto `ICalculator` che è risultato essere di tipo `MySimpleCalculator`.</span><span class="sxs-lookup"><span data-stu-id="e9a06-222">You explicitly composed the `Program` object, which imported an `ICalculator` that turned out to be of type `MySimpleCalculator`.</span></span> <span data-ttu-id="e9a06-223">`MySimpleCalculator`, a sua volta, importa un insieme di oggetti `IOperation` e tale importazione viene compilata quando viene creato `MySimpleCalculator`, contemporaneamente alle importazioni di `Program`.</span><span class="sxs-lookup"><span data-stu-id="e9a06-223">`MySimpleCalculator`, in turn, imports a collection of `IOperation` objects, and that import will be filled when `MySimpleCalculator` is created, at the same time as the imports of `Program`.</span></span> <span data-ttu-id="e9a06-224">Se la classe `Add` avesse dichiarato un'altra importazione, sarebbe stato necessario compilare anch'essa e così via.</span><span class="sxs-lookup"><span data-stu-id="e9a06-224">If the `Add` class declared a further import, that too would have to be filled, and so on.</span></span> <span data-ttu-id="e9a06-225">Qualsiasi importazione non compilata comporta un errore di composizione.</span><span class="sxs-lookup"><span data-stu-id="e9a06-225">Any import left unfilled results in a composition error.</span></span> <span data-ttu-id="e9a06-226">Tuttavia, è possibile dichiarare le importazioni come facoltative oppure assegnare loro valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="e9a06-226">(It is possible, however, to declare imports to be optional or to assign them default values.)</span></span>

## <a name="calculator-logic"></a><span data-ttu-id="e9a06-227">Logica della calcolatrice</span><span class="sxs-lookup"><span data-stu-id="e9a06-227">Calculator Logic</span></span>

<span data-ttu-id="e9a06-228">Dopo aver creato queste parti, l'unica operazione che resta da eseguire è creare la logica della calcolatrice stessa.</span><span class="sxs-lookup"><span data-stu-id="e9a06-228">With these parts in place, all that remains is the calculator logic itself.</span></span> <span data-ttu-id="e9a06-229">Aggiungere il codice seguente nella classe `MySimpleCalculator` per implementare il metodo `Calculate`:</span><span class="sxs-lookup"><span data-stu-id="e9a06-229">Add the following code in the `MySimpleCalculator` class to implement the `Calculate` method:</span></span>

```vb
Public Function Calculate(input As String) As String Implements ICalculator.Calculate
    Dim left, right As Integer
    Dim operation As Char
    ' Finds the operator.
    Dim fn = FindFirstNonDigit(input)
    If fn < 0 Then
        Return "Could not parse command."
    End If
    operation = input(fn)
    Try
        ' Separate out the operands.
        left = Integer.Parse(input.Substring(0, fn))
        right = Integer.Parse(input.Substring(fn + 1))
    Catch ex As Exception
        Return "Could not parse command."
    End Try
    For Each i As Lazy(Of IOperation, IOperationData) In operations
        If i.Metadata.symbol = operation Then
            Return i.Value.Operate(left, right).ToString()
        End If
    Next
    Return "Operation not found!"
End Function
```

```csharp
public String Calculate(string input)
{
    int left;
    int right;
    char operation;
    // Finds the operator.
    int fn = FindFirstNonDigit(input);
    if (fn < 0) return "Could not parse command.";

    try
    {
        // Separate out the operands.
        left = int.Parse(input.Substring(0, fn));
        right = int.Parse(input.Substring(fn + 1));
    }
    catch
    {
        return "Could not parse command.";
    }

    operation = input[fn];

    foreach (Lazy<IOperation, IOperationData> i in operations)
    {
        if (i.Metadata.Symbol.Equals(operation)) return i.Value.Operate(left, right).ToString();
    }
    return "Operation Not Found!";
}
```

<span data-ttu-id="e9a06-230">I passaggi iniziali analizzano la stringa di input in operandi sinistro e destro e carattere dell'operatore.</span><span class="sxs-lookup"><span data-stu-id="e9a06-230">The initial steps parse the input string into left and right operands and an operator character.</span></span> <span data-ttu-id="e9a06-231">Nel ciclo `foreach`, viene esaminato ogni membro della raccolta `operations`.</span><span class="sxs-lookup"><span data-stu-id="e9a06-231">In the `foreach` loop, every member of the `operations` collection is examined.</span></span> <span data-ttu-id="e9a06-232">Questi oggetti sono di tipo <xref:System.Lazy%602> e l'accesso ai relativi valori di metadati e al relativo oggetto esportato può essere eseguito rispettivamente con la proprietà <xref:System.Lazy%602.Metadata%2A> e la proprietà <xref:System.Lazy%601.Value%2A>.</span><span class="sxs-lookup"><span data-stu-id="e9a06-232">These objects are of type <xref:System.Lazy%602>, and their metadata values and exported object can be accessed with the <xref:System.Lazy%602.Metadata%2A> property and the <xref:System.Lazy%601.Value%2A> property respectively.</span></span> <span data-ttu-id="e9a06-233">In questo caso, se si verifica la corrispondenza della proprietà `Symbol` dell'oggetto `IOperationData`, la calcolatrice chiama il metodo `Operate` dell'oggetto `IOperation` e restituisce il risultato.</span><span class="sxs-lookup"><span data-stu-id="e9a06-233">In this case, if the `Symbol` property of the `IOperationData` object is discovered to be a match, the calculator calls the `Operate` method of the `IOperation` object and returns the result.</span></span>

<span data-ttu-id="e9a06-234">Per completare la calcolatrice è inoltre necessario il metodo helper che restituisce la posizione del primo carattere non numerico in una stringa.</span><span class="sxs-lookup"><span data-stu-id="e9a06-234">To complete the calculator, you also need a helper method that returns the position of the first non-digit character in a string.</span></span> <span data-ttu-id="e9a06-235">Aggiungere il seguente metodo helper alla classe `MySimpleCalculator`:</span><span class="sxs-lookup"><span data-stu-id="e9a06-235">Add the following helper method to the `MySimpleCalculator` class:</span></span>

```vb
Private Function FindFirstNonDigit(s As String) As Integer
    For i = 0 To s.Length - 1
        If Not Char.IsDigit(s(i)) Then Return i
    Next
    Return -1
End Function
```

```csharp
private int FindFirstNonDigit(string s)
{
    for (int i = 0; i < s.Length; i++)
    {
        if (!Char.IsDigit(s[i])) return i;
    }
    return -1;
}
```

<span data-ttu-id="e9a06-236">A questo punto è possibile compilare ed eseguire il progetto.</span><span class="sxs-lookup"><span data-stu-id="e9a06-236">You should now be able to compile and run the project.</span></span> <span data-ttu-id="e9a06-237">In Visual Basic, accertarsi di aver aggiunto la parola chiave `Public` a `Module1`.</span><span class="sxs-lookup"><span data-stu-id="e9a06-237">In Visual Basic, make sure that you added the `Public` keyword to `Module1`.</span></span> <span data-ttu-id="e9a06-238">Digitare un'operazione di addizione nella finestra della console, ad esempio "5+3". La calcolatrice restituirà i risultati.</span><span class="sxs-lookup"><span data-stu-id="e9a06-238">In the console window, type an addition operation, such as "5+3", and the calculator returns the results.</span></span> <span data-ttu-id="e9a06-239">Se si usano altri operatori, viene visualizzato un messaggio che indica che l'operazione non è stata</span><span class="sxs-lookup"><span data-stu-id="e9a06-239">Any other operator results in the "Operation Not Found!"</span></span> <span data-ttu-id="e9a06-240">il messaggio "Hello World!".</span><span class="sxs-lookup"><span data-stu-id="e9a06-240">message.</span></span>

## <a name="extending-simplecalculator-using-a-new-class"></a><span data-ttu-id="e9a06-241">Estensione di SimpleCalculator mediante una nuova classe</span><span class="sxs-lookup"><span data-stu-id="e9a06-241">Extending SimpleCalculator using a new class</span></span>

<span data-ttu-id="e9a06-242">Ora che la calcolatrice funziona, risulta facile aggiungere una nuova operazione.</span><span class="sxs-lookup"><span data-stu-id="e9a06-242">Now that the calculator works, adding a new operation is easy.</span></span> <span data-ttu-id="e9a06-243">Aggiungere la classe seguente al modulo o allo spazio dei nomi `SimpleCalculator`:</span><span class="sxs-lookup"><span data-stu-id="e9a06-243">Add the following class to the module or `SimpleCalculator` namespace:</span></span>

```vb
<Export(GetType(IOperation))>
<ExportMetadata("Symbol", "-"c)>
Public Class Subtract
    Implements IOperation

    Public Function Operate(left As Integer, right As Integer) As Integer Implements IOperation.Operate
        Return left - right
    End Function
End Class
```

```csharp
[Export(typeof(IOperation))]
[ExportMetadata("Symbol", '-')]
class Subtract : IOperation
{
    public int Operate(int left, int right)
    {
        return left - right;
    }
}
```

<span data-ttu-id="e9a06-244">Compilare ed eseguire il progetto.</span><span class="sxs-lookup"><span data-stu-id="e9a06-244">Compile and run the project.</span></span> <span data-ttu-id="e9a06-245">Digitare un'operazione di sottrazione, ad esempio "5-3".</span><span class="sxs-lookup"><span data-stu-id="e9a06-245">Type a subtraction operation, such as "5-3".</span></span> <span data-ttu-id="e9a06-246">Oltre all'addizione, la calcolatrice supporta ora anche la sottrazione.</span><span class="sxs-lookup"><span data-stu-id="e9a06-246">The calculator now supports subtraction as well as addition.</span></span>

## <a name="extending-simplecalculator-using-a-new-assembly"></a><span data-ttu-id="e9a06-247">Estensione di SimpleCalculator tramite un nuovo assembly</span><span class="sxs-lookup"><span data-stu-id="e9a06-247">Extending SimpleCalculator using a new assembly</span></span>

<span data-ttu-id="e9a06-248">Benché aggiungere classi al codice sorgente sia abbastanza semplice, MEF offre la possibilità di cercare le parti all'esterno del codice sorgente di un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="e9a06-248">Adding classes to the source code is simple enough, but MEF provides the ability to look outside an application’s own source for parts.</span></span> <span data-ttu-id="e9a06-249">Per dimostrarlo, sarà necessario modificare SimpleCalculator affinché cerchi le parti in una directory, nonché nel proprio assembly, mediante l'aggiunta di <xref:System.ComponentModel.Composition.Hosting.DirectoryCatalog>.</span><span class="sxs-lookup"><span data-stu-id="e9a06-249">To demonstrate this, you will need to modify SimpleCalculator to search a directory, as well as its own assembly, for parts, by adding a <xref:System.ComponentModel.Composition.Hosting.DirectoryCatalog>.</span></span>

<span data-ttu-id="e9a06-250">Aggiungere al progetto SimpleCalculator una nuova directory denominata `Extensions`.</span><span class="sxs-lookup"><span data-stu-id="e9a06-250">Add a new directory named `Extensions` to the SimpleCalculator project.</span></span> <span data-ttu-id="e9a06-251">Assicurarsi di aggiungerla a livello di progetto e non a livello di soluzione.</span><span class="sxs-lookup"><span data-stu-id="e9a06-251">Make sure to add it at the project level, and not at the solution level.</span></span> <span data-ttu-id="e9a06-252">Aggiungere quindi alla soluzione un nuovo progetto Libreria di classi denominato `ExtendedOperations`.</span><span class="sxs-lookup"><span data-stu-id="e9a06-252">Then add a new Class Library project to the solution, named `ExtendedOperations`.</span></span> <span data-ttu-id="e9a06-253">Il nuovo progetto verrà compilato in un assembly separato.</span><span class="sxs-lookup"><span data-stu-id="e9a06-253">The new project will compile into a separate assembly.</span></span>

<span data-ttu-id="e9a06-254">Aprire la finestra di progettazione Proprietà progetto per il progetto ExtendedOperations e **Compile** fare clic **sulla scheda Compila o compila.** modificare il percorso dell' **output di compilazione** o il **percorso di output** in modo che punti alla directory Extensions nella directory del progetto SimpleCalculator (\*.. \SimpleCalculator\Extensions \\ \*).</span><span class="sxs-lookup"><span data-stu-id="e9a06-254">Open the Project Properties Designer for the ExtendedOperations project and click the **Compile** or **Build** tab. Change the **Build output path** or **Output path** to point to the Extensions directory in the SimpleCalculator project directory (*..\SimpleCalculator\Extensions\\*).</span></span>

 <span data-ttu-id="e9a06-255">In *Module1. vb* o *Program.cs*aggiungere la riga seguente al `Program` costruttore:</span><span class="sxs-lookup"><span data-stu-id="e9a06-255">In *Module1.vb* or *Program.cs*, add the following line to the `Program` constructor:</span></span>

```vb
catalog.Catalogs.Add(New DirectoryCatalog("C:\SimpleCalculator\SimpleCalculator\Extensions"))
```

```csharp
catalog.Catalogs.Add(new DirectoryCatalog("C:\\SimpleCalculator\\SimpleCalculator\\Extensions"));
```

<span data-ttu-id="e9a06-256">Sostituire il percorso di esempio con il percorso della directory Extensions.</span><span class="sxs-lookup"><span data-stu-id="e9a06-256">Replace the example path with the path to your Extensions directory.</span></span> <span data-ttu-id="e9a06-257">Il percorso assoluto è solo a scopo di debug.</span><span class="sxs-lookup"><span data-stu-id="e9a06-257">(This absolute path is for debugging purposes only.</span></span> <span data-ttu-id="e9a06-258">In un'applicazione di produzione è necessario usare un percorso relativo. <xref:System.ComponentModel.Composition.Hosting.DirectoryCatalog>A questo punto, le parti presenti in tutti gli assembly nella directory Extensions verranno aggiunte al contenitore di composizione.</span><span class="sxs-lookup"><span data-stu-id="e9a06-258">In a production application, you would use a relative path.) The <xref:System.ComponentModel.Composition.Hosting.DirectoryCatalog> will now add any parts found in any assemblies in the Extensions directory to the composition container.</span></span>

<span data-ttu-id="e9a06-259">Nel progetto ExtendedOperations aggiungere i riferimenti a SimpleCalculator e System.ComponentModel.Composition.</span><span class="sxs-lookup"><span data-stu-id="e9a06-259">In the ExtendedOperations project, add references to SimpleCalculator and System.ComponentModel.Composition.</span></span> <span data-ttu-id="e9a06-260">Nel file di classe ExtendedOperations aggiungere un'istruzione `Imports` o `using` per System.ComponentModel.Composition.</span><span class="sxs-lookup"><span data-stu-id="e9a06-260">In the ExtendedOperations class file, add an `Imports` or a `using` statement for System.ComponentModel.Composition.</span></span> <span data-ttu-id="e9a06-261">In Visual Basic aggiungere anche un'istruzione `Imports` per SimpleCalculator.</span><span class="sxs-lookup"><span data-stu-id="e9a06-261">In Visual Basic, also add an `Imports` statement for SimpleCalculator.</span></span> <span data-ttu-id="e9a06-262">Quindi, aggiungere la seguente classe al file di classe ExtendedOperations:</span><span class="sxs-lookup"><span data-stu-id="e9a06-262">Then add the following class to the ExtendedOperations class file:</span></span>

```vb
<Export(GetType(SimpleCalculator.IOperation))>
<ExportMetadata("Symbol", "%"c)>
Public Class Modulo
    Implements IOperation

    Public Function Operate(left As Integer, right As Integer) As Integer Implements IOperation.Operate
        Return left Mod right
    End Function
End Class
```

```csharp
[Export(typeof(SimpleCalculator.IOperation))]
[ExportMetadata("Symbol", '%')]
public class Mod : SimpleCalculator.IOperation
{
    public int Operate(int left, int right)
    {
        return left % right;
    }
}
```

<span data-ttu-id="e9a06-263">Per la corrispondenza del contratto, l'attributo <xref:System.ComponentModel.Composition.ExportAttribute> deve avere lo stesso tipo di <xref:System.ComponentModel.Composition.ImportAttribute>.</span><span class="sxs-lookup"><span data-stu-id="e9a06-263">Note that in order for the contract to match, the <xref:System.ComponentModel.Composition.ExportAttribute> attribute must have the same type as the <xref:System.ComponentModel.Composition.ImportAttribute>.</span></span>

<span data-ttu-id="e9a06-264">Compilare ed eseguire il progetto.</span><span class="sxs-lookup"><span data-stu-id="e9a06-264">Compile and run the project.</span></span> <span data-ttu-id="e9a06-265">Testare il nuovo operatore Mod (%).</span><span class="sxs-lookup"><span data-stu-id="e9a06-265">Test the new Mod (%) operator.</span></span>

## <a name="conclusion"></a><span data-ttu-id="e9a06-266">Conclusioni</span><span class="sxs-lookup"><span data-stu-id="e9a06-266">Conclusion</span></span>

<span data-ttu-id="e9a06-267">In questo argomento sono stati trattati i concetti di base di MEF.</span><span class="sxs-lookup"><span data-stu-id="e9a06-267">This topic covered the basic concepts of MEF.</span></span>

- <span data-ttu-id="e9a06-268">Parti, cataloghi e contenitore di composizione</span><span class="sxs-lookup"><span data-stu-id="e9a06-268">Parts, catalogs, and the composition container</span></span>

     <span data-ttu-id="e9a06-269">Le parti e il contenitore di composizione sono i blocchi predefiniti di base di un'applicazione MEF.</span><span class="sxs-lookup"><span data-stu-id="e9a06-269">Parts and the composition container are the basic building blocks of a MEF application.</span></span> <span data-ttu-id="e9a06-270">Una parte è qualsiasi oggetto che importa o esporta un valore, fino al proprio valore (incluso).</span><span class="sxs-lookup"><span data-stu-id="e9a06-270">A part is any object that imports or exports a value, up to and including itself.</span></span> <span data-ttu-id="e9a06-271">Un catalogo fornisce un insieme di parti ottenute da una determinata origine.</span><span class="sxs-lookup"><span data-stu-id="e9a06-271">A catalog provides a collection of parts from a particular source.</span></span> <span data-ttu-id="e9a06-272">Il contenitore di composizione usa le parti fornite da un catalogo per eseguire la composizione, ovvero l'associazione tra le importazioni e le esportazioni.</span><span class="sxs-lookup"><span data-stu-id="e9a06-272">The composition container uses the parts provided by a catalog to perform composition, the binding of imports to exports.</span></span>

- <span data-ttu-id="e9a06-273">Importazioni ed esportazioni</span><span class="sxs-lookup"><span data-stu-id="e9a06-273">Imports and exports</span></span>

     <span data-ttu-id="e9a06-274">Le importazioni e le esportazioni rappresentano il canale di comunicazione fra i componenti.</span><span class="sxs-lookup"><span data-stu-id="e9a06-274">Imports and exports are the way by which components communicate.</span></span> <span data-ttu-id="e9a06-275">Con un'importazione il componente specifica la necessità di un determinato valore o oggetto, mentre con un'esportazione specifica la disponibilità di un valore.</span><span class="sxs-lookup"><span data-stu-id="e9a06-275">With an import, the component specifies a need for a particular value or object, and with an export it specifies the availability of a value.</span></span> <span data-ttu-id="e9a06-276">Ogni importazione viene associata a un elenco di esportazioni mediante il relativo contratto.</span><span class="sxs-lookup"><span data-stu-id="e9a06-276">Each import is matched with a list of exports by way of its contract.</span></span>

## <a name="next-steps"></a><span data-ttu-id="e9a06-277">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="e9a06-277">Next steps</span></span>

<span data-ttu-id="e9a06-278">Per scaricare il codice completo per questo esempio, vedere l' [esempio SimpleCalculator (Visual Basic)](https://docs.microsoft.com/samples/dotnet/samples/simple-calculator-vb/).</span><span class="sxs-lookup"><span data-stu-id="e9a06-278">To download the complete code for this example, see the [SimpleCalculator sample (Visual Basic)](https://docs.microsoft.com/samples/dotnet/samples/simple-calculator-vb/).</span></span>

 <span data-ttu-id="e9a06-279">Per altre informazioni e per esempi di codice, vedere [Managed Extensibility Framework](https://github.com/MicrosoftArchive/mef).</span><span class="sxs-lookup"><span data-stu-id="e9a06-279">For more information and code examples, see [Managed Extensibility Framework](https://github.com/MicrosoftArchive/mef).</span></span> <span data-ttu-id="e9a06-280">Per un elenco di tipi MEF, vedere lo spazio dei nomi <xref:System.ComponentModel.Composition?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="e9a06-280">For a list of the MEF types, see the <xref:System.ComponentModel.Composition?displayProperty=nameWithType> namespace.</span></span>

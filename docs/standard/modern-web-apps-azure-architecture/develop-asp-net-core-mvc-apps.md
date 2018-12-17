---
title: Sviluppo di app ASP.NET Core MVC
description: Progettare applicazioni Web moderne con ASP.NET Core e Azure | Sviluppo di app ASP.NET Core MVC
author: ardalis
ms.author: wiwagn
ms.date: 06/28/2018
ms.openlocfilehash: 7459173f21bd5219c2aa7b994ac2b2b44857375f
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2018
ms.locfileid: "53152779"
---
# <a name="develop-aspnet-core-mvc-apps"></a><span data-ttu-id="4b3d2-103">Sviluppare app ASP.NET Core MVC</span><span class="sxs-lookup"><span data-stu-id="4b3d2-103">Develop ASP.NET Core MVC apps</span></span>

> <span data-ttu-id="4b3d2-104">"Non è importante ottenere il risultato desiderato al primo tentativo.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-104">"It's not important to get it right the first time.</span></span> <span data-ttu-id="4b3d2-105">L'importante è ottenerlo all'ultimo".</span><span class="sxs-lookup"><span data-stu-id="4b3d2-105">It's vitally important to get it right the last time."</span></span>  
> <span data-ttu-id="4b3d2-106">_- Andrew Hunt e David Thomas_</span><span class="sxs-lookup"><span data-stu-id="4b3d2-106">_- Andrew Hunt and David Thomas_</span></span>

<span data-ttu-id="4b3d2-107">ASP.NET Core è un framework multipiattaforma open source per la compilazione di moderne applicazioni Web ottimizzate per il cloud.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-107">ASP.NET Core is a cross-platform, open-source framework for building modern cloud-optimized web applications.</span></span> <span data-ttu-id="4b3d2-108">Le app ASP.NET Core sono leggere e modulari, con supporto incorporato per l'inserimento di dipendenze, e offrono maggiore testabilità e gestibilità.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-108">ASP.NET Core apps are lightweight and modular, with built-in support for dependency injection, enabling greater testability and maintainability.</span></span> <span data-ttu-id="4b3d2-109">In associazione a MVC, che supporta la compilazione di API Web moderne oltre che di app basate su visualizzazione, ASP.NET Core è un framework potente per la compilazione di applicazioni Web aziendali.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-109">Combined with MVC, which supports building modern web APIs in addition to view-based apps, ASP.NET Core is a powerful framework with which to build enterprise web applications.</span></span>

## <a name="mapping-requests-to-responses"></a><span data-ttu-id="4b3d2-110">Mapping delle richieste alle risposte</span><span class="sxs-lookup"><span data-stu-id="4b3d2-110">Mapping requests to responses</span></span>

<span data-ttu-id="4b3d2-111">Fondamentalmente, le app ASP.NET Core mappano le richieste in ingresso alle risposte in uscita.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-111">At its heart, ASP.NET Core apps map incoming requests to outgoing responses.</span></span> <span data-ttu-id="4b3d2-112">Questa operazione viene eseguita tramite middleware e le semplici app ASP.NET Core e i microservizi possono essere costituiti esclusivamente da middleware personalizzato.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-112">At a low level, this is done with middleware, and simple ASP.NET Core apps and microservices may be comprised solely of custom middleware.</span></span> <span data-ttu-id="4b3d2-113">Quando si usa ASP.NET Core MVC, è possibile lavorare a un livello avanzato con _route_, _controller_ e _azioni_.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-113">When using ASP.NET Core MVC, you can work at a somewhat higher level, thinking in terms of _routes_, _controllers_, and _actions_.</span></span> <span data-ttu-id="4b3d2-114">Ogni richiesta in ingresso viene confrontata con la tabella di routing dell'applicazione e se viene trovata una route corrispondente, viene chiamato il metodo di azione associato (appartenente a un controller) per gestire la richiesta.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-114">Each incoming request is compared with the application's routing table, and if a matching route is found, the associated action method (belonging to a controller) is called to handle the request.</span></span> <span data-ttu-id="4b3d2-115">Se non viene trovata alcuna route corrispondente, viene chiamato un gestore degli errori (in questo caso, viene restituito un risultato NotFound).</span><span class="sxs-lookup"><span data-stu-id="4b3d2-115">If no matching route is found, an error handler (in this case, returning a NotFound result) is called.</span></span>

<span data-ttu-id="4b3d2-116">Le app ASP.NET Core MVC possono usare route convenzionali, route di attributi o entrambi i tipi di route.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-116">ASP.NET Core MVC apps can use conventional routes, attribute routes, or both.</span></span> <span data-ttu-id="4b3d2-117">Le route convenzionali sono definite nel codice tramite la specifica delle _convenzioni_ di routing usando una sintassi simile a quella dell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="4b3d2-117">Conventional routes are defined in code, specifying routing _conventions_ using syntax like in the example below:</span></span>

```csharp
app.UseMvc(routes =>;
{
    routes.MapRoute("default","{controller=Home}/{action=Index}/{id?}");
});
```

<span data-ttu-id="4b3d2-118">In questo esempio è stata aggiunta una route denominata "default" alla tabella di routing.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-118">In this example, a route named "default" has been added to the routing table.</span></span> <span data-ttu-id="4b3d2-119">Definisce un modello di route con segnaposto per _controller_, _azione_ e _ID_. I segnaposto di controller e azione hanno un valore predefinito specificato, rispettivamente "Home" e "Index", mentre il segnaposto di ID è facoltativo poiché è applicato un "?".</span><span class="sxs-lookup"><span data-stu-id="4b3d2-119">It defines a route template with placeholders for _controller_, _action_, and _id_. The controller and action placeholders have default specified ("Home" and "Index", respectively), and the id placeholder is optional (by virtue of a "?" applied to it).</span></span> <span data-ttu-id="4b3d2-120">La convenzione definita in questo caso stabilisce che la prima parte di una richiesta deve corrispondere al nome del controller, la seconda parte all'azione e, se necessaria, una terza parte al parametro dell'ID.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-120">The convention defined here states that the first part of a request should correspond to the name of the controller, the second part to the action, and then if necessary a third part will represent an id parameter.</span></span> <span data-ttu-id="4b3d2-121">Le route convenzionali vengono in genere definite in un'unica posizione per l'applicazione, ad esempio nel metodo Configure della classe Startup.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-121">Conventional routes are typically defined in one place for the application, such as in the Configure method in the Startup class.</span></span>

<span data-ttu-id="4b3d2-122">Le route di attributi vengono applicate a controller e azioni direttamente anziché essere specificate a livello globale.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-122">Attribute routes are applied to controllers and actions directly, rather than specified globally.</span></span> <span data-ttu-id="4b3d2-123">Ciò offre il vantaggio di renderle più facilmente individuabili durante la ricerca di un metodo specifico, ma significa che le informazioni di routing non vengono mantenute in un'unica posizione nell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-123">This has the advantage of making them much more discoverable when you're looking at a particular method, but does mean that routing information is not kept in one place in the application.</span></span> <span data-ttu-id="4b3d2-124">Con le route di attributi, è possibile specificare in modo semplice più route per una determinata azione nonché combinare le route tra i controller e le azioni.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-124">With attribute routes, you can easily specify multiple routes for a given action, as well as combine routes between controllers and actions.</span></span> <span data-ttu-id="4b3d2-125">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="4b3d2-125">For example:</span></span>

```csharp
[Route("Home")]
public class HomeController : Controller
{
    [Route("")] // Combines to define the route template "Home"
    [Route("Index")] // Combines to define route template "Home/Index"
    [Route("/")] // Does not combine, defines the route template ""
    public IActionResult Index() {}
}
```

<span data-ttu-id="4b3d2-126">Le route possono essere specificate in [HttpGet] e attributi simili, evitando la necessità di aggiungere attributi [Route] separati.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-126">Routes can be specified on [HttpGet] and similar attributes, avoiding the need to add separate [Route] attributes.</span></span> <span data-ttu-id="4b3d2-127">Le route di attributi possono anche usare i token per ridurre la necessità di ripetere i nomi di controller o azioni, come illustrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="4b3d2-127">Attribute routes can also use tokens to reduce the need to repeat controller or action names, as shown below:</span></span>

```csharp
[Route("[controller\]")]
public class ProductsController : Controller
{
    [Route("")] // Matches 'Products'
    [Route("Index")] // Matches 'Products/Index'
    public IActionResult Index() {}
}
```

<span data-ttu-id="4b3d2-128">Dopo aver individuato una determinata richiesta corrispondente a una route e prima della chiamata al metodo di azione, ASP.NET Core MVC eseguirà l'[associazione del modello](/aspnet/core/mvc/models/model-binding) e la [convalida del modello](/aspnet/core/mvc/models/validation) nella richiesta.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-128">Once a given request has been matched to a route, but before the action method is called, ASP.NET Core MVC will perform [model binding](/aspnet/core/mvc/models/model-binding) and [model validation](/aspnet/core/mvc/models/validation) on the request.</span></span> <span data-ttu-id="4b3d2-129">L'associazione del modello converte i dati HTTP in ingresso nei tipi .NET specificati come parametri del metodo di azione da chiamare.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-129">Model binding is responsible for converting incoming HTTP data into the .NET types specified as parameters of the action method to be called.</span></span> <span data-ttu-id="4b3d2-130">Ad esempio, se il metodo di azione prevede un parametro ID di tipo int, l'associazione del modello tenterà di usare questo parametro in base a un valore specificato come parte della richiesta.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-130">For example, if the action method expects an int id parameter, model binding will attempt to provide this parameter from a value provided as part of the request.</span></span> <span data-ttu-id="4b3d2-131">A tale scopo, l'associazione del modello cerca i valori in un form pubblicato, i valori nella route e i valori di stringa di query.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-131">To do so, model binding looks for values in a posted form, values in the route itself, and query string values.</span></span> <span data-ttu-id="4b3d2-132">Se viene trovato un valore ID, il valore viene convertito in un intero prima di essere passato nel metodo di azione.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-132">Assuming an id value is found, it will be converted to an integer before being passed into the action method.</span></span>

<span data-ttu-id="4b3d2-133">Dopo l'associazione del modello ma prima della chiamata al metodo di azione, viene eseguita la convalida del modello.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-133">After binding the model but before calling the action method, model validation occurs.</span></span> <span data-ttu-id="4b3d2-134">La convalida del modello usa gli attributi facoltativi del tipo di modello e contribuisce a garantire che l'oggetto di modello specificato sia conforme a determinati requisiti dei dati.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-134">Model validation uses optional attributes on the model type, and can help ensure that the provided model object conforms to certain data requirements.</span></span> <span data-ttu-id="4b3d2-135">Alcuni valori possono essere specificati come obbligatori o limitati a una determinata lunghezza o a un determinato intervallo numerico e così via. Se vengono specificati gli attributi di convalida ma il modello non è conforme ai requisiti, la proprietà ModelState.IsValid avrà valore false e il set di regole della convalida non riuscita sarà disponibile per l'invio al client che effettua la richiesta.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-135">Certain values may be specified as required, or limited to a certain length or numeric range, etc. If validation attributes are specified but the model does not conform to their requirements, the property ModelState.IsValid will be false, and the set of failing validation rules will be available to send to the client making the request.</span></span>

<span data-ttu-id="4b3d2-136">Se viene usata la convalida del modello, è necessario verificare sempre che il modello sia valido prima di eseguire i comandi di modifica dello stato per garantire che l'app non sia danneggiata da dati non validi.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-136">If you're using model validation, you should be sure to always check that the model is valid before performing any state-altering commands, to ensure your app is not corrupted by invalid data.</span></span> <span data-ttu-id="4b3d2-137">È possibile usare un [filtro](/aspnet/core/mvc/controllers/filters) per evitare di aggiungere il codice necessario in ogni azione.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-137">You can use a [filter](/aspnet/core/mvc/controllers/filters) to avoid the need to add code for this in every action.</span></span> <span data-ttu-id="4b3d2-138">I filtri di ASP.NET Core MVC consentono di intercettare i gruppi di richieste in modo che sia possibile applicare alla base di destinazione i criteri e gli aspetti comuni.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-138">ASP.NET Core MVC filters offer a way of intercepting groups of requests, so that common policies and cross-cutting concerns can be applied on a targeted basis.</span></span> <span data-ttu-id="4b3d2-139">I filtri possono essere applicati alle singole azioni, a interi controller o a livello globale per un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-139">Filters can be applied to individual actions, whole controllers, or globally for an application.</span></span>

<span data-ttu-id="4b3d2-140">Per le API Web, ASP.NET Core MVC supporta la [_negoziazione del contenuto_](/aspnet/core/mvc/models/formatting) consentendo alle richieste di specificare la formattazione delle risposte.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-140">For web APIs, ASP.NET Core MVC supports [_content negotiation_](/aspnet/core/mvc/models/formatting), allowing requests to specify how responses should be formatted.</span></span> <span data-ttu-id="4b3d2-141">In base alle intestazioni specificate nella richiesta, le azioni che restituiscono dati formattano la risposta nel formato XML, JSON o un altro formato supportato.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-141">Based on headers provided in the request, actions returning data will format the response in XML, JSON, or another supported format.</span></span> <span data-ttu-id="4b3d2-142">Questa funzionalità consente a più client con requisiti diversi di formattazione dei dati di usare la stessa API.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-142">This feature enables the same API to be used by multiple clients with different data format requirements.</span></span>

> ### <a name="references--mapping-requests-to-responses"></a><span data-ttu-id="4b3d2-143">Riferimenti - Mapping delle richieste alle risposte</span><span class="sxs-lookup"><span data-stu-id="4b3d2-143">References – Mapping Requests to Responses</span></span>
>
> - <span data-ttu-id="4b3d2-144">**Routing ad azioni del controller**
> <https://docs.microsoft.com/aspnet/core/mvc/controllers/routing></span><span class="sxs-lookup"><span data-stu-id="4b3d2-144">**Routing to Controller Actions**
<https://docs.microsoft.com/aspnet/core/mvc/controllers/routing></span></span>
> - <span data-ttu-id="4b3d2-145">**Associazione di modelli**
> <https://docs.microsoft.com/aspnet/core/mvc/models/model-binding></span><span class="sxs-lookup"><span data-stu-id="4b3d2-145">**Model Binding**
<https://docs.microsoft.com/aspnet/core/mvc/models/model-binding></span></span>
> - <span data-ttu-id="4b3d2-146">**Convalida del modello**
> <https://docs.microsoft.com/aspnet/core/mvc/models/validation></span><span class="sxs-lookup"><span data-stu-id="4b3d2-146">**Model Validation**
<https://docs.microsoft.com/aspnet/core/mvc/models/validation></span></span>
> - <span data-ttu-id="4b3d2-147">**Filtri**
> <https://docs.microsoft.com/aspnet/core/mvc/controllers/filters></span><span class="sxs-lookup"><span data-stu-id="4b3d2-147">**Filters**
<https://docs.microsoft.com/aspnet/core/mvc/controllers/filters></span></span>

## <a name="working-with-dependencies"></a><span data-ttu-id="4b3d2-148">Uso delle dipendenze</span><span class="sxs-lookup"><span data-stu-id="4b3d2-148">Working with dependencies</span></span>

<span data-ttu-id="4b3d2-149">ASP.NET Core include il supporto incorporato e usa internamente una tecnica chiamata [inserimento di dipendenze](/aspnet/core/fundamentals/dependency-injection).</span><span class="sxs-lookup"><span data-stu-id="4b3d2-149">ASP.NET Core has built-in support for and internally makes use of a technique known as [dependency injection](/aspnet/core/fundamentals/dependency-injection).</span></span> <span data-ttu-id="4b3d2-150">L'inserimento di dipendenze è una tecnica che abilita l'accoppiamento libero tra parti diverse di un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-150">Dependency injection is a technique that enables loose coupling between different parts of an application.</span></span> <span data-ttu-id="4b3d2-151">L'accoppiamento libero può essere utile perché rende più semplice isolare le parti dell'applicazione per il test o la sostituzione.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-151">Looser coupling is desirable because it makes it easier to isolate parts of the application, allowing for testing or replacement.</span></span> <span data-ttu-id="4b3d2-152">Rende anche meno probabile che una modifica in una parte dell'applicazione abbia un impatto imprevisto in un'altra posizione nell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-152">It also makes it less likely that a change in one part of the application will have an unexpected impact somewhere else in the application.</span></span> <span data-ttu-id="4b3d2-153">L'inserimento di dipendenze si basa sul principio di inversione della dipendenza e rappresenta spesso la chiave per ottenere il principio di apertura/chiusura.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-153">Dependency injection is based on the dependency inversion principle, and is often key to achieving the open/closed principle.</span></span> <span data-ttu-id="4b3d2-154">Quando si valuta il funzionamento dell'applicazione con le dipendenze, prestare attenzione al codice [static cling](https://deviq.com/static-cling/) e ricordare la frase "[New is Glue](https://ardalis.com/new-is-glue)".</span><span class="sxs-lookup"><span data-stu-id="4b3d2-154">When evaluating how your application works with its dependencies, beware of the [static cling](https://deviq.com/static-cling/) code smell, and remember the aphorism "[new is glue](https://ardalis.com/new-is-glue)."</span></span>

<span data-ttu-id="4b3d2-155">Lo static cling si verifica quando le classi chiamano metodi statici o accedono a proprietà statiche, un'operazione che comporta effetti collaterali o dipendenze nell'infrastruttura.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-155">Static cling occurs when your classes make calls to static methods, or access static properties, which have side effects or dependencies on infrastructure.</span></span> <span data-ttu-id="4b3d2-156">Ad esempio, se è presente un metodo che chiama un metodo statico che a sua volta scrive in un database, il metodo è strettamente accoppiato al database.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-156">For example, if you have a method that calls a static method, which in turn writes to a database, your method is tightly coupled to the database.</span></span> <span data-ttu-id="4b3d2-157">Qualsiasi elemento che interrompe la chiamata al database interromperà il metodo.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-157">Anything that breaks that database call will break your method.</span></span> <span data-ttu-id="4b3d2-158">Eseguire i test di questi tipi di metodi è notoriamente difficile poiché i test richiedono librerie di simulazione commerciali per simulare le chiamate statiche oppure possono essere eseguiti solo con un database di prova.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-158">Testing such methods is notoriously difficult, since such tests either require commercial mocking libraries to mock the static calls, or can only be tested with a test database in place.</span></span> <span data-ttu-id="4b3d2-159">Le chiamate statiche che non hanno alcuna dipendenza nell'infrastruttura, in particolare quelle che sono completamente senza stato, possono essere eseguite senza problemi e non hanno alcun effetto sull'accoppiamento o la testabilità (oltre all'accoppiamento del codice alla chiamata statica).</span><span class="sxs-lookup"><span data-stu-id="4b3d2-159">Static calls that don't have any dependence on infrastructure, especially those that are completely stateless, are fine to call and have no impact on coupling or testability (beyond coupling code to the static call itself).</span></span>

<span data-ttu-id="4b3d2-160">Sebbene conoscano i rischi dello static cling e dello stato globale, molti sviluppatori eseguono comunque uno stretto accoppiamento del codice a implementazioni specifiche attraverso la creazione diretta delle istanze.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-160">Many developers understand the risks of static cling and global state, but will still tightly couple their code to specific implementations through direct instantiation.</span></span> <span data-ttu-id="4b3d2-161">"New is glue" vuole essere un promemoria di questo accoppiamento e non una condanna generale dell'uso della parola chiave `new`.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-161">"New is glue" is meant to be a reminder of this coupling, and not a general condemnation of the use of the `new` keyword.</span></span> <span data-ttu-id="4b3d2-162">Come con le chiamate a metodi statici, le nuove istanze dei tipi che non hanno dipendenze esterne in genere non accoppiano strettamente il codice ai dettagli di implementazione o rendono più difficile il test.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-162">Just as with static method calls, new instances of types that have no external dependencies typically do not tightly couple code to implementation details or make testing more difficult.</span></span> <span data-ttu-id="4b3d2-163">Tuttavia, ogni volta che viene creata un'istanza di una classe, fermarsi a considerare se è consigliabile impostare come hardcoded l'istanza specifica in quella determinata posizione oppure richiedere l'istanza come dipendenza.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-163">But each time a class is instantiated, take just a brief moment to consider whether it makes sense to hard-code that specific instance in that particular location, or if it would be a better design to request that instance as a dependency.</span></span>

### <a name="declare-your-dependencies"></a><span data-ttu-id="4b3d2-164">Dichiarare le dipendenze</span><span class="sxs-lookup"><span data-stu-id="4b3d2-164">Declare your dependencies</span></span>

<span data-ttu-id="4b3d2-165">ASP.NET Core si basa su metodi e classi che dichiarano le relative dipendenze richiedendole come argomenti.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-165">ASP.NET Core is built around having methods and classes declare their dependencies, requesting them as arguments.</span></span> <span data-ttu-id="4b3d2-166">Le applicazioni ASP.NET sono in genere configurate in una classe Startup che è a sua volta configurata per supportare l'inserimento di dipendenze in punti diversi.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-166">ASP.NET applications are typically set up in a Startup class, which itself is configured to support dependency injection at several points.</span></span> <span data-ttu-id="4b3d2-167">Se la classe Startup ha un costruttore, può richiedere le dipendenze mediante il costruttore, come illustrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="4b3d2-167">If your Startup class has a constructor, it can request dependencies through the constructor, like so:</span></span>

```csharp
public class Startup
{
    public Startup(IHostingEnvironment env)
    {
        var builder = new ConfigurationBuilder()
        .SetBasePath(env.ContentRootPath)
        .AddJsonFile("appsettings.json", optional: false, reloadOnChange: true)
        .AddJsonFile(\$"appsettings.{env.EnvironmentName}.json", optional: true);
    }
}
```

<span data-ttu-id="4b3d2-168">La classe Startup è particolare perché non include requisiti di tipo espliciti per la classe.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-168">The Startup class is interesting in that there are no explicit type requirements for it.</span></span> <span data-ttu-id="4b3d2-169">Non eredita da una classe di base Startup, né implementa alcuna interfaccia specifica.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-169">It doesn't inherit from a special Startup base class, nor does it implement any particular interface.</span></span> <span data-ttu-id="4b3d2-170">È possibile assegnare o meno alla classe un costruttore ed è possibile specificare il numero di parametri desiderato nel costruttore.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-170">You can give it a constructor, or not, and you can specify as many parameters on the constructor as you want.</span></span> <span data-ttu-id="4b3d2-171">Quando viene avviato l'host Web configurato per l'applicazione, l'host chiama la classe Startup specificata e usa l'inserimento di dipendenze per popolare le dipendenze richieste dalla classe Startup.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-171">When the web host you've configured for your application starts, it will call the Startup class you've told it to use, and will use dependency injection to populate any dependencies the Startup class requires.</span></span> <span data-ttu-id="4b3d2-172">Naturalmente, se si richiedono parametri che non sono configurati nel contenitore dei servizi usato da ASP.NET Core, viene generata un'eccezione, ma se le richieste si limitano alle dipendenze riconosciute dal contenitore, sarà possibile richiedere qualsiasi elemento.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-172">Of course, if you request parameters that aren't configured in the services container used by ASP.NET Core, you'll get an exception, but as long as you stick to dependencies the container knows about, you can request anything you want.</span></span>

<span data-ttu-id="4b3d2-173">L'inserimento di dipendenze è incorporato nelle app ASP.NET Core sin dall'inizio, ovvero dalla creazione dell'istanza di Startup.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-173">Dependency injection is built into your ASP.NET Core apps right from the start, when you create the Startup instance.</span></span> <span data-ttu-id="4b3d2-174">Non viene interrotto per la classe Startup.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-174">It doesn't stop there for the Startup class.</span></span> <span data-ttu-id="4b3d2-175">È possibile richiedere le dipendenze anche nel metodo Configure:</span><span class="sxs-lookup"><span data-stu-id="4b3d2-175">You can also request dependencies in the Configure method:</span></span>

```csharp
public void Configure(IApplicationBuilder app,
    IHostingEnvironment env,
    ILoggerFactory loggerFactory)
{

}
```

<span data-ttu-id="4b3d2-176">Il metodo ConfigureServices rappresenta l'eccezione a questo comportamento. Il metodo deve ricevere un solo parametro di tipo IServiceCollection.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-176">The ConfigureServices method is the exception to this behavior; it must take just one parameter of type IServiceCollection.</span></span> <span data-ttu-id="4b3d2-177">Non necessita del supporto dell'inserimento delle dipendenze poiché da un lato è responsabile dell'aggiunta degli oggetti al contenitore dei servizi e dall'altro ha accesso a tutti i servizi correntemente configurati tramite il parametro IServiceCollection.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-177">It doesn't really need to support dependency injection, since on the one hand it is responsible for adding objects to the services container, and on the other it has access to all currently configured services via the IServiceCollection parameter.</span></span> <span data-ttu-id="4b3d2-178">Per questa ragione, è possibile usare le dipendenze definite nella raccolta di servizi di ASP.NET Core in ogni parte della classe Startup, richiedendo il servizi necessario come parametro o usando IServiceCollection in ConfigureServices.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-178">Thus, you can work with dependencies defined in the ASP.NET Core services collection in every part of the Startup class, either by requesting the needed service as a parameter or by working with the IServiceCollection in ConfigureServices.</span></span>

> [!NOTE]
> <span data-ttu-id="4b3d2-179">Se è necessario garantire che alcuni servizi siano disponibili per la classe Startup, è possibile configurarli usando WebHostBuilder e il relativo metodo ConfigureServices.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-179">If you need to ensure certain services are available to your Startup class, you can configure them using WebHostBuilder and its ConfigureServices method.</span></span>

<span data-ttu-id="4b3d2-180">La classe Startup costituisce un modello per la struttura delle altre parti dell'applicazione ASP.NET Core, dai controller al middleware e dai filtri ai servizi.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-180">The Startup class is a model for how you should structure other parts of your ASP.NET Core application, from Controllers to Middleware to Filters to your own Services.</span></span> <span data-ttu-id="4b3d2-181">In ogni caso, è necessario seguire il [principio delle dipendenze esplicite](https://deviq.com/explicit-dependencies-principle/) richiedendo le dipendenze anziché crearle direttamente e usando l'inserimento di dipendenze in tutta l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-181">In each case, you should follow the [Explicit Dependencies Principle](https://deviq.com/explicit-dependencies-principle/), requesting your dependencies rather than directly creating them, and leveraging dependency injection throughout your application.</span></span> <span data-ttu-id="4b3d2-182">Prestare attenzione alla posizione e alla modalità di creazione diretta delle istanze delle implementazioni, in particolare dei servizi e degli oggetti che usano l'infrastruttura o presentano effetti collaterali.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-182">Be careful of where and how you directly instantiate implementations, especially services and objects that work with infrastructure or have side effects.</span></span> <span data-ttu-id="4b3d2-183">Preferire l'uso di astrazioni definite nell'applicazione e passate come argomenti anziché l'uso di riferimenti hardcoded a tipi di implementazione specifici.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-183">Prefer working with abstractions defined in your application core and passed in as arguments to hardcoding references to specific implementation types.</span></span>

## <a name="structuring-the-application"></a><span data-ttu-id="4b3d2-184">Creazione della struttura dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="4b3d2-184">Structuring the application</span></span>

<span data-ttu-id="4b3d2-185">Le applicazioni monolitiche hanno in genere un singolo punto di ingresso.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-185">Monolithic applications typically have a single entry point.</span></span> <span data-ttu-id="4b3d2-186">In un'applicazione Web ASP.NET Core il punto di ingresso sarà il progetto Web ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-186">In the case of an ASP.NET Core web application, the entry point will be the ASP.NET Core web project.</span></span> <span data-ttu-id="4b3d2-187">Tuttavia, ciò non significa che la soluzione deve essere costituita da un singolo progetto.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-187">However, that doesn't mean the solution should consist of just a single project.</span></span> <span data-ttu-id="4b3d2-188">È utile suddividere l'applicazione in livelli diversi per riflettere la separazione delle competenze.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-188">It's useful to break up the application into different layers in order to follow separation of concerns.</span></span> <span data-ttu-id="4b3d2-189">Dopo la suddivisione in livelli, è utile andare oltre le cartelle per separare i progetti per ottenere un miglior incapsulamento.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-189">Once broken up into layers, it's helpful to go beyond folders to separate projects, which can help achieve better encapsulation.</span></span> <span data-ttu-id="4b3d2-190">L'approccio migliore per raggiungere questi obiettivi con un'applicazione ASP.NET Core è una variante dell'architettura "pulita" descritta nel capitolo 5.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-190">The best approach to achieve these goals with an ASP.NET Core application is a variation of the Clean Architecture discussed in chapter 5.</span></span> <span data-ttu-id="4b3d2-191">Seguendo questo approccio, la soluzione dell'applicazione sarà costituita da librerie separate per interfaccia utente, infrastruttura e ApplicationCore.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-191">Following this approach, the application's solution will be comprised of separate libraries for the UI, Infrastructure, and ApplicationCore.</span></span>

<span data-ttu-id="4b3d2-192">Oltre a questi progetti, sono inclusi anche i progetti di test separati (i test sono descritti nel capitolo 9).</span><span class="sxs-lookup"><span data-stu-id="4b3d2-192">In addition to these projects, separate test projects are included as well (Testing is discussed in Chapter 9).</span></span>

<span data-ttu-id="4b3d2-193">Il modello a oggetti e le interfacce dell'applicazione devono trovarsi nel progetto ApplicationCore.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-193">The application's object model and interfaces should be placed in the ApplicationCore project.</span></span> <span data-ttu-id="4b3d2-194">Questo progetto avrà il minor numero possibile di dipendenze e gli altri progetti nella soluzione faranno riferimento ad esso.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-194">This project will have as few dependencies as possible, and the other projects in the solution will reference it.</span></span> <span data-ttu-id="4b3d2-195">Le entità di business che devono essere mantenute sono definite nel progetto ApplicationCore, analogamente ai servizi che non dipendono direttamente dall'infrastruttura.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-195">Business entities that need to be persisted are defined in the ApplicationCore project, as are services that do not directly depend on infrastructure.</span></span>

<span data-ttu-id="4b3d2-196">I dettagli di implementazione, ad esempio la modalità di persistenza o di invio delle notifiche a un utente, si trovano nel progetto Infrastructure.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-196">Implementation details, such as how persistence is performed or how notifications might be sent to a user, are kept in the Infrastructure project.</span></span> <span data-ttu-id="4b3d2-197">Il progetto farà riferimento a pacchetti specifici dell'implementazione, ad esempio Entity Framework Core, ma non deve esporre informazioni dettagliate su queste implementazioni all'esterno del progetto.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-197">This project will reference implementation-specific packages such as Entity Framework Core, but should not expose details about these implementations outside of the project.</span></span> <span data-ttu-id="4b3d2-198">I servizi e i repository dell'infrastruttura devono implementare interfacce definite nel progetto ApplicationCore e le relative implementazioni della persistenza sono responsabili del recupero e dell'archiviazione delle entità definite in ApplicationCore.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-198">Infrastructure services and repositories should implement interfaces that are defined in the ApplicationCore project, and its persistence implementations are responsible for retrieving and storing entities defined in ApplicationCore.</span></span>

<span data-ttu-id="4b3d2-199">Il progetto dell'interfaccia utente ASP.NET Core è responsabile di tutte le competenze a livello dell'interfaccia utente, ma non deve includere la logica di business o i dettagli dell'infrastruttura.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-199">The ASP.NET Core UI project is responsible for any UI level concerns, but should not include business logic or infrastructure details.</span></span> <span data-ttu-id="4b3d2-200">Di fatto, il progetto non deve includere alcuna dipendenza nel progetto Infrastructure in modo che non venga inserita accidentalmente alcuna dipendenza tra i due progetti.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-200">In fact, ideally it shouldn't even have a dependency on the Infrastructure project, which will help ensure no dependency between the two projects is introduced accidentally.</span></span> <span data-ttu-id="4b3d2-201">Questo obiettivo può essere raggiunto usando un contenitore DI di terze parti come StructureMap che consente di definire le regole DI nelle classi Registry in ogni progetto.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-201">This can be achieved using a third-party DI container like StructureMap, which allows you to define DI rules in Registry classes in each project.</span></span>

<span data-ttu-id="4b3d2-202">Un altro approccio per disaccoppiare l'applicazione dai dettagli di implementazione consiste nel fare in modo che l'applicazione chiami i microservizi, forse distribuiti in singoli contenitori Docker.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-202">Another approach to decoupling the application from implementation details is to have the application call microservices, perhaps deployed in individual Docker containers.</span></span> <span data-ttu-id="4b3d2-203">Ciò offre una separazione delle competenze e un disaccoppiamento maggiori rispetto all'utilizzo di DI tra due progetti ma comporta una maggiore complessità.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-203">This provides even greater separation of concerns and decoupling than leveraging DI between two projects, but has additional complexity.</span></span>

### <a name="feature-organization"></a><span data-ttu-id="4b3d2-204">Organizzazione basata sulle funzionalità</span><span class="sxs-lookup"><span data-stu-id="4b3d2-204">Feature organization</span></span>

<span data-ttu-id="4b3d2-205">Per impostazione predefinita, le applicazioni ASP.NET Core organizzano la struttura delle cartelle in modo da includere controller e visualizzazioni e spesso modelli di visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-205">By default, ASP.NET Core applications organize their folder structure to include Controllers and Views, and frequently ViewModels.</span></span> <span data-ttu-id="4b3d2-206">Il codice lato client per supportare queste strutture lato server è in genere archiviato separatamente nella cartella wwwroot.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-206">Client-side code to support these server-side structures is typically stored separately in the wwwroot folder.</span></span> <span data-ttu-id="4b3d2-207">Questa organizzazione, tuttavia, può creare problemi nelle applicazioni di grandi dimensioni poiché l'utilizzo di qualsiasi funzionalità specificata richiede spesso il passaggio da una cartella all'altra.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-207">However, large applications may encounter problems with this organization, since working on any given feature often requires jumping between these folders.</span></span> <span data-ttu-id="4b3d2-208">Questa operazione diventa ancora più complessa con un numero più elevato di file e sottocartelle in ogni cartella richiedendo un maggior esplorazione in Esplora soluzioni.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-208">This gets more and more difficult as the number of files and subfolders in each folder grows, resulting in a great deal of scrolling through Solution Explorer.</span></span> <span data-ttu-id="4b3d2-209">Per risolvere questo problema è possibile organizzare il codice dell'applicazione per _funzionalità_ anziché per tipo di file.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-209">One solution to this problem is to organize application code by _feature_ instead of by file type.</span></span> <span data-ttu-id="4b3d2-210">Questo tipo di organizzazione viene solitamente chiamato "cartelle di funzionalità" o "sezioni di funzionalità". Vedere anche [Vertical Slices](https://deviq.com/vertical-slices/) (Sezioni verticali).</span><span class="sxs-lookup"><span data-stu-id="4b3d2-210">This organizational style is typically referred to as feature folders or feature slices (see also: [Vertical Slices](https://deviq.com/vertical-slices/)).</span></span>

<span data-ttu-id="4b3d2-211">A tale scopo, ASP.NET Core MVC supporta le aree.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-211">ASP.NET Core MVC supports Areas for this purpose.</span></span> <span data-ttu-id="4b3d2-212">Usando le aree è possibile creare set separati di cartelle di controller e visualizzazioni, inclusi i modelli associati, in ogni cartella Area.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-212">Using areas, you can create separate sets of Controllers and Views folders (as well as any associated models) in each Area folder.</span></span> <span data-ttu-id="4b3d2-213">La figure 7-1 illustra un esempio di struttura di cartelle con aree.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-213">Figure 7-1 shows an example folder structure, using Areas.</span></span>

![](./media/image7-1.png)

<span data-ttu-id="4b3d2-214">Figura 7-1 Organizzazione di aree di esempio</span><span class="sxs-lookup"><span data-stu-id="4b3d2-214">Figure 7-1 Sample Area Organization</span></span>

<span data-ttu-id="4b3d2-215">Quando si usano le aree, è necessario usare gli attributi per decorare i controller con il nome dell'area a cui appartengono:</span><span class="sxs-lookup"><span data-stu-id="4b3d2-215">When using Areas, you must use attributes to decorate your controllers with the name of the area to which they belong:</span></span>

```csharp
[Area("Catalog")]
public class HomeController
{}
```

<span data-ttu-id="4b3d2-216">È anche necessario aggiungere il supporto delle aree alle route:</span><span class="sxs-lookup"><span data-stu-id="4b3d2-216">You also need to add area support to your routes:</span></span>

```csharp
app.UseMvc(routes =>
{
    // Areas support
    routes.MapRoute(
    name: "areaRoute",
    template: "{area:exists}/{controller=Home}/{action=Index}/{id?}");
    routes.MapRoute(
    name: "default",
    template: "{controller=Home}/{action=Index}/{id?}");
});
```

<span data-ttu-id="4b3d2-217">Oltre al supporto incorporato per le aree, è possibile usare anche la propria struttura di cartelle e le convenzioni al posto di attributi e route personalizzate.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-217">In addition to the built-in support for Areas, you can also use your own folder structure, and conventions in place of attributes and custom routes.</span></span> <span data-ttu-id="4b3d2-218">Ciò consentirebbe di avere cartelle di funzionalità che non includano cartelle separate per le visualizzazioni, i controller e così via, creando in questo modo una gerarchia più piana e rendendo più semplice visualizzare tutti i file correlati in un'unica posizione per ogni funzionalità.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-218">This would allow you to have feature folders that didn't include separate folders for Views, Controllers, etc., keeping the hierarchy flatter and making it easier to see all related files in a single place for each feature.</span></span>

<span data-ttu-id="4b3d2-219">ASP.NET Core usa tipi convenzione predefiniti per controllare il comportamento.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-219">ASP.NET Core uses built-in convention types to control its behavior.</span></span> <span data-ttu-id="4b3d2-220">È possibile modificare o sostituire queste convenzioni.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-220">You can modify or replace these conventions.</span></span> <span data-ttu-id="4b3d2-221">Ad esempio, è possibile creare una convenzione che ottiene automaticamente il nome della funzionalità per un controller specifico in base al relativo spazio dei nomi (che in genere è correlato alla cartella in cui si trova il controller):</span><span class="sxs-lookup"><span data-stu-id="4b3d2-221">For example, you can create a convention that will automatically get the feature name for a given controller based on its namespace (which typically correlates to the folder in which the controller is located):</span></span>

```csharp
FeatureConvention : IControllerModelConvention
{
    public void Apply(ControllerModel controller)
    {
        controller.Properties.Add("feature",
        GetFeatureName(controller.ControllerType));
    }

    private string GetFeatureName(TypeInfo controllerType)
    {
        string[] tokens = controllerType.FullName.Split('.');
        if (!tokens.Any(t => t == "Features")) return "";
        string featureName = tokens
        .SkipWhile(t => !t.Equals("features",
        StringComparison.CurrentCultureIgnoreCase))
        .Skip(1)
        .Take(1)
        .FirstOrDefault();
        return featureName;
    }
}
```

<span data-ttu-id="4b3d2-222">Specificare quindi questa convenzione come opzione quando si aggiunge il supporto per MVC all'applicazione in ConfigureServices:</span><span class="sxs-lookup"><span data-stu-id="4b3d2-222">You then specify this convention as an option when you add support for MVC to your application in ConfigureServices:</span></span>

```csharp
services.AddMvc(o => o.Conventions.Add(new FeatureConvention()));
```

<span data-ttu-id="4b3d2-223">ASP.NET Core MVC usa una convenzione anche per individuare le visualizzazioni.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-223">ASP.NET Core MVC also uses a convention to locate views.</span></span> <span data-ttu-id="4b3d2-224">Questa convenzione può essere sostituita con una convenzione personalizzata in modo che le visualizzazioni vengano inserite nelle cartelle delle funzionalità (usando il nome della funzionalità specificato da FeatureConvention).</span><span class="sxs-lookup"><span data-stu-id="4b3d2-224">You can override it with a custom convention so that views will be located in your feature folders (using the feature name provided by the FeatureConvention, above).</span></span> <span data-ttu-id="4b3d2-225">Per altre informazioni su questo approccio e per scaricare un esempio funzionante, vedere l'articolo di MSDN [Feature Slices for ASP.NET Core MVC](https://msdn.microsoft.com/magazine/mt763233.aspx) (Sezioni di funzionalità per ASP.NET Core MVC).</span><span class="sxs-lookup"><span data-stu-id="4b3d2-225">You can learn more about this approach and download a working sample from the MSDN article, [Feature Slices for ASP.NET Core MVC](https://msdn.microsoft.com/magazine/mt763233.aspx).</span></span>

### <a name="cross-cutting-concerns"></a><span data-ttu-id="4b3d2-226">Problemi di montaggio incrociato</span><span class="sxs-lookup"><span data-stu-id="4b3d2-226">Cross-cutting concerns</span></span>

<span data-ttu-id="4b3d2-227">Con l'aumento delle dimensioni delle applicazioni, diventa sempre più importante evitare i problemi di cross-cutting per eliminare la duplicazione e mantenere la coerenza.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-227">As applications grow, it becomes increasingly important to factor out cross-cutting concerns to eliminate duplication and maintain consistency.</span></span> <span data-ttu-id="4b3d2-228">Alcuni esempi di problemi di cross-cutting nelle applicazioni ASP.NET Core sono, tra gli altri, l'autenticazione, le regole di convalida del modello, la memorizzazione nella cache dell'output e la gestione degli errori.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-228">Some examples of cross-cutting concerns in ASP.NET Core applications are authentication, model validation rules, output caching, and error handling, though there are many others.</span></span> <span data-ttu-id="4b3d2-229">I [filtri](/aspnet/core/mvc/controllers/filters) di ASP.NET Core MVC consentono di eseguire codice prima o dopo determinate fasi della pipeline di elaborazione della richiesta.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-229">ASP.NET Core MVC [filters](/aspnet/core/mvc/controllers/filters) allow you to run code before or after certain steps in the request processing pipeline.</span></span> <span data-ttu-id="4b3d2-230">Ad esempio, un filtro può essere eseguito prima e dopo l'associazione di modelli, prima e dopo un'azione o prima e dopo il risultato di un'azione.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-230">For instance, a filter can run before and after model binding, before and after an action, or before and after an action's result.</span></span> <span data-ttu-id="4b3d2-231">È anche possibile usare un filtro di autorizzazione per controllare l'accesso alla parte rimanente della pipeline.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-231">You can also use an authorization filter to control access to the rest of the pipeline.</span></span> <span data-ttu-id="4b3d2-232">La figura 7-2 mostra l'esecuzione della richiesta attraverso i filtri, se configurati.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-232">Figures 7-2 shows how request execution flows through filters, if configured.</span></span>

![La richiesta passa attraverso i filtri autorizzazione, i filtri risorse, l'associazione di modelli, i filtri azione, l'esecuzione dell'azione e la conversione del risultato dell'azione, i filtri eccezioni, i filtri risultato e l'esecuzione del risultato.](./media/image7-2.png)

<span data-ttu-id="4b3d2-235">Figura 7-2 Esecuzione della richiesta attraverso i filtri e pipeline della richiesta.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-235">Figure 7-2 Request execution through filters and request pipeline.</span></span>

<span data-ttu-id="4b3d2-236">Poiché i filtri vengono in genere implementati come attributi, è possibile applicare controller o azioni ai filtri.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-236">Filters are usually implemented as attributes, so you can apply them controllers or actions.</span></span> <span data-ttu-id="4b3d2-237">Quando vengono aggiunti in questo modo, i filtri specificati a livello di azione sostituiscono o sono basati sui filtri specificati a livello di controller che a loro volta sostituiscono i filtri globali.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-237">When added in this fashion, filters specified at the action level override or build upon filters specified at the controller level, which themselves override global filters.</span></span> <span data-ttu-id="4b3d2-238">È possibile ad esempio usare l'attributo \[Route\] per creare route tra i controller e le azioni.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-238">For example, the \[Route\] attribute can be used to build up routes between controllers and actions.</span></span> <span data-ttu-id="4b3d2-239">Analogamente, l'autorizzazione può essere configurata a livello di controller e quindi sostituita da singole azioni, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="4b3d2-239">Likewise, authorization can be configured at the controller level, and then overridden by individual actions, as the following sample demonstrates:</span></span>

```csharp
[Authorize]
public class AccountController : Controller

{
    [AllowAnonymous]
    public async Task<IActionResult> Login() {}
    public async Task<IActionResult> ForgotPassword() {}
}
```

<span data-ttu-id="4b3d2-240">Il primo metodo, Login, usa il filtro AllowAnonymous (attributo) per sostituire il filtro Authorize impostato a livello di controller.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-240">The first method, Login, uses the AllowAnonymous filter (attribute) to override the Authorize filter set at the controller level.</span></span> <span data-ttu-id="4b3d2-241">L'azione ForgotPassword (e qualsiasi altra azione nella classe che non ha un attributo AllowAnonymous) richiederà una richiesta autenticata.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-241">The ForgotPassword action (and any other action in the class that doesn't have an AllowAnonymous attribute) will require an authenticated request.</span></span>

<span data-ttu-id="4b3d2-242">È possibile usare i filtri per eliminare la duplicazione come criteri di gestione degli errori comuni delle API.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-242">Filters can be used to eliminate duplication in the form of common error handling policies for APIs.</span></span> <span data-ttu-id="4b3d2-243">Ad esempio, un criterio di API tipico consiste nel restituire una risposta NotFound alle richieste che fanno riferimento a chiavi non esistenti e una risposta BadRequest nei casi in cui la convalida del modello ha esito negativo.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-243">For example, a typical API policy is to return a NotFound response to requests referencing keys that do not exist, and a BadRequest response if model validation fails.</span></span> <span data-ttu-id="4b3d2-244">L'esempio seguente illustrate questi due criteri:</span><span class="sxs-lookup"><span data-stu-id="4b3d2-244">The following example demonstrates these two policies in action:</span></span>

```csharp
[HttpPut("{id}")]
public async Task<IActionResult> Put(int id, [FromBody]Author author)
{
    if ((await _authorRepository.ListAsync()).All(a => a.Id != id))
    {
        return NotFound(id);
    }
    if (!ModelState.IsValid)
    {
        return BadRequest(ModelState);
    }
    author.Id = id;
    await _authorRepository.UpdateAsync(author);
    return Ok();
}
```

<span data-ttu-id="4b3d2-245">Evitare che i metodi di azione diventino troppo pieni con codice condizionale di questo tipo.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-245">Don't allow your action methods to become cluttered with conditional code like this.</span></span> <span data-ttu-id="4b3d2-246">Eseguire invece il pull dei criteri nei filtri che possono essere applicati quando necessario.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-246">Instead, pull the policies into filters that can be applied on an as-needed basis.</span></span> <span data-ttu-id="4b3d2-247">In questo esempio la convalida del modello che dovrebbe verificarsi ogni volta che viene inviato un comando all'API può essere sostituita dall'attributo seguente:</span><span class="sxs-lookup"><span data-stu-id="4b3d2-247">In this example, the model validation check, which should occur any time a command is sent to the API, can be replaced by the following attribute:</span></span>

```csharp
public class ValidateModelAttribute : ActionFilterAttribute
{
    public override void OnActionExecuting(ActionExecutingContext context)
    {
        if (!context.ModelState.IsValid)
        {
            context.Result = new BadRequestObjectResult(context.ModelState);
        }
    }
}
```

<span data-ttu-id="4b3d2-248">Analogamente, è possibile usare un filtro per verificare l'esistenza di un record e restituire un errore 404 prima che venga eseguita l'azione, eliminando la necessità di eseguire questi controlli nell'azione.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-248">Likewise, a filter can be used to check if a record exists and return a 404 before the action is executed, eliminating the need to perform these checks in the action.</span></span> <span data-ttu-id="4b3d2-249">Dopo aver estratto le convenzioni comuni e aver organizzato la soluzione per separare il codice dell'infrastruttura e la logica di business dall'interfaccia utente, i metodi delle azioni MVC dovrebbero essere estremamente snelli:</span><span class="sxs-lookup"><span data-stu-id="4b3d2-249">Once you've pulled out common conventions and organized your solution to separate infrastructure code and business logic from your UI, your MVC action methods should be extremely thin:</span></span>

```csharp
[HttpPut("{id}")]
[ValidateAuthorExists]
public async Task<IActionResult> Put(int id, [FromBody]Author author)
{
    await _authorRepository.UpdateAsync(author);
    return Ok();
}
```

<span data-ttu-id="4b3d2-250">Per altre informazioni sull'implementazione di filtri e per scaricare un esempio funzionante, vedere l'articolo di MSDN [Filtri reali di ASP.NET Core MVC](https://msdn.microsoft.com/magazine/mt767699.aspx).</span><span class="sxs-lookup"><span data-stu-id="4b3d2-250">You can read more about implementing filters and download a working sample from the MSDN article, [Real World ASP.NET Core MVC Filters](https://msdn.microsoft.com/magazine/mt767699.aspx).</span></span>

> ### <a name="references--structuring-applications"></a><span data-ttu-id="4b3d2-251">Riferimenti - Creazione della struttura delle applicazioni</span><span class="sxs-lookup"><span data-stu-id="4b3d2-251">References – Structuring applications</span></span>
>
> - <span data-ttu-id="4b3d2-252">**Aree**</span><span class="sxs-lookup"><span data-stu-id="4b3d2-252">**Areas**</span></span>  
>   <https://docs.microsoft.com/aspnet/core/mvc/controllers/areas>
> - <span data-ttu-id="4b3d2-253">**MSDN Magazine - Funzionalità Feature Slices per ASP.NET Core MVC**</span><span class="sxs-lookup"><span data-stu-id="4b3d2-253">**MSDN Magazine – Feature Slices for ASP.NET Core MVC**</span></span>  
 > <https://msdn.microsoft.com/magazine/mt763233.aspx>
> - <span data-ttu-id="4b3d2-254">**Filtri**</span><span class="sxs-lookup"><span data-stu-id="4b3d2-254">**Filters**</span></span>  
>   <https://docs.microsoft.com/aspnet/core/mvc/controllers/filters>
> - <span data-ttu-id="4b3d2-255">**MSDN - Real World ASP.NET Core MVC Filters (MSDN - Filtri reali di ASP.NET Core MVC)**</span><span class="sxs-lookup"><span data-stu-id="4b3d2-255">**MSDN – Real World ASP.NET Core MVC Filters**</span></span>  
>   <https://msdn.microsoft.com/magazine/mt767699.aspx>

## <a name="security"></a><span data-ttu-id="4b3d2-256">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="4b3d2-256">Security</span></span>

<span data-ttu-id="4b3d2-257">La protezione delle applicazioni Web è un argomento molto ampio con numerose considerazioni.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-257">Securing web applications is a large topic, with many considerations.</span></span> <span data-ttu-id="4b3d2-258">A un livello di base, per garantire la sicurezza è necessario conoscere l'identità dell'utente da cui proviene una determinata richiesta e assicurarsi che la richiesta abbia accesso solo alle risorse necessarie.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-258">At its most basic level, security involves ensuring you know who a given request is coming from, and then ensuring that the request only has access to resources it should.</span></span> <span data-ttu-id="4b3d2-259">L'autenticazione è il processo di confronto delle credenziali specificate con una richiesta con quelle di un archivio di dati attendibili per verificare se la richiesta deve essere trattata come proveniente da un'entità nota.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-259">Authentication is the process of comparing credentials provided with a request to those in a trusted data store, to see if the request should be treated as coming from a known entity.</span></span> <span data-ttu-id="4b3d2-260">L'autorizzazione è il processo di limitazione dell'accesso a determinate risorse in base all'identità utente.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-260">Authorization is the process of restricting access to certain resources based on user identity.</span></span> <span data-ttu-id="4b3d2-261">Un terzo aspetto relativo alla sicurezza è la protezione delle richieste dall'intercettazione da terze parti per cui è necessario [assicurarsi che l'applicazione usi SSL](/aspnet/core/security/enforcing-ssl).</span><span class="sxs-lookup"><span data-stu-id="4b3d2-261">A third security concern is protecting requests from eavesdropping by third parties, for which you should at least [ensure that SSL is used by your application](/aspnet/core/security/enforcing-ssl).</span></span>

### <a name="authentication"></a><span data-ttu-id="4b3d2-262">Autenticazione</span><span class="sxs-lookup"><span data-stu-id="4b3d2-262">Authentication</span></span>

<span data-ttu-id="4b3d2-263">ASP.NET Core Identity è un sistema di appartenenza che è possibile usare per supportare la funzionalità di accesso per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-263">ASP.NET Core Identity is a membership system you can use to support login functionality for your application.</span></span> <span data-ttu-id="4b3d2-264">Include il supporto degli account utente locali e il supporto dei provider di accesso esterni come l'account Microsoft, Twitter, Facebook, Google e altri ancora.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-264">It has support for local user accounts as well as external login provider support from providers like Microsoft Account, Twitter, Facebook, Google, and more.</span></span> <span data-ttu-id="4b3d2-265">Oltre a ASP.NET Core Identity, l'applicazione può usare l'autenticazione di Windows o un provider di identità di terze parti come [Identity Server](https://github.com/IdentityServer/IdentityServer4).</span><span class="sxs-lookup"><span data-stu-id="4b3d2-265">In addition to ASP.NET Core Identity, your application can use windows authentication, or a third-party identity provider like [Identity Server](https://github.com/IdentityServer/IdentityServer4).</span></span>

<span data-ttu-id="4b3d2-266">ASP.NET Core Identity è incluso nei nuovi modelli di progetto se l'opzione Account utente individuali è selezionata.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-266">ASP.NET Core Identity is included in new project templates if the Individual User Accounts option is selected.</span></span> <span data-ttu-id="4b3d2-267">Questo modello include il supporto per la registrazione, l'accesso, gli accessi esterni, le password dimenticate e funzionalità aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-267">This template includes support for registration, login, external logins, forgotten passwords, and additional functionality.</span></span>

![](./media/image7-3.png)

<span data-ttu-id="4b3d2-268">Figura 7-3 Selezionare Account utente individuali per preconfigurare Identity.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-268">Figure 7-3 Select Individual User Accounts to have Identity preconfigured.</span></span>

<span data-ttu-id="4b3d2-269">Il supporto di Identity è configurato in Startup, sia in ConfigureServices che in Configure:</span><span class="sxs-lookup"><span data-stu-id="4b3d2-269">Identity support is configured in Startup, both in ConfigureServices and Configure:</span></span>

```csharp
public void ConfigureServices(IServiceCollection services)
{
    // Add framework services.
    services.AddDbContext<ApplicationDbContext>(options =>
    options.UseSqlServer(Configuration.GetConnectionString("DefaultConnection")));
    services.AddIdentity<ApplicationUser, IdentityRole>()
    .AddEntityFrameworkStores<ApplicationDbContext>()
    .AddDefaultTokenProviders();
    services.AddMvc();
}

public void Configure(IApplicationBuilder app)
{
    app.UseStaticFiles();
    app.UseIdentity();
    app.UseMvc(routes =>
    {
        routes.MapRoute(
        name: "default",
        template: "{controller=Home}/{action=Index}/{id?}");
    });
}
```

<span data-ttu-id="4b3d2-270">È importante che UseIdentity si trovi prima di UseMvc nel metodo Configure.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-270">It's important that UseIdentity appear before UseMvc in the Configure method.</span></span> <span data-ttu-id="4b3d2-271">Quando si configura Identity in ConfigureServices, è possibile notare una chiamata ad AddDefaultTokenProviders.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-271">When configuring Identity in ConfigureServices, you'll notice a call to AddDefaultTokenProviders.</span></span> <span data-ttu-id="4b3d2-272">La chiamata non è correlata ai token che possono essere usati per proteggere le connessioni Web, ma fa riferimento ai provider che creano prompt che è possibile inviare agli utenti tramite SMS o posta elettronica per la conferma dell'identità.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-272">This has nothing to do with tokens that may be used to secure web communications, but instead refers to providers that create prompts that can be sent to users via SMS or email in order for them to confirm their identity.</span></span>

<span data-ttu-id="4b3d2-273">Per altre informazioni sulla [configurazione dell'autenticazione a due fattori](/aspnet/core/security/authentication/2fa) e l'[abilitazione di provider di accesso esterni](/aspnet/core/security/authentication/social/), vedere la documentazione ufficiale di ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-273">You can learn more about [configuring two-factor authentication](/aspnet/core/security/authentication/2fa) and [enabling external login providers](/aspnet/core/security/authentication/social/) from the official ASP.NET Core docs.</span></span>

### <a name="authorization"></a><span data-ttu-id="4b3d2-274">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="4b3d2-274">Authorization</span></span>

<span data-ttu-id="4b3d2-275">La forma di autorizzazione più semplice prevede la limitazione dell'accesso per gli utenti anonimi.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-275">The simplest form of authorization involves restricting access to anonymous users.</span></span> <span data-ttu-id="4b3d2-276">La limitazione può essere ottenuta semplicemente applicando l'attributo \[Authorize\] a determinati controller o azioni.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-276">This can be achieved by simply applying the \[Authorize\] attribute to certain controllers or actions.</span></span> <span data-ttu-id="4b3d2-277">Se vengono usati i ruoli, è possibile estendere ulteriormente l'attributo per limitare l'accesso agli utenti che appartengono a determinati ruoli, come illustrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="4b3d2-277">If roles are being used, the attribute can be further extended to restrict access to users who belong to certain roles, as shown:</span></span>

```csharp
[Authorize(Roles = "HRManager,Finance")]
public class SalaryController : Controller
{

}
```

<span data-ttu-id="4b3d2-278">In questo caso gli utenti che appartengono al ruolo HRManager o Finance o a entrambi i ruoli hanno accesso a SalaryController.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-278">In this case, users belonging to either the HRManager or Finance roles (or both) would have access to the SalaryController.</span></span> <span data-ttu-id="4b3d2-279">Per richiedere l'appartenenza di un utente a più ruoli e non a un solo ruolo, è possibile applicare l'attributo più volte specificando ogni volta il ruolo richiesto.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-279">To require that a user belong to multiple roles (not just one of several), you can apply the attribute multiple times, specifying a required role each time.</span></span>

<span data-ttu-id="4b3d2-280">La specifica di determinati set di ruoli come stringhe in diversi controller e azioni può causare una ripetizione indesiderata.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-280">Specifying certain sets of roles as strings in many different controllers and actions can lead to undesirable repetition.</span></span> <span data-ttu-id="4b3d2-281">È possibile configurare criteri di autorizzazione che incapsulano regole di autorizzazione e quindi specificare i criteri anziché i singoli ruoli durante l'applicazione dell'attributo \[Authorize\]:</span><span class="sxs-lookup"><span data-stu-id="4b3d2-281">You can configure authorization policies, which encapsulate authorization rules, and then specify the policy instead of individual roles when applying the \[Authorize\] attribute:</span></span>

```csharp
[Authorize(Policy = "CanViewPrivateReport")]
public IActionResult ExecutiveSalaryReport()
{
    return View();
}
```

<span data-ttu-id="4b3d2-282">Questa modalità di utilizzo dei criteri consente di suddividere i tipi di azione limitati dai ruoli o dalle regole specifiche applicate.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-282">Using policies in this way, you can separate the kinds of actions being restricted from the specific roles or rules that apply to it.</span></span> <span data-ttu-id="4b3d2-283">In seguito, se si crea un nuovo ruolo che necessita dell'accesso a determinate risorse, sarà sufficiente aggiornare i criteri anziché aggiornare ogni elenco di ruoli in ogni attributo \[Authorize\].</span><span class="sxs-lookup"><span data-stu-id="4b3d2-283">Later, if you create a new role that needs to have access to certain resources, you can just update a policy, rather than updating every list of roles on every \[Authorize\] attribute.</span></span>

#### <a name="claims"></a><span data-ttu-id="4b3d2-284">Attestazioni</span><span class="sxs-lookup"><span data-stu-id="4b3d2-284">Claims</span></span>

<span data-ttu-id="4b3d2-285">Le attestazioni sono coppie nome-valore che rappresentano le proprietà di un utente autenticato.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-285">Claims are name value pairs that represent properties of an authenticated user.</span></span> <span data-ttu-id="4b3d2-286">Ad esempio, è possibile archiviare il numero di dipendente degli utenti come attestazione.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-286">For example, you might store users' employee number as a claim.</span></span> <span data-ttu-id="4b3d2-287">Le attestazioni possono quindi essere usate come parte dei criteri di autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-287">Claims can then be used as part of authorization policies.</span></span> <span data-ttu-id="4b3d2-288">È possibile creare un criterio denominato "EmployeeOnly" che richiede l'esistenza di un'attestazione denominata "EmployeeNumber", come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="4b3d2-288">You could create a policy called "EmployeeOnly" that requires the existence of a claim called "EmployeeNumber", as shown in this example:</span></span>

```csharp
public void ConfigureServices(IServiceCollection services)
{
    services.AddMvc();
    services.AddAuthorization(options =>
    {
        options.AddPolicy("EmployeeOnly", policy => policy.RequireClaim("EmployeeNumber"));
    });
}
```

<span data-ttu-id="4b3d2-289">Questo criterio può quindi essere usato con l'attributo \[Authorize\] per proteggere qualsiasi controller e/o azione, come descritto in precedenza.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-289">This policy could then be used with the \[Authorize\] attribute to protect any controller and/or action, as described above.</span></span>

#### <a name="securing-web-apis"></a><span data-ttu-id="4b3d2-290">Protezione delle API Web</span><span class="sxs-lookup"><span data-stu-id="4b3d2-290">Securing web APIs</span></span>

<span data-ttu-id="4b3d2-291">La maggior parte delle API Web deve implementare un sistema di autenticazione basato su token.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-291">Most web APIs should implement a token-based authentication system.</span></span> <span data-ttu-id="4b3d2-292">L'autenticazione del token è progettata per essere scalabile e senza stato.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-292">Token authentication is stateless and designed to be scalable.</span></span> <span data-ttu-id="4b3d2-293">In un sistema di autenticazione basato su token, è necessario che il client esegua prima l'autenticazione nel provider di autenticazione.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-293">In a token-based authentication system, the client must first authenticate with the authentication provider.</span></span> <span data-ttu-id="4b3d2-294">Se l'autenticazione ha esito positivo, per il client viene emesso un token che è costituito semplicemente da una stringa di caratteri crittograficamente significativa.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-294">If successful, the client is issued a token, which is simply a cryptographically meaningful string of characters.</span></span> <span data-ttu-id="4b3d2-295">Per inviare una richiesta a un'API, il client aggiunge il token come intestazione della richiesta.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-295">When the client then needs to issue a request to an API, it adds this token as a header on the request.</span></span> <span data-ttu-id="4b3d2-296">Il server convalida il token individuato nell'intestazione della richiesta prima di eseguire la richiesta.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-296">The server then validates the token found in the request header before completing the request.</span></span> <span data-ttu-id="4b3d2-297">La figura 7-4 illustra questo processo.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-297">Figure 7-4 demonstrates this process.</span></span>

![TokenAuth](./media/image7-4.png)

<span data-ttu-id="4b3d2-299">**Figura 7-4.**</span><span class="sxs-lookup"><span data-stu-id="4b3d2-299">**Figure 7-4.**</span></span> <span data-ttu-id="4b3d2-300">Autenticazione basata su token per le API Web.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-300">Token-based authentication for Web APIs.</span></span>

> ### <a name="references--security"></a><span data-ttu-id="4b3d2-301">Riferimenti - Sicurezza</span><span class="sxs-lookup"><span data-stu-id="4b3d2-301">References – Security</span></span>
>
> - <span data-ttu-id="4b3d2-302">**Panoramica della documentazione sulla sicurezza**</span><span class="sxs-lookup"><span data-stu-id="4b3d2-302">**Security Docs Overview**</span></span>  
>   https://docs.microsoft.com/aspnet/core/security/
> - <span data-ttu-id="4b3d2-303">**Applicazione di SSL in un'app ASP.NET Core**</span><span class="sxs-lookup"><span data-stu-id="4b3d2-303">**Enforcing SSL in an ASP.NET Core App**</span></span>  
>   <https://docs.microsoft.com/aspnet/core/security/enforcing-ssl>
> - <span data-ttu-id="4b3d2-304">**Introduzione a Identity**</span><span class="sxs-lookup"><span data-stu-id="4b3d2-304">**Introduction to Identity**</span></span>  
>   <https://docs.microsoft.com/aspnet/core/security/authentication/identity>
> - <span data-ttu-id="4b3d2-305">**Introduzione alle autorizzazioni**</span><span class="sxs-lookup"><span data-stu-id="4b3d2-305">**Introduction to Authorization**</span></span>  
>   <https://docs.microsoft.com/aspnet/core/security/authorization/introduction>
> - <span data-ttu-id="4b3d2-306">**Autenticazione e autorizzazione per app per le API nel servizio app di Azure**</span><span class="sxs-lookup"><span data-stu-id="4b3d2-306">**Authentication and Authorization for API Apps in Azure App Service**</span></span>  
>   <https://docs.microsoft.com/azure/app-service-api/app-service-api-authentication>

## <a name="client-communication"></a><span data-ttu-id="4b3d2-307">Comunicazione con i client</span><span class="sxs-lookup"><span data-stu-id="4b3d2-307">Client communication</span></span>

<span data-ttu-id="4b3d2-308">Oltre a visualizzare le pagine e a rispondere alle richieste di dati tramite le API Web, le app ASP.NET Core possono comunicare direttamente con i client connessi.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-308">In addition to serving pages and responding to requests for data via web APIs, ASP.NET Core apps can communicate directly with connected clients.</span></span> <span data-ttu-id="4b3d2-309">Questa comunicazione in uscita può usare diverse tecnologie di trasporto, tra cui la più comune sono i WebSocket.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-309">This outbound communication can use a variety of transport technologies, the most common being WebSockets.</span></span> <span data-ttu-id="4b3d2-310">ASP.NET ASP.NET Core SignalR è una libreria che semplifica l'aggiunta della funzionalità di comunicazione da server a client in tempo reale alle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-310">ASP.NET Core SignalR is a library that makes it simple to add real-time server-to-client communication functionality to your applications.</span></span> <span data-ttu-id="4b3d2-311">SignalR supporta diverse tecnologie di trasporto, inclusi i WebSocket, ed elimina molti dei dettagli di implementazione specificati dallo sviluppatore.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-311">SignalR supports a variety of transport technologies, including WebSockets, and abstracts away many of the implementation details from the developer.</span></span>

<span data-ttu-id="4b3d2-312">ASP.NET Core SignalR è incluso in ASP.NET Core 2.1.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-312">ASP.NET Core SignalR is available with ASP.NET Core 2.1.</span></span>

<span data-ttu-id="4b3d2-313">La comunicazione con il client in tempo reale, con l'utilizzo diretto di WebSocket o altre tecniche, è utile in diversi scenari di applicazioni.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-313">Real-time client communication, whether using WebSockets directly or other techniques, are useful in a variety of application scenarios.</span></span> <span data-ttu-id="4b3d2-314">Di seguito sono riportati alcuni esempi:</span><span class="sxs-lookup"><span data-stu-id="4b3d2-314">Some examples include:</span></span>

- <span data-ttu-id="4b3d2-315">Applicazioni live chat room</span><span class="sxs-lookup"><span data-stu-id="4b3d2-315">Live chat room applications</span></span>

- <span data-ttu-id="4b3d2-316">Applicazioni di monitoraggio</span><span class="sxs-lookup"><span data-stu-id="4b3d2-316">Monitoring applications</span></span>

- <span data-ttu-id="4b3d2-317">Aggiornamenti dello stato di processo</span><span class="sxs-lookup"><span data-stu-id="4b3d2-317">Job progress updates</span></span>

- <span data-ttu-id="4b3d2-318">Notifiche</span><span class="sxs-lookup"><span data-stu-id="4b3d2-318">Notifications</span></span>

- <span data-ttu-id="4b3d2-319">Applicazioni di moduli interattivi</span><span class="sxs-lookup"><span data-stu-id="4b3d2-319">Interactive forms applications</span></span>

<span data-ttu-id="4b3d2-320">Quando si definisce la comunicazione con i client nelle applicazioni, vengono in genere usati due componenti:</span><span class="sxs-lookup"><span data-stu-id="4b3d2-320">When building client communication into your applications, there are typically two components:</span></span>

- <span data-ttu-id="4b3d2-321">Gestione della connessione sul lato server (hub SignalR, WebSocketManager, WebSocketHandler)</span><span class="sxs-lookup"><span data-stu-id="4b3d2-321">Server-side connection manager (SignalR Hub, WebSocketManager WebSocketHandler)</span></span>

- <span data-ttu-id="4b3d2-322">Libreria lato client</span><span class="sxs-lookup"><span data-stu-id="4b3d2-322">Client-side library</span></span>

<span data-ttu-id="4b3d2-323">I client non sono costituiti solo da browser. Anche le app per dispositivi mobili, le app della console e altre app native possono comunicare tramite SignalR/WebSocket.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-323">Clients aren't limited to browsers – mobile apps, console apps, and other native apps can also communicate using SignalR/WebSockets.</span></span> <span data-ttu-id="4b3d2-324">Il semplice programma seguente ripete tutto il contenuto inviato a un'applicazione chat alla console, come parte di un'applicazione di esempio WebSocketManager:</span><span class="sxs-lookup"><span data-stu-id="4b3d2-324">The following simple program echoes all content sent to a chat application to the console, as part of a WebSocketManager sample application:</span></span>

```csharp
public class Program
{
    private static Connection _connection;
    public static void Main(string[] args)
    {
        StartConnectionAsync();
        _connection.On("receiveMessage", (arguments) =>;
        {
            Console.WriteLine(\$"{arguments\[0\]} said: {arguments\[1\]}");
        });
        Console.ReadLine();
        StopConnectionAsync();
    }

    public static async Task StartConnectionAsync()
    {
        _connection = new Connection();
        await _connection.StartConnectionAsync("ws://localhost:65110/chat");
    }

    public static async Task StopConnectionAsync()
    {
        await _connection.StopConnectionAsync();
    }
}
```

<span data-ttu-id="4b3d2-325">Esaminare i modi in cui le applicazioni comunicano direttamente con le applicazioni client e considerare se la comunicazione in tempo reale migliorerebbe l'esperienza utente dell'app.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-325">Consider ways in which your applications communicate directly with client applications, and consider whether real-time communication would improve your app's user experience.</span></span>

> ### <a name="references--client-communication"></a><span data-ttu-id="4b3d2-326">Riferimenti - Comunicazione con i client</span><span class="sxs-lookup"><span data-stu-id="4b3d2-326">References – Client Communication</span></span>
>
> - <span data-ttu-id="4b3d2-327">**ASP.NET Core SignalR**</span><span class="sxs-lookup"><span data-stu-id="4b3d2-327">**ASP.NET Core SignalR**</span></span>  
>   <https://github.com/aspnet/SignalR>
> - <span data-ttu-id="4b3d2-328">**WebSocket Manager**</span><span class="sxs-lookup"><span data-stu-id="4b3d2-328">**WebSocket Manager**</span></span>  
>   https://github.com/radu-matei/websocket-manager

## <a name="domain-driven-design--should-you-apply-it"></a><span data-ttu-id="4b3d2-329">Quando usare la progettazione basata su domini</span><span class="sxs-lookup"><span data-stu-id="4b3d2-329">Domain-driven design – Should you apply it?</span></span>

<span data-ttu-id="4b3d2-330">La progettazione basata su domini (Domain-Driven Design, DDD) è un approccio semplice alla creazione di software che pone l'attenzione sul _dominio aziendale_.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-330">Domain-Driven Design (DDD) is an agile approach to building software that emphasizes focusing on the _business domain_.</span></span> <span data-ttu-id="4b3d2-331">Evidenzia in particolare la comunicazione e l'interazione con gli esperti dei domini aziendali che possono indicare agli sviluppatori come funziona il sistema nel mondo reale.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-331">It places a heavy emphasis on communication and interaction with business domain expert(s) who can relate to the developers how the real-world system works.</span></span> <span data-ttu-id="4b3d2-332">Ad esempio, se si crea un sistema per la gestione dei titoli azionari, l'esperto del dominio potrebbe essere un agente di cambio.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-332">For example, if you're building a system that handles stock trades, your domain expert might be an experienced stock broker.</span></span> <span data-ttu-id="4b3d2-333">La progettazione basata su domini (DDD) è indirizzata alla soluzione di problemi aziendali estesi e complessi e spesso non è adatta ad applicazioni più semplici e di piccole dimensioni poiché l'investimento nella conoscenza e nella modellazione del dominio potrebbe essere eccessivo.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-333">DDD is designed to address large, complex business problems, and is often not appropriate for smaller, simpler applications, as the investment in understanding and modeling the domain is not worth it.</span></span>

<span data-ttu-id="4b3d2-334">Quando si compila un software seguendo un approccio DDD, è necessario che il team, inclusi gli utenti e i collaboratori non tecnici, sviluppi un _linguaggio universale_ per l'area dei problemi.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-334">When building software following a DDD approach, your team (including non-technical stakeholders and contributors) should develop a _ubiquitous language_ for the problem space.</span></span> <span data-ttu-id="4b3d2-335">Ciò significa che è necessario usare la stessa terminologia per il concetto del mondo reale modellato, l'equivalente software ed eventuali strutture esistenti per il mantenimento del concetto, ad esempio le tabelle di database.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-335">That is, the same terminology should be used for the real-world concept being modeled, the software equivalent, and any structures that might exist to persist the concept (for example, database tables).</span></span> <span data-ttu-id="4b3d2-336">Di conseguenza, i concetti descritti in linguaggio universale devono costituire la base del _modello di dominio_.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-336">Thus, the concepts described in the ubiquitous language should form the basis for your _domain model_.</span></span>

<span data-ttu-id="4b3d2-337">Il modello di dominio è costituito da oggetti che interagiscono tra loro per rappresentare il comportamento del sistema.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-337">Your domain model is comprised of objects that interact with one another to represent the behavior of the system.</span></span> <span data-ttu-id="4b3d2-338">Gli oggetti sono suddivisi nelle categorie seguenti:</span><span class="sxs-lookup"><span data-stu-id="4b3d2-338">These objects may fall into the following categories:</span></span>

- <span data-ttu-id="4b3d2-339">[Entità](https://deviq.com/entity/) che rappresentano gli oggetti con un thread di identità.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-339">[Entities](https://deviq.com/entity/), which represent objects with a thread of identity.</span></span> <span data-ttu-id="4b3d2-340">Le entità sono in genere salvate in modo permanente con una chiave con cui possono essere recuperate in seguito.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-340">Entities are typically stored in persistence with a key by which they can later be retrieved.</span></span>

- <span data-ttu-id="4b3d2-341">[Aggregazioni](https://deviq.com/aggregate-pattern/) che rappresentano gruppi di oggetti che devono essere salvati in modo permanente come unità.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-341">[Aggregates](https://deviq.com/aggregate-pattern/), which represent groups of objects that should be persisted as a unit.</span></span>

- <span data-ttu-id="4b3d2-342">[Oggetti valore](https://deviq.com/value-object/) che rappresentano i concetti che possono essere confrontati mediante la somma dei valori delle relative proprietà.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-342">[Value objects](https://deviq.com/value-object/), which represent concepts that can be compared on the basis of the sum of their property values.</span></span> <span data-ttu-id="4b3d2-343">Ad esempio, DateRange costituito da una data di inizio e di fine.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-343">For example, DateRange consisting of a start and end date.</span></span>

- <span data-ttu-id="4b3d2-344">[Eventi del dominio](https://martinfowler.com/eaaDev/DomainEvent.html) che rappresentano operazioni eseguite all'interno del sistema di interesse ad altre parti del sistema.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-344">[Domain events](https://martinfowler.com/eaaDev/DomainEvent.html), which represent things happening within the system that are of interest to other parts of the system.</span></span>

<span data-ttu-id="4b3d2-345">Si noti che un modello di dominio DDD deve incapsulare un comportamento complesso all'interno del modello.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-345">Note that a DDD domain model should encapsulate complex behavior within the model.</span></span> <span data-ttu-id="4b3d2-346">Le entità, in particolare, non devono essere semplici raccolte di proprietà.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-346">Entities, in particular, should not merely be collections of properties.</span></span> <span data-ttu-id="4b3d2-347">Quando il modello di dominio non include il comportamento e rappresenta solo lo stato del sistema viene definito un [modello anemico](https://deviq.com/anemic-model/) non adatto per la progettazione DDD.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-347">When the domain model lacks behavior and merely represents the state of the system, it is said to be an [anemic model](https://deviq.com/anemic-model/), which is undesirable in DDD.</span></span>

<span data-ttu-id="4b3d2-348">Oltre a questi tipi di modello, la progettazione DDD usa in genere un'ampia gamma di modelli:</span><span class="sxs-lookup"><span data-stu-id="4b3d2-348">In addition to these model types, DDD typically employs a variety of patterns:</span></span>

- <span data-ttu-id="4b3d2-349">[Repository](https://deviq.com/repository-pattern/), per fornire l'astrazione dei dettagli di persistenza.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-349">[Repository](https://deviq.com/repository-pattern/), for abstracting persistence details.</span></span>

- <span data-ttu-id="4b3d2-350">[Factory](https://en.wikipedia.org/wiki/Factory_method_pattern), per incapsulare la creazione di oggetti complessi.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-350">[Factory](https://en.wikipedia.org/wiki/Factory_method_pattern), for encapsulating complex object creation.</span></span>

- <span data-ttu-id="4b3d2-351">Eventi di dominio, per separare il comportamento dipendente dal comportamento di attivazione.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-351">Domain events, for decoupling dependent behavior from triggering behavior.</span></span>

- <span data-ttu-id="4b3d2-352">[Servizi](http://gorodinski.com/blog/2012/04/14/services-in-domain-driven-design-ddd/), per incapsulare un comportamento complesso e/o i dettagli di implementazione dell'infrastruttura.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-352">[Services](http://gorodinski.com/blog/2012/04/14/services-in-domain-driven-design-ddd/), for encapsulating complex behavior and/or infrastructure implementation details.</span></span>

- <span data-ttu-id="4b3d2-353">[Comando](https://en.wikipedia.org/wiki/Command_pattern), per separare l'invio dei comandi e l'esecuzione del comando.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-353">[Command](https://en.wikipedia.org/wiki/Command_pattern), for decoupling issuing commands and executing the command itself.</span></span>

- <span data-ttu-id="4b3d2-354">[Specifica](https://deviq.com/specification-pattern/), per incapsulare i dettagli di query.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-354">[Specification](https://deviq.com/specification-pattern/), for encapsulating query details.</span></span>

<span data-ttu-id="4b3d2-355">Con la progettazione DDD è inoltre consigliabile usare l'architettura "pulita" descritta in precedenza che offre l'accoppiamento libero, l'incapsulamento e un codice che può essere facilmente verificato tramite unit test.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-355">DDD also recommends the use of the Clean Architecture discussed previously, allowing for loose coupling, encapsulation, and code that can easily be verified using unit tests.</span></span>

### <a name="when-should-you-apply-ddd"></a><span data-ttu-id="4b3d2-356">Quando applicare la progettazione basata su domini (DDD)</span><span class="sxs-lookup"><span data-stu-id="4b3d2-356">When should you apply DDD</span></span>

<span data-ttu-id="4b3d2-357">La progettazione DDD è particolarmente adatta alle applicazioni di grandi dimensioni con elevata complessità di business (non solo tecnica).</span><span class="sxs-lookup"><span data-stu-id="4b3d2-357">DDD is well-suited to large applications with significant business (not just technical) complexity.</span></span> <span data-ttu-id="4b3d2-358">L'applicazione deve richiedere la competenza degli esperti di dominio.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-358">The application should require the knowledge of domain experts.</span></span> <span data-ttu-id="4b3d2-359">Deve inoltre essere presente un comportamento significativo nel modello di dominio stesso, che rappresenta le regole business e le interazioni e non si limita all'archiviazione e al recupero dello stato corrente dei diversi record dagli archivi dati.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-359">There should be significant behavior in the domain model itself, representing business rules and interactions beyond simply storing and retrieving the current state of various records from data stores.</span></span>

### <a name="when-shouldnt-you-apply-ddd"></a><span data-ttu-id="4b3d2-360">Quando non applicare la progettazione basata su domini (DDD)</span><span class="sxs-lookup"><span data-stu-id="4b3d2-360">When shouldn't you apply DDD</span></span>

<span data-ttu-id="4b3d2-361">La progettazione DDD prevede investimenti nella modellazione, nell'architettura e nella comunicazione non sempre garantiti per le applicazioni di piccole dimensioni o le applicazioni CRUD (Create/Read/Update/Delete).</span><span class="sxs-lookup"><span data-stu-id="4b3d2-361">DDD involves investments in modeling, architecture, and communication that may not be warranted for smaller applications or applications that are essentially just CRUD (create/read/update/delete).</span></span> <span data-ttu-id="4b3d2-362">Se si sceglie un approccio basato sulla progettazione DDD per l'applicazione e si scopre che il dominio ha un modello anemico senza comportamento, potrebbe essere necessario cambiare approccio.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-362">If you choose to approach your application following DDD, but find that your domain has an anemic model with no behavior, you may need to rethink your approach.</span></span> <span data-ttu-id="4b3d2-363">È possibile che l'applicazione non richieda la progettazione DDD oppure potrebbe essere necessario ricevere assistenza per effettuare il refactoring dell'applicazione in modo da incapsulare la logica di business nel modello di dominio anziché nel database o nell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-363">Either your application may not need DDD, or you may need assistance refactoring your application to encapsulate business logic in the domain model, rather than in your database or user interface.</span></span>

<span data-ttu-id="4b3d2-364">Un approccio ibrido potrebbe essere quello di usare la progettazione DDD solo per le aree transazionali o più complesse dell'applicazione e di non usarla per le parti più semplici CRUD o di sola lettura dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-364">A hybrid approach would be to only use DDD for the transactional or more complex areas of the application, but not for simpler CRUD or read-only portions of the application.</span></span> <span data-ttu-id="4b3d2-365">Ad esempio, non sono necessari i vincoli di un'aggregazione quando si eseguono query sui dati per visualizzare un report o i dati di un dashboard.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-365">For instance, you needn't have the constraints of an Aggregate if you're querying data to display a report or to visualize data for a dashboard.</span></span> <span data-ttu-id="4b3d2-366">Per questo tipo di requisiti è possibile avere un modello di lettura più semplice separato.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-366">It's perfectly acceptable to have a separate, simpler read model for such requirements.</span></span>

> ### <a name="references--domain-driven-design"></a><span data-ttu-id="4b3d2-367">Riferimenti - Progettazione basata su domini (DDD)</span><span class="sxs-lookup"><span data-stu-id="4b3d2-367">References – Domain-Driven Design</span></span>
>
> - <span data-ttu-id="4b3d2-368">**DDD in Plain English (StackOverflow Answer)** (Progettazione basata su domini (risposta StackOverflow))</span><span class="sxs-lookup"><span data-stu-id="4b3d2-368">**DDD in Plain English (StackOverflow Answer)**</span></span>  
>   <https://stackoverflow.com/questions/1222392/can-someone-explain-domain-driven-design-ddd-in-plain-english-please/1222488#1222488>

## <a name="deployment"></a><span data-ttu-id="4b3d2-369">Distribuzione</span><span class="sxs-lookup"><span data-stu-id="4b3d2-369">Deployment</span></span>

<span data-ttu-id="4b3d2-370">Il processo di distribuzione di un'applicazione ASP.NET Core prevede alcuni passaggi, indipendentemente dalla posizione in cui verrà ospitata.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-370">There are a few steps involved in the process of deploying your ASP.NET Core application, regardless of where it will be hosted.</span></span> <span data-ttu-id="4b3d2-371">Il primo passaggio consiste nel pubblicare l'applicazione, operazione che può essere eseguita con il comando di pubblicazione dell'interfaccia della riga di comando per .NET.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-371">The first step is to publish the application, which can be done using the dotnet publish CLI command.</span></span> <span data-ttu-id="4b3d2-372">Viene compilata l'applicazione e tutti i file necessari per eseguire l'applicazione vengono inseriti in una cartella specificata.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-372">This will compile the application and place all of the files needed to run the application into a designated folder.</span></span> <span data-ttu-id="4b3d2-373">Per le distribuzioni da Visual Studio, questo passaggio viene eseguito automaticamente.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-373">When you deploy from Visual Studio, this step is performed for you automatically.</span></span> <span data-ttu-id="4b3d2-374">La cartella di publish contiene i file con estensione exe e dll dell'applicazione e le relative dipendenze.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-374">The publish folder contains .exe and .dll files for the application and its dependencies.</span></span> <span data-ttu-id="4b3d2-375">Un'applicazione indipendente includerà anche una versione del runtime .NET.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-375">A self-contained application will also include a version of the .NET runtime.</span></span> <span data-ttu-id="4b3d2-376">Le applicazioni ASP.NET Core includeranno anche i file di configurazione, gli asset client statici e le visualizzazioni MVC.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-376">ASP.NET Core applications will also include configuration files, static client assets, and MVC views.</span></span>

<span data-ttu-id="4b3d2-377">Le applicazioni ASP.NET Core sono applicazioni console che devono essere avviate all'avvio del server e riavviate in caso di arresto anomalo dell'applicazione o del server.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-377">ASP.NET Core applications are console applications that must be started when the server boots and restarted if the application (or server) crashes.</span></span> <span data-ttu-id="4b3d2-378">È possibile usare un'utilità di gestione dei processi per automatizzare questo processo.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-378">A process manager can be used to automate this process.</span></span> <span data-ttu-id="4b3d2-379">Le utilità di gestione dei processi più comuni per ASP.NET Core sono Nginx e Apache in Linux e IIS o Windows Service in Windows.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-379">The most common process managers for ASP.NET Core are Nginx and Apache on Linux and IIS or Windows Service on Windows.</span></span>

<span data-ttu-id="4b3d2-380">Oltre a un'utilità di gestione dei processi, le applicazioni ASP.NET Core ospitate nel server Web Kestrel devono usare un server proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-380">In addition to a process manager, ASP.NET Core applications hosted in the Kestrel web server must use a reverse proxy server.</span></span> <span data-ttu-id="4b3d2-381">Il server proxy inverso riceve le richieste HTTP da Internet e le inoltra a Kestrel dopo alcune operazioni di gestione preliminari.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-381">A reverse proxy server receives HTTP requests from the internet and forwards them to Kestrel after some preliminary handling.</span></span> <span data-ttu-id="4b3d2-382">I server proxy inversi offrono un livello di sicurezza per l'applicazione e sono necessari per le distribuzioni Edge esposte al traffico di Internet.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-382">Reverse proxy servers provide a layer of security for the application, and are required for edge deployments (exposed to traffic from the Internet).</span></span> <span data-ttu-id="4b3d2-383">Kestrel è relativamente nuovo e non offre ancora difese da alcuni attacchi.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-383">Kestrel is relatively new and does not yet offer defenses against certain attacks.</span></span> <span data-ttu-id="4b3d2-384">Inoltre, poiché Kestrel non supporta l'hosting di più applicazioni sulla stessa porta, non è possibile usare tecniche come le intestazioni host per abilitare l'hosting di più applicazioni sulla stessa porta e sullo stesso indirizzo IP.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-384">Kestrel also doesn't support hosting multiple applications on the same port, so techniques like host headers cannot be used with it to enable hosting multiple applications on the same port and IP address.</span></span>

![Kestrel in Internet](./media/image7-5.png)

<span data-ttu-id="4b3d2-386">Figura 7-5 ASP.NET ospitato in Kestrel con server proxy inverso</span><span class="sxs-lookup"><span data-stu-id="4b3d2-386">Figure 7-5 ASP.NET hosted in Kestrel behind a reverse proxy server</span></span>

<span data-ttu-id="4b3d2-387">Un proxy inverso può risultare utile anche in uno scenario in cui è necessario proteggere più applicazioni con SSL e HTTPS.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-387">Another scenario in which a reverse proxy can be helpful is to secure multiple applications using SSL/HTTPS.</span></span> <span data-ttu-id="4b3d2-388">In questo caso è necessario configurare SSL solo per il proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-388">In this case, only the reverse proxy would need to have SSL configured.</span></span> <span data-ttu-id="4b3d2-389">La comunicazione tra il server proxy inverso e Kestrel può avvenire su HTTP, come illustrato nella figura 7-6.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-389">Communication between the reverse proxy server and Kestrel could take place over HTTP, as shown in Figure 7-6.</span></span>

![](./media/image7-6.png)

<span data-ttu-id="4b3d2-390">Figura 7-6 ASP.NET ospitato in un server proxy inverso con protezione HTTPS</span><span class="sxs-lookup"><span data-stu-id="4b3d2-390">Figure 7-6 ASP.NET hosted behind an HTTPS-secured reverse proxy server</span></span>

<span data-ttu-id="4b3d2-391">Un approccio sempre più diffuso consiste nell'ospitare l'applicazione ASP.NET Core in un contenitore Docker che può essere ospitato in locale o distribuito in Azure per l'hosting basato su cloud.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-391">An increasingly popular approach is to host your ASP.NET Core application in a Docker container, which then can be hosted locally or deployed to Azure for cloud-based hosting.</span></span> <span data-ttu-id="4b3d2-392">Il contenitore Docker può contenere il codice dell'applicazione in esecuzione su Kestrel e può essere distribuito in un server proxy inverso, come illustrato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-392">The Docker container could contain your application code, running on Kestrel, and would be deployed behind a reverse proxy server, as shown above.</span></span>

<span data-ttu-id="4b3d2-393">Se l'applicazione è ospitata in Azure, è possibile usare il gateway applicazione di Microsoft Azure come appliance virtuale dedicata per offrire servizi diversi.</span><span class="sxs-lookup"><span data-stu-id="4b3d2-393">If you're hosting your application on Azure, you can use Microsoft Azure Application Gateway as a dedicated virtual appliance to provide several services.</span></span> <span data-ttu-id="4b3d2-394">Oltre a svolgere la funzione di proxy inverso per le singole applicazioni, il gateway applicazione può offrire anche le funzionalità seguenti:</span><span class="sxs-lookup"><span data-stu-id="4b3d2-394">In addition to acting as a reverse proxy for individual applications, Application Gateway can also offer the following features:</span></span>

- <span data-ttu-id="4b3d2-395">Bilanciamento del carico HTTP</span><span class="sxs-lookup"><span data-stu-id="4b3d2-395">HTTP load balancing</span></span>

- <span data-ttu-id="4b3d2-396">Ripartizione del carico di lavoro SSL (SSL sono in Internet)</span><span class="sxs-lookup"><span data-stu-id="4b3d2-396">SSL offload (SSL only to Internet)</span></span>

- <span data-ttu-id="4b3d2-397">SSL end-to-end</span><span class="sxs-lookup"><span data-stu-id="4b3d2-397">End to End SSL</span></span>

- <span data-ttu-id="4b3d2-398">Routing multisito (consolidare fino a 20 siti in un unico gateway applicazione)</span><span class="sxs-lookup"><span data-stu-id="4b3d2-398">Multi-site routing (consolidate up to 20 sites on a single Application Gateway)</span></span>

- <span data-ttu-id="4b3d2-399">Firewall dell'applicazione Web</span><span class="sxs-lookup"><span data-stu-id="4b3d2-399">Web application firewall</span></span>

- <span data-ttu-id="4b3d2-400">Supporto di WebSocket</span><span class="sxs-lookup"><span data-stu-id="4b3d2-400">Websocket support</span></span>

- <span data-ttu-id="4b3d2-401">Diagnostica avanzata</span><span class="sxs-lookup"><span data-stu-id="4b3d2-401">Advanced diagnostics</span></span>

<span data-ttu-id="4b3d2-402">_Per altre informazioni sulle opzioni di distribuzione di Azure, vedere il [capitolo 10](development-process-for-azure.md)._</span><span class="sxs-lookup"><span data-stu-id="4b3d2-402">_Learn more about Azure deployment options in [Chapter 10](development-process-for-azure.md)._</span></span>

> ### <a name="references--deployment"></a><span data-ttu-id="4b3d2-403">Riferimenti - Distribuzione</span><span class="sxs-lookup"><span data-stu-id="4b3d2-403">References – Deployment</span></span>
>
> - <span data-ttu-id="4b3d2-404">**Panoramica sull'hosting e la distribuzione**</span><span class="sxs-lookup"><span data-stu-id="4b3d2-404">**Hosting and Deployment Overview**</span></span>  
>   <https://docs.microsoft.com/aspnet/core/publishing/>
> - <span data-ttu-id="4b3d2-405">**Quando usare Kestrel con un proxy inverso**</span><span class="sxs-lookup"><span data-stu-id="4b3d2-405">**When to use Kestrel with a reverse proxy**</span></span>  
>   <https://docs.microsoft.com/aspnet/core/fundamentals/servers/kestrel#when-to-use-kestrel-with-a-reverse-proxy>
> - <span data-ttu-id="4b3d2-406">**Ospitare app ASP.NET Core in Docker**</span><span class="sxs-lookup"><span data-stu-id="4b3d2-406">**Host ASP.NET Core apps in Docker**</span></span>  
>   <https://docs.microsoft.com/aspnet/core/publishing/docker>
> - <span data-ttu-id="4b3d2-407">**Introduzione al gateway applicazione di Azure**</span><span class="sxs-lookup"><span data-stu-id="4b3d2-407">**Introducing Azure Application Gateway**</span></span>  
>   <https://docs.microsoft.com/azure/application-gateway/application-gateway-introduction>

>[!div class="step-by-step"]
><span data-ttu-id="4b3d2-408">[Precedente](common-client-side-web-technologies.md)
>[Successivo](work-with-data-in-asp-net-core-apps.md)</span><span class="sxs-lookup"><span data-stu-id="4b3d2-408">[Previous](common-client-side-web-technologies.md)
[Next](work-with-data-in-asp-net-core-apps.md)</span></span>
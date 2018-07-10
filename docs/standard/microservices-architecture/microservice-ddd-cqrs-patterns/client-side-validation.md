---
title: Convalida lato client (convalida nei livelli di presentazione)
description: Architettura di microservizi .NET per applicazioni .NET in contenitori | Convalida lato client (convalida nei livelli di presentazione)
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.openlocfilehash: c61a08566492a59090b19f99aaf97b5f6082c1fb
ms.sourcegitcommit: 979597cd8055534b63d2c6ee8322938a27d0c87b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/29/2018
ms.locfileid: "37104569"
---
# <a name="client-side-validation-validation-in-the-presentation-layers"></a><span data-ttu-id="8aeb4-103">Convalida lato client (convalida nei livelli di presentazione)</span><span class="sxs-lookup"><span data-stu-id="8aeb4-103">Client-side validation (validation in the presentation layers)</span></span>

<span data-ttu-id="8aeb4-104">Anche quando l'origine della verità è il modello di dominio e occorre una convalida al livello del modello di dominio, è comunque possibile gestire la convalida sia a livello del modello di dominio (lato server) che sul lato client.</span><span class="sxs-lookup"><span data-stu-id="8aeb4-104">Even when the source of truth is the domain model and ultimately you must have validation at the domain model level, validation can still be handled at both the domain model level (server side) and the client side.</span></span>

<span data-ttu-id="8aeb4-105">La convalida lato client è molto pratica per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="8aeb4-105">Client-side validation is a great convenience for users.</span></span> <span data-ttu-id="8aeb4-106">Consente infatti di ridurre i tempi di attesa di un round trip al server che potrebbe restituire errori di convalida.</span><span class="sxs-lookup"><span data-stu-id="8aeb4-106">It saves time they would otherwise spend waiting for a round trip to the server that might return validation errors.</span></span> <span data-ttu-id="8aeb4-107">In termini di business, anche poche frazioni di secondo moltiplicate per centinaia di volte al giorno contribuiscono all'aumento di tempo, costi e frustrazione.</span><span class="sxs-lookup"><span data-stu-id="8aeb4-107">In business terms, even a few fractions of seconds multiplied hundreds of times each day adds up to a lot of time, expense, and frustration.</span></span> <span data-ttu-id="8aeb4-108">Grazie a un processo di convalida semplice e immediato, gli utenti possono lavorare in modo più efficiente e garantire input e output di qualità elevata.</span><span class="sxs-lookup"><span data-stu-id="8aeb4-108">Straightforward and immediate validation enables users to work more efficiently and produce better quality input and output.</span></span>

<span data-ttu-id="8aeb4-109">Così come il modello di visualizzazione e il modello di dominio sono diversi, la convalida del modello di visualizzazione e del modello di dominio possono essere simili ma hanno uno scopo diverso.</span><span class="sxs-lookup"><span data-stu-id="8aeb4-109">Just as the view model and the domain model are different, view model validation and domain model validation might be similar but serve a different purpose.</span></span> <span data-ttu-id="8aeb4-110">Se si è preoccupati circa il principio DRY (Don't Repeat Yourself), ovvero non ripetersi, considerare che in questo caso il riutilizzo del codice può significare un accoppiamento, ma nelle applicazioni aziendali è più importante non accoppiare il lato server al lato client che non seguire il principio DRY.</span><span class="sxs-lookup"><span data-stu-id="8aeb4-110">If you are concerned about DRY (the Don’t Repeat Yourself principle), consider that in this case code reuse might also mean coupling, and in enterprise applications it is more important not to couple the server side to the client side than to follow the DRY principle.</span></span>

<span data-ttu-id="8aeb4-111">Quando si usa la convalida lato client, è necessario convalidare sempre i comandi o gli oggetti DTO di input nel codice del server, poiché le API del server rappresentano un possibile vettore di attacco.</span><span class="sxs-lookup"><span data-stu-id="8aeb4-111">Even when using client-side validation, you should always validate your commands or input DTOs in server code, because the server APIs are a possible attack vector.</span></span> <span data-ttu-id="8aeb4-112">In genere, l'opzione migliore prevede di eseguirle entrambe, perché nel caso di un'applicazione client, dalla prospettiva dell'esperienza utente è consigliabile essere proattivi e non consentire all'utente di immettere informazioni non valide.</span><span class="sxs-lookup"><span data-stu-id="8aeb4-112">Usually, doing both is your best bet because if you have a client application, from a UX perspective, it is best to be proactive and not allow the user to enter invalid information.</span></span>

<span data-ttu-id="8aeb4-113">Di conseguenza, nel codice sul lato client vengono in genere convalidati gli oggetti ViewModel.</span><span class="sxs-lookup"><span data-stu-id="8aeb4-113">Therefore, in client-side code you typically validate the ViewModels.</span></span> <span data-ttu-id="8aeb4-114">È anche possibile convalidare i comandi o gli oggetti DTO di output del client prima di inviarli ai servizi.</span><span class="sxs-lookup"><span data-stu-id="8aeb4-114">You could also validate the client output DTOs or commands before you send them to the services.</span></span>

<span data-ttu-id="8aeb4-115">L'implementazione della convalida del lato client dipende dalla tipologia di applicazione client che si sta creando.</span><span class="sxs-lookup"><span data-stu-id="8aeb4-115">The implementation of client-side validation depends on what kind of client application you are building.</span></span> <span data-ttu-id="8aeb4-116">La scelta sarà diversa se si vogliono convalidare i dati in un'applicazione Web MVC con la maggior parte del codice in .NET, un'applicazione Web a pagina singola con la convalida scritta in JavaScript o TypeScript o un'applicazione per dispositivi mobili scritta in Xamarin e C\#.</span><span class="sxs-lookup"><span data-stu-id="8aeb4-116">It will be different if you are validating data in a web MVC web application with most of the code in .NET, an SPA web application with that validation being coded in JavaScript or TypeScript, or a mobile app coded with Xamarin and C\#.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="8aeb4-117">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="8aeb4-117">Additional resources</span></span>

### <a name="validation-in-xamarin-mobile-apps"></a><span data-ttu-id="8aeb4-118">Convalida nelle app per dispositivi mobili in Xamarin</span><span class="sxs-lookup"><span data-stu-id="8aeb4-118">Validation in Xamarin mobile apps</span></span>

-   <span data-ttu-id="8aeb4-119">**Convalidare l'input di testo e visualizzare gli errori**
    [*https://developer.xamarin.com/recipes/ios/standard\_controls/text\_field/validate\_input/*](https://developer.xamarin.com/recipes/ios/standard_controls/text_field/validate_input/)</span><span class="sxs-lookup"><span data-stu-id="8aeb4-119">**Validate Text Input and Show Errors**
[*https://developer.xamarin.com/recipes/ios/standard\_controls/text\_field/validate\_input/*](https://developer.xamarin.com/recipes/ios/standard_controls/text_field/validate_input/)</span></span>

-   <span data-ttu-id="8aeb4-120">**Richiamata di convalida**
    [*https://developer.xamarin.com/samples/xamarin-forms/XAML/ValidationCallback/*](https://developer.xamarin.com/samples/xamarin-forms/XAML/ValidationCallback/)</span><span class="sxs-lookup"><span data-stu-id="8aeb4-120">**Validation Callback**
[*https://developer.xamarin.com/samples/xamarin-forms/XAML/ValidationCallback/*](https://developer.xamarin.com/samples/xamarin-forms/XAML/ValidationCallback/)</span></span>

### <a name="validation-in-aspnet-core-apps"></a><span data-ttu-id="8aeb4-121">Convalida nelle app ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="8aeb4-121">Validation in ASP.NET Core apps</span></span>

-   <span data-ttu-id="8aeb4-122">**Rick Anderson. Aggiunta della convalida**
    [*https://docs.microsoft.com/aspnet/core/tutorials/first-mvc-app/validation*](https://docs.microsoft.com/aspnet/core/tutorials/first-mvc-app/validation)</span><span class="sxs-lookup"><span data-stu-id="8aeb4-122">**Rick Anderson. Adding validation**
[*https://docs.microsoft.com/aspnet/core/tutorials/first-mvc-app/validation*](https://docs.microsoft.com/aspnet/core/tutorials/first-mvc-app/validation)</span></span>

### <a name="validation-in-spa-web-apps-angular-2-typescript-javascript"></a><span data-ttu-id="8aeb4-123">Convalida nelle app Web a pagina singola (Angular 2, TypeScript, JavaScript)</span><span class="sxs-lookup"><span data-stu-id="8aeb4-123">Validation in SPA Web apps (Angular 2, TypeScript, JavaScript)</span></span>

-   <span data-ttu-id="8aeb4-124">**Ado Kukic. Convalida del modulo angular 2** **
    **[*https://scotch.io/tutorials/angular-2-form-validation*](https://scotch.io/tutorials/angular-2-form-validation)</span><span class="sxs-lookup"><span data-stu-id="8aeb4-124">**Ado Kukic. Angular 2 Form Validation** **
**[*https://scotch.io/tutorials/angular-2-form-validation*](https://scotch.io/tutorials/angular-2-form-validation)</span></span>

-   <span data-ttu-id="8aeb4-125">**Convalida del modulo**
    [*https://angular.io/docs/ts/latest/cookbook/form-validation.html*](https://angular.io/docs/ts/latest/cookbook/form-validation.html)</span><span class="sxs-lookup"><span data-stu-id="8aeb4-125">**Form Validation**
[*https://angular.io/docs/ts/latest/cookbook/form-validation.html*](https://angular.io/docs/ts/latest/cookbook/form-validation.html)</span></span>

-   <span data-ttu-id="8aeb4-126">**Convalida.**</span><span class="sxs-lookup"><span data-stu-id="8aeb4-126">**Validation.**</span></span> <span data-ttu-id="8aeb4-127">Documentazione per Breeze.</span><span class="sxs-lookup"><span data-stu-id="8aeb4-127">Breeze documentation.</span></span>
    [*https://breeze.github.io/doc-js/validation.html*](https://breeze.github.io/doc-js/validation.html)

<span data-ttu-id="8aeb4-128">In breve, questi sono i concetti più importanti in merito alla convalida:</span><span class="sxs-lookup"><span data-stu-id="8aeb4-128">In summary, these are the most important concepts in regards to validation:</span></span>

-   <span data-ttu-id="8aeb4-129">Le entità e le aggregazioni devono imporre la propria coerenza ed essere "sempre valide".</span><span class="sxs-lookup"><span data-stu-id="8aeb4-129">Entities and aggregates should enforce their own consistency and be "always valid”.</span></span> <span data-ttu-id="8aeb4-130">Le radici di aggregazione sono responsabili della coerenza di più entità all'interno della stessa aggregazione.</span><span class="sxs-lookup"><span data-stu-id="8aeb4-130">Aggregate roots are responsible for multi-entity consistency within the same aggregate.</span></span>

-   <span data-ttu-id="8aeb4-131">Se si pensa che un'entità debba passare a uno stato non valido, provare a usare un modello a oggetti diverso, ad esempio un oggetto DTO temporaneo fino a quando non viene creata l'entità del dominio finale.</span><span class="sxs-lookup"><span data-stu-id="8aeb4-131">If you think that an entity needs to enter an invalid state, consider using a different object model—for example, using a temporary DTO until you create the final domain entity.</span></span>

-   <span data-ttu-id="8aeb4-132">Se occorre creare numerosi oggetti correlati, ad esempio un'aggregazione, e questi sono validi solo quando tutti saranno stati creati, provare a usare lo schema Factory.</span><span class="sxs-lookup"><span data-stu-id="8aeb4-132">If you need to create several related objects, such as an aggregate, and they are only valid once all of them have been created, consider using the Factory pattern.</span></span>

-   <span data-ttu-id="8aeb4-133">I framework di convalida sono ideali per l'uso in livelli specifici, ad esempio il livello della presentazione o il livello dell'applicazione/servizio, ma in genere non nel livello del modello di dominio, in quanto sarebbe necessario creare una dipendenza elevata dal framework dell'infrastruttura.</span><span class="sxs-lookup"><span data-stu-id="8aeb4-133">Validation frameworks are best used in specific layers, such as the presentation layer or the application/service layer, but usually not in the domain model layer, because you would need to take a strong dependency on an infrastructure framework.</span></span>

-   <span data-ttu-id="8aeb4-134">Nella maggior parte dei client, è consigliabile adottare una convalida ridondante sul lato client, per aumentare la proattività dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="8aeb4-134">In most of the cases, having redundant validation in the client side is good, because the application can be proactive.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="8aeb4-135">[Precedente](domain-model-layer-validations.md)
[Successivo](domain-events-design-implementation.md)</span><span class="sxs-lookup"><span data-stu-id="8aeb4-135">[Previous](domain-model-layer-validations.md)
[Next](domain-events-design-implementation.md)</span></span>

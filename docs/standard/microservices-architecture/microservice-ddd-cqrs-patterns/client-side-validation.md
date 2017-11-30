---
title: Convalida lato client (convalida dei livelli di presentazione)
description: Architettura di Microservizi .NET per le applicazioni nei contenitori .NET | Convalida lato client (convalida dei livelli di presentazione)
keywords: Docker, microservizi, ASP.NET, contenitore
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: db88a3b5c95afdc8d5a20094105f1f5991483ed6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="client-side-validation-validation-in-the-presentation-layers"></a><span data-ttu-id="a8a6e-104">Convalida lato client (convalida dei livelli di presentazione)</span><span class="sxs-lookup"><span data-stu-id="a8a6e-104">Client-side validation (validation in the presentation layers)</span></span>

<span data-ttu-id="a8a6e-105">Anche quando l'origine di dati reali è il modello di dominio e infine è necessario disporre convalida al livello del modello di dominio, convalida ancora può essere gestita a livello di modello di dominio (lato server) e il lato client.</span><span class="sxs-lookup"><span data-stu-id="a8a6e-105">Even when the source of truth is the domain model and ultimately you must have validation at the domain model level, validation can still be handled at both the domain model level (server side) and the client side.</span></span>

<span data-ttu-id="a8a6e-106">La convalida lato client è una maggiore praticità per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="a8a6e-106">Client-side validation is a great convenience for users.</span></span> <span data-ttu-id="a8a6e-107">Consente di risparmiare tempo in caso contrario spendere in attesa di un round trip al server che potrebbero restituire gli errori di convalida.</span><span class="sxs-lookup"><span data-stu-id="a8a6e-107">It saves time they would otherwise spend waiting for a round trip to the server that might return validation errors.</span></span> <span data-ttu-id="a8a6e-108">In termini di business, anche alcuni le frazioni di secondo moltiplicato centinaia di volte in cui ogni giorno vengono aggiunti a una grande quantità di tempo, expense e frustrazione.</span><span class="sxs-lookup"><span data-stu-id="a8a6e-108">In business terms, even a few fractions of seconds multiplied hundreds of times each day adds up to a lot of time, expense, and frustration.</span></span> <span data-ttu-id="a8a6e-109">Convalida semplice e immediata consente agli utenti di lavorare in modo più efficiente e ottenere una migliore qualità di input e output.</span><span class="sxs-lookup"><span data-stu-id="a8a6e-109">Straightforward and immediate validation enables users to work more efficiently and produce better quality input and output.</span></span>

<span data-ttu-id="a8a6e-110">Come il modello di visualizzazione e il modello di dominio sono diversi, la convalida del modello di visualizzazione e la convalida del modello di dominio potrebbe essere simile ma uno scopo diverso.</span><span class="sxs-lookup"><span data-stu-id="a8a6e-110">Just as the view model and the domain model are different, view model validation and domain model validation might be similar but serve a different purpose.</span></span> <span data-ttu-id="a8a6e-111">Se si teme su sorgente (non ripetere manualmente principio), tenere presente che in questo caso il riutilizzo del codice potrebbe anche trattarsi di attacco, e in applicazioni aziendali è più importante per non associare lato server al lato client rispetto in base al principio secca.</span><span class="sxs-lookup"><span data-stu-id="a8a6e-111">If you are concerned about DRY (the Don’t Repeat Yourself principle), consider that in this case code reuse might also mean coupling, and in enterprise applications it is more important not to couple the server side to the client side than to follow the DRY principle.</span></span>

<span data-ttu-id="a8a6e-112">Anche quando si utilizza la convalida lato client, è consigliabile sempre convalidare i comandi o di input DTO nel codice server, perché le API server rappresentano un vettore di attacco.</span><span class="sxs-lookup"><span data-stu-id="a8a6e-112">Even when using client-side validation, you should always validate your commands or input DTOs in server code, because the server APIs are a possible attack vector.</span></span> <span data-ttu-id="a8a6e-113">In genere, ciò infatti il modo migliore se si dispone di un'applicazione client, dal punto di vista dell'esperienza utente, è consigliabile essere attiva e non consentire all'utente di immettere informazioni non valide.</span><span class="sxs-lookup"><span data-stu-id="a8a6e-113">Usually, doing both is your best bet because if you have a client application, from a UX perspective, it is best to be proactive and not allow the user to enter invalid information.</span></span>

<span data-ttu-id="a8a6e-114">Pertanto, nel codice sul lato client è in genere convalidare il ViewModel.</span><span class="sxs-lookup"><span data-stu-id="a8a6e-114">Therefore, in client-side code you typically validate the ViewModels.</span></span> <span data-ttu-id="a8a6e-115">È inoltre possibile convalidare il client invia l'output DTO o comandi prima di inviarli ai servizi.</span><span class="sxs-lookup"><span data-stu-id="a8a6e-115">You could also validate the client output DTOs or commands before you send them to the services.</span></span>

<span data-ttu-id="a8a6e-116">L'implementazione della convalida lato client dipende dal tipo di applicazione client si sta compilando.</span><span class="sxs-lookup"><span data-stu-id="a8a6e-116">The implementation of client-side validation depends on what kind of client application you are building.</span></span> <span data-ttu-id="a8a6e-117">Sarà diverso se si esegue la convalida dei dati in un'applicazione web MVC web con la maggior parte del codice in .NET, un'applicazione web SPA con tale convalida codificata in JavaScript o TypeScript, o un'app mobile codificati con Xamarin e C\#.</span><span class="sxs-lookup"><span data-stu-id="a8a6e-117">It will be different if you are validating data in a web MVC web application with most of the code in .NET, an SPA web application with that validation being coded in JavaScript or TypeScript, or a mobile app coded with Xamarin and C\#.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="a8a6e-118">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="a8a6e-118">Additional resources</span></span>

### <a name="validation-in-xamarin-mobile-apps"></a><span data-ttu-id="a8a6e-119">Convalida Xamarin App per dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="a8a6e-119">Validation in Xamarin mobile apps</span></span>

-   <span data-ttu-id="a8a6e-120">**Convalidare l'Input di testo e Visualizza errori**
    [*https://developer.xamarin.com/recipes/ios/standard\_testo o controlli\_campo/convalidare\_input /*](https://developer.xamarin.com/recipes/ios/standard_controls/text_field/validate_input/)</span><span class="sxs-lookup"><span data-stu-id="a8a6e-120">**Validate Text Input and Show Errors**
[*https://developer.xamarin.com/recipes/ios/standard\_controls/text\_field/validate\_input/*](https://developer.xamarin.com/recipes/ios/standard_controls/text_field/validate_input/)</span></span>

-   <span data-ttu-id="a8a6e-121">**Callback di convalida**
    [*https://developer.xamarin.com/samples/xamarin-forms/XAML/ValidationCallback/*](https://developer.xamarin.com/samples/xamarin-forms/XAML/ValidationCallback/)</span><span class="sxs-lookup"><span data-stu-id="a8a6e-121">**Validation Callback**
[*https://developer.xamarin.com/samples/xamarin-forms/XAML/ValidationCallback/*](https://developer.xamarin.com/samples/xamarin-forms/XAML/ValidationCallback/)</span></span>

### <a name="validation-in-aspnet-core-apps"></a><span data-ttu-id="a8a6e-122">Convalida nelle applicazioni ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="a8a6e-122">Validation in ASP.NET Core apps</span></span>

-   <span data-ttu-id="a8a6e-123">**Rick Anderson. Aggiunta della convalida**
    [*https://docs.microsoft.com/aspnet/core/tutorials/first-mvc-app/validation*](https://docs.microsoft.com/aspnet/core/tutorials/first-mvc-app/validation)</span><span class="sxs-lookup"><span data-stu-id="a8a6e-123">**Rick Anderson. Adding validation**
[*https://docs.microsoft.com/aspnet/core/tutorials/first-mvc-app/validation*](https://docs.microsoft.com/aspnet/core/tutorials/first-mvc-app/validation)</span></span>

### <a name="validation-in-spa-web-apps-angular-2-typescript-javascript"></a><span data-ttu-id="a8a6e-124">Convalida in SPA Web App (angolare 2, macchina, JavaScript)</span><span class="sxs-lookup"><span data-stu-id="a8a6e-124">Validation in SPA Web apps (Angular 2, TypeScript, JavaScript)</span></span>

-   <span data-ttu-id="a8a6e-125">**Kukic ADO. Convalida modulo 2 angolare** **
     ** [ *https://scotch.io/tutorials/angular-2-form-validation*](https://scotch.io/tutorials/angular-2-form-validation)</span><span class="sxs-lookup"><span data-stu-id="a8a6e-125">**Ado Kukic. Angular 2 Form Validation** **
**[*https://scotch.io/tutorials/angular-2-form-validation*](https://scotch.io/tutorials/angular-2-form-validation)</span></span>

-   <span data-ttu-id="a8a6e-126">**Modulo di convalida**
    [*https://angular.io/docs/ts/latest/cookbook/form-validation.html*](https://angular.io/docs/ts/latest/cookbook/form-validation.html)</span><span class="sxs-lookup"><span data-stu-id="a8a6e-126">**Form Validation**
[*https://angular.io/docs/ts/latest/cookbook/form-validation.html*](https://angular.io/docs/ts/latest/cookbook/form-validation.html)</span></span>

-   <span data-ttu-id="a8a6e-127">**Convalida.**</span><span class="sxs-lookup"><span data-stu-id="a8a6e-127">**Validation.**</span></span> <span data-ttu-id="a8a6e-128">Documentazione molto semplice.</span><span class="sxs-lookup"><span data-stu-id="a8a6e-128">Breeze documentation.</span></span>
    [<span data-ttu-id="a8a6e-129">*http://Breeze.github.IO/doc-js/Validation.HTML*</span><span class="sxs-lookup"><span data-stu-id="a8a6e-129">*http://breeze.github.io/doc-js/validation.html*</span></span>](http://breeze.github.io/doc-js/validation.html)

<span data-ttu-id="a8a6e-130">In sintesi, ecco i concetti più importanti relativamente alla convalida:</span><span class="sxs-lookup"><span data-stu-id="a8a6e-130">In summary, these are the most important concepts in regards to validation:</span></span>

-   <span data-ttu-id="a8a6e-131">Entità e funzioni di aggregazione deve applicare le proprie coerenza e "sempre valido".</span><span class="sxs-lookup"><span data-stu-id="a8a6e-131">Entities and aggregates should enforce their own consistency and be "always valid”.</span></span> <span data-ttu-id="a8a6e-132">Radici di aggregazione sono responsabili per la coerenza di più entità all'interno dell'aggregazione stesso.</span><span class="sxs-lookup"><span data-stu-id="a8a6e-132">Aggregate roots are responsible for multi-entity consistency within the same aggregate.</span></span>

-   <span data-ttu-id="a8a6e-133">Se si ritiene che un'entità deve entri in uno stato non valido, è consigliabile utilizzare un modello a oggetti diversi, ad esempio, usando un DTO temporanea fino a creare l'entità finale di dominio.</span><span class="sxs-lookup"><span data-stu-id="a8a6e-133">If you think that an entity needs to enter an invalid state, consider using a different object model—for example, using a temporary DTO until you create the final domain entity.</span></span>

-   <span data-ttu-id="a8a6e-134">Se è necessario creare diversi oggetti correlati, ad esempio un'aggregazione, e sono validi solo dopo avere creati tutti gli elementi, utilizzare il modello di Factory.</span><span class="sxs-lookup"><span data-stu-id="a8a6e-134">If you need to create several related objects, such as an aggregate, and they are only valid once all of them have been created, consider using the Factory pattern.</span></span>

-   <span data-ttu-id="a8a6e-135">Framework di convalida vengono utilizzate in livelli specifici, ad esempio il livello di presentazione o il livello di servizio / dell'applicazione, ma in genere non nel livello del modello di dominio, in quanto è necessario accettare una dipendenza sicura su un framework di infrastruttura.</span><span class="sxs-lookup"><span data-stu-id="a8a6e-135">Validation frameworks are best used in specific layers, such as the presentation layer or the application/service layer, but usually not in the domain model layer, because you would need to take a strong dependency on an infrastructure framework.</span></span>

-   <span data-ttu-id="a8a6e-136">Nella maggior parte dei casi, con la convalida ridondante sul lato client è valida, poiché l'applicazione può essere attiva.</span><span class="sxs-lookup"><span data-stu-id="a8a6e-136">In most of the cases, having redundant validation in the client side is good, because the application can be proactive.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="a8a6e-137">[Precedente] (dominio-modello-layer-validations.md) [Avanti] (dominio eventi-progettazione implementation.md)</span><span class="sxs-lookup"><span data-stu-id="a8a6e-137">[Previous] (domain-model-layer-validations.md) [Next] (domain-events-design-implementation.md)</span></span>

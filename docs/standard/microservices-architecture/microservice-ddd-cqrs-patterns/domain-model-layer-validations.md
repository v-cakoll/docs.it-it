---
title: Progettazione di convalide nel livello del modello di dominio
description: Architettura di microservizi .NET per applicazioni .NET in contenitori | Progettazione di convalide nel livello del modello di dominio
keywords: Docker, microservizi, ASP.NET, contenitore
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: e7a111ce20039f8c87d3c3d63efdeaf38a4e1e96
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/23/2017
---
# <a name="designing-validations-in-the-domain-model-layer"></a><span data-ttu-id="995fb-104">Progettazione di convalide nel livello del modello di dominio</span><span class="sxs-lookup"><span data-stu-id="995fb-104">Designing validations in the domain model layer</span></span>

<span data-ttu-id="995fb-105">In DDD le regole di convalida possono essere considerate invariabili.</span><span class="sxs-lookup"><span data-stu-id="995fb-105">In DDD, validation rules can be thought as invariants.</span></span> <span data-ttu-id="995fb-106">Lo scopo principale di un'aggregazione consiste nell'applicare invariabili tra modifiche dello stato per tutte le entità entro tale aggregazione.</span><span class="sxs-lookup"><span data-stu-id="995fb-106">The main responsibility of an aggregate is to enforce invariants across state changes for all the entities within that aggregate.</span></span>

<span data-ttu-id="995fb-107">Le entità di dominio devono essere sempre entità valide.</span><span class="sxs-lookup"><span data-stu-id="995fb-107">Domain entities should always be valid entities.</span></span> <span data-ttu-id="995fb-108">Alcune invariabili per un oggetto devono essere sempre true.</span><span class="sxs-lookup"><span data-stu-id="995fb-108">There are a certain number of invariants for an object that should always be true.</span></span> <span data-ttu-id="995fb-109">Ad esempio, la quantità di un oggetto di tipo articolo dell'ordine deve essere sempre un numero intero positivo e tale oggetto deve includere anche un nome di articolo e il prezzo.</span><span class="sxs-lookup"><span data-stu-id="995fb-109">For example, an order item object always has to have a quantity that must be a positive integer, plus an article name and price.</span></span> <span data-ttu-id="995fb-110">L'applicazione delle invariabili è quindi responsabilità delle entità di dominio, in particolare per la radice dell'aggregazione, e l'oggetto entità non può esistere senza essere valido.</span><span class="sxs-lookup"><span data-stu-id="995fb-110">Therefore, invariants enforcement is the responsibility of the domain entities (especially of the aggregate root) and an entity object should not be able to exist without being valid.</span></span> <span data-ttu-id="995fb-111">Le regole delle invariabili vengono semplicemente espresse come contratti e vengono generate eccezioni o notifiche in caso di violazione.</span><span class="sxs-lookup"><span data-stu-id="995fb-111">Invariant rules are simply expressed as contracts, and exceptions or notifications are raised when they are violated.</span></span>

<span data-ttu-id="995fb-112">È infatti possibile che vengano generati molti bug perché gli oggetti hanno uno stato non previsto.</span><span class="sxs-lookup"><span data-stu-id="995fb-112">The reasoning behind this is that many bugs occur because objects are in a state they should never have been in.</span></span> <span data-ttu-id="995fb-113">Greg Young fornisce una spiegazione eccellente in una [discussione online](http://jeffreypalermo.com/blog/the-fallacy-of-the-always-valid-entity/):</span><span class="sxs-lookup"><span data-stu-id="995fb-113">The following is a good explanation from Greg Young in an [online discussion](http://jeffreypalermo.com/blog/the-fallacy-of-the-always-valid-entity/):</span></span>

<span data-ttu-id="995fb-114">Si supponga che sia disponibile un SendUserCreationEmailService che accetta un valore UserProfile. È necessario stabilire come razionalizzare il fatto che il nome non sia Null in tale servizio.</span><span class="sxs-lookup"><span data-stu-id="995fb-114">Let's propose we now have a SendUserCreationEmailService that takes a UserProfile ... how can we rationalize in that service that Name is not null?</span></span> <span data-ttu-id="995fb-115">È ad esempio possibile controllarlo di nuovo</span><span class="sxs-lookup"><span data-stu-id="995fb-115">Do we check it again?</span></span> <span data-ttu-id="995fb-116">oppure è semplicemente possibile non controllare e augurarsi che il nome sia stato convalidato prima dell'invio.</span><span class="sxs-lookup"><span data-stu-id="995fb-116">Or more likely ... you just don't bother to check and "hope for the best"—you hope that someone bothered to validate it before sending it to you.</span></span> <span data-ttu-id="995fb-117">Usando TDD è ovviamente consigliabile scrivere prima di tutto un test in modo che venga generato un errore in caso di invio di un cliente con nome Null.</span><span class="sxs-lookup"><span data-stu-id="995fb-117">Of course, using TDD one of the first tests we should be writing is that if I send a customer with a null name that it should raise an error.</span></span> <span data-ttu-id="995fb-118">Quando tuttavia si scrivono ripetutamente test di questo tipo, ci si rende conto che se non si consente mai al nome di essere Null non sarebbe necessario scrivere i test.</span><span class="sxs-lookup"><span data-stu-id="995fb-118">But once we start writing these kinds of tests over and over again we realize ... "wait if we never allowed name to become null we wouldn't have all of these tests"</span></span>

## <a name="implementing-validations-in-the-domain-model-layer"></a><span data-ttu-id="995fb-119">Implementazione di convalide nel livello del modello di dominio</span><span class="sxs-lookup"><span data-stu-id="995fb-119">Implementing validations in the domain model layer</span></span>

<span data-ttu-id="995fb-120">Le convalide vengono in genere implementate nei costruttori delle entità di dominio o nei metodi in grado di aggiornare l'entità.</span><span class="sxs-lookup"><span data-stu-id="995fb-120">Validations are usually implemented in domain entity constructors or in methods that can update the entity.</span></span> <span data-ttu-id="995fb-121">È possibile implementare le convalide in molti modi, ad esempio verificando i dati e generando eccezioni in caso di esito negativo della convalida.</span><span class="sxs-lookup"><span data-stu-id="995fb-121">There are multiple ways to implement validations, such as verifying data and raising exceptions if the validation fails.</span></span> <span data-ttu-id="995fb-122">Sono disponibili anche schemi più avanzati, ad esempio l'uso dello schema Specification per le convalide e dello schema Notification per la restituzione di una raccolta di errori invece di restituire un'eccezione per ogni convalida eseguita.</span><span class="sxs-lookup"><span data-stu-id="995fb-122">There are also more advanced patterns such as using the Specification pattern for validations, and the Notification pattern to return a collection of errors instead of returning an exception for each validation as it occurs.</span></span>

### <a name="validating-conditions-and-throwing-exceptions"></a><span data-ttu-id="995fb-123">Convalida delle condizioni e generazione delle eccezioni</span><span class="sxs-lookup"><span data-stu-id="995fb-123">Validating conditions and throwing exceptions</span></span>

<span data-ttu-id="995fb-124">L'esempio di codice seguente mostra l'approccio più semplice per la convalida in una entità di dominio tramite la generazione di un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="995fb-124">The following code example shows the simplest approach to validation in a domain entity by raising an exception.</span></span> <span data-ttu-id="995fb-125">Nella tabella dei riferimenti alla fine di questa sezione sono disponibili collegamenti a implementazioni più avanzate basate sugli schemi illustrati in precedenza.</span><span class="sxs-lookup"><span data-stu-id="995fb-125">In the references table at the end of this section you can see links to more advanced implementations based on the patterns we have discussed previously.</span></span>

```csharp
public void SetAddress(Address address)
{
    _shippingAddress = address?? throw new ArgumentNullException(nameof(address));
}
```

<span data-ttu-id="995fb-126">Un esempio migliore consente di dimostrare la necessità di assicurare che lo stato interno non abbia subito modifiche o che si siano verificate tutte le mutazioni per un metodo.</span><span class="sxs-lookup"><span data-stu-id="995fb-126">A better example would demonstrate the need to ensure that either the internal state did not change, or that all the mutations for a method occurred.</span></span> <span data-ttu-id="995fb-127">L'implementazione seguente, ad esempio, lascia l'oggetto in uno stato non valido:</span><span class="sxs-lookup"><span data-stu-id="995fb-127">For example, the following implementation would leave the object in an invalid state:</span></span>

```csharp
public void SetAddress(string line1, string line2,
    string city, string state, int zip)
{
    _shipingAddress.line1 = line1 ?? throw new ...
    _shippingAddress.line2 = line2;
    _shippingAddress.city = city ?? throw new ...
    _shippingAddress.state = (IsValid(state) ? state : throw new …);
}
```

<span data-ttu-id="995fb-128">Se il valore dello stato non è valido, la prima riga dell'indirizzo e la città sono già state modificate.</span><span class="sxs-lookup"><span data-stu-id="995fb-128">If the value of the state is invalid, the first address line and the city have already been changed.</span></span> <span data-ttu-id="995fb-129">È quindi possibile che l'indirizzo non sia valido.</span><span class="sxs-lookup"><span data-stu-id="995fb-129">That might make the address invalid.</span></span>

<span data-ttu-id="995fb-130">Un approccio simile può essere usato nel costruttore dell'entità, generando un'eccezione per assicurarsi che l'entità sia valida dopo la creazione.</span><span class="sxs-lookup"><span data-stu-id="995fb-130">A similar approach can be used in the entity’s constructor, raising an exception to make sure that the entity is valid once it is created.</span></span>

### <a name="using-validation-attributes-in-the-model-based-on-data-annotations"></a><span data-ttu-id="995fb-131">Uso degli attributi di convalida nel modello in base alle annotazioni dei dati</span><span class="sxs-lookup"><span data-stu-id="995fb-131">Using validation attributes in the model based on data annotations</span></span>

<span data-ttu-id="995fb-132">Un altro approccio prevede l'uso degli attributi di convalida in base alle annotazioni dei dati.</span><span class="sxs-lookup"><span data-stu-id="995fb-132">Another approach is to use validation attributes based on data annotations.</span></span> <span data-ttu-id="995fb-133">Gli attributi di convalida consentono di configurare la convalida. Concettualmente assomigliano alla convalida nei campi delle tabelle del database.</span><span class="sxs-lookup"><span data-stu-id="995fb-133">Validation attributes provide a way to configure model validation, which is similar conceptually to validation on fields in database tables.</span></span> <span data-ttu-id="995fb-134">Esistono vincoli, ad esempio l'assegnazione di tipi di dati o campi obbligatori.</span><span class="sxs-lookup"><span data-stu-id="995fb-134">This includes constraints such as assigning data types or required fields.</span></span> <span data-ttu-id="995fb-135">Altri tipi di convalida includono l'uso di schemi di dati per applicare le regole di business, ad esempio un numero di carta di credito, il numero di telefono o un indirizzo di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="995fb-135">Other types of validation include applying patterns to data to enforce business rules, such as a credit card number, phone number, or email address.</span></span> <span data-ttu-id="995fb-136">Gli attributi di convalida semplificano l'applicazione dei requisiti.</span><span class="sxs-lookup"><span data-stu-id="995fb-136">Validation attributes make it easy to enforce requirements.</span></span>

<span data-ttu-id="995fb-137">Come mostrato nel codice seguente, tuttavia, questo approccio potrebbe essere troppo invadente in un modello DDD, perché accetta una dipendenza su ModelState.IsValid da Microsoft.AspNetCore.Mvc.ModelState, che deve essere chiamato dai controller MVC.</span><span class="sxs-lookup"><span data-stu-id="995fb-137">However, as shown in the following code, this approach might be too intrusive in a DDD model, because it takes a dependency on ModelState.IsValid from Microsoft.AspNetCore.Mvc.ModelState, which you must call from your MVC controllers.</span></span> <span data-ttu-id="995fb-138">La convalida del modello viene eseguita prima della chiamata di ogni azione del controller e il metodo del controller deve verificare il risultato della chiamata di ModelState.IsValid e rispondere in modo appropriato.</span><span class="sxs-lookup"><span data-stu-id="995fb-138">The model validation occurs prior to each controller action being invoked, and it is the controller method’s responsibility to inspect the result of calling ModelState.IsValid and react appropriately.</span></span> <span data-ttu-id="995fb-139">La scelta di questo approccio dipende dal livello di associazione che si vuole applicare al modello e all'infrastruttura.</span><span class="sxs-lookup"><span data-stu-id="995fb-139">The decision to use it depends on how tightly coupled you want the model to be with that infrastructure.</span></span>

```csharp
using System.ComponentModel.DataAnnotations;
// Other using statements ...
// Entity is a custom base class which has the ID
public class Product : Entity
{
    [Required]
    [StringLength(100)]
    public string Title { get; private set; }

    [Required]
    [Range(0, 999.99)]
    public decimal Price { get; private set; }

    [Required]
    [VintageProduct(1970)]
    [DataType(DataType.Date)]
    public DateTime ReleaseDate { get; private set; }

    [Required]
    [StringLength(1000)]
    public string Description { get; private set; }

    // Constructor...
    // Additional methods for entity logic and constructor...
}
```

<span data-ttu-id="995fb-140">Dal punto di vista di DDD, tuttavia, è consigliabile mantenere un modello di dominio molto semplice tramite l'uso di eccezioni nei metodi di comportamento dell'entità o tramite l'implementazione degli schemi Specification e Notification per applicare le regole di convalida.</span><span class="sxs-lookup"><span data-stu-id="995fb-140">However, from a DDD point of view, the domain model is best kept lean with the use of exceptions in your entity’s behavior methods, or by implementing the Specification and Notification patterns to enforce validation rules.</span></span> <span data-ttu-id="995fb-141">I framework di convalida come le annotazioni dei dati in ASP.NET Core o qualsiasi altro framework di convalida come FluentValidation prevedono un requisito relativo alla chiamata al framework dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="995fb-141">Validation frameworks like data annotations in ASP.NET Core or any other validation frameworks like FluentValidation carry a requirement to invoke the application framework.</span></span> <span data-ttu-id="995fb-142">Quando ad esempio si chiama il metodo ModelState.IsValid nelle annotazioni dei dati, è necessario richiamare i controller ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="995fb-142">For example, when calling the ModelState.IsValid method in data annotations, you need to invoke ASP.NET controllers.</span></span>

<span data-ttu-id="995fb-143">L'uso delle annotazioni dei dati a livello di applicazione nelle classi ViewModel, invece delle entità di dominio, che accetteranno l'input può risultare vantaggioso per consentire la convalida dei modelli entro il livello dell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="995fb-143">It can make sense to use data annotations at the application layer in ViewModel classes (instead of domain entities) that will accept input, to allow for model validation within the UI layer.</span></span> <span data-ttu-id="995fb-144">Questo approccio tuttavia non deve escludere la convalida entro il modello di dominio.</span><span class="sxs-lookup"><span data-stu-id="995fb-144">However, this should not be done at the exclusion of validation within the domain model.</span></span>

### <a name="validating-entities-by-implementing-the-specification-pattern-and-the-notification-pattern"></a><span data-ttu-id="995fb-145">Convalida di entità tramite l'implementazione dello schema Specification e dello schema Notification</span><span class="sxs-lookup"><span data-stu-id="995fb-145">Validating entities by implementing the Specification pattern and the Notification pattern</span></span>

<span data-ttu-id="995fb-146">Un approccio più complesso per l'implementazione delle convalide nel modello di dominio è infine costituito dall'implementazione dello schema Specification insieme allo schema Notification, come illustrato in alcune risorse aggiuntive elencate più avanti.</span><span class="sxs-lookup"><span data-stu-id="995fb-146">Finally, a more elaborate approach to implementing validations in the domain model is by implementing the Specification pattern in conjunction with the Notification pattern, as explained in some of the additional resources listed later.</span></span>

<span data-ttu-id="995fb-147">È importante notare che è possibile usare anche uno solo degli schemi, ad esempio eseguendo la convalida manualmente con le istruzioni di controllo, usando tuttavia lo schema Notification per creare uno stack e restituire un elenco di errori di convalida.</span><span class="sxs-lookup"><span data-stu-id="995fb-147">It is worth mentioning that you can also use just one of those patterns—for example, validating manually with control statements, but using the Notification pattern to stack and return a list of validation errors.</span></span>

### <a name="using-deferred-validation-in-the-domain"></a><span data-ttu-id="995fb-148">Uso della convalida posticipata nel dominio</span><span class="sxs-lookup"><span data-stu-id="995fb-148">Using deferred validation in the domain</span></span>

<span data-ttu-id="995fb-149">Sono disponibili diversi approcci per la gestione delle convalide posticipate nel dominio.</span><span class="sxs-lookup"><span data-stu-id="995fb-149">There are various approaches to deal with deferred validations in the domain.</span></span> <span data-ttu-id="995fb-150">Nel suo manuale [Implementing Domain-Driven Design](https://www.amazon.com/Implementing-Domain-Driven-Design-Vaughn-Vernon/dp/0321834577) (Implementazione della progettazione basata su dominio) Vaughn Vernon illustra tali approcci nella sezione relativa alla convalida.</span><span class="sxs-lookup"><span data-stu-id="995fb-150">In his book [Implementing Domain-Driven Design](https://www.amazon.com/Implementing-Domain-Driven-Design-Vaughn-Vernon/dp/0321834577), Vaughn Vernon discusses these in the section on validation.</span></span>

### <a name="two-step-validation"></a><span data-ttu-id="995fb-151">Convalida in due passaggi</span><span class="sxs-lookup"><span data-stu-id="995fb-151">Two-step validation</span></span>

<span data-ttu-id="995fb-152">È possibile prendere in considerazione anche la convalida in due passaggi.</span><span class="sxs-lookup"><span data-stu-id="995fb-152">Also consider two-step validation.</span></span> <span data-ttu-id="995fb-153">Usare la convalida a livello di campo sugli oggetti di trasferimento dei dati del comando e la convalida a livello di dominio nelle entità.</span><span class="sxs-lookup"><span data-stu-id="995fb-153">Use field-level validation on your command Data Transfer Objects (DTOs) and domain-level validation inside your entities.</span></span> <span data-ttu-id="995fb-154">Per usare questo approccio è possibile restituire un oggetto risultato invece di eccezioni per semplificare la gestione degli errori di convalida.</span><span class="sxs-lookup"><span data-stu-id="995fb-154">You can do this by returning a result object instead exceptions in order to make it easier to deal with the validation errors.</span></span>

<span data-ttu-id="995fb-155">L'uso della convalida dei campi con le annotazioni dei dati, ad esempio, consente di non duplicare la definizione della convalida.</span><span class="sxs-lookup"><span data-stu-id="995fb-155">Using field validation with data annotations, for example, you do not duplicate the validation definition.</span></span> <span data-ttu-id="995fb-156">L'esecuzione tuttavia può essere lato server e lato client nel caso degli oggetti di trasferimento dei dati (comandi e ViewModels, ad esempio).</span><span class="sxs-lookup"><span data-stu-id="995fb-156">The execution, though, can be both server-side and client-side in the case of DTOs (commands and ViewModels, for instance).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="995fb-157">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="995fb-157">Additional resources</span></span>

-   <span data-ttu-id="995fb-158">**Rachel Appel. Introduzione alla convalida del modello in ASP.NET Core MVC**
    [*https://docs.microsoft.com/aspnet/core/mvc/models/validation*](https://docs.microsoft.com/aspnet/core/mvc/models/validation)</span><span class="sxs-lookup"><span data-stu-id="995fb-158">**Rachel Appel. Introduction to model validation in ASP.NET Core MVC**
[*https://docs.microsoft.com/aspnet/core/mvc/models/validation*](https://docs.microsoft.com/aspnet/core/mvc/models/validation)</span></span>

-   <span data-ttu-id="995fb-159">**Rick Anderson. Aggiunta della convalida**
    [*https://docs.microsoft.com/aspnet/core/tutorials/first-mvc-app/validation*](https://docs.microsoft.com/aspnet/core/tutorials/first-mvc-app/validation)</span><span class="sxs-lookup"><span data-stu-id="995fb-159">**Rick Anderson. Adding validation**
[*https://docs.microsoft.com/aspnet/core/tutorials/first-mvc-app/validation*](https://docs.microsoft.com/aspnet/core/tutorials/first-mvc-app/validation)</span></span>

-   <span data-ttu-id="995fb-160">**Martin Fowler. Replacing Throwing Exceptions with Notification in Validations** (Sostituzione della generazione di eccezioni con le notifiche nelle convalide) 
    [*https://martinfowler.com/articles/replaceThrowWithNotification.html*](https://martinfowler.com/articles/replaceThrowWithNotification.html)</span><span class="sxs-lookup"><span data-stu-id="995fb-160">**Martin Fowler. Replacing Throwing Exceptions with Notification in Validations**
[*https://martinfowler.com/articles/replaceThrowWithNotification.html*](https://martinfowler.com/articles/replaceThrowWithNotification.html)</span></span>

-   <span data-ttu-id="995fb-161">**Specification and Notification Patterns** (Schemi Specification e Notification) 
    [*https://www.codeproject.com/Tips/790758/Specification-and-Notification-Patterns*](https://www.codeproject.com/Tips/790758/Specification-and-Notification-Patterns)</span><span class="sxs-lookup"><span data-stu-id="995fb-161">**Specification and Notification Patterns**
[*https://www.codeproject.com/Tips/790758/Specification-and-Notification-Patterns*](https://www.codeproject.com/Tips/790758/Specification-and-Notification-Patterns)</span></span>

-   <span data-ttu-id="995fb-162">**Lev Gorodinski. Validation in Domain-Driven Design (DDD)** (Convalida in DDD) 
    [*http://gorodinski.com/blog/2012/05/19/validation-in-domain-driven-design-ddd/*](http://gorodinski.com/blog/2012/05/19/validation-in-domain-driven-design-ddd/)</span><span class="sxs-lookup"><span data-stu-id="995fb-162">**Lev Gorodinski. Validation in Domain-Driven Design (DDD)**
[*http://gorodinski.com/blog/2012/05/19/validation-in-domain-driven-design-ddd/*](http://gorodinski.com/blog/2012/05/19/validation-in-domain-driven-design-ddd/)</span></span>

-   <span data-ttu-id="995fb-163">**Colin Jack. Domain Model Validation** (Convalida dei modelli di dominio) 
    [*http://colinjack.blogspot.com/2008/03/domain-model-validation.html*](http://colinjack.blogspot.com/2008/03/domain-model-validation.html)</span><span class="sxs-lookup"><span data-stu-id="995fb-163">**Colin Jack. Domain Model Validation**
[*http://colinjack.blogspot.com/2008/03/domain-model-validation.html*](http://colinjack.blogspot.com/2008/03/domain-model-validation.html)</span></span>

-   <span data-ttu-id="995fb-164">**Jimmy Bogard. Validation in a DDD world** (Convalida in ambito DDD) 
    [*https://lostechies.com/jimmybogard/2009/02/15/validation-in-a-ddd-world/*](https://lostechies.com/jimmybogard/2009/02/15/validation-in-a-ddd-world/)</span><span class="sxs-lookup"><span data-stu-id="995fb-164">**Jimmy Bogard. Validation in a DDD world**
[*https://lostechies.com/jimmybogard/2009/02/15/validation-in-a-ddd-world/*](https://lostechies.com/jimmybogard/2009/02/15/validation-in-a-ddd-world/)</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="995fb-165">[Indietro] (enumeration-classes-over-enum-types.md) [Avanti] (client-side-validation.md)</span><span class="sxs-lookup"><span data-stu-id="995fb-165">[Previous] (enumeration-classes-over-enum-types.md) [Next] (client-side-validation.md)</span></span>

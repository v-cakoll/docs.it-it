---
title: Progettazione di convalide nel livello del modello di dominio
description: Architettura di Microservizi .NET per le applicazioni nei contenitori .NET | Progettazione di convalide nel livello del modello di dominio
keywords: Docker, microservizi, ASP.NET, contenitore
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: f4870d0568c3539f296bcb3f577291cb0250cfca
ms.sourcegitcommit: 62d3e3e74c1b7ffa927590012c0b9f87de1b0848
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2017
---
# <a name="designing-validations-in-the-domain-model-layer"></a><span data-ttu-id="eca94-104">Progettazione di convalide nel livello del modello di dominio</span><span class="sxs-lookup"><span data-stu-id="eca94-104">Designing validations in the domain model layer</span></span>

<span data-ttu-id="eca94-105">In DDD, le regole di convalida possono essere considerate come invarianti.</span><span class="sxs-lookup"><span data-stu-id="eca94-105">In DDD, validation rules can be thought as invariants.</span></span> <span data-ttu-id="eca94-106">Il compito principale di un'aggregazione consiste nell'imporre invarianti le modifiche di stato per tutte le entità all'interno di tale aggregazione.</span><span class="sxs-lookup"><span data-stu-id="eca94-106">The main responsibility of an aggregate is to enforce invariants across state changes for all the entities within that aggregate.</span></span>

<span data-ttu-id="eca94-107">Entità di dominio deve essere sempre entità valida.</span><span class="sxs-lookup"><span data-stu-id="eca94-107">Domain entities should always be valid entities.</span></span> <span data-ttu-id="eca94-108">Esistono un certo numero di invarianti per un oggetto che deve essere sempre true.</span><span class="sxs-lookup"><span data-stu-id="eca94-108">There are a certain number of invariants for an object that should always be true.</span></span> <span data-ttu-id="eca94-109">Ad esempio, è sempre un oggetto elemento di ordine deve disporre di una quantità che deve essere un numero intero positivo e un nome di articolo e prezzo.</span><span class="sxs-lookup"><span data-stu-id="eca94-109">For example, an order item object always has to have a quantity that must be a positive integer, plus an article name and price.</span></span> <span data-ttu-id="eca94-110">Pertanto, l'imposizione invarianti è responsabilità dell'entità di dominio (in particolare di aggregazione radice) e un oggetto entità non deve essere in grado di non essere validi.</span><span class="sxs-lookup"><span data-stu-id="eca94-110">Therefore, invariants enforcement is the responsibility of the domain entities (especially of the aggregate root) and an entity object should not be able to exist without being valid.</span></span> <span data-ttu-id="eca94-111">Regole invariante semplicemente sono espressi come contratti e le eccezioni o le notifiche vengono generate quando essi vengono violati.</span><span class="sxs-lookup"><span data-stu-id="eca94-111">Invariant rules are simply expressed as contracts, and exceptions or notifications are raised when they are violated.</span></span>

<span data-ttu-id="eca94-112">La giustificazione è che molti bug si verificano perché gli oggetti sono in uno stato che avrebbero non dovuto essere mai in.</span><span class="sxs-lookup"><span data-stu-id="eca94-112">The reasoning behind this is that many bugs occur because objects are in a state they should never have been in.</span></span> <span data-ttu-id="eca94-113">Di seguito è riportato una spiegazione chiara da Greg Young in un [conversazione](http://jeffreypalermo.com/blog/the-fallacy-of-the-always-valid-entity/):</span><span class="sxs-lookup"><span data-stu-id="eca94-113">The following is a good explanation from Greg Young in an [online discussion](http://jeffreypalermo.com/blog/the-fallacy-of-the-always-valid-entity/):</span></span>

<span data-ttu-id="eca94-114">Di seguito viene proposto che è ora disponibile un SendUserCreationEmailService che accetta un UserProfile … come possiamo è razionalizzare in quel servizio nome non è null?</span><span class="sxs-lookup"><span data-stu-id="eca94-114">Let's propose we now have a SendUserCreationEmailService that takes a UserProfile ... how can we rationalize in that service that Name is not null?</span></span> <span data-ttu-id="eca94-115">È ripetere il controllo?</span><span class="sxs-lookup"><span data-stu-id="eca94-115">Do we check it again?</span></span> <span data-ttu-id="eca94-116">O più probabile che... semplicemente, non preoccuparti per controllare e "auguriamo per ottenere la migliore", che si spera che qualcuno preoccupare di convalida prima di inviarlo all'utente.</span><span class="sxs-lookup"><span data-stu-id="eca94-116">Or more likely ... you just don't bother to check and "hope for the best"—you hope that someone bothered to validate it before sending it to you.</span></span> <span data-ttu-id="eca94-117">Naturalmente, Usa TDD uno dei test prima che si dovrebbe essere scritto è che, se si invia un cliente con un nome null deve essere generato un errore.</span><span class="sxs-lookup"><span data-stu-id="eca94-117">Of course, using TDD one of the first tests we should be writing is that if I send a customer with a null name that it should raise an error.</span></span> <span data-ttu-id="eca94-118">Ma quando si inizia la scrittura di questi tipi di test in modo continuativo si... "se è mai consentito nome diventi null non sono tutti di questi test"</span><span class="sxs-lookup"><span data-stu-id="eca94-118">But once we start writing these kinds of tests over and over again we realize ... "wait if we never allowed name to become null we wouldn't have all of these tests"</span></span>

## <a name="implementing-validations-in-the-domain-model-layer"></a><span data-ttu-id="eca94-119">Implementazione di convalide nel livello del modello di dominio</span><span class="sxs-lookup"><span data-stu-id="eca94-119">Implementing validations in the domain model layer</span></span>

<span data-ttu-id="eca94-120">Le convalide vengono in genere implementate in costruttori di entità di dominio o in metodi che è possano aggiornare l'entità.</span><span class="sxs-lookup"><span data-stu-id="eca94-120">Validations are usually implemented in domain entity constructors or in methods that can update the entity.</span></span> <span data-ttu-id="eca94-121">Esistono diversi modi per implementare le convalide, ad esempio dati di verifica e la generazione di eccezioni se la convalida non riesce.</span><span class="sxs-lookup"><span data-stu-id="eca94-121">There are multiple ways to implement validations, such as verifying data and raising exceptions if the validation fails.</span></span> <span data-ttu-id="eca94-122">Esistono anche modelli più avanzati, ad esempio usando il modello specifica per le convalide e il modello di notifica per restituire una raccolta di errori anziché restituire un'eccezione per ogni convalida quando si verifica.</span><span class="sxs-lookup"><span data-stu-id="eca94-122">There are also more advanced patterns such as using the Specification pattern for validations, and the Notification pattern to return a collection of errors instead of returning an exception for each validation as it occurs.</span></span>

### <a name="validating-conditions-and-throwing-exceptions"></a><span data-ttu-id="eca94-123">Le condizioni di convalida e generazione di eccezioni</span><span class="sxs-lookup"><span data-stu-id="eca94-123">Validating conditions and throwing exceptions</span></span>

<span data-ttu-id="eca94-124">Esempio di codice seguente viene illustrato l'approccio più semplice per la convalida di un'entità di dominio genera un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="eca94-124">The following code example shows the simplest approach to validation in a domain entity by raising an exception.</span></span> <span data-ttu-id="eca94-125">Nella tabella di riferimento alla fine di questa sezione è possibile visualizzare i collegamenti alle implementazioni più avanzate in base agli schemi che sono stati illustrati in precedenza.</span><span class="sxs-lookup"><span data-stu-id="eca94-125">In the references table at the end of this section you can see links to more advanced implementations based on the patterns we have discussed previously.</span></span>

```csharp
public void SetAddress(Address address)
{
    _shippingAddress = address?? throw new ArgumentNullException(nameof(address));
}
```

<span data-ttu-id="eca94-126">Un esempio migliore sarebbe illustrano la necessità di verificare che lo stato interno non sono stati modificati o che tutte le modifiche per un metodo si è verificato.</span><span class="sxs-lookup"><span data-stu-id="eca94-126">A better example would demonstrate the need to ensure that either the internal state did not change, or that all the mutations for a method occurred.</span></span> <span data-ttu-id="eca94-127">Ad esempio, l'implementazione seguente lascia l'oggetto in uno stato non valido:</span><span class="sxs-lookup"><span data-stu-id="eca94-127">For example, the following implementation would leave the object in an invalid state:</span></span>

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

<span data-ttu-id="eca94-128">Se il valore dello stato è valido, la prima riga dell'indirizzo e la città sono già stati modificati.</span><span class="sxs-lookup"><span data-stu-id="eca94-128">If the value of the state is invalid, the first address line and the city have already been changed.</span></span> <span data-ttu-id="eca94-129">Che potrebbe rendere l'indirizzo non valido.</span><span class="sxs-lookup"><span data-stu-id="eca94-129">That might make the address invalid.</span></span>

<span data-ttu-id="eca94-130">Un approccio simile può essere utilizzato nel costruttore dell'entità, generare un'eccezione per assicurarsi che l'entità sia valido dopo averla creata.</span><span class="sxs-lookup"><span data-stu-id="eca94-130">A similar approach can be used in the entity’s constructor, raising an exception to make sure that the entity is valid once it is created.</span></span>

### <a name="using-validation-attributes-in-the-model-based-on-data-annotations"></a><span data-ttu-id="eca94-131">Utilizzo degli attributi di convalida del modello in base alle annotazioni dati</span><span class="sxs-lookup"><span data-stu-id="eca94-131">Using validation attributes in the model based on data annotations</span></span>

<span data-ttu-id="eca94-132">Un altro approccio consiste nell'utilizzare attributi di convalida in base alle annotazioni dei dati.</span><span class="sxs-lookup"><span data-stu-id="eca94-132">Another approach is to use validation attributes based on data annotations.</span></span> <span data-ttu-id="eca94-133">Gli attributi di convalida consentono di configurare la convalida del modello, che è concettualmente simile convalida nei campi nelle tabelle di database.</span><span class="sxs-lookup"><span data-stu-id="eca94-133">Validation attributes provide a way to configure model validation, which is similar conceptually to validation on fields in database tables.</span></span> <span data-ttu-id="eca94-134">Sono inclusi i vincoli, ad esempio l'assegnazione di tipi di dati o i campi obbligatori.</span><span class="sxs-lookup"><span data-stu-id="eca94-134">This includes constraints such as assigning data types or required fields.</span></span> <span data-ttu-id="eca94-135">Altri tipi di convalida includono l'applicazione di modelli per i dati per applicare le regole di business, ad esempio un numero di carta di credito, il numero di telefono o indirizzo di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="eca94-135">Other types of validation include applying patterns to data to enforce business rules, such as a credit card number, phone number, or email address.</span></span> <span data-ttu-id="eca94-136">Gli attributi di convalida rendono più semplice applicare requisiti.</span><span class="sxs-lookup"><span data-stu-id="eca94-136">Validation attributes make it easy to enforce requirements.</span></span>

<span data-ttu-id="eca94-137">Tuttavia, come illustrato nel codice seguente, questo approccio potrebbe essere troppo intrusivo in un modello DDD, poiché assume una dipendenza ModelState.IsValid da Microsoft.AspNetCore.Mvc.ModelState, che è necessario chiamare da controller MVC.</span><span class="sxs-lookup"><span data-stu-id="eca94-137">However, as shown in the following code, this approach might be too intrusive in a DDD model, because it takes a dependency on ModelState.IsValid from Microsoft.AspNetCore.Mvc.ModelState, which you must call from your MVC controllers.</span></span> <span data-ttu-id="eca94-138">Si verifica la convalida del modello prima di ogni azione del controller richiamato e, è responsabilità del metodo del controller per controllare il risultato della chiamata ModelState.IsValid e rispondere nel modo appropriato.</span><span class="sxs-lookup"><span data-stu-id="eca94-138">The model validation occurs prior to each controller action being invoked, and it is the controller method’s responsibility to inspect the result of calling ModelState.IsValid and react appropriately.</span></span> <span data-ttu-id="eca94-139">La decisione di usarla dipende strettamente si desidera che il modello da utilizzare con l'infrastruttura.</span><span class="sxs-lookup"><span data-stu-id="eca94-139">The decision to use it depends on how tightly coupled you want the model to be with that infrastructure.</span></span>

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

<span data-ttu-id="eca94-140">Tuttavia, dal punto di vista DDD, il modello di dominio è preferibile mantenere pulito con l'utilizzo delle eccezioni nei metodi di comportamento dell'entità o mediante l'implementazione di modelli specifica e di notifica per applicare le regole di convalida.</span><span class="sxs-lookup"><span data-stu-id="eca94-140">However, from a DDD point of view, the domain model is best kept lean with the use of exceptions in your entity’s behavior methods, or by implementing the Specification and Notification patterns to enforce validation rules.</span></span> <span data-ttu-id="eca94-141">Il framework di convalida come le annotazioni dei dati in ASP.NET Core o altri framework di convalida come FluentValidation contengono un requisito per richiamare il framework dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="eca94-141">Validation frameworks like data annotations in ASP.NET Core or any other validation frameworks like FluentValidation carry a requirement to invoke the application framework.</span></span> <span data-ttu-id="eca94-142">Ad esempio, quando si chiama il metodo ModelState.IsValid nelle annotazioni dei dati, è necessario richiamare il controller di ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="eca94-142">For example, when calling the ModelState.IsValid method in data annotations, you need to invoke ASP.NET controllers.</span></span>

<span data-ttu-id="eca94-143">Senso per utilizzare le annotazioni dei dati al livello dell'applicazione nelle classi ViewModel (anziché le entità di dominio) che accetta l'input, per consentire la convalida del modello all'interno del livello dell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="eca94-143">It can make sense to use data annotations at the application layer in ViewModel classes (instead of domain entities) that will accept input, to allow for model validation within the UI layer.</span></span> <span data-ttu-id="eca94-144">Tuttavia, questo non deve essere eseguito all'esclusione di convalida all'interno del modello di dominio.</span><span class="sxs-lookup"><span data-stu-id="eca94-144">However, this should not be done at the exclusion of validation within the domain model.</span></span>

### <a name="validating-entities-by-implementing-the-specification-pattern-and-the-notification-pattern"></a><span data-ttu-id="eca94-145">Convalida l'entità implementando il modello specifica e il modello di notifica</span><span class="sxs-lookup"><span data-stu-id="eca94-145">Validating entities by implementing the Specification pattern and the Notification pattern</span></span>

<span data-ttu-id="eca94-146">Infine, un approccio più complesso per l'implementazione delle convalide del modello di dominio è implementando il modello specifica in combinazione con il modello di notifica, come illustrato in alcune risorse aggiuntive elencate più avanti.</span><span class="sxs-lookup"><span data-stu-id="eca94-146">Finally, a more elaborate approach to implementing validations in the domain model is by implementing the Specification pattern in conjunction with the Notification pattern, as explained in some of the additional resources listed later.</span></span>

<span data-ttu-id="eca94-147">È importante ricordare che è possibile utilizzare anche solo uno di questi modelli, ad esempio, la convalida manualmente con le istruzioni di controllo, ma usando il modello di notifica dello stack e restituire un elenco di errori di convalida.</span><span class="sxs-lookup"><span data-stu-id="eca94-147">It is worth mentioning that you can also use just one of those patterns—for example, validating manually with control statements, but using the Notification pattern to stack and return a list of validation errors.</span></span>

### <a name="using-deferred-validation-in-the-domain"></a><span data-ttu-id="eca94-148">Tramite la convalida posticipata nel dominio</span><span class="sxs-lookup"><span data-stu-id="eca94-148">Using deferred validation in the domain</span></span>

<span data-ttu-id="eca94-149">Esistono diversi approcci per affrontare le convalide posticipate nel dominio.</span><span class="sxs-lookup"><span data-stu-id="eca94-149">There are various approaches to deal with deferred validations in the domain.</span></span> <span data-ttu-id="eca94-150">Nel suo libro [Implementing Domain-Driven progettazione](https://www.amazon.com/Implementing-Domain-Driven-Design-Vaughn-Vernon/dp/0321834577), Vaughn Vernon illustra queste nella sezione sulla convalida.</span><span class="sxs-lookup"><span data-stu-id="eca94-150">In his book [Implementing Domain-Driven Design](https://www.amazon.com/Implementing-Domain-Driven-Design-Vaughn-Vernon/dp/0321834577), Vaughn Vernon discusses these in the section on validation.</span></span>

### <a name="two-step-validation"></a><span data-ttu-id="eca94-151">Convalida in due passaggi</span><span class="sxs-lookup"><span data-stu-id="eca94-151">Two-step validation</span></span>

<span data-ttu-id="eca94-152">Considerare inoltre la convalida in due passaggi.</span><span class="sxs-lookup"><span data-stu-id="eca94-152">Also consider two-step validation.</span></span> <span data-ttu-id="eca94-153">Utilizzare la convalida a livello di campo nel comando dati trasferire oggetti DTO e la convalida a livello di dominio le entità.</span><span class="sxs-lookup"><span data-stu-id="eca94-153">Use field-level validation on your command Data Transfer Objects (DTOs) and domain-level validation inside your entities.</span></span> <span data-ttu-id="eca94-154">Ciò si realizza tramite la restituzione di un oggetto risultato invece le eccezioni per renderlo più semplice gestire gli errori di convalida.</span><span class="sxs-lookup"><span data-stu-id="eca94-154">You can do this by returning a result object instead exceptions in order to make it easier to deal with the validation errors.</span></span>

<span data-ttu-id="eca94-155">Utilizza la convalida dei campi con le annotazioni dei dati, ad esempio, si effettua la duplicazione la definizione di convalida.</span><span class="sxs-lookup"><span data-stu-id="eca94-155">Using field validation with data annotations, for example, you do not duplicate the validation definition.</span></span> <span data-ttu-id="eca94-156">L'esecuzione, tuttavia, può essere sul lato server sia lato client nel caso di DTO (comandi e ViewModel, ad esempio).</span><span class="sxs-lookup"><span data-stu-id="eca94-156">The execution, though, can be both server-side and client-side in the case of DTOs (commands and ViewModels, for instance).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="eca94-157">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="eca94-157">Additional resources</span></span>

-   <span data-ttu-id="eca94-158">**Rachel Appel. Introduzione alla convalida del modello in ASP.NET MVC Core**
    [*https://docs.microsoft.com/aspnet/core/mvc/models/validation*](https://docs.microsoft.com/aspnet/core/mvc/models/validation)</span><span class="sxs-lookup"><span data-stu-id="eca94-158">**Rachel Appel. Introduction to model validation in ASP.NET Core MVC**
[*https://docs.microsoft.com/aspnet/core/mvc/models/validation*](https://docs.microsoft.com/aspnet/core/mvc/models/validation)</span></span>

-   <span data-ttu-id="eca94-159">**Rick Anderson. Aggiunta della convalida**
    [*https://docs.microsoft.com/aspnet/core/tutorials/first-mvc-app/validation*](https://docs.microsoft.com/aspnet/core/tutorials/first-mvc-app/validation)</span><span class="sxs-lookup"><span data-stu-id="eca94-159">**Rick Anderson. Adding validation**
[*https://docs.microsoft.com/aspnet/core/tutorials/first-mvc-app/validation*](https://docs.microsoft.com/aspnet/core/tutorials/first-mvc-app/validation)</span></span>

-   <span data-ttu-id="eca94-160">**Martin Fowler. Sostituzione di generare un'eccezione con la notifica convalide**
    [*https://martinfowler.com/articles/replaceThrowWithNotification.html*](https://martinfowler.com/articles/replaceThrowWithNotification.html)</span><span class="sxs-lookup"><span data-stu-id="eca94-160">**Martin Fowler. Replacing Throwing Exceptions with Notification in Validations**
[*https://martinfowler.com/articles/replaceThrowWithNotification.html*](https://martinfowler.com/articles/replaceThrowWithNotification.html)</span></span>

-   <span data-ttu-id="eca94-161">**Specifica e i modelli di notifica**
    [*https://www.codeproject.com/Tips/790758/Specification-and-Notification-Patterns*](https://www.codeproject.com/Tips/790758/Specification-and-Notification-Patterns)</span><span class="sxs-lookup"><span data-stu-id="eca94-161">**Specification and Notification Patterns**
[*https://www.codeproject.com/Tips/790758/Specification-and-Notification-Patterns*](https://www.codeproject.com/Tips/790758/Specification-and-Notification-Patterns)</span></span>

-   <span data-ttu-id="eca94-162">**Gorodinski Lev. Convalida progettazione basati su dominio (DDD)**
    [*http://gorodinski.com/blog/2012/05/19/validation-in-domain-driven-design-ddd/*](http://gorodinski.com/blog/2012/05/19/validation-in-domain-driven-design-ddd/)</span><span class="sxs-lookup"><span data-stu-id="eca94-162">**Lev Gorodinski. Validation in Domain-Driven Design (DDD)**
[*http://gorodinski.com/blog/2012/05/19/validation-in-domain-driven-design-ddd/*](http://gorodinski.com/blog/2012/05/19/validation-in-domain-driven-design-ddd/)</span></span>

-   <span data-ttu-id="eca94-163">**Colin presa. La convalida del modello di dominio**
    [*http://colinjack.blogspot.com/2008/03/domain-model-validation.html*](http://colinjack.blogspot.com/2008/03/domain-model-validation.html)</span><span class="sxs-lookup"><span data-stu-id="eca94-163">**Colin Jack. Domain Model Validation**
[*http://colinjack.blogspot.com/2008/03/domain-model-validation.html*](http://colinjack.blogspot.com/2008/03/domain-model-validation.html)</span></span>

-   <span data-ttu-id="eca94-164">**Jimmy Bogard. Convalida in un mondo DDD**
    [*https://lostechies.com/jimmybogard/2009/02/15/validation-in-a-ddd-world/*](https://lostechies.com/jimmybogard/2009/02/15/validation-in-a-ddd-world/)</span><span class="sxs-lookup"><span data-stu-id="eca94-164">**Jimmy Bogard. Validation in a DDD world**
[*https://lostechies.com/jimmybogard/2009/02/15/validation-in-a-ddd-world/*](https://lostechies.com/jimmybogard/2009/02/15/validation-in-a-ddd-world/)</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="eca94-165">[Precedente] (enumerazione-classi-over-enum-types.md) [Avanti] (validation.md client-side)</span><span class="sxs-lookup"><span data-stu-id="eca94-165">[Previous] (enumeration-classes-over-enum-types.md) [Next] (client-side-validation.md)</span></span>

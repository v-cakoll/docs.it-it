---
title: Progettazione di convalide nel livello del modello di dominio
description: Architettura di microservizi .NET per applicazioni .NET in contenitori | Progettazione di convalide nel livello del modello di dominio
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.openlocfilehash: 6ff325bb062da2ebff815fc847d2247707a0bf7f
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2018
ms.locfileid: "50188053"
---
# <a name="designing-validations-in-the-domain-model-layer"></a>Progettazione di convalide nel livello del modello di dominio

In DDD le regole di convalida possono essere considerate invariabili. Lo scopo principale di un'aggregazione consiste nell'applicare invariabili tra modifiche dello stato per tutte le entità entro tale aggregazione.

Le entità di dominio devono essere sempre entità valide. Alcune invariabili per un oggetto devono essere sempre true. Ad esempio, la quantità di un oggetto di tipo articolo dell'ordine deve essere sempre un numero intero positivo e tale oggetto deve includere anche un nome di articolo e il prezzo. L'applicazione delle invariabili è quindi responsabilità delle entità di dominio, in particolare per la radice dell'aggregazione, e l'oggetto entità non può esistere senza essere valido. Le regole delle invariabili vengono semplicemente espresse come contratti e vengono generate eccezioni o notifiche in caso di violazione.

È infatti possibile che vengano generati molti bug perché gli oggetti hanno uno stato non previsto. Greg Young fornisce una spiegazione eccellente in una [discussione online](https://jeffreypalermo.com/blog/the-fallacy-of-the-always-valid-entity/):

Si supponga che sia disponibile un SendUserCreationEmailService che accetta un valore UserProfile. È necessario stabilire come razionalizzare il fatto che il nome non sia Null in tale servizio. È ad esempio possibile controllarlo di nuovo oppure è semplicemente possibile non controllare e augurarsi che il nome sia stato convalidato prima dell'invio. Usando TDD è ovviamente consigliabile scrivere prima di tutto un test in modo che venga generato un errore in caso di invio di un cliente con nome Null. Quando tuttavia si scrivono ripetutamente test di questo tipo, ci si rende conto che se non si consente mai al nome di essere Null non sarebbe necessario scrivere i test.

## <a name="implementing-validations-in-the-domain-model-layer"></a>Implementazione di convalide nel livello del modello di dominio

Le convalide vengono in genere implementate nei costruttori delle entità di dominio o nei metodi in grado di aggiornare l'entità. È possibile implementare le convalide in molti modi, ad esempio verificando i dati e generando eccezioni in caso di esito negativo della convalida. Sono disponibili anche schemi più avanzati, ad esempio l'uso dello schema Specification per le convalide e dello schema Notification per la restituzione di una raccolta di errori invece di restituire un'eccezione per ogni convalida eseguita.

### <a name="validating-conditions-and-throwing-exceptions"></a>Convalida delle condizioni e generazione delle eccezioni

L'esempio di codice seguente mostra l'approccio più semplice per la convalida in una entità di dominio tramite la generazione di un'eccezione. Nella tabella dei riferimenti alla fine di questa sezione sono disponibili collegamenti a implementazioni più avanzate basate sugli schemi illustrati in precedenza.

```csharp
public void SetAddress(Address address)
{
    _shippingAddress = address?? throw new ArgumentNullException(nameof(address));
}
```

Un esempio migliore consente di dimostrare la necessità di assicurare che lo stato interno non abbia subito modifiche o che si siano verificate tutte le mutazioni per un metodo. L'implementazione seguente, ad esempio, lascia l'oggetto in uno stato non valido:

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

Se il valore dello stato non è valido, la prima riga dell'indirizzo e la città sono già state modificate. È quindi possibile che l'indirizzo non sia valido.

Un approccio simile può essere usato nel costruttore dell'entità, generando un'eccezione per assicurarsi che l'entità sia valida dopo la creazione.

### <a name="using-validation-attributes-in-the-model-based-on-data-annotations"></a>Uso degli attributi di convalida nel modello in base alle annotazioni dei dati

Un altro approccio prevede l'uso degli attributi di convalida in base alle annotazioni dei dati. Gli attributi di convalida consentono di configurare la convalida. Concettualmente assomigliano alla convalida nei campi delle tabelle del database. Esistono vincoli, ad esempio l'assegnazione di tipi di dati o campi obbligatori. Altri tipi di convalida includono l'uso di schemi di dati per applicare le regole di business, ad esempio un numero di carta di credito, il numero di telefono o un indirizzo di posta elettronica. Gli attributi di convalida semplificano l'applicazione dei requisiti.

Come mostrato nel codice seguente, tuttavia, questo approccio potrebbe essere troppo invadente in un modello DDD, perché accetta una dipendenza su ModelState.IsValid da Microsoft.AspNetCore.Mvc.ModelState, che deve essere chiamato dai controller MVC. La convalida del modello viene eseguita prima della chiamata di ogni azione del controller e il metodo del controller deve verificare il risultato della chiamata di ModelState.IsValid e rispondere in modo appropriato. La scelta di questo approccio dipende dal livello di associazione che si vuole applicare al modello e all'infrastruttura.

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

Dal punto di vista di DDD, tuttavia, è consigliabile mantenere un modello di dominio molto semplice tramite l'uso di eccezioni nei metodi di comportamento dell'entità o tramite l'implementazione degli schemi Specification e Notification per applicare le regole di convalida. I framework di convalida come le annotazioni dei dati in ASP.NET Core o qualsiasi altro framework di convalida come FluentValidation prevedono un requisito relativo alla chiamata al framework dell'applicazione. Quando ad esempio si chiama il metodo ModelState.IsValid nelle annotazioni dei dati, è necessario richiamare i controller ASP.NET.

L'uso delle annotazioni dei dati a livello di applicazione nelle classi ViewModel, invece delle entità di dominio, che accetteranno l'input può risultare vantaggioso per consentire la convalida dei modelli entro il livello dell'interfaccia utente. Questo approccio tuttavia non deve escludere la convalida entro il modello di dominio.

### <a name="validating-entities-by-implementing-the-specification-pattern-and-the-notification-pattern"></a>Convalida di entità tramite l'implementazione dello schema Specification e dello schema Notification

Un approccio più complesso per l'implementazione delle convalide nel modello di dominio è infine costituito dall'implementazione dello schema Specification insieme allo schema Notification, come illustrato in alcune risorse aggiuntive elencate più avanti.

È importante notare che è possibile usare anche uno solo degli schemi, ad esempio eseguendo la convalida manualmente con le istruzioni di controllo, usando tuttavia lo schema Notification per creare uno stack e restituire un elenco di errori di convalida.

### <a name="using-deferred-validation-in-the-domain"></a>Uso della convalida posticipata nel dominio

Sono disponibili diversi approcci per la gestione delle convalide posticipate nel dominio. Nel suo manuale [Implementing Domain-Driven Design](https://www.amazon.com/Implementing-Domain-Driven-Design-Vaughn-Vernon/dp/0321834577) (Implementazione della progettazione basata su dominio) Vaughn Vernon illustra tali approcci nella sezione relativa alla convalida.

### <a name="two-step-validation"></a>Convalida in due passaggi

È possibile prendere in considerazione anche la convalida in due passaggi. Usare la convalida a livello di campo sugli oggetti di trasferimento dei dati del comando e la convalida a livello di dominio nelle entità. Per usare questo approccio è possibile restituire un oggetto risultato invece di eccezioni per semplificare la gestione degli errori di convalida.

L'uso della convalida dei campi con le annotazioni dei dati, ad esempio, consente di non duplicare la definizione della convalida. L'esecuzione tuttavia può essere lato server e lato client nel caso degli oggetti di trasferimento dei dati (comandi e ViewModels, ad esempio).

## <a name="additional-resources"></a>Risorse aggiuntive

-   **Rachel Appel. Introduzione alla convalida del modello in ASP.NET Core MVC**
    [*https://docs.microsoft.com/aspnet/core/mvc/models/validation*](https://docs.microsoft.com/aspnet/core/mvc/models/validation)

-   **Rick Anderson. Aggiunta della convalida**
    [*https://docs.microsoft.com/aspnet/core/tutorials/first-mvc-app/validation*](https://docs.microsoft.com/aspnet/core/tutorials/first-mvc-app/validation)

-   **Martin Fowler. Replacing Throwing Exceptions with Notification in Validations**
    [*https://martinfowler.com/articles/replaceThrowWithNotification.html*](https://martinfowler.com/articles/replaceThrowWithNotification.html) (Sostituzione della generazione di eccezioni con la notifica nelle convalide)

-   **Specification and Notification Patterns**
    [*https://www.codeproject.com/Tips/790758/Specification-and-Notification-Patterns*](https://www.codeproject.com/Tips/790758/Specification-and-Notification-Patterns) (Modelli di specifica e notifica)

-   **Lev Gorodinski. Validation in Domain-Driven Design (DDD)**
    [*http://gorodinski.com/blog/2012/05/19/validation-in-domain-driven-design-ddd/*](http://gorodinski.com/blog/2012/05/19/validation-in-domain-driven-design-ddd/) (Convalida nella progettazione basata su dominio (DDD))

-   **Colin Jack. Domain Model Validation**
    [*http://colinjack.blogspot.com/2008/03/domain-model-validation.html*](http://colinjack.blogspot.com/2008/03/domain-model-validation.html) (Convalida del modello di dominio)

-   **Jimmy Bogard. Validation in a DDD world**
    [*https://lostechies.com/jimmybogard/2009/02/15/validation-in-a-ddd-world/*](https://lostechies.com/jimmybogard/2009/02/15/validation-in-a-ddd-world/) (Convalida in un mondo DDD)


>[!div class="step-by-step"]
[Precedente](enumeration-classes-over-enum-types.md)
[Successivo](client-side-validation.md)

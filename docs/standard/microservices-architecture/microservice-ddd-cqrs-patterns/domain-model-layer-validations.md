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
# <a name="designing-validations-in-the-domain-model-layer"></a>Progettazione di convalide nel livello del modello di dominio

In DDD, le regole di convalida possono essere considerate come invarianti. Il compito principale di un'aggregazione consiste nell'imporre invarianti le modifiche di stato per tutte le entità all'interno di tale aggregazione.

Entità di dominio deve essere sempre entità valida. Esistono un certo numero di invarianti per un oggetto che deve essere sempre true. Ad esempio, è sempre un oggetto elemento di ordine deve disporre di una quantità che deve essere un numero intero positivo e un nome di articolo e prezzo. Pertanto, l'imposizione invarianti è responsabilità dell'entità di dominio (in particolare di aggregazione radice) e un oggetto entità non deve essere in grado di non essere validi. Regole invariante semplicemente sono espressi come contratti e le eccezioni o le notifiche vengono generate quando essi vengono violati.

La giustificazione è che molti bug si verificano perché gli oggetti sono in uno stato che avrebbero non dovuto essere mai in. Di seguito è riportato una spiegazione chiara da Greg Young in un [conversazione](http://jeffreypalermo.com/blog/the-fallacy-of-the-always-valid-entity/):

Di seguito viene proposto che è ora disponibile un SendUserCreationEmailService che accetta un UserProfile … come possiamo è razionalizzare in quel servizio nome non è null? È ripetere il controllo? O più probabile che... semplicemente, non preoccuparti per controllare e "auguriamo per ottenere la migliore", che si spera che qualcuno preoccupare di convalida prima di inviarlo all'utente. Naturalmente, Usa TDD uno dei test prima che si dovrebbe essere scritto è che, se si invia un cliente con un nome null deve essere generato un errore. Ma quando si inizia la scrittura di questi tipi di test in modo continuativo si... "se è mai consentito nome diventi null non sono tutti di questi test"

## <a name="implementing-validations-in-the-domain-model-layer"></a>Implementazione di convalide nel livello del modello di dominio

Le convalide vengono in genere implementate in costruttori di entità di dominio o in metodi che è possano aggiornare l'entità. Esistono diversi modi per implementare le convalide, ad esempio dati di verifica e la generazione di eccezioni se la convalida non riesce. Esistono anche modelli più avanzati, ad esempio usando il modello specifica per le convalide e il modello di notifica per restituire una raccolta di errori anziché restituire un'eccezione per ogni convalida quando si verifica.

### <a name="validating-conditions-and-throwing-exceptions"></a>Le condizioni di convalida e generazione di eccezioni

Esempio di codice seguente viene illustrato l'approccio più semplice per la convalida di un'entità di dominio genera un'eccezione. Nella tabella di riferimento alla fine di questa sezione è possibile visualizzare i collegamenti alle implementazioni più avanzate in base agli schemi che sono stati illustrati in precedenza.

```csharp
public void SetAddress(Address address)
{
    _shippingAddress = address?? throw new ArgumentNullException(nameof(address));
}
```

Un esempio migliore sarebbe illustrano la necessità di verificare che lo stato interno non sono stati modificati o che tutte le modifiche per un metodo si è verificato. Ad esempio, l'implementazione seguente lascia l'oggetto in uno stato non valido:

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

Se il valore dello stato è valido, la prima riga dell'indirizzo e la città sono già stati modificati. Che potrebbe rendere l'indirizzo non valido.

Un approccio simile può essere utilizzato nel costruttore dell'entità, generare un'eccezione per assicurarsi che l'entità sia valido dopo averla creata.

### <a name="using-validation-attributes-in-the-model-based-on-data-annotations"></a>Utilizzo degli attributi di convalida del modello in base alle annotazioni dati

Un altro approccio consiste nell'utilizzare attributi di convalida in base alle annotazioni dei dati. Gli attributi di convalida consentono di configurare la convalida del modello, che è concettualmente simile convalida nei campi nelle tabelle di database. Sono inclusi i vincoli, ad esempio l'assegnazione di tipi di dati o i campi obbligatori. Altri tipi di convalida includono l'applicazione di modelli per i dati per applicare le regole di business, ad esempio un numero di carta di credito, il numero di telefono o indirizzo di posta elettronica. Gli attributi di convalida rendono più semplice applicare requisiti.

Tuttavia, come illustrato nel codice seguente, questo approccio potrebbe essere troppo intrusivo in un modello DDD, poiché assume una dipendenza ModelState.IsValid da Microsoft.AspNetCore.Mvc.ModelState, che è necessario chiamare da controller MVC. Si verifica la convalida del modello prima di ogni azione del controller richiamato e, è responsabilità del metodo del controller per controllare il risultato della chiamata ModelState.IsValid e rispondere nel modo appropriato. La decisione di usarla dipende strettamente si desidera che il modello da utilizzare con l'infrastruttura.

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

Tuttavia, dal punto di vista DDD, il modello di dominio è preferibile mantenere pulito con l'utilizzo delle eccezioni nei metodi di comportamento dell'entità o mediante l'implementazione di modelli specifica e di notifica per applicare le regole di convalida. Il framework di convalida come le annotazioni dei dati in ASP.NET Core o altri framework di convalida come FluentValidation contengono un requisito per richiamare il framework dell'applicazione. Ad esempio, quando si chiama il metodo ModelState.IsValid nelle annotazioni dei dati, è necessario richiamare il controller di ASP.NET.

Senso per utilizzare le annotazioni dei dati al livello dell'applicazione nelle classi ViewModel (anziché le entità di dominio) che accetta l'input, per consentire la convalida del modello all'interno del livello dell'interfaccia utente. Tuttavia, questo non deve essere eseguito all'esclusione di convalida all'interno del modello di dominio.

### <a name="validating-entities-by-implementing-the-specification-pattern-and-the-notification-pattern"></a>Convalida l'entità implementando il modello specifica e il modello di notifica

Infine, un approccio più complesso per l'implementazione delle convalide del modello di dominio è implementando il modello specifica in combinazione con il modello di notifica, come illustrato in alcune risorse aggiuntive elencate più avanti.

È importante ricordare che è possibile utilizzare anche solo uno di questi modelli, ad esempio, la convalida manualmente con le istruzioni di controllo, ma usando il modello di notifica dello stack e restituire un elenco di errori di convalida.

### <a name="using-deferred-validation-in-the-domain"></a>Tramite la convalida posticipata nel dominio

Esistono diversi approcci per affrontare le convalide posticipate nel dominio. Nel suo libro [Implementing Domain-Driven progettazione](https://www.amazon.com/Implementing-Domain-Driven-Design-Vaughn-Vernon/dp/0321834577), Vaughn Vernon illustra queste nella sezione sulla convalida.

### <a name="two-step-validation"></a>Convalida in due passaggi

Considerare inoltre la convalida in due passaggi. Utilizzare la convalida a livello di campo nel comando dati trasferire oggetti DTO e la convalida a livello di dominio le entità. Ciò si realizza tramite la restituzione di un oggetto risultato invece le eccezioni per renderlo più semplice gestire gli errori di convalida.

Utilizza la convalida dei campi con le annotazioni dei dati, ad esempio, si effettua la duplicazione la definizione di convalida. L'esecuzione, tuttavia, può essere sul lato server sia lato client nel caso di DTO (comandi e ViewModel, ad esempio).

## <a name="additional-resources"></a>Risorse aggiuntive

-   **Rachel Appel. Introduzione alla convalida del modello in ASP.NET MVC Core**
    [*https://docs.microsoft.com/aspnet/core/mvc/models/validation*](https://docs.microsoft.com/aspnet/core/mvc/models/validation)

-   **Rick Anderson. Aggiunta della convalida**
    [*https://docs.microsoft.com/aspnet/core/tutorials/first-mvc-app/validation*](https://docs.microsoft.com/aspnet/core/tutorials/first-mvc-app/validation)

-   **Martin Fowler. Sostituzione di generare un'eccezione con la notifica convalide**
    [*https://martinfowler.com/articles/replaceThrowWithNotification.html*](https://martinfowler.com/articles/replaceThrowWithNotification.html)

-   **Specifica e i modelli di notifica**
    [*https://www.codeproject.com/Tips/790758/Specification-and-Notification-Patterns*](https://www.codeproject.com/Tips/790758/Specification-and-Notification-Patterns)

-   **Gorodinski Lev. Convalida progettazione basati su dominio (DDD)**
    [*http://gorodinski.com/blog/2012/05/19/validation-in-domain-driven-design-ddd/*](http://gorodinski.com/blog/2012/05/19/validation-in-domain-driven-design-ddd/)

-   **Colin presa. La convalida del modello di dominio**
    [*http://colinjack.blogspot.com/2008/03/domain-model-validation.html*](http://colinjack.blogspot.com/2008/03/domain-model-validation.html)

-   **Jimmy Bogard. Convalida in un mondo DDD**
    [*https://lostechies.com/jimmybogard/2009/02/15/validation-in-a-ddd-world/*](https://lostechies.com/jimmybogard/2009/02/15/validation-in-a-ddd-world/)


>[!div class="step-by-step"]
[Precedente] (enumerazione-classi-over-enum-types.md) [Avanti] (validation.md client-side)

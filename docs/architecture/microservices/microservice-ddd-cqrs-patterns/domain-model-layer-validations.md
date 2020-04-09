---
title: Progettazione di convalide nel livello del modello di dominio
description: Architettura di microservizi .NET per applicazioni .NET in contenitori | Informazioni sui concetti chiave delle convalide del modello di dominio.
ms.date: 10/08/2018
ms.openlocfilehash: d2efc5f3b3267c4573409952791c6e883a01aae2
ms.sourcegitcommit: e3cbf26d67f7e9286c7108a2752804050762d02d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2020
ms.locfileid: "80988505"
---
# <a name="design-validations-in-the-domain-model-layer"></a>Progettare convalide nel livello del modello di dominio

In DDD le regole di convalida possono essere considerate invariabili. Lo scopo principale di un'aggregazione consiste nell'applicare invariabili tra modifiche dello stato per tutte le entità entro tale aggregazione.

Le entità di dominio devono essere sempre entità valide. Alcune invariabili per un oggetto devono essere sempre true. Ad esempio, la quantità di un oggetto di tipo articolo dell'ordine deve essere sempre un numero intero positivo e tale oggetto deve includere anche un nome di articolo e il prezzo. L'applicazione delle invariabili è quindi responsabilità delle entità di dominio, in particolare per la radice dell'aggregazione, e l'oggetto entità non può esistere senza essere valido. Le regole delle invariabili vengono semplicemente espresse come contratti e vengono generate eccezioni o notifiche in caso di violazione.

È infatti possibile che vengano generati molti bug perché gli oggetti hanno uno stato non previsto. Greg Young fornisce una spiegazione eccellente in una [discussione online](https://jeffreypalermo.com/2009/05/the-fallacy-of-the-always-valid-entity/):

Si supponga che sia disponibile un SendUserCreationEmailService che accetta un valore UserProfile. È necessario stabilire come razionalizzare il fatto che il nome non sia Null in tale servizio. È ad esempio possibile controllarlo di nuovo oppure è semplicemente possibile non controllare e augurarsi che il nome sia stato convalidato prima dell'invio. Usando TDD è ovviamente consigliabile scrivere prima di tutto un test in modo che venga generato un errore in caso di invio di un cliente con nome Null. Quando tuttavia si scrivono ripetutamente test di questo tipo, ci si rende conto che se non si consente mai al nome di essere Null non sarebbe necessario scrivere i test.

## <a name="implement-validations-in-the-domain-model-layer"></a>Implementare convalide nel livello del modello di dominio

Le convalide vengono in genere implementate nei costruttori delle entità di dominio o nei metodi in grado di aggiornare l'entità. È possibile implementare le convalide in molti modi, ad esempio verificando i dati e generando eccezioni in caso di esito negativo della convalida. Sono disponibili anche schemi più avanzati, ad esempio l'uso dello schema Specification per le convalide e dello schema Notification per la restituzione di una raccolta di errori invece di restituire un'eccezione per ogni convalida eseguita.

### <a name="validate-conditions-and-throw-exceptions"></a>Convalidare le condizioni e generare eccezioni

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
    _shippingAddress.line1 = line1 ?? throw new ...
    _shippingAddress.line2 = line2;
    _shippingAddress.city = city ?? throw new ...
    _shippingAddress.state = (IsValid(state) ? state : throw new …);
}
```

Se il valore dello stato non è valido, la prima riga dell'indirizzo e la città sono già state modificate. È quindi possibile che l'indirizzo non sia valido.

Un approccio simile può essere usato nel costruttore dell'entità, generando un'eccezione per assicurarsi che l'entità sia valida una volta creata.

### <a name="use-validation-attributes-in-the-model-based-on-data-annotations"></a>Usare gli attributi di convalida nel modello in base alle annotazioni dei dati

Le annotazioni dei dati, come gli attributi Required o MaxLength, possono essere usate per configurare le proprietà dei campi di database EF Core, come illustrato in dettaglio nella sezione [Mapping di tabella](infrastructure-persistence-layer-implemenation-entity-framework-core.md#table-mapping) ma [non funzionano più per la convalida di entità in EF Core](https://github.com/dotnet/efcore/issues/3680) (e nemmeno il metodo <xref:System.ComponentModel.DataAnnotations.IValidatableObject.Validate%2A?displayProperty=nameWithType>), come invece era il caso fino a EF 4.x in .NET Framework.

Le annotazioni <xref:System.ComponentModel.DataAnnotations.IValidatableObject> dei dati e l'interfaccia possono comunque essere utilizzate per la convalida del modello durante l'associazione del modello, prima della chiamata alle azioni del controller come di consueto, ma tale modello deve essere un ViewModel o DTO e si tratta di un problema MVC o API e non di un problema di modello di dominio.

Una volta chiarita la differenza concettuale, è possibile comunque usare le annotazioni dei dati e `IValidatableObject` nella classe dell'entità per la convalida, se le azioni ricevono un parametro di oggetto classe di entità, eventualità non consigliata. In tal caso, la convalida verrà eseguita durante l'associazione del modello, appena prima di richiamare l'azione ed è possibile controllare il controller ModelState.IsValid proprietà per controllare il risultato, ma poi nuovamente, si verifica nel controller, non prima di rendere persistente l'oggetto entità nel DbContext, come aveva fatto da EF 4.x.

È comunque possibile implementare la convalida personalizzata `IValidatableObject.Validate` nella classe di entità usando le annotazioni dei dati e il metodo, eseguendo l'override del metodo SaveChanges di DbContext.You can still implement custom validation in the entity class using data annotations and the method, by overriding the DbContext's SaveChanges method.

È possibile visualizzare un esempio di implementazione della convalida delle entità `IValidatableObject` in [questo commento in GitHub](https://github.com/dotnet/efcore/issues/3680#issuecomment-155502539). Questo esempio non esegue convalide basate su attributi, ma devono essere facili da implementare usando la reflection nello stesso override.

Tuttavia, da un punto di vista DDD, il modello di dominio è meglio mantenere snello con l'uso di eccezioni nei metodi di comportamento dell'entità o implementando i modelli di specifica e notifica per applicare le regole di convalida.

L'uso delle annotazioni dei dati a livello di applicazione nelle classi ViewModel, invece delle entità di dominio, che accetteranno l'input può risultare vantaggioso per consentire la convalida dei modelli entro il livello dell'interfaccia utente. Questo approccio tuttavia non deve escludere la convalida entro il modello di dominio.

### <a name="validate-entities-by-implementing-the-specification-pattern-and-the-notification-pattern"></a>Convalida di entità tramite l'implementazione dello schema Specification e dello schema Notification

Un approccio più complesso per l'implementazione delle convalide nel modello di dominio è infine costituito dall'implementazione dello schema Specification insieme allo schema Notification, come illustrato in alcune risorse aggiuntive elencate più avanti.

È importante notare che è possibile usare anche uno solo degli schemi, ad esempio eseguendo la convalida manualmente con le istruzioni di controllo, usando tuttavia lo schema Notification per creare uno stack e restituire un elenco di errori di convalida.

### <a name="use-deferred-validation-in-the-domain"></a>Usare la convalida posticipata nel dominio

Sono disponibili diversi approcci per la gestione delle convalide posticipate nel dominio. Nel suo manuale [Implementing Domain-Driven Design](https://www.amazon.com/Implementing-Domain-Driven-Design-Vaughn-Vernon/dp/0321834577) (Implementazione della progettazione basata su dominio) Vaughn Vernon illustra tali approcci nella sezione relativa alla convalida.

### <a name="two-step-validation"></a>Convalida in due passaggi

È possibile prendere in considerazione anche la convalida in due passaggi. Usare la convalida a livello di campo sugli oggetti di trasferimento dei dati del comando e la convalida a livello di dominio nelle entità. Per usare questo approccio è possibile restituire un oggetto risultato invece di eccezioni per semplificare la gestione degli errori di convalida.

L'uso della convalida dei campi con le annotazioni dei dati, ad esempio, consente di non duplicare la definizione della convalida. L'esecuzione tuttavia può essere lato server e lato client nel caso degli oggetti di trasferimento dei dati (comandi e ViewModels, ad esempio).

## <a name="additional-resources"></a>Risorse aggiuntive

- **Rachel Appel. Introduzione alla convalida del modello in ASP.NET Core MVCIntroduction to model validation in ASP.NET Core MVC** \
  <https://docs.microsoft.com/aspnet/core/mvc/models/validation>

- **Rick Anderson. Aggiunta della convalida** \
  <https://docs.microsoft.com/aspnet/core/tutorials/first-mvc-app/validation>

- **Martin Fowler. Sostituzione delle eccezioni di generazione con la notifica nelle convalideReplacing Throwing Exceptions with Notification in Validations** \
  <https://martinfowler.com/articles/replaceThrowWithNotification.html>

- **Specifiche e modelli di notifica** \
  <https://www.codeproject.com/Tips/790758/Specification-and-Notification-Patterns>

- **Lev Gorodinski. Convalida nella progettazione basata su dominio (DDD)Validation in Domain-Driven Design (DDD)** \
  <http://gorodinski.com/blog/2012/05/19/validation-in-domain-driven-design-ddd/>

- **Colin Jack. Convalida del modello di dominioDomain Model Validation** \
  <https://colinjack.blogspot.com/2008/03/domain-model-validation.html>

- **Jimmy Bogard. Convalida in un mondo DDD** \
  <https://lostechies.com/jimmybogard/2009/02/15/validation-in-a-ddd-world/>

> [!div class="step-by-step"]
> [Successivo](enumeration-classes-over-enum-types.md)
> [precedente](client-side-validation.md)

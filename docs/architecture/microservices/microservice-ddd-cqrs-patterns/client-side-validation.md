---
title: Convalida lato client (convalida nei livelli di presentazione)
description: Architettura di microservizi .NET per applicazioni .NET in contenitori | Panoramica dei concetti chiave delle convalide lato client.
ms.date: 10/08/2018
ms.openlocfilehash: 44c1e9fa280b19fcee87d4d1cdfcaa2ab9462f27
ms.sourcegitcommit: e3cbf26d67f7e9286c7108a2752804050762d02d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2020
ms.locfileid: "80988701"
---
# <a name="client-side-validation-validation-in-the-presentation-layers"></a>Convalida lato client (convalida nei livelli di presentazione)

Anche quando l'origine dati è il modello di dominio e occorre una convalida a livello del modello di dominio, è comunque possibile gestire la convalida sia a livello del modello di dominio (lato server) che a livello di interfaccia utente (lato client).

La convalida lato client è molto pratica per gli utenti. Consente infatti di ridurre i tempi di attesa di un round trip al server che potrebbe restituire errori di convalida. In termini di business, anche poche frazioni di secondo moltiplicate per centinaia di volte al giorno contribuiscono all'aumento di tempo, costi e frustrazione. Grazie a un processo di convalida semplice e immediato, gli utenti possono lavorare in modo più efficiente e garantire input e output di qualità elevata.

Così come il modello di visualizzazione e il modello di dominio sono diversi, la convalida del modello di visualizzazione e del modello di dominio possono essere simili ma hanno uno scopo diverso. Se sei preoccupato per DRY (il principio Don't Repeat Yourself), considera che in questo caso il riutilizzo del codice potrebbe anche significare l'accoppiamento, e nelle applicazioni aziendali è più importante non accoppiare il lato server al lato client piuttosto che seguire il principio DRY.

Quando si usa la convalida lato client, è necessario convalidare sempre i comandi o gli oggetti DTO di input nel codice del server, poiché le API del server rappresentano un possibile vettore di attacco. In genere, l'opzione migliore prevede di eseguirle entrambe, perché nel caso di un'applicazione client, dalla prospettiva dell'esperienza utente è consigliabile essere proattivi e non consentire all'utente di immettere informazioni non valide.

Di conseguenza, nel codice sul lato client vengono in genere convalidati gli oggetti ViewModel. È anche possibile convalidare i comandi o gli oggetti DTO di output del client prima di inviarli ai servizi.

L'implementazione della convalida del lato client dipende dalla tipologia di applicazione client che si sta creando. La scelta sarà diversa se si vogliono convalidare i dati in un'applicazione Web MVC con la maggior parte del codice in .NET, un'applicazione Web a pagina singola con la convalida scritta in JavaScript o TypeScript o un'applicazione per dispositivi mobili scritta in Xamarin e C#.

## <a name="additional-resources"></a>Risorse aggiuntive

### <a name="validation-in-xamarin-mobile-apps"></a>Convalida nelle app per dispositivi mobili in Xamarin

- **Convalida dell'input di testo e visualizzazione degli errori** \
  [https://developer.xamarin.com/recipes/ios/standard\_controls/text\_field/validate\_input/](https://developer.xamarin.com/recipes/ios/standard_controls/text_field/validate_input/)

- **Callback di convalidaValidation Callback** \
  <https://developer.xamarin.com/samples/xamarin-forms/XAML/ValidationCallback/>

### <a name="validation-in-aspnet-core-apps"></a>Convalida nelle app ASP.NET Core

- **Rick Anderson. Aggiunta della convalida** \
  <https://docs.microsoft.com/aspnet/core/tutorials/first-mvc-app/validation>

### <a name="validation-in-spa-web-apps-angular-2-typescript-javascript"></a>Convalida nelle app Web a pagina singola (Angular 2, TypeScript, JavaScript)

- **Ado Kukic. Convalida angolare 2 del modulo** \
  <https://scotch.io/tutorials/angular-2-form-validation>

- **Convalida modulo** \
  <https://angular.io/guide/form-validation>

- **Convalida.** Documentazione per Breeze. \
  <https://breeze.github.io/doc-js/validation.html>

In breve, questi sono i concetti più importanti in merito alla convalida:

- Le entità e le aggregazioni devono applicare la coerenza propria ed essere "sempre valide". Le radici di aggregazione sono responsabili della coerenza di più entità all'interno della stessa aggregazione.

- Se si pensa che un'entità debba passare a uno stato non valido, provare a usare un modello a oggetti diverso, ad esempio un oggetto DTO temporaneo fino a quando non viene creata l'entità del dominio finale.

- Se occorre creare numerosi oggetti correlati, ad esempio un'aggregazione, e questi sono validi solo quando tutti saranno stati creati, provare a usare lo schema Factory.

- Nella maggior parte dei client, è consigliabile adottare una convalida ridondante sul lato client, per aumentare la proattività dell'applicazione.

>[!div class="step-by-step"]
>[Successivo](domain-model-layer-validations.md)
>[precedente](domain-events-design-implementation.md)

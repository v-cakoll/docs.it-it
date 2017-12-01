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
# <a name="client-side-validation-validation-in-the-presentation-layers"></a>Convalida lato client (convalida dei livelli di presentazione)

Anche quando l'origine di dati reali è il modello di dominio e infine è necessario disporre convalida al livello del modello di dominio, convalida ancora può essere gestita a livello di modello di dominio (lato server) e il lato client.

La convalida lato client è una maggiore praticità per gli utenti. Consente di risparmiare tempo in caso contrario spendere in attesa di un round trip al server che potrebbero restituire gli errori di convalida. In termini di business, anche alcuni le frazioni di secondo moltiplicato centinaia di volte in cui ogni giorno vengono aggiunti a una grande quantità di tempo, expense e frustrazione. Convalida semplice e immediata consente agli utenti di lavorare in modo più efficiente e ottenere una migliore qualità di input e output.

Come il modello di visualizzazione e il modello di dominio sono diversi, la convalida del modello di visualizzazione e la convalida del modello di dominio potrebbe essere simile ma uno scopo diverso. Se si teme su sorgente (non ripetere manualmente principio), tenere presente che in questo caso il riutilizzo del codice potrebbe anche trattarsi di attacco, e in applicazioni aziendali è più importante per non associare lato server al lato client rispetto in base al principio secca.

Anche quando si utilizza la convalida lato client, è consigliabile sempre convalidare i comandi o di input DTO nel codice server, perché le API server rappresentano un vettore di attacco. In genere, ciò infatti il modo migliore se si dispone di un'applicazione client, dal punto di vista dell'esperienza utente, è consigliabile essere attiva e non consentire all'utente di immettere informazioni non valide.

Pertanto, nel codice sul lato client è in genere convalidare il ViewModel. È inoltre possibile convalidare il client invia l'output DTO o comandi prima di inviarli ai servizi.

L'implementazione della convalida lato client dipende dal tipo di applicazione client si sta compilando. Sarà diverso se si esegue la convalida dei dati in un'applicazione web MVC web con la maggior parte del codice in .NET, un'applicazione web SPA con tale convalida codificata in JavaScript o TypeScript, o un'app mobile codificati con Xamarin e C\#.

## <a name="additional-resources"></a>Risorse aggiuntive

### <a name="validation-in-xamarin-mobile-apps"></a>Convalida Xamarin App per dispositivi mobili

-   **Convalidare l'Input di testo e Visualizza errori**
    [*https://developer.xamarin.com/recipes/ios/standard\_testo o controlli\_campo/convalidare\_input /*](https://developer.xamarin.com/recipes/ios/standard_controls/text_field/validate_input/)

-   **Callback di convalida**
    [*https://developer.xamarin.com/samples/xamarin-forms/XAML/ValidationCallback/*](https://developer.xamarin.com/samples/xamarin-forms/XAML/ValidationCallback/)

### <a name="validation-in-aspnet-core-apps"></a>Convalida nelle applicazioni ASP.NET Core

-   **Rick Anderson. Aggiunta della convalida**
    [*https://docs.microsoft.com/aspnet/core/tutorials/first-mvc-app/validation*](https://docs.microsoft.com/aspnet/core/tutorials/first-mvc-app/validation)

### <a name="validation-in-spa-web-apps-angular-2-typescript-javascript"></a>Convalida in SPA Web App (angolare 2, macchina, JavaScript)

-   **Kukic ADO. Convalida modulo 2 angolare** **
     ** [ *https://scotch.io/tutorials/angular-2-form-validation*](https://scotch.io/tutorials/angular-2-form-validation)

-   **Modulo di convalida**
    [*https://angular.io/docs/ts/latest/cookbook/form-validation.html*](https://angular.io/docs/ts/latest/cookbook/form-validation.html)

-   **Convalida.** Documentazione molto semplice.
    [*http://Breeze.github.IO/doc-js/Validation.HTML*](http://breeze.github.io/doc-js/validation.html)

In sintesi, ecco i concetti più importanti relativamente alla convalida:

-   Entità e funzioni di aggregazione deve applicare le proprie coerenza e "sempre valido". Radici di aggregazione sono responsabili per la coerenza di più entità all'interno dell'aggregazione stesso.

-   Se si ritiene che un'entità deve entri in uno stato non valido, è consigliabile utilizzare un modello a oggetti diversi, ad esempio, usando un DTO temporanea fino a creare l'entità finale di dominio.

-   Se è necessario creare diversi oggetti correlati, ad esempio un'aggregazione, e sono validi solo dopo avere creati tutti gli elementi, utilizzare il modello di Factory.

-   Framework di convalida vengono utilizzate in livelli specifici, ad esempio il livello di presentazione o il livello di servizio / dell'applicazione, ma in genere non nel livello del modello di dominio, in quanto è necessario accettare una dipendenza sicura su un framework di infrastruttura.

-   Nella maggior parte dei casi, con la convalida ridondante sul lato client è valida, poiché l'applicazione può essere attiva.


>[!div class="step-by-step"]
[Precedente] (dominio-modello-layer-validations.md) [Avanti] (dominio eventi-progettazione implementation.md)

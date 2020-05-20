---
title: Flag di funzionalità
description: Implementare i flag delle funzionalità nelle applicazioni native del cloud sfruttando app Azure config
author: robvet
ms.date: 05/13/2020
ms.openlocfilehash: 607bd14a415a25b382f550e697542cf749a21772
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614071"
---
# <a name="feature-flags"></a>Flag di funzionalità

Nel capitolo 1 si è affermato che cloud native è molto di più di velocità e agilità. Gli utenti si aspettano velocità di risposta rapida, funzionalità innovative e nessun tempo di inattività. `Feature flags`sono una tecnica di distribuzione moderna che consente di aumentare l'agilità per le applicazioni native del cloud. Consentono di distribuire nuove funzionalità in un ambiente di produzione, ma limitarne la disponibilità. Con il gesto rapido di un'opzione, è possibile attivare una nuova funzionalità per utenti specifici senza riavviare l'app o distribuire nuovo codice. Separano il rilascio di nuove funzionalità dalla distribuzione del codice.

I flag di funzionalità sono basati sulla logica condizionale che controlla la visibilità delle funzionalità per gli utenti in fase di esecuzione. Nei moderni sistemi nativi del cloud, è comune distribuire le nuove funzionalità in produzione in anticipo, ma testarle con un numero limitato di destinatari. Con l'aumentare della confidenza, la funzionalità può essere implementata in modo incrementale in gruppi di destinatari più ampi.

Altri casi d'uso per i flag di funzionalità includono:

- Limita le funzionalità Premium a gruppi di clienti specifici disposti a pagare più tariffe di sottoscrizione.
- Stabilizzare un sistema disattivando rapidamente una funzionalità di problema, evitando i rischi di un rollback o di un hotfix immediato.
- Disabilitare una funzionalità facoltativa con un consumo di risorse elevato durante i periodi di utilizzo massimo.
- Condurre `experimental feature releases` a segmenti di utenti piccoli per convalidare la fattibilità e la popolarità.

I flag funzionalità favoriscono anche `trunk-based` lo sviluppo. Si tratta di un modello di diramazione del controllo del codice sorgente in cui gli sviluppatori collaborano con le funzionalità in un singolo Branch. L'approccio consente di ridurre al minimo il rischio e la complessità di unire un numero elevato di rami di funzionalità con esecuzione prolungata. Le funzionalità non sono disponibili finché non vengono attivate.

## <a name="implementing-feature-flags"></a>Implementazione di flag funzionalità

Al suo nucleo, un flag di funzionalità è un riferimento a un semplice `decision object` . Restituisce uno stato booleano di `on` o `off` . Il flag esegue in genere il wrapping di un blocco di codice che incapsula una funzionalità della funzionalità. Lo stato del flag determina se il blocco di codice viene eseguito per un determinato utente. La figura 10-11 illustra l'implementazione.

```c#
if (featureFlag) {
    // Run this code block if the featureFlag value is true
} else {
    // Run this code block if the featureFlag value is false
}
```

**Figura 10-11** -implementazione del flag di funzionalità semplice.

Si noti che questo approccio separa la logica decisionale dal codice della funzionalità.

Nel capitolo 1 è stato illustrato il `Twelve-Factor App` . Le linee guida consigliate per mantenere le impostazioni di configurazione esterne dal codice eseguibile dell'applicazione. Quando necessario, le impostazioni possono essere lette dall'origine esterna. I valori di configurazione dei flag funzionalità devono inoltre essere indipendenti dalla relativa codebase. Con la configurazione del flag l'esternalizzazione in un repository separato, è possibile modificare lo stato del flag senza modificare e ridistribuire l'applicazione.

[App Azure configurazione](https://docs.microsoft.com/azure/azure-app-configuration/overview) fornisce un repository centralizzato per i flag funzionalità. Con esso, è possibile definire diversi tipi di flag di funzionalità e modificare i relativi stati in modo rapido e sicuro. È possibile aggiungere le librerie client di configurazione dell'app all'applicazione per abilitare la funzionalità dei flag funzionalità. Sono supportati diversi framework del linguaggio di programmazione.

I flag funzionalità possono essere implementati facilmente in un [servizio ASP.NET Core](https://docs.microsoft.com/azure/azure-app-configuration/use-feature-flags-dotnet-core). L'installazione delle librerie di gestione delle funzionalità .NET e del provider di configurazione delle app consente di aggiungere in modo dichiarativo i flag funzionalità al codice. Abilitano `FeatureGate` gli attributi in modo che non sia necessario scrivere manualmente istruzioni If nella codebase.

Una volta configurata nella classe di avvio, è possibile aggiungere funzionalità per i flag di funzionalità a livello di controller, azione o middleware. La figura 10-12 presenta l'implementazione del controller e dell'azione:

```c#
[FeatureGate(MyFeatureFlags.FeatureA)]
public class ProductController : Controller
{
    ...
}
```

```c#
[FeatureGate(MyFeatureFlags.FeatureA)]
public IActionResult UpdateProductStatus()
{
    return ObjectResult(ProductDto);
}
```

**Figura 10-12** : implementazione del flag di funzionalità in un controller e in un'azione.

Se un flag di funzionalità è disabilitato, l'utente riceverà un codice di stato 404 (non trovato) senza corpo della risposta.

I flag di funzionalità possono anche essere inseriti direttamente nelle classi C#. La figura 10-13 Mostra l'inserimento del flag funzionalità:

```c#
public class ProductController : Controller
{
    private readonly IFeatureManager _featureManager;

    public ProductController(IFeatureManager featureManager)
    {
        _featureManager = featureManager;
    }
}
```

**Figura 10-13** -inserimento di flag di funzionalità in una classe.

Le librerie di gestione delle funzionalità gestiscono il ciclo di vita dei flag funzionalità dietro le quinte. Ad esempio, per ridurre al minimo un numero elevato di chiamate all'archivio di configurazione, lo stato del flag della cache delle librerie è per una durata specificata. Possono garantire l'immutabilità degli Stati dei flag durante una chiamata di richiesta. Offrono anche un `Point-in-time snapshot` . È possibile ricostruire la cronologia di qualsiasi valore chiave e fornire il relativo valore passato in qualsiasi momento nei sette giorni precedenti.

>[!div class="step-by-step"]
>[Precedente](devops.md) 
> [Avanti](infrastructure-as-code.md)

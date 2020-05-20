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
# <a name="feature-flags"></a><span data-ttu-id="c04ba-103">Flag di funzionalità</span><span class="sxs-lookup"><span data-stu-id="c04ba-103">Feature flags</span></span>

<span data-ttu-id="c04ba-104">Nel capitolo 1 si è affermato che cloud native è molto di più di velocità e agilità.</span><span class="sxs-lookup"><span data-stu-id="c04ba-104">In chapter 1, we affirmed that cloud native is much about speed and agility.</span></span> <span data-ttu-id="c04ba-105">Gli utenti si aspettano velocità di risposta rapida, funzionalità innovative e nessun tempo di inattività.</span><span class="sxs-lookup"><span data-stu-id="c04ba-105">Users expect rapid responsiveness, innovative features, and zero downtime.</span></span> <span data-ttu-id="c04ba-106">`Feature flags`sono una tecnica di distribuzione moderna che consente di aumentare l'agilità per le applicazioni native del cloud.</span><span class="sxs-lookup"><span data-stu-id="c04ba-106">`Feature flags` are a modern deployment technique that helps increase agility for cloud-native applications.</span></span> <span data-ttu-id="c04ba-107">Consentono di distribuire nuove funzionalità in un ambiente di produzione, ma limitarne la disponibilità.</span><span class="sxs-lookup"><span data-stu-id="c04ba-107">They enable you to deploy new features into a production environment, but restrict their availability.</span></span> <span data-ttu-id="c04ba-108">Con il gesto rapido di un'opzione, è possibile attivare una nuova funzionalità per utenti specifici senza riavviare l'app o distribuire nuovo codice.</span><span class="sxs-lookup"><span data-stu-id="c04ba-108">With the flick of a switch, you can activate a new feature for specific users without restarting the app or deploying new code.</span></span> <span data-ttu-id="c04ba-109">Separano il rilascio di nuove funzionalità dalla distribuzione del codice.</span><span class="sxs-lookup"><span data-stu-id="c04ba-109">They separate the release of new features from their code deployment.</span></span>

<span data-ttu-id="c04ba-110">I flag di funzionalità sono basati sulla logica condizionale che controlla la visibilità delle funzionalità per gli utenti in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="c04ba-110">Feature flags are built upon conditional logic that control visibility of functionality for users at runtime.</span></span> <span data-ttu-id="c04ba-111">Nei moderni sistemi nativi del cloud, è comune distribuire le nuove funzionalità in produzione in anticipo, ma testarle con un numero limitato di destinatari.</span><span class="sxs-lookup"><span data-stu-id="c04ba-111">In modern cloud-native systems, it's common to deploy new features into production early, but test them with a limited audience.</span></span> <span data-ttu-id="c04ba-112">Con l'aumentare della confidenza, la funzionalità può essere implementata in modo incrementale in gruppi di destinatari più ampi.</span><span class="sxs-lookup"><span data-stu-id="c04ba-112">As confidence increases, the feature can be incrementally rolled out to wider audiences.</span></span>

<span data-ttu-id="c04ba-113">Altri casi d'uso per i flag di funzionalità includono:</span><span class="sxs-lookup"><span data-stu-id="c04ba-113">Other use cases for feature flags include:</span></span>

- <span data-ttu-id="c04ba-114">Limita le funzionalità Premium a gruppi di clienti specifici disposti a pagare più tariffe di sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="c04ba-114">Restrict premium functionality to specific customer groups willing to pay higher subscription fees.</span></span>
- <span data-ttu-id="c04ba-115">Stabilizzare un sistema disattivando rapidamente una funzionalità di problema, evitando i rischi di un rollback o di un hotfix immediato.</span><span class="sxs-lookup"><span data-stu-id="c04ba-115">Stabilize a system by quickly deactivating a problem feature, avoiding the risks of a rollback or immediate hotfix.</span></span>
- <span data-ttu-id="c04ba-116">Disabilitare una funzionalità facoltativa con un consumo di risorse elevato durante i periodi di utilizzo massimo.</span><span class="sxs-lookup"><span data-stu-id="c04ba-116">Disable an optional feature with high resource consumption during peak usage periods.</span></span>
- <span data-ttu-id="c04ba-117">Condurre `experimental feature releases` a segmenti di utenti piccoli per convalidare la fattibilità e la popolarità.</span><span class="sxs-lookup"><span data-stu-id="c04ba-117">Conduct `experimental feature releases` to small user segments to validate feasibility and popularity.</span></span>

<span data-ttu-id="c04ba-118">I flag funzionalità favoriscono anche `trunk-based` lo sviluppo.</span><span class="sxs-lookup"><span data-stu-id="c04ba-118">Feature flags also promote `trunk-based` development.</span></span> <span data-ttu-id="c04ba-119">Si tratta di un modello di diramazione del controllo del codice sorgente in cui gli sviluppatori collaborano con le funzionalità in un singolo Branch.</span><span class="sxs-lookup"><span data-stu-id="c04ba-119">It's a source-control branching model where developers collaborate on features in a single branch.</span></span> <span data-ttu-id="c04ba-120">L'approccio consente di ridurre al minimo il rischio e la complessità di unire un numero elevato di rami di funzionalità con esecuzione prolungata.</span><span class="sxs-lookup"><span data-stu-id="c04ba-120">The approach minimizes the risk and complexity of merging large numbers of long-running feature branches.</span></span> <span data-ttu-id="c04ba-121">Le funzionalità non sono disponibili finché non vengono attivate.</span><span class="sxs-lookup"><span data-stu-id="c04ba-121">Features are unavailable until activated.</span></span>

## <a name="implementing-feature-flags"></a><span data-ttu-id="c04ba-122">Implementazione di flag funzionalità</span><span class="sxs-lookup"><span data-stu-id="c04ba-122">Implementing feature flags</span></span>

<span data-ttu-id="c04ba-123">Al suo nucleo, un flag di funzionalità è un riferimento a un semplice `decision object` .</span><span class="sxs-lookup"><span data-stu-id="c04ba-123">At its core, a feature flag is a reference to a simple `decision object`.</span></span> <span data-ttu-id="c04ba-124">Restituisce uno stato booleano di `on` o `off` .</span><span class="sxs-lookup"><span data-stu-id="c04ba-124">It returns a Boolean state of `on` or `off`.</span></span> <span data-ttu-id="c04ba-125">Il flag esegue in genere il wrapping di un blocco di codice che incapsula una funzionalità della funzionalità.</span><span class="sxs-lookup"><span data-stu-id="c04ba-125">The flag typically wraps a block of code that encapsulates a feature capability.</span></span> <span data-ttu-id="c04ba-126">Lo stato del flag determina se il blocco di codice viene eseguito per un determinato utente.</span><span class="sxs-lookup"><span data-stu-id="c04ba-126">The state of the flag determines whether that code block executes for a given user.</span></span> <span data-ttu-id="c04ba-127">La figura 10-11 illustra l'implementazione.</span><span class="sxs-lookup"><span data-stu-id="c04ba-127">Figure 10-11 shows the implementation.</span></span>

```c#
if (featureFlag) {
    // Run this code block if the featureFlag value is true
} else {
    // Run this code block if the featureFlag value is false
}
```

<span data-ttu-id="c04ba-128">**Figura 10-11** -implementazione del flag di funzionalità semplice.</span><span class="sxs-lookup"><span data-stu-id="c04ba-128">**Figure 10-11** - Simple feature flag implementation.</span></span>

<span data-ttu-id="c04ba-129">Si noti che questo approccio separa la logica decisionale dal codice della funzionalità.</span><span class="sxs-lookup"><span data-stu-id="c04ba-129">Note how this approach separates the decision logic from the feature code.</span></span>

<span data-ttu-id="c04ba-130">Nel capitolo 1 è stato illustrato il `Twelve-Factor App` .</span><span class="sxs-lookup"><span data-stu-id="c04ba-130">In chapter 1, we discussed the `Twelve-Factor App`.</span></span> <span data-ttu-id="c04ba-131">Le linee guida consigliate per mantenere le impostazioni di configurazione esterne dal codice eseguibile dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="c04ba-131">The guidance recommended keeping configuration settings external from application executable code.</span></span> <span data-ttu-id="c04ba-132">Quando necessario, le impostazioni possono essere lette dall'origine esterna.</span><span class="sxs-lookup"><span data-stu-id="c04ba-132">When needed, settings can be read in from the external source.</span></span> <span data-ttu-id="c04ba-133">I valori di configurazione dei flag funzionalità devono inoltre essere indipendenti dalla relativa codebase.</span><span class="sxs-lookup"><span data-stu-id="c04ba-133">Feature flag configuration values should also be independent from their codebase.</span></span> <span data-ttu-id="c04ba-134">Con la configurazione del flag l'esternalizzazione in un repository separato, è possibile modificare lo stato del flag senza modificare e ridistribuire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="c04ba-134">By externalizing flag configuration in a separate repository, you can change flag state without modifying and redeploying the application.</span></span>

<span data-ttu-id="c04ba-135">[App Azure configurazione](https://docs.microsoft.com/azure/azure-app-configuration/overview) fornisce un repository centralizzato per i flag funzionalità.</span><span class="sxs-lookup"><span data-stu-id="c04ba-135">[Azure App Configuration](https://docs.microsoft.com/azure/azure-app-configuration/overview) provides a centralized repository for feature flags.</span></span> <span data-ttu-id="c04ba-136">Con esso, è possibile definire diversi tipi di flag di funzionalità e modificare i relativi stati in modo rapido e sicuro.</span><span class="sxs-lookup"><span data-stu-id="c04ba-136">With it, you define different kinds of feature flags and manipulate their states quickly and confidently.</span></span> <span data-ttu-id="c04ba-137">È possibile aggiungere le librerie client di configurazione dell'app all'applicazione per abilitare la funzionalità dei flag funzionalità.</span><span class="sxs-lookup"><span data-stu-id="c04ba-137">You add the App Configuration client libraries to your application to enable feature flag functionality.</span></span> <span data-ttu-id="c04ba-138">Sono supportati diversi framework del linguaggio di programmazione.</span><span class="sxs-lookup"><span data-stu-id="c04ba-138">Various programming language frameworks are supported.</span></span>

<span data-ttu-id="c04ba-139">I flag funzionalità possono essere implementati facilmente in un [servizio ASP.NET Core](https://docs.microsoft.com/azure/azure-app-configuration/use-feature-flags-dotnet-core).</span><span class="sxs-lookup"><span data-stu-id="c04ba-139">Feature flags can be easily implemented in an [ASP.NET Core service](https://docs.microsoft.com/azure/azure-app-configuration/use-feature-flags-dotnet-core).</span></span> <span data-ttu-id="c04ba-140">L'installazione delle librerie di gestione delle funzionalità .NET e del provider di configurazione delle app consente di aggiungere in modo dichiarativo i flag funzionalità al codice.</span><span class="sxs-lookup"><span data-stu-id="c04ba-140">Installing the .NET Feature Management libraries and App Configuration provider enable you to declaratively add feature flags to your code.</span></span> <span data-ttu-id="c04ba-141">Abilitano `FeatureGate` gli attributi in modo che non sia necessario scrivere manualmente istruzioni If nella codebase.</span><span class="sxs-lookup"><span data-stu-id="c04ba-141">They enable `FeatureGate` attributes so that you don't have to manually write if statements across your codebase.</span></span>

<span data-ttu-id="c04ba-142">Una volta configurata nella classe di avvio, è possibile aggiungere funzionalità per i flag di funzionalità a livello di controller, azione o middleware.</span><span class="sxs-lookup"><span data-stu-id="c04ba-142">Once configured in your Startup class, you can add feature flag functionality at the controller, action, or middleware level.</span></span> <span data-ttu-id="c04ba-143">La figura 10-12 presenta l'implementazione del controller e dell'azione:</span><span class="sxs-lookup"><span data-stu-id="c04ba-143">Figure 10-12 presents controller and action implementation:</span></span>

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

<span data-ttu-id="c04ba-144">**Figura 10-12** : implementazione del flag di funzionalità in un controller e in un'azione.</span><span class="sxs-lookup"><span data-stu-id="c04ba-144">**Figure 10-12** - Feature flag implementation in a controller and action.</span></span>

<span data-ttu-id="c04ba-145">Se un flag di funzionalità è disabilitato, l'utente riceverà un codice di stato 404 (non trovato) senza corpo della risposta.</span><span class="sxs-lookup"><span data-stu-id="c04ba-145">If a feature flag is disabled, the user will receive a 404 (Not Found) status code with no response body.</span></span>

<span data-ttu-id="c04ba-146">I flag di funzionalità possono anche essere inseriti direttamente nelle classi C#.</span><span class="sxs-lookup"><span data-stu-id="c04ba-146">Feature flags can also be injected directly into C# classes.</span></span> <span data-ttu-id="c04ba-147">La figura 10-13 Mostra l'inserimento del flag funzionalità:</span><span class="sxs-lookup"><span data-stu-id="c04ba-147">Figure 10-13 shows feature flag injection:</span></span>

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

<span data-ttu-id="c04ba-148">**Figura 10-13** -inserimento di flag di funzionalità in una classe.</span><span class="sxs-lookup"><span data-stu-id="c04ba-148">**Figure 10-13** - Feature flag injection into a class.</span></span>

<span data-ttu-id="c04ba-149">Le librerie di gestione delle funzionalità gestiscono il ciclo di vita dei flag funzionalità dietro le quinte.</span><span class="sxs-lookup"><span data-stu-id="c04ba-149">The Feature Management libraries manage the feature flag lifecycle behind the scenes.</span></span> <span data-ttu-id="c04ba-150">Ad esempio, per ridurre al minimo un numero elevato di chiamate all'archivio di configurazione, lo stato del flag della cache delle librerie è per una durata specificata.</span><span class="sxs-lookup"><span data-stu-id="c04ba-150">For example, to minimize high numbers of calls to the configuration store, the libraries cache flag states for a specified duration.</span></span> <span data-ttu-id="c04ba-151">Possono garantire l'immutabilità degli Stati dei flag durante una chiamata di richiesta.</span><span class="sxs-lookup"><span data-stu-id="c04ba-151">They can guarantee the immutability of flag states during a request call.</span></span> <span data-ttu-id="c04ba-152">Offrono anche un `Point-in-time snapshot` .</span><span class="sxs-lookup"><span data-stu-id="c04ba-152">They also offer a `Point-in-time snapshot`.</span></span> <span data-ttu-id="c04ba-153">È possibile ricostruire la cronologia di qualsiasi valore chiave e fornire il relativo valore passato in qualsiasi momento nei sette giorni precedenti.</span><span class="sxs-lookup"><span data-stu-id="c04ba-153">You can reconstruct the history of any key-value and provide its past value at any moment within the previous seven days.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="c04ba-154">[Precedente](devops.md) 
> [Avanti](infrastructure-as-code.md)</span><span class="sxs-lookup"><span data-stu-id="c04ba-154">[Previous](devops.md)
[Next](infrastructure-as-code.md)</span></span>

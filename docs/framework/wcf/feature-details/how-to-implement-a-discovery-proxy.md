---
title: 'Procedura: implementare un proxy di individuazione'
ms.date: 03/30/2017
ms.assetid: 78d70e0a-f6c3-4cfb-a7ca-f66ebddadde0
ms.openlocfilehash: ca7ab2ee434aef7649d71cbfc33273f48020788f
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84597072"
---
# <a name="how-to-implement-a-discovery-proxy"></a><span data-ttu-id="9a0a9-102">Procedura: implementare un proxy di individuazione</span><span class="sxs-lookup"><span data-stu-id="9a0a9-102">How to: Implement a Discovery Proxy</span></span>

<span data-ttu-id="9a0a9-103">In questo argomento viene illustrato come implementare un proxy di individuazione.</span><span class="sxs-lookup"><span data-stu-id="9a0a9-103">This topic explains how to implement a discovery proxy.</span></span> <span data-ttu-id="9a0a9-104">Per ulteriori informazioni sulla funzionalità di individuazione in Windows Communication Foundation (WCF), vedere [WCF Discovery Overview](wcf-discovery-overview.md).</span><span class="sxs-lookup"><span data-stu-id="9a0a9-104">For more information about the discovery feature in Windows Communication Foundation (WCF), see [WCF Discovery Overview](wcf-discovery-overview.md).</span></span> <span data-ttu-id="9a0a9-105">È possibile implementare un proxy di individuazione creando una classe che estende la classe astratta <xref:System.ServiceModel.Discovery.DiscoveryProxy>.</span><span class="sxs-lookup"><span data-stu-id="9a0a9-105">A discovery proxy can be implemented by creating a class that extends the <xref:System.ServiceModel.Discovery.DiscoveryProxy> abstract class.</span></span> <span data-ttu-id="9a0a9-106">In questo esempio vengono definite e utilizzate altre classi di supporto.</span><span class="sxs-lookup"><span data-stu-id="9a0a9-106">There are a number of other support classes defined and used in this sample.</span></span> <span data-ttu-id="9a0a9-107">`OnResolveAsyncResult`, `OnFindAsyncResult`e `AsyncResult`.</span><span class="sxs-lookup"><span data-stu-id="9a0a9-107">`OnResolveAsyncResult`, `OnFindAsyncResult`, and `AsyncResult`.</span></span> <span data-ttu-id="9a0a9-108">Queste classi implementano l'interfaccia <xref:System.IAsyncResult>.</span><span class="sxs-lookup"><span data-stu-id="9a0a9-108">These classes implement the <xref:System.IAsyncResult> interface.</span></span> <span data-ttu-id="9a0a9-109">Per ulteriori informazioni su <xref:System.IAsyncResult> , vedere [interfaccia System. IAsyncResult](xref:System.IAsyncResult).</span><span class="sxs-lookup"><span data-stu-id="9a0a9-109">For more information about <xref:System.IAsyncResult> see [System.IAsyncResult interface](xref:System.IAsyncResult).</span></span>

 <span data-ttu-id="9a0a9-110">In questo argomento l'implementazione di un proxy di individuazione è articolata in tre fasi principali:</span><span class="sxs-lookup"><span data-stu-id="9a0a9-110">Implementing a discovery proxy is broken down into three main parts in this topic:</span></span>

- <span data-ttu-id="9a0a9-111">Definire una classe che contiene un archivio dati ed estende la classe astratta <xref:System.ServiceModel.Discovery.DiscoveryProxy>.</span><span class="sxs-lookup"><span data-stu-id="9a0a9-111">Define a class that contains a data store and extends the abstract <xref:System.ServiceModel.Discovery.DiscoveryProxy> class.</span></span>

- <span data-ttu-id="9a0a9-112">Implementare la classe di supporto `AsyncResult`.</span><span class="sxs-lookup"><span data-stu-id="9a0a9-112">Implement the helper `AsyncResult` class.</span></span>

- <span data-ttu-id="9a0a9-113">Ospitare il proxy di individuazione.</span><span class="sxs-lookup"><span data-stu-id="9a0a9-113">Host the Discovery Proxy.</span></span>

### <a name="to-create-a-new-console-application-project"></a><span data-ttu-id="9a0a9-114">Per creare un nuovo progetto di applicazione console</span><span class="sxs-lookup"><span data-stu-id="9a0a9-114">To create a new console application project</span></span>

1. <span data-ttu-id="9a0a9-115">Avviare Visual Studio 2012.</span><span class="sxs-lookup"><span data-stu-id="9a0a9-115">Start Visual Studio 2012.</span></span>

2. <span data-ttu-id="9a0a9-116">Creare un nuovo progetto di applicazione console.</span><span class="sxs-lookup"><span data-stu-id="9a0a9-116">Create a new console application project.</span></span> <span data-ttu-id="9a0a9-117">Assegnare al progetto il nome `DiscoveryProxy` e assegnare alla soluzione il nome `DiscoveryProxyExample`.</span><span class="sxs-lookup"><span data-stu-id="9a0a9-117">Name the project `DiscoveryProxy` and the name the solution `DiscoveryProxyExample`.</span></span>

3. <span data-ttu-id="9a0a9-118">Aggiungere al progetto i riferimenti seguenti</span><span class="sxs-lookup"><span data-stu-id="9a0a9-118">Add the following references to the project</span></span>

    1. <span data-ttu-id="9a0a9-119">System.ServiceModel.dll</span><span class="sxs-lookup"><span data-stu-id="9a0a9-119">System.ServiceModel.dll</span></span>

    2. <span data-ttu-id="9a0a9-120">System.Servicemodel.Discovery.dll</span><span class="sxs-lookup"><span data-stu-id="9a0a9-120">System.Servicemodel.Discovery.dll</span></span>

    > [!CAUTION]
    > <span data-ttu-id="9a0a9-121">Accertarsi di fare riferimento alla versione 4.0 o successiva di questi assembly.</span><span class="sxs-lookup"><span data-stu-id="9a0a9-121">Ensure that you reference version 4.0 or greater of these assemblies.</span></span>

### <a name="to-implement-the-proxydiscoveryservice-class"></a><span data-ttu-id="9a0a9-122">Per implementare la classe ProxyDiscoveryService</span><span class="sxs-lookup"><span data-stu-id="9a0a9-122">To implement the ProxyDiscoveryService class</span></span>

1. <span data-ttu-id="9a0a9-123">Aggiungere un nuovo file di codice al progetto e denominarlo DiscoveryProxy.cs.</span><span class="sxs-lookup"><span data-stu-id="9a0a9-123">Add a new code file to your project and name it DiscoveryProxy.cs.</span></span>

2. <span data-ttu-id="9a0a9-124">Aggiungere le istruzioni `using` seguenti a DiscoveryProxy.cs.</span><span class="sxs-lookup"><span data-stu-id="9a0a9-124">Add the following `using` statements to DiscoveryProxy.cs.</span></span>

    ```csharp
    using System;
    using System.Collections.Generic;
    using System.ServiceModel;
    using System.ServiceModel.Discovery;
    using System.Xml;
    ```

3. <span data-ttu-id="9a0a9-125">Derivare `DiscoveryProxyService` da <xref:System.ServiceModel.Discovery.DiscoveryProxy>.</span><span class="sxs-lookup"><span data-stu-id="9a0a9-125">Derive the `DiscoveryProxyService` from <xref:System.ServiceModel.Discovery.DiscoveryProxy>.</span></span> <span data-ttu-id="9a0a9-126">Applicare l'attributo `ServiceBehavior` alla classe, come illustrato nell'esempio riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="9a0a9-126">Apply the `ServiceBehavior` attribute to the class as shown in the following example.</span></span>

    ```csharp
    // Implement DiscoveryProxy by extending the DiscoveryProxy class and overriding the abstract methods
    [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single, ConcurrencyMode = ConcurrencyMode.Multiple)]
    public class DiscoveryProxyService : DiscoveryProxy
    {
    }
    ```

4. <span data-ttu-id="9a0a9-127">Nella classe `DiscoveryProxy` definire un dizionario per conservare i servizi registrati.</span><span class="sxs-lookup"><span data-stu-id="9a0a9-127">Inside the `DiscoveryProxy` class define a dictionary to hold the registered services.</span></span>

    ```csharp
    // Repository to store EndpointDiscoveryMetadata.
    Dictionary<EndpointAddress, EndpointDiscoveryMetadata> onlineServices;
    ```

5. <span data-ttu-id="9a0a9-128">Definire un costruttore che inizializza il dizionario.</span><span class="sxs-lookup"><span data-stu-id="9a0a9-128">Define a constructor that initializes the dictionary.</span></span>

    ```csharp
    public DiscoveryProxyService()
            {
                this.onlineServices = new Dictionary<EndpointAddress, EndpointDiscoveryMetadata>();
            }
    ```

### <a name="to-define-the-methods-used-to-update-the-discovery-proxy-cache"></a><span data-ttu-id="9a0a9-129">Per definire i metodi utilizzati per aggiornare la cache del proxy di individuazione</span><span class="sxs-lookup"><span data-stu-id="9a0a9-129">To define the methods used to update the discovery proxy cache</span></span>

1. <span data-ttu-id="9a0a9-130">Implementare il metodo `AddOnlineservice` per aggiungere servizi alla cache.</span><span class="sxs-lookup"><span data-stu-id="9a0a9-130">Implement the `AddOnlineservice` method to add services to the cache.</span></span> <span data-ttu-id="9a0a9-131">Questo metodo viene chiamato ogni volta che il proxy riceve un messaggio di annuncio.</span><span class="sxs-lookup"><span data-stu-id="9a0a9-131">This is called every time the proxy receives an announcement message.</span></span>

    ```csharp
    void AddOnlineService(EndpointDiscoveryMetadata endpointDiscoveryMetadata)
    {
        lock (this.onlineServices)
        {
            this.onlineServices[endpointDiscoveryMetadata.Address] = endpointDiscoveryMetadata;
        }

        PrintDiscoveryMetadata(endpointDiscoveryMetadata, "Adding");
    }
    ```

2. <span data-ttu-id="9a0a9-132">Implementare il metodo `RemoveOnlineService` utilizzato per rimuovere servizi dalla cache.</span><span class="sxs-lookup"><span data-stu-id="9a0a9-132">Implement the `RemoveOnlineService` method that is used to remove services from the cache.</span></span>

    ```csharp
    void RemoveOnlineService(EndpointDiscoveryMetadata endpointDiscoveryMetadata)
    {
        if (endpointDiscoveryMetadata != null)
        {
            lock (this.onlineServices)
            {
                this.onlineServices.Remove(endpointDiscoveryMetadata.Address);
            }

            PrintDiscoveryMetadata(endpointDiscoveryMetadata, "Removing");
        }
    }
    ```

3. <span data-ttu-id="9a0a9-133">Implementare i metodi `MatchFromOnlineService`, che tentano di individuare una corrispondenza tra un servizio e un servizio nel dizionario.</span><span class="sxs-lookup"><span data-stu-id="9a0a9-133">Implement the `MatchFromOnlineService` methods that attempt to match a service with a service in the dictionary.</span></span>

    ```csharp
    void MatchFromOnlineService(FindRequestContext findRequestContext)
    {
        lock (this.onlineServices)
        {
            foreach (EndpointDiscoveryMetadata endpointDiscoveryMetadata in this.onlineServices.Values)
            {
                if (findRequestContext.Criteria.IsMatch(endpointDiscoveryMetadata))
                {
                    findRequestContext.AddMatchingEndpoint(endpointDiscoveryMetadata);
                }
            }
        }
    }
    ```

    ```csharp
    EndpointDiscoveryMetadata MatchFromOnlineService(ResolveCriteria criteria)
    {
        EndpointDiscoveryMetadata matchingEndpoint = null;
        lock (this.onlineServices)
        {
            foreach (EndpointDiscoveryMetadata endpointDiscoveryMetadata in this.onlineServices.Values)
            {
                if (criteria.Address == endpointDiscoveryMetadata.Address)
                {
                    matchingEndpoint = endpointDiscoveryMetadata;
                }
            }
        }
        return matchingEndpoint;
    }
    ```

4. <span data-ttu-id="9a0a9-134">Implementare il metodo `PrintDiscoveryMetadata`, che fornisce all'utente l'output di testo della console indicante le operazioni eseguite dal proxy di individuazione.</span><span class="sxs-lookup"><span data-stu-id="9a0a9-134">Implement the `PrintDiscoveryMetadata` method that provides the user with console text output of what the discovery proxy is doing.</span></span>

    ```csharp
    void PrintDiscoveryMetadata(EndpointDiscoveryMetadata endpointDiscoveryMetadata, string verb)
    {
        Console.WriteLine("\n**** " + verb + " service of the following type from cache. ");
        foreach (XmlQualifiedName contractName in endpointDiscoveryMetadata.ContractTypeNames)
        {
            Console.WriteLine("** " + contractName.ToString());
            break;
        }
        Console.WriteLine("**** Operation Completed");
    }
    ```

5. <span data-ttu-id="9a0a9-135">Aggiungere le classi AsyncResult seguenti a DiscoveryProxyService.</span><span class="sxs-lookup"><span data-stu-id="9a0a9-135">Add the following AsyncResult classes to the DiscoveryProxyService.</span></span> <span data-ttu-id="9a0a9-136">Tali classi vengono utilizzate per distinguere i diversi risultati delle operazioni asincrone.</span><span class="sxs-lookup"><span data-stu-id="9a0a9-136">These classes are used to differentiate between the different asynchronous operation results.</span></span>

    ```csharp
    sealed class OnOnlineAnnouncementAsyncResult : AsyncResult
    {
        public OnOnlineAnnouncementAsyncResult(AsyncCallback callback, object state)
            : base(callback, state)
        {
            this.Complete(true);
        }

        public static void End(IAsyncResult result)
        {
            AsyncResult.End<OnOnlineAnnouncementAsyncResult>(result);
        }
    }

    sealed class OnOfflineAnnouncementAsyncResult : AsyncResult
    {
        public OnOfflineAnnouncementAsyncResult(AsyncCallback callback, object state)
            : base(callback, state)
        {
            this.Complete(true);
        }

        public static void End(IAsyncResult result)
        {
            AsyncResult.End<OnOfflineAnnouncementAsyncResult>(result);
        }
    }

    sealed class OnFindAsyncResult : AsyncResult
    {
        public OnFindAsyncResult(AsyncCallback callback, object state)
            : base(callback, state)
        {
            this.Complete(true);
        }

        public static void End(IAsyncResult result)
        {
            AsyncResult.End<OnFindAsyncResult>(result);
        }
    }

    sealed class OnResolveAsyncResult : AsyncResult
    {
        EndpointDiscoveryMetadata matchingEndpoint;

        public OnResolveAsyncResult(EndpointDiscoveryMetadata matchingEndpoint, AsyncCallback callback, object state)
            : base(callback, state)
        {
            this.matchingEndpoint = matchingEndpoint;
            this.Complete(true);
        }

        public static EndpointDiscoveryMetadata End(IAsyncResult result)
        {
            OnResolveAsyncResult thisPtr = AsyncResult.End<OnResolveAsyncResult>(result);
            return thisPtr.matchingEndpoint;
        }
    }
    ```

### <a name="to-define-the-methods-that-implement-the-discovery-proxy-functionality"></a><span data-ttu-id="9a0a9-137">Per definire i metodi che implementano la funzionalità del proxy di individuazione</span><span class="sxs-lookup"><span data-stu-id="9a0a9-137">To define the methods that implement the discovery proxy functionality</span></span>

1. <span data-ttu-id="9a0a9-138">Eseguire l'override del metodo <xref:System.ServiceModel.Discovery.DiscoveryProxy.OnBeginOnlineAnnouncement%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="9a0a9-138">Override the <xref:System.ServiceModel.Discovery.DiscoveryProxy.OnBeginOnlineAnnouncement%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="9a0a9-139">Questo metodo viene chiamato quando il proxy di individuazione riceve un messaggio di annuncio online.</span><span class="sxs-lookup"><span data-stu-id="9a0a9-139">This method is called when the discovery proxy receives an online announcement message.</span></span>

    ```csharp
    // OnBeginOnlineAnnouncement method is called when a Hello message is received by the Proxy
    protected override IAsyncResult OnBeginOnlineAnnouncement(DiscoveryMessageSequence messageSequence, EndpointDiscoveryMetadata endpointDiscoveryMetadata, AsyncCallback callback, object state)
    {
        this.AddOnlineService(endpointDiscoveryMetadata);
        return new OnOnlineAnnouncementAsyncResult(callback, state);
    }
    ```

2. <span data-ttu-id="9a0a9-140">Eseguire l'override del metodo <xref:System.ServiceModel.Discovery.DiscoveryProxy.OnEndOnlineAnnouncement%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="9a0a9-140">Override the <xref:System.ServiceModel.Discovery.DiscoveryProxy.OnEndOnlineAnnouncement%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="9a0a9-141">Questo metodo viene chiamato quando il proxy di individuazione completa l'elaborazione di un messaggio di annuncio.</span><span class="sxs-lookup"><span data-stu-id="9a0a9-141">This method is called when the discovery proxy finishes processing an announcement message.</span></span>

    ```csharp
    protected override void OnEndOnlineAnnouncement(IAsyncResult result)
    {
        OnOnlineAnnouncementAsyncResult.End(result);
    }
    ```

3. <span data-ttu-id="9a0a9-142">Eseguire l'override del metodo <xref:System.ServiceModel.Discovery.DiscoveryProxy.OnBeginOfflineAnnouncement%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="9a0a9-142">Override the <xref:System.ServiceModel.Discovery.DiscoveryProxy.OnBeginOfflineAnnouncement%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="9a0a9-143">Questo metodo viene chiamato quando il proxy di individuazione riceve un messaggio di annuncio offline.</span><span class="sxs-lookup"><span data-stu-id="9a0a9-143">This method is called with the discovery proxy receives an offline announcement message.</span></span>

    ```csharp
    // OnBeginOfflineAnnouncement method is called when a Bye message is received by the Proxy
    protected override IAsyncResult OnBeginOfflineAnnouncement(DiscoveryMessageSequence messageSequence, EndpointDiscoveryMetadata endpointDiscoveryMetadata, AsyncCallback callback, object state)
    {
        this.RemoveOnlineService(endpointDiscoveryMetadata);
        return new OnOfflineAnnouncementAsyncResult(callback, state);
    }
    ```

4. <span data-ttu-id="9a0a9-144">Eseguire l'override del metodo <xref:System.ServiceModel.Discovery.DiscoveryProxy.OnEndOfflineAnnouncement%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="9a0a9-144">Override the <xref:System.ServiceModel.Discovery.DiscoveryProxy.OnEndOfflineAnnouncement%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="9a0a9-145">Questo metodo viene chiamato quando il proxy di individuazione completa l'elaborazione di un messaggio di annuncio offline.</span><span class="sxs-lookup"><span data-stu-id="9a0a9-145">This method is called when the discovery proxy finishes processing an offline announcement message.</span></span>

    ```csharp
    protected override void OnEndOfflineAnnouncement(IAsyncResult result)
    {
        OnOfflineAnnouncementAsyncResult.End(result);
    }
    ```

5. <span data-ttu-id="9a0a9-146">Eseguire l'override del metodo <xref:System.ServiceModel.Discovery.DiscoveryProxy.OnBeginFind%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="9a0a9-146">Override the <xref:System.ServiceModel.Discovery.DiscoveryProxy.OnBeginFind%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="9a0a9-147">Questo metodo viene chiamato quando il proxy di individuazione riceve una richiesta di ricerca.</span><span class="sxs-lookup"><span data-stu-id="9a0a9-147">This method is called when the discovery proxy receives a find request.</span></span>

    ```csharp
    // OnBeginFind method is called when a Probe request message is received by the Proxy
    protected override IAsyncResult OnBeginFind(FindRequestContext findRequestContext, AsyncCallback callback, object state)
    {
        this.MatchFromOnlineService(findRequestContext);
        return new OnFindAsyncResult(callback, state);
    }
    protected override IAsyncResult OnBeginFind(FindRequest findRequest, AsyncCallback callback, object state)
    {
        Collection<EndpointDiscoveryMetadata> matchingEndpoints = MatchFromCache(findRequest.Criteria);
        return new OnFindAsyncResult(
                    matchingEndpoints,
                    callback,
                    state);
    }
    ```

6. <span data-ttu-id="9a0a9-148">Eseguire l'override del metodo <xref:System.ServiceModel.Discovery.DiscoveryProxy.OnEndFind%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="9a0a9-148">Override the <xref:System.ServiceModel.Discovery.DiscoveryProxy.OnEndFind%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="9a0a9-149">Questo metodo viene chiamato quando il proxy di individuazione completa l'elaborazione di una richiesta di ricerca.</span><span class="sxs-lookup"><span data-stu-id="9a0a9-149">This method is called when the discovery proxy finishes processing a find request.</span></span>

    ```csharp
    protected override void OnEndFind(IAsyncResult result)
    {
        OnFindAsyncResult.End(result);
    }
    ```

7. <span data-ttu-id="9a0a9-150">Eseguire l'override del metodo <xref:System.ServiceModel.Discovery.DiscoveryProxy.OnBeginResolve%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="9a0a9-150">Override the <xref:System.ServiceModel.Discovery.DiscoveryProxy.OnBeginResolve%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="9a0a9-151">Questo metodo viene chiamato quando il proxy di individuazione riceve un messaggio di risoluzione.</span><span class="sxs-lookup"><span data-stu-id="9a0a9-151">This method is called when the discovery proxy receives a resolve message.</span></span>

    ```csharp
    // OnBeginFind method is called when a Resolve request message is received by the Proxy
    protected override IAsyncResult OnBeginResolve(ResolveCriteria resolveCriteria, AsyncCallback callback, object state)
    {
        return new OnResolveAsyncResult(this.MatchFromOnlineService(resolveCriteria), callback, state);
    }
    protected override IAsyncResult OnBeginResolve(ResolveRequest resolveRequest, AsyncCallback callback, object state)
    {
        return new OnResolveAsyncResult(
            this.proxy.MatchFromOnlineService(resolveRequest.Criteria),
            callback,
            state);
    }
    ```

8. <span data-ttu-id="9a0a9-152">Eseguire l'override del metodo <xref:System.ServiceModel.Discovery.DiscoveryProxy.OnEndResolve%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="9a0a9-152">Override the <xref:System.ServiceModel.Discovery.DiscoveryProxy.OnEndResolve%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="9a0a9-153">Questo metodo viene chiamato quando il proxy di individuazione completa l'elaborazione di un messaggio di risoluzione.</span><span class="sxs-lookup"><span data-stu-id="9a0a9-153">This method is called when the discovery proxy finishes processing a resolve message.</span></span>

    ```csharp
    protected override EndpointDiscoveryMetadata OnEndResolve(IAsyncResult result)
    {
        return OnResolveAsyncResult.End(result);
    }
    ```

<span data-ttu-id="9a0a9-154">I metodi OnBegin.</span><span class="sxs-lookup"><span data-stu-id="9a0a9-154">The OnBegin..</span></span> <span data-ttu-id="9a0a9-155">/ OnEnd.</span><span class="sxs-lookup"><span data-stu-id="9a0a9-155">/ OnEnd..</span></span> <span data-ttu-id="9a0a9-156">forniscono la logica per le operazioni di individuazione successive.</span><span class="sxs-lookup"><span data-stu-id="9a0a9-156">methods provide the logic for the subsequent discovery operations.</span></span> <span data-ttu-id="9a0a9-157">I metodi <xref:System.ServiceModel.Discovery.DiscoveryProxy.OnBeginFind%2A> e <xref:System.ServiceModel.Discovery.DiscoveryProxy.OnEndFind%2A> implementano ad esempio la logica di ricerca per il proxy di individuazione.</span><span class="sxs-lookup"><span data-stu-id="9a0a9-157">For example the <xref:System.ServiceModel.Discovery.DiscoveryProxy.OnBeginFind%2A> and <xref:System.ServiceModel.Discovery.DiscoveryProxy.OnEndFind%2A> methods implement the find logic for discovery proxy.</span></span> <span data-ttu-id="9a0a9-158">Quando il proxy di individuazione riceve un messaggio del probe, questi metodi vengono eseguiti per inviare una risposta al client.</span><span class="sxs-lookup"><span data-stu-id="9a0a9-158">When the discovery proxy receives a probe message these methods are executed to send a response back to the client.</span></span> <span data-ttu-id="9a0a9-159">È possibile modificare la logica di ricerca in base alle proprie esigenze. È ad esempio possibile incorporare un ambito personalizzato in base ad algoritmi o all'analisi dei metadati XML specifici dell'applicazione nell'ambito dell'operazione di ricerca.</span><span class="sxs-lookup"><span data-stu-id="9a0a9-159">You may modify the find logic as you wish, for example you can incorporate custom scope matching by algorithms or application specific XML metadata parsing as part of your find operation.</span></span>

### <a name="to-implement-the-asyncresult-class"></a><span data-ttu-id="9a0a9-160">Per implementare la classe AsyncResult</span><span class="sxs-lookup"><span data-stu-id="9a0a9-160">To implement the AsyncResult class</span></span>

1. <span data-ttu-id="9a0a9-161">Definire la classe di base astratta AsyncResult, utilizzata per derivare le varie classi AsyncResult.</span><span class="sxs-lookup"><span data-stu-id="9a0a9-161">Define the abstract base class AsyncResult which is used to derive the various async result classes.</span></span>

2. <span data-ttu-id="9a0a9-162">Creare un nuovo file di codice denominato AsyncResult.cs.</span><span class="sxs-lookup"><span data-stu-id="9a0a9-162">Create a new code file called AsyncResult.cs.</span></span>

3. <span data-ttu-id="9a0a9-163">Aggiungere le istruzioni `using` seguenti a AsyncResult.cs.</span><span class="sxs-lookup"><span data-stu-id="9a0a9-163">Add the following `using` statements to AsyncResult.cs.</span></span>

    ```csharp
    using System;
    using System.Threading;
    ```

4. <span data-ttu-id="9a0a9-164">Aggiungere la classe AsyncResult seguente.</span><span class="sxs-lookup"><span data-stu-id="9a0a9-164">Add the following AsyncResult class.</span></span>

    ```csharp
    abstract class AsyncResult : IAsyncResult
    {
        AsyncCallback callback;
        bool completedSynchronously;
        bool endCalled;
        Exception exception;
        bool isCompleted;
        ManualResetEvent manualResetEvent;
        object state;
        object thisLock;

        protected AsyncResult(AsyncCallback callback, object state)
        {
            this.callback = callback;
            this.state = state;
            this.thisLock = new object();
        }

        public object AsyncState
        {
            get
            {
                return state;
            }
        }

        public WaitHandle AsyncWaitHandle
        {
            get
            {
                if (manualResetEvent != null)
                {
                    return manualResetEvent;
                }
                lock (ThisLock)
                {
                    manualResetEvent ??= new ManualResetEvent(isCompleted);
                }
                return manualResetEvent;
            }
        }

        public bool CompletedSynchronously
        {
            get
            {
                return completedSynchronously;
            }
        }

        public bool IsCompleted
        {
            get
            {
                return isCompleted;
            }
        }

        object ThisLock
        {
            get
            {
                return this.thisLock;
            }
        }

        protected static TAsyncResult End<TAsyncResult>(IAsyncResult result)
            where TAsyncResult : AsyncResult
        {
            if (result == null)
            {
                throw new ArgumentNullException("result");
            }

            TAsyncResult asyncResult = result as TAsyncResult;

            if (asyncResult == null)
            {
                throw new ArgumentException("Invalid async result.", "result");
            }

            if (asyncResult.endCalled)
            {
                throw new InvalidOperationException("Async object already ended.");
            }

            asyncResult.endCalled = true;

            if (!asyncResult.isCompleted)
            {
                asyncResult.AsyncWaitHandle.WaitOne();
            }

            if (asyncResult.manualResetEvent != null)
            {
                asyncResult.manualResetEvent.Close();
            }

            if (asyncResult.exception != null)
            {
                throw asyncResult.exception;
            }

            return asyncResult;
        }

        protected void Complete(bool completedSynchronously)
        {
            if (isCompleted)
            {
                throw new InvalidOperationException("This async result is already completed.");
            }

            this.completedSynchronously = completedSynchronously;

            if (completedSynchronously)
            {
                this.isCompleted = true;
            }
            else
            {
                lock (ThisLock)
                {
                    this.isCompleted = true;
                    if (this.manualResetEvent != null)
                    {
                        this.manualResetEvent.Set();
                    }
                }
            }

            if (callback != null)
            {
                callback(this);
            }
        }

        protected void Complete(bool completedSynchronously, Exception exception)
        {
            this.exception = exception;
            Complete(completedSynchronously);
        }
    }
    ```

### <a name="to-host-the-discoveryproxy"></a><span data-ttu-id="9a0a9-165">Per ospitare DiscoveryProxy</span><span class="sxs-lookup"><span data-stu-id="9a0a9-165">To host the DiscoveryProxy</span></span>

1. <span data-ttu-id="9a0a9-166">Aprire il file Program.cs nel progetto DiscoveryProxyExample.</span><span class="sxs-lookup"><span data-stu-id="9a0a9-166">Open the Program.cs file in the DiscoveryProxyExample project.</span></span>

2. <span data-ttu-id="9a0a9-167">Aggiungere le istruzioni `using` seguenti.</span><span class="sxs-lookup"><span data-stu-id="9a0a9-167">Add the following `using` statements.</span></span>

    ```csharp
    using System;
    using System.ServiceModel;
    using System.ServiceModel.Discovery;
    ```

3. <span data-ttu-id="9a0a9-168">Aggiungere nel metodo `Main()` il codice riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="9a0a9-168">Within the `Main()` method, add the following code.</span></span> <span data-ttu-id="9a0a9-169">In questo modo viene creata un'istanza della classe `DiscoveryProxy`.</span><span class="sxs-lookup"><span data-stu-id="9a0a9-169">This creates an instance of the `DiscoveryProxy` class.</span></span>

    ```csharp
    Uri probeEndpointAddress = new Uri("net.tcp://localhost:8001/Probe");
    Uri announcementEndpointAddress = new Uri("net.tcp://localhost:9021/Announcement");

    // Host the DiscoveryProxy service
    ServiceHost proxyServiceHost = new ServiceHost(new DiscoveryProxyService());
    ```

4. <span data-ttu-id="9a0a9-170">Aggiungere quindi il codice seguente per aggiungere un endpoint di individuazione e un endpoint annunci.</span><span class="sxs-lookup"><span data-stu-id="9a0a9-170">Next add the following code to add a discovery endpoint and an announcement endpoint.</span></span>

    ```csharp
    try
    {
        // Add DiscoveryEndpoint to receive Probe and Resolve messages
        DiscoveryEndpoint discoveryEndpoint = new DiscoveryEndpoint(new NetTcpBinding(), new EndpointAddress(probeEndpointAddress));
        discoveryEndpoint.IsSystemEndpoint = false;

        // Add AnnouncementEndpoint to receive Hello and Bye announcement messages
        AnnouncementEndpoint announcementEndpoint = new AnnouncementEndpoint(new NetTcpBinding(), new EndpointAddress(announcementEndpointAddress));

        proxyServiceHost.AddServiceEndpoint(discoveryEndpoint);
        proxyServiceHost.AddServiceEndpoint(announcementEndpoint);

        proxyServiceHost.Open();

        Console.WriteLine("Proxy Service started.");
        Console.WriteLine();
        Console.WriteLine("Press <ENTER> to terminate the service.");
        Console.WriteLine();
        Console.ReadLine();

        proxyServiceHost.Close();
    }
    catch (CommunicationException e)
    {
        Console.WriteLine(e.Message);
    }
    catch (TimeoutException e)
    {
        Console.WriteLine(e.Message);
    }

    if (proxyServiceHost.State != CommunicationState.Closed)
    {
        Console.WriteLine("Aborting the service...");
        proxyServiceHost.Abort();
    }
    ```

<span data-ttu-id="9a0a9-171">L'implementazione del proxy di individuazione è quindi completata.</span><span class="sxs-lookup"><span data-stu-id="9a0a9-171">You have completed implementing the discovery proxy.</span></span> <span data-ttu-id="9a0a9-172">Continuare con [la procedura: implementare un servizio individuabile che esegue la registrazione con il proxy di individuazione](discoverable-service-that-registers-with-the-discovery-proxy.md).</span><span class="sxs-lookup"><span data-stu-id="9a0a9-172">Continue on to [How to: Implement a Discoverable Service that Registers with the Discovery Proxy](discoverable-service-that-registers-with-the-discovery-proxy.md).</span></span>

## <a name="example"></a><span data-ttu-id="9a0a9-173">Esempio</span><span class="sxs-lookup"><span data-stu-id="9a0a9-173">Example</span></span>

<span data-ttu-id="9a0a9-174">Quello che segue è l'elenco completo del codice usato in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="9a0a9-174">This is the full listing of the code used in this topic.</span></span>

```csharp
// DiscoveryProxy.cs
//----------------------------------------------------------------
// Copyright (c) Microsoft Corporation.  All rights reserved.
//----------------------------------------------------------------

using System;
using System.Collections.Generic;
using System.ServiceModel;
using System.ServiceModel.Discovery;
using System.Xml;

namespace Microsoft.Samples.Discovery
{
    // Implement DiscoveryProxy by extending the DiscoveryProxy class and overriding the abstract methods
    [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single, ConcurrencyMode = ConcurrencyMode.Multiple)]
    public class DiscoveryProxyService : DiscoveryProxy
    {
        // Repository to store EndpointDiscoveryMetadata. A database or a flat file could also be used instead.
        Dictionary<EndpointAddress, EndpointDiscoveryMetadata> onlineServices;

        public DiscoveryProxyService()
        {
            this.onlineServices = new Dictionary<EndpointAddress, EndpointDiscoveryMetadata>();
        }

        // OnBeginOnlineAnnouncement method is called when a Hello message is received by the Proxy
        protected override IAsyncResult OnBeginOnlineAnnouncement(DiscoveryMessageSequence messageSequence, EndpointDiscoveryMetadata endpointDiscoveryMetadata, AsyncCallback callback, object state)
        {
            this.AddOnlineService(endpointDiscoveryMetadata);
            return new OnOnlineAnnouncementAsyncResult(callback, state);
        }

        protected override void OnEndOnlineAnnouncement(IAsyncResult result)
        {
            OnOnlineAnnouncementAsyncResult.End(result);
        }

        // OnBeginOfflineAnnouncement method is called when a Bye message is received by the Proxy
        protected override IAsyncResult OnBeginOfflineAnnouncement(DiscoveryMessageSequence messageSequence, EndpointDiscoveryMetadata endpointDiscoveryMetadata, AsyncCallback callback, object state)
        {
            this.RemoveOnlineService(endpointDiscoveryMetadata);
            return new OnOfflineAnnouncementAsyncResult(callback, state);
        }

        protected override void OnEndOfflineAnnouncement(IAsyncResult result)
        {
            OnOfflineAnnouncementAsyncResult.End(result);
        }

        // OnBeginFind method is called when a Probe request message is received by the Proxy
        protected override IAsyncResult OnBeginFind(FindRequestContext findRequestContext, AsyncCallback callback, object state)
        {
            this.MatchFromOnlineService(findRequestContext);
            return new OnFindAsyncResult(callback, state);
        }

        protected override void OnEndFind(IAsyncResult result)
        {
            OnFindAsyncResult.End(result);
        }

        // OnBeginFind method is called when a Resolve request message is received by the Proxy
        protected override IAsyncResult OnBeginResolve(ResolveCriteria resolveCriteria, AsyncCallback callback, object state)
        {
            return new OnResolveAsyncResult(this.MatchFromOnlineService(resolveCriteria), callback, state);
        }

        protected override EndpointDiscoveryMetadata OnEndResolve(IAsyncResult result)
        {
            return OnResolveAsyncResult.End(result);
        }

        // The following are helper methods required by the Proxy implementation
        void AddOnlineService(EndpointDiscoveryMetadata endpointDiscoveryMetadata)
        {
            lock (this.onlineServices)
            {
                this.onlineServices[endpointDiscoveryMetadata.Address] = endpointDiscoveryMetadata;
            }

            PrintDiscoveryMetadata(endpointDiscoveryMetadata, "Adding");
        }

        void RemoveOnlineService(EndpointDiscoveryMetadata endpointDiscoveryMetadata)
        {
            if (endpointDiscoveryMetadata != null)
            {
                lock (this.onlineServices)
                {
                    this.onlineServices.Remove(endpointDiscoveryMetadata.Address);
                }

                PrintDiscoveryMetadata(endpointDiscoveryMetadata, "Removing");
            }
        }

        void MatchFromOnlineService(FindRequestContext findRequestContext)
        {
            lock (this.onlineServices)
            {
                foreach (EndpointDiscoveryMetadata endpointDiscoveryMetadata in this.onlineServices.Values)
                {
                    if (findRequestContext.Criteria.IsMatch(endpointDiscoveryMetadata))
                    {
                        findRequestContext.AddMatchingEndpoint(endpointDiscoveryMetadata);
                    }
                }
            }
        }

        EndpointDiscoveryMetadata MatchFromOnlineService(ResolveCriteria criteria)
        {
            EndpointDiscoveryMetadata matchingEndpoint = null;
            lock (this.onlineServices)
            {
                foreach (EndpointDiscoveryMetadata endpointDiscoveryMetadata in this.onlineServices.Values)
                {
                    if (criteria.Address == endpointDiscoveryMetadata.Address)
                    {
                        matchingEndpoint = endpointDiscoveryMetadata;
                    }
                }
            }
            return matchingEndpoint;
        }

        void PrintDiscoveryMetadata(EndpointDiscoveryMetadata endpointDiscoveryMetadata, string verb)
        {
            Console.WriteLine("\n**** " + verb + " service of the following type from cache. ");
            foreach (XmlQualifiedName contractName in endpointDiscoveryMetadata.ContractTypeNames)
            {
                Console.WriteLine("** " + contractName.ToString());
                break;
            }
            Console.WriteLine("**** Operation Completed");
        }

        sealed class OnOnlineAnnouncementAsyncResult : AsyncResult
        {
            public OnOnlineAnnouncementAsyncResult(AsyncCallback callback, object state)
                : base(callback, state)
            {
                this.Complete(true);
            }

            public static void End(IAsyncResult result)
            {
                AsyncResult.End<OnOnlineAnnouncementAsyncResult>(result);
            }
        }

        sealed class OnOfflineAnnouncementAsyncResult : AsyncResult
        {
            public OnOfflineAnnouncementAsyncResult(AsyncCallback callback, object state)
                : base(callback, state)
            {
                this.Complete(true);
            }

            public static void End(IAsyncResult result)
            {
                AsyncResult.End<OnOfflineAnnouncementAsyncResult>(result);
            }
        }

        sealed class OnFindAsyncResult : AsyncResult
        {
            public OnFindAsyncResult(AsyncCallback callback, object state)
                : base(callback, state)
            {
                this.Complete(true);
            }

            public static void End(IAsyncResult result)
            {
                AsyncResult.End<OnFindAsyncResult>(result);
            }
        }

        sealed class OnResolveAsyncResult : AsyncResult
        {
            EndpointDiscoveryMetadata matchingEndpoint;

            public OnResolveAsyncResult(EndpointDiscoveryMetadata matchingEndpoint, AsyncCallback callback, object state)
                : base(callback, state)
            {
                this.matchingEndpoint = matchingEndpoint;
                this.Complete(true);
            }

            public static EndpointDiscoveryMetadata End(IAsyncResult result)
            {
                OnResolveAsyncResult thisPtr = AsyncResult.End<OnResolveAsyncResult>(result);
                return thisPtr.matchingEndpoint;
            }
        }
    }
}
```

```csharp
// AsyncResult.cs
//----------------------------------------------------------------
// Copyright (c) Microsoft Corporation.  All rights reserved.
//----------------------------------------------------------------

using System;
using System.Threading;

namespace Microsoft.Samples.Discovery
{
    abstract class AsyncResult : IAsyncResult
    {
        AsyncCallback callback;
        bool completedSynchronously;
        bool endCalled;
        Exception exception;
        bool isCompleted;
        ManualResetEvent manualResetEvent;
        object state;
        object thisLock;

        protected AsyncResult(AsyncCallback callback, object state)
        {
            this.callback = callback;
            this.state = state;
            this.thisLock = new object();
        }

        public object AsyncState
        {
            get
            {
                return state;
            }
        }

        public WaitHandle AsyncWaitHandle
        {
            get
            {
                if (manualResetEvent != null)
                {
                    return manualResetEvent;
                }
                lock (ThisLock)
                {
                    manualResetEvent ??= new ManualResetEvent(isCompleted);
                }
                return manualResetEvent;
            }
        }

        public bool CompletedSynchronously
        {
            get
            {
                return completedSynchronously;
            }
        }

        public bool IsCompleted
        {
            get
            {
                return isCompleted;
            }
        }

        object ThisLock
        {
            get
            {
                return this.thisLock;
            }
        }

        protected static TAsyncResult End<TAsyncResult>(IAsyncResult result)
            where TAsyncResult : AsyncResult
        {
            if (result == null)
            {
                throw new ArgumentNullException("result");
            }

            TAsyncResult asyncResult = result as TAsyncResult;

            if (asyncResult == null)
            {
                throw new ArgumentException("Invalid async result.", "result");
            }

            if (asyncResult.endCalled)
            {
                throw new InvalidOperationException("Async object already ended.");
            }

            asyncResult.endCalled = true;

            if (!asyncResult.isCompleted)
            {
                asyncResult.AsyncWaitHandle.WaitOne();
            }

            if (asyncResult.manualResetEvent != null)
            {
                asyncResult.manualResetEvent.Close();
            }

            if (asyncResult.exception != null)
            {
                throw asyncResult.exception;
            }

            return asyncResult;
        }

        protected void Complete(bool completedSynchronously)
        {
            if (isCompleted)
            {
                throw new InvalidOperationException("This async result is already completed.");
            }

            this.completedSynchronously = completedSynchronously;

            if (completedSynchronously)
            {
                this.isCompleted = true;
            }
            else
            {
                lock (ThisLock)
                {
                    this.isCompleted = true;
                    if (this.manualResetEvent != null)
                    {
                        this.manualResetEvent.Set();
                    }
                }
            }

            if (callback != null)
            {
                callback(this);
            }
        }

        protected void Complete(bool completedSynchronously, Exception exception)
        {
            this.exception = exception;
            Complete(completedSynchronously);
        }
    }
}
```

```csharp
// program.cs
//----------------------------------------------------------------
// Copyright (c) Microsoft Corporation.  All rights reserved.
//----------------------------------------------------------------

using System;
using System.ServiceModel;
using System.ServiceModel.Discovery;

namespace Microsoft.Samples.Discovery
{
    class Program
    {
        public static void Main()
        {
            Uri probeEndpointAddress = new Uri("net.tcp://localhost:8001/Probe");
            Uri announcementEndpointAddress = new Uri("net.tcp://localhost:9021/Announcement");

            // Host the DiscoveryProxy service
            ServiceHost proxyServiceHost = new ServiceHost(new DiscoveryProxyService());

            try
            {
                // Add DiscoveryEndpoint to receive Probe and Resolve messages
                DiscoveryEndpoint discoveryEndpoint = new DiscoveryEndpoint(new NetTcpBinding(), new EndpointAddress(probeEndpointAddress));
                discoveryEndpoint.IsSystemEndpoint = false;

                // Add AnnouncementEndpoint to receive Hello and Bye announcement messages
                AnnouncementEndpoint announcementEndpoint = new AnnouncementEndpoint(new NetTcpBinding(), new EndpointAddress(announcementEndpointAddress));

                proxyServiceHost.AddServiceEndpoint(discoveryEndpoint);
                proxyServiceHost.AddServiceEndpoint(announcementEndpoint);

                proxyServiceHost.Open();

                Console.WriteLine("Proxy Service started.");
                Console.WriteLine();
                Console.WriteLine("Press <ENTER> to terminate the service.");
                Console.WriteLine();
                Console.ReadLine();

                proxyServiceHost.Close();
            }
            catch (CommunicationException e)
            {
                Console.WriteLine(e.Message);
            }
            catch (TimeoutException e)
            {
                Console.WriteLine(e.Message);
            }

            if (proxyServiceHost.State != CommunicationState.Closed)
            {
                Console.WriteLine("Aborting the service...");
                proxyServiceHost.Abort();
            }
        }
    }
}
```

## <a name="see-also"></a><span data-ttu-id="9a0a9-175">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9a0a9-175">See also</span></span>

- [<span data-ttu-id="9a0a9-176">Panoramica di WCF Discovery</span><span class="sxs-lookup"><span data-stu-id="9a0a9-176">WCF Discovery Overview</span></span>](wcf-discovery-overview.md)
- [<span data-ttu-id="9a0a9-177">Procedura: implementare un servizio individuabile che esegue la registrazione al proxy di individuazione</span><span class="sxs-lookup"><span data-stu-id="9a0a9-177">How to: Implement a Discoverable Service that Registers with the Discovery Proxy</span></span>](discoverable-service-that-registers-with-the-discovery-proxy.md)
- [<span data-ttu-id="9a0a9-178">Procedura: implementare un'applicazione client che usa il proxy di individuazione per cercare un servizio</span><span class="sxs-lookup"><span data-stu-id="9a0a9-178">How to: Implement a Client Application that Uses the Discovery Proxy to Find a Service</span></span>](client-app-discovery-proxy-to-find-a-service.md)
- [<span data-ttu-id="9a0a9-179">Procedura: test del proxy di individuazione</span><span class="sxs-lookup"><span data-stu-id="9a0a9-179">How to: Test the Discovery Proxy</span></span>](how-to-test-the-discovery-proxy.md)

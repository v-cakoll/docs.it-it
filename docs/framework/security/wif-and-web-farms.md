---
title: WIF e Web farm
ms.date: 03/30/2017
ms.assetid: fc3cd7fa-2b45-4614-a44f-8fa9b9d15284
author: BrucePerlerMS
ms.openlocfilehash: 85fbebcd210e7df17212d39b8e3aca9bf76bfb67
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54543055"
---
# <a name="wif-and-web-farms"></a><span data-ttu-id="321ce-102">WIF e Web farm</span><span class="sxs-lookup"><span data-stu-id="321ce-102">WIF and Web Farms</span></span>
<span data-ttu-id="321ce-103">Quando si usa Windows Identity Foundation (WIF) per proteggere le risorse di un'applicazione relying party (RP) distribuita in una Web farm, è necessario eseguire passaggi specifici per garantire che WIF possa elaborare i token da istanze dell'applicazione relying party in esecuzione in computer diversi nella farm.</span><span class="sxs-lookup"><span data-stu-id="321ce-103">When you use Windows Identity Foundation (WIF) to secure the resources of a relying party (RP) application that is deployed in a web farm, you must take specific steps to ensure that WIF can process tokens from instances of the RP application running on different computers in the farm.</span></span> <span data-ttu-id="321ce-104">Tale elaborazione comprende la convalida delle firme dei token di sessione, la crittografia e la decrittografia dei token di sessione, la memorizzazione nella cache dei token di sessione e il rilevamento dei token di sicurezza riprodotti.</span><span class="sxs-lookup"><span data-stu-id="321ce-104">This processing includes validating session token signatures, encrypting and decrypting session tokens, caching session tokens, and detecting replayed security tokens.</span></span>  
  
 <span data-ttu-id="321ce-105">In genere, quando si usa WIF per proteggere le risorse di un'applicazione relying party, indipendentemente dal fatto che la relying party sia in esecuzione in un singolo computer o in una Web farm, viene stabilita una sessione con il client in base al token di sicurezza ottenuto dal servizio token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="321ce-105">In the typical case, when WIF is used to secure resources of an RP application – whether the RP is running on a single computer or in a web farm -- a session is established with the client based on the security token that was obtained from the security token service (STS).</span></span> <span data-ttu-id="321ce-106">Ciò avviene per evitare di forzare il client a eseguire l'autenticazione nel servizio token di sicurezza per tutte le risorse dell'applicazione protette mediante WIF.</span><span class="sxs-lookup"><span data-stu-id="321ce-106">This is to avoid forcing the client to have to authenticate at the STS for every application resource that is secured using WIF.</span></span> <span data-ttu-id="321ce-107">Per altre informazioni sulla modalità di gestione delle sessioni in WIF, vedere [Gestione delle sessioni WIF](../../../docs/framework/security/wif-session-management.md).</span><span class="sxs-lookup"><span data-stu-id="321ce-107">For more information about how WIF handles sessions, see [WIF Session Management](../../../docs/framework/security/wif-session-management.md).</span></span>  
  
 <span data-ttu-id="321ce-108">Quando vengono usate le impostazioni predefinite, WIF esegue le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="321ce-108">When default settings are used, WIF does the following:</span></span>  
  
-   <span data-ttu-id="321ce-109">Usa un'istanza della classe <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> per leggere e scrivere un token di sessione (un'istanza della classe <xref:System.IdentityModel.Tokens.SessionSecurityToken>) che contiene le attestazioni e altre informazioni sul token di sicurezza usato per l'autenticazione, oltre che informazioni relative alla sessione stessa.</span><span class="sxs-lookup"><span data-stu-id="321ce-109">It uses an instance of the <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> class to read and write a session token (an instance of the <xref:System.IdentityModel.Tokens.SessionSecurityToken> class) that carries the claims and other information about the security token that was used for authentication as well as information about the session itself.</span></span> <span data-ttu-id="321ce-110">Il token di sessione viene inserito in un pacchetto e archiviato in un cookie di sessione.</span><span class="sxs-lookup"><span data-stu-id="321ce-110">The session token is packaged and stored in a session cookie.</span></span> <span data-ttu-id="321ce-111">Per impostazione predefinita, <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> usa la classe <xref:System.IdentityModel.ProtectedDataCookieTransform>, che usa Data Protection API (DPAPI) per proteggere il token di sessione.</span><span class="sxs-lookup"><span data-stu-id="321ce-111">By default, <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> uses the <xref:System.IdentityModel.ProtectedDataCookieTransform> class, which uses the Data Protection API (DPAPI), to protect the session token.</span></span> <span data-ttu-id="321ce-112">DPAPI fornisce la protezione usando le credenziali dell'utente o del computer e archivia i dati della chiave nel profilo utente.</span><span class="sxs-lookup"><span data-stu-id="321ce-112">The DPAPI provides protection by using the user or machine credentials and stores the key data in the user profile.</span></span>  
  
-   <span data-ttu-id="321ce-113">Usa un'implementazione in memoria predefinita della classe <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> per archiviare ed elaborare il token di sessione.</span><span class="sxs-lookup"><span data-stu-id="321ce-113">It uses a default, in-memory implementation of the <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> class to store and process the session token.</span></span>  
  
 <span data-ttu-id="321ce-114">Queste impostazioni predefinite funzionano in scenari in cui l'applicazione relying party viene distribuita in un singolo computer. Se la distribuzione avviene invece in una Web farm, ogni richiesta HTTP può essere inviata a, ed elaborata da, un'istanza diversa dell'applicazione relying party in esecuzione in un computer diverso.</span><span class="sxs-lookup"><span data-stu-id="321ce-114">These default settings work in scenarios in which the RP application is deployed on a single computer; however, when deployed in a web farm, each HTTP request may be sent to and processed by a different instance of the RP application running on a different computer.</span></span> <span data-ttu-id="321ce-115">In questo scenario le impostazioni WIF predefinite descritte in precedenza non funzionano perché sia la protezione del token che la sua memorizzazione nella cache dipendono da un computer specifico.</span><span class="sxs-lookup"><span data-stu-id="321ce-115">In this scenario, the default WIF settings described above will not work because both token protection and token caching are dependent on a specific computer.</span></span>  
  
 <span data-ttu-id="321ce-116">Per distribuire un'applicazione relying party in una Web farm, è necessario assicurarsi che l'elaborazione dei token di sessione (oltre che dei token riprodotti) non dipenda dall'esecuzione dell'applicazione in un computer specifico.</span><span class="sxs-lookup"><span data-stu-id="321ce-116">To deploy an RP application in a web farm, you must ensure that the processing of session tokens (as well as of replayed tokens) is not dependent on the application running on a specific computer.</span></span> <span data-ttu-id="321ce-117">A tale scopo, è possibile implementare l'applicazione relying party in modo che usi le funzionalità fornite dall'elemento di configurazione `<machineKey>` ASP.NET e fornisca la cache distribuita per l'elaborazione dei token di sessione e dei token riprodotti.</span><span class="sxs-lookup"><span data-stu-id="321ce-117">One way to do this is to implement your RP application so that it uses the functionality provided by the ASP.NET `<machineKey>` configuration element and provides distributed caching for processing session tokens and replayed tokens.</span></span> <span data-ttu-id="321ce-118">L'elemento `<machineKey>` consente di specificare le chiavi necessarie per convalidare, crittografare e decrittografare i token in un file di configurazione, permettendo di specificare le stesse chiavi in computer diversi nella Web farm.</span><span class="sxs-lookup"><span data-stu-id="321ce-118">The `<machineKey>` element allows you to specify the keys needed to validate, encrypt, and decrypt tokens in a configuration file, which enables you to specify the same keys on different computers in the web farm.</span></span> <span data-ttu-id="321ce-119">WIF fornisce un gestore di token di sessione specializzato, <xref:System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler>, che protegge i token usando le chiavi specificate nell'elemento `<machineKey>`.</span><span class="sxs-lookup"><span data-stu-id="321ce-119">WIF provides a specialized session token handler, the <xref:System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler>, that protects tokens by using the keys specified in the `<machineKey>` element.</span></span> <span data-ttu-id="321ce-120">Per implementare questa strategia, è possibile seguire queste linee guida:</span><span class="sxs-lookup"><span data-stu-id="321ce-120">To implement this strategy, you can follow these guidelines:</span></span>  
  
-   <span data-ttu-id="321ce-121">Usare l'elemento `<machineKey>` ASP.NET nella configurazione per specificare in modo esplicito le chiavi di firma e di crittografia che possono essere usate tra più computer nella farm.</span><span class="sxs-lookup"><span data-stu-id="321ce-121">Use the ASP.NET `<machineKey>` element in configuration to explicitly specify signing and encryption keys that can be used across computers in the farm.</span></span> <span data-ttu-id="321ce-122">Il codice XML seguente mostra come specificare l'elemento `<machineKey>` sotto l'elemento `<system.web>` in un file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="321ce-122">The following XML shows the specification of the `<machineKey>` element under the `<system.web>` element in a configuration file.</span></span>  
  
    ```xml  
    <machineKey compatibilityMode="Framework45" decryptionKey="CC510D … 8925E6" validationKey="BEAC8 … 6A4B1DE" />  
    ```  
  
-   <span data-ttu-id="321ce-123">Configurare l'applicazione per usare <xref:System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler> aggiungendo l'oggetto alla raccolta di gestori di token.</span><span class="sxs-lookup"><span data-stu-id="321ce-123">Configure the application to use the <xref:System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler> by adding it to the token handler collection.</span></span> <span data-ttu-id="321ce-124">È prima necessario rimuovere <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> (o qualsiasi gestore derivato dalla classe <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler>) dalla raccolta di gestori di token, se tale gestore è presente.</span><span class="sxs-lookup"><span data-stu-id="321ce-124">You must first remove the <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> (or any handler derived from the <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> class) from the token handler collection if such a handler is present.</span></span> <span data-ttu-id="321ce-125"><xref:System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler> usa la classe <xref:System.IdentityModel.Services.MachineKeyTransform>, che protegge i dati dei cookie di sessione usando il materiale di crittografia specificato nell'elemento `<machineKey>`.</span><span class="sxs-lookup"><span data-stu-id="321ce-125">The <xref:System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler> uses the <xref:System.IdentityModel.Services.MachineKeyTransform> class, which protects the session cookie data by using the cryptographic material specified in the `<machineKey>` element.</span></span> <span data-ttu-id="321ce-126">Il codice XML seguente mostra come aggiungere <xref:System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler> a una raccolta di gestori di token.</span><span class="sxs-lookup"><span data-stu-id="321ce-126">The following XML shows how to add the <xref:System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler> to a token handler collection.</span></span>  
  
    ```xml  
    <securityTokenHandlers>  
      <remove type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
      <add type="System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
    </securityTokenHandlers>  
    ```  
  
-   <span data-ttu-id="321ce-127">Derivare da <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> e implementare la cache distribuita, ovvero una cache accessibile da tutti i computer della farm in cui la relying party potrebbe venire eseguita.</span><span class="sxs-lookup"><span data-stu-id="321ce-127">Derive from <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> and implement distributed caching, that is, a cache that is accessible from all computers in the farm on which the RP might run.</span></span> <span data-ttu-id="321ce-128">Configurare la relying party per usare la cache distribuita, specificando l'elemento [\<sessionSecurityTokenCache>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/sessionsecuritytokencache.md) nel file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="321ce-128">Configure the RP to use your distributed cache by specifying the [\<sessionSecurityTokenCache>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/sessionsecuritytokencache.md) element in the configuration file.</span></span> <span data-ttu-id="321ce-129">È possibile eseguire l'override del metodo <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache.LoadCustomConfiguration%2A?displayProperty=nameWithType> nella classe derivata per implementare gli elementi figlio dell'elemento `<sessionSecurityTokenCache>`, se sono necessari.</span><span class="sxs-lookup"><span data-stu-id="321ce-129">You can override the <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache.LoadCustomConfiguration%2A?displayProperty=nameWithType> method in your derived class to implement child elements of the `<sessionSecurityTokenCache>` element if they are required.</span></span>  
  
    ```xml  
    <caches>  
      <sessionSecurityTokenCache type="MyCacheLibrary.MySharedSessionSecurityTokenCache, MyCacheLibrary">  
        <!--optional child configuration elements, if implemented by the derived class -->  
      </sessionSecurityTokenCache>  
    </caches>  
    ```  
  
     <span data-ttu-id="321ce-130">Un modo per implementare la cache distribuita consiste nel fornire un front-end WCF per la cache personalizzata.</span><span class="sxs-lookup"><span data-stu-id="321ce-130">One way to implement distributed caching is to provide a WCF front end for your custom cache.</span></span> <span data-ttu-id="321ce-131">Per altre informazioni sull'implementazione di un servizio di caching WCF, vedere [Servizio di caching WCF](#BKMK_TheWCFCachingService).</span><span class="sxs-lookup"><span data-stu-id="321ce-131">For more information about implementing a WCF caching service, see [The WCF Caching Service](#BKMK_TheWCFCachingService).</span></span> <span data-ttu-id="321ce-132">Per altre informazioni sull'implementazione di un client WCF che l'applicazione relying party può usare per chiamare il servizio di caching, vedere [Servizio di caching WCF](#BKMK_TheWCFClient).</span><span class="sxs-lookup"><span data-stu-id="321ce-132">For more information about implementing a WCF client that the RP application can use to call the caching service, see [The WCF Caching Client](#BKMK_TheWCFClient).</span></span>  
  
-   <span data-ttu-id="321ce-133">Se l'applicazione rileva token riprodotti, è necessario seguire una strategia di cache distribuita simile per la cache di riproduzione dei token, derivando da <xref:System.IdentityModel.Tokens.TokenReplayCache> e puntando al servizio di caching di riproduzione dei token nell'elemento di configurazione [\<tokenReplayCache>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaycache.md).</span><span class="sxs-lookup"><span data-stu-id="321ce-133">If your application detects replayed tokens you must follow a similar distributed caching strategy for the token replay cache by deriving from <xref:System.IdentityModel.Tokens.TokenReplayCache> and pointing to your token replay caching service in the [\<tokenReplayCache>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaycache.md) configuration element.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="321ce-134">Tutti gli XML di esempio e codice in questo argomento è tratto dal [ClaimsAwareWebFarm](https://go.microsoft.com/fwlink/?LinkID=248408) esempio.</span><span class="sxs-lookup"><span data-stu-id="321ce-134">All of the example XML and code in this topic is taken from the [ClaimsAwareWebFarm](https://go.microsoft.com/fwlink/?LinkID=248408) sample.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="321ce-135">Gli esempi in questo argomento vengono forniti come sono e non devono essere usati nel codice di produzione senza alcuna modifica.</span><span class="sxs-lookup"><span data-stu-id="321ce-135">The examples in this topic are provided as-is and are not intended to be used in production code without modification.</span></span>  
  
<a name="BKMK_TheWCFCachingService"></a>   
## <a name="the-wcf-caching-service"></a><span data-ttu-id="321ce-136">Servizio di caching WCF</span><span class="sxs-lookup"><span data-stu-id="321ce-136">The WCF Caching Service</span></span>  
 <span data-ttu-id="321ce-137">L'interfaccia seguente definisce il contratto tra il servizio di caching WCF e il client WCF usato dall'applicazione relying party per comunicare.</span><span class="sxs-lookup"><span data-stu-id="321ce-137">The following interface defines the contract between the WCF caching service and the WCF client used by the relying party application to communicate with it.</span></span> <span data-ttu-id="321ce-138">Essenzialmente espone i metodi della classe <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> come operazioni del servizio.</span><span class="sxs-lookup"><span data-stu-id="321ce-138">It essentially exposes the methods of the <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> class as service operations.</span></span>  
  
```  
[ServiceContract()]  
public interface ISessionSecurityTokenCacheService  
{  
    [OperationContract]  
    void AddOrUpdate(string endpointId, string contextId, string keyGeneration, SessionSecurityToken value, DateTime expiryTime);  
  
    [OperationContract]  
    IEnumerable<SessionSecurityToken> GetAll(string endpointId, string contextId);  
  
    [OperationContract]  
    SessionSecurityToken Get(string endpointId, string contextId, string keyGeneration);  
  
    [OperationContract(Name = "RemoveAll")]  
    void RemoveAll(string endpointId, string contextId);  
  
    [OperationContract(Name = "RemoveAllByEndpointId")]  
    void RemoveAll(string endpointId);  
  
    [OperationContract]  
    void Remove(string endpointId, string contextId, string keyGeneration);  
}  
```  
  
 <span data-ttu-id="321ce-139">Il codice seguente mostra l'implementazione del servizio di caching WCF.</span><span class="sxs-lookup"><span data-stu-id="321ce-139">The following code shows the implementation of the WCF caching service.</span></span> <span data-ttu-id="321ce-140">In questo esempio viene usata la cache dei token di sessione in memoria predefinita implementata da WIF.</span><span class="sxs-lookup"><span data-stu-id="321ce-140">In this example, the default, in-memory session token cache implemented by WIF is used.</span></span> <span data-ttu-id="321ce-141">In alternativa, è possibile implementare una cache durevole supportata da un database.</span><span class="sxs-lookup"><span data-stu-id="321ce-141">Alternatively, you could implement a durable cache backed by a database.</span></span> <span data-ttu-id="321ce-142">`ISessionSecurityTokenCacheService` definisce l'interfaccia illustrata in precedenza.</span><span class="sxs-lookup"><span data-stu-id="321ce-142">`ISessionSecurityTokenCacheService` defines the interface shown above.</span></span> <span data-ttu-id="321ce-143">In questo esempio, per motivi di brevità, non vengono mostrati tutti i metodi necessari per implementare l'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="321ce-143">In this example, not all of the methods required to implement the interface are shown for brevity.</span></span>  
  
```  
using System;  
using System.Collections.Generic;  
using System.IdentityModel.Configuration;  
using System.IdentityModel.Tokens;  
using System.ServiceModel;  
using System.Xml;  
  
namespace WcfSessionSecurityTokenCacheService  
{  
    [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  
    public class SessionSecurityTokenCacheService : ISessionSecurityTokenCacheService  
    {  
        SessionSecurityTokenCache internalCache;  
  
        // sets the internal cache used by the service to the default WIF in-memory cache.  
        public SessionSecurityTokenCacheService()  
        {  
            internalCache = new IdentityModelCaches().SessionSecurityTokenCache;  
        }  
  
        ...  
  
        public SessionSecurityToken Get(string endpointId, string contextId, string keyGeneration)  
        {  
            // Delegates to the default, in-memory MruSessionSecurityTokenCache used by WIF  
            SessionSecurityToken token = internalCache.Get(new SessionSecurityTokenCacheKey(endpointId, GetContextId(contextId), GetKeyGeneration(keyGeneration)));  
            return token;  
        }  
  
        ...  
  
        private static UniqueId GetContextId(string contextIdString)  
        {  
            return contextIdString == null ? null : new UniqueId(contextIdString);  
        }  
  
        private static UniqueId GetKeyGeneration(string keyGenerationString)  
        {  
            return keyGenerationString == null ? null : new UniqueId(keyGenerationString);  
        }  
    }  
}  
```  
  
<a name="BKMK_TheWCFClient"></a>   
## <a name="the-wcf-caching-client"></a><span data-ttu-id="321ce-144">Client di memorizzazione nella cache WCF</span><span class="sxs-lookup"><span data-stu-id="321ce-144">The WCF Caching Client</span></span>  
 <span data-ttu-id="321ce-145">Questa sezione mostra l'implementazione di una classe che deriva da <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> e che delega le chiamate al servizio di caching.</span><span class="sxs-lookup"><span data-stu-id="321ce-145">This section shows the implementation of a class that derives from <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> and that delegates calls to the caching service.</span></span> <span data-ttu-id="321ce-146">L'applicazione relying party viene configurata per usare questa classe tramite l'elemento [\<sessionSecurityTokenCache>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/sessionsecuritytokencache.md), come nel codice XML seguente</span><span class="sxs-lookup"><span data-stu-id="321ce-146">You configure the RP application to use this class through the [\<sessionSecurityTokenCache>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/sessionsecuritytokencache.md) element as in the following XML</span></span>  
  
```xml  
<caches>  
  <sessionSecurityTokenCache type="CacheLibrary.SharedSessionSecurityTokenCache, CacheLibrary">  
    <!--cacheServiceAddress points to the centralized session security token cache service running in the web farm.-->  
    <cacheServiceAddress url="http://localhost:4161/SessionSecurityTokenCacheService.svc" />  
  </sessionSecurityTokenCache>  
</caches>  
```  
  
 <span data-ttu-id="321ce-147">La classe esegue l'override del metodo <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache.LoadCustomConfiguration%2A> per ottenere l'endpoint servizio dall'elemento figlio `<cacheServiceAddress>` personalizzato dell'elemento `<sessionSecurityTokenCache>`.</span><span class="sxs-lookup"><span data-stu-id="321ce-147">The class overrides the <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache.LoadCustomConfiguration%2A> method to get the service endpoint from the custom `<cacheServiceAddress>` child element of the `<sessionSecurityTokenCache>` element.</span></span> <span data-ttu-id="321ce-148">Usa l'endpoint per inizializzare un canale `ISessionSecurityTokenCacheService` su cui può comunicare con il servizio.</span><span class="sxs-lookup"><span data-stu-id="321ce-148">It uses this endpoint to initialize an `ISessionSecurityTokenCacheService` channel over which it can communicate with the service.</span></span>  <span data-ttu-id="321ce-149">In questo esempio, per motivi di brevità, non vengono mostrati tutti i metodi necessari per implementare la classe <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache>.</span><span class="sxs-lookup"><span data-stu-id="321ce-149">In this example, not all of the methods required to implement the <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> class are shown for brevity.</span></span>  
  
```  
using System;  
using System.Configuration;  
using System.IdentityModel.Configuration;  
using System.IdentityModel.Tokens;  
using System.ServiceModel;  
using System.Xml;  
  
namespace CacheLibrary  
{  
    /// <summary>  
    /// This class acts as a proxy to the WcfSessionSecurityTokenCacheService.  
    /// </summary>  
    public class SharedSessionSecurityTokenCache : SessionSecurityTokenCache, ICustomIdentityConfiguration  
    {  
        private ISessionSecurityTokenCacheService WcfSessionSecurityTokenCacheServiceClient;  
  
        internal SharedSessionSecurityTokenCache()  
        {  
        }  
  
        /// <summary>  
        /// Creates a client channel to call the service host.  
        /// </summary>  
        protected void Initialize(string cacheServiceAddress)  
        {  
            if (this.WcfSessionSecurityTokenCacheServiceClient != null)  
            {  
                return;  
            }  
  
            ChannelFactory<ISessionSecurityTokenCacheService> cf = new ChannelFactory<ISessionSecurityTokenCacheService>(  
                new WS2007HttpBinding(SecurityMode.None),  
                new EndpointAddress(cacheServiceAddress));  
            this.WcfSessionSecurityTokenCacheServiceClient = cf.CreateChannel();  
        }  
  
        #region SessionSecurityTokenCache Members  
        // Delegates the following operations to the centralized session security token cache service in the web farm.  
  
        ...  
  
        public override SessionSecurityToken Get(SessionSecurityTokenCacheKey key)  
        {  
            return this.WcfSessionSecurityTokenCacheServiceClient.Get(key.EndpointId, GetContextIdString(key), GetKeyGenerationString(key));  
        }  
  
        ...  
  
        #endregion  
  
        #region ICustomIdentityConfiguration Members  
        // Called from configuration infrastructure to load custom elements  
        public void LoadCustomConfiguration(XmlNodeList nodeList)  
        {  
            // Retrieve the endpoint address of the centralized session security token cache service running in the web farm  
            if (nodeList.Count == 0)  
            {  
                throw new ConfigurationException("No child config element found under <sessionSecurityTokenCache>.");  
            }  
  
            XmlElement cacheServiceAddressElement = nodeList.Item(0) as XmlElement;  
            if (cacheServiceAddressElement.LocalName != "cacheServiceAddress")  
            {  
                throw new ConfigurationException("First child config element under <sessionSecurityTokenCache> is expected to be <cacheServiceAddress>.");  
            }  
  
            string cacheServiceAddress = null;  
            if (cacheServiceAddressElement.Attributes["url"] != null)  
            {  
                cacheServiceAddress = cacheServiceAddressElement.Attributes["url"].Value;  
            }  
            else  
            {  
                throw new ConfigurationException("<cacheServiceAddress> is expected to contain a 'url' attribute.");  
            }  
  
            // Initialize the proxy to the WebFarmSessionSecurityTokenCacheService  
            this.Initialize(cacheServiceAddress);  
        }  
        #endregion  
  
        private static string GetKeyGenerationString(SessionSecurityTokenCacheKey key)  
        {  
            return key.KeyGeneration == null ? null : key.KeyGeneration.ToString();  
        }  
  
        private static string GetContextIdString(SessionSecurityTokenCacheKey key)  
        {  
            return GetContextIdString(key.ContextId);  
        }  
  
        private static string GetContextIdString(UniqueId contextId)  
        {  
            return contextId == null ? null : contextId.ToString();  
        }  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="321ce-150">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="321ce-150">See also</span></span>
- <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache>
- <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler>
- <xref:System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler>
- [<span data-ttu-id="321ce-151">Gestione delle sessioni WIF</span><span class="sxs-lookup"><span data-stu-id="321ce-151">WIF Session Management</span></span>](../../../docs/framework/security/wif-session-management.md)

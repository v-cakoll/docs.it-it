---
title: WIF e Web farm
ms.date: 03/30/2017
ms.assetid: fc3cd7fa-2b45-4614-a44f-8fa9b9d15284
author: BrucePerlerMS
ms.openlocfilehash: 09d5f3f745f170439a7fbf160b78439c103623b9
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2019
ms.locfileid: "70851526"
---
# <a name="wif-and-web-farms"></a>WIF e Web farm
Quando si usa Windows Identity Foundation (WIF) per proteggere le risorse di un'applicazione relying party (RP) distribuita in una Web farm, è necessario eseguire passaggi specifici per garantire che WIF possa elaborare i token da istanze dell'applicazione relying party in esecuzione in computer diversi nella farm. Tale elaborazione comprende la convalida delle firme dei token di sessione, la crittografia e la decrittografia dei token di sessione, la memorizzazione nella cache dei token di sessione e il rilevamento dei token di sicurezza riprodotti.  
  
 In genere, quando si usa WIF per proteggere le risorse di un'applicazione relying party, indipendentemente dal fatto che la relying party sia in esecuzione in un singolo computer o in una Web farm, viene stabilita una sessione con il client in base al token di sicurezza ottenuto dal servizio token di sicurezza. Ciò avviene per evitare di forzare il client a eseguire l'autenticazione nel servizio token di sicurezza per tutte le risorse dell'applicazione protette mediante WIF. Per altre informazioni sulla modalità di gestione delle sessioni in WIF, vedere [Gestione delle sessioni WIF](../../../docs/framework/security/wif-session-management.md).  
  
 Quando vengono usate le impostazioni predefinite, WIF esegue le operazioni seguenti:  
  
- Usa un'istanza della classe <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> per leggere e scrivere un token di sessione (un'istanza della classe <xref:System.IdentityModel.Tokens.SessionSecurityToken>) che contiene le attestazioni e altre informazioni sul token di sicurezza usato per l'autenticazione, oltre che informazioni relative alla sessione stessa. Il token di sessione viene inserito in un pacchetto e archiviato in un cookie di sessione. Per impostazione predefinita, <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> usa la classe <xref:System.IdentityModel.ProtectedDataCookieTransform>, che usa Data Protection API (DPAPI) per proteggere il token di sessione. DPAPI fornisce la protezione usando le credenziali dell'utente o del computer e archivia i dati della chiave nel profilo utente.  
  
- Usa un'implementazione in memoria predefinita della classe <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> per archiviare ed elaborare il token di sessione.  
  
 Queste impostazioni predefinite funzionano in scenari in cui l'applicazione relying party viene distribuita in un singolo computer. Se la distribuzione avviene invece in una Web farm, ogni richiesta HTTP può essere inviata a, ed elaborata da, un'istanza diversa dell'applicazione relying party in esecuzione in un computer diverso. In questo scenario le impostazioni WIF predefinite descritte in precedenza non funzionano perché sia la protezione del token che la sua memorizzazione nella cache dipendono da un computer specifico.  
  
 Per distribuire un'applicazione relying party in una Web farm, è necessario assicurarsi che l'elaborazione dei token di sessione (oltre che dei token riprodotti) non dipenda dall'esecuzione dell'applicazione in un computer specifico. A tale scopo, è possibile implementare l'applicazione relying party in modo che usi le funzionalità fornite dall'elemento di configurazione `<machineKey>` ASP.NET e fornisca la cache distribuita per l'elaborazione dei token di sessione e dei token riprodotti. L'elemento `<machineKey>` consente di specificare le chiavi necessarie per convalidare, crittografare e decrittografare i token in un file di configurazione, permettendo di specificare le stesse chiavi in computer diversi nella Web farm. WIF fornisce un gestore di token di sessione specializzato, <xref:System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler>, che protegge i token usando le chiavi specificate nell'elemento `<machineKey>`. Per implementare questa strategia, è possibile seguire queste linee guida:  
  
- Usare l'elemento `<machineKey>` ASP.NET nella configurazione per specificare in modo esplicito le chiavi di firma e di crittografia che possono essere usate tra più computer nella farm. Il codice XML seguente mostra come specificare l'elemento `<machineKey>` sotto l'elemento `<system.web>` in un file di configurazione.  
  
    ```xml  
    <machineKey compatibilityMode="Framework45" decryptionKey="CC510D … 8925E6" validationKey="BEAC8 … 6A4B1DE" />  
    ```  
  
- Configurare l'applicazione per usare <xref:System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler> aggiungendo l'oggetto alla raccolta di gestori di token. È prima necessario rimuovere <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> (o qualsiasi gestore derivato dalla classe <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler>) dalla raccolta di gestori di token, se tale gestore è presente. <xref:System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler> usa la classe <xref:System.IdentityModel.Services.MachineKeyTransform>, che protegge i dati dei cookie di sessione usando il materiale di crittografia specificato nell'elemento `<machineKey>`. Il codice XML seguente mostra come aggiungere <xref:System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler> a una raccolta di gestori di token.  
  
    ```xml  
    <securityTokenHandlers>  
      <remove type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
      <add type="System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
    </securityTokenHandlers>  
    ```  
  
- Derivare da <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> e implementare la cache distribuita, ovvero una cache accessibile da tutti i computer della farm in cui la relying party potrebbe venire eseguita. Configurare la relying party per usare la cache distribuita, specificando l'elemento [\<sessionSecurityTokenCache>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/sessionsecuritytokencache.md) nel file di configurazione. È possibile eseguire l'override del metodo <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache.LoadCustomConfiguration%2A?displayProperty=nameWithType> nella classe derivata per implementare gli elementi figlio dell'elemento `<sessionSecurityTokenCache>`, se sono necessari.  
  
    ```xml  
    <caches>  
      <sessionSecurityTokenCache type="MyCacheLibrary.MySharedSessionSecurityTokenCache, MyCacheLibrary">  
        <!--optional child configuration elements, if implemented by the derived class -->  
      </sessionSecurityTokenCache>  
    </caches>  
    ```  
  
     Un modo per implementare la cache distribuita consiste nel fornire un front-end WCF per la cache personalizzata. Per altre informazioni sull'implementazione di un servizio di caching WCF, vedere [Servizio di caching WCF](#BKMK_TheWCFCachingService). Per altre informazioni sull'implementazione di un client WCF che l'applicazione relying party può usare per chiamare il servizio di caching, vedere [Servizio di caching WCF](#BKMK_TheWCFClient).  
  
- Se l'applicazione rileva token riprodotti, è necessario seguire una strategia di cache distribuita simile per la cache di riproduzione dei token, derivando da <xref:System.IdentityModel.Tokens.TokenReplayCache> e puntando al servizio di caching di riproduzione dei token nell'elemento di configurazione [\<tokenReplayCache>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaycache.md).  
  
> [!IMPORTANT]
> Tutto il codice XML di esempio e il codice in questo argomento sono tratti dall'esempio [ClaimsAwareWebFarm](https://go.microsoft.com/fwlink/?LinkID=248408) .  
  
> [!IMPORTANT]
> Gli esempi in questo argomento vengono forniti come sono e non devono essere usati nel codice di produzione senza alcuna modifica.  
  
<a name="BKMK_TheWCFCachingService"></a>   
## <a name="the-wcf-caching-service"></a>Servizio di caching WCF  
 L'interfaccia seguente definisce il contratto tra il servizio di caching WCF e il client WCF usato dall'applicazione relying party per comunicare. Essenzialmente espone i metodi della classe <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> come operazioni del servizio.  
  
```csharp
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
  
 Il codice seguente mostra l'implementazione del servizio di caching WCF. In questo esempio viene usata la cache dei token di sessione in memoria predefinita implementata da WIF. In alternativa, è possibile implementare una cache durevole supportata da un database. `ISessionSecurityTokenCacheService` definisce l'interfaccia illustrata in precedenza. In questo esempio, per motivi di brevità, non vengono mostrati tutti i metodi necessari per implementare l'interfaccia.  
  
```csharp
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
## <a name="the-wcf-caching-client"></a>Client di memorizzazione nella cache WCF  
 Questa sezione mostra l'implementazione di una classe che deriva da <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> e che delega le chiamate al servizio di caching. L'applicazione relying party viene configurata per usare questa classe tramite l'elemento [\<sessionSecurityTokenCache>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/sessionsecuritytokencache.md), come nel codice XML seguente  
  
```xml  
<caches>  
  <sessionSecurityTokenCache type="CacheLibrary.SharedSessionSecurityTokenCache, CacheLibrary">  
    <!--cacheServiceAddress points to the centralized session security token cache service running in the web farm.-->  
    <cacheServiceAddress url="http://localhost:4161/SessionSecurityTokenCacheService.svc" />  
  </sessionSecurityTokenCache>  
</caches>  
```  
  
 La classe esegue l'override del metodo <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache.LoadCustomConfiguration%2A> per ottenere l'endpoint servizio dall'elemento figlio `<cacheServiceAddress>` personalizzato dell'elemento `<sessionSecurityTokenCache>`. Usa l'endpoint per inizializzare un canale `ISessionSecurityTokenCacheService` su cui può comunicare con il servizio.  In questo esempio, per motivi di brevità, non vengono mostrati tutti i metodi necessari per implementare la classe <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache>.  
  
```csharp
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
  
## <a name="see-also"></a>Vedere anche

- <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache>
- <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler>
- <xref:System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler>
- [Gestione delle sessioni WIF](../../../docs/framework/security/wif-session-management.md)

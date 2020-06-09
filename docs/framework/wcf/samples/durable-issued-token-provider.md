---
title: Provider di token rilasciati in modo durevole
ms.date: 03/30/2017
ms.assetid: 76fb27f5-8787-4b6a-bf4c-99b4be1d2e8b
ms.openlocfilehash: fed5f44e6cc40cfe2ca963077b6371c14b3b086a
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84600561"
---
# <a name="durable-issued-token-provider"></a><span data-ttu-id="2ca69-102">Provider di token rilasciati in modo durevole</span><span class="sxs-lookup"><span data-stu-id="2ca69-102">Durable Issued Token Provider</span></span>
<span data-ttu-id="2ca69-103">Questo esempio illustra come implementare un provider di token rilasciato del client personalizzato.</span><span class="sxs-lookup"><span data-stu-id="2ca69-103">This sample demonstrates how to implement a custom client issued token provider.</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="2ca69-104">Discussione</span><span class="sxs-lookup"><span data-stu-id="2ca69-104">Discussion</span></span>  
 <span data-ttu-id="2ca69-105">Un provider di token in Windows Communication Foundation (WCF) viene utilizzato per fornire le credenziali all'infrastruttura di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="2ca69-105">A token provider in Windows Communication Foundation (WCF) is used to supply credentials to the security infrastructure.</span></span> <span data-ttu-id="2ca69-106">In generale, il provider di token esamina la destinazione ed emette credenziali adatte in modo che l'infrastruttura di sicurezza possa proteggere il messaggio.</span><span class="sxs-lookup"><span data-stu-id="2ca69-106">The token provider in general examines the target and issues appropriate credentials so that the security infrastructure can secure the message.</span></span> <span data-ttu-id="2ca69-107">WCF viene fornito con un provider di token CardSpace.</span><span class="sxs-lookup"><span data-stu-id="2ca69-107">WCF ships with a CardSpace token provider.</span></span> <span data-ttu-id="2ca69-108">I provider di token personalizzati sono utili nei casi seguenti:</span><span class="sxs-lookup"><span data-stu-id="2ca69-108">Custom token providers are useful in the following cases:</span></span>  
  
- <span data-ttu-id="2ca69-109">Se è disponibile un archivio di credenziali con cui il provider di token incluso non è in grado di operare.</span><span class="sxs-lookup"><span data-stu-id="2ca69-109">If you have a credential store that the built-in token provider cannot operate with.</span></span>  
  
- <span data-ttu-id="2ca69-110">Se si desidera fornire un meccanismo personalizzato per la trasformazione delle credenziali dal punto in cui l'utente fornisce i dettagli su quando il client WCF usa le credenziali.</span><span class="sxs-lookup"><span data-stu-id="2ca69-110">If you want to provide your own custom mechanism for transforming the credentials from the point when the user provides the details to when the WCF client uses the credentials.</span></span>  
  
- <span data-ttu-id="2ca69-111">Se si sta compilando un token personalizzato.</span><span class="sxs-lookup"><span data-stu-id="2ca69-111">If you are building a custom token.</span></span>  
  
 <span data-ttu-id="2ca69-112">Questo esempio illustra come compilare un provider di token personalizzato che memorizza nella cache token rilasciati da un servizio token di sicurezza (STS, Security Token Service).</span><span class="sxs-lookup"><span data-stu-id="2ca69-112">This sample shows how to build a custom token provider that caches tokens issued by a Security Token Service (STS).</span></span>  
  
 <span data-ttu-id="2ca69-113">Per riassumere, questo esempio dimostra quanto segue.</span><span class="sxs-lookup"><span data-stu-id="2ca69-113">To summarize, this sample demonstrates the following:</span></span>  
  
- <span data-ttu-id="2ca69-114">Come è possibile configurare un client con un provider personalizzato.</span><span class="sxs-lookup"><span data-stu-id="2ca69-114">How a client can be configured with a custom token provider.</span></span>  
  
- <span data-ttu-id="2ca69-115">Come i token rilasciati possono essere memorizzati nella cache e forniti al client WCF.</span><span class="sxs-lookup"><span data-stu-id="2ca69-115">How issued tokens can be cached and provided to the WCF client.</span></span>  
  
- <span data-ttu-id="2ca69-116">Come viene autenticato il servizio dal client mediante il certificato X.509 del server.</span><span class="sxs-lookup"><span data-stu-id="2ca69-116">How the server is authenticated by the client using the server's X.509 certificate.</span></span>  
  
 <span data-ttu-id="2ca69-117">L'esempio è costituito da un programma console del client (Client.exe), da un programma console del servizio token di sicurezza (Securitytokenservice.exe) e da un programma console del servizio (Service.exe).</span><span class="sxs-lookup"><span data-stu-id="2ca69-117">This sample consists of a client console program (Client.exe), a security token service console program (Securitytokenservice.exe) and a service console program (Service.exe).</span></span> <span data-ttu-id="2ca69-118">Il servizio implementa un contratto che definisce un modello di comunicazione richiesta/risposta.</span><span class="sxs-lookup"><span data-stu-id="2ca69-118">The service implements a contract that defines a request-reply communication pattern.</span></span> <span data-ttu-id="2ca69-119">Il contratto è definito dall'interfaccia `ICalculator` che espone operazioni matematiche (somma, sottrazione, moltiplicazione e divisione).</span><span class="sxs-lookup"><span data-stu-id="2ca69-119">The contract is defined by the `ICalculator` interface, which exposes math operations (add, subtract, multiply, and divide).</span></span> <span data-ttu-id="2ca69-120">Il client riceve un token di sicurezza dal servizio token di sicurezza (STS), esegue richieste sincrone al servizio per un'operazione matematica specificata e il servizio risponde fornendo il risultato.</span><span class="sxs-lookup"><span data-stu-id="2ca69-120">The client gets a security token from the Security Token Service (STS) and makes synchronous requests to the service for a given math operation and the service replies with the result.</span></span> <span data-ttu-id="2ca69-121">L'attività del client è visibile nella finestra della console.</span><span class="sxs-lookup"><span data-stu-id="2ca69-121">Client activity is visible in the console window.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2ca69-122">La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="2ca69-122">The set-up procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="2ca69-123">Questo esempio espone il contratto ICalculator usando [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="2ca69-123">This sample exposes the ICalculator contract using the [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md).</span></span> <span data-ttu-id="2ca69-124">La configurazione di quest'associazione sul client viene illustrata nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="2ca69-124">The configuration of this binding on the client is shown in the following code.</span></span>  
  
```xml  
<bindings>
  <wsFederationHttpBinding>
    <binding name="ServiceFed">
      <security mode="Message">
        <message issuedKeyType="SymmetricKey"
                 issuedTokenType="http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAMLV1.1">
          <issuer address="http://localhost:8000/sts/windows"
                  binding="wsHttpBinding" />
        </message>
      </security>
    </binding>
  </wsFederationHttpBinding>
</bindings>  
```  
  
 <span data-ttu-id="2ca69-125">Nell'elemento `security` di `wsFederationHttpBinding`, il valore `mode` configura quale modalità di sicurezza deve essere utilizzata.</span><span class="sxs-lookup"><span data-stu-id="2ca69-125">On the `security` element of `wsFederationHttpBinding`, the `mode` value configures which security mode should be used.</span></span> <span data-ttu-id="2ca69-126">In questo esempio viene utilizzata la sicurezza dei messaggi; per tale motivo, l'elemento `message` di `wsFederationHttpBinding` viene specificato all'interno dell'elemento `security` di `wsFederationHttpBinding`.</span><span class="sxs-lookup"><span data-stu-id="2ca69-126">In this sample, messages security is being used, which is why the `message` element of `wsFederationHttpBinding` is specified inside the `security` element of `wsFederationHttpBinding`.</span></span> <span data-ttu-id="2ca69-127">L'elemento `issuer` di `wsFederationHttpBinding` all'interno dell'elemento `message` di `wsFederationHttpBinding` specifica l'indirizzo e l'associazione per il servizio token di sicurezza che rilascia un token di sicurezza al client, in modo che quest'ultimo possa autenticarsi presso il servizio di calcolatrice.</span><span class="sxs-lookup"><span data-stu-id="2ca69-127">The `issuer` element of `wsFederationHttpBinding` inside the `message` element of `wsFederationHttpBinding` specifies the address and binding for the Security Token Service that issues a security token to the client so that the client can authenticate to the Calculator service.</span></span>  
  
 <span data-ttu-id="2ca69-128">La configurazione di quest'associazione sul servizio viene illustrata nel seguente codice.</span><span class="sxs-lookup"><span data-stu-id="2ca69-128">The configuration of this binding on the service is shown in the following code.</span></span>  
  
```xml  
<bindings>
  <wsFederationHttpBinding>
    <binding name="ServiceFed">
      <security mode="Message">
        <message issuedKeyType="SymmetricKey"
                 issuedTokenType="http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAMLV1.1">
          <issuerMetadata address="http://localhost:8000/sts/mex">
            <identity>
              <certificateReference storeLocation="CurrentUser"
                                    storeName="TrustedPeople"
                                    x509FindType="FindBySubjectDistinguishedName"
                                    findValue="CN=STS" />
            </identity>
          </issuerMetadata>
        </message>
      </security>
    </binding>
  </wsFederationHttpBinding>
</bindings>  
```  
  
 <span data-ttu-id="2ca69-129">Nell'elemento `security` di `wsFederationHttpBinding`, il valore `mode` configura quale modalità di sicurezza deve essere utilizzata.</span><span class="sxs-lookup"><span data-stu-id="2ca69-129">On the `security` element of `wsFederationHttpBinding`, the `mode` value configures which security mode should be used.</span></span> <span data-ttu-id="2ca69-130">In questo esempio viene utilizzata la sicurezza dei messaggi; per tale motivo, l'elemento `message` di `wsFederationHttpBinding` viene specificato all'interno dell'elemento `security` di `wsFederationHttpBinding`.</span><span class="sxs-lookup"><span data-stu-id="2ca69-130">In this sample, messages security is being used, which is why the `message` element of `wsFederationHttpBinding` is specified inside the `security` element of `wsFederationHttpBinding`.</span></span> <span data-ttu-id="2ca69-131">L'elemento `issuerMetadata` di `wsFederationHttpBinding` all'interno dell'elemento `message` di `wsFederationHttpBinding` specifica l'indirizzo e l'identità di un endpoint che può essere utilizzato per recuperare metadati per il servizio token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="2ca69-131">The `issuerMetadata` element of `wsFederationHttpBinding` inside the `message` element of `wsFederationHttpBinding` specifies the address and identity for an endpoint that can be used to retrieve metadata for the Security Token Service.</span></span>  
  
 <span data-ttu-id="2ca69-132">Il comportamento per il servizio viene illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="2ca69-132">The behavior for the service is shown in the following code.</span></span>  
  
```xml  
<behavior name="ServiceBehavior">
  <serviceDebug includeExceptionDetailInFaults="true" />
  <serviceMetadata httpGetEnabled="true" />
  <serviceCredentials>
    <issuedTokenAuthentication>
      <knownCertificates>
        <add storeLocation="LocalMachine"
              storeName="TrustedPeople"
              x509FindType="FindBySubjectDistinguishedName"
              findValue="CN=STS" />
      </knownCertificates>
    </issuedTokenAuthentication>
    <serviceCertificate storeLocation="LocalMachine"
                        storeName="My"
                        x509FindType="FindBySubjectDistinguishedName"
                        findValue="CN=localhost" />
  </serviceCredentials>
</behavior>  
```  
  
 <span data-ttu-id="2ca69-133">L'elemento `issuedTokenAuthentication` all'interno dell'elemento `serviceCredentials` consente al servizio di specificare i vincoli nei token che i client possono presentare durante l'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="2ca69-133">The `issuedTokenAuthentication` element inside the `serviceCredentials` element allows the service to specify constraints on the tokens it allows clients to present during authentication.</span></span> <span data-ttu-id="2ca69-134">Questa configurazione specifica che i token firmati da un certificato il cui Nome soggetto è CN=STS possono essere accettati dal servizio.</span><span class="sxs-lookup"><span data-stu-id="2ca69-134">This configuration specifies that tokens signed by a certificate whose Subject Name is CN=STS are accepted by the service.</span></span>  
  
 <span data-ttu-id="2ca69-135">Il servizio token di sicurezza espone un solo endpoint utilizzando l'elemento wsHttpBinding standard.</span><span class="sxs-lookup"><span data-stu-id="2ca69-135">The Security Token Service exposes a single endpoint using the standard wsHttpBinding.</span></span> <span data-ttu-id="2ca69-136">Il servizio token di sicurezza risponde alle richieste di token dei client e, se il client si autentica utilizzando un account di Windows, emette un token che contiene il nome utente del client come attestazione nel token emesso.</span><span class="sxs-lookup"><span data-stu-id="2ca69-136">The Security Token Service responds to request from clients for tokens and, provided the client authenticates using a Windows account, issues a token that contains the client's user name as a claim in the issued token.</span></span> <span data-ttu-id="2ca69-137">Come parte del processo di creazione del token, il servizio token di protezione firma il token utilizzando la chiave privata associata al certificato CN=STS .</span><span class="sxs-lookup"><span data-stu-id="2ca69-137">As part of creating the token, the Security Token Service signs the token using the private key associated with the CN=STS certificate.</span></span> <span data-ttu-id="2ca69-138">Crea, inoltre, una chiave simmetrica e la crittografa utilizzando la chiave pubblica associata al certificato CN=localhost.</span><span class="sxs-lookup"><span data-stu-id="2ca69-138">In addition, it creates a symmetric key and encrypts it using the public key associated with the CN=localhost certificate.</span></span> <span data-ttu-id="2ca69-139">Nel restituire il token al client, il servizio token di protezione restituisce anche la chiave simmetrica.</span><span class="sxs-lookup"><span data-stu-id="2ca69-139">In returning the token to the client, the Security Token Service also returns the symmetric key.</span></span> <span data-ttu-id="2ca69-140">Il client presenta il token emesso al servizio di calcolatrice e dimostra che conosce la chiave simmetrica firmando il messaggio con quella chiave.</span><span class="sxs-lookup"><span data-stu-id="2ca69-140">The client presents the issued token to the Calculator service, and proves that it knows the symmetric key by signing the message with that key.</span></span>  
  
## <a name="custom-client-credentials-and-token-provider"></a><span data-ttu-id="2ca69-141">Credenziali client e servizio token di protezione personalizzati</span><span class="sxs-lookup"><span data-stu-id="2ca69-141">Custom Client Credentials and Token Provider</span></span>  
 <span data-ttu-id="2ca69-142">Nei passaggi seguenti viene illustrato come sviluppare un provider di token personalizzato che memorizza nella cache i token rilasciati e li integra con WCF: Security.</span><span class="sxs-lookup"><span data-stu-id="2ca69-142">The following steps show how to develop a custom token provider that caches issued tokens and integrate it with WCF: security.</span></span>  
  
### <a name="to-develop-a-custom-token-provider"></a><span data-ttu-id="2ca69-143">Per sviluppare un provider di token personalizzato</span><span class="sxs-lookup"><span data-stu-id="2ca69-143">To develop a custom token provider</span></span>  
  
1. <span data-ttu-id="2ca69-144">Scrivere un provider di token personalizzati.</span><span class="sxs-lookup"><span data-stu-id="2ca69-144">Write a custom token provider.</span></span>  
  
     <span data-ttu-id="2ca69-145">L'esempio implementa un provider di token personalizzato che restituisce un token di sicurezza recuperato da una cache.</span><span class="sxs-lookup"><span data-stu-id="2ca69-145">The sample implements a custom token provider that returns a security token retrieved from a cache.</span></span>  
  
     <span data-ttu-id="2ca69-146">Per eseguire questa attività il provider di token personalizzato deriva dalla classe <xref:System.IdentityModel.Selectors.SecurityTokenProvider> ed esegue l'override del metodo <xref:System.IdentityModel.Selectors.SecurityTokenProvider.GetTokenCore%2A>.</span><span class="sxs-lookup"><span data-stu-id="2ca69-146">To perform this task, the custom token provider derives the <xref:System.IdentityModel.Selectors.SecurityTokenProvider> class and overrides the <xref:System.IdentityModel.Selectors.SecurityTokenProvider.GetTokenCore%2A> method.</span></span> <span data-ttu-id="2ca69-147">Questo metodo tenta di ottenere un token dalla cache o, se non è possibile trovare un token nella cache, recupera un token dal provider sottostante e quindi lo memorizza nella cache.</span><span class="sxs-lookup"><span data-stu-id="2ca69-147">This method tries to get a token from the cache, or if a token cannot be found in the cache, retrieves a token from the underlying provider and then caches that token.</span></span> <span data-ttu-id="2ca69-148">In entrambi i casi, il metodo restituisce `SecurityToken`.</span><span class="sxs-lookup"><span data-stu-id="2ca69-148">In both cases the method returns a `SecurityToken`.</span></span>  
  
    ```csharp  
    protected override SecurityToken GetTokenCore(TimeSpan timeout)  
    {  
      GenericXmlSecurityToken token;  
      if (!this.cache.TryGetToken(target, issuer, out token))  
      {  
        token = (GenericXmlSecurityToken) this.innerTokenProvider.GetToken(timeout);  
        this.cache.AddToken(token, target, issuer);  
      }  
      return token;  
    }  
    ```  
  
2. <span data-ttu-id="2ca69-149">Scrivere il gestore di token di sicurezza personalizzato.</span><span class="sxs-lookup"><span data-stu-id="2ca69-149">Write custom security token manager.</span></span>  
  
     <span data-ttu-id="2ca69-150">La classe <xref:System.IdentityModel.Selectors.SecurityTokenManager> viene utilizzata per creare un <xref:System.IdentityModel.Selectors.SecurityTokenProvider> per un <xref:System.IdentityModel.Selectors.SecurityTokenRequirement> specifico che viene passato nel metodo `CreateSecurityTokenProvider`.</span><span class="sxs-lookup"><span data-stu-id="2ca69-150">The <xref:System.IdentityModel.Selectors.SecurityTokenManager> is used to create a <xref:System.IdentityModel.Selectors.SecurityTokenProvider> for a specific <xref:System.IdentityModel.Selectors.SecurityTokenRequirement> that is passed to it in the `CreateSecurityTokenProvider` method.</span></span> <span data-ttu-id="2ca69-151">Viene inoltre utilizzato un gestore del token di sicurezza per creare autenticatori del token e serializzatori del token, che però non vengono presi in esame in questo esempio.</span><span class="sxs-lookup"><span data-stu-id="2ca69-151">Security token manager is also used to create token authenticators and token serializers, but those are not covered by this sample.</span></span> <span data-ttu-id="2ca69-152">Nell'esempio, il gestore del token di sicurezza eredita dalla classe <xref:System.ServiceModel.ClientCredentialsSecurityTokenManager> ed esegue l'override del metodo `CreateSecurityTokenProvider` per restituire il provider di token personalizzato quando i requisiti del token passati indicano che viene richiesto un token emesso.</span><span class="sxs-lookup"><span data-stu-id="2ca69-152">In this sample, the custom security token manager inherits from the <xref:System.ServiceModel.ClientCredentialsSecurityTokenManager> class and overrides the `CreateSecurityTokenProvider` method to return the custom token provider when the passed token requirements indicate that an issued token is requested.</span></span>  
  
    ```csharp
    class DurableIssuedTokenClientCredentialsTokenManager :  
     ClientCredentialsSecurityTokenManager  
    {  
      IssuedTokenCache cache;  
  
      public DurableIssuedTokenClientCredentialsTokenManager ( DurableIssuedTokenClientCredentials creds ): base(creds)  
      {  
        this.cache = creds.IssuedTokenCache;  
      }  
  
      public override SecurityTokenProvider CreateSecurityTokenProvider ( SecurityTokenRequirement tokenRequirement )  
      {  
        if (IsIssuedSecurityTokenRequirement(tokenRequirement))  
        {  
          return new DurableIssuedSecurityTokenProvider ((IssuedSecurityTokenProvider)base.CreateSecurityTokenProvider( tokenRequirement), this.cache);  
        }  
        else
        {  
          return base.CreateSecurityTokenProvider(tokenRequirement);  
        }  
      }  
    }  
    ```  
  
3. <span data-ttu-id="2ca69-153">Scrivere una credenziale client personalizzata.</span><span class="sxs-lookup"><span data-stu-id="2ca69-153">Write a custom client credential.</span></span>  
  
     <span data-ttu-id="2ca69-154">La classe delle credenziali di un client viene utilizzata per rappresentare le credenziali configurate per il proxy client e crea il gestore del token di protezione utilizzato per ottenere gli autenticatori del token, i provider di token e i serializzatori di token.</span><span class="sxs-lookup"><span data-stu-id="2ca69-154">A client credentials class is used to represent the credentials that are configured for the client proxy and creates the security token manager that is used to obtain token authenticators, token providers and token serializers.</span></span>  
  
    ```csharp
    public class DurableIssuedTokenClientCredentials : ClientCredentials  
    {  
      IssuedTokenCache cache;  
  
      public DurableIssuedTokenClientCredentials() : base()  
      {  
      }  
  
      DurableIssuedTokenClientCredentials ( DurableIssuedTokenClientCredentials other) : base(other)  
      {  
        this.cache = other.cache;  
      }  
  
      public IssuedTokenCache IssuedTokenCache  
      {  
        get  
        {  
          return this.cache;  
        }  
        set  
        {  
          this.cache = value;  
        }  
      }  
  
      protected override ClientCredentials CloneCore()  
      {  
        return new DurableIssuedTokenClientCredentials(this);  
      }  
  
      public override SecurityTokenManager CreateSecurityTokenManager()  
      {  
        return new DurableIssuedTokenClientCredentialsTokenManager ((DurableIssuedTokenClientCredentials)this.Clone());  
      }  
    }  
    ```  
  
4. <span data-ttu-id="2ca69-155">Implementare la cache del token.</span><span class="sxs-lookup"><span data-stu-id="2ca69-155">Implement the token cache.</span></span> <span data-ttu-id="2ca69-156">L'implementazione di esempio utilizza una classe di base astratta tramite la quale utenti di una cache del token specificata interagiscono con la cache.</span><span class="sxs-lookup"><span data-stu-id="2ca69-156">The sample implementation uses an abstract base class through which consumers of a given token cache interact with the cache.</span></span>  
  
    ```csharp
    public abstract class IssuedTokenCache  
    {  
      public abstract void AddToken ( GenericXmlSecurityToken token, EndpointAddress target, EndpointAddress issuer);  
      public abstract bool TryGetToken(EndpointAddress target, EndpointAddress issuer, out GenericXmlSecurityToken cachedToken);  
    }  
    // Configure the client to use the custom client credential.  
    ```  
  
     <span data-ttu-id="2ca69-157">L'esempio elimina la classe della credenziale client predefinita e fornisce la nuova classe della credenziale client affinché il client possa utilizzare la credenziale client personalizzata.</span><span class="sxs-lookup"><span data-stu-id="2ca69-157">For the client to use the custom client credential, the sample deletes the default client credential class and supplies the new client credential class.</span></span>  
  
    ```csharp
    clientFactory.Endpoint.Behaviors.Remove<ClientCredentials>();  
    DurableIssuedTokenClientCredentials durableCreds = new DurableIssuedTokenClientCredentials();  
    durableCreds.IssuedTokenCache = cache;  
    durableCreds.ServiceCertificate.Authentication.CertificateValidationMode = X509CertificateValidationMode.PeerOrChainTrust;  
    clientFactory.Endpoint.Behaviors.Add(durableCreds);  
    ```  
  
## <a name="running-the-sample"></a><span data-ttu-id="2ca69-158">Esecuzione dell'esempio</span><span class="sxs-lookup"><span data-stu-id="2ca69-158">Running the sample</span></span>  
 <span data-ttu-id="2ca69-159">Per eseguire l'esempio seguire le istruzioni riportate qui.</span><span class="sxs-lookup"><span data-stu-id="2ca69-159">See the following instructions to run the sample.</span></span> <span data-ttu-id="2ca69-160">Quando si esegue l'esempio, la richiesta per il token di protezione viene visualizzata nella finestra della console del servizio token di protezione.</span><span class="sxs-lookup"><span data-stu-id="2ca69-160">When you run the sample, the request for the security token is shown in the Security Token Service console window.</span></span> <span data-ttu-id="2ca69-161">Le richieste e le risposte dell'operazione vengono visualizzate nella finestra della console del client e del servizio.</span><span class="sxs-lookup"><span data-stu-id="2ca69-161">The operation requests and responses are displayed in the client and service console windows.</span></span> <span data-ttu-id="2ca69-162">Premere INVIO in una delle finestre della console per arrestare l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="2ca69-162">Press ENTER in any of the console windows to shut down the application.</span></span>  
  
## <a name="the-setupcmd-batch-file"></a><span data-ttu-id="2ca69-163">File batch Setup.cmd</span><span class="sxs-lookup"><span data-stu-id="2ca69-163">The Setup.cmd Batch File</span></span>  
 <span data-ttu-id="2ca69-164">Il file batch Setup.cmd incluso con questo esempio consente di configurare il server e il servizio token di sicurezza con i certificati attinenti per eseguire un'applicazione indipendente.</span><span class="sxs-lookup"><span data-stu-id="2ca69-164">The Setup.cmd batch file included with this sample allows you to configure the server and security token service with relevant certificates to run a self-hosted application.</span></span> <span data-ttu-id="2ca69-165">Il file batch crea due certificati, entrambi nell'archivio certificati di CurrentUser/TrustedPeople.</span><span class="sxs-lookup"><span data-stu-id="2ca69-165">The batch file creates two certificates both in the CurrentUser/TrustedPeople certificate store.</span></span> <span data-ttu-id="2ca69-166">Il primo certificato ha un nome soggetto di CN=STS e viene utilizzato dal servizio token di protezione per firmare i token di protezione emessi al client.</span><span class="sxs-lookup"><span data-stu-id="2ca69-166">The first certificate has a subject name of CN=STS and is used by the Security Token Service to sign the security tokens that it issues to the client.</span></span> <span data-ttu-id="2ca69-167">Il secondo certificato ha un nome soggetto di CN=localhost e viene utilizzato dal servizio token di sicurezza per crittografare un segreto in modo che il servizio non possa decrittografarlo.</span><span class="sxs-lookup"><span data-stu-id="2ca69-167">The second certificate has a subject name of CN=localhost and is used by the Security Token Service to encrypt a secret so that the service can decrypt it.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="2ca69-168">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="2ca69-168">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="2ca69-169">Eseguire il file Setup.cmd per creare i certificati richiesti.</span><span class="sxs-lookup"><span data-stu-id="2ca69-169">Run the Setup.cmd file to create the required certificates.</span></span>  
  
2. <span data-ttu-id="2ca69-170">Per compilare la soluzione, seguire le istruzioni riportate in [compilazione degli esempi di Windows Communication Foundation](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="2ca69-170">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span> <span data-ttu-id="2ca69-171">Assicurarsi che tutti i progetti nella soluzione siano stati generati  (Shared, RSTRSTR, Service, SecurityTokenService e Client).</span><span class="sxs-lookup"><span data-stu-id="2ca69-171">Ensure that all the projects in the solution are built (Shared, RSTRSTR, Service, SecurityTokenService, and Client).</span></span>  
  
3. <span data-ttu-id="2ca69-172">Assicurarsi che Service.exe e SecurityTokenService.exe siano entrambi in esecuzione con privilegi di amministratore.</span><span class="sxs-lookup"><span data-stu-id="2ca69-172">Ensure that Service.exe and SecurityTokenService.exe are both running with administrator privileges.</span></span>  
  
4. <span data-ttu-id="2ca69-173">Eseguire Client.exe.</span><span class="sxs-lookup"><span data-stu-id="2ca69-173">Run Client.exe.</span></span>  
  
### <a name="to-clean-up-after-the-sample"></a><span data-ttu-id="2ca69-174">Per eseguire la pulizia dopo l'esempio</span><span class="sxs-lookup"><span data-stu-id="2ca69-174">To clean up after the sample</span></span>  
  
1. <span data-ttu-id="2ca69-175">Eseguire Cleanup.cmd nella cartella degli esempi una volta completato l'esempio.</span><span class="sxs-lookup"><span data-stu-id="2ca69-175">Run Cleanup.cmd in the samples folder once you have finished running the sample.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="2ca69-176">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="2ca69-176">The samples may already be installed on your machine.</span></span> <span data-ttu-id="2ca69-177">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="2ca69-177">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="2ca69-178">Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti i Windows Communication Foundation (WCF) ed [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="2ca69-178">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="2ca69-179">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="2ca69-179">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Security\DurableIssuedTokenProvider`  

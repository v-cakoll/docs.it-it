---
title: Federazione
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, federation
- federation [WCF]
ms.assetid: 2f1e646f-8361-48d4-9d5d-1b961f31ede4
ms.openlocfilehash: 9616a5afb88e46bb5d69f1cd253c854cc1684d9f
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/16/2020
ms.locfileid: "81464177"
---
# <a name="federation"></a><span data-ttu-id="7b01c-102">Federazione</span><span class="sxs-lookup"><span data-stu-id="7b01c-102">Federation</span></span>
<span data-ttu-id="7b01c-103">In questo argomento viene illustrato brevemente il concetto di sicurezza federata.</span><span class="sxs-lookup"><span data-stu-id="7b01c-103">This topic provides a brief overview of the concept of federated security.</span></span> <span data-ttu-id="7b01c-104">Viene inoltre descritto il supporto di Windows Communication Foundation (WCF) per la distribuzione di architetture di sicurezza federate.</span><span class="sxs-lookup"><span data-stu-id="7b01c-104">It also describes Windows Communication Foundation (WCF) support for deploying federated security architectures.</span></span> <span data-ttu-id="7b01c-105">Per un'applicazione di esempio che illustra la federazione, vedere [Esempio di federazione](../../../../docs/framework/wcf/samples/federation-sample.md).</span><span class="sxs-lookup"><span data-stu-id="7b01c-105">For a sample application that demonstrates federation, see [Federation Sample](../../../../docs/framework/wcf/samples/federation-sample.md).</span></span>  
  
## <a name="definition-of-federated-security"></a><span data-ttu-id="7b01c-106">Definizione di sicurezza federata</span><span class="sxs-lookup"><span data-stu-id="7b01c-106">Definition of Federated Security</span></span>  
 <span data-ttu-id="7b01c-107">La protezione federata consente di separare con precisione il servizio al quale sta accedendo un client dalle procedure pertinenti di autenticazione e di autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="7b01c-107">Federated security allows for clean separation between the service a client is accessing and the associated authentication and authorization procedures.</span></span> <span data-ttu-id="7b01c-108">La protezione federata consente inoltre la collaborazione attraverso più sistemi, reti e organizzazioni in diverse aree di attendibilità.</span><span class="sxs-lookup"><span data-stu-id="7b01c-108">Federated security also enables collaboration across multiple systems, networks, and organizations in different trust realms.</span></span>  
  
 <span data-ttu-id="7b01c-109">WCF fornisce supporto per la compilazione e la distribuzione di sistemi distribuiti che utilizzano la sicurezza federata.</span><span class="sxs-lookup"><span data-stu-id="7b01c-109">WCF provides support for building and deploying distributed systems that employ federated security.</span></span>  
  
### <a name="elements-of-a-federated-security-architecture"></a><span data-ttu-id="7b01c-110">Elementi di un'architettura di sicurezza federata</span><span class="sxs-lookup"><span data-stu-id="7b01c-110">Elements of a Federated Security Architecture</span></span>  
 <span data-ttu-id="7b01c-111">L'architettura di sicurezza federata è composta da tre elementi principali, come descritto nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="7b01c-111">The federated security architecture has three key elements, as described in the following table.</span></span>  
  
|<span data-ttu-id="7b01c-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="7b01c-112">Element</span></span>|<span data-ttu-id="7b01c-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7b01c-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7b01c-114">Dominio/area</span><span class="sxs-lookup"><span data-stu-id="7b01c-114">Domain/realm</span></span>|<span data-ttu-id="7b01c-115">Una singola unità di amministrazione di sicurezza o attendibilità.</span><span class="sxs-lookup"><span data-stu-id="7b01c-115">A single unit of security administration or trust.</span></span> <span data-ttu-id="7b01c-116">Un dominio tipico potrebbe includere una sola organizzazione.</span><span class="sxs-lookup"><span data-stu-id="7b01c-116">A typical domain might include a single organization.</span></span>|  
|<span data-ttu-id="7b01c-117">Federazione</span><span class="sxs-lookup"><span data-stu-id="7b01c-117">Federation</span></span>|<span data-ttu-id="7b01c-118">Una raccolta di domini che hanno stabilito una relazione di trust.</span><span class="sxs-lookup"><span data-stu-id="7b01c-118">A collection of domains that have established trust.</span></span> <span data-ttu-id="7b01c-119">Il livello di attendibilità può variare, ma in genere include l'autenticazione e quasi sempre l'autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="7b01c-119">The level of trust may vary, but typically includes authentication and almost always includes authorization.</span></span> <span data-ttu-id="7b01c-120">Una federazione tipica può includere numerose organizzazioni che hanno stabilito una relazione di trust per l'accesso condiviso per un set di risorse.</span><span class="sxs-lookup"><span data-stu-id="7b01c-120">A typical federation might include a number of organizations that have established trust for shared access to a set of resources.</span></span>|  
|<span data-ttu-id="7b01c-121">Servizio Token di sicurezza (STS, Security Token Service)</span><span class="sxs-lookup"><span data-stu-id="7b01c-121">Security Token Service (STS)</span></span>|<span data-ttu-id="7b01c-122">Servizio Web che rilascia token di sicurezza, ovvero, fa asserzioni basate su evidenze che considera attendibili, a chiunque lo consideri attendibile.</span><span class="sxs-lookup"><span data-stu-id="7b01c-122">A Web service that issues security tokens; that is, it makes assertions based on evidence that it trusts, to whomever trusts it.</span></span> <span data-ttu-id="7b01c-123">Questa è la base della negoziazione di attendibilità tra domini.</span><span class="sxs-lookup"><span data-stu-id="7b01c-123">This forms the basis of trust brokering between domains.</span></span>|  
  
### <a name="example-scenario"></a><span data-ttu-id="7b01c-124">Scenario di esempio</span><span class="sxs-lookup"><span data-stu-id="7b01c-124">Example Scenario</span></span>  
 <span data-ttu-id="7b01c-125">Nella figura seguente viene illustrato un esempio di sicurezza federata:The following illustration shows an example of federated security:</span><span class="sxs-lookup"><span data-stu-id="7b01c-125">The following illustration shows an example of federated security:</span></span>  
  
 ![Diagramma che mostra uno scenario di sicurezza federato tipico.](./media/federation/typical-federated-security-scenario.gif)  
  
 <span data-ttu-id="7b01c-127">In questo scenario sono incluse due organizzazioni: A e B. L'organizzazione B ha una risorsa Web (un servizio Web) che alcuni utenti dell'organizzazione A ritengono preziosa.</span><span class="sxs-lookup"><span data-stu-id="7b01c-127">This scenario includes two organizations: A and B. Organization B has a Web resource (a Web service) that some users in organization A find valuable.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7b01c-128">In questa sezione vengono utilizzati i termini *resource*, *service*e *Web service* in modo intercambiabile.</span><span class="sxs-lookup"><span data-stu-id="7b01c-128">This section uses the terms *resource*, *service*, and *Web service* interchangeably.</span></span>  
  
 <span data-ttu-id="7b01c-129">L'organizzazione B richiede in genere che un utente dell'organizzazione A fornisca un tipo valido di autenticazione prima di accedere al servizio.</span><span class="sxs-lookup"><span data-stu-id="7b01c-129">Typically, organization B requires that a user from organization A provide some valid form of authentication before accessing the service.</span></span> <span data-ttu-id="7b01c-130">Potrebbe inoltre richiedere che l'utente venga autorizzato ad accedere alla risorsa specifica in questione.</span><span class="sxs-lookup"><span data-stu-id="7b01c-130">In addition, the organization may also require that the user be authorized to access the specific resource in question.</span></span> <span data-ttu-id="7b01c-131">Un modo per risolvere questo problema e consentire agli utenti dell'organizzazione A di accedere alla risorsa nell'organizzazione B è il seguente:</span><span class="sxs-lookup"><span data-stu-id="7b01c-131">One way to address this problem and enable users in organization A to access the resource in organization B is as follows:</span></span>  
  
- <span data-ttu-id="7b01c-132">Gli utenti dell'organizzazione A registrano le proprie credenziali (un nome utente e una password) presso l'organizzazione B.</span><span class="sxs-lookup"><span data-stu-id="7b01c-132">Users from organization A register their credentials (a user name and password) with organization B.</span></span>  
  
- <span data-ttu-id="7b01c-133">Durante l'accesso alla risorsa, gli utenti dell'organizzazione A presentano le proprie credenziali all'organizzazione B e vengono autenticati prima di accedere alla risorsa.</span><span class="sxs-lookup"><span data-stu-id="7b01c-133">During the resource access, users from organization A present their credentials to organization B and are authenticated before accessing the resource.</span></span>  
  
 <span data-ttu-id="7b01c-134">Questo approccio ha tre grandi inconvenienti:</span><span class="sxs-lookup"><span data-stu-id="7b01c-134">This approach has three significant drawbacks:</span></span>  
  
- <span data-ttu-id="7b01c-135">L'organizzazione B deve gestire le credenziali degli utenti dell'organizzazione A, oltre a quelle dei propri utenti locali.</span><span class="sxs-lookup"><span data-stu-id="7b01c-135">Organization B has to manage the credentials for users from organization A in addition to managing the credentials of its local users.</span></span>  
  
- <span data-ttu-id="7b01c-136">Gli utenti dell'organizzazione A devono mantenere un set aggiuntivo di credenziali (ovvero, ricordare un nome utente e una password in più), oltre a quelle normalmente utilizzate per accedere alle risorse all'interno dell'organizzazione A. Ciò incoraggia la pratica dell'utilizzo dello stesso nome utente e della stessa password in più siti del servizio, il che non è una misura efficace di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="7b01c-136">Users in organization A need to maintain an additional set of credentials (that is, remember an additional user name and password) apart from the credentials they normally use to gain access to resources within organization A. This usually encourages the practice of using the same user name and password at multiple service sites, which is a weak security measure.</span></span>  
  
- <span data-ttu-id="7b01c-137">L'architettura non si adatta, in quanto più organizzazioni percepiscono la risorsa dell'organizzazione B come di un qualche valore.</span><span class="sxs-lookup"><span data-stu-id="7b01c-137">The architecture does not scale as more organizations perceive the resource at organization B as being of some value.</span></span>  
  
 <span data-ttu-id="7b01c-138">Un approccio alternativo, che risolve gli inconvenienti menzionati in precedenza, consiste nell'utilizzare la protezione federata.</span><span class="sxs-lookup"><span data-stu-id="7b01c-138">An alternative approach, which addresses the previously mentioned drawbacks, is to employ federated security.</span></span> <span data-ttu-id="7b01c-139">In questo approccio, le organizzazioni A e B stabiliscono una relazione di trust e utilizzano il servizio token di sicurezza (STS, Security Token Service) per consentire la negoziazione della relazione di trust stabilita.</span><span class="sxs-lookup"><span data-stu-id="7b01c-139">In this approach, organizations A and B establish a trust relationship and employ Security Token Service (STS) to enable brokering of the established trust.</span></span>  
  
 <span data-ttu-id="7b01c-140">In un'architettura di sicurezza federata, gli utenti dell'organizzazione A sanno che se vogliono accedere al servizio Web dell'organizzazione B devono presentare un token di sicurezza valido dall'STS dell'organizzazione B, che autentica e autorizza il loro accesso al servizio specifico.</span><span class="sxs-lookup"><span data-stu-id="7b01c-140">In a federated security architecture, users from organization A know that if they want to access the Web service in organization B that they must present a valid security token from the STS at organization B, which authenticates and authorizes their access to the specific service.</span></span>  
  
 <span data-ttu-id="7b01c-141">Quando contattano l'STS B, gli utenti ricevono un altro livello di riferimento indiretto dal criterio associato a STS.</span><span class="sxs-lookup"><span data-stu-id="7b01c-141">On contacting the STS B, the users receive another level of indirection from the policy associated with the STS.</span></span> <span data-ttu-id="7b01c-142">Devono presentare un token di sicurezza valido da STS A (ovvero, l'area di attendibilità del client) prima che STS B possa rilasciare loro un token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="7b01c-142">They must present a valid security token from the STS A (that is, the client trust realm) before the STS B can issue them a security token.</span></span> <span data-ttu-id="7b01c-143">Si tratta di un corollario della relazione di trust stabilita tra le due organizzazioni e implica che l'organizzazione B non deve gestire le identità degli utenti dell'organizzazione A. In pratica, STS B in genere ha `issuerAddress` e `issuerMetadataAddress` nulli.</span><span class="sxs-lookup"><span data-stu-id="7b01c-143">This is a corollary of the trust relationship established between the two organizations and implies that organization B does not have to manage identities for users from organization A. In practice, STS B typically has a null `issuerAddress` and `issuerMetadataAddress`.</span></span> <span data-ttu-id="7b01c-144">Per ulteriori informazioni, vedere [Procedura: Configurare un'autorità di certificazione locale](../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md).</span><span class="sxs-lookup"><span data-stu-id="7b01c-144">For more information, see [How to: Configure a Local Issuer](../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md).</span></span> <span data-ttu-id="7b01c-145">In tal caso, il client consulta un criterio locale per individuare il servizio token di protezione A. Questa configurazione è denominata *federazione dell'area di autenticazione principale* e viene ridimensionata meglio perché il servizio token di sicurezza B non deve mantenere le informazioni sul servizio token di sicurezza A.</span><span class="sxs-lookup"><span data-stu-id="7b01c-145">In that case, the client consults a local policy to locate STS A. This configuration is called *home realm federation* and it scales better because STS B does not have to maintain information about STS A.</span></span>  
  
 <span data-ttu-id="7b01c-146">Gli utenti contattano quindi l'STS dell'organizzazione A e ottengono un token di sicurezza presentando le credenziali di autenticazione che utilizzano normalmente per accedere a qualsiasi altra risorsa all'interno dell'organizzazione A. In tal modo, si evita loro di dover conservare più set di credenziali o utilizzare lo stesso set di credenziali in più siti del servizio.</span><span class="sxs-lookup"><span data-stu-id="7b01c-146">The users then contact the STS at organization A and obtain a security token by presenting authentication credentials that they normally use to gain access to any other resource within organization A. This also alleviates the problem of users having to maintain multiple sets of credentials or using the same set of credentials at multiple service sites.</span></span>  
  
 <span data-ttu-id="7b01c-147">Una volta ottenuto un token di sicurezza da STS A, gli utenti lo presentano a STS B. L'organizzazione B procede per eseguire l'autorizzazione delle richieste degli utenti e rilascia loro un token di sicurezza preso dal proprio set di token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="7b01c-147">Once the users obtain a security token from the STS A, they present the token to the STS B. Organization B proceeds to perform authorization of the users' requests and issues a security token to the users from its own set of security tokens.</span></span> <span data-ttu-id="7b01c-148">Gli utenti possono presentare quindi il proprio token alla risorsa dell'organizzazione B e accedere al servizio.</span><span class="sxs-lookup"><span data-stu-id="7b01c-148">The users can then present their token to the resource at organization B and access the service.</span></span>  
  
## <a name="support-for-federated-security-in-wcf"></a><span data-ttu-id="7b01c-149">Supporto per la protezione federata in WCF</span><span class="sxs-lookup"><span data-stu-id="7b01c-149">Support for Federated Security in WCF</span></span>  
 <span data-ttu-id="7b01c-150">WCF fornisce il supporto chiavi in funzione per la distribuzione di architetture di sicurezza federate tramite [ \<wsFederationHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="7b01c-150">WCF provides turnkey support for deploying federated security architectures through the [\<wsFederationHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md).</span></span>  
  
 <span data-ttu-id="7b01c-151">Il [ \<>wsFederationHttpBinding>elemento](../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) fornisce un'associazione sicura, affidabile e interoperabile che comporta l'utilizzo di HTTP come meccanismo di trasporto sottostante per lo stile di comunicazione richiesta-risposta, utilizzando testo e XML come formato wire per la codifica.</span><span class="sxs-lookup"><span data-stu-id="7b01c-151">The [\<wsFederationHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) element provides for a secure, reliable, interoperable binding that entails the use of HTTP as the underlying transport mechanism for request-reply communication style, employing text and XML as the wire format for encoding.</span></span>  
  
 <span data-ttu-id="7b01c-152">L'utilizzo di [ \<wsFederationHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) in uno scenario di sicurezza federata può essere disaccoppiato in due fasi logicamente indipendenti, come descritto nelle sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="7b01c-152">The use of [\<wsFederationHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) in a federated security scenario can be decoupled into two logically independent phases, as described in the following sections.</span></span>  
  
### <a name="phase-1-design-phase"></a><span data-ttu-id="7b01c-153">Fase 1: Progettazione</span><span class="sxs-lookup"><span data-stu-id="7b01c-153">Phase 1: Design Phase</span></span>  
 <span data-ttu-id="7b01c-154">Durante la fase di progettazione, il client utilizza lo [strumento ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) per leggere i criteri esposti dall'endpoint del servizio e per raccogliere i requisiti di autenticazione e autorizzazione del servizio.</span><span class="sxs-lookup"><span data-stu-id="7b01c-154">During the design phase, the client uses the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) to read the policy the service endpoint exposes and to collect the service's authentication and authorization requirements.</span></span> <span data-ttu-id="7b01c-155">Vengono costruiti proxy adatti per creare il modello di comunicazione di sicurezza federata seguente nel client:</span><span class="sxs-lookup"><span data-stu-id="7b01c-155">The appropriate proxies are constructed to create the following federated security communication pattern at the client:</span></span>  
  
- <span data-ttu-id="7b01c-156">Ottenere un token di sicurezza da STS nell'area di attendibilità del client.</span><span class="sxs-lookup"><span data-stu-id="7b01c-156">Obtain a security token from the STS in the client trust realm.</span></span>  
  
- <span data-ttu-id="7b01c-157">Presentare il token a STS nell'area di attendibilità del servizio.</span><span class="sxs-lookup"><span data-stu-id="7b01c-157">Present the token to the STS in the service trust realm.</span></span>  
  
- <span data-ttu-id="7b01c-158">Ottenere un token di sicurezza da STS nell'area di attendibilità del servizio.</span><span class="sxs-lookup"><span data-stu-id="7b01c-158">Obtain a security token from the STS in the service trust realm.</span></span>  
  
- <span data-ttu-id="7b01c-159">Presentare il token al servizio per accedere ad esso.</span><span class="sxs-lookup"><span data-stu-id="7b01c-159">Present the token to the service to access the service.</span></span>  
  
### <a name="phase-2-run-time-phase"></a><span data-ttu-id="7b01c-160">Fase 2: Runtime</span><span class="sxs-lookup"><span data-stu-id="7b01c-160">Phase 2: Run-Time Phase</span></span>  
 <span data-ttu-id="7b01c-161">Durante la fase di runtime, il client crea un'istanza di un oggetto della classe client WCF ed effettua una chiamata utilizzando il client WCF.</span><span class="sxs-lookup"><span data-stu-id="7b01c-161">During the run-time phase, the client instantiates an object of the WCF client class and makes a call using the WCF client.</span></span> <span data-ttu-id="7b01c-162">Il framework sottostante di WCF gestisce i passaggi menzionati in precedenza nel modello di comunicazione di sicurezza federata e consente al client di utilizzare senza problemi il servizio.</span><span class="sxs-lookup"><span data-stu-id="7b01c-162">The underlying framework of WCF handles the previously mentioned steps in the federated security communication pattern and enables the client to seamlessly consume the service.</span></span>  
  
## <a name="sample-implementation-using-wcf"></a><span data-ttu-id="7b01c-163">Implementazione di esempio utilizzando WCF</span><span class="sxs-lookup"><span data-stu-id="7b01c-163">Sample Implementation Using WCF</span></span>  
 <span data-ttu-id="7b01c-164">Nella figura seguente viene illustrata un'implementazione di esempio per un'architettura di sicurezza federata usando il supporto nativo da WCF.</span><span class="sxs-lookup"><span data-stu-id="7b01c-164">The following illustration shows a sample implementation for a federated security architecture using native support from WCF.</span></span>  
  
 ![Diagramma che mostra un esempio di implementazione della sicurezza della federazione.](./media/federation/federated-security-implementation.gif)  
  
### <a name="example-myservice"></a><span data-ttu-id="7b01c-166">Esempio MyService</span><span class="sxs-lookup"><span data-stu-id="7b01c-166">Example MyService</span></span>  
 <span data-ttu-id="7b01c-167">Il servizio `MyService` espone un singolo endpoint tramite `MyServiceEndpoint`.</span><span class="sxs-lookup"><span data-stu-id="7b01c-167">The service `MyService` exposes a single endpoint through `MyServiceEndpoint`.</span></span> <span data-ttu-id="7b01c-168">Nella figura seguente vengono illustrati l'indirizzo, l'associazione e il contratto associati all'endpoint.</span><span class="sxs-lookup"><span data-stu-id="7b01c-168">The following illustration shows the address, binding, and contract associated with the endpoint.</span></span>  
  
 ![Diagramma che mostra i dettagli di MyServiceEndpoint.Diagram showing the MyServiceEndpoint details.](./media/federation/myserviceendpoint-details.gif)  
  
 <span data-ttu-id="7b01c-170">L'endpoint `MyServiceEndpoint` del servizio utilizza il [ \<>wsFederationHttpBinding](../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) e richiede un token `accessAuthorized` SAML (Security Assertions Markup Language) valido con un'attestazione rilasciata dal servizio token di sicurezza B. Viene specificato in modo dichiarativo nella configurazione del servizio.</span><span class="sxs-lookup"><span data-stu-id="7b01c-170">The service endpoint `MyServiceEndpoint` uses the [\<wsFederationHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) and requires a valid Security Assertions Markup Language (SAML) token with an `accessAuthorized` claim issued by STS B. This is declaratively specified in the service configuration.</span></span>  
  
```xml  
<system.serviceModel>  
  <services>  
    <service type="FederationSample.MyService"
        behaviorConfiguration='MyServiceBehavior'>  
        <endpoint address=""  
            binding=" wsFederationHttpBinding"  
            bindingConfiguration='MyServiceBinding'  
            contract="Federation.IMyService" />  
   </service>  
  </services>  
  
  <bindings>  
    <wsFederationHttpBinding>  
    <!-- This is the binding used by MyService. It redirects   
    clients to STS-B. -->  
      <binding name='MyServiceBinding'>  
        <security mode="Message">  
           <message issuedTokenType=  
"http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAMLV1.1">  
           <issuer address="http://localhost/FederationSample/STS-B/STS.svc" />  
            <issuerMetadata
           address=  
"http://localhost/FederationSample/STS-B/STS.svc/mex" />  
         <requiredClaimTypes>  
            <add claimType="http://tempuri.org:accessAuthorized" />  
         </requiredClaimTypes>  
        </message>  
      </security>  
      </binding>  
    </wsFederationHttpBinding>  
  </bindings>  
  
  <behaviors>  
    <behavior name='MyServiceBehavior'>  
      <serviceAuthorization
operationRequirementType="FederationSample.MyServiceOperationRequirement, MyService" />  
       <serviceCredentials>  
         <serviceCertificate findValue="CN=FederationSample.com"  
         x509FindType="FindBySubjectDistinguishedName"  
         storeLocation='LocalMachine'  
         storeName='My' />  
      </serviceCredentials>  
    </behavior>  
  </behaviors>  
</system.serviceModel>  
```  
  
> [!NOTE]
> <span data-ttu-id="7b01c-171">In relazione alle attestazioni richieste da `MyService`, è opportuno tenere presente un fattore importante.</span><span class="sxs-lookup"><span data-stu-id="7b01c-171">A subtle point should be noted about the claims required by `MyService`.</span></span> <span data-ttu-id="7b01c-172">La seconda figura indica che `MyService` richiede un token SAML con l'attestazione `accessAuthorized`.</span><span class="sxs-lookup"><span data-stu-id="7b01c-172">The second figure indicates that `MyService` requires a SAML token with the `accessAuthorized` claim.</span></span> <span data-ttu-id="7b01c-173">Per essere più precisi, viene specificato il tipo di attestazione richiesto da `MyService`.</span><span class="sxs-lookup"><span data-stu-id="7b01c-173">To be more precise, this specifies the claim type that `MyService` requires.</span></span> <span data-ttu-id="7b01c-174">Il nome completo di questo `http://tempuri.org:accessAuthorized` tipo di attestazione è (insieme allo spazio dei nomi associato), utilizzato nel file di configurazione del servizio.</span><span class="sxs-lookup"><span data-stu-id="7b01c-174">The fully-qualified name of this claim type is `http://tempuri.org:accessAuthorized` (along with the associated namespace), which is used in the service configuration file.</span></span> <span data-ttu-id="7b01c-175">Il valore di questa attestazione indica la sua presenza e si presuppone che sia impostato su `true` da STS B.</span><span class="sxs-lookup"><span data-stu-id="7b01c-175">The value of this claim indicates the presence of this claim and is assumed to be set to `true` by STS B.</span></span>  
  
 <span data-ttu-id="7b01c-176">In fase di esecuzione, questo criterio viene imposto dalla classe `MyServiceOperationRequirement` implementata come parte di `MyService`.</span><span class="sxs-lookup"><span data-stu-id="7b01c-176">At runtime, this policy is enforced by the `MyServiceOperationRequirement` class that is implemented as part of the `MyService`.</span></span>  
  
 [!code-csharp[C_Federation#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_federation/cs/source.cs#0)]
 [!code-vb[C_Federation#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_federation/vb/source.vb#0)]  
[!code-csharp[C_Federation#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_federation/cs/source.cs#1)]
[!code-vb[C_Federation#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_federation/vb/source.vb#1)]  
  
#### <a name="sts-b"></a><span data-ttu-id="7b01c-177">STS B</span><span class="sxs-lookup"><span data-stu-id="7b01c-177">STS B</span></span>  
 <span data-ttu-id="7b01c-178">Nella figura seguente viene illustrato STS B. Come dichiarato precedentemente, un servizio token di sicurezza (STS) è anche un servizio Web a cui possono essere associati endpoint, criterio e così via.</span><span class="sxs-lookup"><span data-stu-id="7b01c-178">The following illustration shows the STS B. As stated earlier, a security token service (STS) is also a Web service and can have its associated endpoints, policy, and so on.</span></span>  
  
 ![Diagramma che mostra il servizio token di sicurezza B.Diagram showing security token service B.](./media/federation/myservice-security-token-service-b.gif)  
  
 <span data-ttu-id="7b01c-180">STS B espone un singolo endpoint, chiamato `STSEndpoint` che può essere utilizzato per richiedere token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="7b01c-180">STS B exposes a single endpoint, called `STSEndpoint` that can be use to request security tokens.</span></span> <span data-ttu-id="7b01c-181">Nello specifico, STS B rilascia token SAML con l'attestazione `accessAuthorized`, che può essere presentata al sito del servizio `MyService` per accedere al servizio.</span><span class="sxs-lookup"><span data-stu-id="7b01c-181">Specifically, STS B issues SAML tokens with the `accessAuthorized` claim, which can be presented at the `MyService` service site for accessing the service.</span></span> <span data-ttu-id="7b01c-182">STS B richiede tuttavia che gli utenti presentino un token SAML valido rilasciato da STS A, contenente l'attestazione `userAuthenticated`.</span><span class="sxs-lookup"><span data-stu-id="7b01c-182">However, STS B requires users to present a valid SAML token issued by STS A that contains the `userAuthenticated` claim.</span></span> <span data-ttu-id="7b01c-183">Questo è specificato in modo dichiarativo nella configurazione STS.</span><span class="sxs-lookup"><span data-stu-id="7b01c-183">This is declaratively specified in the STS configuration.</span></span>  
  
```xml  
<system.serviceModel>  
  <services>  
    <service type="FederationSample.STS_B" behaviorConfiguration=  
     "STS-B_Behavior">  
    <endpoint address=""  
              binding="wsFederationHttpBinding"  
              bindingConfiguration='STS-B_Binding'  
      contract="FederationSample.ISts" />  
    </service>  
  </services>  
  <bindings>  
    <wsFederationHttpBinding>  
    <!-- This is the binding used by STS-B. It redirects clients to   
         STS-A. -->  
      <binding name='STS-B_Binding'>  
        <security mode='Message'>  
          <message issuedTokenType="http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAMLV1.1">  
          <issuer address='http://localhost/FederationSample/STS-A/STS.svc' />  
          <issuerMetadata address='http://localhost/FederationSample/STS-A/STS.svc/mex'/>  
          <requiredClaimTypes>  
            <add claimType='http://tempuri.org:userAuthenticated'/>  
          </requiredClaimTypes>  
          </message>  
        </security>  
    </binding>  
   </wsFederationHttpBinding>  
  </bindings>  
  <behaviors>  
  <behavior name='STS-B_Behavior'>  
    <serviceAuthorization   operationRequirementType='FederationSample.STS_B_OperationRequirement, STS_B' />  
    <serviceCredentials>  
      <serviceCertificate findValue='CN=FederationSample.com'  
      x509FindType='FindBySubjectDistinguishedName'  
       storeLocation='LocalMachine'  
       storeName='My' />  
     </serviceCredentials>  
   </behavior>  
  </behaviors>  
</system.serviceModel>  
```  
  
> [!NOTE]
> <span data-ttu-id="7b01c-184">Anche in `userAuthenticated` questo caso, l'attestazione è il tipo di attestazione richiesto dal servizio token di sicurezza B. Il nome completo di questo `http://tempuri.org:userAuthenticated` tipo di attestazione è (insieme allo spazio dei nomi associato), utilizzato nel file di configurazione del servizio token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="7b01c-184">Again, the `userAuthenticated` claim is the claim type that is required by STS B. The fully-qualified name of this claim type is `http://tempuri.org:userAuthenticated` (along with the associated namespace), which is used in the STS configuration file.</span></span> <span data-ttu-id="7b01c-185">Il valore di questa attestazione indica la sua presenza e si presuppone che sia impostato su `true` da STS A.</span><span class="sxs-lookup"><span data-stu-id="7b01c-185">The value of this claim indicates the presence of this claim and is assumed to be set to `true` by STS A.</span></span>  
  
 <span data-ttu-id="7b01c-186">In fase di esecuzione, questo criterio viene imposto dalla classe `STS_B_OperationRequirement` implementata come parte di STS B.</span><span class="sxs-lookup"><span data-stu-id="7b01c-186">At runtime, the `STS_B_OperationRequirement` class enforces this policy, which is implemented as part of STS B.</span></span>  
  
 [!code-csharp[C_Federation#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_federation/cs/source.cs#2)]
 [!code-vb[C_Federation#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_federation/vb/source.vb#2)]  
  
 <span data-ttu-id="7b01c-187">Se il controllo di accesso è chiaro, STS B rilascia un token SAML con l'attestazione `accessAuthorized`.</span><span class="sxs-lookup"><span data-stu-id="7b01c-187">If the access check is clear, STS B issues a SAML token with the `accessAuthorized` claim.</span></span>  
  
 [!code-csharp[C_Federation#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_federation/cs/source.cs#3)]
 [!code-vb[C_Federation#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_federation/vb/source.vb#3)]  
  
#### <a name="sts-a"></a><span data-ttu-id="7b01c-188">STS A</span><span class="sxs-lookup"><span data-stu-id="7b01c-188">STS A</span></span>  
 <span data-ttu-id="7b01c-189">Nella figura seguente viene illustrato STS A.</span><span class="sxs-lookup"><span data-stu-id="7b01c-189">The following illustration shows the STS A.</span></span>  
  
 <span data-ttu-id="7b01c-190">![Federazione](../../../../docs/framework/wcf/feature-details/media/sts-b.gif "STS_B")</span><span class="sxs-lookup"><span data-stu-id="7b01c-190">![Federation](../../../../docs/framework/wcf/feature-details/media/sts-b.gif "STS_B")</span></span>  
  
 <span data-ttu-id="7b01c-191">Anche STS A, come STS B, è un servizio Web che rilascia token di sicurezza ed espone a tale fine un solo endpoint.</span><span class="sxs-lookup"><span data-stu-id="7b01c-191">Similar to the STS B, the STS A is also a Web service that issues security tokens and exposes a single endpoint for this purpose.</span></span> <span data-ttu-id="7b01c-192">Tuttavia, utilizza un'associazione diversa (`wsHttpBinding`) e richiede `emailAddress` agli utenti di presentare un CardSpace valido con un'attestazione.</span><span class="sxs-lookup"><span data-stu-id="7b01c-192">However, it uses a different binding (`wsHttpBinding`) and requires users to present a valid CardSpace with an `emailAddress` claim.</span></span> <span data-ttu-id="7b01c-193">In risposta, rilascia token SAML con l'attestazione `userAuthenticated`.</span><span class="sxs-lookup"><span data-stu-id="7b01c-193">In response, it issues SAML tokens with the `userAuthenticated` claim.</span></span> <span data-ttu-id="7b01c-194">Questo è specificato in modo dichiarativo nella configurazione del servizio.</span><span class="sxs-lookup"><span data-stu-id="7b01c-194">This is declaratively specified in the service configuration.</span></span>  
  
```xml  
<system.serviceModel>  
  <services>  
    <service type="FederationSample.STS_A" behaviorConfiguration="STS-A_Behavior">  
      <endpoint address=""  
                binding="wsHttpBinding"  
                bindingConfiguration="STS-A_Binding"  
                contract="FederationSample.ISts">  
       <identity>  
       <certificateReference findValue="CN=FederationSample.com"
                       x509FindType="FindBySubjectDistinguishedName"  
                       storeLocation="LocalMachine"
                       storeName="My" />  
       </identity>  
    </endpoint>  
  </service>  
</services>  
  
<bindings>  
  <wsHttpBinding>  
  <!-- This is the binding used by STS-A. It requires users to present  
   a CardSpace. -->  
    <binding name='STS-A_Binding'>  
      <security mode='Message'>  
        <message clientCredentialType="CardSpace" />  
      </security>  
    </binding>  
  </wsHttpBinding>  
</bindings>  
  
<behaviors>  
  <behavior name='STS-A_Behavior'>  
    <serviceAuthorization operationRequirementType=  
     "FederationSample.STS_A_OperationRequirement, STS_A" />  
      <serviceCredentials>  
  <serviceCertificate findValue="CN=FederationSample.com"  
                     x509FindType='FindBySubjectDistinguishedName'  
                     storeLocation='LocalMachine'  
                     storeName='My' />  
      </serviceCredentials>  
    </behavior>  
  </behaviors>  
</system.serviceModel>  
```  
  
 <span data-ttu-id="7b01c-195">In fase di esecuzione, questo criterio viene imposto dalla classe `STS_A_OperationRequirement` implementata come parte di STS A.</span><span class="sxs-lookup"><span data-stu-id="7b01c-195">At runtime, the `STS_A_OperationRequirement` class enforces this policy, which is implemented as part of STS A.</span></span>  
  
 [!code-csharp[C_Federation#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_federation/cs/source.cs#4)]
 [!code-vb[C_Federation#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_federation/vb/source.vb#4)]  
  
 <span data-ttu-id="7b01c-196">Se l'accesso è `true`, STS A rilascia un token SAML con l'attestazione `userAuthenticated`.</span><span class="sxs-lookup"><span data-stu-id="7b01c-196">If the access is `true`, STS A issues a SAML token with `userAuthenticated` claim.</span></span>  
  
 [!code-csharp[C_Federation#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_federation/cs/source.cs#5)]
 [!code-vb[C_Federation#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_federation/vb/source.vb#5)]  
  
### <a name="client-at-organization-a"></a><span data-ttu-id="7b01c-197">Client nell'organizzazione A</span><span class="sxs-lookup"><span data-stu-id="7b01c-197">Client at Organization A</span></span>  
 <span data-ttu-id="7b01c-198">Nella figura seguente viene illustrato il client nell'organizzazione A, insieme ai passaggi necessari per eseguire una chiamata al servizio `MyService`.</span><span class="sxs-lookup"><span data-stu-id="7b01c-198">The following illustration shows the client at organization A, along with the steps involved in making a `MyService` service call.</span></span> <span data-ttu-id="7b01c-199">A fini di completezza, sono inclusi anche gli altri componenti funzionali.</span><span class="sxs-lookup"><span data-stu-id="7b01c-199">The other functional components are also included for completeness.</span></span>  
  
 ![Diagramma che illustra i passaggi in una chiamata al servizio MyService.Diagram showing the steps in a MyService service call.](./media/federation/federation-myservice-service-call-process.gif)  
  
## <a name="summary"></a><span data-ttu-id="7b01c-201">Summary</span><span class="sxs-lookup"><span data-stu-id="7b01c-201">Summary</span></span>  
 <span data-ttu-id="7b01c-202">La protezione federata offre una divisione netta della responsabilità e contribuisce a creare architetture del servizio sicure e scalabili.</span><span class="sxs-lookup"><span data-stu-id="7b01c-202">Federated security provides a clean division of responsibility and helps to build secure, scalable service architectures.</span></span> <span data-ttu-id="7b01c-203">Come piattaforma per la compilazione e la distribuzione di applicazioni distribuite, WCF fornisce supporto nativo per l'implementazione della sicurezza federata.</span><span class="sxs-lookup"><span data-stu-id="7b01c-203">As a platform for building and deploying distributed applications, WCF provides native support for implementing federated security.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b01c-204">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7b01c-204">See also</span></span>

- [<span data-ttu-id="7b01c-205">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="7b01c-205">Security</span></span>](../../../../docs/framework/wcf/feature-details/security.md)

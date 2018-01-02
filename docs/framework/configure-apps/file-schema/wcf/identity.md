---
title: '&lt;identity&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c1d2ae56-e231-4a07-9c3f-9f13381dc0d8
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 819bb9dc9817050e45a39331361dd5489692f0b9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ltidentitygt"></a><span data-ttu-id="2bb74-102">&lt;identity&gt;</span><span class="sxs-lookup"><span data-stu-id="2bb74-102">&lt;identity&gt;</span></span>
<span data-ttu-id="2bb74-103">L'elemento identity consente a uno sviluppatore di client di specificare in fase di progettazione l'identità prevista del servizio.</span><span class="sxs-lookup"><span data-stu-id="2bb74-103">The identity element allows a client developer to specify at design time the expected identity of the service.</span></span> <span data-ttu-id="2bb74-104">Nel processo di handshake tra il client e il servizio, l'infrastruttura [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] garantirà che l'identità del servizio previsto corrisponda ai valori di questo elemento consentendone pertanto l'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="2bb74-104">In the handshake process between the client and service, the [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] infrastructure will ensure that the identity of the expected service matches the values of this element, and thus can be authenticated.</span></span> <span data-ttu-id="2bb74-105">Per ulteriori informazioni, vedere [autenticazione e identità del servizio](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="2bb74-105">For more information, see [Service Identity and Authentication](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
 <span data-ttu-id="2bb74-106">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="2bb74-106">\<system.ServiceModel></span></span>  
<span data-ttu-id="2bb74-107">\<client ></span><span class="sxs-lookup"><span data-stu-id="2bb74-107">\<client></span></span>  
<span data-ttu-id="2bb74-108">\<endpoint ></span><span class="sxs-lookup"><span data-stu-id="2bb74-108">\<endpoint></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2bb74-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2bb74-109">Syntax</span></span>  
  
```xml  
<identity>  
    <certificate encodedValue="String"/>  
    <certificateReference findValue="String"   
       isChainIncluded="Boolean"  
       storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"storeName="  
       storeLocation="LocalMachine/CurrentUser"  
       X509FindType= Enumeration./>  
    <dns value="String"/>  
    <rsa value="String"/>  
    <servicePrincipalName value="String"/>  
    <usePrincipalName value="String"/>  
</identity>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2bb74-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="2bb74-110">Attributes and Elements</span></span>  
 <span data-ttu-id="2bb74-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="2bb74-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2bb74-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="2bb74-112">Attributes</span></span>  
 <span data-ttu-id="2bb74-113">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="2bb74-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="2bb74-114">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="2bb74-114">Child Elements</span></span>  
  
|<span data-ttu-id="2bb74-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="2bb74-115">Element</span></span>|<span data-ttu-id="2bb74-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2bb74-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2bb74-117">certificato</span><span class="sxs-lookup"><span data-stu-id="2bb74-117">certificate</span></span>|<span data-ttu-id="2bb74-118">Specifica le impostazioni di un certificato X.509.</span><span class="sxs-lookup"><span data-stu-id="2bb74-118">Specifies settings of an X.509 certificate.</span></span> <span data-ttu-id="2bb74-119">L'elemento è di tipo <xref:System.ServiceModel.Configuration.CertificateElement>.</span><span class="sxs-lookup"><span data-stu-id="2bb74-119">This element is of type <xref:System.ServiceModel.Configuration.CertificateElement>.</span></span> <span data-ttu-id="2bb74-120">Contiene un attributo stringa `encodedValue` che specifica il valore codificato da questo certificato.</span><span class="sxs-lookup"><span data-stu-id="2bb74-120">It contains an attribute `encodedValue` that is a string, which specifies the value encoded by this certificate.</span></span>|  
|<span data-ttu-id="2bb74-121">certificateReference</span><span class="sxs-lookup"><span data-stu-id="2bb74-121">certificateReference</span></span>|<span data-ttu-id="2bb74-122">Specifica le impostazioni per la convalida del certificato X.509.</span><span class="sxs-lookup"><span data-stu-id="2bb74-122">Specifies settings for X.509 certificate validation.</span></span> <span data-ttu-id="2bb74-123">L'elemento è di tipo <xref:System.ServiceModel.Configuration.CertificateReferenceElement>.</span><span class="sxs-lookup"><span data-stu-id="2bb74-123">This element is of type <xref:System.ServiceModel.Configuration.CertificateReferenceElement>.</span></span>|  
|<span data-ttu-id="2bb74-124">dns</span><span class="sxs-lookup"><span data-stu-id="2bb74-124">dns</span></span>|<span data-ttu-id="2bb74-125">Specifica il DNS di un certificato X.509 usato per autenticare un servizio.</span><span class="sxs-lookup"><span data-stu-id="2bb74-125">Specifies the DNS of an X.509 certificate used to authenticate a service.</span></span> <span data-ttu-id="2bb74-126">Questo elemento contiene un attributo stringa `value` contenente l'identità effettiva.</span><span class="sxs-lookup"><span data-stu-id="2bb74-126">This element contains an attribute `value` that is a string, and contains the actual identity.</span></span>|  
|<span data-ttu-id="2bb74-127">rsa</span><span class="sxs-lookup"><span data-stu-id="2bb74-127">rsa</span></span>|<span data-ttu-id="2bb74-128">Specifica il valore del campo RSA di un certificato X.509 usato per autenticare un servizio presso un client.</span><span class="sxs-lookup"><span data-stu-id="2bb74-128">Specifies the value of the RSA field of an X.509 certificate used to authenticate a service to a client.</span></span> <span data-ttu-id="2bb74-129">Questo elemento contiene un attributo stringa `value` contenente l'identità effettiva.</span><span class="sxs-lookup"><span data-stu-id="2bb74-129">This element contains an attribute `value` that is a string, and contains the actual identity</span></span>|  
|<span data-ttu-id="2bb74-130">servicePrincipalName</span><span class="sxs-lookup"><span data-stu-id="2bb74-130">servicePrincipalName</span></span>|<span data-ttu-id="2bb74-131">Specifica l'identità di un nome principale di servizio (SPN, Server Principal Name), ovvero il nome principale usato da un client per identificare in modo univoco un'istanza di un servizio.</span><span class="sxs-lookup"><span data-stu-id="2bb74-131">Specifies a server principal name (SPN) identity, which is the principal name used by a client to uniquely identify an instance of a service.</span></span> <span data-ttu-id="2bb74-132">Questo elemento contiene un attributo stringa `value` contenente il nome principale effettivo.</span><span class="sxs-lookup"><span data-stu-id="2bb74-132">This element contains an attribute `value` that is a string, and contains the actual principal name.</span></span> <span data-ttu-id="2bb74-133">L'elemento è di tipo <xref:System.ServiceModel.Configuration.ServicePrincipalNameElement>.</span><span class="sxs-lookup"><span data-stu-id="2bb74-133">This element is of type <xref:System.ServiceModel.Configuration.ServicePrincipalNameElement>.</span></span>|  
|<span data-ttu-id="2bb74-134">nomeEntitàUtente</span><span class="sxs-lookup"><span data-stu-id="2bb74-134">userPrincipalName</span></span>|<span data-ttu-id="2bb74-135">Specifica l'identità di un nome principale dell'utente (UPN, User Principal Name), ovvero il tipo di nome che un utente usa per accedere a una rete.</span><span class="sxs-lookup"><span data-stu-id="2bb74-135">Specifies a user principal name (UPN) identity, which is the logon name type of a user on a network.</span></span> <span data-ttu-id="2bb74-136">È costituito dal nome dell'oggetto utente usato in Active Directory seguito dal simbolo "@" e quindi, in genere, dal dominio padre DNS (Domain Name System).</span><span class="sxs-lookup"><span data-stu-id="2bb74-136">The user principal name consists of the user object name used in Active Directory, followed by the at symbol (@) and then, typically, the Domain Name System parent domain.</span></span> <span data-ttu-id="2bb74-137">Jeff nell'albero di dominio Fabrikam.com sarebbe ad esempio, il nome dell'entità utente [ jeff@fabrikam.com ](mailto:jeffsmith@fabrikam.com).  Questo elemento contiene un attributo stringa `value` contenente il nome principale effettivo.</span><span class="sxs-lookup"><span data-stu-id="2bb74-137">For example, Jeff in the Fabrikam.com domain tree might have the user principal name [jeff@fabrikam.com](mailto:jeffsmith@fabrikam.com).  This element contains an attribute `value` that is a string, and contains the actual principal name.</span></span> <span data-ttu-id="2bb74-138">L'elemento è di tipo <xref:System.ServiceModel.Configuration.UserPrincipalNameElement>.</span><span class="sxs-lookup"><span data-stu-id="2bb74-138">This element is of type <xref:System.ServiceModel.Configuration.UserPrincipalNameElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2bb74-139">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="2bb74-139">Parent Elements</span></span>  
  
|<span data-ttu-id="2bb74-140">Elemento</span><span class="sxs-lookup"><span data-stu-id="2bb74-140">Element</span></span>|<span data-ttu-id="2bb74-141">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2bb74-141">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2bb74-142">\<personalizzate ></span><span class="sxs-lookup"><span data-stu-id="2bb74-142">\<custom></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custom.md)|<span data-ttu-id="2bb74-143">Specifica un resolver peer personalizzato per un'associazione netPeerTcpBinding.</span><span class="sxs-lookup"><span data-stu-id="2bb74-143">Specifies a custom peer resolver for a netPeerTcpBinding.</span></span>|  
|[<span data-ttu-id="2bb74-144">\<endpoint ></span><span class="sxs-lookup"><span data-stu-id="2bb74-144">\<endpoint></span></span>](http://msdn.microsoft.com/en-us/13aa23b7-2f08-4add-8dbf-a99f8127c017)|<span data-ttu-id="2bb74-145">Configura differenti tipi di endpoint.</span><span class="sxs-lookup"><span data-stu-id="2bb74-145">Configures different types of endpoints.</span></span>|  
|[<span data-ttu-id="2bb74-146">\<autorità di certificazione ></span><span class="sxs-lookup"><span data-stu-id="2bb74-146">\<issuer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuer.md)|<span data-ttu-id="2bb74-147">Specifica il servizio token di sicurezza del servizio federato.</span><span class="sxs-lookup"><span data-stu-id="2bb74-147">Specifies the Security Token Service (STS) for the federated service.</span></span>|  
|[<span data-ttu-id="2bb74-148">\<issuerMetadata ></span><span class="sxs-lookup"><span data-stu-id="2bb74-148">\<issuerMetadata></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuermetadata.md)|<span data-ttu-id="2bb74-149">Specifica l'endpoint dei metadati del servizio token di sicurezza di un servizio federato.</span><span class="sxs-lookup"><span data-stu-id="2bb74-149">Specifies the metadata endpoint for the Security Token Service (STS) of a federated service.</span></span>|  
|[<span data-ttu-id="2bb74-150">\<issuedTokenParameters ></span><span class="sxs-lookup"><span data-stu-id="2bb74-150">\<issuedTokenParameters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenparameters.md)|<span data-ttu-id="2bb74-151">Definisce i parametri di un token emesso in un'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="2bb74-151">Defines parameters for an issued token in a custom binding.</span></span>|  
|[<span data-ttu-id="2bb74-152">\<localIssuer ></span><span class="sxs-lookup"><span data-stu-id="2bb74-152">\<localIssuer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/localissuer.md)|<span data-ttu-id="2bb74-153">Specifica un servizio token di sicurezza locale.</span><span class="sxs-lookup"><span data-stu-id="2bb74-153">Specifies a local Security Token Service (STS).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2bb74-154">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2bb74-154">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.IdentityElement>  
 <xref:System.ServiceModel.EndpointAddress>  
 <xref:System.ServiceModel.EndpointAddress.Identity%2A>  
 [<span data-ttu-id="2bb74-155">Identità del servizio e autenticazione</span><span class="sxs-lookup"><span data-stu-id="2bb74-155">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="2bb74-156">Endpoint: indirizzi, associazioni e contratti</span><span class="sxs-lookup"><span data-stu-id="2bb74-156">Endpoints: Addresses, Bindings, and Contracts</span></span>](../../../../../docs/framework/wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)

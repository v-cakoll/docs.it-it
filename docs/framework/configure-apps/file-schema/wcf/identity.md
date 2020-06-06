---
title: <identity>
ms.date: 03/30/2017
ms.assetid: c1d2ae56-e231-4a07-9c3f-9f13381dc0d8
ms.openlocfilehash: 15c9e38a141fc294c47863b1a932711444ac079a
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855145"
---
# \<identity>
<span data-ttu-id="f3b26-101">L'elemento identity consente a uno sviluppatore di client di specificare in fase di progettazione l'identità prevista del servizio.</span><span class="sxs-lookup"><span data-stu-id="f3b26-101">The identity element allows a client developer to specify at design time the expected identity of the service.</span></span> <span data-ttu-id="f3b26-102">Nel processo di handshake tra il client e il servizio, l'infrastruttura Windows Communication Foundation (WCF) garantirà che l'identità del servizio previsto corrisponda ai valori di questo elemento e possa quindi essere autenticata.</span><span class="sxs-lookup"><span data-stu-id="f3b26-102">In the handshake process between the client and service, the Windows Communication Foundation (WCF) infrastructure will ensure that the identity of the expected service matches the values of this element, and thus can be authenticated.</span></span> <span data-ttu-id="f3b26-103">Per altre informazioni, vedere [identità e autenticazione del servizio](../../../wcf/feature-details/service-identity-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="f3b26-103">For more information, see [Service Identity and Authentication](../../../wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpoint>**](endpoint-of-client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<identity>**  
  
## <a name="syntax"></a><span data-ttu-id="f3b26-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f3b26-104">Syntax</span></span>  
  
```xml  
<identity>
  <certificate encodedValue="String" />
  <certificateReference findValue="String"
                        isChainIncluded="Boolean"
                        storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
                        storeLocation="LocalMachine/CurrentUser"
                        X509FindType="Enumeration" />
  <dns value="String" />
  <rsa value="String" />
  <servicePrincipalName value="String" />
  <userPrincipalName value="String" />
</identity>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f3b26-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="f3b26-105">Attributes and Elements</span></span>  
 <span data-ttu-id="f3b26-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="f3b26-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f3b26-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="f3b26-107">Attributes</span></span>  
 <span data-ttu-id="f3b26-108">No.</span><span class="sxs-lookup"><span data-stu-id="f3b26-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="f3b26-109">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="f3b26-109">Child Elements</span></span>  
  
|<span data-ttu-id="f3b26-110">Elemento</span><span class="sxs-lookup"><span data-stu-id="f3b26-110">Element</span></span>|<span data-ttu-id="f3b26-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f3b26-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f3b26-112">certificato</span><span class="sxs-lookup"><span data-stu-id="f3b26-112">certificate</span></span>|<span data-ttu-id="f3b26-113">Specifica le impostazioni di un certificato X.509.</span><span class="sxs-lookup"><span data-stu-id="f3b26-113">Specifies settings of an X.509 certificate.</span></span> <span data-ttu-id="f3b26-114">L'elemento è di tipo <xref:System.ServiceModel.Configuration.CertificateElement>.</span><span class="sxs-lookup"><span data-stu-id="f3b26-114">This element is of type <xref:System.ServiceModel.Configuration.CertificateElement>.</span></span> <span data-ttu-id="f3b26-115">Contiene un attributo stringa `encodedValue` che specifica il valore codificato da questo certificato.</span><span class="sxs-lookup"><span data-stu-id="f3b26-115">It contains an attribute `encodedValue` that is a string, which specifies the value encoded by this certificate.</span></span>|  
|<span data-ttu-id="f3b26-116">certificateReference</span><span class="sxs-lookup"><span data-stu-id="f3b26-116">certificateReference</span></span>|<span data-ttu-id="f3b26-117">Specifica le impostazioni per la convalida del certificato X.509.</span><span class="sxs-lookup"><span data-stu-id="f3b26-117">Specifies settings for X.509 certificate validation.</span></span> <span data-ttu-id="f3b26-118">L'elemento è di tipo <xref:System.ServiceModel.Configuration.CertificateReferenceElement>.</span><span class="sxs-lookup"><span data-stu-id="f3b26-118">This element is of type <xref:System.ServiceModel.Configuration.CertificateReferenceElement>.</span></span>|  
|<span data-ttu-id="f3b26-119">dns</span><span class="sxs-lookup"><span data-stu-id="f3b26-119">dns</span></span>|<span data-ttu-id="f3b26-120">Specifica il DNS di un certificato X.509 usato per autenticare un servizio.</span><span class="sxs-lookup"><span data-stu-id="f3b26-120">Specifies the DNS of an X.509 certificate used to authenticate a service.</span></span> <span data-ttu-id="f3b26-121">Questo elemento contiene un attributo stringa `value` contenente l'identità effettiva.</span><span class="sxs-lookup"><span data-stu-id="f3b26-121">This element contains an attribute `value` that is a string, and contains the actual identity.</span></span>|  
|<span data-ttu-id="f3b26-122">rsa</span><span class="sxs-lookup"><span data-stu-id="f3b26-122">rsa</span></span>|<span data-ttu-id="f3b26-123">Specifica il valore del campo RSA di un certificato X.509 usato per autenticare un servizio presso un client.</span><span class="sxs-lookup"><span data-stu-id="f3b26-123">Specifies the value of the RSA field of an X.509 certificate used to authenticate a service to a client.</span></span> <span data-ttu-id="f3b26-124">Questo elemento contiene un attributo stringa `value` contenente l'identità effettiva.</span><span class="sxs-lookup"><span data-stu-id="f3b26-124">This element contains an attribute `value` that is a string, and contains the actual identity</span></span>|  
|<span data-ttu-id="f3b26-125">servicePrincipalName</span><span class="sxs-lookup"><span data-stu-id="f3b26-125">servicePrincipalName</span></span>|<span data-ttu-id="f3b26-126">Specifica l'identità di un nome principale di servizio (SPN, Server Principal Name), ovvero il nome principale usato da un client per identificare in modo univoco un'istanza di un servizio.</span><span class="sxs-lookup"><span data-stu-id="f3b26-126">Specifies a server principal name (SPN) identity, which is the principal name used by a client to uniquely identify an instance of a service.</span></span> <span data-ttu-id="f3b26-127">Questo elemento contiene un attributo stringa `value` contenente il nome principale effettivo.</span><span class="sxs-lookup"><span data-stu-id="f3b26-127">This element contains an attribute `value` that is a string, and contains the actual principal name.</span></span> <span data-ttu-id="f3b26-128">L'elemento è di tipo <xref:System.ServiceModel.Configuration.ServicePrincipalNameElement>.</span><span class="sxs-lookup"><span data-stu-id="f3b26-128">This element is of type <xref:System.ServiceModel.Configuration.ServicePrincipalNameElement>.</span></span>|  
|<span data-ttu-id="f3b26-129">userPrincipalName</span><span class="sxs-lookup"><span data-stu-id="f3b26-129">userPrincipalName</span></span>|<span data-ttu-id="f3b26-130">Specifica l'identità di un nome principale dell'utente (UPN, User Principal Name), ovvero il tipo di nome che un utente usa per accedere a una rete.</span><span class="sxs-lookup"><span data-stu-id="f3b26-130">Specifies a user principal name (UPN) identity, which is the logon name type of a user on a network.</span></span> <span data-ttu-id="f3b26-131">Il nome dell'entità utente è costituito dal nome dell'oggetto utente utilizzato in Active Directory, seguito dal simbolo di chiocciola ( \@ ) e quindi, in genere, dal dominio Domain Name System padre.</span><span class="sxs-lookup"><span data-stu-id="f3b26-131">The user principal name consists of the user object name used in Active Directory, followed by the at symbol (\@) and then, typically, the Domain Name System parent domain.</span></span> <span data-ttu-id="f3b26-132">Ad esempio, Jeff nell'albero di dominio Fabrikam.com potrebbe avere il nome dell'entità utente [jeff@fabrikam.com](mailto:jeffsmith@fabrikam.com) .</span><span class="sxs-lookup"><span data-stu-id="f3b26-132">For example, Jeff in the Fabrikam.com domain tree might have the user principal name [jeff@fabrikam.com](mailto:jeffsmith@fabrikam.com).</span></span>  <span data-ttu-id="f3b26-133">Questo elemento contiene un attributo stringa `value` contenente il nome principale effettivo.</span><span class="sxs-lookup"><span data-stu-id="f3b26-133">This element contains an attribute `value` that is a string, and contains the actual principal name.</span></span> <span data-ttu-id="f3b26-134">L'elemento è di tipo <xref:System.ServiceModel.Configuration.UserPrincipalNameElement>.</span><span class="sxs-lookup"><span data-stu-id="f3b26-134">This element is of type <xref:System.ServiceModel.Configuration.UserPrincipalNameElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f3b26-135">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="f3b26-135">Parent Elements</span></span>  
  
|<span data-ttu-id="f3b26-136">Elemento</span><span class="sxs-lookup"><span data-stu-id="f3b26-136">Element</span></span>|<span data-ttu-id="f3b26-137">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f3b26-137">Description</span></span>|  
|-------------|-----------------|  
|[\<custom>](custom.md)|<span data-ttu-id="f3b26-138">Specifica un resolver peer personalizzato per un'associazione netPeerTcpBinding.</span><span class="sxs-lookup"><span data-stu-id="f3b26-138">Specifies a custom peer resolver for a netPeerTcpBinding.</span></span>|  
|[\<endpoint>](endpoint-element.md)|<span data-ttu-id="f3b26-139">Configura gli endpoint di servizio.</span><span class="sxs-lookup"><span data-stu-id="f3b26-139">Configures service endpoints.</span></span>|  
|[<span data-ttu-id="f3b26-140">\<endpoint>di\<client></span><span class="sxs-lookup"><span data-stu-id="f3b26-140">\<endpoint> of \<client></span></span>](endpoint-of-client.md)|<span data-ttu-id="f3b26-141">Configura gli endpoint del canale.</span><span class="sxs-lookup"><span data-stu-id="f3b26-141">Configures channel endpoints.</span></span>|  
|[\<issuer>](issuer.md)|<span data-ttu-id="f3b26-142">Specifica il servizio token di sicurezza del servizio federato.</span><span class="sxs-lookup"><span data-stu-id="f3b26-142">Specifies the Security Token Service (STS) for the federated service.</span></span>|  
|[\<issuerMetadata>](issuermetadata.md)|<span data-ttu-id="f3b26-143">Specifica l'endpoint dei metadati del servizio token di sicurezza di un servizio federato.</span><span class="sxs-lookup"><span data-stu-id="f3b26-143">Specifies the metadata endpoint for the Security Token Service (STS) of a federated service.</span></span>|  
|[\<issuedTokenParameters>](issuedtokenparameters.md)|<span data-ttu-id="f3b26-144">Definisce i parametri di un token emesso in un'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="f3b26-144">Defines parameters for an issued token in a custom binding.</span></span>|  
|[\<localIssuer>](localissuer.md)|<span data-ttu-id="f3b26-145">Specifica un servizio token di sicurezza locale.</span><span class="sxs-lookup"><span data-stu-id="f3b26-145">Specifies a local Security Token Service (STS).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f3b26-146">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="f3b26-146">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- [<span data-ttu-id="f3b26-147">Identità del servizio e autenticazione</span><span class="sxs-lookup"><span data-stu-id="f3b26-147">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="f3b26-148">Endpoint: indirizzi, associazioni e contratti</span><span class="sxs-lookup"><span data-stu-id="f3b26-148">Endpoints: Addresses, Bindings, and Contracts</span></span>](../../../wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)

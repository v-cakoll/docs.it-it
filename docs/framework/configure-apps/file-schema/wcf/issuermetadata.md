---
title: <issuerMetadata>
ms.date: 03/30/2017
ms.assetid: e7eae2c0-cc17-4281-af59-e4eb8d54f92a
ms.openlocfilehash: a28223127f7987a80bdf12d2dcf42878f717a377
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70397890"
---
# \<issuerMetadata>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsFederationHttpBinding>**](wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<message>**](message-element-of-wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuerMetadata>**  
  
## <a name="syntax"></a><span data-ttu-id="42495-101">Sintassi</span><span class="sxs-lookup"><span data-stu-id="42495-101">Syntax</span></span>  
  
```xml  
<issuerMetadata address="String">
  <headers>
    <add name="String"
         namespace="String" />
  </headers>
  <identity>
    <certificate encodedValue="String" />
    <certificateReference findValue="String"
                          isChainIncluded="Boolean"
                          storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
                          storeLocation="LocalMachine/CurrentUser"
                          x509FindType="System.Security.Cryptography.X509certificates.X509findtype" />
    <dns value="String" />
    <rsa value="String" />
    <servicePrincipalName value="String" />
    <usePrincipalName value="String" />
  </identity>
</issuerMetadata>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="42495-102">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="42495-102">Attributes and Elements</span></span>  
 <span data-ttu-id="42495-103">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="42495-103">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="42495-104">Attributi</span><span class="sxs-lookup"><span data-stu-id="42495-104">Attributes</span></span>  
  
|<span data-ttu-id="42495-105">Attributo</span><span class="sxs-lookup"><span data-stu-id="42495-105">Attribute</span></span>|<span data-ttu-id="42495-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="42495-106">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="42495-107">address</span><span class="sxs-lookup"><span data-stu-id="42495-107">address</span></span>|<span data-ttu-id="42495-108">Attributo `string` obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="42495-108">Required `string` attribute.</span></span><br /><br /> <span data-ttu-id="42495-109">Specifica l'indirizzo dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="42495-109">Specifies the address of the endpoint.</span></span> <span data-ttu-id="42495-110">L'indirizzo deve essere un URI assoluto.</span><span class="sxs-lookup"><span data-stu-id="42495-110">The address must be an absolute URI.</span></span> <span data-ttu-id="42495-111">Il valore predefinito è una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="42495-111">The default value is an empty string.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="42495-112">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="42495-112">Child Elements</span></span>  
  
|<span data-ttu-id="42495-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="42495-113">Element</span></span>|<span data-ttu-id="42495-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="42495-114">Description</span></span>|  
|-------------|-----------------|  
|[\<headers>](headers-element.md)|<span data-ttu-id="42495-115">Raccolte di intestazioni di indirizzo.</span><span class="sxs-lookup"><span data-stu-id="42495-115">A collection of address headers.</span></span>|  
|[\<identity>](identity.md)|<span data-ttu-id="42495-116">Identità che consente l'autenticazione di un endpoint da altri endpoint con i quali vengono scambiati messaggi.</span><span class="sxs-lookup"><span data-stu-id="42495-116">An identity that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="42495-117">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="42495-117">Parent Elements</span></span>  
  
|<span data-ttu-id="42495-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="42495-118">Element</span></span>|<span data-ttu-id="42495-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="42495-119">Description</span></span>|  
|-------------|-----------------|  
|[\<message>](message-element-of-wsfederationhttpbinding.md)|<span data-ttu-id="42495-120">Definisce le impostazioni per la sicurezza a livello di messaggio per l' [\<wsFederationHttpBinding>](wsfederationhttpbinding.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="42495-120">Defines the settings for the message-level security for the [\<wsFederationHttpBinding>](wsfederationhttpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="42495-121">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="42495-121">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.IssuerMetadataAddress%2A>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.IssuerMetadata%2A>
- [<span data-ttu-id="42495-122">Identità del servizio e autenticazione</span><span class="sxs-lookup"><span data-stu-id="42495-122">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="42495-123">Federazione e token emessi</span><span class="sxs-lookup"><span data-stu-id="42495-123">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="42495-124">Funzionalità di sicurezza con associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="42495-124">Security Capabilities with Custom Bindings</span></span>](../../../wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="42495-125">Federazione e token emessi</span><span class="sxs-lookup"><span data-stu-id="42495-125">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)

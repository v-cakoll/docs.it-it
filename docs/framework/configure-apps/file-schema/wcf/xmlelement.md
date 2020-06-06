---
title: <xmlElement>
ms.date: 03/30/2017
ms.assetid: 395205c2-d8c0-4a5e-90f3-7ce3c085fccd
ms.openlocfilehash: 841331f233bb8c42c25c88ad8e9b4fb1a86faa76
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70398995"
---
# \<xmlElement>
<span data-ttu-id="7a930-101">Specifica un elemento XML inviato nel corpo del messaggio al servizio token di sicurezza per la richiesta di un token.</span><span class="sxs-lookup"><span data-stu-id="7a930-101">Specifies an XML element that is sent in the message body to the Security Token Service when requesting a token.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsFederationHttpBinding>**](wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<message>**](message-element-of-wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<tokenRequestParameters>**](tokenrequestparameters.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<xmlElement>**  
  
## <a name="syntax"></a><span data-ttu-id="7a930-102">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7a930-102">Syntax</span></span>  
  
```xml  
<tokenRequestParameters>
  <xmlElement xmlElement="String" />
</tokenRequestParameters>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7a930-103">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="7a930-103">Attributes and Elements</span></span>  
 <span data-ttu-id="7a930-104">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="7a930-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7a930-105">Attributi</span><span class="sxs-lookup"><span data-stu-id="7a930-105">Attributes</span></span>  
  
|<span data-ttu-id="7a930-106">Attributo</span><span class="sxs-lookup"><span data-stu-id="7a930-106">Attribute</span></span>|<span data-ttu-id="7a930-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7a930-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7a930-108">xmlElement</span><span class="sxs-lookup"><span data-stu-id="7a930-108">xmlElement</span></span>|<span data-ttu-id="7a930-109">Stringa che specifica un elemento XML inviato nel corpo del messaggio al servizio token di sicurezza per la richiesta di un token.</span><span class="sxs-lookup"><span data-stu-id="7a930-109">A string specifying an XML element that is sent in the message body to the Security Token Service when requesting a token.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7a930-110">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="7a930-110">Child Elements</span></span>  
 <span data-ttu-id="7a930-111">No.</span><span class="sxs-lookup"><span data-stu-id="7a930-111">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7a930-112">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="7a930-112">Parent Elements</span></span>  
  
|<span data-ttu-id="7a930-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="7a930-113">Element</span></span>|<span data-ttu-id="7a930-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7a930-114">Description</span></span>|  
|-------------|-----------------|  
|[\<tokenRequestParameters>](tokenrequestparameters.md)|<span data-ttu-id="7a930-115">Raccolta di parametri della richiesta di token.</span><span class="sxs-lookup"><span data-stu-id="7a930-115">A collection of token request parameters.</span></span> <span data-ttu-id="7a930-116">Ciascun parametro è un elemento XML.</span><span class="sxs-lookup"><span data-stu-id="7a930-116">Each parameter is an XML element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7a930-117">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="7a930-117">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.TokenRequestParameters%2A>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.TokenRequestParameters%2A>
- [<span data-ttu-id="7a930-118">Identità del servizio e autenticazione</span><span class="sxs-lookup"><span data-stu-id="7a930-118">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="7a930-119">Federazione e token emessi</span><span class="sxs-lookup"><span data-stu-id="7a930-119">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="7a930-120">Funzionalità di sicurezza con associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="7a930-120">Security Capabilities with Custom Bindings</span></span>](../../../wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="7a930-121">Federazione e token emessi</span><span class="sxs-lookup"><span data-stu-id="7a930-121">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="7a930-122">Binding</span><span class="sxs-lookup"><span data-stu-id="7a930-122">Bindings</span></span>](../../../wcf/bindings.md)

---
title: <xmlElement>
ms.date: 03/30/2017
ms.assetid: 395205c2-d8c0-4a5e-90f3-7ce3c085fccd
ms.openlocfilehash: 841331f233bb8c42c25c88ad8e9b4fb1a86faa76
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398995"
---
# <a name="xmlelement"></a><span data-ttu-id="04c13-101">\<xmlElement></span><span class="sxs-lookup"><span data-stu-id="04c13-101">\<xmlElement></span></span>
<span data-ttu-id="04c13-102">Specifica un elemento XML inviato nel corpo del messaggio al servizio token di sicurezza per la richiesta di un token.</span><span class="sxs-lookup"><span data-stu-id="04c13-102">Specifies an XML element that is sent in the message body to the Security Token Service when requesting a token.</span></span>  
  
<span data-ttu-id="04c13-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="04c13-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="04c13-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="04c13-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="04c13-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Binding >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="04c13-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="04c13-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> wsFederationHttpBinding**](wsfederationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="04c13-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsFederationHttpBinding>**](wsfederationhttpbinding.md)</span></span>\
<span data-ttu-id="04c13-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Binding >** </span><span class="sxs-lookup"><span data-stu-id="04c13-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="04c13-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> di sicurezza**](security-of-wsfederationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="04c13-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-wsfederationhttpbinding.md)</span></span>\
<span data-ttu-id="04c13-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> messaggi**](message-element-of-wsfederationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="04c13-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<message>**](message-element-of-wsfederationhttpbinding.md)</span></span>\
<span data-ttu-id="04c13-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> tokenRequestParameters**](tokenrequestparameters.md)</span><span class="sxs-lookup"><span data-stu-id="04c13-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<tokenRequestParameters>**](tokenrequestparameters.md)</span></span>\
<span data-ttu-id="04c13-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> xmlElement**</span><span class="sxs-lookup"><span data-stu-id="04c13-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<xmlElement>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="04c13-112">Sintassi</span><span class="sxs-lookup"><span data-stu-id="04c13-112">Syntax</span></span>  
  
```xml  
<tokenRequestParameters>
  <xmlElement xmlElement="String" />
</tokenRequestParameters>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="04c13-113">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="04c13-113">Attributes and Elements</span></span>  
 <span data-ttu-id="04c13-114">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="04c13-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="04c13-115">Attributi</span><span class="sxs-lookup"><span data-stu-id="04c13-115">Attributes</span></span>  
  
|<span data-ttu-id="04c13-116">Attributo</span><span class="sxs-lookup"><span data-stu-id="04c13-116">Attribute</span></span>|<span data-ttu-id="04c13-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="04c13-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="04c13-118">xmlElement</span><span class="sxs-lookup"><span data-stu-id="04c13-118">xmlElement</span></span>|<span data-ttu-id="04c13-119">Stringa che specifica un elemento XML inviato nel corpo del messaggio al servizio token di sicurezza per la richiesta di un token.</span><span class="sxs-lookup"><span data-stu-id="04c13-119">A string specifying an XML element that is sent in the message body to the Security Token Service when requesting a token.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="04c13-120">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="04c13-120">Child Elements</span></span>  
 <span data-ttu-id="04c13-121">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="04c13-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="04c13-122">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="04c13-122">Parent Elements</span></span>  
  
|<span data-ttu-id="04c13-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="04c13-123">Element</span></span>|<span data-ttu-id="04c13-124">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="04c13-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="04c13-125">\<tokenRequestParameters></span><span class="sxs-lookup"><span data-stu-id="04c13-125">\<tokenRequestParameters></span></span>](tokenrequestparameters.md)|<span data-ttu-id="04c13-126">Raccolta di parametri della richiesta di token.</span><span class="sxs-lookup"><span data-stu-id="04c13-126">A collection of token request parameters.</span></span> <span data-ttu-id="04c13-127">Ciascun parametro è un elemento XML.</span><span class="sxs-lookup"><span data-stu-id="04c13-127">Each parameter is an XML element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="04c13-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="04c13-128">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.TokenRequestParameters%2A>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.TokenRequestParameters%2A>
- [<span data-ttu-id="04c13-129">Identità del servizio e autenticazione</span><span class="sxs-lookup"><span data-stu-id="04c13-129">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="04c13-130">Federazione e token rilasciati</span><span class="sxs-lookup"><span data-stu-id="04c13-130">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="04c13-131">Funzionalità di sicurezza con associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="04c13-131">Security Capabilities with Custom Bindings</span></span>](../../../wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="04c13-132">Federazione e token rilasciati</span><span class="sxs-lookup"><span data-stu-id="04c13-132">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="04c13-133">Associazioni</span><span class="sxs-lookup"><span data-stu-id="04c13-133">Bindings</span></span>](../../../wcf/bindings.md)

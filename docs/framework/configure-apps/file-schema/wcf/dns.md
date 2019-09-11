---
title: <dns>
ms.date: 03/30/2017
ms.assetid: 81819dae-4825-43b7-bccd-f16d2d3d2f06
ms.openlocfilehash: c68cabd03eca71b41a0d0acce26897fa2653f4d3
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855371"
---
# <a name="dns"></a><span data-ttu-id="ae68f-101">\<> DNS</span><span class="sxs-lookup"><span data-stu-id="ae68f-101">\<dns></span></span>
<span data-ttu-id="ae68f-102">Specifica l'identità prevista del server.</span><span class="sxs-lookup"><span data-stu-id="ae68f-102">Specifies the expected identity of the server.</span></span> <span data-ttu-id="ae68f-103">Questa identità è valida per la modalità di autenticazione tramite certificato X509 se il certificato del server contiene un DNS con lo stesso valore.</span><span class="sxs-lookup"><span data-stu-id="ae68f-103">This identity is valid for X509 Certificate authentication mode if the server’s certificate contains a DNS with the same value.</span></span> <span data-ttu-id="ae68f-104">Questa identità è inoltre valida per la modalità di autenticazione Windows se il nome SPN presenta lo stesso valore.</span><span class="sxs-lookup"><span data-stu-id="ae68f-104">It is also valid for Windows authentication mode if the SPN has the same value.</span></span>  
  
<span data-ttu-id="ae68f-105">Per ulteriori informazioni sull'impostazione del valore dell'elemento, vedere [identità e autenticazione del servizio](../../../wcf/feature-details/service-identity-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="ae68f-105">For more information about setting the element value, see [Service Identity and Authentication](../../../wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
<span data-ttu-id="ae68f-106">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="ae68f-106">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="ae68f-107">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="ae68f-107">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="ae68f-108">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> client**](client.md)</span><span class="sxs-lookup"><span data-stu-id="ae68f-108">&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)</span></span>\
<span data-ttu-id="ae68f-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> endpoint**](endpoint-of-client.md)</span><span class="sxs-lookup"><span data-stu-id="ae68f-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpoint>**](endpoint-of-client.md)</span></span>\
<span data-ttu-id="ae68f-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> identità**](identity.md)</span><span class="sxs-lookup"><span data-stu-id="ae68f-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<identity>**](identity.md)</span></span>\
<span data-ttu-id="ae68f-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> DNS**</span><span class="sxs-lookup"><span data-stu-id="ae68f-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<dns>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae68f-112">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ae68f-112">Syntax</span></span>  
  
```xml  
<dns value = "String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ae68f-113">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="ae68f-113">Attributes and Elements</span></span>  
 <span data-ttu-id="ae68f-114">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="ae68f-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ae68f-115">Attributi</span><span class="sxs-lookup"><span data-stu-id="ae68f-115">Attributes</span></span>  
  
|<span data-ttu-id="ae68f-116">Attributo</span><span class="sxs-lookup"><span data-stu-id="ae68f-116">Attribute</span></span>|<span data-ttu-id="ae68f-117">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="ae68f-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ae68f-118">value</span><span class="sxs-lookup"><span data-stu-id="ae68f-118">value</span></span>|<span data-ttu-id="ae68f-119">DNS del certificato.</span><span class="sxs-lookup"><span data-stu-id="ae68f-119">The DNS of the certificate.</span></span> <span data-ttu-id="ae68f-120">DNS è un protocollo conforme a standard di settore usato per individuare i computer di una rete basata su IP.</span><span class="sxs-lookup"><span data-stu-id="ae68f-120">DNS is an industry-standard protocol used to locate computers on an IP-based network.</span></span> <span data-ttu-id="ae68f-121">Gli utenti possono ricordare i nomi visualizzati, <https://go.microsoft.com/fwlink/?prd=10929> ad [https://go.microsoft.com/fwlink/?LinkID=96165](https://go.microsoft.com/fwlink/?LinkID=96165)esempio o, più semplici degli indirizzi basati su numeri, ad esempio 207.46.131.137.</span><span class="sxs-lookup"><span data-stu-id="ae68f-121">Users can remember display names, such as <https://go.microsoft.com/fwlink/?prd=10929> or [https://go.microsoft.com/fwlink/?LinkID=96165](https://go.microsoft.com/fwlink/?LinkID=96165), easier than number-based addresses, such as 207.46.131.137.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ae68f-122">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="ae68f-122">Child Elements</span></span>  
 <span data-ttu-id="ae68f-123">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="ae68f-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ae68f-124">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="ae68f-124">Parent Elements</span></span>  
  
|<span data-ttu-id="ae68f-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="ae68f-125">Element</span></span>|<span data-ttu-id="ae68f-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ae68f-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ae68f-127">\<identity></span><span class="sxs-lookup"><span data-stu-id="ae68f-127">\<identity></span></span>](identity.md)|<span data-ttu-id="ae68f-128">Specifica l'identità del servizio da autenticare presso il client.</span><span class="sxs-lookup"><span data-stu-id="ae68f-128">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="ae68f-129">Esempio</span><span class="sxs-lookup"><span data-stu-id="ae68f-129">Example</span></span>  
 <span data-ttu-id="ae68f-130">Nel codice di configurazione seguente viene specificato il DNS di un certificato X.509 usato per autenticare un server.</span><span class="sxs-lookup"><span data-stu-id="ae68f-130">The following configuration code specifies the DNS of an X.509 certificate that is used to authenticate a server.</span></span>  
  
```xml  
<identity>
  <dns value = "www.cohowinery.com" />
</identity>
```  
  
## <a name="see-also"></a><span data-ttu-id="ae68f-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ae68f-131">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.DnsEndpointIdentity>
- [<span data-ttu-id="ae68f-132">Identità del servizio e autenticazione</span><span class="sxs-lookup"><span data-stu-id="ae68f-132">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="ae68f-133">\<identity></span><span class="sxs-lookup"><span data-stu-id="ae68f-133">\<identity></span></span>](identity.md)

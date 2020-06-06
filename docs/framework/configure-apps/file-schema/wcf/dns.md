---
title: <dns>
ms.date: 03/30/2017
ms.assetid: 81819dae-4825-43b7-bccd-f16d2d3d2f06
ms.openlocfilehash: e49a564c9793b371425b2b787586bb9d3cbed58b
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "77452227"
---
# \<dns>
<span data-ttu-id="fc9a1-101">Specifica l'identità prevista del server.</span><span class="sxs-lookup"><span data-stu-id="fc9a1-101">Specifies the expected identity of the server.</span></span> <span data-ttu-id="fc9a1-102">Questa identità è valida per la modalità di autenticazione tramite certificato X509 se il certificato del server contiene un DNS con lo stesso valore.</span><span class="sxs-lookup"><span data-stu-id="fc9a1-102">This identity is valid for X509 Certificate authentication mode if the server’s certificate contains a DNS with the same value.</span></span> <span data-ttu-id="fc9a1-103">Questa identità è inoltre valida per la modalità di autenticazione Windows se il nome SPN presenta lo stesso valore.</span><span class="sxs-lookup"><span data-stu-id="fc9a1-103">It is also valid for Windows authentication mode if the SPN has the same value.</span></span>  
  
<span data-ttu-id="fc9a1-104">Per ulteriori informazioni sull'impostazione del valore dell'elemento, vedere [identità e autenticazione del servizio](../../../wcf/feature-details/service-identity-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="fc9a1-104">For more information about setting the element value, see [Service Identity and Authentication](../../../wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpoint>**](endpoint-of-client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<identity>**](identity.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<dns>**  
  
## <a name="syntax"></a><span data-ttu-id="fc9a1-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fc9a1-105">Syntax</span></span>  
  
```xml  
<dns value = "String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fc9a1-106">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="fc9a1-106">Attributes and Elements</span></span>  
 <span data-ttu-id="fc9a1-107">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="fc9a1-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fc9a1-108">Attributi</span><span class="sxs-lookup"><span data-stu-id="fc9a1-108">Attributes</span></span>  
  
|<span data-ttu-id="fc9a1-109">Attributo</span><span class="sxs-lookup"><span data-stu-id="fc9a1-109">Attribute</span></span>|<span data-ttu-id="fc9a1-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fc9a1-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="fc9a1-111">Valore</span><span class="sxs-lookup"><span data-stu-id="fc9a1-111">value</span></span>|<span data-ttu-id="fc9a1-112">DNS del certificato.</span><span class="sxs-lookup"><span data-stu-id="fc9a1-112">The DNS of the certificate.</span></span> <span data-ttu-id="fc9a1-113">DNS è un protocollo conforme a standard di settore usato per individuare i computer di una rete basata su IP.</span><span class="sxs-lookup"><span data-stu-id="fc9a1-113">DNS is an industry-standard protocol used to locate computers on an IP-based network.</span></span> <span data-ttu-id="fc9a1-114">Gli utenti possono ricordare i nomi visualizzati, ad esempio `https://go.microsoft.com/fwlink/?prd=10929` o `https://go.microsoft.com/fwlink/?LinkID=96165` , più semplici degli indirizzi basati su numeri, ad esempio 207.46.131.137.</span><span class="sxs-lookup"><span data-stu-id="fc9a1-114">Users can remember display names, such as `https://go.microsoft.com/fwlink/?prd=10929` or `https://go.microsoft.com/fwlink/?LinkID=96165`, easier than number-based addresses, such as 207.46.131.137.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fc9a1-115">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="fc9a1-115">Child Elements</span></span>  
 <span data-ttu-id="fc9a1-116">No.</span><span class="sxs-lookup"><span data-stu-id="fc9a1-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="fc9a1-117">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="fc9a1-117">Parent Elements</span></span>  
  
|<span data-ttu-id="fc9a1-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="fc9a1-118">Element</span></span>|<span data-ttu-id="fc9a1-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fc9a1-119">Description</span></span>|  
|-------------|-----------------|  
|[\<identity>](identity.md)|<span data-ttu-id="fc9a1-120">Specifica l'identità del servizio da autenticare presso il client.</span><span class="sxs-lookup"><span data-stu-id="fc9a1-120">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="fc9a1-121">Esempio</span><span class="sxs-lookup"><span data-stu-id="fc9a1-121">Example</span></span>  
 <span data-ttu-id="fc9a1-122">Nel codice di configurazione seguente viene specificato il DNS di un certificato X.509 usato per autenticare un server.</span><span class="sxs-lookup"><span data-stu-id="fc9a1-122">The following configuration code specifies the DNS of an X.509 certificate that is used to authenticate a server.</span></span>  
  
```xml  
<identity>
  <dns value = "www.cohowinery.com" />
</identity>
```  
  
## <a name="see-also"></a><span data-ttu-id="fc9a1-123">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="fc9a1-123">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.DnsEndpointIdentity>
- [<span data-ttu-id="fc9a1-124">Identità del servizio e autenticazione</span><span class="sxs-lookup"><span data-stu-id="fc9a1-124">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [\<identity>](identity.md)

---
title: '&lt;DNS&gt;'
ms.date: 03/30/2017
ms.assetid: 81819dae-4825-43b7-bccd-f16d2d3d2f06
ms.openlocfilehash: 6125bf157d04a1b0298a183465d11a18ac3786f0
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
ms.locfileid: "32746735"
---
# <a name="ltdnsgt"></a><span data-ttu-id="c324a-102">&lt;DNS&gt;</span><span class="sxs-lookup"><span data-stu-id="c324a-102">&lt;dns&gt;</span></span>
<span data-ttu-id="c324a-103">Specifica l'identità prevista del server.</span><span class="sxs-lookup"><span data-stu-id="c324a-103">Specifies the expected identity of the server.</span></span> <span data-ttu-id="c324a-104">Questa identità è valida per la modalità di autenticazione tramite certificato X509 se il certificato del server contiene un DNS con lo stesso valore.</span><span class="sxs-lookup"><span data-stu-id="c324a-104">This identity is valid for X509 Certificate authentication mode if the server’s certificate contains a DNS with the same value.</span></span> <span data-ttu-id="c324a-105">Questa identità è inoltre valida per la modalità di autenticazione Windows se il nome SPN presenta lo stesso valore.</span><span class="sxs-lookup"><span data-stu-id="c324a-105">It is also valid for Windows authentication mode if the SPN has the same value.</span></span>  
  
 <span data-ttu-id="c324a-106">Per ulteriori informazioni sull'impostazione del valore dell'elemento, vedere [autenticazione e identità del servizio](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="c324a-106">For more information about setting the element value, see [Service Identity and Authentication](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
 <span data-ttu-id="c324a-107">\<identità ></span><span class="sxs-lookup"><span data-stu-id="c324a-107">\<identity></span></span>  
<span data-ttu-id="c324a-108">\<DNS ></span><span class="sxs-lookup"><span data-stu-id="c324a-108">\<dns></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c324a-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c324a-109">Syntax</span></span>  
  
```xml  
<dns value = "String" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c324a-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="c324a-110">Attributes and Elements</span></span>  
 <span data-ttu-id="c324a-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="c324a-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c324a-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="c324a-112">Attributes</span></span>  
  
|<span data-ttu-id="c324a-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="c324a-113">Attribute</span></span>|<span data-ttu-id="c324a-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c324a-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c324a-115">Valore</span><span class="sxs-lookup"><span data-stu-id="c324a-115">value</span></span>|<span data-ttu-id="c324a-116">DNS del certificato.</span><span class="sxs-lookup"><span data-stu-id="c324a-116">The DNS of the certificate.</span></span> <span data-ttu-id="c324a-117">DNS è un protocollo conforme a standard di settore usato per individuare i computer di una rete basata su IP.</span><span class="sxs-lookup"><span data-stu-id="c324a-117">DNS is an industry-standard protocol used to locate computers on an IP-based network.</span></span> <span data-ttu-id="c324a-118">Gli utenti possono ricordare i nomi visualizzati, ad esempio [ http://go.microsoft.com/fwlink/?prd=10929 ](http://go.microsoft.com/fwlink/?prd=10929) o [ http://go.microsoft.com/fwlink/?LinkID=96165 ](http://go.microsoft.com/fwlink/?LinkID=96165), anziché dover usare indirizzi numerici, ad esempio 207.46.131.137.</span><span class="sxs-lookup"><span data-stu-id="c324a-118">Users can remember display names, such as [http://go.microsoft.com/fwlink/?prd=10929](http://go.microsoft.com/fwlink/?prd=10929) or [http://go.microsoft.com/fwlink/?LinkID=96165](http://go.microsoft.com/fwlink/?LinkID=96165), easier than number-based addresses, such as 207.46.131.137.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c324a-119">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="c324a-119">Child Elements</span></span>  
 <span data-ttu-id="c324a-120">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="c324a-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c324a-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="c324a-121">Parent Elements</span></span>  
  
|<span data-ttu-id="c324a-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="c324a-122">Element</span></span>|<span data-ttu-id="c324a-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c324a-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c324a-124">\<identità ></span><span class="sxs-lookup"><span data-stu-id="c324a-124">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="c324a-125">Specifica l'identità del servizio da autenticare presso il client.</span><span class="sxs-lookup"><span data-stu-id="c324a-125">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="c324a-126">Esempio</span><span class="sxs-lookup"><span data-stu-id="c324a-126">Example</span></span>  
 <span data-ttu-id="c324a-127">Nel codice di configurazione seguente viene specificato il DNS di un certificato X.509 usato per autenticare un server.</span><span class="sxs-lookup"><span data-stu-id="c324a-127">The following configuration code specifies the DNS of an X.509 certificate that is used to authenticate a server.</span></span>  
  
```xml  
<identity>  
  <dns value = "www.cohowinery.com" />  
</identity>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c324a-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c324a-128">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.IdentityElement>  
 <xref:System.ServiceModel.EndpointAddress>  
 <xref:System.ServiceModel.EndpointAddress.Identity%2A>  
 <xref:System.ServiceModel.DnsEndpointIdentity>  
 [<span data-ttu-id="c324a-129">Identità del servizio e autenticazione</span><span class="sxs-lookup"><span data-stu-id="c324a-129">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="c324a-130">\<identità ></span><span class="sxs-lookup"><span data-stu-id="c324a-130">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)

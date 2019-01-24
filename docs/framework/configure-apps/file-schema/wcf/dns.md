---
title: '&lt;dns&gt;'
ms.date: 03/30/2017
ms.assetid: 81819dae-4825-43b7-bccd-f16d2d3d2f06
ms.openlocfilehash: 68cbb25b79bbda301c29d72800a125c7a6ba0b6f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54616459"
---
# <a name="ltdnsgt"></a><span data-ttu-id="844b0-102">&lt;dns&gt;</span><span class="sxs-lookup"><span data-stu-id="844b0-102">&lt;dns&gt;</span></span>
<span data-ttu-id="844b0-103">Specifica l'identità prevista del server.</span><span class="sxs-lookup"><span data-stu-id="844b0-103">Specifies the expected identity of the server.</span></span> <span data-ttu-id="844b0-104">Questa identità è valida per la modalità di autenticazione tramite certificato X509 se il certificato del server contiene un DNS con lo stesso valore.</span><span class="sxs-lookup"><span data-stu-id="844b0-104">This identity is valid for X509 Certificate authentication mode if the server’s certificate contains a DNS with the same value.</span></span> <span data-ttu-id="844b0-105">Questa identità è inoltre valida per la modalità di autenticazione Windows se il nome SPN presenta lo stesso valore.</span><span class="sxs-lookup"><span data-stu-id="844b0-105">It is also valid for Windows authentication mode if the SPN has the same value.</span></span>  
  
 <span data-ttu-id="844b0-106">Per altre informazioni sull'impostazione del valore dell'elemento, vedere [identità del servizio e autenticazione](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="844b0-106">For more information about setting the element value, see [Service Identity and Authentication](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
 <span data-ttu-id="844b0-107">\<identity></span><span class="sxs-lookup"><span data-stu-id="844b0-107">\<identity></span></span>  
<span data-ttu-id="844b0-108">\<dns></span><span class="sxs-lookup"><span data-stu-id="844b0-108">\<dns></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="844b0-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="844b0-109">Syntax</span></span>  
  
```xml  
<dns value = "String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="844b0-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="844b0-110">Attributes and Elements</span></span>  
 <span data-ttu-id="844b0-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="844b0-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="844b0-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="844b0-112">Attributes</span></span>  
  
|<span data-ttu-id="844b0-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="844b0-113">Attribute</span></span>|<span data-ttu-id="844b0-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="844b0-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="844b0-115">Valore</span><span class="sxs-lookup"><span data-stu-id="844b0-115">value</span></span>|<span data-ttu-id="844b0-116">DNS del certificato.</span><span class="sxs-lookup"><span data-stu-id="844b0-116">The DNS of the certificate.</span></span> <span data-ttu-id="844b0-117">DNS è un protocollo conforme a standard di settore usato per individuare i computer di una rete basata su IP.</span><span class="sxs-lookup"><span data-stu-id="844b0-117">DNS is an industry-standard protocol used to locate computers on an IP-based network.</span></span> <span data-ttu-id="844b0-118">Gli utenti in grado di memorizzare i nomi visualizzati, ad esempio [ https://go.microsoft.com/fwlink/?prd=10929 ](https://go.microsoft.com/fwlink/?prd=10929) oppure [ https://go.microsoft.com/fwlink/?LinkID=96165 ](https://go.microsoft.com/fwlink/?LinkID=96165), più facile che dover utilizzare indirizzi numerici, ad esempio 207.46.131.137.</span><span class="sxs-lookup"><span data-stu-id="844b0-118">Users can remember display names, such as [https://go.microsoft.com/fwlink/?prd=10929](https://go.microsoft.com/fwlink/?prd=10929) or [https://go.microsoft.com/fwlink/?LinkID=96165](https://go.microsoft.com/fwlink/?LinkID=96165), easier than number-based addresses, such as 207.46.131.137.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="844b0-119">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="844b0-119">Child Elements</span></span>  
 <span data-ttu-id="844b0-120">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="844b0-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="844b0-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="844b0-121">Parent Elements</span></span>  
  
|<span data-ttu-id="844b0-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="844b0-122">Element</span></span>|<span data-ttu-id="844b0-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="844b0-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="844b0-124">\<identity></span><span class="sxs-lookup"><span data-stu-id="844b0-124">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="844b0-125">Specifica l'identità del servizio da autenticare presso il client.</span><span class="sxs-lookup"><span data-stu-id="844b0-125">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="844b0-126">Esempio</span><span class="sxs-lookup"><span data-stu-id="844b0-126">Example</span></span>  
 <span data-ttu-id="844b0-127">Nel codice di configurazione seguente viene specificato il DNS di un certificato X.509 usato per autenticare un server.</span><span class="sxs-lookup"><span data-stu-id="844b0-127">The following configuration code specifies the DNS of an X.509 certificate that is used to authenticate a server.</span></span>  
  
```xml  
<identity>
  <dns value = "www.cohowinery.com" />
</identity>
```  
  
## <a name="see-also"></a><span data-ttu-id="844b0-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="844b0-128">See also</span></span>
- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.DnsEndpointIdentity>
- [<span data-ttu-id="844b0-129">Identità del servizio e autenticazione</span><span class="sxs-lookup"><span data-stu-id="844b0-129">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="844b0-130">\<identity></span><span class="sxs-lookup"><span data-stu-id="844b0-130">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)

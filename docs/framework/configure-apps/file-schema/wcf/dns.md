---
title: <dns>
ms.date: 03/30/2017
ms.assetid: 81819dae-4825-43b7-bccd-f16d2d3d2f06
ms.openlocfilehash: 26b45b17ecd7bbd3fffb5d03553834ec22eedc62
ms.sourcegitcommit: 438919211260bb415fc8f96ca3eabc33cf2d681d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/16/2019
ms.locfileid: "59611172"
---
# <a name="dns"></a><span data-ttu-id="90f7d-101">\<dns></span><span class="sxs-lookup"><span data-stu-id="90f7d-101">\<dns></span></span>
<span data-ttu-id="90f7d-102">Specifica l'identità prevista del server.</span><span class="sxs-lookup"><span data-stu-id="90f7d-102">Specifies the expected identity of the server.</span></span> <span data-ttu-id="90f7d-103">Questa identità è valida per la modalità di autenticazione tramite certificato X509 se il certificato del server contiene un DNS con lo stesso valore.</span><span class="sxs-lookup"><span data-stu-id="90f7d-103">This identity is valid for X509 Certificate authentication mode if the server’s certificate contains a DNS with the same value.</span></span> <span data-ttu-id="90f7d-104">Questa identità è inoltre valida per la modalità di autenticazione Windows se il nome SPN presenta lo stesso valore.</span><span class="sxs-lookup"><span data-stu-id="90f7d-104">It is also valid for Windows authentication mode if the SPN has the same value.</span></span>  
  
 <span data-ttu-id="90f7d-105">Per altre informazioni sull'impostazione del valore dell'elemento, vedere [identità del servizio e autenticazione](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="90f7d-105">For more information about setting the element value, see [Service Identity and Authentication](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
 <span data-ttu-id="90f7d-106">\<identity></span><span class="sxs-lookup"><span data-stu-id="90f7d-106">\<identity></span></span>  
<span data-ttu-id="90f7d-107">\<dns></span><span class="sxs-lookup"><span data-stu-id="90f7d-107">\<dns></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90f7d-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="90f7d-108">Syntax</span></span>  
  
```xml  
<dns value = "String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="90f7d-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="90f7d-109">Attributes and Elements</span></span>  
 <span data-ttu-id="90f7d-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="90f7d-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="90f7d-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="90f7d-111">Attributes</span></span>  
  
|<span data-ttu-id="90f7d-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="90f7d-112">Attribute</span></span>|<span data-ttu-id="90f7d-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="90f7d-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="90f7d-114">predefinito</span><span class="sxs-lookup"><span data-stu-id="90f7d-114">value</span></span>|<span data-ttu-id="90f7d-115">DNS del certificato.</span><span class="sxs-lookup"><span data-stu-id="90f7d-115">The DNS of the certificate.</span></span> <span data-ttu-id="90f7d-116">DNS è un protocollo conforme a standard di settore usato per individuare i computer di una rete basata su IP.</span><span class="sxs-lookup"><span data-stu-id="90f7d-116">DNS is an industry-standard protocol used to locate computers on an IP-based network.</span></span> <span data-ttu-id="90f7d-117">Gli utenti in grado di memorizzare i nomi visualizzati, ad esempio <https://go.microsoft.com/fwlink/?prd=10929> oppure [ https://go.microsoft.com/fwlink/?LinkID=96165 ](https://go.microsoft.com/fwlink/?LinkID=96165), più facile che dover utilizzare indirizzi numerici, ad esempio 207.46.131.137.</span><span class="sxs-lookup"><span data-stu-id="90f7d-117">Users can remember display names, such as <https://go.microsoft.com/fwlink/?prd=10929> or [https://go.microsoft.com/fwlink/?LinkID=96165](https://go.microsoft.com/fwlink/?LinkID=96165), easier than number-based addresses, such as 207.46.131.137.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="90f7d-118">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="90f7d-118">Child Elements</span></span>  
 <span data-ttu-id="90f7d-119">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="90f7d-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="90f7d-120">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="90f7d-120">Parent Elements</span></span>  
  
|<span data-ttu-id="90f7d-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="90f7d-121">Element</span></span>|<span data-ttu-id="90f7d-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="90f7d-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="90f7d-123">\<identity></span><span class="sxs-lookup"><span data-stu-id="90f7d-123">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="90f7d-124">Specifica l'identità del servizio da autenticare presso il client.</span><span class="sxs-lookup"><span data-stu-id="90f7d-124">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="90f7d-125">Esempio</span><span class="sxs-lookup"><span data-stu-id="90f7d-125">Example</span></span>  
 <span data-ttu-id="90f7d-126">Nel codice di configurazione seguente viene specificato il DNS di un certificato X.509 usato per autenticare un server.</span><span class="sxs-lookup"><span data-stu-id="90f7d-126">The following configuration code specifies the DNS of an X.509 certificate that is used to authenticate a server.</span></span>  
  
```xml  
<identity>
  <dns value = "www.cohowinery.com" />
</identity>
```  
  
## <a name="see-also"></a><span data-ttu-id="90f7d-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="90f7d-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.DnsEndpointIdentity>
- [<span data-ttu-id="90f7d-128">Identità del servizio e autenticazione</span><span class="sxs-lookup"><span data-stu-id="90f7d-128">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="90f7d-129">\<identity></span><span class="sxs-lookup"><span data-stu-id="90f7d-129">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)

---
title: '&lt;DNS&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 81819dae-4825-43b7-bccd-f16d2d3d2f06
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4c7585cfa85d805a3d1454b0c16e38eee297280a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ltdnsgt"></a><span data-ttu-id="47c99-102">&lt;DNS&gt;</span><span class="sxs-lookup"><span data-stu-id="47c99-102">&lt;dns&gt;</span></span>
<span data-ttu-id="47c99-103">Specifica l'identità prevista del server.</span><span class="sxs-lookup"><span data-stu-id="47c99-103">Specifies the expected identity of the server.</span></span> <span data-ttu-id="47c99-104">Questa identità è valida per la modalità di autenticazione tramite certificato X509 se il certificato del server contiene un DNS con lo stesso valore.</span><span class="sxs-lookup"><span data-stu-id="47c99-104">This identity is valid for X509 Certificate authentication mode if the server’s certificate contains a DNS with the same value.</span></span> <span data-ttu-id="47c99-105">Questa identità è inoltre valida per la modalità di autenticazione Windows se il nome SPN presenta lo stesso valore.</span><span class="sxs-lookup"><span data-stu-id="47c99-105">It is also valid for Windows authentication mode if the SPN has the same value.</span></span>  
  
 <span data-ttu-id="47c99-106">Per ulteriori informazioni sull'impostazione del valore dell'elemento, vedere [autenticazione e identità del servizio](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="47c99-106">For more information about setting the element value, see [Service Identity and Authentication](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
 <span data-ttu-id="47c99-107">\<identità ></span><span class="sxs-lookup"><span data-stu-id="47c99-107">\<identity></span></span>  
<span data-ttu-id="47c99-108">\<DNS ></span><span class="sxs-lookup"><span data-stu-id="47c99-108">\<dns></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="47c99-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="47c99-109">Syntax</span></span>  
  
```xml  
<dns value = "String" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="47c99-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="47c99-110">Attributes and Elements</span></span>  
 <span data-ttu-id="47c99-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="47c99-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="47c99-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="47c99-112">Attributes</span></span>  
  
|<span data-ttu-id="47c99-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="47c99-113">Attribute</span></span>|<span data-ttu-id="47c99-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="47c99-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="47c99-115">Valore</span><span class="sxs-lookup"><span data-stu-id="47c99-115">value</span></span>|<span data-ttu-id="47c99-116">DNS del certificato.</span><span class="sxs-lookup"><span data-stu-id="47c99-116">The DNS of the certificate.</span></span> <span data-ttu-id="47c99-117">DNS è un protocollo conforme a standard di settore usato per individuare i computer di una rete basata su IP.</span><span class="sxs-lookup"><span data-stu-id="47c99-117">DNS is an industry-standard protocol used to locate computers on an IP-based network.</span></span> <span data-ttu-id="47c99-118">Gli utenti possono ricordare i nomi visualizzati, ad esempio [http://go.microsoft.com/fwlink/?prd=10929](http://go.microsoft.com/fwlink/?prd=10929) o [http://go.microsoft.com/fwlink/?LinkID=96165](http://go.microsoft.com/fwlink/?LinkID=96165), anziché gli indirizzi basata sul numero, ad esempio 207.46.131.137.</span><span class="sxs-lookup"><span data-stu-id="47c99-118">Users can remember display names, such as [http://go.microsoft.com/fwlink/?prd=10929](http://go.microsoft.com/fwlink/?prd=10929) or [http://go.microsoft.com/fwlink/?LinkID=96165](http://go.microsoft.com/fwlink/?LinkID=96165), easier than number-based addresses, such as 207.46.131.137.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="47c99-119">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="47c99-119">Child Elements</span></span>  
 <span data-ttu-id="47c99-120">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="47c99-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="47c99-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="47c99-121">Parent Elements</span></span>  
  
|<span data-ttu-id="47c99-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="47c99-122">Element</span></span>|<span data-ttu-id="47c99-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="47c99-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="47c99-124">\<identità ></span><span class="sxs-lookup"><span data-stu-id="47c99-124">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="47c99-125">Specifica l'identità del servizio da autenticare presso il client.</span><span class="sxs-lookup"><span data-stu-id="47c99-125">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="47c99-126">Esempio</span><span class="sxs-lookup"><span data-stu-id="47c99-126">Example</span></span>  
 <span data-ttu-id="47c99-127">Nel codice di configurazione seguente viene specificato il DNS di un certificato X.509 usato per autenticare un server.</span><span class="sxs-lookup"><span data-stu-id="47c99-127">The following configuration code specifies the DNS of an X.509 certificate that is used to authenticate a server.</span></span>  
  
```xml  
<identity>  
  <dns value = "www.cohowinery.com" />  
</identity>  
```  
  
## <a name="see-also"></a><span data-ttu-id="47c99-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="47c99-128">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.IdentityElement>  
 <xref:System.ServiceModel.EndpointAddress>  
 <xref:System.ServiceModel.EndpointAddress.Identity%2A>  
 <xref:System.ServiceModel.DnsEndpointIdentity>  
 [<span data-ttu-id="47c99-129">Identità del servizio e autenticazione</span><span class="sxs-lookup"><span data-stu-id="47c99-129">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="47c99-130">\<identità ></span><span class="sxs-lookup"><span data-stu-id="47c99-130">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)

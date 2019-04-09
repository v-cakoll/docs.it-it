---
title: <rsa>
ms.date: 03/30/2017
ms.assetid: ae1f2267-e40d-42ff-8abf-06ab7067bdb9
ms.openlocfilehash: 0e307069bd3a98153cc66147ba7bcf511cf13a8e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59091655"
---
# <a name="rsa"></a><span data-ttu-id="35632-101">\<rsa></span><span class="sxs-lookup"><span data-stu-id="35632-101">\<rsa></span></span>
<span data-ttu-id="35632-102">Un client WCF protetto che si connette a un endpoint con questa identità verifica che le attestazioni presentate dal server contengano un'attestazione contenente a sua volta la chiave pubblica RSA usata per costruire tale identità.</span><span class="sxs-lookup"><span data-stu-id="35632-102">A secure WCF client that connects to an endpoint with this identity verifies that the claims presented by the server contain a claim that contains the RSA public key used to construct this identity.</span></span>  
  
 <span data-ttu-id="35632-103">\<identity></span><span class="sxs-lookup"><span data-stu-id="35632-103">\<identity></span></span>  
<span data-ttu-id="35632-104">\<rsa></span><span class="sxs-lookup"><span data-stu-id="35632-104">\<rsa></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35632-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="35632-105">Syntax</span></span>  
  
```xml  
<rsa value="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="35632-106">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="35632-106">Attributes and Elements</span></span>  
 <span data-ttu-id="35632-107">Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.</span><span class="sxs-lookup"><span data-stu-id="35632-107">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="35632-108">Attributi</span><span class="sxs-lookup"><span data-stu-id="35632-108">Attributes</span></span>  
  
|<span data-ttu-id="35632-109">Attributo</span><span class="sxs-lookup"><span data-stu-id="35632-109">Attribute</span></span>|<span data-ttu-id="35632-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="35632-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="35632-111">predefinito</span><span class="sxs-lookup"><span data-stu-id="35632-111">value</span></span>|<span data-ttu-id="35632-112">Stringa facoltativa.</span><span class="sxs-lookup"><span data-stu-id="35632-112">Optional String.</span></span> <span data-ttu-id="35632-113">Valore della chiave pubblica RSA con cui eseguire il confronto nel client.</span><span class="sxs-lookup"><span data-stu-id="35632-113">The RSA public key value to be compared with on the client.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="35632-114">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="35632-114">Child Elements</span></span>  
 <span data-ttu-id="35632-115">nessuno</span><span class="sxs-lookup"><span data-stu-id="35632-115">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="35632-116">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="35632-116">Parent Elements</span></span>  
  
|<span data-ttu-id="35632-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="35632-117">Element</span></span>|<span data-ttu-id="35632-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="35632-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="35632-119">\<identity></span><span class="sxs-lookup"><span data-stu-id="35632-119">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="35632-120">Specifica l'identità del servizio da autenticare presso il client.</span><span class="sxs-lookup"><span data-stu-id="35632-120">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="35632-121">Note</span><span class="sxs-lookup"><span data-stu-id="35632-121">Remarks</span></span>  
 <span data-ttu-id="35632-122">Un controllo RSA consente di restringere specificamente l'autenticazione a un solo certificato in base alla relativa chiave RSA o in base a un valore di chiave RSA generato manualmente.</span><span class="sxs-lookup"><span data-stu-id="35632-122">A RSA check enables you to specifically restrict authentication to a single certificate based upon its RSA key or generated your own RSA key value.</span></span> <span data-ttu-id="35632-123">Ciò consente l'autenticazione più restrittiva di una chiave RSA specifica a spese del servizio, che non funziona più con i client esistenti se il valore della chiave RSA viene modificato.</span><span class="sxs-lookup"><span data-stu-id="35632-123">This enables stricter authentication of a specific RSA key at the expense of the service no longer working with existing clients if the RSA key value is changed.</span></span>  
  
 <span data-ttu-id="35632-124">Per altre informazioni sull'utilizzo dell'identità per convalidare un servizio a un client, vedere [identità del servizio e autenticazione](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="35632-124">For more information about using identity to validate a service to a client, see [Service Identity and Authentication](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="35632-125">Esempio</span><span class="sxs-lookup"><span data-stu-id="35632-125">Example</span></span>  
 <span data-ttu-id="35632-126">Nel codice di configurazione seguente viene specificato il valore della chiave pubblica di un certificato X.509 usato per autenticare un server.</span><span class="sxs-lookup"><span data-stu-id="35632-126">The following configuration code specifies the public key value of an X.509 certificate that is used to authenticate a server.</span></span>  
  
```xml  
<identity>
  <rsa value="0000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000" />
</identity>
```  
  
## <a name="see-also"></a><span data-ttu-id="35632-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="35632-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.RsaEndpointIdentity>
- [<span data-ttu-id="35632-128">Identità del servizio e autenticazione</span><span class="sxs-lookup"><span data-stu-id="35632-128">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="35632-129">\<identity></span><span class="sxs-lookup"><span data-stu-id="35632-129">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)

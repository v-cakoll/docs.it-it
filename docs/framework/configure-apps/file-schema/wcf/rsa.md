---
title: <rsa>
ms.date: 03/30/2017
ms.assetid: ae1f2267-e40d-42ff-8abf-06ab7067bdb9
ms.openlocfilehash: dd8e5ab11a7c019a8fe967f1c14b88a922a16c33
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69934743"
---
# <a name="rsa"></a><span data-ttu-id="79bd1-101">\<rsa></span><span class="sxs-lookup"><span data-stu-id="79bd1-101">\<rsa></span></span>
<span data-ttu-id="79bd1-102">Un client WCF protetto che si connette a un endpoint con questa identità verifica che le attestazioni presentate dal server contengano un'attestazione contenente a sua volta la chiave pubblica RSA usata per costruire tale identità.</span><span class="sxs-lookup"><span data-stu-id="79bd1-102">A secure WCF client that connects to an endpoint with this identity verifies that the claims presented by the server contain a claim that contains the RSA public key used to construct this identity.</span></span>  
  
 <span data-ttu-id="79bd1-103">\<identity></span><span class="sxs-lookup"><span data-stu-id="79bd1-103">\<identity></span></span>  
<span data-ttu-id="79bd1-104">\<rsa></span><span class="sxs-lookup"><span data-stu-id="79bd1-104">\<rsa></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="79bd1-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="79bd1-105">Syntax</span></span>  
  
```xml  
<rsa value="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="79bd1-106">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="79bd1-106">Attributes and Elements</span></span>  
 <span data-ttu-id="79bd1-107">Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.</span><span class="sxs-lookup"><span data-stu-id="79bd1-107">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="79bd1-108">Attributi</span><span class="sxs-lookup"><span data-stu-id="79bd1-108">Attributes</span></span>  
  
|<span data-ttu-id="79bd1-109">Attributo</span><span class="sxs-lookup"><span data-stu-id="79bd1-109">Attribute</span></span>|<span data-ttu-id="79bd1-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="79bd1-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="79bd1-111">value</span><span class="sxs-lookup"><span data-stu-id="79bd1-111">value</span></span>|<span data-ttu-id="79bd1-112">Stringa facoltativa.</span><span class="sxs-lookup"><span data-stu-id="79bd1-112">Optional String.</span></span> <span data-ttu-id="79bd1-113">Valore della chiave pubblica RSA con cui eseguire il confronto nel client.</span><span class="sxs-lookup"><span data-stu-id="79bd1-113">The RSA public key value to be compared with on the client.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="79bd1-114">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="79bd1-114">Child Elements</span></span>  
 <span data-ttu-id="79bd1-115">Nessuna</span><span class="sxs-lookup"><span data-stu-id="79bd1-115">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="79bd1-116">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="79bd1-116">Parent Elements</span></span>  
  
|<span data-ttu-id="79bd1-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="79bd1-117">Element</span></span>|<span data-ttu-id="79bd1-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="79bd1-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="79bd1-119">\<identity></span><span class="sxs-lookup"><span data-stu-id="79bd1-119">\<identity></span></span>](identity.md)|<span data-ttu-id="79bd1-120">Specifica l'identità del servizio da autenticare presso il client.</span><span class="sxs-lookup"><span data-stu-id="79bd1-120">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="79bd1-121">Note</span><span class="sxs-lookup"><span data-stu-id="79bd1-121">Remarks</span></span>  
 <span data-ttu-id="79bd1-122">Un controllo RSA consente di restringere specificamente l'autenticazione a un solo certificato in base alla relativa chiave RSA o in base a un valore di chiave RSA generato manualmente.</span><span class="sxs-lookup"><span data-stu-id="79bd1-122">A RSA check enables you to specifically restrict authentication to a single certificate based upon its RSA key or generated your own RSA key value.</span></span> <span data-ttu-id="79bd1-123">Ciò consente l'autenticazione più restrittiva di una chiave RSA specifica a spese del servizio, che non funziona più con i client esistenti se il valore della chiave RSA viene modificato.</span><span class="sxs-lookup"><span data-stu-id="79bd1-123">This enables stricter authentication of a specific RSA key at the expense of the service no longer working with existing clients if the RSA key value is changed.</span></span>  
  
 <span data-ttu-id="79bd1-124">Per ulteriori informazioni sull'utilizzo di Identity per convalidare un servizio a un client, vedere [identità e autenticazione del servizio](../../../wcf/feature-details/service-identity-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="79bd1-124">For more information about using identity to validate a service to a client, see [Service Identity and Authentication](../../../wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="79bd1-125">Esempio</span><span class="sxs-lookup"><span data-stu-id="79bd1-125">Example</span></span>  
 <span data-ttu-id="79bd1-126">Nel codice di configurazione seguente viene specificato il valore della chiave pubblica di un certificato X.509 usato per autenticare un server.</span><span class="sxs-lookup"><span data-stu-id="79bd1-126">The following configuration code specifies the public key value of an X.509 certificate that is used to authenticate a server.</span></span>  
  
```xml  
<identity>
  <rsa value="0000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000" />
</identity>
```  
  
## <a name="see-also"></a><span data-ttu-id="79bd1-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="79bd1-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.RsaEndpointIdentity>
- [<span data-ttu-id="79bd1-128">Identità del servizio e autenticazione</span><span class="sxs-lookup"><span data-stu-id="79bd1-128">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="79bd1-129">\<identity></span><span class="sxs-lookup"><span data-stu-id="79bd1-129">\<identity></span></span>](identity.md)

---
title: <rsa>
ms.date: 03/30/2017
ms.assetid: ae1f2267-e40d-42ff-8abf-06ab7067bdb9
ms.openlocfilehash: 0e1651f563bdb2b2b24eacacf7bfe387e33a82c7
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855049"
---
# \<rsa>
<span data-ttu-id="6fc94-101">Un client WCF protetto che si connette a un endpoint con questa identità verifica che le attestazioni presentate dal server contengano un'attestazione contenente a sua volta la chiave pubblica RSA usata per costruire tale identità.</span><span class="sxs-lookup"><span data-stu-id="6fc94-101">A secure WCF client that connects to an endpoint with this identity verifies that the claims presented by the server contain a claim that contains the RSA public key used to construct this identity.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpoint>**](endpoint-of-client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<identity>**](identity.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<rsa>**  
  
## <a name="syntax"></a><span data-ttu-id="6fc94-102">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6fc94-102">Syntax</span></span>  
  
```xml  
<rsa value="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6fc94-103">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="6fc94-103">Attributes and Elements</span></span>  
 <span data-ttu-id="6fc94-104">Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.</span><span class="sxs-lookup"><span data-stu-id="6fc94-104">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6fc94-105">Attributi</span><span class="sxs-lookup"><span data-stu-id="6fc94-105">Attributes</span></span>  
  
|<span data-ttu-id="6fc94-106">Attributo</span><span class="sxs-lookup"><span data-stu-id="6fc94-106">Attribute</span></span>|<span data-ttu-id="6fc94-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6fc94-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6fc94-108">Valore</span><span class="sxs-lookup"><span data-stu-id="6fc94-108">value</span></span>|<span data-ttu-id="6fc94-109">Stringa facoltativa.</span><span class="sxs-lookup"><span data-stu-id="6fc94-109">Optional String.</span></span> <span data-ttu-id="6fc94-110">Valore della chiave pubblica RSA con cui eseguire il confronto nel client.</span><span class="sxs-lookup"><span data-stu-id="6fc94-110">The RSA public key value to be compared with on the client.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6fc94-111">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="6fc94-111">Child Elements</span></span>  
 <span data-ttu-id="6fc94-112">nessuno</span><span class="sxs-lookup"><span data-stu-id="6fc94-112">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6fc94-113">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="6fc94-113">Parent Elements</span></span>  
  
|<span data-ttu-id="6fc94-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="6fc94-114">Element</span></span>|<span data-ttu-id="6fc94-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6fc94-115">Description</span></span>|  
|-------------|-----------------|  
|[\<identity>](identity.md)|<span data-ttu-id="6fc94-116">Specifica l'identità del servizio da autenticare presso il client.</span><span class="sxs-lookup"><span data-stu-id="6fc94-116">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6fc94-117">Commenti</span><span class="sxs-lookup"><span data-stu-id="6fc94-117">Remarks</span></span>  
 <span data-ttu-id="6fc94-118">Un controllo RSA consente di restringere specificamente l'autenticazione a un solo certificato in base alla relativa chiave RSA o in base a un valore di chiave RSA generato manualmente.</span><span class="sxs-lookup"><span data-stu-id="6fc94-118">A RSA check enables you to specifically restrict authentication to a single certificate based upon its RSA key or generated your own RSA key value.</span></span> <span data-ttu-id="6fc94-119">Ciò consente l'autenticazione più restrittiva di una chiave RSA specifica a spese del servizio, che non funziona più con i client esistenti se il valore della chiave RSA viene modificato.</span><span class="sxs-lookup"><span data-stu-id="6fc94-119">This enables stricter authentication of a specific RSA key at the expense of the service no longer working with existing clients if the RSA key value is changed.</span></span>  
  
 <span data-ttu-id="6fc94-120">Per ulteriori informazioni sull'utilizzo di Identity per convalidare un servizio a un client, vedere [identità e autenticazione del servizio](../../../wcf/feature-details/service-identity-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="6fc94-120">For more information about using identity to validate a service to a client, see [Service Identity and Authentication](../../../wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="6fc94-121">Esempio</span><span class="sxs-lookup"><span data-stu-id="6fc94-121">Example</span></span>  
 <span data-ttu-id="6fc94-122">Nel codice di configurazione seguente viene specificato il valore della chiave pubblica di un certificato X.509 usato per autenticare un server.</span><span class="sxs-lookup"><span data-stu-id="6fc94-122">The following configuration code specifies the public key value of an X.509 certificate that is used to authenticate a server.</span></span>  
  
```xml  
<identity>
  <rsa value="0000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000" />
</identity>
```  
  
## <a name="see-also"></a><span data-ttu-id="6fc94-123">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="6fc94-123">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.RsaEndpointIdentity>
- [<span data-ttu-id="6fc94-124">Identità del servizio e autenticazione</span><span class="sxs-lookup"><span data-stu-id="6fc94-124">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [\<identity>](identity.md)

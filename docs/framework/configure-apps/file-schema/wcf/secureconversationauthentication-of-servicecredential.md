---
title: '&lt;secureConversationAuthentication&gt; di &lt;serviceCredential&gt;'
ms.date: 03/30/2017
ms.assetid: 0bd3fac7-befd-4a45-ba51-c200b33be0fd
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 7b56d12793ad35e6f951638465e77b92a66a6fd0
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="ltsecureconversationauthenticationgt-of-ltservicecredentialgt"></a><span data-ttu-id="ece5e-102">&lt;secureConversationAuthentication&gt; di &lt;serviceCredential&gt;</span><span class="sxs-lookup"><span data-stu-id="ece5e-102">&lt;secureConversationAuthentication&gt; of &lt;serviceCredential&gt;</span></span>
<span data-ttu-id="ece5e-103">Specifica le impostazioni per un servizio di conversazione protetta.</span><span class="sxs-lookup"><span data-stu-id="ece5e-103">Specifies the settings for a secure conversation service.</span></span>  
  
 <span data-ttu-id="ece5e-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="ece5e-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="ece5e-105">\<i comportamenti ></span><span class="sxs-lookup"><span data-stu-id="ece5e-105">\<behaviors></span></span>  
<span data-ttu-id="ece5e-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="ece5e-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="ece5e-107">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="ece5e-107">\<behavior></span></span>  
<span data-ttu-id="ece5e-108">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="ece5e-108">\<serviceCredentials></span></span>  
<span data-ttu-id="ece5e-109">\<secureConversationAuthentication ></span><span class="sxs-lookup"><span data-stu-id="ece5e-109">\<secureConversationAuthentication></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ece5e-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ece5e-110">Syntax</span></span>  
  
```xml  
<secureConversationAuthentication securityStateEncoderType="String" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ece5e-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="ece5e-111">Attributes and Elements</span></span>  
 <span data-ttu-id="ece5e-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="ece5e-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ece5e-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="ece5e-113">Attributes</span></span>  
  
|<span data-ttu-id="ece5e-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="ece5e-114">Attribute</span></span>|<span data-ttu-id="ece5e-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ece5e-115">Description</span></span>|  
|---------------|-----------------|  
|`securityStateEncoderType`|<span data-ttu-id="ece5e-116">Stringa che specifica il tipo di <xref:System.ServiceModel.Security.SecurityStateEncoder> da usare.</span><span class="sxs-lookup"><span data-stu-id="ece5e-116">A string that specifies the type of <xref:System.ServiceModel.Security.SecurityStateEncoder> to be used.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ece5e-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="ece5e-117">Child Elements</span></span>  
 <span data-ttu-id="ece5e-118">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="ece5e-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ece5e-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="ece5e-119">Parent Elements</span></span>  
  
|<span data-ttu-id="ece5e-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="ece5e-120">Element</span></span>|<span data-ttu-id="ece5e-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ece5e-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ece5e-122">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="ece5e-122">\<serviceCredentials></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)|<span data-ttu-id="ece5e-123">Specifica la credenziale da usare nell'autenticazione del servizio e le impostazioni relative alla convalida delle credenziali client.</span><span class="sxs-lookup"><span data-stu-id="ece5e-123">Specifies the credential to be used in authenticating the service, and the client credential validation-related settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ece5e-124">Note</span><span class="sxs-lookup"><span data-stu-id="ece5e-124">Remarks</span></span>  
 <span data-ttu-id="ece5e-125">Usare questo elemento di configurazione per specificare un elenco di tipi di attestazione noti per la serializzazione dei cookie del token del contesto di sicurezza (SCT, Security Context Token), oltre a un codificatore per la codifica e la sicurezza delle informazioni sui cookie.</span><span class="sxs-lookup"><span data-stu-id="ece5e-125">Use this configuration element to specify a list of known claim types for the Security Context Token (SCT) cookies serialization, as well as an encoder to encode and secure cookies information.</span></span> <span data-ttu-id="ece5e-126">Per altre informazioni su SCT, vedere <xref:System.ServiceModel.Security.SecureConversationServiceCredential>.</span><span class="sxs-lookup"><span data-stu-id="ece5e-126">For more information on SCT, see <xref:System.ServiceModel.Security.SecureConversationServiceCredential>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ece5e-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ece5e-127">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.SecureConversationServiceElement>  
 <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.SecureConversationAuthentication%2A>  
 <xref:System.ServiceModel.Description.ServiceCredentials.SecureConversationAuthentication%2A>  
 <xref:System.ServiceModel.Security.SecureConversationServiceCredential>

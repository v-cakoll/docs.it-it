---
title: '&lt;secureConversationAuthentication&gt; di &lt;serviceCredential&gt;'
ms.date: 03/30/2017
ms.assetid: 0bd3fac7-befd-4a45-ba51-c200b33be0fd
ms.openlocfilehash: 2c8479c4d8a321c822d49bdc24f359ffad5500e9
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2019
ms.locfileid: "54147187"
---
# <a name="ltsecureconversationauthenticationgt-of-ltservicecredentialgt"></a><span data-ttu-id="03558-102">&lt;secureConversationAuthentication&gt; di &lt;serviceCredential&gt;</span><span class="sxs-lookup"><span data-stu-id="03558-102">&lt;secureConversationAuthentication&gt; of &lt;serviceCredential&gt;</span></span>
<span data-ttu-id="03558-103">Specifica le impostazioni per un servizio di conversazione protetta.</span><span class="sxs-lookup"><span data-stu-id="03558-103">Specifies the settings for a secure conversation service.</span></span>  
  
 <span data-ttu-id="03558-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="03558-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="03558-105">\<i comportamenti ></span><span class="sxs-lookup"><span data-stu-id="03558-105">\<behaviors></span></span>  
<span data-ttu-id="03558-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="03558-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="03558-107">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="03558-107">\<behavior></span></span>  
<span data-ttu-id="03558-108">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="03558-108">\<serviceCredentials></span></span>  
<span data-ttu-id="03558-109">\<secureConversationAuthentication ></span><span class="sxs-lookup"><span data-stu-id="03558-109">\<secureConversationAuthentication></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="03558-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="03558-110">Syntax</span></span>  
  
```xml  
<secureConversationAuthentication securityStateEncoderType="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="03558-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="03558-111">Attributes and Elements</span></span>  
 <span data-ttu-id="03558-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="03558-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="03558-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="03558-113">Attributes</span></span>  
  
|<span data-ttu-id="03558-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="03558-114">Attribute</span></span>|<span data-ttu-id="03558-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="03558-115">Description</span></span>|  
|---------------|-----------------|  
|`securityStateEncoderType`|<span data-ttu-id="03558-116">Stringa che specifica il tipo di <xref:System.ServiceModel.Security.SecurityStateEncoder> da usare.</span><span class="sxs-lookup"><span data-stu-id="03558-116">A string that specifies the type of <xref:System.ServiceModel.Security.SecurityStateEncoder> to be used.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="03558-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="03558-117">Child Elements</span></span>  
 <span data-ttu-id="03558-118">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="03558-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="03558-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="03558-119">Parent Elements</span></span>  
  
|<span data-ttu-id="03558-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="03558-120">Element</span></span>|<span data-ttu-id="03558-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="03558-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="03558-122">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="03558-122">\<serviceCredentials></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)|<span data-ttu-id="03558-123">Specifica la credenziale da usare nell'autenticazione del servizio e le impostazioni relative alla convalida delle credenziali client.</span><span class="sxs-lookup"><span data-stu-id="03558-123">Specifies the credential to be used in authenticating the service, and the client credential validation-related settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="03558-124">Note</span><span class="sxs-lookup"><span data-stu-id="03558-124">Remarks</span></span>  
 <span data-ttu-id="03558-125">Usare questo elemento di configurazione per specificare un elenco di tipi di attestazione noti per la serializzazione dei cookie del token del contesto di sicurezza (SCT, Security Context Token), oltre a un codificatore per la codifica e la sicurezza delle informazioni sui cookie.</span><span class="sxs-lookup"><span data-stu-id="03558-125">Use this configuration element to specify a list of known claim types for the Security Context Token (SCT) cookies serialization, as well as an encoder to encode and secure cookies information.</span></span> <span data-ttu-id="03558-126">Per altre informazioni su SCT, vedere <xref:System.ServiceModel.Security.SecureConversationServiceCredential>.</span><span class="sxs-lookup"><span data-stu-id="03558-126">For more information on SCT, see <xref:System.ServiceModel.Security.SecureConversationServiceCredential>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03558-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="03558-127">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.SecureConversationServiceElement>  
 <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.SecureConversationAuthentication%2A>  
 <xref:System.ServiceModel.Description.ServiceCredentials.SecureConversationAuthentication%2A>  
 <xref:System.ServiceModel.Security.SecureConversationServiceCredential>

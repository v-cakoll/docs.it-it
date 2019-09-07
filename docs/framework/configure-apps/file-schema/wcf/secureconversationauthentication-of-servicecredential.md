---
title: <secureConversationAuthentication> di <serviceCredential>
ms.date: 03/30/2017
ms.assetid: 0bd3fac7-befd-4a45-ba51-c200b33be0fd
ms.openlocfilehash: 336969c654f332ae3d838d8fd6d1c4243838539c
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399929"
---
# <a name="secureconversationauthentication-of-servicecredential"></a><span data-ttu-id="e4b7e-102">\<> SecureConversationAuthentication di \<serviceCredential ></span><span class="sxs-lookup"><span data-stu-id="e4b7e-102">\<secureConversationAuthentication> of \<serviceCredential></span></span>
<span data-ttu-id="e4b7e-103">Specifica le impostazioni per un servizio di conversazione protetta.</span><span class="sxs-lookup"><span data-stu-id="e4b7e-103">Specifies the settings for a secure conversation service.</span></span>  
  
<span data-ttu-id="e4b7e-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="e4b7e-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="e4b7e-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="e4b7e-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="e4b7e-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamenti >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="e4b7e-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="e4b7e-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> serviceBehaviors**](servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="e4b7e-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="e4b7e-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamento >** ](behavior-of-servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="e4b7e-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)</span></span>\
<span data-ttu-id="e4b7e-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> di serviceCredentials**](servicecredentials.md)</span><span class="sxs-lookup"><span data-stu-id="e4b7e-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)</span></span>\
<span data-ttu-id="e4b7e-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> secureConversationAuthentication**</span><span class="sxs-lookup"><span data-stu-id="e4b7e-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<secureConversationAuthentication>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e4b7e-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e4b7e-111">Syntax</span></span>  
  
```xml  
<secureConversationAuthentication securityStateEncoderType="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e4b7e-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="e4b7e-112">Attributes and Elements</span></span>  
 <span data-ttu-id="e4b7e-113">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="e4b7e-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e4b7e-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="e4b7e-114">Attributes</span></span>  
  
|<span data-ttu-id="e4b7e-115">Attributo</span><span class="sxs-lookup"><span data-stu-id="e4b7e-115">Attribute</span></span>|<span data-ttu-id="e4b7e-116">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="e4b7e-116">Description</span></span>|  
|---------------|-----------------|  
|`securityStateEncoderType`|<span data-ttu-id="e4b7e-117">Stringa che specifica il tipo di <xref:System.ServiceModel.Security.SecurityStateEncoder> da usare.</span><span class="sxs-lookup"><span data-stu-id="e4b7e-117">A string that specifies the type of <xref:System.ServiceModel.Security.SecurityStateEncoder> to be used.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e4b7e-118">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="e4b7e-118">Child Elements</span></span>  
 <span data-ttu-id="e4b7e-119">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="e4b7e-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e4b7e-120">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="e4b7e-120">Parent Elements</span></span>  
  
|<span data-ttu-id="e4b7e-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="e4b7e-121">Element</span></span>|<span data-ttu-id="e4b7e-122">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="e4b7e-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e4b7e-123">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="e4b7e-123">\<serviceCredentials></span></span>](servicecredentials.md)|<span data-ttu-id="e4b7e-124">Specifica la credenziale da usare nell'autenticazione del servizio e le impostazioni relative alla convalida delle credenziali client.</span><span class="sxs-lookup"><span data-stu-id="e4b7e-124">Specifies the credential to be used in authenticating the service, and the client credential validation-related settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e4b7e-125">Note</span><span class="sxs-lookup"><span data-stu-id="e4b7e-125">Remarks</span></span>  
 <span data-ttu-id="e4b7e-126">Usare questo elemento di configurazione per specificare un elenco di tipi di attestazione noti per la serializzazione dei cookie del token del contesto di sicurezza (SCT, Security Context Token), oltre a un codificatore per la codifica e la sicurezza delle informazioni sui cookie.</span><span class="sxs-lookup"><span data-stu-id="e4b7e-126">Use this configuration element to specify a list of known claim types for the Security Context Token (SCT) cookies serialization, as well as an encoder to encode and secure cookies information.</span></span> <span data-ttu-id="e4b7e-127">Per altre informazioni su SCT, vedere <xref:System.ServiceModel.Security.SecureConversationServiceCredential>.</span><span class="sxs-lookup"><span data-stu-id="e4b7e-127">For more information on SCT, see <xref:System.ServiceModel.Security.SecureConversationServiceCredential>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4b7e-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e4b7e-128">See also</span></span>

- <xref:System.ServiceModel.Configuration.SecureConversationServiceElement>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.SecureConversationAuthentication%2A>
- <xref:System.ServiceModel.Description.ServiceCredentials.SecureConversationAuthentication%2A>
- <xref:System.ServiceModel.Security.SecureConversationServiceCredential>

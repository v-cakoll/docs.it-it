---
title: <secureConversationAuthentication> di <serviceCredential>
ms.date: 03/30/2017
ms.assetid: 0bd3fac7-befd-4a45-ba51-c200b33be0fd
ms.openlocfilehash: 336969c654f332ae3d838d8fd6d1c4243838539c
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70399929"
---
# <a name="secureconversationauthentication-of-servicecredential"></a><span data-ttu-id="9b0a1-102">\<secureConversationAuthentication> di \<serviceCredential></span><span class="sxs-lookup"><span data-stu-id="9b0a1-102">\<secureConversationAuthentication> of \<serviceCredential></span></span>
<span data-ttu-id="9b0a1-103">Specifica le impostazioni per un servizio di conversazione protetta.</span><span class="sxs-lookup"><span data-stu-id="9b0a1-103">Specifies the settings for a secure conversation service.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<secureConversationAuthentication>**  
  
## <a name="syntax"></a><span data-ttu-id="9b0a1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9b0a1-104">Syntax</span></span>  
  
```xml  
<secureConversationAuthentication securityStateEncoderType="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9b0a1-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="9b0a1-105">Attributes and Elements</span></span>  
 <span data-ttu-id="9b0a1-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="9b0a1-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9b0a1-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="9b0a1-107">Attributes</span></span>  
  
|<span data-ttu-id="9b0a1-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="9b0a1-108">Attribute</span></span>|<span data-ttu-id="9b0a1-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9b0a1-109">Description</span></span>|  
|---------------|-----------------|  
|`securityStateEncoderType`|<span data-ttu-id="9b0a1-110">Stringa che specifica il tipo di <xref:System.ServiceModel.Security.SecurityStateEncoder> da usare.</span><span class="sxs-lookup"><span data-stu-id="9b0a1-110">A string that specifies the type of <xref:System.ServiceModel.Security.SecurityStateEncoder> to be used.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9b0a1-111">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="9b0a1-111">Child Elements</span></span>  
 <span data-ttu-id="9b0a1-112">No.</span><span class="sxs-lookup"><span data-stu-id="9b0a1-112">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9b0a1-113">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="9b0a1-113">Parent Elements</span></span>  
  
|<span data-ttu-id="9b0a1-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="9b0a1-114">Element</span></span>|<span data-ttu-id="9b0a1-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9b0a1-115">Description</span></span>|  
|-------------|-----------------|  
|[\<serviceCredentials>](servicecredentials.md)|<span data-ttu-id="9b0a1-116">Specifica la credenziale da usare nell'autenticazione del servizio e le impostazioni relative alla convalida delle credenziali client.</span><span class="sxs-lookup"><span data-stu-id="9b0a1-116">Specifies the credential to be used in authenticating the service, and the client credential validation-related settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9b0a1-117">Commenti</span><span class="sxs-lookup"><span data-stu-id="9b0a1-117">Remarks</span></span>  
 <span data-ttu-id="9b0a1-118">Usare questo elemento di configurazione per specificare un elenco di tipi di attestazione noti per la serializzazione dei cookie del token del contesto di sicurezza (SCT, Security Context Token), oltre a un codificatore per la codifica e la sicurezza delle informazioni sui cookie.</span><span class="sxs-lookup"><span data-stu-id="9b0a1-118">Use this configuration element to specify a list of known claim types for the Security Context Token (SCT) cookies serialization, as well as an encoder to encode and secure cookies information.</span></span> <span data-ttu-id="9b0a1-119">Per altre informazioni su SCT, vedere <xref:System.ServiceModel.Security.SecureConversationServiceCredential>.</span><span class="sxs-lookup"><span data-stu-id="9b0a1-119">For more information on SCT, see <xref:System.ServiceModel.Security.SecureConversationServiceCredential>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b0a1-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9b0a1-120">See also</span></span>

- <xref:System.ServiceModel.Configuration.SecureConversationServiceElement>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.SecureConversationAuthentication%2A>
- <xref:System.ServiceModel.Description.ServiceCredentials.SecureConversationAuthentication%2A>
- <xref:System.ServiceModel.Security.SecureConversationServiceCredential>

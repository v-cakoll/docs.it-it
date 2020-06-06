---
title: <serviceCredentials>
ms.date: 03/30/2017
ms.assetid: 96db336c-4f7a-4193-81a5-910b8ffd804f
ms.openlocfilehash: 90a34a4a52b4c7a2e67d733fecba132818cac4fc
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70399626"
---
# \<serviceCredentials>
<span data-ttu-id="bc061-101">Specifica la credenziale da usare nell'autenticazione del servizio e le impostazioni relative alla convalida delle credenziali client.</span><span class="sxs-lookup"><span data-stu-id="bc061-101">Specifies the credential to be used in authenticating the service and the client credential validation-related settings.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceCredentials>**  
  
## <a name="syntax"></a><span data-ttu-id="bc061-102">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bc061-102">Syntax</span></span>  
  
```xml  
<serviceCredentials type="String">
  <clientCertificate>
  </clientCertificate>
  <issuedTokenAuthentication>
  </issuedTokenAuthentication>
  <peer>
  </peer>
  <secureConversationAuthentication>
  </secureConversationAuthentication>
  <serviceCertificate>
  </serviceCertificate>
  <userNameAuthentication>
  </userNameAuthentication>
  <windowsAuthentication>
  </windowsAuthentication>
</serviceCredentials>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bc061-103">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="bc061-103">Attributes and Elements</span></span>  
 <span data-ttu-id="bc061-104">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="bc061-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bc061-105">Attributi</span><span class="sxs-lookup"><span data-stu-id="bc061-105">Attributes</span></span>  
  
|<span data-ttu-id="bc061-106">Attributo</span><span class="sxs-lookup"><span data-stu-id="bc061-106">Attribute</span></span>|<span data-ttu-id="bc061-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bc061-107">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="bc061-108">Stringa che specifica il tipo di questo elemento di configurazione.</span><span class="sxs-lookup"><span data-stu-id="bc061-108">A string that specifies the type of this configuration element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bc061-109">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="bc061-109">Child Elements</span></span>  
  
|<span data-ttu-id="bc061-110">Elemento</span><span class="sxs-lookup"><span data-stu-id="bc061-110">Element</span></span>|<span data-ttu-id="bc061-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bc061-111">Description</span></span>|  
|-------------|-----------------|  
|[\<clientCertificate>](clientcertificate-of-servicecredentials.md)|<span data-ttu-id="bc061-112">Specifica il certificato client da usare quando il certificato client è disponibile fuori banda.</span><span class="sxs-lookup"><span data-stu-id="bc061-112">Specifies the certificate to be used when the client certificate is available out-of-band.</span></span> <span data-ttu-id="bc061-113">Questo elemento specifica anche impostazioni di convalida dei certificati client.</span><span class="sxs-lookup"><span data-stu-id="bc061-113">This element also specifies client certificate validation settings.</span></span> <span data-ttu-id="bc061-114">L'elemento è di tipo <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="bc061-114">This element is of type <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>.</span></span>|  
|[\<issuedTokenAuthentication>](issuedtokenauthentication-of-servicecredentials.md)|<span data-ttu-id="bc061-115">Specifica il token corrente emesso per questo servizio.</span><span class="sxs-lookup"><span data-stu-id="bc061-115">Specifies the current issued token for this service.</span></span> <span data-ttu-id="bc061-116">L'elemento è di tipo <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="bc061-116">This element is of type <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement>.</span></span>|  
|[\<peer>](peer-of-servicecredentials.md)|<span data-ttu-id="bc061-117">Specifica le credenziali correnti per un nodo peer.</span><span class="sxs-lookup"><span data-stu-id="bc061-117">Specifies the current credentials for a peer node.</span></span> <span data-ttu-id="bc061-118">L'elemento è di tipo <xref:System.ServiceModel.Configuration.PeerCredentialElement>.</span><span class="sxs-lookup"><span data-stu-id="bc061-118">This element is of type <xref:System.ServiceModel.Configuration.PeerCredentialElement>.</span></span>|  
|[\<secureConversationAuthentication>](secureconversationauthentication-of-servicecredential.md)|<span data-ttu-id="bc061-119">Specifica le credenziali correnti per una conversazione protetta.</span><span class="sxs-lookup"><span data-stu-id="bc061-119">Specifies the current credentials for a secure conversation.</span></span> <span data-ttu-id="bc061-120">L'elemento è di tipo <xref:System.ServiceModel.Configuration.SecureConversationServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="bc061-120">This element is of type <xref:System.ServiceModel.Configuration.SecureConversationServiceElement>.</span></span>|  
|[\<serviceCertificate>](servicecertificate-of-servicecredentials.md)|<span data-ttu-id="bc061-121">Specifica un certificato usato da un servizio per identificarsi.</span><span class="sxs-lookup"><span data-stu-id="bc061-121">Specifies a certificate used by a service to identify itself.</span></span> <span data-ttu-id="bc061-122">L'elemento è di tipo <xref:System.ServiceModel.Configuration.X509RecipientCertificateServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="bc061-122">This element is of type <xref:System.ServiceModel.Configuration.X509RecipientCertificateServiceElement>.</span></span>|  
|[\<userNameAuthentication>](usernameauthentication.md)|<span data-ttu-id="bc061-123">Specifica le impostazioni per la convalida nome utente e password.</span><span class="sxs-lookup"><span data-stu-id="bc061-123">Specifies the settings for username password validation.</span></span> <span data-ttu-id="bc061-124">L'elemento è di tipo <xref:System.ServiceModel.Configuration.UserNameServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="bc061-124">This element is of type <xref:System.ServiceModel.Configuration.UserNameServiceElement>.</span></span>|  
|[\<windowsAuthentication>](windowsauthentication-of-servicecredentials.md)|<span data-ttu-id="bc061-125">Specifica le impostazioni per la convalida di credenziali Windows.</span><span class="sxs-lookup"><span data-stu-id="bc061-125">Specifies the settings for Windows credential validation.</span></span> <span data-ttu-id="bc061-126">L'elemento è di tipo <xref:System.ServiceModel.Configuration.WindowsServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="bc061-126">This element is of type <xref:System.ServiceModel.Configuration.WindowsServiceElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="bc061-127">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="bc061-127">Parent Elements</span></span>  
  
|<span data-ttu-id="bc061-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="bc061-128">Element</span></span>|<span data-ttu-id="bc061-129">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bc061-129">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="bc061-130">Specifica un elemento di comportamento.</span><span class="sxs-lookup"><span data-stu-id="bc061-130">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bc061-131">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="bc061-131">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement>
- <xref:System.ServiceModel.Description.ServiceCredentials>
- [<span data-ttu-id="bc061-132">Comportamenti di sicurezza</span><span class="sxs-lookup"><span data-stu-id="bc061-132">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)

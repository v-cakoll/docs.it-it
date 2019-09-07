---
title: <serviceCredentials>
ms.date: 03/30/2017
ms.assetid: 96db336c-4f7a-4193-81a5-910b8ffd804f
ms.openlocfilehash: 90a34a4a52b4c7a2e67d733fecba132818cac4fc
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399626"
---
# <a name="servicecredentials"></a><span data-ttu-id="ecdf6-101">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="ecdf6-101">\<serviceCredentials></span></span>
<span data-ttu-id="ecdf6-102">Specifica la credenziale da usare nell'autenticazione del servizio e le impostazioni relative alla convalida delle credenziali client.</span><span class="sxs-lookup"><span data-stu-id="ecdf6-102">Specifies the credential to be used in authenticating the service and the client credential validation-related settings.</span></span>  
  
<span data-ttu-id="ecdf6-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="ecdf6-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="ecdf6-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="ecdf6-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="ecdf6-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamenti >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="ecdf6-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="ecdf6-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> serviceBehaviors**](servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="ecdf6-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="ecdf6-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamento >** ](behavior-of-servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="ecdf6-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)</span></span>\
<span data-ttu-id="ecdf6-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> di serviceCredentials**</span><span class="sxs-lookup"><span data-stu-id="ecdf6-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceCredentials>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ecdf6-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ecdf6-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ecdf6-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="ecdf6-110">Attributes and Elements</span></span>  
 <span data-ttu-id="ecdf6-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="ecdf6-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ecdf6-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="ecdf6-112">Attributes</span></span>  
  
|<span data-ttu-id="ecdf6-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="ecdf6-113">Attribute</span></span>|<span data-ttu-id="ecdf6-114">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="ecdf6-114">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="ecdf6-115">Stringa che specifica il tipo di questo elemento di configurazione.</span><span class="sxs-lookup"><span data-stu-id="ecdf6-115">A string that specifies the type of this configuration element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ecdf6-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="ecdf6-116">Child Elements</span></span>  
  
|<span data-ttu-id="ecdf6-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="ecdf6-117">Element</span></span>|<span data-ttu-id="ecdf6-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ecdf6-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ecdf6-119">\<clientCertificate></span><span class="sxs-lookup"><span data-stu-id="ecdf6-119">\<clientCertificate></span></span>](clientcertificate-of-servicecredentials.md)|<span data-ttu-id="ecdf6-120">Specifica il certificato client da usare quando il certificato client è disponibile fuori banda.</span><span class="sxs-lookup"><span data-stu-id="ecdf6-120">Specifies the certificate to be used when the client certificate is available out-of-band.</span></span> <span data-ttu-id="ecdf6-121">Questo elemento specifica anche impostazioni di convalida dei certificati client.</span><span class="sxs-lookup"><span data-stu-id="ecdf6-121">This element also specifies client certificate validation settings.</span></span> <span data-ttu-id="ecdf6-122">L'elemento è di tipo <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="ecdf6-122">This element is of type <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>.</span></span>|  
|[<span data-ttu-id="ecdf6-123">\<issuedTokenAuthentication></span><span class="sxs-lookup"><span data-stu-id="ecdf6-123">\<issuedTokenAuthentication></span></span>](issuedtokenauthentication-of-servicecredentials.md)|<span data-ttu-id="ecdf6-124">Specifica il token corrente emesso per questo servizio.</span><span class="sxs-lookup"><span data-stu-id="ecdf6-124">Specifies the current issued token for this service.</span></span> <span data-ttu-id="ecdf6-125">L'elemento è di tipo <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="ecdf6-125">This element is of type <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement>.</span></span>|  
|[<span data-ttu-id="ecdf6-126">\<peer></span><span class="sxs-lookup"><span data-stu-id="ecdf6-126">\<peer></span></span>](peer-of-servicecredentials.md)|<span data-ttu-id="ecdf6-127">Specifica le credenziali correnti per un nodo peer.</span><span class="sxs-lookup"><span data-stu-id="ecdf6-127">Specifies the current credentials for a peer node.</span></span> <span data-ttu-id="ecdf6-128">L'elemento è di tipo <xref:System.ServiceModel.Configuration.PeerCredentialElement>.</span><span class="sxs-lookup"><span data-stu-id="ecdf6-128">This element is of type <xref:System.ServiceModel.Configuration.PeerCredentialElement>.</span></span>|  
|[<span data-ttu-id="ecdf6-129">\<secureConversationAuthentication></span><span class="sxs-lookup"><span data-stu-id="ecdf6-129">\<secureConversationAuthentication></span></span>](secureconversationauthentication-of-servicecredential.md)|<span data-ttu-id="ecdf6-130">Specifica le credenziali correnti per una conversazione protetta.</span><span class="sxs-lookup"><span data-stu-id="ecdf6-130">Specifies the current credentials for a secure conversation.</span></span> <span data-ttu-id="ecdf6-131">L'elemento è di tipo <xref:System.ServiceModel.Configuration.SecureConversationServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="ecdf6-131">This element is of type <xref:System.ServiceModel.Configuration.SecureConversationServiceElement>.</span></span>|  
|[<span data-ttu-id="ecdf6-132">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="ecdf6-132">\<serviceCertificate></span></span>](servicecertificate-of-servicecredentials.md)|<span data-ttu-id="ecdf6-133">Specifica un certificato usato da un servizio per identificarsi.</span><span class="sxs-lookup"><span data-stu-id="ecdf6-133">Specifies a certificate used by a service to identify itself.</span></span> <span data-ttu-id="ecdf6-134">L'elemento è di tipo <xref:System.ServiceModel.Configuration.X509RecipientCertificateServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="ecdf6-134">This element is of type <xref:System.ServiceModel.Configuration.X509RecipientCertificateServiceElement>.</span></span>|  
|[<span data-ttu-id="ecdf6-135">\<userNameAuthentication></span><span class="sxs-lookup"><span data-stu-id="ecdf6-135">\<userNameAuthentication></span></span>](usernameauthentication.md)|<span data-ttu-id="ecdf6-136">Specifica le impostazioni per la convalida nome utente e password.</span><span class="sxs-lookup"><span data-stu-id="ecdf6-136">Specifies the settings for username password validation.</span></span> <span data-ttu-id="ecdf6-137">L'elemento è di tipo <xref:System.ServiceModel.Configuration.UserNameServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="ecdf6-137">This element is of type <xref:System.ServiceModel.Configuration.UserNameServiceElement>.</span></span>|  
|[<span data-ttu-id="ecdf6-138">\<windowsAuthentication></span><span class="sxs-lookup"><span data-stu-id="ecdf6-138">\<windowsAuthentication></span></span>](windowsauthentication-of-servicecredentials.md)|<span data-ttu-id="ecdf6-139">Specifica le impostazioni per la convalida di credenziali Windows.</span><span class="sxs-lookup"><span data-stu-id="ecdf6-139">Specifies the settings for Windows credential validation.</span></span> <span data-ttu-id="ecdf6-140">L'elemento è di tipo <xref:System.ServiceModel.Configuration.WindowsServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="ecdf6-140">This element is of type <xref:System.ServiceModel.Configuration.WindowsServiceElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ecdf6-141">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="ecdf6-141">Parent Elements</span></span>  
  
|<span data-ttu-id="ecdf6-142">Elemento</span><span class="sxs-lookup"><span data-stu-id="ecdf6-142">Element</span></span>|<span data-ttu-id="ecdf6-143">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ecdf6-143">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ecdf6-144">\<behavior></span><span class="sxs-lookup"><span data-stu-id="ecdf6-144">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="ecdf6-145">Specifica un elemento di comportamento.</span><span class="sxs-lookup"><span data-stu-id="ecdf6-145">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ecdf6-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ecdf6-146">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement>
- <xref:System.ServiceModel.Description.ServiceCredentials>
- [<span data-ttu-id="ecdf6-147">Comportamenti di sicurezza</span><span class="sxs-lookup"><span data-stu-id="ecdf6-147">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)

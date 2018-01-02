---
title: '&lt;serviceCredentials&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 96db336c-4f7a-4193-81a5-910b8ffd804f
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 00567c32b800bb98386e15b2ba822ccc9623d72b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ltservicecredentialsgt"></a><span data-ttu-id="01cd9-102">&lt;serviceCredentials&gt;</span><span class="sxs-lookup"><span data-stu-id="01cd9-102">&lt;serviceCredentials&gt;</span></span>
<span data-ttu-id="01cd9-103">Specifica la credenziale da usare nell'autenticazione del servizio e le impostazioni relative alla convalida delle credenziali client.</span><span class="sxs-lookup"><span data-stu-id="01cd9-103">Specifies the credential to be used in authenticating the service and the client credential validation-related settings.</span></span>  
  
 <span data-ttu-id="01cd9-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="01cd9-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="01cd9-105">\<i comportamenti ></span><span class="sxs-lookup"><span data-stu-id="01cd9-105">\<behaviors></span></span>  
<span data-ttu-id="01cd9-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="01cd9-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="01cd9-107">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="01cd9-107">\<behavior></span></span>  
<span data-ttu-id="01cd9-108">\<serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="01cd9-108">\<serviceCredentials></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="01cd9-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="01cd9-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="01cd9-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="01cd9-110">Attributes and Elements</span></span>  
 <span data-ttu-id="01cd9-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="01cd9-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="01cd9-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="01cd9-112">Attributes</span></span>  
  
|<span data-ttu-id="01cd9-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="01cd9-113">Attribute</span></span>|<span data-ttu-id="01cd9-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="01cd9-114">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="01cd9-115">Stringa che specifica il tipo di questo elemento di configurazione.</span><span class="sxs-lookup"><span data-stu-id="01cd9-115">A string that specifies the type of this configuration element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="01cd9-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="01cd9-116">Child Elements</span></span>  
  
|<span data-ttu-id="01cd9-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="01cd9-117">Element</span></span>|<span data-ttu-id="01cd9-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="01cd9-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="01cd9-119">\<clientCertificate ></span><span class="sxs-lookup"><span data-stu-id="01cd9-119">\<clientCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-servicecredentials.md)|<span data-ttu-id="01cd9-120">Specifica il certificato client da usare quando il certificato client è disponibile fuori banda.</span><span class="sxs-lookup"><span data-stu-id="01cd9-120">Specifies the certificate to be used when the client certificate is available out-of-band.</span></span> <span data-ttu-id="01cd9-121">Questo elemento specifica anche impostazioni di convalida dei certificati client.</span><span class="sxs-lookup"><span data-stu-id="01cd9-121">This element also specifies client certificate validation settings.</span></span> <span data-ttu-id="01cd9-122">L'elemento è di tipo <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="01cd9-122">This element is of type <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>.</span></span>|  
|[<span data-ttu-id="01cd9-123">\<issuedTokenAuthentication ></span><span class="sxs-lookup"><span data-stu-id="01cd9-123">\<issuedTokenAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md)|<span data-ttu-id="01cd9-124">Specifica il token corrente emesso per questo servizio.</span><span class="sxs-lookup"><span data-stu-id="01cd9-124">Specifies the current issued token for this service.</span></span> <span data-ttu-id="01cd9-125">L'elemento è di tipo <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="01cd9-125">This element is of type <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement>.</span></span>|  
|[<span data-ttu-id="01cd9-126">\<peer ></span><span class="sxs-lookup"><span data-stu-id="01cd9-126">\<peer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-servicecredentials.md)|<span data-ttu-id="01cd9-127">Specifica le credenziali correnti per un nodo peer.</span><span class="sxs-lookup"><span data-stu-id="01cd9-127">Specifies the current credentials for a peer node.</span></span> <span data-ttu-id="01cd9-128">L'elemento è di tipo <xref:System.ServiceModel.Configuration.PeerCredentialElement>.</span><span class="sxs-lookup"><span data-stu-id="01cd9-128">This element is of type <xref:System.ServiceModel.Configuration.PeerCredentialElement>.</span></span>|  
|[<span data-ttu-id="01cd9-129">\<secureConversationAuthentication ></span><span class="sxs-lookup"><span data-stu-id="01cd9-129">\<secureConversationAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationauthentication-of-servicecredential.md)|<span data-ttu-id="01cd9-130">Specifica le credenziali correnti per una conversazione protetta.</span><span class="sxs-lookup"><span data-stu-id="01cd9-130">Specifies the current credentials for a secure conversation.</span></span> <span data-ttu-id="01cd9-131">L'elemento è di tipo <xref:System.ServiceModel.Configuration.SecureConversationServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="01cd9-131">This element is of type <xref:System.ServiceModel.Configuration.SecureConversationServiceElement>.</span></span>|  
|[<span data-ttu-id="01cd9-132">\<serviceCertificate ></span><span class="sxs-lookup"><span data-stu-id="01cd9-132">\<serviceCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md)|<span data-ttu-id="01cd9-133">Specifica un certificato usato da un servizio per identificarsi.</span><span class="sxs-lookup"><span data-stu-id="01cd9-133">Specifies a certificate used by a service to identify itself.</span></span> <span data-ttu-id="01cd9-134">L'elemento è di tipo <xref:System.ServiceModel.Configuration.X509RecipientCertificateServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="01cd9-134">This element is of type <xref:System.ServiceModel.Configuration.X509RecipientCertificateServiceElement>.</span></span>|  
|[<span data-ttu-id="01cd9-135">\<userNameAuthentication ></span><span class="sxs-lookup"><span data-stu-id="01cd9-135">\<userNameAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/usernameauthentication.md)|<span data-ttu-id="01cd9-136">Specifica le impostazioni per la convalida nome utente e password.</span><span class="sxs-lookup"><span data-stu-id="01cd9-136">Specifies the settings for username password validation.</span></span> <span data-ttu-id="01cd9-137">L'elemento è di tipo <xref:System.ServiceModel.Configuration.UserNameServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="01cd9-137">This element is of type <xref:System.ServiceModel.Configuration.UserNameServiceElement>.</span></span>|  
|[<span data-ttu-id="01cd9-138">\<windowsAuthentication ></span><span class="sxs-lookup"><span data-stu-id="01cd9-138">\<windowsAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/windowsauthentication-of-servicecredentials.md)|<span data-ttu-id="01cd9-139">Specifica le impostazioni per la convalida di credenziali Windows.</span><span class="sxs-lookup"><span data-stu-id="01cd9-139">Specifies the settings for Windows credential validation.</span></span> <span data-ttu-id="01cd9-140">L'elemento è di tipo <xref:System.ServiceModel.Configuration.WindowsServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="01cd9-140">This element is of type <xref:System.ServiceModel.Configuration.WindowsServiceElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="01cd9-141">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="01cd9-141">Parent Elements</span></span>  
  
|<span data-ttu-id="01cd9-142">Elemento</span><span class="sxs-lookup"><span data-stu-id="01cd9-142">Element</span></span>|<span data-ttu-id="01cd9-143">Descrizione</span><span class="sxs-lookup"><span data-stu-id="01cd9-143">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="01cd9-144">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="01cd9-144">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="01cd9-145">Specifica un elemento di comportamento.</span><span class="sxs-lookup"><span data-stu-id="01cd9-145">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="01cd9-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="01cd9-146">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServiceCredentialsElement>  
 <xref:System.ServiceModel.Description.ServiceCredentials>  
 [<span data-ttu-id="01cd9-147">Comportamenti di sicurezza</span><span class="sxs-lookup"><span data-stu-id="01cd9-147">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)

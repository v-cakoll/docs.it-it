---
title: '&lt;ServiceCredentials&gt;'
ms.date: 03/30/2017
ms.assetid: 96db336c-4f7a-4193-81a5-910b8ffd804f
ms.openlocfilehash: b9e32509a5e182301455eaf0e602a03c51fbc23a
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2019
ms.locfileid: "54150773"
---
# <a name="ltservicecredentialsgt"></a><span data-ttu-id="10474-102">&lt;ServiceCredentials&gt;</span><span class="sxs-lookup"><span data-stu-id="10474-102">&lt;serviceCredentials&gt;</span></span>
<span data-ttu-id="10474-103">Specifica la credenziale da usare nell'autenticazione del servizio e le impostazioni relative alla convalida delle credenziali client.</span><span class="sxs-lookup"><span data-stu-id="10474-103">Specifies the credential to be used in authenticating the service and the client credential validation-related settings.</span></span>  
  
 <span data-ttu-id="10474-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="10474-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="10474-105">\<i comportamenti ></span><span class="sxs-lookup"><span data-stu-id="10474-105">\<behaviors></span></span>  
<span data-ttu-id="10474-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="10474-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="10474-107">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="10474-107">\<behavior></span></span>  
<span data-ttu-id="10474-108">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="10474-108">\<serviceCredentials></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="10474-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="10474-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="10474-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="10474-110">Attributes and Elements</span></span>  
 <span data-ttu-id="10474-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="10474-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="10474-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="10474-112">Attributes</span></span>  
  
|<span data-ttu-id="10474-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="10474-113">Attribute</span></span>|<span data-ttu-id="10474-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="10474-114">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="10474-115">Stringa che specifica il tipo di questo elemento di configurazione.</span><span class="sxs-lookup"><span data-stu-id="10474-115">A string that specifies the type of this configuration element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="10474-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="10474-116">Child Elements</span></span>  
  
|<span data-ttu-id="10474-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="10474-117">Element</span></span>|<span data-ttu-id="10474-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="10474-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="10474-119">\<clientCertificate ></span><span class="sxs-lookup"><span data-stu-id="10474-119">\<clientCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-servicecredentials.md)|<span data-ttu-id="10474-120">Specifica il certificato client da usare quando il certificato client è disponibile fuori banda.</span><span class="sxs-lookup"><span data-stu-id="10474-120">Specifies the certificate to be used when the client certificate is available out-of-band.</span></span> <span data-ttu-id="10474-121">Questo elemento specifica anche impostazioni di convalida dei certificati client.</span><span class="sxs-lookup"><span data-stu-id="10474-121">This element also specifies client certificate validation settings.</span></span> <span data-ttu-id="10474-122">L'elemento è di tipo <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="10474-122">This element is of type <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>.</span></span>|  
|[<span data-ttu-id="10474-123">\<issuedTokenAuthentication ></span><span class="sxs-lookup"><span data-stu-id="10474-123">\<issuedTokenAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md)|<span data-ttu-id="10474-124">Specifica il token corrente emesso per questo servizio.</span><span class="sxs-lookup"><span data-stu-id="10474-124">Specifies the current issued token for this service.</span></span> <span data-ttu-id="10474-125">L'elemento è di tipo <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="10474-125">This element is of type <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement>.</span></span>|  
|[<span data-ttu-id="10474-126">\<peer ></span><span class="sxs-lookup"><span data-stu-id="10474-126">\<peer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-servicecredentials.md)|<span data-ttu-id="10474-127">Specifica le credenziali correnti per un nodo peer.</span><span class="sxs-lookup"><span data-stu-id="10474-127">Specifies the current credentials for a peer node.</span></span> <span data-ttu-id="10474-128">L'elemento è di tipo <xref:System.ServiceModel.Configuration.PeerCredentialElement>.</span><span class="sxs-lookup"><span data-stu-id="10474-128">This element is of type <xref:System.ServiceModel.Configuration.PeerCredentialElement>.</span></span>|  
|[<span data-ttu-id="10474-129">\<secureConversationAuthentication ></span><span class="sxs-lookup"><span data-stu-id="10474-129">\<secureConversationAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationauthentication-of-servicecredential.md)|<span data-ttu-id="10474-130">Specifica le credenziali correnti per una conversazione protetta.</span><span class="sxs-lookup"><span data-stu-id="10474-130">Specifies the current credentials for a secure conversation.</span></span> <span data-ttu-id="10474-131">L'elemento è di tipo <xref:System.ServiceModel.Configuration.SecureConversationServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="10474-131">This element is of type <xref:System.ServiceModel.Configuration.SecureConversationServiceElement>.</span></span>|  
|[<span data-ttu-id="10474-132">\<serviceCertificate ></span><span class="sxs-lookup"><span data-stu-id="10474-132">\<serviceCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md)|<span data-ttu-id="10474-133">Specifica un certificato usato da un servizio per identificarsi.</span><span class="sxs-lookup"><span data-stu-id="10474-133">Specifies a certificate used by a service to identify itself.</span></span> <span data-ttu-id="10474-134">L'elemento è di tipo <xref:System.ServiceModel.Configuration.X509RecipientCertificateServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="10474-134">This element is of type <xref:System.ServiceModel.Configuration.X509RecipientCertificateServiceElement>.</span></span>|  
|[<span data-ttu-id="10474-135">\<userNameAuthentication ></span><span class="sxs-lookup"><span data-stu-id="10474-135">\<userNameAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/usernameauthentication.md)|<span data-ttu-id="10474-136">Specifica le impostazioni per la convalida nome utente e password.</span><span class="sxs-lookup"><span data-stu-id="10474-136">Specifies the settings for username password validation.</span></span> <span data-ttu-id="10474-137">L'elemento è di tipo <xref:System.ServiceModel.Configuration.UserNameServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="10474-137">This element is of type <xref:System.ServiceModel.Configuration.UserNameServiceElement>.</span></span>|  
|[<span data-ttu-id="10474-138">\<windowsAuthentication ></span><span class="sxs-lookup"><span data-stu-id="10474-138">\<windowsAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/windowsauthentication-of-servicecredentials.md)|<span data-ttu-id="10474-139">Specifica le impostazioni per la convalida di credenziali Windows.</span><span class="sxs-lookup"><span data-stu-id="10474-139">Specifies the settings for Windows credential validation.</span></span> <span data-ttu-id="10474-140">L'elemento è di tipo <xref:System.ServiceModel.Configuration.WindowsServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="10474-140">This element is of type <xref:System.ServiceModel.Configuration.WindowsServiceElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="10474-141">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="10474-141">Parent Elements</span></span>  
  
|<span data-ttu-id="10474-142">Elemento</span><span class="sxs-lookup"><span data-stu-id="10474-142">Element</span></span>|<span data-ttu-id="10474-143">Descrizione</span><span class="sxs-lookup"><span data-stu-id="10474-143">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="10474-144">\<behavior></span><span class="sxs-lookup"><span data-stu-id="10474-144">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="10474-145">Specifica un elemento di comportamento.</span><span class="sxs-lookup"><span data-stu-id="10474-145">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="10474-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="10474-146">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServiceCredentialsElement>  
 <xref:System.ServiceModel.Description.ServiceCredentials>  
 [<span data-ttu-id="10474-147">Comportamenti di sicurezza</span><span class="sxs-lookup"><span data-stu-id="10474-147">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)

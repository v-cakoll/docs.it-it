---
title: <serviceCredentials>
ms.date: 03/30/2017
ms.assetid: 96db336c-4f7a-4193-81a5-910b8ffd804f
ms.openlocfilehash: d9f8fdf272962916cd08aede484e9bbde55b96a3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61670287"
---
# <a name="servicecredentials"></a><span data-ttu-id="592f6-101">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="592f6-101">\<serviceCredentials></span></span>
<span data-ttu-id="592f6-102">Specifica la credenziale da usare nell'autenticazione del servizio e le impostazioni relative alla convalida delle credenziali client.</span><span class="sxs-lookup"><span data-stu-id="592f6-102">Specifies the credential to be used in authenticating the service and the client credential validation-related settings.</span></span>  
  
 <span data-ttu-id="592f6-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="592f6-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="592f6-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="592f6-104">\<behaviors></span></span>  
<span data-ttu-id="592f6-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="592f6-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="592f6-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="592f6-106">\<behavior></span></span>  
<span data-ttu-id="592f6-107">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="592f6-107">\<serviceCredentials></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="592f6-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="592f6-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="592f6-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="592f6-109">Attributes and Elements</span></span>  
 <span data-ttu-id="592f6-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="592f6-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="592f6-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="592f6-111">Attributes</span></span>  
  
|<span data-ttu-id="592f6-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="592f6-112">Attribute</span></span>|<span data-ttu-id="592f6-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="592f6-113">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="592f6-114">Stringa che specifica il tipo di questo elemento di configurazione.</span><span class="sxs-lookup"><span data-stu-id="592f6-114">A string that specifies the type of this configuration element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="592f6-115">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="592f6-115">Child Elements</span></span>  
  
|<span data-ttu-id="592f6-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="592f6-116">Element</span></span>|<span data-ttu-id="592f6-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="592f6-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="592f6-118">\<clientCertificate></span><span class="sxs-lookup"><span data-stu-id="592f6-118">\<clientCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-servicecredentials.md)|<span data-ttu-id="592f6-119">Specifica il certificato client da usare quando il certificato client è disponibile fuori banda.</span><span class="sxs-lookup"><span data-stu-id="592f6-119">Specifies the certificate to be used when the client certificate is available out-of-band.</span></span> <span data-ttu-id="592f6-120">Questo elemento specifica anche impostazioni di convalida dei certificati client.</span><span class="sxs-lookup"><span data-stu-id="592f6-120">This element also specifies client certificate validation settings.</span></span> <span data-ttu-id="592f6-121">L'elemento è di tipo <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="592f6-121">This element is of type <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>.</span></span>|  
|[<span data-ttu-id="592f6-122">\<issuedTokenAuthentication></span><span class="sxs-lookup"><span data-stu-id="592f6-122">\<issuedTokenAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md)|<span data-ttu-id="592f6-123">Specifica il token corrente emesso per questo servizio.</span><span class="sxs-lookup"><span data-stu-id="592f6-123">Specifies the current issued token for this service.</span></span> <span data-ttu-id="592f6-124">L'elemento è di tipo <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="592f6-124">This element is of type <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement>.</span></span>|  
|[<span data-ttu-id="592f6-125">\<peer></span><span class="sxs-lookup"><span data-stu-id="592f6-125">\<peer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-servicecredentials.md)|<span data-ttu-id="592f6-126">Specifica le credenziali correnti per un nodo peer.</span><span class="sxs-lookup"><span data-stu-id="592f6-126">Specifies the current credentials for a peer node.</span></span> <span data-ttu-id="592f6-127">L'elemento è di tipo <xref:System.ServiceModel.Configuration.PeerCredentialElement>.</span><span class="sxs-lookup"><span data-stu-id="592f6-127">This element is of type <xref:System.ServiceModel.Configuration.PeerCredentialElement>.</span></span>|  
|[<span data-ttu-id="592f6-128">\<secureConversationAuthentication></span><span class="sxs-lookup"><span data-stu-id="592f6-128">\<secureConversationAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationauthentication-of-servicecredential.md)|<span data-ttu-id="592f6-129">Specifica le credenziali correnti per una conversazione protetta.</span><span class="sxs-lookup"><span data-stu-id="592f6-129">Specifies the current credentials for a secure conversation.</span></span> <span data-ttu-id="592f6-130">L'elemento è di tipo <xref:System.ServiceModel.Configuration.SecureConversationServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="592f6-130">This element is of type <xref:System.ServiceModel.Configuration.SecureConversationServiceElement>.</span></span>|  
|[<span data-ttu-id="592f6-131">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="592f6-131">\<serviceCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md)|<span data-ttu-id="592f6-132">Specifica un certificato usato da un servizio per identificarsi.</span><span class="sxs-lookup"><span data-stu-id="592f6-132">Specifies a certificate used by a service to identify itself.</span></span> <span data-ttu-id="592f6-133">L'elemento è di tipo <xref:System.ServiceModel.Configuration.X509RecipientCertificateServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="592f6-133">This element is of type <xref:System.ServiceModel.Configuration.X509RecipientCertificateServiceElement>.</span></span>|  
|[<span data-ttu-id="592f6-134">\<userNameAuthentication></span><span class="sxs-lookup"><span data-stu-id="592f6-134">\<userNameAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/usernameauthentication.md)|<span data-ttu-id="592f6-135">Specifica le impostazioni per la convalida nome utente e password.</span><span class="sxs-lookup"><span data-stu-id="592f6-135">Specifies the settings for username password validation.</span></span> <span data-ttu-id="592f6-136">L'elemento è di tipo <xref:System.ServiceModel.Configuration.UserNameServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="592f6-136">This element is of type <xref:System.ServiceModel.Configuration.UserNameServiceElement>.</span></span>|  
|[<span data-ttu-id="592f6-137">\<windowsAuthentication></span><span class="sxs-lookup"><span data-stu-id="592f6-137">\<windowsAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/windowsauthentication-of-servicecredentials.md)|<span data-ttu-id="592f6-138">Specifica le impostazioni per la convalida di credenziali Windows.</span><span class="sxs-lookup"><span data-stu-id="592f6-138">Specifies the settings for Windows credential validation.</span></span> <span data-ttu-id="592f6-139">L'elemento è di tipo <xref:System.ServiceModel.Configuration.WindowsServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="592f6-139">This element is of type <xref:System.ServiceModel.Configuration.WindowsServiceElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="592f6-140">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="592f6-140">Parent Elements</span></span>  
  
|<span data-ttu-id="592f6-141">Elemento</span><span class="sxs-lookup"><span data-stu-id="592f6-141">Element</span></span>|<span data-ttu-id="592f6-142">Descrizione</span><span class="sxs-lookup"><span data-stu-id="592f6-142">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="592f6-143">\<behavior></span><span class="sxs-lookup"><span data-stu-id="592f6-143">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="592f6-144">Specifica un elemento di comportamento.</span><span class="sxs-lookup"><span data-stu-id="592f6-144">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="592f6-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="592f6-145">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement>
- <xref:System.ServiceModel.Description.ServiceCredentials>
- [<span data-ttu-id="592f6-146">Comportamenti di sicurezza</span><span class="sxs-lookup"><span data-stu-id="592f6-146">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)

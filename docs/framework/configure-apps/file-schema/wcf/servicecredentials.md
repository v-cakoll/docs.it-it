---
title: <serviceCredentials>
ms.date: 03/30/2017
ms.assetid: 96db336c-4f7a-4193-81a5-910b8ffd804f
ms.openlocfilehash: b5d257b3082717ba94b9a4517ed5ccd4bd325c06
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69936303"
---
# <a name="servicecredentials"></a><span data-ttu-id="f1491-101">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="f1491-101">\<serviceCredentials></span></span>
<span data-ttu-id="f1491-102">Specifica la credenziale da usare nell'autenticazione del servizio e le impostazioni relative alla convalida delle credenziali client.</span><span class="sxs-lookup"><span data-stu-id="f1491-102">Specifies the credential to be used in authenticating the service and the client credential validation-related settings.</span></span>  
  
 <span data-ttu-id="f1491-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="f1491-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="f1491-104">\<comportamenti ></span><span class="sxs-lookup"><span data-stu-id="f1491-104">\<behaviors></span></span>  
<span data-ttu-id="f1491-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="f1491-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="f1491-106">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="f1491-106">\<behavior></span></span>  
<span data-ttu-id="f1491-107">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="f1491-107">\<serviceCredentials></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1491-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f1491-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f1491-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="f1491-109">Attributes and Elements</span></span>  
 <span data-ttu-id="f1491-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="f1491-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f1491-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="f1491-111">Attributes</span></span>  
  
|<span data-ttu-id="f1491-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="f1491-112">Attribute</span></span>|<span data-ttu-id="f1491-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f1491-113">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="f1491-114">Stringa che specifica il tipo di questo elemento di configurazione.</span><span class="sxs-lookup"><span data-stu-id="f1491-114">A string that specifies the type of this configuration element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f1491-115">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="f1491-115">Child Elements</span></span>  
  
|<span data-ttu-id="f1491-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="f1491-116">Element</span></span>|<span data-ttu-id="f1491-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f1491-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f1491-118">\<clientCertificate></span><span class="sxs-lookup"><span data-stu-id="f1491-118">\<clientCertificate></span></span>](clientcertificate-of-servicecredentials.md)|<span data-ttu-id="f1491-119">Specifica il certificato client da usare quando il certificato client è disponibile fuori banda.</span><span class="sxs-lookup"><span data-stu-id="f1491-119">Specifies the certificate to be used when the client certificate is available out-of-band.</span></span> <span data-ttu-id="f1491-120">Questo elemento specifica anche impostazioni di convalida dei certificati client.</span><span class="sxs-lookup"><span data-stu-id="f1491-120">This element also specifies client certificate validation settings.</span></span> <span data-ttu-id="f1491-121">L'elemento è di tipo <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="f1491-121">This element is of type <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>.</span></span>|  
|[<span data-ttu-id="f1491-122">\<issuedTokenAuthentication></span><span class="sxs-lookup"><span data-stu-id="f1491-122">\<issuedTokenAuthentication></span></span>](issuedtokenauthentication-of-servicecredentials.md)|<span data-ttu-id="f1491-123">Specifica il token corrente emesso per questo servizio.</span><span class="sxs-lookup"><span data-stu-id="f1491-123">Specifies the current issued token for this service.</span></span> <span data-ttu-id="f1491-124">L'elemento è di tipo <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="f1491-124">This element is of type <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement>.</span></span>|  
|[<span data-ttu-id="f1491-125">\<peer></span><span class="sxs-lookup"><span data-stu-id="f1491-125">\<peer></span></span>](peer-of-servicecredentials.md)|<span data-ttu-id="f1491-126">Specifica le credenziali correnti per un nodo peer.</span><span class="sxs-lookup"><span data-stu-id="f1491-126">Specifies the current credentials for a peer node.</span></span> <span data-ttu-id="f1491-127">L'elemento è di tipo <xref:System.ServiceModel.Configuration.PeerCredentialElement>.</span><span class="sxs-lookup"><span data-stu-id="f1491-127">This element is of type <xref:System.ServiceModel.Configuration.PeerCredentialElement>.</span></span>|  
|[<span data-ttu-id="f1491-128">\<secureConversationAuthentication></span><span class="sxs-lookup"><span data-stu-id="f1491-128">\<secureConversationAuthentication></span></span>](secureconversationauthentication-of-servicecredential.md)|<span data-ttu-id="f1491-129">Specifica le credenziali correnti per una conversazione protetta.</span><span class="sxs-lookup"><span data-stu-id="f1491-129">Specifies the current credentials for a secure conversation.</span></span> <span data-ttu-id="f1491-130">L'elemento è di tipo <xref:System.ServiceModel.Configuration.SecureConversationServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="f1491-130">This element is of type <xref:System.ServiceModel.Configuration.SecureConversationServiceElement>.</span></span>|  
|[<span data-ttu-id="f1491-131">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="f1491-131">\<serviceCertificate></span></span>](servicecertificate-of-servicecredentials.md)|<span data-ttu-id="f1491-132">Specifica un certificato usato da un servizio per identificarsi.</span><span class="sxs-lookup"><span data-stu-id="f1491-132">Specifies a certificate used by a service to identify itself.</span></span> <span data-ttu-id="f1491-133">L'elemento è di tipo <xref:System.ServiceModel.Configuration.X509RecipientCertificateServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="f1491-133">This element is of type <xref:System.ServiceModel.Configuration.X509RecipientCertificateServiceElement>.</span></span>|  
|[<span data-ttu-id="f1491-134">\<userNameAuthentication></span><span class="sxs-lookup"><span data-stu-id="f1491-134">\<userNameAuthentication></span></span>](usernameauthentication.md)|<span data-ttu-id="f1491-135">Specifica le impostazioni per la convalida nome utente e password.</span><span class="sxs-lookup"><span data-stu-id="f1491-135">Specifies the settings for username password validation.</span></span> <span data-ttu-id="f1491-136">L'elemento è di tipo <xref:System.ServiceModel.Configuration.UserNameServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="f1491-136">This element is of type <xref:System.ServiceModel.Configuration.UserNameServiceElement>.</span></span>|  
|[<span data-ttu-id="f1491-137">\<windowsAuthentication></span><span class="sxs-lookup"><span data-stu-id="f1491-137">\<windowsAuthentication></span></span>](windowsauthentication-of-servicecredentials.md)|<span data-ttu-id="f1491-138">Specifica le impostazioni per la convalida di credenziali Windows.</span><span class="sxs-lookup"><span data-stu-id="f1491-138">Specifies the settings for Windows credential validation.</span></span> <span data-ttu-id="f1491-139">L'elemento è di tipo <xref:System.ServiceModel.Configuration.WindowsServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="f1491-139">This element is of type <xref:System.ServiceModel.Configuration.WindowsServiceElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f1491-140">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="f1491-140">Parent Elements</span></span>  
  
|<span data-ttu-id="f1491-141">Elemento</span><span class="sxs-lookup"><span data-stu-id="f1491-141">Element</span></span>|<span data-ttu-id="f1491-142">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="f1491-142">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f1491-143">\<behavior></span><span class="sxs-lookup"><span data-stu-id="f1491-143">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="f1491-144">Specifica un elemento di comportamento.</span><span class="sxs-lookup"><span data-stu-id="f1491-144">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f1491-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f1491-145">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement>
- <xref:System.ServiceModel.Description.ServiceCredentials>
- [<span data-ttu-id="f1491-146">Comportamenti di sicurezza</span><span class="sxs-lookup"><span data-stu-id="f1491-146">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)

---
title: <clientCredentials>
ms.date: 03/30/2017
ms.assetid: 1e6eef0d-a34e-4d74-b0f7-f65d2181858d
ms.openlocfilehash: ebe976df9af0c316e95a1e089412e57a575a6df1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61673381"
---
# <a name="clientcredentials"></a><span data-ttu-id="e8166-101">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="e8166-101">\<clientCredentials></span></span>
<span data-ttu-id="e8166-102">Specifica le credenziali usate per autenticare il client presso un servizio.</span><span class="sxs-lookup"><span data-stu-id="e8166-102">Specifies the credentials used to authenticate the client to a service.</span></span>  
  
 <span data-ttu-id="e8166-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="e8166-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="e8166-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="e8166-104">\<behaviors></span></span>  
<span data-ttu-id="e8166-105">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="e8166-105">\<endpointBehaviors></span></span>  
<span data-ttu-id="e8166-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="e8166-106">\<behavior></span></span>  
<span data-ttu-id="e8166-107">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="e8166-107">\<clientCredentials></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8166-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e8166-108">Syntax</span></span>  
  
```xml  
<clientCredentials type="String"
                   supportInteractive="Boolean" >
  <clientCertificate>
  </clientCertificate>
  <digest>
  </digest>
  <isuedToken>
  </isuedToken>
  <peer>
  </peer>
  <serviceCertificate>
  </serviceCertificate>
  <windowsAuthentication>
  </windowsAuthentication>
</clientCredentials>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e8166-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="e8166-109">Attributes and Elements</span></span>  
 <span data-ttu-id="e8166-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="e8166-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e8166-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="e8166-111">Attributes</span></span>  
  
|<span data-ttu-id="e8166-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="e8166-112">Attribute</span></span>|<span data-ttu-id="e8166-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e8166-113">Description</span></span>|  
|---------------|-----------------|  
|`supportInteractive`|<span data-ttu-id="e8166-114">Valore booleano che specifica se un utente interattivo può essere coinvolto nella selezione di una credenziale client in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="e8166-114">A Boolean value that specifies whether an interactive user can be involved in selecting a client credential at runtime.</span></span> <span data-ttu-id="e8166-115">Il valore predefinito è `true`.</span><span class="sxs-lookup"><span data-stu-id="e8166-115">The default value is `true`.</span></span>|  
|`type`|<span data-ttu-id="e8166-116">Stringa che specifica il tipo di questo elemento di configurazione.</span><span class="sxs-lookup"><span data-stu-id="e8166-116">A string that specifies the type of this configuration element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e8166-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="e8166-117">Child Elements</span></span>  
  
|<span data-ttu-id="e8166-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="e8166-118">Element</span></span>|<span data-ttu-id="e8166-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e8166-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e8166-120">\<clientCertificate></span><span class="sxs-lookup"><span data-stu-id="e8166-120">\<clientCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-clientcredentials-element.md)|<span data-ttu-id="e8166-121">Specifica il certificato usato per autenticare il client presso il servizio.</span><span class="sxs-lookup"><span data-stu-id="e8166-121">Specifies the certificate used to authenticate the client to the service.</span></span> <span data-ttu-id="e8166-122">L'elemento è di tipo <xref:System.ServiceModel.Configuration.X509InitiatorCertificateClientElement>.</span><span class="sxs-lookup"><span data-stu-id="e8166-122">This element is of type <xref:System.ServiceModel.Configuration.X509InitiatorCertificateClientElement>.</span></span>|  
|[<span data-ttu-id="e8166-123">\<httpDigest></span><span class="sxs-lookup"><span data-stu-id="e8166-123">\<httpDigest></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/httpdigest-element.md)|<span data-ttu-id="e8166-124">Specifica un digest usato per autenticare il client presso il servizio.</span><span class="sxs-lookup"><span data-stu-id="e8166-124">Specifies a digest used to authenticate the client to the service.</span></span> <span data-ttu-id="e8166-125">L'elemento è di tipo <xref:System.ServiceModel.Configuration.HttpDigestClientElement>.</span><span class="sxs-lookup"><span data-stu-id="e8166-125">This element is of type <xref:System.ServiceModel.Configuration.HttpDigestClientElement>.</span></span>|  
|[<span data-ttu-id="e8166-126">\<issuedToken></span><span class="sxs-lookup"><span data-stu-id="e8166-126">\<issuedToken></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtoken.md)|<span data-ttu-id="e8166-127">Specifica un tipo di token personalizzato usato per autenticare il client presso un servizio token di sicurezza (STS, Secure Token Service).</span><span class="sxs-lookup"><span data-stu-id="e8166-127">Specifies a custom token type used to authenticate the client to a Secure Token Service (STS).</span></span> <span data-ttu-id="e8166-128">L'elemento è di tipo <xref:System.ServiceModel.Configuration.IssuedTokenClientElement>.</span><span class="sxs-lookup"><span data-stu-id="e8166-128">This element is of type <xref:System.ServiceModel.Configuration.IssuedTokenClientElement>.</span></span>|  
|[<span data-ttu-id="e8166-129">\<peer></span><span class="sxs-lookup"><span data-stu-id="e8166-129">\<peer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-clientcredentials-element.md)|<span data-ttu-id="e8166-130">Specifica una credenziale peer corrente.</span><span class="sxs-lookup"><span data-stu-id="e8166-130">Specifies a current peer credential.</span></span> <span data-ttu-id="e8166-131">L'elemento è di tipo <xref:System.ServiceModel.Configuration.PeerCredentialElement>.</span><span class="sxs-lookup"><span data-stu-id="e8166-131">This element is of type <xref:System.ServiceModel.Configuration.PeerCredentialElement>.</span></span>|  
|[<span data-ttu-id="e8166-132">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="e8166-132">\<serviceCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-clientcredentials-element.md)|<span data-ttu-id="e8166-133">Specifica il certificato usato per autenticare il servizio presso il client e fornisce una struttura per l'impostazione delle opzioni del certificato.</span><span class="sxs-lookup"><span data-stu-id="e8166-133">Specifies the certificate used to authenticate the service to the client and provides a structure for setting certificate options.</span></span> <span data-ttu-id="e8166-134">Questo certificato deve essere fornito fuori banda dal servizio al client.</span><span class="sxs-lookup"><span data-stu-id="e8166-134">This certificate must be supplied out-of-band from the service to the client.</span></span> <span data-ttu-id="e8166-135">L'elemento è di tipo <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement>.</span><span class="sxs-lookup"><span data-stu-id="e8166-135">This element is of type <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement>.</span></span>|  
|[<span data-ttu-id="e8166-136">\<windows></span><span class="sxs-lookup"><span data-stu-id="e8166-136">\<windows></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/windows-of-clientcredentials-element.md)|<span data-ttu-id="e8166-137">Specifica una credenziale Windows.</span><span class="sxs-lookup"><span data-stu-id="e8166-137">Specifies a Windows credential.</span></span> <span data-ttu-id="e8166-138">Il valore predefinito è la credenziale del thread corrente.</span><span class="sxs-lookup"><span data-stu-id="e8166-138">The default is the credential of the current thread.</span></span> <span data-ttu-id="e8166-139">L'elemento è di tipo <xref:System.ServiceModel.Configuration.WindowsClientElement>.</span><span class="sxs-lookup"><span data-stu-id="e8166-139">This element is of type <xref:System.ServiceModel.Configuration.WindowsClientElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e8166-140">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="e8166-140">Parent Elements</span></span>  
  
|<span data-ttu-id="e8166-141">Elemento</span><span class="sxs-lookup"><span data-stu-id="e8166-141">Element</span></span>|<span data-ttu-id="e8166-142">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e8166-142">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e8166-143">\<behavior></span><span class="sxs-lookup"><span data-stu-id="e8166-143">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="e8166-144">Specifica un comportamento dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="e8166-144">Specifies an endpoint behavior.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e8166-145">Note</span><span class="sxs-lookup"><span data-stu-id="e8166-145">Remarks</span></span>  
 <span data-ttu-id="e8166-146">Le credenziali client sono usate per autenticare i client presso i servizi nei casi in cui non è richiesta l'autenticazione reciproca.</span><span class="sxs-lookup"><span data-stu-id="e8166-146">Client credentials are used to authenticate the client to services in cases where mutual authentication is required.</span></span> <span data-ttu-id="e8166-147">È inoltre possibile usare questa sezione di configurazione per specificare i certificati di servizio negli scenari in cui il client deve usare il certificato di un servizio per proteggere i messaggi inviati a un servizio.</span><span class="sxs-lookup"><span data-stu-id="e8166-147">This configuration section can also be used to specify service certificates for scenarios where the client must secure messages to a service with the service's certificate.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8166-148">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e8166-148">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Description.ClientCredentials>
- [<span data-ttu-id="e8166-149">Comportamenti di sicurezza</span><span class="sxs-lookup"><span data-stu-id="e8166-149">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="e8166-150">Protezione di client</span><span class="sxs-lookup"><span data-stu-id="e8166-150">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)

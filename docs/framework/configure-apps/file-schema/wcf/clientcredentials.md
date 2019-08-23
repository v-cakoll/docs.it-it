---
title: <clientCredentials>
ms.date: 03/30/2017
ms.assetid: 1e6eef0d-a34e-4d74-b0f7-f65d2181858d
ms.openlocfilehash: c3e756f49b7054d6553eb6c3f1850f0fbce14943
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926126"
---
# <a name="clientcredentials"></a><span data-ttu-id="924e8-101">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="924e8-101">\<clientCredentials></span></span>
<span data-ttu-id="924e8-102">Specifica le credenziali usate per autenticare il client presso un servizio.</span><span class="sxs-lookup"><span data-stu-id="924e8-102">Specifies the credentials used to authenticate the client to a service.</span></span>  
  
 <span data-ttu-id="924e8-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="924e8-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="924e8-104">\<comportamenti ></span><span class="sxs-lookup"><span data-stu-id="924e8-104">\<behaviors></span></span>  
<span data-ttu-id="924e8-105">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="924e8-105">\<endpointBehaviors></span></span>  
<span data-ttu-id="924e8-106">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="924e8-106">\<behavior></span></span>  
<span data-ttu-id="924e8-107">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="924e8-107">\<clientCredentials></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="924e8-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="924e8-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="924e8-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="924e8-109">Attributes and Elements</span></span>  
 <span data-ttu-id="924e8-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="924e8-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="924e8-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="924e8-111">Attributes</span></span>  
  
|<span data-ttu-id="924e8-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="924e8-112">Attribute</span></span>|<span data-ttu-id="924e8-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="924e8-113">Description</span></span>|  
|---------------|-----------------|  
|`supportInteractive`|<span data-ttu-id="924e8-114">Valore booleano che specifica se un utente interattivo può essere coinvolto nella selezione di una credenziale client in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="924e8-114">A Boolean value that specifies whether an interactive user can be involved in selecting a client credential at runtime.</span></span> <span data-ttu-id="924e8-115">Il valore predefinito è `true`.</span><span class="sxs-lookup"><span data-stu-id="924e8-115">The default value is `true`.</span></span>|  
|`type`|<span data-ttu-id="924e8-116">Stringa che specifica il tipo di questo elemento di configurazione.</span><span class="sxs-lookup"><span data-stu-id="924e8-116">A string that specifies the type of this configuration element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="924e8-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="924e8-117">Child Elements</span></span>  
  
|<span data-ttu-id="924e8-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="924e8-118">Element</span></span>|<span data-ttu-id="924e8-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="924e8-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="924e8-120">\<clientCertificate></span><span class="sxs-lookup"><span data-stu-id="924e8-120">\<clientCertificate></span></span>](clientcertificate-of-clientcredentials-element.md)|<span data-ttu-id="924e8-121">Specifica il certificato usato per autenticare il client presso il servizio.</span><span class="sxs-lookup"><span data-stu-id="924e8-121">Specifies the certificate used to authenticate the client to the service.</span></span> <span data-ttu-id="924e8-122">L'elemento è di tipo <xref:System.ServiceModel.Configuration.X509InitiatorCertificateClientElement>.</span><span class="sxs-lookup"><span data-stu-id="924e8-122">This element is of type <xref:System.ServiceModel.Configuration.X509InitiatorCertificateClientElement>.</span></span>|  
|[<span data-ttu-id="924e8-123">\<> httpDigest</span><span class="sxs-lookup"><span data-stu-id="924e8-123">\<httpDigest></span></span>](httpdigest-element.md)|<span data-ttu-id="924e8-124">Specifica un digest usato per autenticare il client presso il servizio.</span><span class="sxs-lookup"><span data-stu-id="924e8-124">Specifies a digest used to authenticate the client to the service.</span></span> <span data-ttu-id="924e8-125">L'elemento è di tipo <xref:System.ServiceModel.Configuration.HttpDigestClientElement>.</span><span class="sxs-lookup"><span data-stu-id="924e8-125">This element is of type <xref:System.ServiceModel.Configuration.HttpDigestClientElement>.</span></span>|  
|[<span data-ttu-id="924e8-126">\<issuedToken></span><span class="sxs-lookup"><span data-stu-id="924e8-126">\<issuedToken></span></span>](issuedtoken.md)|<span data-ttu-id="924e8-127">Specifica un tipo di token personalizzato usato per autenticare il client presso un servizio token di sicurezza (STS, Secure Token Service).</span><span class="sxs-lookup"><span data-stu-id="924e8-127">Specifies a custom token type used to authenticate the client to a Secure Token Service (STS).</span></span> <span data-ttu-id="924e8-128">L'elemento è di tipo <xref:System.ServiceModel.Configuration.IssuedTokenClientElement>.</span><span class="sxs-lookup"><span data-stu-id="924e8-128">This element is of type <xref:System.ServiceModel.Configuration.IssuedTokenClientElement>.</span></span>|  
|[<span data-ttu-id="924e8-129">\<peer></span><span class="sxs-lookup"><span data-stu-id="924e8-129">\<peer></span></span>](peer-of-clientcredentials-element.md)|<span data-ttu-id="924e8-130">Specifica una credenziale peer corrente.</span><span class="sxs-lookup"><span data-stu-id="924e8-130">Specifies a current peer credential.</span></span> <span data-ttu-id="924e8-131">L'elemento è di tipo <xref:System.ServiceModel.Configuration.PeerCredentialElement>.</span><span class="sxs-lookup"><span data-stu-id="924e8-131">This element is of type <xref:System.ServiceModel.Configuration.PeerCredentialElement>.</span></span>|  
|[<span data-ttu-id="924e8-132">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="924e8-132">\<serviceCertificate></span></span>](servicecertificate-of-clientcredentials-element.md)|<span data-ttu-id="924e8-133">Specifica il certificato usato per autenticare il servizio presso il client e fornisce una struttura per l'impostazione delle opzioni del certificato.</span><span class="sxs-lookup"><span data-stu-id="924e8-133">Specifies the certificate used to authenticate the service to the client and provides a structure for setting certificate options.</span></span> <span data-ttu-id="924e8-134">Questo certificato deve essere fornito fuori banda dal servizio al client.</span><span class="sxs-lookup"><span data-stu-id="924e8-134">This certificate must be supplied out-of-band from the service to the client.</span></span> <span data-ttu-id="924e8-135">L'elemento è di tipo <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement>.</span><span class="sxs-lookup"><span data-stu-id="924e8-135">This element is of type <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement>.</span></span>|  
|[<span data-ttu-id="924e8-136">\<windows></span><span class="sxs-lookup"><span data-stu-id="924e8-136">\<windows></span></span>](windows-of-clientcredentials-element.md)|<span data-ttu-id="924e8-137">Specifica una credenziale Windows.</span><span class="sxs-lookup"><span data-stu-id="924e8-137">Specifies a Windows credential.</span></span> <span data-ttu-id="924e8-138">Il valore predefinito è la credenziale del thread corrente.</span><span class="sxs-lookup"><span data-stu-id="924e8-138">The default is the credential of the current thread.</span></span> <span data-ttu-id="924e8-139">L'elemento è di tipo <xref:System.ServiceModel.Configuration.WindowsClientElement>.</span><span class="sxs-lookup"><span data-stu-id="924e8-139">This element is of type <xref:System.ServiceModel.Configuration.WindowsClientElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="924e8-140">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="924e8-140">Parent Elements</span></span>  
  
|<span data-ttu-id="924e8-141">Elemento</span><span class="sxs-lookup"><span data-stu-id="924e8-141">Element</span></span>|<span data-ttu-id="924e8-142">Descrizione</span><span class="sxs-lookup"><span data-stu-id="924e8-142">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="924e8-143">\<behavior></span><span class="sxs-lookup"><span data-stu-id="924e8-143">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="924e8-144">Specifica un comportamento dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="924e8-144">Specifies an endpoint behavior.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="924e8-145">Note</span><span class="sxs-lookup"><span data-stu-id="924e8-145">Remarks</span></span>  
 <span data-ttu-id="924e8-146">Le credenziali client sono usate per autenticare i client presso i servizi nei casi in cui non è richiesta l'autenticazione reciproca.</span><span class="sxs-lookup"><span data-stu-id="924e8-146">Client credentials are used to authenticate the client to services in cases where mutual authentication is required.</span></span> <span data-ttu-id="924e8-147">È inoltre possibile usare questa sezione di configurazione per specificare i certificati di servizio negli scenari in cui il client deve usare il certificato di un servizio per proteggere i messaggi inviati a un servizio.</span><span class="sxs-lookup"><span data-stu-id="924e8-147">This configuration section can also be used to specify service certificates for scenarios where the client must secure messages to a service with the service's certificate.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="924e8-148">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="924e8-148">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Description.ClientCredentials>
- [<span data-ttu-id="924e8-149">Comportamenti di sicurezza</span><span class="sxs-lookup"><span data-stu-id="924e8-149">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="924e8-150">Protezione di client</span><span class="sxs-lookup"><span data-stu-id="924e8-150">Securing Clients</span></span>](../../../wcf/securing-clients.md)

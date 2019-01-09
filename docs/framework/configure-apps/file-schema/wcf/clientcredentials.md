---
title: '&lt;ClientCredentials&gt;'
ms.date: 03/30/2017
ms.assetid: 1e6eef0d-a34e-4d74-b0f7-f65d2181858d
ms.openlocfilehash: 3f70a4e6e27507c3820e1b67f49664e538ac736f
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2019
ms.locfileid: "54145749"
---
# <a name="ltclientcredentialsgt"></a><span data-ttu-id="05d29-102">&lt;ClientCredentials&gt;</span><span class="sxs-lookup"><span data-stu-id="05d29-102">&lt;clientCredentials&gt;</span></span>
<span data-ttu-id="05d29-103">Specifica le credenziali usate per autenticare il client presso un servizio.</span><span class="sxs-lookup"><span data-stu-id="05d29-103">Specifies the credentials used to authenticate the client to a service.</span></span>  
  
 <span data-ttu-id="05d29-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="05d29-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="05d29-105">\<i comportamenti ></span><span class="sxs-lookup"><span data-stu-id="05d29-105">\<behaviors></span></span>  
<span data-ttu-id="05d29-106">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="05d29-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="05d29-107">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="05d29-107">\<behavior></span></span>  
<span data-ttu-id="05d29-108">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="05d29-108">\<clientCredentials></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="05d29-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="05d29-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="05d29-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="05d29-110">Attributes and Elements</span></span>  
 <span data-ttu-id="05d29-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="05d29-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="05d29-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="05d29-112">Attributes</span></span>  
  
|<span data-ttu-id="05d29-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="05d29-113">Attribute</span></span>|<span data-ttu-id="05d29-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="05d29-114">Description</span></span>|  
|---------------|-----------------|  
|`supportInteractive`|<span data-ttu-id="05d29-115">Valore booleano che specifica se un utente interattivo può essere coinvolto nella selezione di una credenziale client in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="05d29-115">A Boolean value that specifies whether an interactive user can be involved in selecting a client credential at runtime.</span></span> <span data-ttu-id="05d29-116">Il valore predefinito è `true`.</span><span class="sxs-lookup"><span data-stu-id="05d29-116">The default value is `true`.</span></span>|  
|`type`|<span data-ttu-id="05d29-117">Stringa che specifica il tipo di questo elemento di configurazione.</span><span class="sxs-lookup"><span data-stu-id="05d29-117">A string that specifies the type of this configuration element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="05d29-118">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="05d29-118">Child Elements</span></span>  
  
|<span data-ttu-id="05d29-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="05d29-119">Element</span></span>|<span data-ttu-id="05d29-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="05d29-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="05d29-121">\<clientCertificate ></span><span class="sxs-lookup"><span data-stu-id="05d29-121">\<clientCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-clientcredentials-element.md)|<span data-ttu-id="05d29-122">Specifica il certificato usato per autenticare il client presso il servizio.</span><span class="sxs-lookup"><span data-stu-id="05d29-122">Specifies the certificate used to authenticate the client to the service.</span></span> <span data-ttu-id="05d29-123">L'elemento è di tipo <xref:System.ServiceModel.Configuration.X509InitiatorCertificateClientElement>.</span><span class="sxs-lookup"><span data-stu-id="05d29-123">This element is of type <xref:System.ServiceModel.Configuration.X509InitiatorCertificateClientElement>.</span></span>|  
|[<span data-ttu-id="05d29-124">\<httpDigest ></span><span class="sxs-lookup"><span data-stu-id="05d29-124">\<httpDigest></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/httpdigest-element.md)|<span data-ttu-id="05d29-125">Specifica un digest usato per autenticare il client presso il servizio.</span><span class="sxs-lookup"><span data-stu-id="05d29-125">Specifies a digest used to authenticate the client to the service.</span></span> <span data-ttu-id="05d29-126">L'elemento è di tipo <xref:System.ServiceModel.Configuration.HttpDigestClientElement>.</span><span class="sxs-lookup"><span data-stu-id="05d29-126">This element is of type <xref:System.ServiceModel.Configuration.HttpDigestClientElement>.</span></span>|  
|[<span data-ttu-id="05d29-127">\<issuedToken ></span><span class="sxs-lookup"><span data-stu-id="05d29-127">\<issuedToken></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtoken.md)|<span data-ttu-id="05d29-128">Specifica un tipo di token personalizzato usato per autenticare il client presso un servizio token di sicurezza (STS, Secure Token Service).</span><span class="sxs-lookup"><span data-stu-id="05d29-128">Specifies a custom token type used to authenticate the client to a Secure Token Service (STS).</span></span> <span data-ttu-id="05d29-129">L'elemento è di tipo <xref:System.ServiceModel.Configuration.IssuedTokenClientElement>.</span><span class="sxs-lookup"><span data-stu-id="05d29-129">This element is of type <xref:System.ServiceModel.Configuration.IssuedTokenClientElement>.</span></span>|  
|[<span data-ttu-id="05d29-130">\<peer ></span><span class="sxs-lookup"><span data-stu-id="05d29-130">\<peer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-clientcredentials-element.md)|<span data-ttu-id="05d29-131">Specifica una credenziale peer corrente.</span><span class="sxs-lookup"><span data-stu-id="05d29-131">Specifies a current peer credential.</span></span> <span data-ttu-id="05d29-132">L'elemento è di tipo <xref:System.ServiceModel.Configuration.PeerCredentialElement>.</span><span class="sxs-lookup"><span data-stu-id="05d29-132">This element is of type <xref:System.ServiceModel.Configuration.PeerCredentialElement>.</span></span>|  
|[<span data-ttu-id="05d29-133">\<serviceCertificate ></span><span class="sxs-lookup"><span data-stu-id="05d29-133">\<serviceCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-clientcredentials-element.md)|<span data-ttu-id="05d29-134">Specifica il certificato usato per autenticare il servizio presso il client e fornisce una struttura per l'impostazione delle opzioni del certificato.</span><span class="sxs-lookup"><span data-stu-id="05d29-134">Specifies the certificate used to authenticate the service to the client and provides a structure for setting certificate options.</span></span> <span data-ttu-id="05d29-135">Questo certificato deve essere fornito fuori banda dal servizio al client.</span><span class="sxs-lookup"><span data-stu-id="05d29-135">This certificate must be supplied out-of-band from the service to the client.</span></span> <span data-ttu-id="05d29-136">L'elemento è di tipo <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement>.</span><span class="sxs-lookup"><span data-stu-id="05d29-136">This element is of type <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement>.</span></span>|  
|[<span data-ttu-id="05d29-137">\<Windows ></span><span class="sxs-lookup"><span data-stu-id="05d29-137">\<windows></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/windows-of-clientcredentials-element.md)|<span data-ttu-id="05d29-138">Specifica una credenziale Windows.</span><span class="sxs-lookup"><span data-stu-id="05d29-138">Specifies a Windows credential.</span></span> <span data-ttu-id="05d29-139">Il valore predefinito è la credenziale del thread corrente.</span><span class="sxs-lookup"><span data-stu-id="05d29-139">The default is the credential of the current thread.</span></span> <span data-ttu-id="05d29-140">L'elemento è di tipo <xref:System.ServiceModel.Configuration.WindowsClientElement>.</span><span class="sxs-lookup"><span data-stu-id="05d29-140">This element is of type <xref:System.ServiceModel.Configuration.WindowsClientElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="05d29-141">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="05d29-141">Parent Elements</span></span>  
  
|<span data-ttu-id="05d29-142">Elemento</span><span class="sxs-lookup"><span data-stu-id="05d29-142">Element</span></span>|<span data-ttu-id="05d29-143">Descrizione</span><span class="sxs-lookup"><span data-stu-id="05d29-143">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="05d29-144">\<behavior></span><span class="sxs-lookup"><span data-stu-id="05d29-144">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="05d29-145">Specifica un comportamento dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="05d29-145">Specifies an endpoint behavior.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="05d29-146">Note</span><span class="sxs-lookup"><span data-stu-id="05d29-146">Remarks</span></span>  
 <span data-ttu-id="05d29-147">Le credenziali client sono usate per autenticare i client presso i servizi nei casi in cui non è richiesta l'autenticazione reciproca.</span><span class="sxs-lookup"><span data-stu-id="05d29-147">Client credentials are used to authenticate the client to services in cases where mutual authentication is required.</span></span> <span data-ttu-id="05d29-148">È inoltre possibile usare questa sezione di configurazione per specificare i certificati di servizio negli scenari in cui il client deve usare il certificato di un servizio per proteggere i messaggi inviati a un servizio.</span><span class="sxs-lookup"><span data-stu-id="05d29-148">This configuration section can also be used to specify service certificates for scenarios where the client must secure messages to a service with the service's certificate.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05d29-149">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="05d29-149">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement>  
 <xref:System.ServiceModel.Description.ClientCredentials>  
 [<span data-ttu-id="05d29-150">Comportamenti di sicurezza</span><span class="sxs-lookup"><span data-stu-id="05d29-150">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [<span data-ttu-id="05d29-151">Protezione di client</span><span class="sxs-lookup"><span data-stu-id="05d29-151">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)

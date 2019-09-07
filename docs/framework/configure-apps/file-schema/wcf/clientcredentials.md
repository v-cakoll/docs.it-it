---
title: <clientCredentials>
ms.date: 03/30/2017
ms.assetid: 1e6eef0d-a34e-4d74-b0f7-f65d2181858d
ms.openlocfilehash: f295fe48e194611c80b78c0c23ab3e66ea1c0b64
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400506"
---
# <a name="clientcredentials"></a><span data-ttu-id="7f448-101">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="7f448-101">\<clientCredentials></span></span>
<span data-ttu-id="7f448-102">Specifica le credenziali usate per autenticare il client presso un servizio.</span><span class="sxs-lookup"><span data-stu-id="7f448-102">Specifies the credentials used to authenticate the client to a service.</span></span>  
  
<span data-ttu-id="7f448-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="7f448-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="7f448-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="7f448-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="7f448-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamenti >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="7f448-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="7f448-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> endpointBehaviors**](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="7f448-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="7f448-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamento >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="7f448-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="7f448-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> clientCredentials**</span><span class="sxs-lookup"><span data-stu-id="7f448-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clientCredentials>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7f448-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7f448-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7f448-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="7f448-110">Attributes and Elements</span></span>  
 <span data-ttu-id="7f448-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="7f448-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7f448-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="7f448-112">Attributes</span></span>  
  
|<span data-ttu-id="7f448-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="7f448-113">Attribute</span></span>|<span data-ttu-id="7f448-114">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="7f448-114">Description</span></span>|  
|---------------|-----------------|  
|`supportInteractive`|<span data-ttu-id="7f448-115">Valore booleano che specifica se un utente interattivo può essere coinvolto nella selezione di una credenziale client in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="7f448-115">A Boolean value that specifies whether an interactive user can be involved in selecting a client credential at runtime.</span></span> <span data-ttu-id="7f448-116">Il valore predefinito è `true`.</span><span class="sxs-lookup"><span data-stu-id="7f448-116">The default value is `true`.</span></span>|  
|`type`|<span data-ttu-id="7f448-117">Stringa che specifica il tipo di questo elemento di configurazione.</span><span class="sxs-lookup"><span data-stu-id="7f448-117">A string that specifies the type of this configuration element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7f448-118">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="7f448-118">Child Elements</span></span>  
  
|<span data-ttu-id="7f448-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="7f448-119">Element</span></span>|<span data-ttu-id="7f448-120">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="7f448-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7f448-121">\<clientCertificate></span><span class="sxs-lookup"><span data-stu-id="7f448-121">\<clientCertificate></span></span>](clientcertificate-of-clientcredentials-element.md)|<span data-ttu-id="7f448-122">Specifica il certificato usato per autenticare il client presso il servizio.</span><span class="sxs-lookup"><span data-stu-id="7f448-122">Specifies the certificate used to authenticate the client to the service.</span></span> <span data-ttu-id="7f448-123">L'elemento è di tipo <xref:System.ServiceModel.Configuration.X509InitiatorCertificateClientElement>.</span><span class="sxs-lookup"><span data-stu-id="7f448-123">This element is of type <xref:System.ServiceModel.Configuration.X509InitiatorCertificateClientElement>.</span></span>|  
|[<span data-ttu-id="7f448-124">\<> httpDigest</span><span class="sxs-lookup"><span data-stu-id="7f448-124">\<httpDigest></span></span>](httpdigest-element.md)|<span data-ttu-id="7f448-125">Specifica un digest usato per autenticare il client presso il servizio.</span><span class="sxs-lookup"><span data-stu-id="7f448-125">Specifies a digest used to authenticate the client to the service.</span></span> <span data-ttu-id="7f448-126">L'elemento è di tipo <xref:System.ServiceModel.Configuration.HttpDigestClientElement>.</span><span class="sxs-lookup"><span data-stu-id="7f448-126">This element is of type <xref:System.ServiceModel.Configuration.HttpDigestClientElement>.</span></span>|  
|[<span data-ttu-id="7f448-127">\<issuedToken></span><span class="sxs-lookup"><span data-stu-id="7f448-127">\<issuedToken></span></span>](issuedtoken.md)|<span data-ttu-id="7f448-128">Specifica un tipo di token personalizzato usato per autenticare il client presso un servizio token di sicurezza (STS, Secure Token Service).</span><span class="sxs-lookup"><span data-stu-id="7f448-128">Specifies a custom token type used to authenticate the client to a Secure Token Service (STS).</span></span> <span data-ttu-id="7f448-129">L'elemento è di tipo <xref:System.ServiceModel.Configuration.IssuedTokenClientElement>.</span><span class="sxs-lookup"><span data-stu-id="7f448-129">This element is of type <xref:System.ServiceModel.Configuration.IssuedTokenClientElement>.</span></span>|  
|[<span data-ttu-id="7f448-130">\<peer></span><span class="sxs-lookup"><span data-stu-id="7f448-130">\<peer></span></span>](peer-of-clientcredentials-element.md)|<span data-ttu-id="7f448-131">Specifica una credenziale peer corrente.</span><span class="sxs-lookup"><span data-stu-id="7f448-131">Specifies a current peer credential.</span></span> <span data-ttu-id="7f448-132">L'elemento è di tipo <xref:System.ServiceModel.Configuration.PeerCredentialElement>.</span><span class="sxs-lookup"><span data-stu-id="7f448-132">This element is of type <xref:System.ServiceModel.Configuration.PeerCredentialElement>.</span></span>|  
|[<span data-ttu-id="7f448-133">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="7f448-133">\<serviceCertificate></span></span>](servicecertificate-of-clientcredentials-element.md)|<span data-ttu-id="7f448-134">Specifica il certificato usato per autenticare il servizio presso il client e fornisce una struttura per l'impostazione delle opzioni del certificato.</span><span class="sxs-lookup"><span data-stu-id="7f448-134">Specifies the certificate used to authenticate the service to the client and provides a structure for setting certificate options.</span></span> <span data-ttu-id="7f448-135">Questo certificato deve essere fornito fuori banda dal servizio al client.</span><span class="sxs-lookup"><span data-stu-id="7f448-135">This certificate must be supplied out-of-band from the service to the client.</span></span> <span data-ttu-id="7f448-136">L'elemento è di tipo <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement>.</span><span class="sxs-lookup"><span data-stu-id="7f448-136">This element is of type <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement>.</span></span>|  
|[<span data-ttu-id="7f448-137">\<windows></span><span class="sxs-lookup"><span data-stu-id="7f448-137">\<windows></span></span>](windows-of-clientcredentials-element.md)|<span data-ttu-id="7f448-138">Specifica una credenziale Windows.</span><span class="sxs-lookup"><span data-stu-id="7f448-138">Specifies a Windows credential.</span></span> <span data-ttu-id="7f448-139">Il valore predefinito è la credenziale del thread corrente.</span><span class="sxs-lookup"><span data-stu-id="7f448-139">The default is the credential of the current thread.</span></span> <span data-ttu-id="7f448-140">L'elemento è di tipo <xref:System.ServiceModel.Configuration.WindowsClientElement>.</span><span class="sxs-lookup"><span data-stu-id="7f448-140">This element is of type <xref:System.ServiceModel.Configuration.WindowsClientElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7f448-141">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="7f448-141">Parent Elements</span></span>  
  
|<span data-ttu-id="7f448-142">Elemento</span><span class="sxs-lookup"><span data-stu-id="7f448-142">Element</span></span>|<span data-ttu-id="7f448-143">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7f448-143">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7f448-144">\<behavior></span><span class="sxs-lookup"><span data-stu-id="7f448-144">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="7f448-145">Specifica un comportamento dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="7f448-145">Specifies an endpoint behavior.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7f448-146">Note</span><span class="sxs-lookup"><span data-stu-id="7f448-146">Remarks</span></span>  
 <span data-ttu-id="7f448-147">Le credenziali client sono usate per autenticare i client presso i servizi nei casi in cui non è richiesta l'autenticazione reciproca.</span><span class="sxs-lookup"><span data-stu-id="7f448-147">Client credentials are used to authenticate the client to services in cases where mutual authentication is required.</span></span> <span data-ttu-id="7f448-148">È inoltre possibile usare questa sezione di configurazione per specificare i certificati di servizio negli scenari in cui il client deve usare il certificato di un servizio per proteggere i messaggi inviati a un servizio.</span><span class="sxs-lookup"><span data-stu-id="7f448-148">This configuration section can also be used to specify service certificates for scenarios where the client must secure messages to a service with the service's certificate.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f448-149">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7f448-149">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Description.ClientCredentials>
- [<span data-ttu-id="7f448-150">Comportamenti di sicurezza</span><span class="sxs-lookup"><span data-stu-id="7f448-150">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="7f448-151">Protezione di client</span><span class="sxs-lookup"><span data-stu-id="7f448-151">Securing Clients</span></span>](../../../wcf/securing-clients.md)

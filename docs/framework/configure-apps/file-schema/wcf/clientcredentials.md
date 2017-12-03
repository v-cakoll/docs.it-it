---
title: '&lt;clientCredentials&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1e6eef0d-a34e-4d74-b0f7-f65d2181858d
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 834853d8a922148d2810cd391a64a281f2f9ae3c
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="ltclientcredentialsgt"></a><span data-ttu-id="f97dd-102">&lt;clientCredentials&gt;</span><span class="sxs-lookup"><span data-stu-id="f97dd-102">&lt;clientCredentials&gt;</span></span>
<span data-ttu-id="f97dd-103">Specifica le credenziali usate per autenticare il client presso un servizio.</span><span class="sxs-lookup"><span data-stu-id="f97dd-103">Specifies the credentials used to authenticate the client to a service.</span></span>  
  
 <span data-ttu-id="f97dd-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="f97dd-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="f97dd-105">\<i comportamenti ></span><span class="sxs-lookup"><span data-stu-id="f97dd-105">\<behaviors></span></span>  
<span data-ttu-id="f97dd-106">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="f97dd-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="f97dd-107">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="f97dd-107">\<behavior></span></span>  
<span data-ttu-id="f97dd-108">\<clientCredentials ></span><span class="sxs-lookup"><span data-stu-id="f97dd-108">\<clientCredentials></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f97dd-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f97dd-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f97dd-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="f97dd-110">Attributes and Elements</span></span>  
 <span data-ttu-id="f97dd-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="f97dd-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f97dd-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="f97dd-112">Attributes</span></span>  
  
|<span data-ttu-id="f97dd-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="f97dd-113">Attribute</span></span>|<span data-ttu-id="f97dd-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f97dd-114">Description</span></span>|  
|---------------|-----------------|  
|`supportInteractive`|<span data-ttu-id="f97dd-115">Valore booleano che specifica se un utente interattivo può essere coinvolto nella selezione di una credenziale client in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="f97dd-115">A Boolean value that specifies whether an interactive user can be involved in selecting a client credential at runtime.</span></span> <span data-ttu-id="f97dd-116">Il valore predefinito è `true`.</span><span class="sxs-lookup"><span data-stu-id="f97dd-116">The default value is `true`.</span></span>|  
|`type`|<span data-ttu-id="f97dd-117">Stringa che specifica il tipo di questo elemento di configurazione.</span><span class="sxs-lookup"><span data-stu-id="f97dd-117">A string that specifies the type of this configuration element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f97dd-118">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="f97dd-118">Child Elements</span></span>  
  
|<span data-ttu-id="f97dd-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="f97dd-119">Element</span></span>|<span data-ttu-id="f97dd-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f97dd-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f97dd-121">\<clientCertificate ></span><span class="sxs-lookup"><span data-stu-id="f97dd-121">\<clientCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-clientcredentials-element.md)|<span data-ttu-id="f97dd-122">Specifica il certificato usato per autenticare il client presso il servizio.</span><span class="sxs-lookup"><span data-stu-id="f97dd-122">Specifies the certificate used to authenticate the client to the service.</span></span> <span data-ttu-id="f97dd-123">L'elemento è di tipo <xref:System.ServiceModel.Configuration.X509InitiatorCertificateClientElement>.</span><span class="sxs-lookup"><span data-stu-id="f97dd-123">This element is of type <xref:System.ServiceModel.Configuration.X509InitiatorCertificateClientElement>.</span></span>|  
|[<span data-ttu-id="f97dd-124">\<httpDigest ></span><span class="sxs-lookup"><span data-stu-id="f97dd-124">\<httpDigest></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/httpdigest-element.md)|<span data-ttu-id="f97dd-125">Specifica un digest usato per autenticare il client presso il servizio.</span><span class="sxs-lookup"><span data-stu-id="f97dd-125">Specifies a digest used to authenticate the client to the service.</span></span> <span data-ttu-id="f97dd-126">L'elemento è di tipo <xref:System.ServiceModel.Configuration.HttpDigestClientElement>.</span><span class="sxs-lookup"><span data-stu-id="f97dd-126">This element is of type <xref:System.ServiceModel.Configuration.HttpDigestClientElement>.</span></span>|  
|[<span data-ttu-id="f97dd-127">\<issuedToken ></span><span class="sxs-lookup"><span data-stu-id="f97dd-127">\<issuedToken></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtoken.md)|<span data-ttu-id="f97dd-128">Specifica un tipo di token personalizzato usato per autenticare il client presso un servizio token di sicurezza (STS, Secure Token Service).</span><span class="sxs-lookup"><span data-stu-id="f97dd-128">Specifies a custom token type used to authenticate the client to a Secure Token Service (STS).</span></span> <span data-ttu-id="f97dd-129">L'elemento è di tipo <xref:System.ServiceModel.Configuration.IssuedTokenClientElement>.</span><span class="sxs-lookup"><span data-stu-id="f97dd-129">This element is of type <xref:System.ServiceModel.Configuration.IssuedTokenClientElement>.</span></span>|  
|[<span data-ttu-id="f97dd-130">\<peer ></span><span class="sxs-lookup"><span data-stu-id="f97dd-130">\<peer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-clientcredentials-element.md)|<span data-ttu-id="f97dd-131">Specifica una credenziale peer corrente.</span><span class="sxs-lookup"><span data-stu-id="f97dd-131">Specifies a current peer credential.</span></span> <span data-ttu-id="f97dd-132">L'elemento è di tipo <xref:System.ServiceModel.Configuration.PeerCredentialElement>.</span><span class="sxs-lookup"><span data-stu-id="f97dd-132">This element is of type <xref:System.ServiceModel.Configuration.PeerCredentialElement>.</span></span>|  
|[<span data-ttu-id="f97dd-133">\<serviceCertificate ></span><span class="sxs-lookup"><span data-stu-id="f97dd-133">\<serviceCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-clientcredentials-element.md)|<span data-ttu-id="f97dd-134">Specifica il certificato usato per autenticare il servizio presso il client e fornisce una struttura per l'impostazione delle opzioni del certificato.</span><span class="sxs-lookup"><span data-stu-id="f97dd-134">Specifies the certificate used to authenticate the service to the client and provides a structure for setting certificate options.</span></span> <span data-ttu-id="f97dd-135">Questo certificato deve essere fornito fuori banda dal servizio al client.</span><span class="sxs-lookup"><span data-stu-id="f97dd-135">This certificate must be supplied out-of-band from the service to the client.</span></span> <span data-ttu-id="f97dd-136">L'elemento è di tipo <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement>.</span><span class="sxs-lookup"><span data-stu-id="f97dd-136">This element is of type <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement>.</span></span>|  
|[<span data-ttu-id="f97dd-137">\<Windows ></span><span class="sxs-lookup"><span data-stu-id="f97dd-137">\<windows></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/windows-of-clientcredentials-element.md)|<span data-ttu-id="f97dd-138">Specifica una credenziale Windows.</span><span class="sxs-lookup"><span data-stu-id="f97dd-138">Specifies a Windows credential.</span></span> <span data-ttu-id="f97dd-139">Il valore predefinito è la credenziale del thread corrente.</span><span class="sxs-lookup"><span data-stu-id="f97dd-139">The default is the credential of the current thread.</span></span> <span data-ttu-id="f97dd-140">L'elemento è di tipo <xref:System.ServiceModel.Configuration.WindowsClientElement>.</span><span class="sxs-lookup"><span data-stu-id="f97dd-140">This element is of type <xref:System.ServiceModel.Configuration.WindowsClientElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f97dd-141">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="f97dd-141">Parent Elements</span></span>  
  
|<span data-ttu-id="f97dd-142">Elemento</span><span class="sxs-lookup"><span data-stu-id="f97dd-142">Element</span></span>|<span data-ttu-id="f97dd-143">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f97dd-143">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f97dd-144">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="f97dd-144">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="f97dd-145">Specifica un comportamento dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="f97dd-145">Specifies an endpoint behavior.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f97dd-146">Note</span><span class="sxs-lookup"><span data-stu-id="f97dd-146">Remarks</span></span>  
 <span data-ttu-id="f97dd-147">Le credenziali client sono usate per autenticare i client presso i servizi nei casi in cui non è richiesta l'autenticazione reciproca.</span><span class="sxs-lookup"><span data-stu-id="f97dd-147">Client credentials are used to authenticate the client to services in cases where mutual authentication is required.</span></span> <span data-ttu-id="f97dd-148">È inoltre possibile usare questa sezione di configurazione per specificare i certificati di servizio negli scenari in cui il client deve usare il certificato di un servizio per proteggere i messaggi inviati a un servizio.</span><span class="sxs-lookup"><span data-stu-id="f97dd-148">This configuration section can also be used to specify service certificates for scenarios where the client must secure messages to a service with the service's certificate.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f97dd-149">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f97dd-149">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement>  
 <xref:System.ServiceModel.Description.ClientCredentials>  
 [<span data-ttu-id="f97dd-150">Comportamenti di sicurezza</span><span class="sxs-lookup"><span data-stu-id="f97dd-150">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [<span data-ttu-id="f97dd-151">Protezione di client</span><span class="sxs-lookup"><span data-stu-id="f97dd-151">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)

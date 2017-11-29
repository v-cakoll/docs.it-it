---
title: '&lt;authentication&gt; dell''elemento &lt;serviceCertificate&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 733b67b4-08a1-4d25-9741-10046f9357ef
caps.latest.revision: "13"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 163a035c667c25be4f780daf85c50d96816bd0f3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ltauthenticationgt-of-ltservicecertificategt-element"></a><span data-ttu-id="332e1-102">&lt;authentication&gt; dell'elemento &lt;serviceCertificate&gt;</span><span class="sxs-lookup"><span data-stu-id="332e1-102">&lt;authentication&gt; of &lt;serviceCertificate&gt; Element</span></span>
<span data-ttu-id="332e1-103">Specifica le impostazioni usate dal proxy del client per autenticare i certificati dei servizi ottenuti mediante la negoziazione SSL/TLS.</span><span class="sxs-lookup"><span data-stu-id="332e1-103">Specifies the settings used by the client proxy to authenticate service certificates that are obtained using SSL/TLS negotiation.</span></span>  
  
 <span data-ttu-id="332e1-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="332e1-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="332e1-105">\<i comportamenti ></span><span class="sxs-lookup"><span data-stu-id="332e1-105">\<behaviors></span></span>  
<span data-ttu-id="332e1-106">sezione endpointBehaviors</span><span class="sxs-lookup"><span data-stu-id="332e1-106">endpointBehaviors section</span></span>  
<span data-ttu-id="332e1-107">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="332e1-107">\<behavior></span></span>  
<span data-ttu-id="332e1-108">\<clientCredentials ></span><span class="sxs-lookup"><span data-stu-id="332e1-108">\<clientCredentials></span></span>  
<span data-ttu-id="332e1-109">\<serviceCertificate ></span><span class="sxs-lookup"><span data-stu-id="332e1-109">\<serviceCertificate></span></span>  
<span data-ttu-id="332e1-110">\<autenticazione ></span><span class="sxs-lookup"><span data-stu-id="332e1-110">\<authentication></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="332e1-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="332e1-111">Syntax</span></span>  
  
```xml  
<authentication customCertificateValidatorType="String" certificateValidationMode="None/PeerTrust/ChainTrust/PeerOrChainTrust/Custom"  
revocationMode="NoCheck/Online/Offline"   
trustedStoreLocation="LocalMachine/CurrentUser" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="332e1-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="332e1-112">Attributes and Elements</span></span>  
 <span data-ttu-id="332e1-113">Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.</span><span class="sxs-lookup"><span data-stu-id="332e1-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="332e1-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="332e1-114">Attributes</span></span>  
  
|<span data-ttu-id="332e1-115">Attributo</span><span class="sxs-lookup"><span data-stu-id="332e1-115">Attribute</span></span>|<span data-ttu-id="332e1-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="332e1-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="332e1-117">customCertificateValidatorType</span><span class="sxs-lookup"><span data-stu-id="332e1-117">customCertificateValidatorType</span></span>|<span data-ttu-id="332e1-118">Stringa.</span><span class="sxs-lookup"><span data-stu-id="332e1-118">String.</span></span> <span data-ttu-id="332e1-119">Un tipo e un assembly usati per convalidare un tipo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="332e1-119">A type and assembly used to validate a custom type.</span></span>|  
|<span data-ttu-id="332e1-120">certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="332e1-120">certificateValidationMode</span></span>|<span data-ttu-id="332e1-121">Specifica una delle tre modalità usate per convalidare credenziali.</span><span class="sxs-lookup"><span data-stu-id="332e1-121">Specifies one of three modes used to validate credentials.</span></span> <span data-ttu-id="332e1-122">Se è impostato su `Custom`, è necessario fornire anche un customCertificateValidator.</span><span class="sxs-lookup"><span data-stu-id="332e1-122">If set to `Custom`, then a customCertificateValidator must also be supplied.</span></span> <span data-ttu-id="332e1-123">Il valore predefinito è `ChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="332e1-123">The default is `ChainTrust`.</span></span>|  
|<span data-ttu-id="332e1-124">revocationMode</span><span class="sxs-lookup"><span data-stu-id="332e1-124">revocationMode</span></span>|<span data-ttu-id="332e1-125">Una delle modalità usate per verificare un elenco dei certificati revocati.</span><span class="sxs-lookup"><span data-stu-id="332e1-125">One of the modes used to check for a revoked certificate lists (CRL).</span></span> <span data-ttu-id="332e1-126">Il valore predefinito è `Online`.</span><span class="sxs-lookup"><span data-stu-id="332e1-126">The default is `Online`.</span></span>|  
|<span data-ttu-id="332e1-127">trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="332e1-127">trustedStoreLocation</span></span>|<span data-ttu-id="332e1-128">Uno di due percorsi dell'archivio di sistema: `LocalMachine` o `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="332e1-128">One of the two system store locations: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="332e1-129">Questo valore viene usato quando viene negoziato un certificato del servizio con il client.</span><span class="sxs-lookup"><span data-stu-id="332e1-129">This value is used when a service certificate is negotiated to the client.</span></span> <span data-ttu-id="332e1-130">La convalida viene eseguita su di **persone attendibili** archiviare nel percorso dell'archivio specificato.</span><span class="sxs-lookup"><span data-stu-id="332e1-130">Validation is performed against the **Trusted People** store in the specified store location.</span></span> <span data-ttu-id="332e1-131">Il valore predefinito è `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="332e1-131">The default is `CurrentUser`.</span></span>|  
  
## <a name="customcertificatevalidator-attribute"></a><span data-ttu-id="332e1-132">Attributo customCertificateValidator</span><span class="sxs-lookup"><span data-stu-id="332e1-132">customCertificateValidator Attribute</span></span>  
  
|<span data-ttu-id="332e1-133">Valore</span><span class="sxs-lookup"><span data-stu-id="332e1-133">Value</span></span>|<span data-ttu-id="332e1-134">Descrizione</span><span class="sxs-lookup"><span data-stu-id="332e1-134">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="332e1-135">String</span><span class="sxs-lookup"><span data-stu-id="332e1-135">String</span></span>|<span data-ttu-id="332e1-136">Specifica il nome e l'assembly del tipo e altri dati usati per trovare il tipo.</span><span class="sxs-lookup"><span data-stu-id="332e1-136">Specifies the type name and assembly and other data used to find the type.</span></span>|  
  
## <a name="certificatevalidationmode-attribute"></a><span data-ttu-id="332e1-137">Attributo certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="332e1-137">certificateValidationMode Attribute</span></span>  
  
|<span data-ttu-id="332e1-138">Valore</span><span class="sxs-lookup"><span data-stu-id="332e1-138">Value</span></span>|<span data-ttu-id="332e1-139">Descrizione</span><span class="sxs-lookup"><span data-stu-id="332e1-139">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="332e1-140">Enumerazione</span><span class="sxs-lookup"><span data-stu-id="332e1-140">Enumeration</span></span>|<span data-ttu-id="332e1-141">Uno dei valori seguenti: None, PeerTrust, ChainTrust, PeerOrChainTrust, Custom.</span><span class="sxs-lookup"><span data-stu-id="332e1-141">One of the following values: None, PeerTrust, ChainTrust, PeerOrChainTrust, Custom.</span></span><br /><br /> <span data-ttu-id="332e1-142">Per ulteriori informazioni, vedere [utilizzo dei certificati](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="332e1-142">For more information, see [Working with Certificates](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="revocationmode-attribute"></a><span data-ttu-id="332e1-143">Attributo revocationMode</span><span class="sxs-lookup"><span data-stu-id="332e1-143">revocationMode Attribute</span></span>  
  
|<span data-ttu-id="332e1-144">Valore</span><span class="sxs-lookup"><span data-stu-id="332e1-144">Value</span></span>|<span data-ttu-id="332e1-145">Descrizione</span><span class="sxs-lookup"><span data-stu-id="332e1-145">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="332e1-146">Enumerazione</span><span class="sxs-lookup"><span data-stu-id="332e1-146">Enumeration</span></span>|<span data-ttu-id="332e1-147">Uno dei valori seguenti: NoCheck, Online, Offline.</span><span class="sxs-lookup"><span data-stu-id="332e1-147">One of the following values: NoCheck, Online, Offline.</span></span><br /><br /> <span data-ttu-id="332e1-148">Per ulteriori informazioni, vedere [utilizzo dei certificati](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="332e1-148">For more information, see [Working with Certificates](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="trustedstorelocation-attribute"></a><span data-ttu-id="332e1-149">Attributo trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="332e1-149">trustedStoreLocation Attribute</span></span>  
  
|<span data-ttu-id="332e1-150">Valore</span><span class="sxs-lookup"><span data-stu-id="332e1-150">Value</span></span>|<span data-ttu-id="332e1-151">Descrizione</span><span class="sxs-lookup"><span data-stu-id="332e1-151">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="332e1-152">Enumerazione</span><span class="sxs-lookup"><span data-stu-id="332e1-152">Enumeration</span></span>|<span data-ttu-id="332e1-153">Uno dei valori seguenti: LocalMachine o CurrentUser.</span><span class="sxs-lookup"><span data-stu-id="332e1-153">One of the following values: LocalMachine or CurrentUser.</span></span> <span data-ttu-id="332e1-154">L'impostazione predefinita è CurrentUser.</span><span class="sxs-lookup"><span data-stu-id="332e1-154">The default is CurrentUser.</span></span> <span data-ttu-id="332e1-155">Se l'applicazione client è in esecuzione con un account di sistema, il certificato è in genere in LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="332e1-155">If the client application is running under a system account, then the certificate is typically under LocalMachine.</span></span> <span data-ttu-id="332e1-156">Se l'applicazione client è in esecuzione con un account utente, il certificato è in genere in CurrentUser.</span><span class="sxs-lookup"><span data-stu-id="332e1-156">If the client application is running under a user account, then the certificate is typically in CurrentUser.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="332e1-157">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="332e1-157">Child Elements</span></span>  
 <span data-ttu-id="332e1-158">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="332e1-158">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="332e1-159">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="332e1-159">Parent Elements</span></span>  
  
|<span data-ttu-id="332e1-160">Elemento</span><span class="sxs-lookup"><span data-stu-id="332e1-160">Element</span></span>|<span data-ttu-id="332e1-161">Descrizione</span><span class="sxs-lookup"><span data-stu-id="332e1-161">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="332e1-162">\<serviceCertificate ></span><span class="sxs-lookup"><span data-stu-id="332e1-162">\<serviceCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-clientcredentials-element.md)|<span data-ttu-id="332e1-163">Specifica un certificato da usare per l'autenticazione di un servizio presso il client.</span><span class="sxs-lookup"><span data-stu-id="332e1-163">Specifies a certificate to use when authenticating a service to the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="332e1-164">Note</span><span class="sxs-lookup"><span data-stu-id="332e1-164">Remarks</span></span>  
 <span data-ttu-id="332e1-165">L'attributo `certificateValidationMode` di questo elemento di configurazione specifica il livello di attendibilità usato per autenticare i certificati.</span><span class="sxs-lookup"><span data-stu-id="332e1-165">The `certificateValidationMode` attribute of this configuration element specifies the level of trust used to authenticate certificates.</span></span> <span data-ttu-id="332e1-166">Per impostazione predefinita, il livello è impostato su `ChainTrust`. Tale impostazione prevede che ogni certificato appartenga a una gerarchia di certificati che termina in un'autorità di certificazione attendibile situata all'inizio della catena.</span><span class="sxs-lookup"><span data-stu-id="332e1-166">By default, the level is set to `ChainTrust`, which specifies that each certificate must be found in a hierarchy of certificates ending in a trusted certification authority at the top of the chain.</span></span> <span data-ttu-id="332e1-167">Si tratta della modalità più sicura.</span><span class="sxs-lookup"><span data-stu-id="332e1-167">This is the most secure mode.</span></span> <span data-ttu-id="332e1-168">Il livello può inoltre essere impostato su `PeerOrChainTrust`, a indicare che sia i certificati autocertificati (trust peer) sia i certificati appartenenti a una catena di trust sono ritenuti attendibili.</span><span class="sxs-lookup"><span data-stu-id="332e1-168">You can also set the value to `PeerOrChainTrust`, which specifies that self-issued certificates (peer trust) are accepted as well as certificates that are in a trusted chain.</span></span> <span data-ttu-id="332e1-169">Poiché i certificati autocertificati non devono essere acquistati da un'autorità attendibile, questo livello viene usato in fase di sviluppo e di debug dei client e dei servizi.</span><span class="sxs-lookup"><span data-stu-id="332e1-169">This value is used when developing and debugging clients and services because self-issued certificates need not be purchased from a trusted authority.</span></span> <span data-ttu-id="332e1-170">Quando si distribuisce un client è invece opportuno usare il livello `ChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="332e1-170">When deploying a client, use the `ChainTrust` value instead.</span></span> <span data-ttu-id="332e1-171">È inoltre possibile impostare il valore su `Custom` o `None`.</span><span class="sxs-lookup"><span data-stu-id="332e1-171">You can also set the value to `Custom` or `None`.</span></span> <span data-ttu-id="332e1-172">Per usare il valore `Custom` è necessario impostare anche l'attributo `customCertificateValidator` sull'assembly e sul tipo usati per convalidare il certificato.</span><span class="sxs-lookup"><span data-stu-id="332e1-172">To use the `Custom` value, you must also set the `customCertificateValidator` attribute to an assembly and type used to validate the certificate.</span></span> <span data-ttu-id="332e1-173">Per creare una convalida personalizzata, è necessario ereditare una classe dalla classe X509CertificateValidator astratta.</span><span class="sxs-lookup"><span data-stu-id="332e1-173">To create your own custom validator, you must inherit from the abstract X509CertificateValidator class.</span></span> <span data-ttu-id="332e1-174">Per ulteriori informazioni, vedere [procedura: creare un servizio che usa un Validator del certificato personalizzato](../../../../../docs/framework/wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md).</span><span class="sxs-lookup"><span data-stu-id="332e1-174">For more information, see [How to: Create a Service that Employs a Custom Certificate Validator](../../../../../docs/framework/wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md).</span></span>  
  
 <span data-ttu-id="332e1-175">L'attributo `revocationMode` specifica il modo in cui i certificati vengono contrassegnati per la revoca.</span><span class="sxs-lookup"><span data-stu-id="332e1-175">The `revocationMode` attribute specifies how certificates are checked for revocation.</span></span> <span data-ttu-id="332e1-176">L'impostazione predefinita è `online` a indicare che i certificati vengono contrassegnati automaticamente per la revoca.</span><span class="sxs-lookup"><span data-stu-id="332e1-176">The default is `online` which indicates that certificates will be checked automatically for revocation.</span></span> <span data-ttu-id="332e1-177">Per ulteriori informazioni, vedere [utilizzo dei certificati](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="332e1-177">For more information, see [Working with Certificates](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="332e1-178">Esempio</span><span class="sxs-lookup"><span data-stu-id="332e1-178">Example</span></span>  
 <span data-ttu-id="332e1-179">Nell'esempio vengono svolte due attività:</span><span class="sxs-lookup"><span data-stu-id="332e1-179">The following example does two tasks.</span></span> <span data-ttu-id="332e1-180">Per prima cosa specifica un certificato del servizio che viene usato dal client per comunicare sul protocollo HTTP con endpoint il cui nome di dominio è www.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="332e1-180">It first specifies a service certificate for the client to use when communicating with endpoints whose domain name is www.contoso.com over the HTTP protocol.</span></span> <span data-ttu-id="332e1-181">In secondo luogo, specifica la modalità di revoca e il percorso dell'archivio usati durante l'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="332e1-181">Second, it specifies the revocation mode and store location used during authentication.</span></span>  
  
```xml  
<serviceCertificate>  
  <defaultCertificate findValue="www.contoso.com"   
                      storeLocation="LocalMachine"  
                      storeName="TrustedPeople"   
                      x509FindType="FindByIssuerDistinguishedName" />  
  <scopedCertificates>  
     <add targetUri="http://www.contoso.com"   
          findValue="www.contoso.com" storeLocation="LocalMachine"  
                  storeName="Root" x509FindType="FindByIssuerName" />  
  </scopedCertificates>  
  <authentication revocationMode="Online"   
   trustedStoreLocation="LocalMachine" />  
</serviceCertificate>  
```  
  
## <a name="see-also"></a><span data-ttu-id="332e1-182">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="332e1-182">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement>  
 <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>  
 <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.Authentication%2A>  
 <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication>  
 [<span data-ttu-id="332e1-183">Comportamenti di sicurezza</span><span class="sxs-lookup"><span data-stu-id="332e1-183">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [<span data-ttu-id="332e1-184">Utilizzo dei certificati</span><span class="sxs-lookup"><span data-stu-id="332e1-184">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [<span data-ttu-id="332e1-185">Procedura: creare un servizio che usa un Validator del certificato personalizzato</span><span class="sxs-lookup"><span data-stu-id="332e1-185">How to: Create a Service that Employs a Custom Certificate Validator</span></span>](../../../../../docs/framework/wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md)  
 [<span data-ttu-id="332e1-186">\<autenticazione ></span><span class="sxs-lookup"><span data-stu-id="332e1-186">\<authentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/authentication-of-clientcertificate-element.md)  
 [<span data-ttu-id="332e1-187">Protezione di client</span><span class="sxs-lookup"><span data-stu-id="332e1-187">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)  
 [<span data-ttu-id="332e1-188">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="332e1-188">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)

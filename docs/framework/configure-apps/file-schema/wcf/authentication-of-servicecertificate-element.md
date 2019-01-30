---
title: <authentication> di <serviceCertificate> elemento
ms.date: 03/30/2017
ms.assetid: 733b67b4-08a1-4d25-9741-10046f9357ef
ms.openlocfilehash: 8288e530d0164b41a6cf53cc39385a2d29fdb091
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55255172"
---
# <a name="authentication-of-servicecertificate-element"></a><span data-ttu-id="3ca6c-102">\<autenticazione > di \<serviceCertificate > elemento</span><span class="sxs-lookup"><span data-stu-id="3ca6c-102">\<authentication> of \<serviceCertificate> Element</span></span>
<span data-ttu-id="3ca6c-103">Specifica le impostazioni usate dal proxy del client per autenticare i certificati dei servizi ottenuti mediante la negoziazione SSL/TLS.</span><span class="sxs-lookup"><span data-stu-id="3ca6c-103">Specifies the settings used by the client proxy to authenticate service certificates that are obtained using SSL/TLS negotiation.</span></span>  
  
 <span data-ttu-id="3ca6c-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="3ca6c-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="3ca6c-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="3ca6c-105">\<behaviors></span></span>  
<span data-ttu-id="3ca6c-106">sezione endpointBehaviors</span><span class="sxs-lookup"><span data-stu-id="3ca6c-106">endpointBehaviors section</span></span>  
<span data-ttu-id="3ca6c-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="3ca6c-107">\<behavior></span></span>  
<span data-ttu-id="3ca6c-108">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="3ca6c-108">\<clientCredentials></span></span>  
<span data-ttu-id="3ca6c-109">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="3ca6c-109">\<serviceCertificate></span></span>  
<span data-ttu-id="3ca6c-110">\<authentication></span><span class="sxs-lookup"><span data-stu-id="3ca6c-110">\<authentication></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3ca6c-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3ca6c-111">Syntax</span></span>  
  
```xml  
<authentication customCertificateValidatorType="String"
                certificateValidationMode="None/PeerTrust/ChainTrust/PeerOrChainTrust/Custom"
                revocationMode="NoCheck/Online/Offline"
                trustedStoreLocation="LocalMachine/CurrentUser" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3ca6c-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="3ca6c-112">Attributes and Elements</span></span>  
 <span data-ttu-id="3ca6c-113">Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.</span><span class="sxs-lookup"><span data-stu-id="3ca6c-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3ca6c-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="3ca6c-114">Attributes</span></span>  
  
|<span data-ttu-id="3ca6c-115">Attributo</span><span class="sxs-lookup"><span data-stu-id="3ca6c-115">Attribute</span></span>|<span data-ttu-id="3ca6c-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3ca6c-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3ca6c-117">customCertificateValidatorType</span><span class="sxs-lookup"><span data-stu-id="3ca6c-117">customCertificateValidatorType</span></span>|<span data-ttu-id="3ca6c-118">Stringa.</span><span class="sxs-lookup"><span data-stu-id="3ca6c-118">String.</span></span> <span data-ttu-id="3ca6c-119">Un tipo e un assembly usati per convalidare un tipo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="3ca6c-119">A type and assembly used to validate a custom type.</span></span>|  
|<span data-ttu-id="3ca6c-120">certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="3ca6c-120">certificateValidationMode</span></span>|<span data-ttu-id="3ca6c-121">Specifica una delle tre modalità usate per convalidare credenziali.</span><span class="sxs-lookup"><span data-stu-id="3ca6c-121">Specifies one of three modes used to validate credentials.</span></span> <span data-ttu-id="3ca6c-122">Se è impostato su `Custom`, è necessario fornire anche un customCertificateValidator.</span><span class="sxs-lookup"><span data-stu-id="3ca6c-122">If set to `Custom`, then a customCertificateValidator must also be supplied.</span></span> <span data-ttu-id="3ca6c-123">Il valore predefinito è `ChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="3ca6c-123">The default is `ChainTrust`.</span></span>|  
|<span data-ttu-id="3ca6c-124">revocationMode</span><span class="sxs-lookup"><span data-stu-id="3ca6c-124">revocationMode</span></span>|<span data-ttu-id="3ca6c-125">Una delle modalità usate per verificare un elenco dei certificati revocati.</span><span class="sxs-lookup"><span data-stu-id="3ca6c-125">One of the modes used to check for a revoked certificate lists (CRL).</span></span> <span data-ttu-id="3ca6c-126">Il valore predefinito è `Online`.</span><span class="sxs-lookup"><span data-stu-id="3ca6c-126">The default is `Online`.</span></span>|  
|<span data-ttu-id="3ca6c-127">trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="3ca6c-127">trustedStoreLocation</span></span>|<span data-ttu-id="3ca6c-128">Uno di due percorsi dell'archivio di sistema: `LocalMachine` o `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="3ca6c-128">One of the two system store locations: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="3ca6c-129">Questo valore viene usato quando viene negoziato un certificato del servizio con il client.</span><span class="sxs-lookup"><span data-stu-id="3ca6c-129">This value is used when a service certificate is negotiated to the client.</span></span> <span data-ttu-id="3ca6c-130">La convalida viene eseguita sul **persone attendibili** archiviare nel percorso dell'archivio specificato.</span><span class="sxs-lookup"><span data-stu-id="3ca6c-130">Validation is performed against the **Trusted People** store in the specified store location.</span></span> <span data-ttu-id="3ca6c-131">Il valore predefinito è `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="3ca6c-131">The default is `CurrentUser`.</span></span>|  
  
## <a name="customcertificatevalidator-attribute"></a><span data-ttu-id="3ca6c-132">Attributo customCertificateValidator</span><span class="sxs-lookup"><span data-stu-id="3ca6c-132">customCertificateValidator Attribute</span></span>  
  
|<span data-ttu-id="3ca6c-133">Valore</span><span class="sxs-lookup"><span data-stu-id="3ca6c-133">Value</span></span>|<span data-ttu-id="3ca6c-134">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3ca6c-134">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="3ca6c-135">String</span><span class="sxs-lookup"><span data-stu-id="3ca6c-135">String</span></span>|<span data-ttu-id="3ca6c-136">Specifica il nome e l'assembly del tipo e altri dati usati per trovare il tipo.</span><span class="sxs-lookup"><span data-stu-id="3ca6c-136">Specifies the type name and assembly and other data used to find the type.</span></span>|  
  
## <a name="certificatevalidationmode-attribute"></a><span data-ttu-id="3ca6c-137">Attributo certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="3ca6c-137">certificateValidationMode Attribute</span></span>  
  
|<span data-ttu-id="3ca6c-138">Valore</span><span class="sxs-lookup"><span data-stu-id="3ca6c-138">Value</span></span>|<span data-ttu-id="3ca6c-139">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3ca6c-139">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="3ca6c-140">Enumerazione</span><span class="sxs-lookup"><span data-stu-id="3ca6c-140">Enumeration</span></span>|<span data-ttu-id="3ca6c-141">Uno dei valori seguenti: None, PeerTrust, ChainTrust, PeerOrChainTrust, Custom.</span><span class="sxs-lookup"><span data-stu-id="3ca6c-141">One of the following values: None, PeerTrust, ChainTrust, PeerOrChainTrust, Custom.</span></span><br /><br /> <span data-ttu-id="3ca6c-142">Per altre informazioni, vedere [Working with Certificates](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="3ca6c-142">For more information, see [Working with Certificates](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="revocationmode-attribute"></a><span data-ttu-id="3ca6c-143">Attributo revocationMode</span><span class="sxs-lookup"><span data-stu-id="3ca6c-143">revocationMode Attribute</span></span>  
  
|<span data-ttu-id="3ca6c-144">Valore</span><span class="sxs-lookup"><span data-stu-id="3ca6c-144">Value</span></span>|<span data-ttu-id="3ca6c-145">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3ca6c-145">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="3ca6c-146">Enumerazione</span><span class="sxs-lookup"><span data-stu-id="3ca6c-146">Enumeration</span></span>|<span data-ttu-id="3ca6c-147">Uno dei valori seguenti: NoCheck, Online, Offline.</span><span class="sxs-lookup"><span data-stu-id="3ca6c-147">One of the following values: NoCheck, Online, Offline.</span></span><br /><br /> <span data-ttu-id="3ca6c-148">Per altre informazioni, vedere [Working with Certificates](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="3ca6c-148">For more information, see [Working with Certificates](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="trustedstorelocation-attribute"></a><span data-ttu-id="3ca6c-149">Attributo trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="3ca6c-149">trustedStoreLocation Attribute</span></span>  
  
|<span data-ttu-id="3ca6c-150">Valore</span><span class="sxs-lookup"><span data-stu-id="3ca6c-150">Value</span></span>|<span data-ttu-id="3ca6c-151">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3ca6c-151">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="3ca6c-152">Enumerazione</span><span class="sxs-lookup"><span data-stu-id="3ca6c-152">Enumeration</span></span>|<span data-ttu-id="3ca6c-153">Uno dei valori seguenti: LocalMachine o CurrentUser.</span><span class="sxs-lookup"><span data-stu-id="3ca6c-153">One of the following values: LocalMachine or CurrentUser.</span></span> <span data-ttu-id="3ca6c-154">L'impostazione predefinita è CurrentUser.</span><span class="sxs-lookup"><span data-stu-id="3ca6c-154">The default is CurrentUser.</span></span> <span data-ttu-id="3ca6c-155">Se l'applicazione client è in esecuzione con un account di sistema, il certificato è in genere in LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="3ca6c-155">If the client application is running under a system account, then the certificate is typically under LocalMachine.</span></span> <span data-ttu-id="3ca6c-156">Se l'applicazione client è in esecuzione con un account utente, il certificato è in genere in CurrentUser.</span><span class="sxs-lookup"><span data-stu-id="3ca6c-156">If the client application is running under a user account, then the certificate is typically in CurrentUser.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3ca6c-157">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="3ca6c-157">Child Elements</span></span>  
 <span data-ttu-id="3ca6c-158">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="3ca6c-158">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3ca6c-159">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="3ca6c-159">Parent Elements</span></span>  
  
|<span data-ttu-id="3ca6c-160">Elemento</span><span class="sxs-lookup"><span data-stu-id="3ca6c-160">Element</span></span>|<span data-ttu-id="3ca6c-161">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3ca6c-161">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3ca6c-162">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="3ca6c-162">\<serviceCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-clientcredentials-element.md)|<span data-ttu-id="3ca6c-163">Specifica un certificato da usare per l'autenticazione di un servizio presso il client.</span><span class="sxs-lookup"><span data-stu-id="3ca6c-163">Specifies a certificate to use when authenticating a service to the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3ca6c-164">Note</span><span class="sxs-lookup"><span data-stu-id="3ca6c-164">Remarks</span></span>  
 <span data-ttu-id="3ca6c-165">L'attributo `certificateValidationMode` di questo elemento di configurazione specifica il livello di attendibilità usato per autenticare i certificati.</span><span class="sxs-lookup"><span data-stu-id="3ca6c-165">The `certificateValidationMode` attribute of this configuration element specifies the level of trust used to authenticate certificates.</span></span> <span data-ttu-id="3ca6c-166">Per impostazione predefinita, il livello è impostato su `ChainTrust`. Tale impostazione prevede che ogni certificato appartenga a una gerarchia di certificati che termina in un'autorità di certificazione attendibile situata all'inizio della catena.</span><span class="sxs-lookup"><span data-stu-id="3ca6c-166">By default, the level is set to `ChainTrust`, which specifies that each certificate must be found in a hierarchy of certificates ending in a trusted certification authority at the top of the chain.</span></span> <span data-ttu-id="3ca6c-167">Si tratta della modalità più sicura.</span><span class="sxs-lookup"><span data-stu-id="3ca6c-167">This is the most secure mode.</span></span> <span data-ttu-id="3ca6c-168">Il livello può inoltre essere impostato su `PeerOrChainTrust`, a indicare che sia i certificati autocertificati (trust peer) sia i certificati appartenenti a una catena di trust sono ritenuti attendibili.</span><span class="sxs-lookup"><span data-stu-id="3ca6c-168">You can also set the value to `PeerOrChainTrust`, which specifies that self-issued certificates (peer trust) are accepted as well as certificates that are in a trusted chain.</span></span> <span data-ttu-id="3ca6c-169">Poiché i certificati autocertificati non devono essere acquistati da un'autorità attendibile, questo livello viene usato in fase di sviluppo e di debug dei client e dei servizi.</span><span class="sxs-lookup"><span data-stu-id="3ca6c-169">This value is used when developing and debugging clients and services because self-issued certificates need not be purchased from a trusted authority.</span></span> <span data-ttu-id="3ca6c-170">Quando si distribuisce un client è invece opportuno usare il livello `ChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="3ca6c-170">When deploying a client, use the `ChainTrust` value instead.</span></span> <span data-ttu-id="3ca6c-171">È inoltre possibile impostare il valore su `Custom` o `None`.</span><span class="sxs-lookup"><span data-stu-id="3ca6c-171">You can also set the value to `Custom` or `None`.</span></span> <span data-ttu-id="3ca6c-172">Per usare il valore `Custom` è necessario impostare anche l'attributo `customCertificateValidator` sull'assembly e sul tipo usati per convalidare il certificato.</span><span class="sxs-lookup"><span data-stu-id="3ca6c-172">To use the `Custom` value, you must also set the `customCertificateValidator` attribute to an assembly and type used to validate the certificate.</span></span> <span data-ttu-id="3ca6c-173">Per creare una convalida personalizzata, è necessario ereditare una classe dalla classe X509CertificateValidator astratta.</span><span class="sxs-lookup"><span data-stu-id="3ca6c-173">To create your own custom validator, you must inherit from the abstract X509CertificateValidator class.</span></span> <span data-ttu-id="3ca6c-174">Per altre informazioni, vedere [Procedura: Creare un servizio che usa un Validator del certificato personalizzato](../../../../../docs/framework/wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md).</span><span class="sxs-lookup"><span data-stu-id="3ca6c-174">For more information, see [How to: Create a Service that Employs a Custom Certificate Validator](../../../../../docs/framework/wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md).</span></span>  
  
 <span data-ttu-id="3ca6c-175">L'attributo `revocationMode` specifica il modo in cui i certificati vengono contrassegnati per la revoca.</span><span class="sxs-lookup"><span data-stu-id="3ca6c-175">The `revocationMode` attribute specifies how certificates are checked for revocation.</span></span> <span data-ttu-id="3ca6c-176">L'impostazione predefinita è `online` a indicare che i certificati vengono contrassegnati automaticamente per la revoca.</span><span class="sxs-lookup"><span data-stu-id="3ca6c-176">The default is `online` which indicates that certificates will be checked automatically for revocation.</span></span> <span data-ttu-id="3ca6c-177">Per altre informazioni, vedere [Working with Certificates](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="3ca6c-177">For more information, see [Working with Certificates](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3ca6c-178">Esempio</span><span class="sxs-lookup"><span data-stu-id="3ca6c-178">Example</span></span>  
 <span data-ttu-id="3ca6c-179">Nell'esempio vengono svolte due attività:</span><span class="sxs-lookup"><span data-stu-id="3ca6c-179">The following example does two tasks.</span></span> <span data-ttu-id="3ca6c-180">Per prima cosa specifica un certificato di servizio per il client da utilizzare per comunicare con endpoint il cui nome di dominio è `www.contoso.com` sul protocollo HTTP.</span><span class="sxs-lookup"><span data-stu-id="3ca6c-180">It first specifies a service certificate for the client to use when communicating with endpoints whose domain name is `www.contoso.com` over the HTTP protocol.</span></span> <span data-ttu-id="3ca6c-181">In secondo luogo, specifica la modalità di revoca e il percorso dell'archivio usati durante l'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="3ca6c-181">Second, it specifies the revocation mode and store location used during authentication.</span></span>  
  
```xml  
<serviceCertificate>
  <defaultCertificate findValue="www.contoso.com"
                      storeLocation="LocalMachine"
                      storeName="TrustedPeople"
                      x509FindType="FindByIssuerDistinguishedName" />
  <scopedCertificates>
     <add targetUri="http://www.contoso.com"
          findValue="www.contoso.com"
          storeLocation="LocalMachine"
          storeName="Root"
          x509FindType="FindByIssuerName" />
  </scopedCertificates>
  <authentication revocationMode="Online"
                  trustedStoreLocation="LocalMachine" />
</serviceCertificate>
```  
  
## <a name="see-also"></a><span data-ttu-id="3ca6c-182">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3ca6c-182">See also</span></span>
- <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.Authentication%2A>
- <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication>
- [<span data-ttu-id="3ca6c-183">Comportamenti di sicurezza</span><span class="sxs-lookup"><span data-stu-id="3ca6c-183">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="3ca6c-184">Uso di certificati</span><span class="sxs-lookup"><span data-stu-id="3ca6c-184">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="3ca6c-185">Procedura: Creare un servizio che usa un Validator del certificato personalizzato</span><span class="sxs-lookup"><span data-stu-id="3ca6c-185">How to: Create a Service that Employs a Custom Certificate Validator</span></span>](../../../../../docs/framework/wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md)
- [<span data-ttu-id="3ca6c-186">\<authentication></span><span class="sxs-lookup"><span data-stu-id="3ca6c-186">\<authentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/authentication-of-clientcertificate-element.md)
- [<span data-ttu-id="3ca6c-187">Protezione di client</span><span class="sxs-lookup"><span data-stu-id="3ca6c-187">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)
- [<span data-ttu-id="3ca6c-188">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="3ca6c-188">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)

---
title: <authentication>dell' <serviceCertificate> elemento
ms.date: 03/30/2017
ms.assetid: 733b67b4-08a1-4d25-9741-10046f9357ef
ms.openlocfilehash: 29170f032469b4d55b50f57ca06ce403a5aeaf2c
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398222"
---
# <a name="authentication-of-servicecertificate-element"></a><span data-ttu-id="41db0-102">\<> di autenticazione \<dell'elemento > serviceCertificate</span><span class="sxs-lookup"><span data-stu-id="41db0-102">\<authentication> of \<serviceCertificate> Element</span></span>
<span data-ttu-id="41db0-103">Specifica le impostazioni usate dal proxy del client per autenticare i certificati dei servizi ottenuti mediante la negoziazione SSL/TLS.</span><span class="sxs-lookup"><span data-stu-id="41db0-103">Specifies the settings used by the client proxy to authenticate service certificates that are obtained using SSL/TLS negotiation.</span></span>  
  
<span data-ttu-id="41db0-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="41db0-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="41db0-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="41db0-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="41db0-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamenti >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="41db0-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="41db0-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> endpointBehaviors**](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="41db0-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="41db0-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamento >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="41db0-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="41db0-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> clientCredentials**](clientcredentials.md)</span><span class="sxs-lookup"><span data-stu-id="41db0-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)</span></span>\
<span data-ttu-id="41db0-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> serviceCertificate**](servicecertificate-of-clientcredentials-element.md)</span><span class="sxs-lookup"><span data-stu-id="41db0-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCertificate>**](servicecertificate-of-clientcredentials-element.md)</span></span>\
<span data-ttu-id="41db0-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> di autenticazione**</span><span class="sxs-lookup"><span data-stu-id="41db0-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<authentication>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="41db0-112">Sintassi</span><span class="sxs-lookup"><span data-stu-id="41db0-112">Syntax</span></span>  
  
```xml  
<authentication customCertificateValidatorType="String"
                certificateValidationMode="None/PeerTrust/ChainTrust/PeerOrChainTrust/Custom"
                revocationMode="NoCheck/Online/Offline"
                trustedStoreLocation="LocalMachine/CurrentUser" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="41db0-113">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="41db0-113">Attributes and Elements</span></span>  
 <span data-ttu-id="41db0-114">Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.</span><span class="sxs-lookup"><span data-stu-id="41db0-114">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="41db0-115">Attributi</span><span class="sxs-lookup"><span data-stu-id="41db0-115">Attributes</span></span>  
  
|<span data-ttu-id="41db0-116">Attributo</span><span class="sxs-lookup"><span data-stu-id="41db0-116">Attribute</span></span>|<span data-ttu-id="41db0-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="41db0-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="41db0-118">customCertificateValidatorType</span><span class="sxs-lookup"><span data-stu-id="41db0-118">customCertificateValidatorType</span></span>|<span data-ttu-id="41db0-119">Stringa.</span><span class="sxs-lookup"><span data-stu-id="41db0-119">String.</span></span> <span data-ttu-id="41db0-120">Un tipo e un assembly usati per convalidare un tipo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="41db0-120">A type and assembly used to validate a custom type.</span></span>|  
|<span data-ttu-id="41db0-121">certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="41db0-121">certificateValidationMode</span></span>|<span data-ttu-id="41db0-122">Specifica una delle tre modalità usate per convalidare credenziali.</span><span class="sxs-lookup"><span data-stu-id="41db0-122">Specifies one of three modes used to validate credentials.</span></span> <span data-ttu-id="41db0-123">Se è impostato su `Custom`, è necessario fornire anche un customCertificateValidator.</span><span class="sxs-lookup"><span data-stu-id="41db0-123">If set to `Custom`, then a customCertificateValidator must also be supplied.</span></span> <span data-ttu-id="41db0-124">Il valore predefinito è `ChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="41db0-124">The default is `ChainTrust`.</span></span>|  
|<span data-ttu-id="41db0-125">revocationMode</span><span class="sxs-lookup"><span data-stu-id="41db0-125">revocationMode</span></span>|<span data-ttu-id="41db0-126">Una delle modalità usate per verificare un elenco dei certificati revocati.</span><span class="sxs-lookup"><span data-stu-id="41db0-126">One of the modes used to check for a revoked certificate lists (CRL).</span></span> <span data-ttu-id="41db0-127">Il valore predefinito è `Online`.</span><span class="sxs-lookup"><span data-stu-id="41db0-127">The default is `Online`.</span></span>|  
|<span data-ttu-id="41db0-128">trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="41db0-128">trustedStoreLocation</span></span>|<span data-ttu-id="41db0-129">Uno di due percorsi dell'archivio di sistema: `LocalMachine` o `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="41db0-129">One of the two system store locations: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="41db0-130">Questo valore viene usato quando viene negoziato un certificato del servizio con il client.</span><span class="sxs-lookup"><span data-stu-id="41db0-130">This value is used when a service certificate is negotiated to the client.</span></span> <span data-ttu-id="41db0-131">La convalida viene eseguita sull'archivio **persone attendibili** nel percorso di archiviazione specificato.</span><span class="sxs-lookup"><span data-stu-id="41db0-131">Validation is performed against the **Trusted People** store in the specified store location.</span></span> <span data-ttu-id="41db0-132">Il valore predefinito è `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="41db0-132">The default is `CurrentUser`.</span></span>|  
  
## <a name="customcertificatevalidator-attribute"></a><span data-ttu-id="41db0-133">Attributo customCertificateValidator</span><span class="sxs-lookup"><span data-stu-id="41db0-133">customCertificateValidator Attribute</span></span>  
  
|<span data-ttu-id="41db0-134">Value</span><span class="sxs-lookup"><span data-stu-id="41db0-134">Value</span></span>|<span data-ttu-id="41db0-135">Descrizione</span><span class="sxs-lookup"><span data-stu-id="41db0-135">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="41db0-136">String</span><span class="sxs-lookup"><span data-stu-id="41db0-136">String</span></span>|<span data-ttu-id="41db0-137">Specifica il nome e l'assembly del tipo e altri dati usati per trovare il tipo.</span><span class="sxs-lookup"><span data-stu-id="41db0-137">Specifies the type name and assembly and other data used to find the type.</span></span>|  
  
## <a name="certificatevalidationmode-attribute"></a><span data-ttu-id="41db0-138">Attributo certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="41db0-138">certificateValidationMode Attribute</span></span>  
  
|<span data-ttu-id="41db0-139">Valore</span><span class="sxs-lookup"><span data-stu-id="41db0-139">Value</span></span>|<span data-ttu-id="41db0-140">Descrizione</span><span class="sxs-lookup"><span data-stu-id="41db0-140">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="41db0-141">Enumerazione</span><span class="sxs-lookup"><span data-stu-id="41db0-141">Enumeration</span></span>|<span data-ttu-id="41db0-142">Uno dei valori seguenti: None, PeerTrust, ChainTrust, PeerOrChainTrust, Custom.</span><span class="sxs-lookup"><span data-stu-id="41db0-142">One of the following values: None, PeerTrust, ChainTrust, PeerOrChainTrust, Custom.</span></span><br /><br /> <span data-ttu-id="41db0-143">Per ulteriori informazioni, vedere [utilizzo dei certificati](../../../wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="41db0-143">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="revocationmode-attribute"></a><span data-ttu-id="41db0-144">Attributo revocationMode</span><span class="sxs-lookup"><span data-stu-id="41db0-144">revocationMode Attribute</span></span>  
  
|<span data-ttu-id="41db0-145">Value</span><span class="sxs-lookup"><span data-stu-id="41db0-145">Value</span></span>|<span data-ttu-id="41db0-146">Descrizione</span><span class="sxs-lookup"><span data-stu-id="41db0-146">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="41db0-147">Enumerazione</span><span class="sxs-lookup"><span data-stu-id="41db0-147">Enumeration</span></span>|<span data-ttu-id="41db0-148">Uno dei valori seguenti: NOCHECK, online, offline.</span><span class="sxs-lookup"><span data-stu-id="41db0-148">One of the following values: NoCheck, Online, Offline.</span></span><br /><br /> <span data-ttu-id="41db0-149">Per ulteriori informazioni, vedere [utilizzo dei certificati](../../../wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="41db0-149">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="trustedstorelocation-attribute"></a><span data-ttu-id="41db0-150">Attributo trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="41db0-150">trustedStoreLocation Attribute</span></span>  
  
|<span data-ttu-id="41db0-151">Value</span><span class="sxs-lookup"><span data-stu-id="41db0-151">Value</span></span>|<span data-ttu-id="41db0-152">Descrizione</span><span class="sxs-lookup"><span data-stu-id="41db0-152">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="41db0-153">Enumerazione</span><span class="sxs-lookup"><span data-stu-id="41db0-153">Enumeration</span></span>|<span data-ttu-id="41db0-154">Uno dei valori seguenti: LocalMachine o CurrentUser.</span><span class="sxs-lookup"><span data-stu-id="41db0-154">One of the following values: LocalMachine or CurrentUser.</span></span> <span data-ttu-id="41db0-155">L'impostazione predefinita è CurrentUser.</span><span class="sxs-lookup"><span data-stu-id="41db0-155">The default is CurrentUser.</span></span> <span data-ttu-id="41db0-156">Se l'applicazione client è in esecuzione con un account di sistema, il certificato è in genere in LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="41db0-156">If the client application is running under a system account, then the certificate is typically under LocalMachine.</span></span> <span data-ttu-id="41db0-157">Se l'applicazione client è in esecuzione con un account utente, il certificato è in genere in CurrentUser.</span><span class="sxs-lookup"><span data-stu-id="41db0-157">If the client application is running under a user account, then the certificate is typically in CurrentUser.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="41db0-158">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="41db0-158">Child Elements</span></span>  
 <span data-ttu-id="41db0-159">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="41db0-159">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="41db0-160">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="41db0-160">Parent Elements</span></span>  
  
|<span data-ttu-id="41db0-161">Elemento</span><span class="sxs-lookup"><span data-stu-id="41db0-161">Element</span></span>|<span data-ttu-id="41db0-162">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="41db0-162">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="41db0-163">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="41db0-163">\<serviceCertificate></span></span>](servicecertificate-of-clientcredentials-element.md)|<span data-ttu-id="41db0-164">Specifica un certificato da usare per l'autenticazione di un servizio presso il client.</span><span class="sxs-lookup"><span data-stu-id="41db0-164">Specifies a certificate to use when authenticating a service to the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="41db0-165">Note</span><span class="sxs-lookup"><span data-stu-id="41db0-165">Remarks</span></span>  
 <span data-ttu-id="41db0-166">L'attributo `certificateValidationMode` di questo elemento di configurazione specifica il livello di attendibilità usato per autenticare i certificati.</span><span class="sxs-lookup"><span data-stu-id="41db0-166">The `certificateValidationMode` attribute of this configuration element specifies the level of trust used to authenticate certificates.</span></span> <span data-ttu-id="41db0-167">Per impostazione predefinita, il livello è impostato su `ChainTrust`. Tale impostazione prevede che ogni certificato appartenga a una gerarchia di certificati che termina in un'autorità di certificazione attendibile situata all'inizio della catena.</span><span class="sxs-lookup"><span data-stu-id="41db0-167">By default, the level is set to `ChainTrust`, which specifies that each certificate must be found in a hierarchy of certificates ending in a trusted certification authority at the top of the chain.</span></span> <span data-ttu-id="41db0-168">Si tratta della modalità più protetta.</span><span class="sxs-lookup"><span data-stu-id="41db0-168">This is the most secure mode.</span></span> <span data-ttu-id="41db0-169">Il livello può inoltre essere impostato su `PeerOrChainTrust`, a indicare che sia i certificati autocertificati (trust peer) sia i certificati appartenenti a una catena di trust sono ritenuti attendibili.</span><span class="sxs-lookup"><span data-stu-id="41db0-169">You can also set the value to `PeerOrChainTrust`, which specifies that self-issued certificates (peer trust) are accepted as well as certificates that are in a trusted chain.</span></span> <span data-ttu-id="41db0-170">Poiché i certificati autocertificati non devono essere acquistati da un'autorità attendibile, questo livello viene usato in fase di sviluppo e di debug dei client e dei servizi.</span><span class="sxs-lookup"><span data-stu-id="41db0-170">This value is used when developing and debugging clients and services because self-issued certificates need not be purchased from a trusted authority.</span></span> <span data-ttu-id="41db0-171">Quando si distribuisce un client è invece opportuno usare il livello `ChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="41db0-171">When deploying a client, use the `ChainTrust` value instead.</span></span> <span data-ttu-id="41db0-172">È inoltre possibile impostare il valore su `Custom` o `None`.</span><span class="sxs-lookup"><span data-stu-id="41db0-172">You can also set the value to `Custom` or `None`.</span></span> <span data-ttu-id="41db0-173">Per usare il valore `Custom` è necessario impostare anche l'attributo `customCertificateValidator` sull'assembly e sul tipo usati per convalidare il certificato.</span><span class="sxs-lookup"><span data-stu-id="41db0-173">To use the `Custom` value, you must also set the `customCertificateValidator` attribute to an assembly and type used to validate the certificate.</span></span> <span data-ttu-id="41db0-174">Per creare una convalida personalizzata, è necessario ereditare una classe dalla classe X509CertificateValidator astratta.</span><span class="sxs-lookup"><span data-stu-id="41db0-174">To create your own custom validator, you must inherit from the abstract X509CertificateValidator class.</span></span> <span data-ttu-id="41db0-175">Per altre informazioni, vedere [Procedura: Creare un servizio che usa un validator](../../../wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md)del certificato personalizzato.</span><span class="sxs-lookup"><span data-stu-id="41db0-175">For more information, see [How to: Create a Service that Employs a Custom Certificate Validator](../../../wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md).</span></span>  
  
 <span data-ttu-id="41db0-176">L'attributo `revocationMode` specifica il modo in cui i certificati vengono contrassegnati per la revoca.</span><span class="sxs-lookup"><span data-stu-id="41db0-176">The `revocationMode` attribute specifies how certificates are checked for revocation.</span></span> <span data-ttu-id="41db0-177">L'impostazione predefinita è `online` a indicare che i certificati vengono contrassegnati automaticamente per la revoca.</span><span class="sxs-lookup"><span data-stu-id="41db0-177">The default is `online` which indicates that certificates will be checked automatically for revocation.</span></span> <span data-ttu-id="41db0-178">Per ulteriori informazioni, vedere [utilizzo dei certificati](../../../wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="41db0-178">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="41db0-179">Esempio</span><span class="sxs-lookup"><span data-stu-id="41db0-179">Example</span></span>  
 <span data-ttu-id="41db0-180">Nell'esempio vengono svolte due attività:</span><span class="sxs-lookup"><span data-stu-id="41db0-180">The following example does two tasks.</span></span> <span data-ttu-id="41db0-181">Per prima cosa specifica un certificato di servizio che il client deve usare durante la comunicazione con gli endpoint il `www.contoso.com` cui nome di dominio è sul protocollo http.</span><span class="sxs-lookup"><span data-stu-id="41db0-181">It first specifies a service certificate for the client to use when communicating with endpoints whose domain name is `www.contoso.com` over the HTTP protocol.</span></span> <span data-ttu-id="41db0-182">In secondo luogo, specifica la modalità di revoca e il percorso dell'archivio usati durante l'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="41db0-182">Second, it specifies the revocation mode and store location used during authentication.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="41db0-183">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="41db0-183">See also</span></span>

- <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.Authentication%2A>
- <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication>
- [<span data-ttu-id="41db0-184">Comportamenti di sicurezza</span><span class="sxs-lookup"><span data-stu-id="41db0-184">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="41db0-185">Uso di certificati</span><span class="sxs-lookup"><span data-stu-id="41db0-185">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="41db0-186">Procedura: Creare un servizio che usa un validator del certificato personalizzato</span><span class="sxs-lookup"><span data-stu-id="41db0-186">How to: Create a Service that Employs a Custom Certificate Validator</span></span>](../../../wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md)
- [<span data-ttu-id="41db0-187">\<authentication></span><span class="sxs-lookup"><span data-stu-id="41db0-187">\<authentication></span></span>](authentication-of-clientcertificate-element.md)
- [<span data-ttu-id="41db0-188">Protezione di client</span><span class="sxs-lookup"><span data-stu-id="41db0-188">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="41db0-189">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="41db0-189">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)

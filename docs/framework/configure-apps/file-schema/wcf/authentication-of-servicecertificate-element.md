---
title: <authentication>dell' <serviceCertificate> elemento
ms.date: 03/30/2017
ms.assetid: 733b67b4-08a1-4d25-9741-10046f9357ef
ms.openlocfilehash: 29170f032469b4d55b50f57ca06ce403a5aeaf2c
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70398222"
---
# <a name="authentication-of-servicecertificate-element"></a><span data-ttu-id="5f658-102">\<authentication>dell' \<serviceCertificate> elemento</span><span class="sxs-lookup"><span data-stu-id="5f658-102">\<authentication> of \<serviceCertificate> Element</span></span>
<span data-ttu-id="5f658-103">Specifica le impostazioni usate dal proxy del client per autenticare i certificati dei servizi ottenuti mediante la negoziazione SSL/TLS.</span><span class="sxs-lookup"><span data-stu-id="5f658-103">Specifies the settings used by the client proxy to authenticate service certificates that are obtained using SSL/TLS negotiation.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCertificate>**](servicecertificate-of-clientcredentials-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<authentication>**  
  
## <a name="syntax"></a><span data-ttu-id="5f658-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5f658-104">Syntax</span></span>  
  
```xml  
<authentication customCertificateValidatorType="String"
                certificateValidationMode="None/PeerTrust/ChainTrust/PeerOrChainTrust/Custom"
                revocationMode="NoCheck/Online/Offline"
                trustedStoreLocation="LocalMachine/CurrentUser" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5f658-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="5f658-105">Attributes and Elements</span></span>  
 <span data-ttu-id="5f658-106">Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.</span><span class="sxs-lookup"><span data-stu-id="5f658-106">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5f658-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="5f658-107">Attributes</span></span>  
  
|<span data-ttu-id="5f658-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="5f658-108">Attribute</span></span>|<span data-ttu-id="5f658-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5f658-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5f658-110">customCertificateValidatorType</span><span class="sxs-lookup"><span data-stu-id="5f658-110">customCertificateValidatorType</span></span>|<span data-ttu-id="5f658-111">Stringa.</span><span class="sxs-lookup"><span data-stu-id="5f658-111">String.</span></span> <span data-ttu-id="5f658-112">Un tipo e un assembly usati per convalidare un tipo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="5f658-112">A type and assembly used to validate a custom type.</span></span>|  
|<span data-ttu-id="5f658-113">certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="5f658-113">certificateValidationMode</span></span>|<span data-ttu-id="5f658-114">Specifica una delle tre modalità usate per convalidare credenziali.</span><span class="sxs-lookup"><span data-stu-id="5f658-114">Specifies one of three modes used to validate credentials.</span></span> <span data-ttu-id="5f658-115">Se è impostato su `Custom`, è necessario fornire anche un customCertificateValidator.</span><span class="sxs-lookup"><span data-stu-id="5f658-115">If set to `Custom`, then a customCertificateValidator must also be supplied.</span></span> <span data-ttu-id="5f658-116">Il valore predefinito è `ChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="5f658-116">The default is `ChainTrust`.</span></span>|  
|<span data-ttu-id="5f658-117">revocationMode</span><span class="sxs-lookup"><span data-stu-id="5f658-117">revocationMode</span></span>|<span data-ttu-id="5f658-118">Una delle modalità usate per verificare un elenco dei certificati revocati.</span><span class="sxs-lookup"><span data-stu-id="5f658-118">One of the modes used to check for a revoked certificate lists (CRL).</span></span> <span data-ttu-id="5f658-119">Il valore predefinito è `Online`.</span><span class="sxs-lookup"><span data-stu-id="5f658-119">The default is `Online`.</span></span>|  
|<span data-ttu-id="5f658-120">trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="5f658-120">trustedStoreLocation</span></span>|<span data-ttu-id="5f658-121">Uno di due percorsi dell'archivio di sistema: `LocalMachine` o `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="5f658-121">One of the two system store locations: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="5f658-122">Questo valore viene usato quando viene negoziato un certificato del servizio con il client.</span><span class="sxs-lookup"><span data-stu-id="5f658-122">This value is used when a service certificate is negotiated to the client.</span></span> <span data-ttu-id="5f658-123">La convalida viene eseguita sull'archivio **persone attendibili** nel percorso di archiviazione specificato.</span><span class="sxs-lookup"><span data-stu-id="5f658-123">Validation is performed against the **Trusted People** store in the specified store location.</span></span> <span data-ttu-id="5f658-124">Il valore predefinito è `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="5f658-124">The default is `CurrentUser`.</span></span>|  
  
## <a name="customcertificatevalidator-attribute"></a><span data-ttu-id="5f658-125">Attributo customCertificateValidator</span><span class="sxs-lookup"><span data-stu-id="5f658-125">customCertificateValidator Attribute</span></span>  
  
|<span data-ttu-id="5f658-126">Valore</span><span class="sxs-lookup"><span data-stu-id="5f658-126">Value</span></span>|<span data-ttu-id="5f658-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5f658-127">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="5f658-128">string</span><span class="sxs-lookup"><span data-stu-id="5f658-128">String</span></span>|<span data-ttu-id="5f658-129">Specifica il nome e l'assembly del tipo e altri dati usati per trovare il tipo.</span><span class="sxs-lookup"><span data-stu-id="5f658-129">Specifies the type name and assembly and other data used to find the type.</span></span>|  
  
## <a name="certificatevalidationmode-attribute"></a><span data-ttu-id="5f658-130">Attributo certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="5f658-130">certificateValidationMode Attribute</span></span>  
  
|<span data-ttu-id="5f658-131">Valore</span><span class="sxs-lookup"><span data-stu-id="5f658-131">Value</span></span>|<span data-ttu-id="5f658-132">Description</span><span class="sxs-lookup"><span data-stu-id="5f658-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="5f658-133">Enumerazione</span><span class="sxs-lookup"><span data-stu-id="5f658-133">Enumeration</span></span>|<span data-ttu-id="5f658-134">Uno dei valori seguenti: None, PeerTrust, ChainTrust, PeerOrChainTrust, Custom.</span><span class="sxs-lookup"><span data-stu-id="5f658-134">One of the following values: None, PeerTrust, ChainTrust, PeerOrChainTrust, Custom.</span></span><br /><br /> <span data-ttu-id="5f658-135">Per ulteriori informazioni, vedere [utilizzo dei certificati](../../../wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="5f658-135">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="revocationmode-attribute"></a><span data-ttu-id="5f658-136">Attributo revocationMode</span><span class="sxs-lookup"><span data-stu-id="5f658-136">revocationMode Attribute</span></span>  
  
|<span data-ttu-id="5f658-137">Valore</span><span class="sxs-lookup"><span data-stu-id="5f658-137">Value</span></span>|<span data-ttu-id="5f658-138">Description</span><span class="sxs-lookup"><span data-stu-id="5f658-138">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="5f658-139">Enumerazione</span><span class="sxs-lookup"><span data-stu-id="5f658-139">Enumeration</span></span>|<span data-ttu-id="5f658-140">Uno dei valori seguenti: NoCheck, Online, Offline.</span><span class="sxs-lookup"><span data-stu-id="5f658-140">One of the following values: NoCheck, Online, Offline.</span></span><br /><br /> <span data-ttu-id="5f658-141">Per ulteriori informazioni, vedere [utilizzo dei certificati](../../../wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="5f658-141">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="trustedstorelocation-attribute"></a><span data-ttu-id="5f658-142">Attributo trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="5f658-142">trustedStoreLocation Attribute</span></span>  
  
|<span data-ttu-id="5f658-143">Valore</span><span class="sxs-lookup"><span data-stu-id="5f658-143">Value</span></span>|<span data-ttu-id="5f658-144">Description</span><span class="sxs-lookup"><span data-stu-id="5f658-144">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="5f658-145">Enumerazione</span><span class="sxs-lookup"><span data-stu-id="5f658-145">Enumeration</span></span>|<span data-ttu-id="5f658-146">Uno dei valori seguenti: LocalMachine o CurrentUser.</span><span class="sxs-lookup"><span data-stu-id="5f658-146">One of the following values: LocalMachine or CurrentUser.</span></span> <span data-ttu-id="5f658-147">L'impostazione predefinita è CurrentUser.</span><span class="sxs-lookup"><span data-stu-id="5f658-147">The default is CurrentUser.</span></span> <span data-ttu-id="5f658-148">Se l'applicazione client è in esecuzione con un account di sistema, il certificato è in genere in LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="5f658-148">If the client application is running under a system account, then the certificate is typically under LocalMachine.</span></span> <span data-ttu-id="5f658-149">Se l'applicazione client è in esecuzione con un account utente, il certificato è in genere in CurrentUser.</span><span class="sxs-lookup"><span data-stu-id="5f658-149">If the client application is running under a user account, then the certificate is typically in CurrentUser.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5f658-150">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="5f658-150">Child Elements</span></span>  
 <span data-ttu-id="5f658-151">No.</span><span class="sxs-lookup"><span data-stu-id="5f658-151">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5f658-152">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="5f658-152">Parent Elements</span></span>  
  
|<span data-ttu-id="5f658-153">Elemento</span><span class="sxs-lookup"><span data-stu-id="5f658-153">Element</span></span>|<span data-ttu-id="5f658-154">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5f658-154">Description</span></span>|  
|-------------|-----------------|  
|[\<serviceCertificate>](servicecertificate-of-clientcredentials-element.md)|<span data-ttu-id="5f658-155">Specifica un certificato da usare per l'autenticazione di un servizio presso il client.</span><span class="sxs-lookup"><span data-stu-id="5f658-155">Specifies a certificate to use when authenticating a service to the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5f658-156">Commenti</span><span class="sxs-lookup"><span data-stu-id="5f658-156">Remarks</span></span>  
 <span data-ttu-id="5f658-157">L'attributo `certificateValidationMode` di questo elemento di configurazione specifica il livello di attendibilità usato per autenticare i certificati.</span><span class="sxs-lookup"><span data-stu-id="5f658-157">The `certificateValidationMode` attribute of this configuration element specifies the level of trust used to authenticate certificates.</span></span> <span data-ttu-id="5f658-158">Per impostazione predefinita, il livello è impostato su `ChainTrust`. Tale impostazione prevede che ogni certificato appartenga a una gerarchia di certificati che termina in un'autorità di certificazione attendibile situata all'inizio della catena.</span><span class="sxs-lookup"><span data-stu-id="5f658-158">By default, the level is set to `ChainTrust`, which specifies that each certificate must be found in a hierarchy of certificates ending in a trusted certification authority at the top of the chain.</span></span> <span data-ttu-id="5f658-159">Si tratta della modalità più protetta.</span><span class="sxs-lookup"><span data-stu-id="5f658-159">This is the most secure mode.</span></span> <span data-ttu-id="5f658-160">Il livello può inoltre essere impostato su `PeerOrChainTrust`, a indicare che sia i certificati autocertificati (trust peer) sia i certificati appartenenti a una catena di trust sono ritenuti attendibili.</span><span class="sxs-lookup"><span data-stu-id="5f658-160">You can also set the value to `PeerOrChainTrust`, which specifies that self-issued certificates (peer trust) are accepted as well as certificates that are in a trusted chain.</span></span> <span data-ttu-id="5f658-161">Poiché i certificati autocertificati non devono essere acquistati da un'autorità attendibile, questo livello viene usato in fase di sviluppo e di debug dei client e dei servizi.</span><span class="sxs-lookup"><span data-stu-id="5f658-161">This value is used when developing and debugging clients and services because self-issued certificates need not be purchased from a trusted authority.</span></span> <span data-ttu-id="5f658-162">Quando si distribuisce un client è invece opportuno usare il livello `ChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="5f658-162">When deploying a client, use the `ChainTrust` value instead.</span></span> <span data-ttu-id="5f658-163">È inoltre possibile impostare il valore su `Custom` o `None`.</span><span class="sxs-lookup"><span data-stu-id="5f658-163">You can also set the value to `Custom` or `None`.</span></span> <span data-ttu-id="5f658-164">Per usare il valore `Custom` è necessario impostare anche l'attributo `customCertificateValidator` sull'assembly e sul tipo usati per convalidare il certificato.</span><span class="sxs-lookup"><span data-stu-id="5f658-164">To use the `Custom` value, you must also set the `customCertificateValidator` attribute to an assembly and type used to validate the certificate.</span></span> <span data-ttu-id="5f658-165">Per creare una convalida personalizzata, è necessario ereditare una classe dalla classe X509CertificateValidator astratta.</span><span class="sxs-lookup"><span data-stu-id="5f658-165">To create your own custom validator, you must inherit from the abstract X509CertificateValidator class.</span></span> <span data-ttu-id="5f658-166">Per altre informazioni, vedere [procedura: creare un servizio che usa un validator del certificato personalizzato](../../../wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md).</span><span class="sxs-lookup"><span data-stu-id="5f658-166">For more information, see [How to: Create a Service that Employs a Custom Certificate Validator](../../../wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md).</span></span>  
  
 <span data-ttu-id="5f658-167">L'attributo `revocationMode` specifica il modo in cui i certificati vengono contrassegnati per la revoca.</span><span class="sxs-lookup"><span data-stu-id="5f658-167">The `revocationMode` attribute specifies how certificates are checked for revocation.</span></span> <span data-ttu-id="5f658-168">L'impostazione predefinita è `online` a indicare che i certificati vengono contrassegnati automaticamente per la revoca.</span><span class="sxs-lookup"><span data-stu-id="5f658-168">The default is `online` which indicates that certificates will be checked automatically for revocation.</span></span> <span data-ttu-id="5f658-169">Per ulteriori informazioni, vedere [utilizzo dei certificati](../../../wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="5f658-169">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5f658-170">Esempio</span><span class="sxs-lookup"><span data-stu-id="5f658-170">Example</span></span>  
 <span data-ttu-id="5f658-171">Nell'esempio vengono svolte due attività:</span><span class="sxs-lookup"><span data-stu-id="5f658-171">The following example does two tasks.</span></span> <span data-ttu-id="5f658-172">Per prima cosa specifica un certificato di servizio che il client deve usare durante la comunicazione con gli endpoint il cui nome di dominio è `www.contoso.com` sul protocollo http.</span><span class="sxs-lookup"><span data-stu-id="5f658-172">It first specifies a service certificate for the client to use when communicating with endpoints whose domain name is `www.contoso.com` over the HTTP protocol.</span></span> <span data-ttu-id="5f658-173">In secondo luogo, specifica la modalità di revoca e il percorso dell'archivio usati durante l'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="5f658-173">Second, it specifies the revocation mode and store location used during authentication.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="5f658-174">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="5f658-174">See also</span></span>

- <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.Authentication%2A>
- <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication>
- [<span data-ttu-id="5f658-175">Comportamenti di sicurezza</span><span class="sxs-lookup"><span data-stu-id="5f658-175">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="5f658-176">Working with Certificates</span><span class="sxs-lookup"><span data-stu-id="5f658-176">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="5f658-177">Procedura: creare un servizio che usa un validator del certificato personalizzato</span><span class="sxs-lookup"><span data-stu-id="5f658-177">How to: Create a Service that Employs a Custom Certificate Validator</span></span>](../../../wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md)
- [\<authentication>](authentication-of-clientcertificate-element.md)
- [<span data-ttu-id="5f658-178">Protezione di client</span><span class="sxs-lookup"><span data-stu-id="5f658-178">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="5f658-179">Securing Services and Clients</span><span class="sxs-lookup"><span data-stu-id="5f658-179">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)

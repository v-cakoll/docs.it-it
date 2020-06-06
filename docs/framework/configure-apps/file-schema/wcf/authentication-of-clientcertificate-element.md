---
title: <authentication>dell' <clientCertificate> elemento
ms.date: 03/30/2017
ms.assetid: 4a55eea2-1826-4026-b911-b7cc9e9c8bfe
ms.openlocfilehash: 99084f6b7afbdd8586ee706cd6ec44b349d81ff2
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70398260"
---
# <a name="authentication-of-clientcertificate-element"></a><span data-ttu-id="bd22f-102">\<authentication>dell' \<clientCertificate> elemento</span><span class="sxs-lookup"><span data-stu-id="bd22f-102">\<authentication> of \<clientCertificate> Element</span></span>
<span data-ttu-id="bd22f-103">Specifica i comportamenti di autenticazione per i certificati client utilizzati da un servizio.</span><span class="sxs-lookup"><span data-stu-id="bd22f-103">Specifies authentication behaviors for client certificates used by a service.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCertificate>**](clientcertificate-of-servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<authentication>**  
  
## <a name="syntax"></a><span data-ttu-id="bd22f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bd22f-104">Syntax</span></span>  
  
```xml  
<authentication customCertificateValidatorType="namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"
                certificateValidationMode="ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"
                includeWindowsGroups="Boolean"
                mapClientCertificateToWindowsAccount="Boolean"
                revocationMode="NoCheck/Online/Offline"
                trustedStoreLocation="CurrentUser/LocalMachine" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bd22f-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="bd22f-105">Attributes and Elements</span></span>  
 <span data-ttu-id="bd22f-106">Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.</span><span class="sxs-lookup"><span data-stu-id="bd22f-106">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bd22f-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="bd22f-107">Attributes</span></span>  
  
|<span data-ttu-id="bd22f-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="bd22f-108">Attribute</span></span>|<span data-ttu-id="bd22f-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bd22f-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="bd22f-110">customCertificateValidatorType</span><span class="sxs-lookup"><span data-stu-id="bd22f-110">customCertificateValidatorType</span></span>|<span data-ttu-id="bd22f-111">Stringa facoltativa.</span><span class="sxs-lookup"><span data-stu-id="bd22f-111">Optional string.</span></span> <span data-ttu-id="bd22f-112">Un tipo e un assembly usati per convalidare un tipo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="bd22f-112">A type and assembly used to validate a custom type.</span></span> <span data-ttu-id="bd22f-113">Questo attributo deve essere impostato quando `certificateValidationMode` è impostato su `Custom`.</span><span class="sxs-lookup"><span data-stu-id="bd22f-113">This attribute must be set when `certificateValidationMode` is set to `Custom`.</span></span>|  
|<span data-ttu-id="bd22f-114">certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="bd22f-114">certificateValidationMode</span></span>|<span data-ttu-id="bd22f-115">Enumerazione facoltativa.</span><span class="sxs-lookup"><span data-stu-id="bd22f-115">Optional enumeration.</span></span> <span data-ttu-id="bd22f-116">Specifica una delle modalità usate per convalidare credenziali.</span><span class="sxs-lookup"><span data-stu-id="bd22f-116">Specifies one of the modes used to validate credentials.</span></span> <span data-ttu-id="bd22f-117">L'attributo è di tipo <xref:System.ServiceModel.Security.X509CertificateValidationMode>.</span><span class="sxs-lookup"><span data-stu-id="bd22f-117">This attribute is of the <xref:System.ServiceModel.Security.X509CertificateValidationMode> type.</span></span> <span data-ttu-id="bd22f-118">Se impostato su <xref:System.ServiceModel.Security.X509CertificateValidationMode.Custom?displayProperty=nameWithType>, è necessario fornire anche un `customCertificateValidator`.</span><span class="sxs-lookup"><span data-stu-id="bd22f-118">If set to <xref:System.ServiceModel.Security.X509CertificateValidationMode.Custom?displayProperty=nameWithType>, then a `customCertificateValidator` must also be supplied.</span></span> <span data-ttu-id="bd22f-119">Il valore predefinito è <xref:System.ServiceModel.Security.X509CertificateValidationMode.ChainTrust?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="bd22f-119">The default is <xref:System.ServiceModel.Security.X509CertificateValidationMode.ChainTrust?displayProperty=nameWithType>.</span></span>|  
|<span data-ttu-id="bd22f-120">includeWindowsGroups</span><span class="sxs-lookup"><span data-stu-id="bd22f-120">includeWindowsGroups</span></span>|<span data-ttu-id="bd22f-121">Valore booleano facoltativo.</span><span class="sxs-lookup"><span data-stu-id="bd22f-121">Optional Boolean.</span></span> <span data-ttu-id="bd22f-122">Specifica se i gruppi di Windows sono inclusi nel contesto di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="bd22f-122">Specifies if Windows groups are included in the security context.</span></span> <span data-ttu-id="bd22f-123">L'impostazione di questo attributo su `true` determina un effetto sulle prestazioni in quanto comporta un'espansione completa del gruppo.</span><span class="sxs-lookup"><span data-stu-id="bd22f-123">Setting this attribute to `true` has a performance impact, as it results in a full group expansion.</span></span> <span data-ttu-id="bd22f-124">Impostare questo attributo su `false` se non è necessario stabilire l'elenco di gruppi a cui appartiene un utente.</span><span class="sxs-lookup"><span data-stu-id="bd22f-124">Set this attribute to `false` if you do not need to establish the list of groups a user belongs to.</span></span>|  
|<span data-ttu-id="bd22f-125">mapClientCertificateToWindowsAccount</span><span class="sxs-lookup"><span data-stu-id="bd22f-125">mapClientCertificateToWindowsAccount</span></span>|<span data-ttu-id="bd22f-126">Proprietà di tipo Boolean.</span><span class="sxs-lookup"><span data-stu-id="bd22f-126">Boolean.</span></span> <span data-ttu-id="bd22f-127">Specifica se è possibile eseguire il mapping del client a un'identità di Windows usando il certificato.</span><span class="sxs-lookup"><span data-stu-id="bd22f-127">Specifies whether the client can be mapped to a Windows identity using the certificate.</span></span> <span data-ttu-id="bd22f-128">A tal scopo è necessario che Active Directory sia attivato.</span><span class="sxs-lookup"><span data-stu-id="bd22f-128">Active Directory must be enabled to do this.</span></span>|  
|<span data-ttu-id="bd22f-129">revocationMode</span><span class="sxs-lookup"><span data-stu-id="bd22f-129">revocationMode</span></span>|<span data-ttu-id="bd22f-130">Enumerazione facoltativa.</span><span class="sxs-lookup"><span data-stu-id="bd22f-130">Optional enumeration.</span></span> <span data-ttu-id="bd22f-131">Una delle modalità usate per verificare un elenco dei certificati revocati.</span><span class="sxs-lookup"><span data-stu-id="bd22f-131">One of the modes used to check for a revoked certificate lists (RCL).</span></span> <span data-ttu-id="bd22f-132">Il valore predefinito è `Online`.</span><span class="sxs-lookup"><span data-stu-id="bd22f-132">The default is `Online`.</span></span> <span data-ttu-id="bd22f-133">Questo valore viene ignorato quando si usa la sicurezza del trasporto HTTP.</span><span class="sxs-lookup"><span data-stu-id="bd22f-133">This value is ignored when using HTTP transport security.</span></span>|  
|<span data-ttu-id="bd22f-134">trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="bd22f-134">trustedStoreLocation</span></span>|<span data-ttu-id="bd22f-135">Enumerazione facoltativa.</span><span class="sxs-lookup"><span data-stu-id="bd22f-135">Optional enumeration.</span></span> <span data-ttu-id="bd22f-136">Uno di due percorsi dell'archivio di sistema: `LocalMachine` o `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="bd22f-136">One of the two system store locations: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="bd22f-137">Questo valore viene usato quando viene negoziato un certificato del servizio con il client.</span><span class="sxs-lookup"><span data-stu-id="bd22f-137">This value is used when a service certificate is negotiated to the client.</span></span> <span data-ttu-id="bd22f-138">La convalida viene eseguita sull'archivio **persone attendibili** nel percorso di archiviazione specificato.</span><span class="sxs-lookup"><span data-stu-id="bd22f-138">Validation is performed against the **Trusted People** store in the specified store location.</span></span> <span data-ttu-id="bd22f-139">Il valore predefinito è `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="bd22f-139">The default is `CurrentUser`.</span></span>|  
  
## <a name="customcertificatevalidatortype-attribute"></a><span data-ttu-id="bd22f-140">Attributo customCertificateValidatorType</span><span class="sxs-lookup"><span data-stu-id="bd22f-140">customCertificateValidatorType Attribute</span></span>  
  
|<span data-ttu-id="bd22f-141">Valore</span><span class="sxs-lookup"><span data-stu-id="bd22f-141">Value</span></span>|<span data-ttu-id="bd22f-142">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bd22f-142">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="bd22f-143">string</span><span class="sxs-lookup"><span data-stu-id="bd22f-143">String</span></span>|<span data-ttu-id="bd22f-144">Specifica il nome e l'assembly del tipo e altri dati usati per trovare il tipo.</span><span class="sxs-lookup"><span data-stu-id="bd22f-144">Specifies the type name and assembly and other data used to find the type.</span></span>|  
  
## <a name="certificatevalidationmode-attribute"></a><span data-ttu-id="bd22f-145">Attributo certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="bd22f-145">certificateValidationMode Attribute</span></span>  
  
|<span data-ttu-id="bd22f-146">Valore</span><span class="sxs-lookup"><span data-stu-id="bd22f-146">Value</span></span>|<span data-ttu-id="bd22f-147">Description</span><span class="sxs-lookup"><span data-stu-id="bd22f-147">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="bd22f-148">Enumerazione</span><span class="sxs-lookup"><span data-stu-id="bd22f-148">Enumeration</span></span>|<span data-ttu-id="bd22f-149">Uno dei valori seguenti: None, PeerTrust, ChainTrust, PeerOrChainTrust, Custom.</span><span class="sxs-lookup"><span data-stu-id="bd22f-149">One of the following values: None, PeerTrust, ChainTrust, PeerOrChainTrust, Custom.</span></span><br /><br /> <span data-ttu-id="bd22f-150">Per ulteriori informazioni, vedere [utilizzo dei certificati](../../../wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="bd22f-150">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="revocationmode-attribute"></a><span data-ttu-id="bd22f-151">Attributo revocationMode</span><span class="sxs-lookup"><span data-stu-id="bd22f-151">revocationMode Attribute</span></span>  
  
|<span data-ttu-id="bd22f-152">Valore</span><span class="sxs-lookup"><span data-stu-id="bd22f-152">Value</span></span>|<span data-ttu-id="bd22f-153">Description</span><span class="sxs-lookup"><span data-stu-id="bd22f-153">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="bd22f-154">Enumerazione</span><span class="sxs-lookup"><span data-stu-id="bd22f-154">Enumeration</span></span>|<span data-ttu-id="bd22f-155">Uno dei valori seguenti: NoCheck, Online, Offline.</span><span class="sxs-lookup"><span data-stu-id="bd22f-155">One of the following values: NoCheck, Online, Offline.</span></span> <span data-ttu-id="bd22f-156">Per ulteriori informazioni, vedere [utilizzo dei certificati](../../../wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="bd22f-156">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="trustedstorelocation-attribute"></a><span data-ttu-id="bd22f-157">Attributo trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="bd22f-157">trustedStoreLocation Attribute</span></span>  
  
|<span data-ttu-id="bd22f-158">Valore</span><span class="sxs-lookup"><span data-stu-id="bd22f-158">Value</span></span>|<span data-ttu-id="bd22f-159">Description</span><span class="sxs-lookup"><span data-stu-id="bd22f-159">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="bd22f-160">Enumerazione</span><span class="sxs-lookup"><span data-stu-id="bd22f-160">Enumeration</span></span>|<span data-ttu-id="bd22f-161">Uno dei valori seguenti: `LocalMachine` o `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="bd22f-161">One of the following values: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="bd22f-162">Il valore predefinito è `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="bd22f-162">The default is `CurrentUser`.</span></span> <span data-ttu-id="bd22f-163">Se l'applicazione client viene eseguita con un account di sistema, il certificato è generalmente situato in `LocalMachine`.</span><span class="sxs-lookup"><span data-stu-id="bd22f-163">If the client application is running under a system account then the certificate is typically under `LocalMachine`.</span></span> <span data-ttu-id="bd22f-164">Se l'applicazione client viene eseguita con un account utente, il certificato è generalmente situato in `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="bd22f-164">If the client application is running under a user account then the certificate is typically in `CurrentUser`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bd22f-165">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="bd22f-165">Child Elements</span></span>  
 <span data-ttu-id="bd22f-166">No.</span><span class="sxs-lookup"><span data-stu-id="bd22f-166">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="bd22f-167">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="bd22f-167">Parent Elements</span></span>  
  
|<span data-ttu-id="bd22f-168">Elemento</span><span class="sxs-lookup"><span data-stu-id="bd22f-168">Element</span></span>|<span data-ttu-id="bd22f-169">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bd22f-169">Description</span></span>|  
|-------------|-----------------|  
|[\<clientCertificate>](clientcertificate-of-servicecredentials.md)|<span data-ttu-id="bd22f-170">Definisce un certificato X.509 utilizzato dal client per autenticare un servizio.</span><span class="sxs-lookup"><span data-stu-id="bd22f-170">Defines an X.509 certificate used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bd22f-171">Commenti</span><span class="sxs-lookup"><span data-stu-id="bd22f-171">Remarks</span></span>  
 <span data-ttu-id="bd22f-172">L'elemento `<authentication>` corrisponde alla classe <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication>.</span><span class="sxs-lookup"><span data-stu-id="bd22f-172">The `<authentication>` element corresponds to the <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication> class.</span></span> <span data-ttu-id="bd22f-173">Consente di personalizzare la modalità di autenticazione dei client.</span><span class="sxs-lookup"><span data-stu-id="bd22f-173">It enables you to customize how clients are authenticated.</span></span> <span data-ttu-id="bd22f-174">A tale scopo, l'attributo `certificateValidationMode` può essere impostato su `None`, `ChainTrust`, `PeerOrChainTrust`, `PeerTrust` o `Custom`.</span><span class="sxs-lookup"><span data-stu-id="bd22f-174">You can set the `certificateValidationMode` attribute to `None`, `ChainTrust`, `PeerOrChainTrust`, `PeerTrust`, or `Custom`.</span></span> <span data-ttu-id="bd22f-175">Per impostazione predefinita, il livello è impostato su `ChainTrust` , che specifica che ogni certificato deve trovarsi in una gerarchia di certificati che terminano con un' *autorità radice* nella parte superiore della catena.</span><span class="sxs-lookup"><span data-stu-id="bd22f-175">By default, the level is set to `ChainTrust`, which specifies that each certificate must be found in a hierarchy of certificates ending in a *root authority* at the top of the chain.</span></span> <span data-ttu-id="bd22f-176">Si tratta della modalità più protetta.</span><span class="sxs-lookup"><span data-stu-id="bd22f-176">This is the most secure mode.</span></span> <span data-ttu-id="bd22f-177">Il livello può inoltre essere impostato su `PeerOrChainTrust`, a indicare che sia i certificati autocertificati (trust peer) sia i certificati appartenenti a una catena di trust sono ritenuti attendibili.</span><span class="sxs-lookup"><span data-stu-id="bd22f-177">You can also set the value to `PeerOrChainTrust`, which specifies that self-issued certificates (peer trust) are accepted as well as certificates that are in a trusted chain.</span></span> <span data-ttu-id="bd22f-178">Poiché i certificati autocertificati non devono essere acquistati da un'autorità attendibile, questo livello viene usato in fase di sviluppo e di debug dei client e dei servizi.</span><span class="sxs-lookup"><span data-stu-id="bd22f-178">This value is used when developing and debugging clients and services because self-issued certificates need not be purchased from a trusted authority.</span></span> <span data-ttu-id="bd22f-179">Quando si distribuisce un client è invece opportuno usare il livello `ChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="bd22f-179">When deploying a client, use the `ChainTrust` value instead.</span></span>  
  
 <span data-ttu-id="bd22f-180">Un altro livello disponibile è `Custom`.</span><span class="sxs-lookup"><span data-stu-id="bd22f-180">You can also set the value to `Custom`.</span></span> <span data-ttu-id="bd22f-181">Quando si imposta il livello `Custom` è necessario impostare anche l'attributo `customCertificateValidatorType` sull'assembly e sul tipo usati per convalidare il certificato.</span><span class="sxs-lookup"><span data-stu-id="bd22f-181">When set to the `Custom` value, you must also set the `customCertificateValidatorType` attribute to an assembly and type used to validate the certificate.</span></span> <span data-ttu-id="bd22f-182">Per creare un validator personalizzato è necessario ereditare una classe dalla classe astratta <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span><span class="sxs-lookup"><span data-stu-id="bd22f-182">To create your own custom validator, you must inherit from the abstract <xref:System.IdentityModel.Selectors.X509CertificateValidator> class.</span></span> <span data-ttu-id="bd22f-183">Per altre informazioni, vedere [procedura: creare un servizio che usa un validator del certificato personalizzato](../../../wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md).</span><span class="sxs-lookup"><span data-stu-id="bd22f-183">For more information, see [How to: Create a Service that Employs a Custom Certificate Validator](../../../wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="bd22f-184">Esempio</span><span class="sxs-lookup"><span data-stu-id="bd22f-184">Example</span></span>  
 <span data-ttu-id="bd22f-185">Nel codice seguente sono specificati un certificato X.509 e un tipo di convalida personalizzato nell'elemento `<authentication>`.</span><span class="sxs-lookup"><span data-stu-id="bd22f-185">The following code specifies an X.509 certificate and a custom validation type in the `<authentication>` element.</span></span>  
  
```xml  
<serviceBehaviors>
  <behavior name="myServiceBehavior">
    <clientCertificate>
      <certificate findValue="www.cohowinery.com"
                   storeLocation="CurrentUser"
                   storeName="TrustedPeople"
                   x509FindType="FindByIssuerName" />
      <authentication customCertificateValidatorType="MyTypes.Coho"
                      certificateValidationMode="Custom"
                      revocationMode="Offline"
                      includeWindowsGroups="false"
                      mapClientCertificateToWindowsAccount="true" />
    </clientCertificate>
  </behavior>
</serviceBehaviors>
```  
  
## <a name="see-also"></a><span data-ttu-id="bd22f-186">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="bd22f-186">See also</span></span>

- <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication>
- <xref:System.ServiceModel.Security.X509CertificateValidationMode>
- <xref:System.ServiceModel.Security.X509CertificateInitiatorServiceCredential.Authentication%2A>
- <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement.Authentication%2A>
- <xref:System.ServiceModel.Configuration.X509ClientCertificateAuthenticationElement>
- [<span data-ttu-id="bd22f-187">Comportamenti di sicurezza</span><span class="sxs-lookup"><span data-stu-id="bd22f-187">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="bd22f-188">Procedura: creare un servizio che usa un validator del certificato personalizzato</span><span class="sxs-lookup"><span data-stu-id="bd22f-188">How to: Create a Service that Employs a Custom Certificate Validator</span></span>](../../../wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md)
- [<span data-ttu-id="bd22f-189">Working with Certificates</span><span class="sxs-lookup"><span data-stu-id="bd22f-189">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)

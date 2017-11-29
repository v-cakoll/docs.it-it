---
title: Elemento &lt;authentication&gt; di &lt;clientCertificate&gt;
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4a55eea2-1826-4026-b911-b7cc9e9c8bfe
caps.latest.revision: "16"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 4eb125727d68d1618b32d21612ecfac28eaa5b6b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ltauthenticationgt-of-ltclientcertificategt-element"></a><span data-ttu-id="de8ea-102">Elemento &lt;authentication&gt; di &lt;clientCertificate&gt;</span><span class="sxs-lookup"><span data-stu-id="de8ea-102">&lt;authentication&gt; of &lt;clientCertificate&gt; Element</span></span>
<span data-ttu-id="de8ea-103">Specifica i comportamenti di autenticazione per i certificati client utilizzati da un servizio.</span><span class="sxs-lookup"><span data-stu-id="de8ea-103">Specifies authentication behaviors for client certificates used by a service.</span></span>  
  
 <span data-ttu-id="de8ea-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="de8ea-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="de8ea-105">\<i comportamenti ></span><span class="sxs-lookup"><span data-stu-id="de8ea-105">\<behaviors></span></span>  
<span data-ttu-id="de8ea-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="de8ea-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="de8ea-107">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="de8ea-107">\<behavior></span></span>  
<span data-ttu-id="de8ea-108">\<serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="de8ea-108">\<serviceCredentials></span></span>  
<span data-ttu-id="de8ea-109">\<clientCertificate ></span><span class="sxs-lookup"><span data-stu-id="de8ea-109">\<clientCertificate></span></span>  
<span data-ttu-id="de8ea-110">\<autenticazione ></span><span class="sxs-lookup"><span data-stu-id="de8ea-110">\<authentication></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="de8ea-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="de8ea-111">Syntax</span></span>  
  
```xml  
<authentication  
customCertificateValidatorType="namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"  
certificateValidationMode="ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"  
includeWindowsGroups="Boolean"  
mapClientCertificateToWindowsAccount="Boolean"  
revocationMode="NoCheck/Online/Offline"  
trustedStoreLocation="CurrentUser/LocalMachine"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="de8ea-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="de8ea-112">Attributes and Elements</span></span>  
 <span data-ttu-id="de8ea-113">Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.</span><span class="sxs-lookup"><span data-stu-id="de8ea-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="de8ea-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="de8ea-114">Attributes</span></span>  
  
|<span data-ttu-id="de8ea-115">Attributo</span><span class="sxs-lookup"><span data-stu-id="de8ea-115">Attribute</span></span>|<span data-ttu-id="de8ea-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="de8ea-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="de8ea-117">customCertificateValidatorType</span><span class="sxs-lookup"><span data-stu-id="de8ea-117">customCertificateValidatorType</span></span>|<span data-ttu-id="de8ea-118">Stringa facoltativa.</span><span class="sxs-lookup"><span data-stu-id="de8ea-118">Optional string.</span></span> <span data-ttu-id="de8ea-119">Un tipo e un assembly usati per convalidare un tipo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="de8ea-119">A type and assembly used to validate a custom type.</span></span> <span data-ttu-id="de8ea-120">Questo attributo deve essere impostato quando `certificateValidationMode` è impostato su `Custom`.</span><span class="sxs-lookup"><span data-stu-id="de8ea-120">This attribute must be set when `certificateValidationMode` is set to `Custom`.</span></span>|  
|<span data-ttu-id="de8ea-121">certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="de8ea-121">certificateValidationMode</span></span>|<span data-ttu-id="de8ea-122">Enumerazione facoltativa.</span><span class="sxs-lookup"><span data-stu-id="de8ea-122">Optional enumeration.</span></span> <span data-ttu-id="de8ea-123">Specifica una delle modalità usate per convalidare credenziali.</span><span class="sxs-lookup"><span data-stu-id="de8ea-123">Specifies one of the modes used to validate credentials.</span></span> <span data-ttu-id="de8ea-124">L'attributo è di tipo <xref:System.ServiceModel.Security.X509CertificateValidationMode>.</span><span class="sxs-lookup"><span data-stu-id="de8ea-124">This attribute is of the <xref:System.ServiceModel.Security.X509CertificateValidationMode> type.</span></span> <span data-ttu-id="de8ea-125">Se impostato su <xref:System.ServiceModel.Security.X509CertificateValidationMode.Custom?displayProperty=nameWithType>, è necessario fornire anche un `customCertificateValidator`.</span><span class="sxs-lookup"><span data-stu-id="de8ea-125">If set to <xref:System.ServiceModel.Security.X509CertificateValidationMode.Custom?displayProperty=nameWithType>, then a `customCertificateValidator` must also be supplied.</span></span> <span data-ttu-id="de8ea-126">Il valore predefinito è <xref:System.ServiceModel.Security.X509CertificateValidationMode.ChainTrust?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="de8ea-126">The default is <xref:System.ServiceModel.Security.X509CertificateValidationMode.ChainTrust?displayProperty=nameWithType>.</span></span>|  
|<span data-ttu-id="de8ea-127">includeWindowsGroups</span><span class="sxs-lookup"><span data-stu-id="de8ea-127">includeWindowsGroups</span></span>|<span data-ttu-id="de8ea-128">Valore booleano facoltativo.</span><span class="sxs-lookup"><span data-stu-id="de8ea-128">Optional Boolean.</span></span> <span data-ttu-id="de8ea-129">Specifica se i gruppi di Windows sono inclusi nel contesto di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="de8ea-129">Specifies if Windows groups are included in the security context.</span></span> <span data-ttu-id="de8ea-130">L'impostazione di questo attributo su `true` determina un effetto sulle prestazioni in quanto comporta un'espansione completa del gruppo.</span><span class="sxs-lookup"><span data-stu-id="de8ea-130">Setting this attribute to `true` has a performance impact, as it results in a full group expansion.</span></span> <span data-ttu-id="de8ea-131">Impostare questo attributo su `false` se non è necessario stabilire l'elenco di gruppi a cui appartiene un utente.</span><span class="sxs-lookup"><span data-stu-id="de8ea-131">Set this attribute to `false` if you do not need to establish the list of groups a user belongs to.</span></span>|  
|<span data-ttu-id="de8ea-132">mapClientCertificateToWindowsAcccount</span><span class="sxs-lookup"><span data-stu-id="de8ea-132">mapClientCertificateToWindowsAcccount</span></span>|<span data-ttu-id="de8ea-133">Proprietà di tipo Boolean.</span><span class="sxs-lookup"><span data-stu-id="de8ea-133">Boolean.</span></span> <span data-ttu-id="de8ea-134">Specifica se è possibile eseguire il mapping del client a un'identità di Windows usando il certificato.</span><span class="sxs-lookup"><span data-stu-id="de8ea-134">Specifies whether the client can be mapped to a Windows identity using the certificate.</span></span> <span data-ttu-id="de8ea-135">A tal scopo è necessario che Active Directory sia attivato.</span><span class="sxs-lookup"><span data-stu-id="de8ea-135">Active Directory must be enabled to do this.</span></span>|  
|<span data-ttu-id="de8ea-136">revocationMode</span><span class="sxs-lookup"><span data-stu-id="de8ea-136">revocationMode</span></span>|<span data-ttu-id="de8ea-137">Enumerazione facoltativa.</span><span class="sxs-lookup"><span data-stu-id="de8ea-137">Optional enumeration.</span></span> <span data-ttu-id="de8ea-138">Una delle modalità usate per verificare un elenco dei certificati revocati.</span><span class="sxs-lookup"><span data-stu-id="de8ea-138">One of the modes used to check for a revoked certificate lists (RCL).</span></span> <span data-ttu-id="de8ea-139">Il valore predefinito è `Online`.</span><span class="sxs-lookup"><span data-stu-id="de8ea-139">The default is `Online`.</span></span> <span data-ttu-id="de8ea-140">Questo valore viene ignorato quando si usa la sicurezza del trasporto HTTP.</span><span class="sxs-lookup"><span data-stu-id="de8ea-140">This value is ignored when using HTTP transport security.</span></span>|  
|<span data-ttu-id="de8ea-141">trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="de8ea-141">trustedStoreLocation</span></span>|<span data-ttu-id="de8ea-142">Enumerazione facoltativa.</span><span class="sxs-lookup"><span data-stu-id="de8ea-142">Optional enumeration.</span></span> <span data-ttu-id="de8ea-143">Uno di due percorsi dell'archivio di sistema: `LocalMachine` o `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="de8ea-143">One of the two system store locations: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="de8ea-144">Questo valore viene usato quando viene negoziato un certificato del servizio con il client.</span><span class="sxs-lookup"><span data-stu-id="de8ea-144">This value is used when a service certificate is negotiated to the client.</span></span> <span data-ttu-id="de8ea-145">La convalida viene eseguita su di **persone attendibili** archiviare nel percorso dell'archivio specificato.</span><span class="sxs-lookup"><span data-stu-id="de8ea-145">Validation is performed against the **Trusted People** store in the specified store location.</span></span> <span data-ttu-id="de8ea-146">Il valore predefinito è `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="de8ea-146">The default is `CurrentUser`.</span></span>|  
  
## <a name="customcertificatevalidatortype-attribute"></a><span data-ttu-id="de8ea-147">Attributo customCertificateValidatorType</span><span class="sxs-lookup"><span data-stu-id="de8ea-147">customCertificateValidatorType Attribute</span></span>  
  
|<span data-ttu-id="de8ea-148">Valore</span><span class="sxs-lookup"><span data-stu-id="de8ea-148">Value</span></span>|<span data-ttu-id="de8ea-149">Descrizione</span><span class="sxs-lookup"><span data-stu-id="de8ea-149">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="de8ea-150">String</span><span class="sxs-lookup"><span data-stu-id="de8ea-150">String</span></span>|<span data-ttu-id="de8ea-151">Specifica il nome e l'assembly del tipo e altri dati usati per trovare il tipo.</span><span class="sxs-lookup"><span data-stu-id="de8ea-151">Specifies the type name and assembly and other data used to find the type.</span></span>|  
  
## <a name="certificatevalidationmode-attribute"></a><span data-ttu-id="de8ea-152">Attributo certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="de8ea-152">certificateValidationMode Attribute</span></span>  
  
|<span data-ttu-id="de8ea-153">Valore</span><span class="sxs-lookup"><span data-stu-id="de8ea-153">Value</span></span>|<span data-ttu-id="de8ea-154">Descrizione</span><span class="sxs-lookup"><span data-stu-id="de8ea-154">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="de8ea-155">Enumerazione</span><span class="sxs-lookup"><span data-stu-id="de8ea-155">Enumeration</span></span>|<span data-ttu-id="de8ea-156">Uno dei valori seguenti: None, PeerTrust, ChainTrust, PeerOrChainTrust, Custom.</span><span class="sxs-lookup"><span data-stu-id="de8ea-156">One of the following values: None, PeerTrust, ChainTrust, PeerOrChainTrust, Custom.</span></span><br /><br /> <span data-ttu-id="de8ea-157">Per ulteriori informazioni, vedere [utilizzo dei certificati](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="de8ea-157">For more information, see [Working with Certificates](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="revocationmode-attribute"></a><span data-ttu-id="de8ea-158">Attributo revocationMode</span><span class="sxs-lookup"><span data-stu-id="de8ea-158">revocationMode Attribute</span></span>  
  
|<span data-ttu-id="de8ea-159">Valore</span><span class="sxs-lookup"><span data-stu-id="de8ea-159">Value</span></span>|<span data-ttu-id="de8ea-160">Descrizione</span><span class="sxs-lookup"><span data-stu-id="de8ea-160">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="de8ea-161">Enumerazione</span><span class="sxs-lookup"><span data-stu-id="de8ea-161">Enumeration</span></span>|<span data-ttu-id="de8ea-162">Uno dei valori seguenti: NoCheck, Online, Offline.</span><span class="sxs-lookup"><span data-stu-id="de8ea-162">One of the following values: NoCheck, Online, Offline.</span></span> <span data-ttu-id="de8ea-163">Per ulteriori informazioni, vedere [utilizzo dei certificati](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="de8ea-163">For more information, see [Working with Certificates](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="trustedstorelocation-attribute"></a><span data-ttu-id="de8ea-164">Attributo trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="de8ea-164">trustedStoreLocation Attribute</span></span>  
  
|<span data-ttu-id="de8ea-165">Valore</span><span class="sxs-lookup"><span data-stu-id="de8ea-165">Value</span></span>|<span data-ttu-id="de8ea-166">Descrizione</span><span class="sxs-lookup"><span data-stu-id="de8ea-166">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="de8ea-167">Enumerazione</span><span class="sxs-lookup"><span data-stu-id="de8ea-167">Enumeration</span></span>|<span data-ttu-id="de8ea-168">Uno dei valori seguenti: `LocalMachine` o `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="de8ea-168">One of the following values: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="de8ea-169">Il valore predefinito è `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="de8ea-169">The default is `CurrentUser`.</span></span> <span data-ttu-id="de8ea-170">Se l'applicazione client viene eseguita con un account di sistema, il certificato è generalmente situato in `LocalMachine`.</span><span class="sxs-lookup"><span data-stu-id="de8ea-170">If the client application is running under a system account then the certificate is typically under `LocalMachine`.</span></span> <span data-ttu-id="de8ea-171">Se l'applicazione client viene eseguita con un account utente, il certificato è generalmente situato in `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="de8ea-171">If the client application is running under a user account then the certificate is typically in `CurrentUser`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="de8ea-172">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="de8ea-172">Child Elements</span></span>  
 <span data-ttu-id="de8ea-173">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="de8ea-173">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="de8ea-174">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="de8ea-174">Parent Elements</span></span>  
  
|<span data-ttu-id="de8ea-175">Elemento</span><span class="sxs-lookup"><span data-stu-id="de8ea-175">Element</span></span>|<span data-ttu-id="de8ea-176">Descrizione</span><span class="sxs-lookup"><span data-stu-id="de8ea-176">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="de8ea-177">\<clientCertificate ></span><span class="sxs-lookup"><span data-stu-id="de8ea-177">\<clientCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-servicecredentials.md)|<span data-ttu-id="de8ea-178">Definisce un certificato X.509 utilizzato dal client per autenticare un servizio.</span><span class="sxs-lookup"><span data-stu-id="de8ea-178">Defines an X.509 certificate used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="de8ea-179">Note</span><span class="sxs-lookup"><span data-stu-id="de8ea-179">Remarks</span></span>  
 <span data-ttu-id="de8ea-180">L'elemento `<authentication>` corrisponde alla classe <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication>.</span><span class="sxs-lookup"><span data-stu-id="de8ea-180">The `<authentication>` element corresponds to the <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication> class.</span></span> <span data-ttu-id="de8ea-181">Consente di personalizzare la modalità di autenticazione dei client.</span><span class="sxs-lookup"><span data-stu-id="de8ea-181">It enables you to customize how clients are authenticated.</span></span> <span data-ttu-id="de8ea-182">A tale scopo, l'attributo `certificateValidationMode` può essere impostato su `None`, `ChainTrust`, `PeerOrChainTrust`, `PeerTrust` o `Custom`.</span><span class="sxs-lookup"><span data-stu-id="de8ea-182">You can set the `certificateValidationMode` attribute to `None`, `ChainTrust`, `PeerOrChainTrust`, `PeerTrust`, or `Custom`.</span></span> <span data-ttu-id="de8ea-183">Per impostazione predefinita, il livello è impostato su `ChainTrust`, che consente di specificare che ogni certificato deve trovarsi in una gerarchia di certificati che termina in un *autorità principale* nella parte superiore della catena.</span><span class="sxs-lookup"><span data-stu-id="de8ea-183">By default, the level is set to `ChainTrust`, which specifies that each certificate must be found in a hierarchy of certificates ending in a *root authority* at the top of the chain.</span></span> <span data-ttu-id="de8ea-184">Si tratta della modalità più protetta.</span><span class="sxs-lookup"><span data-stu-id="de8ea-184">This is the most secure mode.</span></span> <span data-ttu-id="de8ea-185">Il livello può inoltre essere impostato su `PeerOrChainTrust`, a indicare che sia i certificati autocertificati (trust peer) sia i certificati appartenenti a una catena di trust sono ritenuti attendibili.</span><span class="sxs-lookup"><span data-stu-id="de8ea-185">You can also set the value to `PeerOrChainTrust`, which specifies that self-issued certificates (peer trust) are accepted as well as certificates that are in a trusted chain.</span></span> <span data-ttu-id="de8ea-186">Poiché i certificati autocertificati non devono essere acquistati da un'autorità attendibile, questo livello viene usato in fase di sviluppo e di debug dei client e dei servizi.</span><span class="sxs-lookup"><span data-stu-id="de8ea-186">This value is used when developing and debugging clients and services because self-issued certificates need not be purchased from a trusted authority.</span></span> <span data-ttu-id="de8ea-187">Quando si distribuisce un client è invece opportuno usare il livello `ChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="de8ea-187">When deploying a client, use the `ChainTrust` value instead.</span></span>  
  
 <span data-ttu-id="de8ea-188">Un altro livello disponibile è `Custom`.</span><span class="sxs-lookup"><span data-stu-id="de8ea-188">You can also set the value to `Custom`.</span></span> <span data-ttu-id="de8ea-189">Quando si imposta il livello `Custom` è necessario impostare anche l'attributo `customCertificateValidatorType` sull'assembly e sul tipo usati per convalidare il certificato.</span><span class="sxs-lookup"><span data-stu-id="de8ea-189">When set to the `Custom` value, you must also set the `customCertificateValidatorType` attribute to an assembly and type used to validate the certificate.</span></span> <span data-ttu-id="de8ea-190">Per creare un validator personalizzato è necessario ereditare una classe dalla classe astratta <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span><span class="sxs-lookup"><span data-stu-id="de8ea-190">To create your own custom validator, you must inherit from the abstract <xref:System.IdentityModel.Selectors.X509CertificateValidator> class.</span></span> <span data-ttu-id="de8ea-191">Per ulteriori informazioni, vedere [procedura: creare un servizio che usa un Validator del certificato personalizzato](../../../../../docs/framework/wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md).</span><span class="sxs-lookup"><span data-stu-id="de8ea-191">For more information, see [How to: Create a Service that Employs a Custom Certificate Validator](../../../../../docs/framework/wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="de8ea-192">Esempio</span><span class="sxs-lookup"><span data-stu-id="de8ea-192">Example</span></span>  
 <span data-ttu-id="de8ea-193">Nel codice seguente sono specificati un certificato X.509 e un tipo di convalida personalizzato nell'elemento `<authentication>`.</span><span class="sxs-lookup"><span data-stu-id="de8ea-193">The following code specifies an X.509 certificate and a custom validation type in the `<authentication>` element.</span></span>  
  
```xml  
<serviceBehaviors>  
 <behavior name="myServiceBehavior">  
  <clientCertificate>  
   <certificate   
         findValue="www.cohowinery.com"   
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
  
## <a name="see-also"></a><span data-ttu-id="de8ea-194">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="de8ea-194">See Also</span></span>  
 <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication>  
 <xref:System.ServiceModel.Security.X509CertificateValidationMode>  
 <xref:System.ServiceModel.Security.X509CertificateInitiatorServiceCredential.Authentication%2A>  
 <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement.Authentication%2A>  
 <xref:System.ServiceModel.Configuration.X509ClientCertificateAuthenticationElement>  
 [<span data-ttu-id="de8ea-195">Comportamenti di sicurezza</span><span class="sxs-lookup"><span data-stu-id="de8ea-195">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [<span data-ttu-id="de8ea-196">Procedura: creare un servizio che usa un Validator del certificato personalizzato</span><span class="sxs-lookup"><span data-stu-id="de8ea-196">How to: Create a Service that Employs a Custom Certificate Validator</span></span>](../../../../../docs/framework/wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md)  
 [<span data-ttu-id="de8ea-197">Utilizzo dei certificati</span><span class="sxs-lookup"><span data-stu-id="de8ea-197">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)

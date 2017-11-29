---
title: Elemento &lt;certificate&gt; di &lt;clientCertificate&gt;
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 00297efb-a7f2-4e03-bc2b-943d545610fc
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: bef4067d0fa74aa90841040ca5e6b3ea22f1e499
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ltcertificategt-of-ltclientcertificategt-element"></a><span data-ttu-id="8113c-102">Elemento &lt;certificate&gt; di &lt;clientCertificate&gt;</span><span class="sxs-lookup"><span data-stu-id="8113c-102">&lt;certificate&gt; of &lt;clientCertificate&gt; Element</span></span>
<span data-ttu-id="8113c-103">Specifica un certificato X.509 usato per firmare e crittografare messaggi.</span><span class="sxs-lookup"><span data-stu-id="8113c-103">Specifies an X.509 certificate used to sign and encrypt messages.</span></span>  
  
 <span data-ttu-id="8113c-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="8113c-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="8113c-105">\<i comportamenti ></span><span class="sxs-lookup"><span data-stu-id="8113c-105">\<behaviors></span></span>  
<span data-ttu-id="8113c-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="8113c-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="8113c-107">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="8113c-107">\<behavior></span></span>  
<span data-ttu-id="8113c-108">\<serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="8113c-108">\<serviceCredentials></span></span>  
<span data-ttu-id="8113c-109">\<clientCertificate ></span><span class="sxs-lookup"><span data-stu-id="8113c-109">\<clientCertificate></span></span>  
<span data-ttu-id="8113c-110">\<certificato ></span><span class="sxs-lookup"><span data-stu-id="8113c-110">\<certificate></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8113c-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8113c-111">Syntax</span></span>  
  
```xml  
<certificate findValue = "String"   
storeLocation = "CurrentUser/LocalMachine"  
storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"  
X509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8113c-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="8113c-112">Attributes and Elements</span></span>  
 <span data-ttu-id="8113c-113">Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.</span><span class="sxs-lookup"><span data-stu-id="8113c-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8113c-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="8113c-114">Attributes</span></span>  
  
|<span data-ttu-id="8113c-115">Attributo</span><span class="sxs-lookup"><span data-stu-id="8113c-115">Attribute</span></span>|<span data-ttu-id="8113c-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8113c-116">Description</span></span>|  
|---------------|-----------------|  
|`findValue`|<span data-ttu-id="8113c-117">Stringa che contiene il valore da cercare nell'archivio certificati X.509.</span><span class="sxs-lookup"><span data-stu-id="8113c-117">A string that contains the value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="8113c-118">Il tipo contenuto in questo attributo deve soddisfare i requisiti del valore X509FindType specificato.</span><span class="sxs-lookup"><span data-stu-id="8113c-118">The type contained in the attribute must satisfy the requirements of the specified X509FindType.</span></span> <span data-ttu-id="8113c-119">Il valore predefinito è una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="8113c-119">The default is an empty string.</span></span>|  
|`storeLocation`|<span data-ttu-id="8113c-120">Specifica il percorso dell'archivio certificati X.509 usato dal client per convalidare il certificato sul server.</span><span class="sxs-lookup"><span data-stu-id="8113c-120">Specifies the location of the X.509 certificate store that the client uses to validate the server’s certificate against.</span></span> <span data-ttu-id="8113c-121">Di seguito vengono elencati i valori validi:</span><span class="sxs-lookup"><span data-stu-id="8113c-121">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="8113c-122">-LocalMachine: l'archivio certificati assegnato al computer locale.</span><span class="sxs-lookup"><span data-stu-id="8113c-122">-   LocalMachine: the certificate store assigned to the local machine.</span></span><br /><span data-ttu-id="8113c-123">-CurrentUser: l'archivio certificati assegnato all'utente corrente.</span><span class="sxs-lookup"><span data-stu-id="8113c-123">-   CurrentUser: the certificate store assigned to the current user.</span></span><br /><br /> <span data-ttu-id="8113c-124">L'impostazione predefinita è LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="8113c-124">The default is LocalMachine.</span></span>|  
|`storeName`|<span data-ttu-id="8113c-125">Specifica il nome dell'archivio certificati X.509 da aprire.</span><span class="sxs-lookup"><span data-stu-id="8113c-125">Specifies the name of the X.509 certificate store to open.</span></span> <span data-ttu-id="8113c-126">Di seguito vengono elencati i valori validi:</span><span class="sxs-lookup"><span data-stu-id="8113c-126">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="8113c-127">-AddressBook: Archivio certificati per altri utenti.</span><span class="sxs-lookup"><span data-stu-id="8113c-127">-   AddressBook: Certificate store for other users.</span></span><br /><span data-ttu-id="8113c-128">-AuthRoot: Archivio certificati per autorità di certificazione di terze parti (CA).</span><span class="sxs-lookup"><span data-stu-id="8113c-128">-   AuthRoot: Certificate store for third-party certification authorities (CAs).</span></span><br /><span data-ttu-id="8113c-129">-CertificationAuthority: Archivio certificati per autorità di certificazione intermedie (CA).</span><span class="sxs-lookup"><span data-stu-id="8113c-129">-   CertificationAuthority: Certificate store for intermediate certification authorities (CAs).</span></span><br /><span data-ttu-id="8113c-130">-Disallowed: Archivio certificati per certificati revocati.</span><span class="sxs-lookup"><span data-stu-id="8113c-130">-   Disallowed: Certificate store for revoked certificates.</span></span><br /><span data-ttu-id="8113c-131">-My: Archivio certificati per certificati personali.</span><span class="sxs-lookup"><span data-stu-id="8113c-131">-   My: Certificate store for personal certificates.</span></span><br /><span data-ttu-id="8113c-132">-Root: Archivio certificati per autorità di certificazione radice attendibili (CA).</span><span class="sxs-lookup"><span data-stu-id="8113c-132">-   Root: Certificate store for trusted root certification authorities (CAs).</span></span><br /><span data-ttu-id="8113c-133">-TrustedPeople: Archivio certificati per utenti e risorse direttamente attendibili.</span><span class="sxs-lookup"><span data-stu-id="8113c-133">-   TrustedPeople: Certificate store for directly trusted people and resources.</span></span><br /><span data-ttu-id="8113c-134">-TrustedPublisher: Archivio certificati per autori direttamente attendibili.</span><span class="sxs-lookup"><span data-stu-id="8113c-134">-   TrustedPublisher: Certificate store for directly trusted publishers.</span></span><br /><br /> <span data-ttu-id="8113c-135">L'impostazione predefinita è My.</span><span class="sxs-lookup"><span data-stu-id="8113c-135">The default is My.</span></span>|  
|`X509FindType`|<span data-ttu-id="8113c-136">Definisce il tipo di ricerca X.509 da eseguire.</span><span class="sxs-lookup"><span data-stu-id="8113c-136">Defines the type of X.509 search to be executed.</span></span> <span data-ttu-id="8113c-137">Di seguito vengono elencati i valori validi:</span><span class="sxs-lookup"><span data-stu-id="8113c-137">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="8113c-138">-FindByThumbPrint</span><span class="sxs-lookup"><span data-stu-id="8113c-138">-   FindByThumbPrint</span></span><br /><span data-ttu-id="8113c-139">-FindBySubjectName</span><span class="sxs-lookup"><span data-stu-id="8113c-139">-   FindBySubjectName</span></span><br /><span data-ttu-id="8113c-140">-FindBySubjectDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="8113c-140">-   FindBySubjectDistinguishedName</span></span><br /><span data-ttu-id="8113c-141">-FindByIssuerName</span><span class="sxs-lookup"><span data-stu-id="8113c-141">-   FindByIssuerName</span></span><br /><span data-ttu-id="8113c-142">-FindByIssuerDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="8113c-142">-   FindByIssuerDistinguishedName</span></span><br /><span data-ttu-id="8113c-143">-FindBySerialNumber</span><span class="sxs-lookup"><span data-stu-id="8113c-143">-   FindBySerialNumber</span></span><br /><span data-ttu-id="8113c-144">-FindByTimeValid</span><span class="sxs-lookup"><span data-stu-id="8113c-144">-   FindByTimeValid</span></span><br /><span data-ttu-id="8113c-145">-FindByTimeNotYetValid</span><span class="sxs-lookup"><span data-stu-id="8113c-145">-   FindByTimeNotYetValid</span></span><br /><span data-ttu-id="8113c-146">-FindByTemplateName</span><span class="sxs-lookup"><span data-stu-id="8113c-146">-   FindByTemplateName</span></span><br /><span data-ttu-id="8113c-147">-FindByApplicationPolicy</span><span class="sxs-lookup"><span data-stu-id="8113c-147">-   FindByApplicationPolicy</span></span><br /><span data-ttu-id="8113c-148">-FindByCertificatePolicy</span><span class="sxs-lookup"><span data-stu-id="8113c-148">-   FindByCertificatePolicy</span></span><br /><span data-ttu-id="8113c-149">-FindByExtension</span><span class="sxs-lookup"><span data-stu-id="8113c-149">-   FindByExtension</span></span><br /><span data-ttu-id="8113c-150">-FindByKeyUsage</span><span class="sxs-lookup"><span data-stu-id="8113c-150">-   FindByKeyUsage</span></span><br /><span data-ttu-id="8113c-151">-FindBySubjectKeyIdentifier</span><span class="sxs-lookup"><span data-stu-id="8113c-151">-   FindBySubjectKeyIdentifier</span></span><br /><br /> <span data-ttu-id="8113c-152">Il tipo contenuto nell'attributo `findValue` deve soddisfare i requisiti del valore X509FindType specificato.</span><span class="sxs-lookup"><span data-stu-id="8113c-152">The type contained in the `findValue` attribute must satisfy the requirements of the specified X509FindType.</span></span><br /><br /> <span data-ttu-id="8113c-153">L'impostazione predefinita è FindBySubjectDistinguishedName.</span><span class="sxs-lookup"><span data-stu-id="8113c-153">The default value is FindBySubjectDistinguishedName.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8113c-154">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="8113c-154">Child Elements</span></span>  
 <span data-ttu-id="8113c-155">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="8113c-155">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8113c-156">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="8113c-156">Parent Elements</span></span>  
  
|<span data-ttu-id="8113c-157">Elemento</span><span class="sxs-lookup"><span data-stu-id="8113c-157">Element</span></span>|<span data-ttu-id="8113c-158">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8113c-158">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8113c-159">\<clientCertificate ></span><span class="sxs-lookup"><span data-stu-id="8113c-159">\<clientCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-servicecredentials.md)||  
  
## <a name="remarks"></a><span data-ttu-id="8113c-160">Note</span><span class="sxs-lookup"><span data-stu-id="8113c-160">Remarks</span></span>  
 <span data-ttu-id="8113c-161">L'elemento `<certificate>` viene usato quando il servizio deve disporre in anticipo del certificato del client per poter comunicare in modo sicuro con quest'ultimo.</span><span class="sxs-lookup"><span data-stu-id="8113c-161">The `<certificate>` element is used when the service must have the client's certificate in advance to communicate securely with the client.</span></span> <span data-ttu-id="8113c-162">Questa esigenza si presenta quando si usa il modello di comunicazione duplex.</span><span class="sxs-lookup"><span data-stu-id="8113c-162">This occurs when using the duplex communication pattern.</span></span> <span data-ttu-id="8113c-163">Nel modello più comune di comunicazione richiesta/risposta, il client include il proprio certificato nella richiesta e il servizio usa tale certificato per crittografare e firmare la risposta che invia al client.</span><span class="sxs-lookup"><span data-stu-id="8113c-163">In the more typical request/response pattern, the client includes its certificate in the request, which the service uses to encrypt and sign its response back to the client.</span></span> <span data-ttu-id="8113c-164">Nel modello di comunicazione duplex, tuttavia, il servizio non riceve alcuna richiesta dal client e pertanto deve disporre in anticipo del certificato del client per proteggere il messaggio da inviare al client.</span><span class="sxs-lookup"><span data-stu-id="8113c-164">In the duplex communication pattern, however, the service does not have a request from the client and therefore it needs the client's certificate in advance to secure the message to the client.</span></span> <span data-ttu-id="8113c-165">Questo certificato deve quindi essere ottenuto mediante una negoziazione fuori banda e deve essere specificato tramite questo elemento.</span><span class="sxs-lookup"><span data-stu-id="8113c-165">Therefore you must obtain the client's certificate in an out-of-band negotiation, and specify the certificate using this element.</span></span> <span data-ttu-id="8113c-166">Per ulteriori informazioni sui servizi duplex, vedere [procedura: creare un contratto Duplex](../../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md).</span><span class="sxs-lookup"><span data-stu-id="8113c-166">For more information about duplex services, see [How to: Create a Duplex Contract](../../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8113c-167">Esempio</span><span class="sxs-lookup"><span data-stu-id="8113c-167">Example</span></span>  
 <span data-ttu-id="8113c-168">Nel codice seguente viene illustrato come individuare un certificato X.509 appropriato e un tipo di convalida personalizzato nell'elemento `<authentication>`.</span><span class="sxs-lookup"><span data-stu-id="8113c-168">The following code specifies how to find an appropriate X.509 certificate and a custom validation type in the `<authentication>` element.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="8113c-169">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8113c-169">See Also</span></span>  
 <xref:System.ServiceModel.Security.X509CertificateInitiatorServiceCredential.Certificate%2A>  
 <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement.Certificate%2A>  
 <xref:System.ServiceModel.Configuration.X509ClientCertificateCredentialsElement>  
 [<span data-ttu-id="8113c-170">Comportamenti di sicurezza</span><span class="sxs-lookup"><span data-stu-id="8113c-170">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [<span data-ttu-id="8113c-171">Procedura: creare un servizio che usa un Validator del certificato personalizzato</span><span class="sxs-lookup"><span data-stu-id="8113c-171">How to: Create a Service that Employs a Custom Certificate Validator</span></span>](../../../../../docs/framework/wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md)  
 [<span data-ttu-id="8113c-172">Utilizzo dei certificati</span><span class="sxs-lookup"><span data-stu-id="8113c-172">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)

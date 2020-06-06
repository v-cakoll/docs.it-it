---
title: <certificate>dell' <clientCertificate> elemento
ms.date: 03/30/2017
ms.assetid: 00297efb-a7f2-4e03-bc2b-943d545610fc
ms.openlocfilehash: d0c4ef9d3657d2dfa787feb3576beda09d1997a3
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70400538"
---
# <a name="certificate-of-clientcertificate-element"></a><span data-ttu-id="ceb60-102">\<certificate>dell' \<clientCertificate> elemento</span><span class="sxs-lookup"><span data-stu-id="ceb60-102">\<certificate> of \<clientCertificate> Element</span></span>
<span data-ttu-id="ceb60-103">Specifica un certificato X.509 usato per firmare e crittografare messaggi.</span><span class="sxs-lookup"><span data-stu-id="ceb60-103">Specifies an X.509 certificate used to sign and encrypt messages.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCertificate>**](clientcertificate-of-servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<certificate>**  
  
## <a name="syntax"></a><span data-ttu-id="ceb60-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ceb60-104">Syntax</span></span>  
  
```xml  
<certificate findValue="String"
             storeLocation = "CurrentUser/LocalMachine"
             storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
             X509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ceb60-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="ceb60-105">Attributes and Elements</span></span>  
 <span data-ttu-id="ceb60-106">Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.</span><span class="sxs-lookup"><span data-stu-id="ceb60-106">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ceb60-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="ceb60-107">Attributes</span></span>  
  
|<span data-ttu-id="ceb60-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="ceb60-108">Attribute</span></span>|<span data-ttu-id="ceb60-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ceb60-109">Description</span></span>|  
|---------------|-----------------|  
|`findValue`|<span data-ttu-id="ceb60-110">Stringa che contiene il valore da cercare nell'archivio certificati X.509.</span><span class="sxs-lookup"><span data-stu-id="ceb60-110">A string that contains the value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="ceb60-111">Il tipo contenuto in questo attributo deve soddisfare i requisiti del valore X509FindType specificato.</span><span class="sxs-lookup"><span data-stu-id="ceb60-111">The type contained in the attribute must satisfy the requirements of the specified X509FindType.</span></span> <span data-ttu-id="ceb60-112">Il valore predefinito è una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="ceb60-112">The default is an empty string.</span></span>|  
|`storeLocation`|<span data-ttu-id="ceb60-113">Specifica il percorso dell'archivio certificati X.509 usato dal client per convalidare il certificato sul server.</span><span class="sxs-lookup"><span data-stu-id="ceb60-113">Specifies the location of the X.509 certificate store that the client uses to validate the server’s certificate against.</span></span> <span data-ttu-id="ceb60-114">I valori validi sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="ceb60-114">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="ceb60-115">-LocalMachine: l'archivio certificati assegnato al computer locale.</span><span class="sxs-lookup"><span data-stu-id="ceb60-115">-   LocalMachine: the certificate store assigned to the local machine.</span></span><br /><span data-ttu-id="ceb60-116">-CurrentUser: l'archivio certificati assegnato all'utente corrente.</span><span class="sxs-lookup"><span data-stu-id="ceb60-116">-   CurrentUser: the certificate store assigned to the current user.</span></span><br /><br /> <span data-ttu-id="ceb60-117">Il valore predefinito è LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="ceb60-117">The default is LocalMachine.</span></span>|  
|`storeName`|<span data-ttu-id="ceb60-118">Specifica il nome dell'archivio certificati X.509 da aprire.</span><span class="sxs-lookup"><span data-stu-id="ceb60-118">Specifies the name of the X.509 certificate store to open.</span></span> <span data-ttu-id="ceb60-119">I valori validi sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="ceb60-119">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="ceb60-120">-AddressBook: archivio certificati per altri utenti.</span><span class="sxs-lookup"><span data-stu-id="ceb60-120">-   AddressBook: Certificate store for other users.</span></span><br /><span data-ttu-id="ceb60-121">-AuthRoot: archivio certificati per autorità di certificazione (CA) di terze parti.</span><span class="sxs-lookup"><span data-stu-id="ceb60-121">-   AuthRoot: Certificate store for third-party certification authorities (CAs).</span></span><br /><span data-ttu-id="ceb60-122">-CertificationAuthority: archivio certificati per autorità di certificazione intermedie (CAs).</span><span class="sxs-lookup"><span data-stu-id="ceb60-122">-   CertificationAuthority: Certificate store for intermediate certification authorities (CAs).</span></span><br /><span data-ttu-id="ceb60-123">-Non consentito: archivio certificati per i certificati revocati.</span><span class="sxs-lookup"><span data-stu-id="ceb60-123">-   Disallowed: Certificate store for revoked certificates.</span></span><br /><span data-ttu-id="ceb60-124">-My: archivio certificati per i certificati personali.</span><span class="sxs-lookup"><span data-stu-id="ceb60-124">-   My: Certificate store for personal certificates.</span></span><br /><span data-ttu-id="ceb60-125">-Root: archivio certificati per autorità di certificazione radice attendibili (CAs).</span><span class="sxs-lookup"><span data-stu-id="ceb60-125">-   Root: Certificate store for trusted root certification authorities (CAs).</span></span><br /><span data-ttu-id="ceb60-126">-TrustedPeople: archivio certificati per utenti e risorse direttamente attendibili.</span><span class="sxs-lookup"><span data-stu-id="ceb60-126">-   TrustedPeople: Certificate store for directly trusted people and resources.</span></span><br /><span data-ttu-id="ceb60-127">-TrustedPublisher: archivio certificati per autori direttamente attendibili.</span><span class="sxs-lookup"><span data-stu-id="ceb60-127">-   TrustedPublisher: Certificate store for directly trusted publishers.</span></span><br /><br /> <span data-ttu-id="ceb60-128">L'impostazione predefinita è My.</span><span class="sxs-lookup"><span data-stu-id="ceb60-128">The default is My.</span></span>|  
|`X509FindType`|<span data-ttu-id="ceb60-129">Definisce il tipo di ricerca X.509 da eseguire.</span><span class="sxs-lookup"><span data-stu-id="ceb60-129">Defines the type of X.509 search to be executed.</span></span> <span data-ttu-id="ceb60-130">I valori validi sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="ceb60-130">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="ceb60-131">-FindByThumbPrint</span><span class="sxs-lookup"><span data-stu-id="ceb60-131">-   FindByThumbPrint</span></span><br /><span data-ttu-id="ceb60-132">-FindBySubjectName</span><span class="sxs-lookup"><span data-stu-id="ceb60-132">-   FindBySubjectName</span></span><br /><span data-ttu-id="ceb60-133">-FindBySubjectDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="ceb60-133">-   FindBySubjectDistinguishedName</span></span><br /><span data-ttu-id="ceb60-134">-FindByIssuerName</span><span class="sxs-lookup"><span data-stu-id="ceb60-134">-   FindByIssuerName</span></span><br /><span data-ttu-id="ceb60-135">-FindByIssuerDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="ceb60-135">-   FindByIssuerDistinguishedName</span></span><br /><span data-ttu-id="ceb60-136">-FindBySerialNumber</span><span class="sxs-lookup"><span data-stu-id="ceb60-136">-   FindBySerialNumber</span></span><br /><span data-ttu-id="ceb60-137">-FindByTimeValid</span><span class="sxs-lookup"><span data-stu-id="ceb60-137">-   FindByTimeValid</span></span><br /><span data-ttu-id="ceb60-138">-FindByTimeNotYetValid</span><span class="sxs-lookup"><span data-stu-id="ceb60-138">-   FindByTimeNotYetValid</span></span><br /><span data-ttu-id="ceb60-139">- FindByTemplateName</span><span class="sxs-lookup"><span data-stu-id="ceb60-139">-   FindByTemplateName</span></span><br /><span data-ttu-id="ceb60-140">- FindByApplicationPolicy</span><span class="sxs-lookup"><span data-stu-id="ceb60-140">-   FindByApplicationPolicy</span></span><br /><span data-ttu-id="ceb60-141">- FindByCertificatePolicy</span><span class="sxs-lookup"><span data-stu-id="ceb60-141">-   FindByCertificatePolicy</span></span><br /><span data-ttu-id="ceb60-142">- FindByExtension</span><span class="sxs-lookup"><span data-stu-id="ceb60-142">-   FindByExtension</span></span><br /><span data-ttu-id="ceb60-143">- FindByKeyUsage</span><span class="sxs-lookup"><span data-stu-id="ceb60-143">-   FindByKeyUsage</span></span><br /><span data-ttu-id="ceb60-144">- FindBySubjectKeyIdentifier</span><span class="sxs-lookup"><span data-stu-id="ceb60-144">-   FindBySubjectKeyIdentifier</span></span><br /><br /> <span data-ttu-id="ceb60-145">Il tipo contenuto nell'attributo `findValue` deve soddisfare i requisiti del valore X509FindType specificato.</span><span class="sxs-lookup"><span data-stu-id="ceb60-145">The type contained in the `findValue` attribute must satisfy the requirements of the specified X509FindType.</span></span><br /><br /> <span data-ttu-id="ceb60-146">L'impostazione predefinita è FindBySubjectDistinguishedName.</span><span class="sxs-lookup"><span data-stu-id="ceb60-146">The default value is FindBySubjectDistinguishedName.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ceb60-147">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="ceb60-147">Child Elements</span></span>  
 <span data-ttu-id="ceb60-148">No.</span><span class="sxs-lookup"><span data-stu-id="ceb60-148">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ceb60-149">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="ceb60-149">Parent Elements</span></span>  
  
|<span data-ttu-id="ceb60-150">Elemento</span><span class="sxs-lookup"><span data-stu-id="ceb60-150">Element</span></span>|<span data-ttu-id="ceb60-151">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ceb60-151">Description</span></span>|  
|-------------|-----------------|  
|[\<clientCertificate>](clientcertificate-of-servicecredentials.md)||  
  
## <a name="remarks"></a><span data-ttu-id="ceb60-152">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="ceb60-152">Remarks</span></span>  
 <span data-ttu-id="ceb60-153">L'elemento `<certificate>` viene usato quando il servizio deve disporre in anticipo del certificato del client per poter comunicare in modo sicuro con quest'ultimo.</span><span class="sxs-lookup"><span data-stu-id="ceb60-153">The `<certificate>` element is used when the service must have the client's certificate in advance to communicate securely with the client.</span></span> <span data-ttu-id="ceb60-154">Questa esigenza si presenta quando si usa il modello di comunicazione duplex.</span><span class="sxs-lookup"><span data-stu-id="ceb60-154">This occurs when using the duplex communication pattern.</span></span> <span data-ttu-id="ceb60-155">Nel modello più comune di comunicazione richiesta/risposta, il client include il proprio certificato nella richiesta e il servizio usa tale certificato per crittografare e firmare la risposta che invia al client.</span><span class="sxs-lookup"><span data-stu-id="ceb60-155">In the more typical request/response pattern, the client includes its certificate in the request, which the service uses to encrypt and sign its response back to the client.</span></span> <span data-ttu-id="ceb60-156">Nel modello di comunicazione duplex, tuttavia, il servizio non riceve alcuna richiesta dal client e pertanto deve disporre in anticipo del certificato del client per proteggere il messaggio da inviare al client.</span><span class="sxs-lookup"><span data-stu-id="ceb60-156">In the duplex communication pattern, however, the service does not have a request from the client and therefore it needs the client's certificate in advance to secure the message to the client.</span></span> <span data-ttu-id="ceb60-157">Questo certificato deve quindi essere ottenuto mediante una negoziazione fuori banda e deve essere specificato tramite questo elemento.</span><span class="sxs-lookup"><span data-stu-id="ceb60-157">Therefore you must obtain the client's certificate in an out-of-band negotiation, and specify the certificate using this element.</span></span> <span data-ttu-id="ceb60-158">Per ulteriori informazioni sui servizi duplex, vedere [procedura: creare un contratto duplex](../../../wcf/feature-details/how-to-create-a-duplex-contract.md).</span><span class="sxs-lookup"><span data-stu-id="ceb60-158">For more information about duplex services, see [How to: Create a Duplex Contract](../../../wcf/feature-details/how-to-create-a-duplex-contract.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ceb60-159">Esempio</span><span class="sxs-lookup"><span data-stu-id="ceb60-159">Example</span></span>  
 <span data-ttu-id="ceb60-160">Nel codice seguente viene illustrato come individuare un certificato X.509 appropriato e un tipo di convalida personalizzato nell'elemento `<authentication>`.</span><span class="sxs-lookup"><span data-stu-id="ceb60-160">The following code specifies how to find an appropriate X.509 certificate and a custom validation type in the `<authentication>` element.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ceb60-161">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="ceb60-161">See also</span></span>

- <xref:System.ServiceModel.Security.X509CertificateInitiatorServiceCredential.Certificate%2A>
- <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement.Certificate%2A>
- <xref:System.ServiceModel.Configuration.X509ClientCertificateCredentialsElement>
- [<span data-ttu-id="ceb60-162">Comportamenti di sicurezza</span><span class="sxs-lookup"><span data-stu-id="ceb60-162">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="ceb60-163">Procedura: creare un servizio che usa un validator del certificato personalizzato</span><span class="sxs-lookup"><span data-stu-id="ceb60-163">How to: Create a Service that Employs a Custom Certificate Validator</span></span>](../../../wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md)
- [<span data-ttu-id="ceb60-164">Working with Certificates</span><span class="sxs-lookup"><span data-stu-id="ceb60-164">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)

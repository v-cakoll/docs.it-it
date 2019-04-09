---
title: <certificate> Elemento
ms.date: 03/30/2017
ms.assetid: 9b3d9233-ef35-477a-bf5d-efd1e80a52f4
ms.openlocfilehash: eea8130911ca3780a6e4e753c17877e58c50b139
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59164268"
---
# <a name="certificate-element"></a><span data-ttu-id="1bb38-102">\<certificato > elemento</span><span class="sxs-lookup"><span data-stu-id="1bb38-102">\<certificate> Element</span></span>
<span data-ttu-id="1bb38-103">Specifica un certificato X.509 da usare per firmare e crittografare i messaggi di client peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="1bb38-103">Specifies an X.509 certificate to use for signing and encrypting messages for peer-to-peer clients.</span></span>  
  
 <span data-ttu-id="1bb38-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="1bb38-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="1bb38-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="1bb38-105">\<behaviors></span></span>  
<span data-ttu-id="1bb38-106">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="1bb38-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="1bb38-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="1bb38-107">\<behavior></span></span>  
<span data-ttu-id="1bb38-108">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="1bb38-108">\<clientCredentials></span></span>  
<span data-ttu-id="1bb38-109">\<peer></span><span class="sxs-lookup"><span data-stu-id="1bb38-109">\<peer></span></span>  
<span data-ttu-id="1bb38-110">\<certificate></span><span class="sxs-lookup"><span data-stu-id="1bb38-110">\<certificate></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1bb38-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1bb38-111">Syntax</span></span>  
  
```xml  
<certificate findValue="String"
             storeLocation="LocalMachine/CurrentUser"
             storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
             X509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1bb38-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="1bb38-112">Attributes and Elements</span></span>  
 <span data-ttu-id="1bb38-113">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="1bb38-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1bb38-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="1bb38-114">Attributes</span></span>  
  
|<span data-ttu-id="1bb38-115">Attributo</span><span class="sxs-lookup"><span data-stu-id="1bb38-115">Attribute</span></span>|<span data-ttu-id="1bb38-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1bb38-116">Description</span></span>|  
|---------------|-----------------|  
|`findValue`|<span data-ttu-id="1bb38-117">Stringa che contiene il valore da cercare nell'archivio certificati X.509.</span><span class="sxs-lookup"><span data-stu-id="1bb38-117">A string that contains the value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="1bb38-118">Il tipo contenuto nell'attributo deve soddisfare i requisiti del valore `x509FindType` specificato.</span><span class="sxs-lookup"><span data-stu-id="1bb38-118">The type contained in the attribute must satisfy the requirements of the specified `x509FindType`.</span></span> <span data-ttu-id="1bb38-119">Il valore predefinito è una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="1bb38-119">The default is an empty string.</span></span>|  
|`storeLocation`|<span data-ttu-id="1bb38-120">Specifica il percorso dell'archivio certificati X.509 usato dal client per eseguire la convalida del certificato peer.</span><span class="sxs-lookup"><span data-stu-id="1bb38-120">Specifies the location of the X.509 certificate store that the client uses to validate the peer's certificate against.</span></span> <span data-ttu-id="1bb38-121">Di seguito vengono elencati i valori validi:</span><span class="sxs-lookup"><span data-stu-id="1bb38-121">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="1bb38-122">-LocalMachine: l'archivio certificati assegnato al computer locale.</span><span class="sxs-lookup"><span data-stu-id="1bb38-122">-   LocalMachine: the certificate store assigned to the local machine.</span></span><br /><span data-ttu-id="1bb38-123">-CurrentUser: l'archivio certificati assegnato all'utente corrente.</span><span class="sxs-lookup"><span data-stu-id="1bb38-123">-   CurrentUser: the certificate store assigned to the current user.</span></span><br /><br /> <span data-ttu-id="1bb38-124">L'impostazione predefinita è LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="1bb38-124">The default is LocalMachine.</span></span>|  
|`storeName`|<span data-ttu-id="1bb38-125">Specifica il nome dell'archivio certificati X.509 da aprire.</span><span class="sxs-lookup"><span data-stu-id="1bb38-125">Specifies the name of the X.509 certificate store to open.</span></span> <span data-ttu-id="1bb38-126">Di seguito vengono elencati i valori validi:</span><span class="sxs-lookup"><span data-stu-id="1bb38-126">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="1bb38-127">-AddressBook: Archivio certificati per altri utenti.</span><span class="sxs-lookup"><span data-stu-id="1bb38-127">-   AddressBook: Certificate store for other users.</span></span><br /><span data-ttu-id="1bb38-128">-AuthRoot: Archivio certificati per autorità di certificazione di terze parti (CA).</span><span class="sxs-lookup"><span data-stu-id="1bb38-128">-   AuthRoot: Certificate store for third-party certification authorities (CAs).</span></span><br /><span data-ttu-id="1bb38-129">-CertificateAuthority: Archivio certificati per autorità di certificazione intermedie (CA).</span><span class="sxs-lookup"><span data-stu-id="1bb38-129">-   CertificateAuthority: Certificate store for intermediate certification authorities (CAs).</span></span><br /><span data-ttu-id="1bb38-130">-Non consentito: Archivio certificati per certificati revocati.</span><span class="sxs-lookup"><span data-stu-id="1bb38-130">-   Disallowed: Certificate store for revoked certificates.</span></span><br /><span data-ttu-id="1bb38-131">-Personali: Archivio certificati per certificati personali.</span><span class="sxs-lookup"><span data-stu-id="1bb38-131">-   My: Certificate store for personal certificates.</span></span><br /><span data-ttu-id="1bb38-132">-Root: Archivio certificati per autorità di certificazione radice attendibile (CA).</span><span class="sxs-lookup"><span data-stu-id="1bb38-132">-   Root: Certificate store for trusted root certification authorities (CAs).</span></span><br /><span data-ttu-id="1bb38-133">-TrustedPeople: Archivio certificati per le risorse e le persone direttamente attendibili.</span><span class="sxs-lookup"><span data-stu-id="1bb38-133">-   TrustedPeople: Certificate store for directly-trusted people and resources.</span></span><br /><span data-ttu-id="1bb38-134">-   TrustedPublisher: Archivio certificati per autori direttamente attendibili.</span><span class="sxs-lookup"><span data-stu-id="1bb38-134">-   TrustedPublisher: Certificate store for directly-trusted publishers.</span></span><br /><br /> <span data-ttu-id="1bb38-135">L'impostazione predefinita è My.</span><span class="sxs-lookup"><span data-stu-id="1bb38-135">The default is My.</span></span>|  
|`X509FindType`|<span data-ttu-id="1bb38-136">Definisce il tipo di ricerca X.509 da eseguire.</span><span class="sxs-lookup"><span data-stu-id="1bb38-136">Defines the type of X.509 search to be executed.</span></span> <span data-ttu-id="1bb38-137">Di seguito vengono elencati i valori validi:</span><span class="sxs-lookup"><span data-stu-id="1bb38-137">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="1bb38-138">-   FindByThumbPrint</span><span class="sxs-lookup"><span data-stu-id="1bb38-138">-   FindByThumbPrint</span></span><br /><span data-ttu-id="1bb38-139">-   FindBySubjectName</span><span class="sxs-lookup"><span data-stu-id="1bb38-139">-   FindBySubjectName</span></span><br /><span data-ttu-id="1bb38-140">-   FindBySubjectDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="1bb38-140">-   FindBySubjectDistinguishedName</span></span><br /><span data-ttu-id="1bb38-141">-   FindByIssuerName</span><span class="sxs-lookup"><span data-stu-id="1bb38-141">-   FindByIssuerName</span></span><br /><span data-ttu-id="1bb38-142">-   FindByIssuerDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="1bb38-142">-   FindByIssuerDistinguishedName</span></span><br /><span data-ttu-id="1bb38-143">-   FindBySerialNumber</span><span class="sxs-lookup"><span data-stu-id="1bb38-143">-   FindBySerialNumber</span></span><br /><span data-ttu-id="1bb38-144">-   FindByTimeValid</span><span class="sxs-lookup"><span data-stu-id="1bb38-144">-   FindByTimeValid</span></span><br /><span data-ttu-id="1bb38-145">-   FindByTimeNotYetValid</span><span class="sxs-lookup"><span data-stu-id="1bb38-145">-   FindByTimeNotYetValid</span></span><br /><span data-ttu-id="1bb38-146">-   FindByTemplateName</span><span class="sxs-lookup"><span data-stu-id="1bb38-146">-   FindByTemplateName</span></span><br /><span data-ttu-id="1bb38-147">-   FindByApplicationPolicy</span><span class="sxs-lookup"><span data-stu-id="1bb38-147">-   FindByApplicationPolicy</span></span><br /><span data-ttu-id="1bb38-148">-   FindByCertificatePolicy</span><span class="sxs-lookup"><span data-stu-id="1bb38-148">-   FindByCertificatePolicy</span></span><br /><span data-ttu-id="1bb38-149">-   FindByExtension</span><span class="sxs-lookup"><span data-stu-id="1bb38-149">-   FindByExtension</span></span><br /><span data-ttu-id="1bb38-150">-   FindByKeyUsage</span><span class="sxs-lookup"><span data-stu-id="1bb38-150">-   FindByKeyUsage</span></span><br /><span data-ttu-id="1bb38-151">-   FindBySubjectKeyIdentifier</span><span class="sxs-lookup"><span data-stu-id="1bb38-151">-   FindBySubjectKeyIdentifier</span></span><br /><br /> <span data-ttu-id="1bb38-152">Il tipo contenuto nell'attributo `findValue` deve soddisfare i requisiti del valore `X509FindType` specificato.</span><span class="sxs-lookup"><span data-stu-id="1bb38-152">The type contained in the `findValue` attribute must satisfy the requirements of the specified `X509FindType`.</span></span><br /><br /> <span data-ttu-id="1bb38-153">L'impostazione predefinita è FindBySubjectDistinguishedName.</span><span class="sxs-lookup"><span data-stu-id="1bb38-153">The default value is FindBySubjectDistinguishedName.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1bb38-154">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="1bb38-154">Child Elements</span></span>  
 <span data-ttu-id="1bb38-155">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="1bb38-155">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1bb38-156">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="1bb38-156">Parent Elements</span></span>  
  
|<span data-ttu-id="1bb38-157">Elemento</span><span class="sxs-lookup"><span data-stu-id="1bb38-157">Element</span></span>|<span data-ttu-id="1bb38-158">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1bb38-158">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1bb38-159">\<peer></span><span class="sxs-lookup"><span data-stu-id="1bb38-159">\<peer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-clientcredentials-element.md)|<span data-ttu-id="1bb38-160">Specifica le credenziali usate per l'autenticazione di client peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="1bb38-160">Specifies credentials used when authenticating peer-to-peer clients.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1bb38-161">Note</span><span class="sxs-lookup"><span data-stu-id="1bb38-161">Remarks</span></span>  
 <span data-ttu-id="1bb38-162">Questa elemento di configurazione contiene un'istanza X509Certificate2 usata per autenticare elementi adiacenti nella rete di peer.</span><span class="sxs-lookup"><span data-stu-id="1bb38-162">This configuration element contains a X509Certificate2 instance used when authenticating neighbors in the peer mesh.</span></span>  
  
 <span data-ttu-id="1bb38-163">Per altre informazioni sulla programmazione peer-to-peer, vedere [Peer-to-Peer Networking](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md).</span><span class="sxs-lookup"><span data-stu-id="1bb38-163">For more information about peer-to-peer programming, see [Peer-to-Peer Networking](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1bb38-164">Esempio</span><span class="sxs-lookup"><span data-stu-id="1bb38-164">Example</span></span>  
 <span data-ttu-id="1bb38-165">Nel codice seguente viene specificato come cercare il certificato usato in uno scenario peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="1bb38-165">The following code specifies how to find the certificate used in a peer-to-peer scenario.</span></span>  
  
```xml  
<behaviors>
  <endpointBehaviors>
    <behavior name="MyEndpointBehavior">
      <clientCredentials>
        <peer>
          <certificate findValue="www.contoso.com"
                       storeLocation="LocalMachine"
                       x509FindType="FindByIssuerName" />
        </peer>
      </clientCredentials>
    </behavior>
  </endpointBehaviors>
</behaviors>
```  
  
## <a name="see-also"></a><span data-ttu-id="1bb38-166">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1bb38-166">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerCredentialElement>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement.Certificate%2A>
- <xref:System.ServiceModel.Configuration.X509PeerCertificateElement>
- <xref:System.ServiceModel.Security.PeerCredential.Certificate%2A>
- [<span data-ttu-id="1bb38-167">Utilizzo dei certificati</span><span class="sxs-lookup"><span data-stu-id="1bb38-167">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="1bb38-168">Rete peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="1bb38-168">Peer-to-Peer Networking</span></span>](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)
- [<span data-ttu-id="1bb38-169">Autenticazione dei messaggi del canale peer</span><span class="sxs-lookup"><span data-stu-id="1bb38-169">Peer Channel Message Authentication</span></span>](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))
- [<span data-ttu-id="1bb38-170">Autenticazione personalizzata dei messaggi del canale</span><span class="sxs-lookup"><span data-stu-id="1bb38-170">Peer Channel Custom Authentication</span></span>](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))
- [<span data-ttu-id="1bb38-171">Protezione di applicazioni del canale peer</span><span class="sxs-lookup"><span data-stu-id="1bb38-171">Securing Peer Channel Applications</span></span>](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)

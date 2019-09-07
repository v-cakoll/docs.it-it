---
title: <certificate> Elemento
ms.date: 03/30/2017
ms.assetid: 9b3d9233-ef35-477a-bf5d-efd1e80a52f4
ms.openlocfilehash: e28e7d16073a56f3b6126439644bfff86c9af18b
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400547"
---
# <a name="certificate-element"></a><span data-ttu-id="1224c-102">\<Elemento certificate ></span><span class="sxs-lookup"><span data-stu-id="1224c-102">\<certificate> Element</span></span>
<span data-ttu-id="1224c-103">Specifica un certificato X.509 da usare per firmare e crittografare i messaggi di client peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="1224c-103">Specifies an X.509 certificate to use for signing and encrypting messages for peer-to-peer clients.</span></span>  
  
<span data-ttu-id="1224c-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="1224c-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="1224c-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="1224c-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="1224c-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamenti >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="1224c-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="1224c-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> endpointBehaviors**](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="1224c-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="1224c-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamento >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="1224c-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="1224c-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> clientCredentials**](clientcredentials.md)</span><span class="sxs-lookup"><span data-stu-id="1224c-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)</span></span>\
<span data-ttu-id="1224c-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> peer**](peer-of-clientcredentials-element.md)</span><span class="sxs-lookup"><span data-stu-id="1224c-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<peer>**](peer-of-clientcredentials-element.md)</span></span>\
<span data-ttu-id="1224c-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> certificato**</span><span class="sxs-lookup"><span data-stu-id="1224c-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<certificate>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1224c-112">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1224c-112">Syntax</span></span>  
  
```xml  
<certificate findValue="String"
             storeLocation="LocalMachine/CurrentUser"
             storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
             X509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1224c-113">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="1224c-113">Attributes and Elements</span></span>  
 <span data-ttu-id="1224c-114">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="1224c-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1224c-115">Attributi</span><span class="sxs-lookup"><span data-stu-id="1224c-115">Attributes</span></span>  
  
|<span data-ttu-id="1224c-116">Attributo</span><span class="sxs-lookup"><span data-stu-id="1224c-116">Attribute</span></span>|<span data-ttu-id="1224c-117">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="1224c-117">Description</span></span>|  
|---------------|-----------------|  
|`findValue`|<span data-ttu-id="1224c-118">Stringa che contiene il valore da cercare nell'archivio certificati X.509.</span><span class="sxs-lookup"><span data-stu-id="1224c-118">A string that contains the value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="1224c-119">Il tipo contenuto nell'attributo deve soddisfare i requisiti del valore `x509FindType` specificato.</span><span class="sxs-lookup"><span data-stu-id="1224c-119">The type contained in the attribute must satisfy the requirements of the specified `x509FindType`.</span></span> <span data-ttu-id="1224c-120">Il valore predefinito è una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="1224c-120">The default is an empty string.</span></span>|  
|`storeLocation`|<span data-ttu-id="1224c-121">Specifica il percorso dell'archivio certificati X.509 usato dal client per eseguire la convalida del certificato peer.</span><span class="sxs-lookup"><span data-stu-id="1224c-121">Specifies the location of the X.509 certificate store that the client uses to validate the peer's certificate against.</span></span> <span data-ttu-id="1224c-122">Di seguito vengono elencati i valori validi:</span><span class="sxs-lookup"><span data-stu-id="1224c-122">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="1224c-123">-LocalMachine: l'archivio certificati assegnato al computer locale.</span><span class="sxs-lookup"><span data-stu-id="1224c-123">-   LocalMachine: the certificate store assigned to the local machine.</span></span><br /><span data-ttu-id="1224c-124">-CurrentUser: l'archivio certificati assegnato all'utente corrente.</span><span class="sxs-lookup"><span data-stu-id="1224c-124">-   CurrentUser: the certificate store assigned to the current user.</span></span><br /><br /> <span data-ttu-id="1224c-125">L'impostazione predefinita è LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="1224c-125">The default is LocalMachine.</span></span>|  
|`storeName`|<span data-ttu-id="1224c-126">Specifica il nome dell'archivio certificati X.509 da aprire.</span><span class="sxs-lookup"><span data-stu-id="1224c-126">Specifies the name of the X.509 certificate store to open.</span></span> <span data-ttu-id="1224c-127">Di seguito vengono elencati i valori validi:</span><span class="sxs-lookup"><span data-stu-id="1224c-127">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="1224c-128">AddressBook Archivio certificati per altri utenti.</span><span class="sxs-lookup"><span data-stu-id="1224c-128">-   AddressBook: Certificate store for other users.</span></span><br /><span data-ttu-id="1224c-129">AuthRoot Archivio certificati per autorità di certificazione (CA) di terze parti.</span><span class="sxs-lookup"><span data-stu-id="1224c-129">-   AuthRoot: Certificate store for third-party certification authorities (CAs).</span></span><br /><span data-ttu-id="1224c-130">CertificateAuthority Archivio certificati per autorità di certificazione intermedie (CAs).</span><span class="sxs-lookup"><span data-stu-id="1224c-130">-   CertificateAuthority: Certificate store for intermediate certification authorities (CAs).</span></span><br /><span data-ttu-id="1224c-131">Consentiti Archivio certificati per i certificati revocati.</span><span class="sxs-lookup"><span data-stu-id="1224c-131">-   Disallowed: Certificate store for revoked certificates.</span></span><br /><span data-ttu-id="1224c-132">My Archivio certificati per i certificati personali.</span><span class="sxs-lookup"><span data-stu-id="1224c-132">-   My: Certificate store for personal certificates.</span></span><br /><span data-ttu-id="1224c-133">Radice Archivio certificati per autorità di certificazione radice attendibili (CAs).</span><span class="sxs-lookup"><span data-stu-id="1224c-133">-   Root: Certificate store for trusted root certification authorities (CAs).</span></span><br /><span data-ttu-id="1224c-134">TrustedPeople Archivio certificati per utenti e risorse direttamente attendibili.</span><span class="sxs-lookup"><span data-stu-id="1224c-134">-   TrustedPeople: Certificate store for directly-trusted people and resources.</span></span><br /><span data-ttu-id="1224c-135">TrustedPublisher Archivio certificati per autori direttamente attendibili.</span><span class="sxs-lookup"><span data-stu-id="1224c-135">-   TrustedPublisher: Certificate store for directly-trusted publishers.</span></span><br /><br /> <span data-ttu-id="1224c-136">L'impostazione predefinita è My.</span><span class="sxs-lookup"><span data-stu-id="1224c-136">The default is My.</span></span>|  
|`X509FindType`|<span data-ttu-id="1224c-137">Definisce il tipo di ricerca X.509 da eseguire.</span><span class="sxs-lookup"><span data-stu-id="1224c-137">Defines the type of X.509 search to be executed.</span></span> <span data-ttu-id="1224c-138">Di seguito vengono elencati i valori validi:</span><span class="sxs-lookup"><span data-stu-id="1224c-138">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="1224c-139">-   FindByThumbPrint</span><span class="sxs-lookup"><span data-stu-id="1224c-139">-   FindByThumbPrint</span></span><br /><span data-ttu-id="1224c-140">-FindBySubjectName</span><span class="sxs-lookup"><span data-stu-id="1224c-140">-   FindBySubjectName</span></span><br /><span data-ttu-id="1224c-141">-FindBySubjectDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="1224c-141">-   FindBySubjectDistinguishedName</span></span><br /><span data-ttu-id="1224c-142">-FindByIssuerName</span><span class="sxs-lookup"><span data-stu-id="1224c-142">-   FindByIssuerName</span></span><br /><span data-ttu-id="1224c-143">-FindByIssuerDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="1224c-143">-   FindByIssuerDistinguishedName</span></span><br /><span data-ttu-id="1224c-144">-FindBySerialNumber</span><span class="sxs-lookup"><span data-stu-id="1224c-144">-   FindBySerialNumber</span></span><br /><span data-ttu-id="1224c-145">-   FindByTimeValid</span><span class="sxs-lookup"><span data-stu-id="1224c-145">-   FindByTimeValid</span></span><br /><span data-ttu-id="1224c-146">-   FindByTimeNotYetValid</span><span class="sxs-lookup"><span data-stu-id="1224c-146">-   FindByTimeNotYetValid</span></span><br /><span data-ttu-id="1224c-147">-   FindByTemplateName</span><span class="sxs-lookup"><span data-stu-id="1224c-147">-   FindByTemplateName</span></span><br /><span data-ttu-id="1224c-148">- FindByApplicationPolicy</span><span class="sxs-lookup"><span data-stu-id="1224c-148">-   FindByApplicationPolicy</span></span><br /><span data-ttu-id="1224c-149">-   FindByCertificatePolicy</span><span class="sxs-lookup"><span data-stu-id="1224c-149">-   FindByCertificatePolicy</span></span><br /><span data-ttu-id="1224c-150">-   FindByExtension</span><span class="sxs-lookup"><span data-stu-id="1224c-150">-   FindByExtension</span></span><br /><span data-ttu-id="1224c-151">-   FindByKeyUsage</span><span class="sxs-lookup"><span data-stu-id="1224c-151">-   FindByKeyUsage</span></span><br /><span data-ttu-id="1224c-152">-   FindBySubjectKeyIdentifier</span><span class="sxs-lookup"><span data-stu-id="1224c-152">-   FindBySubjectKeyIdentifier</span></span><br /><br /> <span data-ttu-id="1224c-153">Il tipo contenuto nell'attributo `findValue` deve soddisfare i requisiti del valore `X509FindType` specificato.</span><span class="sxs-lookup"><span data-stu-id="1224c-153">The type contained in the `findValue` attribute must satisfy the requirements of the specified `X509FindType`.</span></span><br /><br /> <span data-ttu-id="1224c-154">L'impostazione predefinita è FindBySubjectDistinguishedName.</span><span class="sxs-lookup"><span data-stu-id="1224c-154">The default value is FindBySubjectDistinguishedName.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1224c-155">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="1224c-155">Child Elements</span></span>  
 <span data-ttu-id="1224c-156">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="1224c-156">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1224c-157">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="1224c-157">Parent Elements</span></span>  
  
|<span data-ttu-id="1224c-158">Elemento</span><span class="sxs-lookup"><span data-stu-id="1224c-158">Element</span></span>|<span data-ttu-id="1224c-159">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="1224c-159">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1224c-160">\<peer></span><span class="sxs-lookup"><span data-stu-id="1224c-160">\<peer></span></span>](peer-of-clientcredentials-element.md)|<span data-ttu-id="1224c-161">Specifica le credenziali usate per l'autenticazione di client peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="1224c-161">Specifies credentials used when authenticating peer-to-peer clients.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1224c-162">Note</span><span class="sxs-lookup"><span data-stu-id="1224c-162">Remarks</span></span>  
 <span data-ttu-id="1224c-163">Questa elemento di configurazione contiene un'istanza X509Certificate2 usata per autenticare elementi adiacenti nella rete di peer.</span><span class="sxs-lookup"><span data-stu-id="1224c-163">This configuration element contains a X509Certificate2 instance used when authenticating neighbors in the peer mesh.</span></span>  
  
 <span data-ttu-id="1224c-164">Per ulteriori informazioni sulla programmazione peer-to-peer, vedere la pagina relativa [alla rete peer-to-peer](../../../wcf/feature-details/peer-to-peer-networking.md).</span><span class="sxs-lookup"><span data-stu-id="1224c-164">For more information about peer-to-peer programming, see [Peer-to-Peer Networking](../../../wcf/feature-details/peer-to-peer-networking.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1224c-165">Esempio</span><span class="sxs-lookup"><span data-stu-id="1224c-165">Example</span></span>  
 <span data-ttu-id="1224c-166">Nel codice seguente viene specificato come cercare il certificato usato in uno scenario peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="1224c-166">The following code specifies how to find the certificate used in a peer-to-peer scenario.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="1224c-167">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1224c-167">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerCredentialElement>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement.Certificate%2A>
- <xref:System.ServiceModel.Configuration.X509PeerCertificateElement>
- <xref:System.ServiceModel.Security.PeerCredential.Certificate%2A>
- [<span data-ttu-id="1224c-168">Uso di certificati</span><span class="sxs-lookup"><span data-stu-id="1224c-168">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="1224c-169">Reti peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="1224c-169">Peer-to-Peer Networking</span></span>](../../../wcf/feature-details/peer-to-peer-networking.md)
- <span data-ttu-id="1224c-170">[Autenticazione del messaggio Peer Channel](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="1224c-170">[Peer Channel Message Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="1224c-171">[Peer Channel autenticazione personalizzata](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="1224c-171">[Peer Channel Custom Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="1224c-172">Protezione di applicazioni del canale peer</span><span class="sxs-lookup"><span data-stu-id="1224c-172">Securing Peer Channel Applications</span></span>](../../../wcf/feature-details/securing-peer-channel-applications.md)

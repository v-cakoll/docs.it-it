---
title: <certificate> Elemento
ms.date: 03/30/2017
ms.assetid: 9b3d9233-ef35-477a-bf5d-efd1e80a52f4
ms.openlocfilehash: e28e7d16073a56f3b6126439644bfff86c9af18b
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70400547"
---
# <a name="certificate-element"></a><span data-ttu-id="04043-102">\<certificate> Elemento</span><span class="sxs-lookup"><span data-stu-id="04043-102">\<certificate> Element</span></span>
<span data-ttu-id="04043-103">Specifica un certificato X.509 da usare per firmare e crittografare i messaggi di client peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="04043-103">Specifies an X.509 certificate to use for signing and encrypting messages for peer-to-peer clients.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<peer>**](peer-of-clientcredentials-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<certificate>**  
  
## <a name="syntax"></a><span data-ttu-id="04043-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="04043-104">Syntax</span></span>  
  
```xml  
<certificate findValue="String"
             storeLocation="LocalMachine/CurrentUser"
             storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
             X509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="04043-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="04043-105">Attributes and Elements</span></span>  
 <span data-ttu-id="04043-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="04043-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="04043-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="04043-107">Attributes</span></span>  
  
|<span data-ttu-id="04043-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="04043-108">Attribute</span></span>|<span data-ttu-id="04043-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="04043-109">Description</span></span>|  
|---------------|-----------------|  
|`findValue`|<span data-ttu-id="04043-110">Stringa che contiene il valore da cercare nell'archivio certificati X.509.</span><span class="sxs-lookup"><span data-stu-id="04043-110">A string that contains the value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="04043-111">Il tipo contenuto nell'attributo deve soddisfare i requisiti del valore `x509FindType` specificato.</span><span class="sxs-lookup"><span data-stu-id="04043-111">The type contained in the attribute must satisfy the requirements of the specified `x509FindType`.</span></span> <span data-ttu-id="04043-112">Il valore predefinito è una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="04043-112">The default is an empty string.</span></span>|  
|`storeLocation`|<span data-ttu-id="04043-113">Specifica il percorso dell'archivio certificati X.509 usato dal client per eseguire la convalida del certificato peer.</span><span class="sxs-lookup"><span data-stu-id="04043-113">Specifies the location of the X.509 certificate store that the client uses to validate the peer's certificate against.</span></span> <span data-ttu-id="04043-114">I valori validi sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="04043-114">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="04043-115">-LocalMachine: l'archivio certificati assegnato al computer locale.</span><span class="sxs-lookup"><span data-stu-id="04043-115">-   LocalMachine: the certificate store assigned to the local machine.</span></span><br /><span data-ttu-id="04043-116">-CurrentUser: l'archivio certificati assegnato all'utente corrente.</span><span class="sxs-lookup"><span data-stu-id="04043-116">-   CurrentUser: the certificate store assigned to the current user.</span></span><br /><br /> <span data-ttu-id="04043-117">Il valore predefinito è LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="04043-117">The default is LocalMachine.</span></span>|  
|`storeName`|<span data-ttu-id="04043-118">Specifica il nome dell'archivio certificati X.509 da aprire.</span><span class="sxs-lookup"><span data-stu-id="04043-118">Specifies the name of the X.509 certificate store to open.</span></span> <span data-ttu-id="04043-119">I valori validi sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="04043-119">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="04043-120">-AddressBook: archivio certificati per altri utenti.</span><span class="sxs-lookup"><span data-stu-id="04043-120">-   AddressBook: Certificate store for other users.</span></span><br /><span data-ttu-id="04043-121">-AuthRoot: archivio certificati per autorità di certificazione (CA) di terze parti.</span><span class="sxs-lookup"><span data-stu-id="04043-121">-   AuthRoot: Certificate store for third-party certification authorities (CAs).</span></span><br /><span data-ttu-id="04043-122">-CertificateAuthority: archivio certificati per autorità di certificazione intermedie (CAs).</span><span class="sxs-lookup"><span data-stu-id="04043-122">-   CertificateAuthority: Certificate store for intermediate certification authorities (CAs).</span></span><br /><span data-ttu-id="04043-123">-Non consentito: archivio certificati per i certificati revocati.</span><span class="sxs-lookup"><span data-stu-id="04043-123">-   Disallowed: Certificate store for revoked certificates.</span></span><br /><span data-ttu-id="04043-124">-My: archivio certificati per i certificati personali.</span><span class="sxs-lookup"><span data-stu-id="04043-124">-   My: Certificate store for personal certificates.</span></span><br /><span data-ttu-id="04043-125">-Root: archivio certificati per autorità di certificazione radice attendibili (CAs).</span><span class="sxs-lookup"><span data-stu-id="04043-125">-   Root: Certificate store for trusted root certification authorities (CAs).</span></span><br /><span data-ttu-id="04043-126">-TrustedPeople: archivio certificati per utenti e risorse direttamente attendibili.</span><span class="sxs-lookup"><span data-stu-id="04043-126">-   TrustedPeople: Certificate store for directly-trusted people and resources.</span></span><br /><span data-ttu-id="04043-127">-TrustedPublisher: archivio certificati per autori direttamente attendibili.</span><span class="sxs-lookup"><span data-stu-id="04043-127">-   TrustedPublisher: Certificate store for directly-trusted publishers.</span></span><br /><br /> <span data-ttu-id="04043-128">L'impostazione predefinita è My.</span><span class="sxs-lookup"><span data-stu-id="04043-128">The default is My.</span></span>|  
|`X509FindType`|<span data-ttu-id="04043-129">Definisce il tipo di ricerca X.509 da eseguire.</span><span class="sxs-lookup"><span data-stu-id="04043-129">Defines the type of X.509 search to be executed.</span></span> <span data-ttu-id="04043-130">I valori validi sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="04043-130">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="04043-131">-FindByThumbPrint</span><span class="sxs-lookup"><span data-stu-id="04043-131">-   FindByThumbPrint</span></span><br /><span data-ttu-id="04043-132">-FindBySubjectName</span><span class="sxs-lookup"><span data-stu-id="04043-132">-   FindBySubjectName</span></span><br /><span data-ttu-id="04043-133">-FindBySubjectDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="04043-133">-   FindBySubjectDistinguishedName</span></span><br /><span data-ttu-id="04043-134">-FindByIssuerName</span><span class="sxs-lookup"><span data-stu-id="04043-134">-   FindByIssuerName</span></span><br /><span data-ttu-id="04043-135">-FindByIssuerDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="04043-135">-   FindByIssuerDistinguishedName</span></span><br /><span data-ttu-id="04043-136">-FindBySerialNumber</span><span class="sxs-lookup"><span data-stu-id="04043-136">-   FindBySerialNumber</span></span><br /><span data-ttu-id="04043-137">-FindByTimeValid</span><span class="sxs-lookup"><span data-stu-id="04043-137">-   FindByTimeValid</span></span><br /><span data-ttu-id="04043-138">-FindByTimeNotYetValid</span><span class="sxs-lookup"><span data-stu-id="04043-138">-   FindByTimeNotYetValid</span></span><br /><span data-ttu-id="04043-139">- FindByTemplateName</span><span class="sxs-lookup"><span data-stu-id="04043-139">-   FindByTemplateName</span></span><br /><span data-ttu-id="04043-140">- FindByApplicationPolicy</span><span class="sxs-lookup"><span data-stu-id="04043-140">-   FindByApplicationPolicy</span></span><br /><span data-ttu-id="04043-141">- FindByCertificatePolicy</span><span class="sxs-lookup"><span data-stu-id="04043-141">-   FindByCertificatePolicy</span></span><br /><span data-ttu-id="04043-142">- FindByExtension</span><span class="sxs-lookup"><span data-stu-id="04043-142">-   FindByExtension</span></span><br /><span data-ttu-id="04043-143">- FindByKeyUsage</span><span class="sxs-lookup"><span data-stu-id="04043-143">-   FindByKeyUsage</span></span><br /><span data-ttu-id="04043-144">- FindBySubjectKeyIdentifier</span><span class="sxs-lookup"><span data-stu-id="04043-144">-   FindBySubjectKeyIdentifier</span></span><br /><br /> <span data-ttu-id="04043-145">Il tipo contenuto nell'attributo `findValue` deve soddisfare i requisiti del valore `X509FindType` specificato.</span><span class="sxs-lookup"><span data-stu-id="04043-145">The type contained in the `findValue` attribute must satisfy the requirements of the specified `X509FindType`.</span></span><br /><br /> <span data-ttu-id="04043-146">L'impostazione predefinita è FindBySubjectDistinguishedName.</span><span class="sxs-lookup"><span data-stu-id="04043-146">The default value is FindBySubjectDistinguishedName.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="04043-147">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="04043-147">Child Elements</span></span>  
 <span data-ttu-id="04043-148">No.</span><span class="sxs-lookup"><span data-stu-id="04043-148">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="04043-149">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="04043-149">Parent Elements</span></span>  
  
|<span data-ttu-id="04043-150">Elemento</span><span class="sxs-lookup"><span data-stu-id="04043-150">Element</span></span>|<span data-ttu-id="04043-151">Descrizione</span><span class="sxs-lookup"><span data-stu-id="04043-151">Description</span></span>|  
|-------------|-----------------|  
|[\<peer>](peer-of-clientcredentials-element.md)|<span data-ttu-id="04043-152">Specifica le credenziali usate per l'autenticazione di client peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="04043-152">Specifies credentials used when authenticating peer-to-peer clients.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="04043-153">Commenti</span><span class="sxs-lookup"><span data-stu-id="04043-153">Remarks</span></span>  
 <span data-ttu-id="04043-154">Questa elemento di configurazione contiene un'istanza X509Certificate2 usata per autenticare elementi adiacenti nella rete di peer.</span><span class="sxs-lookup"><span data-stu-id="04043-154">This configuration element contains a X509Certificate2 instance used when authenticating neighbors in the peer mesh.</span></span>  
  
 <span data-ttu-id="04043-155">Per ulteriori informazioni sulla programmazione peer-to-peer, vedere la pagina relativa [alla rete peer-to-peer](../../../wcf/feature-details/peer-to-peer-networking.md).</span><span class="sxs-lookup"><span data-stu-id="04043-155">For more information about peer-to-peer programming, see [Peer-to-Peer Networking](../../../wcf/feature-details/peer-to-peer-networking.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="04043-156">Esempio</span><span class="sxs-lookup"><span data-stu-id="04043-156">Example</span></span>  
 <span data-ttu-id="04043-157">Nel codice seguente viene specificato come cercare il certificato usato in uno scenario peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="04043-157">The following code specifies how to find the certificate used in a peer-to-peer scenario.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="04043-158">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="04043-158">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerCredentialElement>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement.Certificate%2A>
- <xref:System.ServiceModel.Configuration.X509PeerCertificateElement>
- <xref:System.ServiceModel.Security.PeerCredential.Certificate%2A>
- [<span data-ttu-id="04043-159">Working with Certificates</span><span class="sxs-lookup"><span data-stu-id="04043-159">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="04043-160">Rete peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="04043-160">Peer-to-Peer Networking</span></span>](../../../wcf/feature-details/peer-to-peer-networking.md)
- <span data-ttu-id="04043-161">[Autenticazione dei messaggi del canale peer](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="04043-161">[Peer Channel Message Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="04043-162">[Autenticazione personalizzata dei messaggi del canale](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="04043-162">[Peer Channel Custom Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="04043-163">Protezione di applicazioni del canale peer</span><span class="sxs-lookup"><span data-stu-id="04043-163">Securing Peer Channel Applications</span></span>](../../../wcf/feature-details/securing-peer-channel-applications.md)

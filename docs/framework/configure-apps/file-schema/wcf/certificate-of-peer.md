---
title: '&lt;certificate&gt; di &lt;peer&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 48b69142-c957-4305-a042-c9d0c9a55c0e
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f46ebab92cbca616b06db5be6dc155a44558aa7e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ltcertificategt-of-ltpeergt"></a><span data-ttu-id="58892-102">&lt;certificate&gt; di &lt;peer&gt;</span><span class="sxs-lookup"><span data-stu-id="58892-102">&lt;certificate&gt; of &lt;peer&gt;</span></span>
<span data-ttu-id="58892-103">Specifica un certificato usato da un peer.</span><span class="sxs-lookup"><span data-stu-id="58892-103">Specifies a certificate used by a peer.</span></span>  
  
 <span data-ttu-id="58892-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="58892-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="58892-105">\<i comportamenti ></span><span class="sxs-lookup"><span data-stu-id="58892-105">\<behaviors></span></span>  
<span data-ttu-id="58892-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="58892-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="58892-107">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="58892-107">\<behavior></span></span>  
<span data-ttu-id="58892-108">\<serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="58892-108">\<serviceCredentials></span></span>  
<span data-ttu-id="58892-109">\<peer ></span><span class="sxs-lookup"><span data-stu-id="58892-109">\<peer></span></span>  
<span data-ttu-id="58892-110">\<certificato ></span><span class="sxs-lookup"><span data-stu-id="58892-110">\<certificate></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58892-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="58892-111">Syntax</span></span>  
  
```xml  
<certificate findValue = "String"   
storeLocation = "CurrentUser/LocalMachine"  
storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"  
X509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="58892-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="58892-112">Attributes and Elements</span></span>  
 <span data-ttu-id="58892-113">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="58892-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="58892-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="58892-114">Attributes</span></span>  
  
|<span data-ttu-id="58892-115">Attributo</span><span class="sxs-lookup"><span data-stu-id="58892-115">Attribute</span></span>|<span data-ttu-id="58892-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="58892-116">Description</span></span>|  
|---------------|-----------------|  
|`findValue`|<span data-ttu-id="58892-117">Stringa che contiene il valore da cercare nell'archivio certificati X.509.</span><span class="sxs-lookup"><span data-stu-id="58892-117">A string that contains the value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="58892-118">Il tipo contenuto nell'attributo deve soddisfare i requisiti del valore `x509FindType` specificato.</span><span class="sxs-lookup"><span data-stu-id="58892-118">The type contained in the attribute must satisfy the requirements of the specified `x509FindType`.</span></span> <span data-ttu-id="58892-119">Il valore predefinito è una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="58892-119">The default is an empty string.</span></span>|  
|`storeLocation`|<span data-ttu-id="58892-120">Specifica il percorso dell'archivio certificati X.509 usato dal client per eseguire la convalida del certificato peer.</span><span class="sxs-lookup"><span data-stu-id="58892-120">Specifies the location of the X.509 certificate store that the client uses to validate the peer's certificate against.</span></span> <span data-ttu-id="58892-121">Di seguito vengono elencati i valori validi:</span><span class="sxs-lookup"><span data-stu-id="58892-121">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="58892-122">-LocalMachine: l'archivio certificati assegnato al computer locale.</span><span class="sxs-lookup"><span data-stu-id="58892-122">-   LocalMachine: the certificate store assigned to the local machine.</span></span><br /><span data-ttu-id="58892-123">-CurrentUser: l'archivio certificati assegnato all'utente corrente.</span><span class="sxs-lookup"><span data-stu-id="58892-123">-   CurrentUser: the certificate store assigned to the current user.</span></span><br /><br /> <span data-ttu-id="58892-124">L'impostazione predefinita è LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="58892-124">The default is LocalMachine.</span></span>|  
|`storeName`|<span data-ttu-id="58892-125">Specifica il nome dell'archivio certificati X.509 da aprire.</span><span class="sxs-lookup"><span data-stu-id="58892-125">Specifies the name of the X.509 certificate store to open.</span></span> <span data-ttu-id="58892-126">Di seguito vengono elencati i valori validi:</span><span class="sxs-lookup"><span data-stu-id="58892-126">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="58892-127">-AddressBook: Archivio certificati per altri utenti.</span><span class="sxs-lookup"><span data-stu-id="58892-127">-   AddressBook: Certificate store for other users.</span></span><br /><span data-ttu-id="58892-128">-AuthRoot: Archivio certificati per autorità di certificazione di terze parti (CA).</span><span class="sxs-lookup"><span data-stu-id="58892-128">-   AuthRoot: Certificate store for third-party certificate authorities (CAs).</span></span><br /><span data-ttu-id="58892-129">-CertificateAuthority: Archivio certificati per autorità di certificazione intermedie (CA).</span><span class="sxs-lookup"><span data-stu-id="58892-129">-   CertificateAuthority: Certificate store for intermediate certificate authorities (CAs).</span></span><br /><span data-ttu-id="58892-130">-Disallowed: Archivio certificati per certificati revocati.</span><span class="sxs-lookup"><span data-stu-id="58892-130">-   Disallowed: Certificate store for revoked certificates.</span></span><br /><span data-ttu-id="58892-131">-My: Archivio certificati per certificati personali.</span><span class="sxs-lookup"><span data-stu-id="58892-131">-   My: Certificate store for personal certificates.</span></span><br /><span data-ttu-id="58892-132">-Root: Archivio certificati per autorità di certificazione radice attendibile (CA).</span><span class="sxs-lookup"><span data-stu-id="58892-132">-   Root: Certificate store for trusted root certificate authorities (CAs).</span></span><br /><span data-ttu-id="58892-133">-TrustedPeople: Archivio certificati per utenti e risorse direttamente attendibili.</span><span class="sxs-lookup"><span data-stu-id="58892-133">-   TrustedPeople: Certificate store for directly-trusted people and resources.</span></span><br /><span data-ttu-id="58892-134">-TrustedPublisher: Archivio certificati per autori direttamente attendibili.</span><span class="sxs-lookup"><span data-stu-id="58892-134">-   TrustedPublisher: Certificate store for directly-trusted publishers.</span></span><br /><br /> <span data-ttu-id="58892-135">L'impostazione predefinita è My.</span><span class="sxs-lookup"><span data-stu-id="58892-135">The default is My.</span></span>|  
|`X509FindType`|<span data-ttu-id="58892-136">Definisce il tipo di ricerca X.509 da eseguire.</span><span class="sxs-lookup"><span data-stu-id="58892-136">Defines the type of X.509 search to be executed.</span></span> <span data-ttu-id="58892-137">Di seguito vengono elencati i valori validi:</span><span class="sxs-lookup"><span data-stu-id="58892-137">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="58892-138">-FindByThumbPrint</span><span class="sxs-lookup"><span data-stu-id="58892-138">-   FindByThumbPrint</span></span><br /><span data-ttu-id="58892-139">-FindBySubjectName</span><span class="sxs-lookup"><span data-stu-id="58892-139">-   FindBySubjectName</span></span><br /><span data-ttu-id="58892-140">-FindBySubjectDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="58892-140">-   FindBySubjectDistinguishedName</span></span><br /><span data-ttu-id="58892-141">-FindByIssuerName</span><span class="sxs-lookup"><span data-stu-id="58892-141">-   FindByIssuerName</span></span><br /><span data-ttu-id="58892-142">-FindByIssuerDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="58892-142">-   FindByIssuerDistinguishedName</span></span><br /><span data-ttu-id="58892-143">-FindBySerialNumber</span><span class="sxs-lookup"><span data-stu-id="58892-143">-   FindBySerialNumber</span></span><br /><span data-ttu-id="58892-144">-FindByTimeValid</span><span class="sxs-lookup"><span data-stu-id="58892-144">-   FindByTimeValid</span></span><br /><span data-ttu-id="58892-145">-FindByTimeNotYetValid</span><span class="sxs-lookup"><span data-stu-id="58892-145">-   FindByTimeNotYetValid</span></span><br /><span data-ttu-id="58892-146">-FindByTemplateName</span><span class="sxs-lookup"><span data-stu-id="58892-146">-   FindByTemplateName</span></span><br /><span data-ttu-id="58892-147">-FindByApplicationPolicy</span><span class="sxs-lookup"><span data-stu-id="58892-147">-   FindByApplicationPolicy</span></span><br /><span data-ttu-id="58892-148">-FindByCertificatePolicy</span><span class="sxs-lookup"><span data-stu-id="58892-148">-   FindByCertificatePolicy</span></span><br /><span data-ttu-id="58892-149">-FindByExtension</span><span class="sxs-lookup"><span data-stu-id="58892-149">-   FindByExtension</span></span><br /><span data-ttu-id="58892-150">-FindByKeyUsage</span><span class="sxs-lookup"><span data-stu-id="58892-150">-   FindByKeyUsage</span></span><br /><span data-ttu-id="58892-151">-FindBySubjectKeyIdentifier</span><span class="sxs-lookup"><span data-stu-id="58892-151">-   FindBySubjectKeyIdentifier</span></span><br /><br /> <span data-ttu-id="58892-152">Il tipo contenuto nell'attributo `findValue` deve soddisfare i requisiti del valore `X509FindType` specificato.</span><span class="sxs-lookup"><span data-stu-id="58892-152">The type contained in the `findValue` attribute must satisfy the requirements of the specified `X509FindType`.</span></span><br /><br /> <span data-ttu-id="58892-153">L'impostazione predefinita è FindBySubjectDistinguishedName.</span><span class="sxs-lookup"><span data-stu-id="58892-153">The default value is FindBySubjectDistinguishedName.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="58892-154">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="58892-154">Child Elements</span></span>  
 <span data-ttu-id="58892-155">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="58892-155">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="58892-156">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="58892-156">Parent Elements</span></span>  
  
|<span data-ttu-id="58892-157">Elemento</span><span class="sxs-lookup"><span data-stu-id="58892-157">Element</span></span>|<span data-ttu-id="58892-158">Descrizione</span><span class="sxs-lookup"><span data-stu-id="58892-158">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="58892-159">\<peer ></span><span class="sxs-lookup"><span data-stu-id="58892-159">\<peer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-servicecredentials.md)|<span data-ttu-id="58892-160">Specifica le credenziali correnti per un nodo peer.</span><span class="sxs-lookup"><span data-stu-id="58892-160">Specifies the current credentials for a peer node.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="58892-161">Note</span><span class="sxs-lookup"><span data-stu-id="58892-161">Remarks</span></span>  
 <span data-ttu-id="58892-162">Questa elemento di configurazione contiene un'istanza `X509Certificate2` usata per autenticare elementi adiacenti nella rete di peer.</span><span class="sxs-lookup"><span data-stu-id="58892-162">This configuration element contains an `X509Certificate2` instance used when authenticating neighbors in the peer mesh.</span></span>  
  
 <span data-ttu-id="58892-163">Per ulteriori informazioni sulla programmazione peer-to-peer, vedere [rete Peer-to-Peer](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md).</span><span class="sxs-lookup"><span data-stu-id="58892-163">For more information about peer-to-peer programming, see [Peer-to-Peer Networking](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58892-164">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="58892-164">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.PeerCredentialElement>  
 <xref:System.ServiceModel.Configuration.PeerCredentialElement.Certificate%2A>  
 <xref:System.ServiceModel.Configuration.X509PeerCertificateElement>  
 <xref:System.ServiceModel.Security.PeerCredential.Certificate%2A>  
 <xref:System.ServiceModel.Security.PeerCredential>  
 [<span data-ttu-id="58892-165">Uso di certificati</span><span class="sxs-lookup"><span data-stu-id="58892-165">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [<span data-ttu-id="58892-166">Reti peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="58892-166">Peer-to-Peer Networking</span></span>](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)  
 [<span data-ttu-id="58892-167">Autenticazione dei messaggi del canale peer</span><span class="sxs-lookup"><span data-stu-id="58892-167">Peer Channel Message Authentication</span></span>](http://msdn.microsoft.com/en-us/80e73386-514e-4c30-9e4a-b9ca8c173a95)  
 [<span data-ttu-id="58892-168">Autenticazione personalizzata canale peer</span><span class="sxs-lookup"><span data-stu-id="58892-168">Peer Channel Custom Authentication</span></span>](http://msdn.microsoft.com/en-us/4aa8a82e-41a8-48e2-8621-7e1cbabdca7c)  
 [<span data-ttu-id="58892-169">Protezione di applicazioni del canale peer</span><span class="sxs-lookup"><span data-stu-id="58892-169">Securing Peer Channel Applications</span></span>](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)  
 [<span data-ttu-id="58892-170">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="58892-170">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)

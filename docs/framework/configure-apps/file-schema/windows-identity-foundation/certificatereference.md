---
title: '&lt;CertificateReference&gt;'
ms.date: 03/30/2017
ms.assetid: 2ac8bc14-e9f1-48fb-b662-f5991558fbe4
author: BrucePerlerMS
ms.openlocfilehash: e04dc90134aadfb8af7b0800c7144963d267f513
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/25/2018
ms.locfileid: "47075083"
---
# <a name="ltcertificatereferencegt"></a><span data-ttu-id="a6449-102">&lt;CertificateReference&gt;</span><span class="sxs-lookup"><span data-stu-id="a6449-102">&lt;certificateReference&gt;</span></span>
<span data-ttu-id="a6449-103">Specifica le impostazioni che consentono di trovare e convalidare un certificato X.509 in un archivio certificati.</span><span class="sxs-lookup"><span data-stu-id="a6449-103">Specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span>  
  
 <span data-ttu-id="a6449-104">\<IdentityModel ></span><span class="sxs-lookup"><span data-stu-id="a6449-104">\<system.identityModel.services></span></span>  
<span data-ttu-id="a6449-105">\<federationConfiguration ></span><span class="sxs-lookup"><span data-stu-id="a6449-105">\<federationConfiguration></span></span>  
<span data-ttu-id="a6449-106">\<serviceCertificate ></span><span class="sxs-lookup"><span data-stu-id="a6449-106">\<serviceCertificate></span></span>  
<span data-ttu-id="a6449-107">\<certificateReference ></span><span class="sxs-lookup"><span data-stu-id="a6449-107">\<certificateReference></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a6449-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a6449-108">Syntax</span></span>  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration>  
    <serviceCertificate>  
      <certificateReference   
        storeName="AddressBook||AuthRoot||CertificateAuthority||Disallowed||My||Root||TrustedPeople||TrustedPublisher"  
        storeLocation="CurrentUser||LocalMachine"  
        x509FindType="FindByThumbprint||FindBySubjectName||FindBySubjectDistinguishedName||FindByIssuerName||FindByIssuerDistinguishedName||FindBySerialNumber||FindByTimeValid||FindByTimeNotYetValid||FindByTimeExpired||FindByTemplateName||FindByApplicationPolicy||FindByCertificatePolicy||FindByExtension||FindByKeyUsage||FindBySubjectKeyIdentifier"  
        findValue=xs:String  
        isChainIncluded=xs:Boolean >  
      </certificateReference>  
    </serviceCertificate>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a6449-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="a6449-109">Attributes and Elements</span></span>  
 <span data-ttu-id="a6449-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="a6449-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a6449-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="a6449-111">Attributes</span></span>  
  
|<span data-ttu-id="a6449-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="a6449-112">Attribute</span></span>|<span data-ttu-id="a6449-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a6449-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a6449-114">storeName</span><span class="sxs-lookup"><span data-stu-id="a6449-114">storeName</span></span>|<span data-ttu-id="a6449-115">Il nome dell'archivio certificati X.509.</span><span class="sxs-lookup"><span data-stu-id="a6449-115">The name of the X.509 certificate store.</span></span> <span data-ttu-id="a6449-116">Il valore predefinito è "My".</span><span class="sxs-lookup"><span data-stu-id="a6449-116">The default is "My".</span></span> <span data-ttu-id="a6449-117">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="a6449-117">Optional.</span></span>|  
|<span data-ttu-id="a6449-118">storeLocation</span><span class="sxs-lookup"><span data-stu-id="a6449-118">storeLocation</span></span>|<span data-ttu-id="a6449-119">Oggetto <xref:System.Security.Cryptography.X509Certificates.StoreLocation> valore che specifica il percorso dell'archivio certificati X.509.</span><span class="sxs-lookup"><span data-stu-id="a6449-119">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the location of the X.509 certificate store.</span></span> <span data-ttu-id="a6449-120">Il valore predefinito è "LocalMachine".</span><span class="sxs-lookup"><span data-stu-id="a6449-120">The default value is "LocalMachine".</span></span> <span data-ttu-id="a6449-121">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="a6449-121">Optional.</span></span>|  
|<span data-ttu-id="a6449-122">x509FindType</span><span class="sxs-lookup"><span data-stu-id="a6449-122">x509FindType</span></span>|<span data-ttu-id="a6449-123">Un <xref:System.Security.Cryptography.X509Certificates.X509FindType> valore che specifica il tipo di ricerca che deve essere eseguito.</span><span class="sxs-lookup"><span data-stu-id="a6449-123">An <xref:System.Security.Cryptography.X509Certificates.X509FindType> value that specifies the type of search that is to be executed.</span></span> <span data-ttu-id="a6449-124">Il valore predefinito è "FindBySubjectDistinguishedName".</span><span class="sxs-lookup"><span data-stu-id="a6449-124">The default is "FindBySubjectDistinguishedName".</span></span> <span data-ttu-id="a6449-125">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="a6449-125">Optional.</span></span>|  
|<span data-ttu-id="a6449-126">findValue</span><span class="sxs-lookup"><span data-stu-id="a6449-126">findValue</span></span>|<span data-ttu-id="a6449-127">Valore da cercare nell'archivio certificati X.509.</span><span class="sxs-lookup"><span data-stu-id="a6449-127">The value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="a6449-128">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="a6449-128">Optional.</span></span>|  
|<span data-ttu-id="a6449-129">isChainIncluded</span><span class="sxs-lookup"><span data-stu-id="a6449-129">isChainIncluded</span></span>|<span data-ttu-id="a6449-130">Specifica se la convalida deve essere eseguita usando la catena di certificati.</span><span class="sxs-lookup"><span data-stu-id="a6449-130">Specifies whether validation should be performed by using the certificate chain.</span></span> <span data-ttu-id="a6449-131">Il valore predefinito è "true". la convalida viene eseguita usando la catena di certificati.</span><span class="sxs-lookup"><span data-stu-id="a6449-131">The default is "true"; validation is performed by using the certificate chain.</span></span> <span data-ttu-id="a6449-132">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="a6449-132">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a6449-133">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="a6449-133">Child Elements</span></span>  
 <span data-ttu-id="a6449-134">nessuno</span><span class="sxs-lookup"><span data-stu-id="a6449-134">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a6449-135">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="a6449-135">Parent Elements</span></span>  
  
|<span data-ttu-id="a6449-136">Elemento</span><span class="sxs-lookup"><span data-stu-id="a6449-136">Element</span></span>|<span data-ttu-id="a6449-137">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a6449-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a6449-138">\<serviceCertificate ></span><span class="sxs-lookup"><span data-stu-id="a6449-138">\<serviceCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/servicecertificate.md)|<span data-ttu-id="a6449-139">Configura il certificato utilizzato per crittografare e decrittografare i token.</span><span class="sxs-lookup"><span data-stu-id="a6449-139">Configures the certificate that is used to encrypt and decrypt tokens.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a6449-140">Note</span><span class="sxs-lookup"><span data-stu-id="a6449-140">Remarks</span></span>  
 <span data-ttu-id="a6449-141">Il `<certificateReference>` elemento specifica le impostazioni che vengono usate per trovare e convalidare un certificato X.509 in un archivio certificati.</span><span class="sxs-lookup"><span data-stu-id="a6449-141">The `<certificateReference>` element specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span> <span data-ttu-id="a6449-142">Quando viene specificato come elemento figlio del `<serviceCertficate>` elemento, specifica la posizione e verifica le impostazioni del certificato X.509 utilizzato per crittografare e decrittografare i token.</span><span class="sxs-lookup"><span data-stu-id="a6449-142">When it is specified as the child element of the `<serviceCertficate>` element, it specifies the location and verification settings of the X.509 certificate that is used to encrypt and decrypt tokens.</span></span> <span data-ttu-id="a6449-143">Il `<certificateReference>` elemento è rappresentato dal <xref:System.ServiceModel.Configuration.CertificateReferenceElement> classe.</span><span class="sxs-lookup"><span data-stu-id="a6449-143">The `<certificateReference>` element is represented by the <xref:System.ServiceModel.Configuration.CertificateReferenceElement> class.</span></span>

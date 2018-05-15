---
title: '&lt;certificateReference&gt;'
ms.date: 03/30/2017
ms.assetid: 2ac8bc14-e9f1-48fb-b662-f5991558fbe4
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: e0f9a826a4c8d292346d9efee7970a82b88fb612
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="ltcertificatereferencegt"></a><span data-ttu-id="f0e7b-102">&lt;certificateReference&gt;</span><span class="sxs-lookup"><span data-stu-id="f0e7b-102">&lt;certificateReference&gt;</span></span>
<span data-ttu-id="f0e7b-103">Specifica le impostazioni che consentono di trovare e convalidare un certificato x. 509 nell'archivio certificati.</span><span class="sxs-lookup"><span data-stu-id="f0e7b-103">Specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span>  
  
 <span data-ttu-id="f0e7b-104">\<IdentityModel ></span><span class="sxs-lookup"><span data-stu-id="f0e7b-104">\<system.identityModel.services></span></span>  
<span data-ttu-id="f0e7b-105">\<federationConfiguration ></span><span class="sxs-lookup"><span data-stu-id="f0e7b-105">\<federationConfiguration></span></span>  
<span data-ttu-id="f0e7b-106">\<elemento serviceCertificate ></span><span class="sxs-lookup"><span data-stu-id="f0e7b-106">\<serviceCertificate></span></span>  
<span data-ttu-id="f0e7b-107">\<certificateReference ></span><span class="sxs-lookup"><span data-stu-id="f0e7b-107">\<certificateReference></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0e7b-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f0e7b-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f0e7b-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="f0e7b-109">Attributes and Elements</span></span>  
 <span data-ttu-id="f0e7b-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="f0e7b-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f0e7b-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="f0e7b-111">Attributes</span></span>  
  
|<span data-ttu-id="f0e7b-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="f0e7b-112">Attribute</span></span>|<span data-ttu-id="f0e7b-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f0e7b-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f0e7b-114">storeName</span><span class="sxs-lookup"><span data-stu-id="f0e7b-114">storeName</span></span>|<span data-ttu-id="f0e7b-115">Il nome dell'archivio certificati x. 509.</span><span class="sxs-lookup"><span data-stu-id="f0e7b-115">The name of the X.509 certificate store.</span></span> <span data-ttu-id="f0e7b-116">Il valore predefinito è "My".</span><span class="sxs-lookup"><span data-stu-id="f0e7b-116">The default is "My".</span></span> <span data-ttu-id="f0e7b-117">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="f0e7b-117">Optional.</span></span>|  
|<span data-ttu-id="f0e7b-118">storeLocation</span><span class="sxs-lookup"><span data-stu-id="f0e7b-118">storeLocation</span></span>|<span data-ttu-id="f0e7b-119">Oggetto <xref:System.Security.Cryptography.X509Certificates.StoreLocation> valore che specifica il percorso dell'archivio certificati x. 509.</span><span class="sxs-lookup"><span data-stu-id="f0e7b-119">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the location of the X.509 certificate store.</span></span> <span data-ttu-id="f0e7b-120">Il valore predefinito è "LocalMachine".</span><span class="sxs-lookup"><span data-stu-id="f0e7b-120">The default value is "LocalMachine".</span></span> <span data-ttu-id="f0e7b-121">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="f0e7b-121">Optional.</span></span>|  
|<span data-ttu-id="f0e7b-122">x509FindType</span><span class="sxs-lookup"><span data-stu-id="f0e7b-122">x509FindType</span></span>|<span data-ttu-id="f0e7b-123">Un <xref:System.Security.Cryptography.X509Certificates.X509FindType> valore che specifica il tipo di ricerca che deve essere eseguito.</span><span class="sxs-lookup"><span data-stu-id="f0e7b-123">An <xref:System.Security.Cryptography.X509Certificates.X509FindType> value that specifies the type of search that is to be executed.</span></span> <span data-ttu-id="f0e7b-124">Il valore predefinito è "FindBySubjectDistinguishedName".</span><span class="sxs-lookup"><span data-stu-id="f0e7b-124">The default is "FindBySubjectDistinguishedName".</span></span> <span data-ttu-id="f0e7b-125">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="f0e7b-125">Optional.</span></span>|  
|<span data-ttu-id="f0e7b-126">findValue</span><span class="sxs-lookup"><span data-stu-id="f0e7b-126">findValue</span></span>|<span data-ttu-id="f0e7b-127">Valore da cercare nell'archivio certificati X.509.</span><span class="sxs-lookup"><span data-stu-id="f0e7b-127">The value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="f0e7b-128">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="f0e7b-128">Optional.</span></span>|  
|<span data-ttu-id="f0e7b-129">isChainIncluded</span><span class="sxs-lookup"><span data-stu-id="f0e7b-129">isChainIncluded</span></span>|<span data-ttu-id="f0e7b-130">Specifica se la convalida deve essere eseguita usando la catena di certificati.</span><span class="sxs-lookup"><span data-stu-id="f0e7b-130">Specifies whether validation should be performed by using the certificate chain.</span></span> <span data-ttu-id="f0e7b-131">Il valore predefinito è "true". la convalida viene eseguita usando la catena di certificati.</span><span class="sxs-lookup"><span data-stu-id="f0e7b-131">The default is "true"; validation is performed by using the certificate chain.</span></span> <span data-ttu-id="f0e7b-132">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="f0e7b-132">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f0e7b-133">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="f0e7b-133">Child Elements</span></span>  
 <span data-ttu-id="f0e7b-134">Nessuno</span><span class="sxs-lookup"><span data-stu-id="f0e7b-134">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f0e7b-135">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="f0e7b-135">Parent Elements</span></span>  
  
|<span data-ttu-id="f0e7b-136">Elemento</span><span class="sxs-lookup"><span data-stu-id="f0e7b-136">Element</span></span>|<span data-ttu-id="f0e7b-137">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f0e7b-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f0e7b-138">\<elemento serviceCertificate ></span><span class="sxs-lookup"><span data-stu-id="f0e7b-138">\<serviceCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/servicecertificate.md)|<span data-ttu-id="f0e7b-139">Consente di configurare il certificato utilizzato per crittografare e decrittografare i token.</span><span class="sxs-lookup"><span data-stu-id="f0e7b-139">Configures the certificate that is used to encrypt and decrypt tokens.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f0e7b-140">Note</span><span class="sxs-lookup"><span data-stu-id="f0e7b-140">Remarks</span></span>  
 <span data-ttu-id="f0e7b-141">Il `<certificateReference>` elemento specifica impostazioni che consentono di trovare e convalidare un certificato x. 509 nell'archivio certificati.</span><span class="sxs-lookup"><span data-stu-id="f0e7b-141">The `<certificateReference>` element specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span> <span data-ttu-id="f0e7b-142">Quando viene specificato come elemento figlio del `<serviceCertficate>` elemento, specifica la posizione e verifica le impostazioni del certificato x. 509 utilizzato per crittografare e decrittografare i token.</span><span class="sxs-lookup"><span data-stu-id="f0e7b-142">When it is specified as the child element of the `<serviceCertficate>` element, it specifies the location and verification settings of the X.509 certificate that is used to encrypt and decrypt tokens.</span></span> <span data-ttu-id="f0e7b-143">Il `<certificateReference>` elemento è rappresentato dalla <xref:System.ServiceModel.Configuration.CertificateReferenceElement> classe.</span><span class="sxs-lookup"><span data-stu-id="f0e7b-143">The `<certificateReference>` element is represented by the <xref:System.ServiceModel.Configuration.CertificateReferenceElement> class.</span></span>

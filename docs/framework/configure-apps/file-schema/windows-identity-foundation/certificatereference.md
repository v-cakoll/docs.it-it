---
title: <certificateReference>
ms.date: 03/30/2017
ms.assetid: 2ac8bc14-e9f1-48fb-b662-f5991558fbe4
author: BrucePerlerMS
ms.openlocfilehash: 6c9c77f96ff6032de43d9b5a257bc0796a19b858
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55269341"
---
# <a name="certificatereference"></a><span data-ttu-id="46f57-101">\<certificateReference></span><span class="sxs-lookup"><span data-stu-id="46f57-101">\<certificateReference></span></span>
<span data-ttu-id="46f57-102">Specifica le impostazioni che consentono di trovare e convalidare un certificato X.509 in un archivio certificati.</span><span class="sxs-lookup"><span data-stu-id="46f57-102">Specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span>  
  
 <span data-ttu-id="46f57-103">\<system.identityModel.services></span><span class="sxs-lookup"><span data-stu-id="46f57-103">\<system.identityModel.services></span></span>  
<span data-ttu-id="46f57-104">\<federationConfiguration></span><span class="sxs-lookup"><span data-stu-id="46f57-104">\<federationConfiguration></span></span>  
<span data-ttu-id="46f57-105">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="46f57-105">\<serviceCertificate></span></span>  
<span data-ttu-id="46f57-106">\<certificateReference></span><span class="sxs-lookup"><span data-stu-id="46f57-106">\<certificateReference></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46f57-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="46f57-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="46f57-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="46f57-108">Attributes and Elements</span></span>  
 <span data-ttu-id="46f57-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="46f57-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="46f57-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="46f57-110">Attributes</span></span>  
  
|<span data-ttu-id="46f57-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="46f57-111">Attribute</span></span>|<span data-ttu-id="46f57-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="46f57-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="46f57-113">storeName</span><span class="sxs-lookup"><span data-stu-id="46f57-113">storeName</span></span>|<span data-ttu-id="46f57-114">Il nome dell'archivio certificati X.509.</span><span class="sxs-lookup"><span data-stu-id="46f57-114">The name of the X.509 certificate store.</span></span> <span data-ttu-id="46f57-115">Il valore predefinito è "My".</span><span class="sxs-lookup"><span data-stu-id="46f57-115">The default is "My".</span></span> <span data-ttu-id="46f57-116">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="46f57-116">Optional.</span></span>|  
|<span data-ttu-id="46f57-117">storeLocation</span><span class="sxs-lookup"><span data-stu-id="46f57-117">storeLocation</span></span>|<span data-ttu-id="46f57-118">Oggetto <xref:System.Security.Cryptography.X509Certificates.StoreLocation> valore che specifica il percorso dell'archivio certificati X.509.</span><span class="sxs-lookup"><span data-stu-id="46f57-118">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the location of the X.509 certificate store.</span></span> <span data-ttu-id="46f57-119">Il valore predefinito è "LocalMachine".</span><span class="sxs-lookup"><span data-stu-id="46f57-119">The default value is "LocalMachine".</span></span> <span data-ttu-id="46f57-120">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="46f57-120">Optional.</span></span>|  
|<span data-ttu-id="46f57-121">x509FindType</span><span class="sxs-lookup"><span data-stu-id="46f57-121">x509FindType</span></span>|<span data-ttu-id="46f57-122">Un <xref:System.Security.Cryptography.X509Certificates.X509FindType> valore che specifica il tipo di ricerca che deve essere eseguito.</span><span class="sxs-lookup"><span data-stu-id="46f57-122">An <xref:System.Security.Cryptography.X509Certificates.X509FindType> value that specifies the type of search that is to be executed.</span></span> <span data-ttu-id="46f57-123">Il valore predefinito è "FindBySubjectDistinguishedName".</span><span class="sxs-lookup"><span data-stu-id="46f57-123">The default is "FindBySubjectDistinguishedName".</span></span> <span data-ttu-id="46f57-124">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="46f57-124">Optional.</span></span>|  
|<span data-ttu-id="46f57-125">findValue</span><span class="sxs-lookup"><span data-stu-id="46f57-125">findValue</span></span>|<span data-ttu-id="46f57-126">Valore da cercare nell'archivio certificati X.509.</span><span class="sxs-lookup"><span data-stu-id="46f57-126">The value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="46f57-127">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="46f57-127">Optional.</span></span>|  
|<span data-ttu-id="46f57-128">isChainIncluded</span><span class="sxs-lookup"><span data-stu-id="46f57-128">isChainIncluded</span></span>|<span data-ttu-id="46f57-129">Specifica se la convalida deve essere eseguita usando la catena di certificati.</span><span class="sxs-lookup"><span data-stu-id="46f57-129">Specifies whether validation should be performed by using the certificate chain.</span></span> <span data-ttu-id="46f57-130">Il valore predefinito è "true". la convalida viene eseguita usando la catena di certificati.</span><span class="sxs-lookup"><span data-stu-id="46f57-130">The default is "true"; validation is performed by using the certificate chain.</span></span> <span data-ttu-id="46f57-131">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="46f57-131">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="46f57-132">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="46f57-132">Child Elements</span></span>  
 <span data-ttu-id="46f57-133">nessuno</span><span class="sxs-lookup"><span data-stu-id="46f57-133">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="46f57-134">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="46f57-134">Parent Elements</span></span>  
  
|<span data-ttu-id="46f57-135">Elemento</span><span class="sxs-lookup"><span data-stu-id="46f57-135">Element</span></span>|<span data-ttu-id="46f57-136">Descrizione</span><span class="sxs-lookup"><span data-stu-id="46f57-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="46f57-137">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="46f57-137">\<serviceCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/servicecertificate.md)|<span data-ttu-id="46f57-138">Configura il certificato utilizzato per crittografare e decrittografare i token.</span><span class="sxs-lookup"><span data-stu-id="46f57-138">Configures the certificate that is used to encrypt and decrypt tokens.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="46f57-139">Note</span><span class="sxs-lookup"><span data-stu-id="46f57-139">Remarks</span></span>  
 <span data-ttu-id="46f57-140">Il `<certificateReference>` elemento specifica le impostazioni che vengono usate per trovare e convalidare un certificato X.509 in un archivio certificati.</span><span class="sxs-lookup"><span data-stu-id="46f57-140">The `<certificateReference>` element specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span> <span data-ttu-id="46f57-141">Quando viene specificato come elemento figlio del `<serviceCertficate>` elemento, specifica la posizione e verifica le impostazioni del certificato X.509 utilizzato per crittografare e decrittografare i token.</span><span class="sxs-lookup"><span data-stu-id="46f57-141">When it is specified as the child element of the `<serviceCertficate>` element, it specifies the location and verification settings of the X.509 certificate that is used to encrypt and decrypt tokens.</span></span> <span data-ttu-id="46f57-142">Il `<certificateReference>` elemento è rappresentato dal <xref:System.ServiceModel.Configuration.CertificateReferenceElement> classe.</span><span class="sxs-lookup"><span data-stu-id="46f57-142">The `<certificateReference>` element is represented by the <xref:System.ServiceModel.Configuration.CertificateReferenceElement> class.</span></span>

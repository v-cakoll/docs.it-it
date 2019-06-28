---
title: <certificateReference>
ms.date: 03/30/2017
ms.assetid: 2ac8bc14-e9f1-48fb-b662-f5991558fbe4
author: BrucePerlerMS
ms.openlocfilehash: c7dc9cfff15e70eff0086cfd98a19f3360ab8bb0
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/28/2019
ms.locfileid: "67423033"
---
# <a name="certificatereference"></a><span data-ttu-id="4e078-101">\<certificateReference></span><span class="sxs-lookup"><span data-stu-id="4e078-101">\<certificateReference></span></span>
<span data-ttu-id="4e078-102">Specifica le impostazioni che consentono di trovare e convalidare un certificato X.509 in un archivio certificati.</span><span class="sxs-lookup"><span data-stu-id="4e078-102">Specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span>  
  
 <span data-ttu-id="4e078-103">\<system.identityModel.services></span><span class="sxs-lookup"><span data-stu-id="4e078-103">\<system.identityModel.services></span></span>  
<span data-ttu-id="4e078-104">\<federationConfiguration></span><span class="sxs-lookup"><span data-stu-id="4e078-104">\<federationConfiguration></span></span>  
<span data-ttu-id="4e078-105">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="4e078-105">\<serviceCertificate></span></span>  
<span data-ttu-id="4e078-106">\<certificateReference></span><span class="sxs-lookup"><span data-stu-id="4e078-106">\<certificateReference></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e078-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4e078-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4e078-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="4e078-108">Attributes and Elements</span></span>  
 <span data-ttu-id="4e078-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="4e078-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4e078-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="4e078-110">Attributes</span></span>  
  
|<span data-ttu-id="4e078-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="4e078-111">Attribute</span></span>|<span data-ttu-id="4e078-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4e078-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4e078-113">storeName</span><span class="sxs-lookup"><span data-stu-id="4e078-113">storeName</span></span>|<span data-ttu-id="4e078-114">Il nome dell'archivio certificati X.509.</span><span class="sxs-lookup"><span data-stu-id="4e078-114">The name of the X.509 certificate store.</span></span> <span data-ttu-id="4e078-115">Il valore predefinito è "My".</span><span class="sxs-lookup"><span data-stu-id="4e078-115">The default is "My".</span></span> <span data-ttu-id="4e078-116">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="4e078-116">Optional.</span></span>|  
|<span data-ttu-id="4e078-117">storeLocation</span><span class="sxs-lookup"><span data-stu-id="4e078-117">storeLocation</span></span>|<span data-ttu-id="4e078-118">Oggetto <xref:System.Security.Cryptography.X509Certificates.StoreLocation> valore che specifica il percorso dell'archivio certificati X.509.</span><span class="sxs-lookup"><span data-stu-id="4e078-118">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the location of the X.509 certificate store.</span></span> <span data-ttu-id="4e078-119">Il valore predefinito è "LocalMachine".</span><span class="sxs-lookup"><span data-stu-id="4e078-119">The default value is "LocalMachine".</span></span> <span data-ttu-id="4e078-120">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="4e078-120">Optional.</span></span>|  
|<span data-ttu-id="4e078-121">x509FindType</span><span class="sxs-lookup"><span data-stu-id="4e078-121">x509FindType</span></span>|<span data-ttu-id="4e078-122">Un <xref:System.Security.Cryptography.X509Certificates.X509FindType> valore che specifica il tipo di ricerca che deve essere eseguito.</span><span class="sxs-lookup"><span data-stu-id="4e078-122">An <xref:System.Security.Cryptography.X509Certificates.X509FindType> value that specifies the type of search that is to be executed.</span></span> <span data-ttu-id="4e078-123">Il valore predefinito è "FindBySubjectDistinguishedName".</span><span class="sxs-lookup"><span data-stu-id="4e078-123">The default is "FindBySubjectDistinguishedName".</span></span> <span data-ttu-id="4e078-124">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="4e078-124">Optional.</span></span>|  
|<span data-ttu-id="4e078-125">findValue</span><span class="sxs-lookup"><span data-stu-id="4e078-125">findValue</span></span>|<span data-ttu-id="4e078-126">Valore da cercare nell'archivio certificati X.509.</span><span class="sxs-lookup"><span data-stu-id="4e078-126">The value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="4e078-127">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="4e078-127">Optional.</span></span>|  
|<span data-ttu-id="4e078-128">isChainIncluded</span><span class="sxs-lookup"><span data-stu-id="4e078-128">isChainIncluded</span></span>|<span data-ttu-id="4e078-129">Specifica se la convalida deve essere eseguita usando la catena di certificati.</span><span class="sxs-lookup"><span data-stu-id="4e078-129">Specifies whether validation should be performed by using the certificate chain.</span></span> <span data-ttu-id="4e078-130">Il valore predefinito è "true". la convalida viene eseguita usando la catena di certificati.</span><span class="sxs-lookup"><span data-stu-id="4e078-130">The default is "true"; validation is performed by using the certificate chain.</span></span> <span data-ttu-id="4e078-131">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="4e078-131">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4e078-132">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="4e078-132">Child Elements</span></span>  
 <span data-ttu-id="4e078-133">nessuno</span><span class="sxs-lookup"><span data-stu-id="4e078-133">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4e078-134">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="4e078-134">Parent Elements</span></span>  
  
|<span data-ttu-id="4e078-135">Elemento</span><span class="sxs-lookup"><span data-stu-id="4e078-135">Element</span></span>|<span data-ttu-id="4e078-136">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4e078-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4e078-137">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="4e078-137">\<serviceCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/servicecertificate.md)|<span data-ttu-id="4e078-138">Configura il certificato utilizzato per crittografare e decrittografare i token.</span><span class="sxs-lookup"><span data-stu-id="4e078-138">Configures the certificate that is used to encrypt and decrypt tokens.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4e078-139">Note</span><span class="sxs-lookup"><span data-stu-id="4e078-139">Remarks</span></span>  
 <span data-ttu-id="4e078-140">Il `<certificateReference>` elemento specifica le impostazioni che vengono usate per trovare e convalidare un certificato X.509 in un archivio certificati.</span><span class="sxs-lookup"><span data-stu-id="4e078-140">The `<certificateReference>` element specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span> <span data-ttu-id="4e078-141">Quando viene specificato come elemento figlio del `<serviceCertificate>` elemento, specifica la posizione e verifica le impostazioni del certificato X.509 utilizzato per crittografare e decrittografare i token.</span><span class="sxs-lookup"><span data-stu-id="4e078-141">When it is specified as the child element of the `<serviceCertificate>` element, it specifies the location and verification settings of the X.509 certificate that is used to encrypt and decrypt tokens.</span></span> <span data-ttu-id="4e078-142">Il `<certificateReference>` elemento è rappresentato dal <xref:System.ServiceModel.Configuration.CertificateReferenceElement> classe.</span><span class="sxs-lookup"><span data-stu-id="4e078-142">The `<certificateReference>` element is represented by the <xref:System.ServiceModel.Configuration.CertificateReferenceElement> class.</span></span>

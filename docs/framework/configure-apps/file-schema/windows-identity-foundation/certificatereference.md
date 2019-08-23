---
title: <certificateReference>
ms.date: 03/30/2017
ms.assetid: 2ac8bc14-e9f1-48fb-b662-f5991558fbe4
author: BrucePerlerMS
ms.openlocfilehash: da8ea128466457409334cd0b4ee3246a923f969a
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69941924"
---
# <a name="certificatereference"></a><span data-ttu-id="31c58-101">\<certificateReference></span><span class="sxs-lookup"><span data-stu-id="31c58-101">\<certificateReference></span></span>
<span data-ttu-id="31c58-102">Specifica le impostazioni utilizzate per individuare e convalidare un certificato X. 509 in un archivio certificati.</span><span class="sxs-lookup"><span data-stu-id="31c58-102">Specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span>  
  
 <span data-ttu-id="31c58-103">\<system.identityModel.services></span><span class="sxs-lookup"><span data-stu-id="31c58-103">\<system.identityModel.services></span></span>  
<span data-ttu-id="31c58-104">\<federationConfiguration></span><span class="sxs-lookup"><span data-stu-id="31c58-104">\<federationConfiguration></span></span>  
<span data-ttu-id="31c58-105">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="31c58-105">\<serviceCertificate></span></span>  
<span data-ttu-id="31c58-106">\<certificateReference></span><span class="sxs-lookup"><span data-stu-id="31c58-106">\<certificateReference></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="31c58-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="31c58-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="31c58-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="31c58-108">Attributes and Elements</span></span>  
 <span data-ttu-id="31c58-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="31c58-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="31c58-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="31c58-110">Attributes</span></span>  
  
|<span data-ttu-id="31c58-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="31c58-111">Attribute</span></span>|<span data-ttu-id="31c58-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="31c58-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="31c58-113">storeName</span><span class="sxs-lookup"><span data-stu-id="31c58-113">storeName</span></span>|<span data-ttu-id="31c58-114">Nome dell'archivio certificati X. 509.</span><span class="sxs-lookup"><span data-stu-id="31c58-114">The name of the X.509 certificate store.</span></span> <span data-ttu-id="31c58-115">Il valore predefinito è "My".</span><span class="sxs-lookup"><span data-stu-id="31c58-115">The default is "My".</span></span> <span data-ttu-id="31c58-116">facoltativo.</span><span class="sxs-lookup"><span data-stu-id="31c58-116">Optional.</span></span>|  
|<span data-ttu-id="31c58-117">storeLocation</span><span class="sxs-lookup"><span data-stu-id="31c58-117">storeLocation</span></span>|<span data-ttu-id="31c58-118"><xref:System.Security.Cryptography.X509Certificates.StoreLocation> Valore che specifica la posizione dell'archivio certificati X. 509.</span><span class="sxs-lookup"><span data-stu-id="31c58-118">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the location of the X.509 certificate store.</span></span> <span data-ttu-id="31c58-119">Il valore predefinito è "LocalMachine".</span><span class="sxs-lookup"><span data-stu-id="31c58-119">The default value is "LocalMachine".</span></span> <span data-ttu-id="31c58-120">facoltativo.</span><span class="sxs-lookup"><span data-stu-id="31c58-120">Optional.</span></span>|  
|<span data-ttu-id="31c58-121">x509FindType</span><span class="sxs-lookup"><span data-stu-id="31c58-121">x509FindType</span></span>|<span data-ttu-id="31c58-122"><xref:System.Security.Cryptography.X509Certificates.X509FindType> Valore che specifica il tipo di ricerca da eseguire.</span><span class="sxs-lookup"><span data-stu-id="31c58-122">An <xref:System.Security.Cryptography.X509Certificates.X509FindType> value that specifies the type of search that is to be executed.</span></span> <span data-ttu-id="31c58-123">Il valore predefinito è "FindBySubjectDistinguishedName".</span><span class="sxs-lookup"><span data-stu-id="31c58-123">The default is "FindBySubjectDistinguishedName".</span></span> <span data-ttu-id="31c58-124">facoltativo.</span><span class="sxs-lookup"><span data-stu-id="31c58-124">Optional.</span></span>|  
|<span data-ttu-id="31c58-125">findValue</span><span class="sxs-lookup"><span data-stu-id="31c58-125">findValue</span></span>|<span data-ttu-id="31c58-126">Valore da cercare nell'archivio certificati X.509.</span><span class="sxs-lookup"><span data-stu-id="31c58-126">The value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="31c58-127">facoltativo.</span><span class="sxs-lookup"><span data-stu-id="31c58-127">Optional.</span></span>|  
|<span data-ttu-id="31c58-128">isChainIncluded</span><span class="sxs-lookup"><span data-stu-id="31c58-128">isChainIncluded</span></span>|<span data-ttu-id="31c58-129">Specifica se la convalida deve essere eseguita utilizzando la catena di certificati.</span><span class="sxs-lookup"><span data-stu-id="31c58-129">Specifies whether validation should be performed by using the certificate chain.</span></span> <span data-ttu-id="31c58-130">Il valore predefinito è "true"; la convalida viene eseguita tramite la catena di certificati.</span><span class="sxs-lookup"><span data-stu-id="31c58-130">The default is "true"; validation is performed by using the certificate chain.</span></span> <span data-ttu-id="31c58-131">facoltativo.</span><span class="sxs-lookup"><span data-stu-id="31c58-131">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="31c58-132">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="31c58-132">Child Elements</span></span>  
 <span data-ttu-id="31c58-133">Nessuna</span><span class="sxs-lookup"><span data-stu-id="31c58-133">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="31c58-134">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="31c58-134">Parent Elements</span></span>  
  
|<span data-ttu-id="31c58-135">Elemento</span><span class="sxs-lookup"><span data-stu-id="31c58-135">Element</span></span>|<span data-ttu-id="31c58-136">Descrizione</span><span class="sxs-lookup"><span data-stu-id="31c58-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="31c58-137">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="31c58-137">\<serviceCertificate></span></span>](servicecertificate.md)|<span data-ttu-id="31c58-138">Configura il certificato usato per crittografare e decrittografare i token.</span><span class="sxs-lookup"><span data-stu-id="31c58-138">Configures the certificate that is used to encrypt and decrypt tokens.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="31c58-139">Note</span><span class="sxs-lookup"><span data-stu-id="31c58-139">Remarks</span></span>  
 <span data-ttu-id="31c58-140">L' `<certificateReference>` elemento specifica le impostazioni utilizzate per individuare e convalidare un certificato X. 509 in un archivio certificati.</span><span class="sxs-lookup"><span data-stu-id="31c58-140">The `<certificateReference>` element specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span> <span data-ttu-id="31c58-141">Quando viene specificato come elemento figlio dell' `<serviceCertificate>` elemento, specifica il percorso e le impostazioni di verifica del certificato X. 509 usato per crittografare e decrittografare i token.</span><span class="sxs-lookup"><span data-stu-id="31c58-141">When it is specified as the child element of the `<serviceCertificate>` element, it specifies the location and verification settings of the X.509 certificate that is used to encrypt and decrypt tokens.</span></span> <span data-ttu-id="31c58-142">L' `<certificateReference>` elemento è rappresentato <xref:System.ServiceModel.Configuration.CertificateReferenceElement> dalla classe.</span><span class="sxs-lookup"><span data-stu-id="31c58-142">The `<certificateReference>` element is represented by the <xref:System.ServiceModel.Configuration.CertificateReferenceElement> class.</span></span>

---
title: <certificateReference>
ms.date: 03/30/2017
ms.assetid: 2ac8bc14-e9f1-48fb-b662-f5991558fbe4
author: BrucePerlerMS
ms.openlocfilehash: 47d432a84d070476ddffd9b98a4ba46d8163bdc3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152814"
---
# <a name="certificatereference"></a><span data-ttu-id="f9b0a-101">\<> di riferimento</span><span class="sxs-lookup"><span data-stu-id="f9b0a-101">\<certificateReference></span></span>
<span data-ttu-id="f9b0a-102">Specifica le impostazioni utilizzate per trovare e convalidare un certificato X.509 in un archivio certificati.</span><span class="sxs-lookup"><span data-stu-id="f9b0a-102">Specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span>  
  
<span data-ttu-id="f9b0a-103">[**\<>di configurazione**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="f9b0a-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="f9b0a-104">&nbsp;&nbsp;[**\<system.identityModel.services>**](system-identitymodel-services.md)</span><span class="sxs-lookup"><span data-stu-id="f9b0a-104">&nbsp;&nbsp;[**\<system.identityModel.services>**](system-identitymodel-services.md)</span></span>\
<span data-ttu-id="f9b0a-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<>di configurazione**](federationconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="f9b0a-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<federationConfiguration>**](federationconfiguration.md)</span></span>\
<span data-ttu-id="f9b0a-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<>serviceCertificate**](servicecertificate.md)</span><span class="sxs-lookup"><span data-stu-id="f9b0a-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCertificate>**](servicecertificate.md)</span></span>\
<span data-ttu-id="f9b0a-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<>di riferimento**</span><span class="sxs-lookup"><span data-stu-id="f9b0a-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<certificateReference>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f9b0a-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f9b0a-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f9b0a-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="f9b0a-109">Attributes and Elements</span></span>  
 <span data-ttu-id="f9b0a-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="f9b0a-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f9b0a-111">Attributes</span><span class="sxs-lookup"><span data-stu-id="f9b0a-111">Attributes</span></span>  
  
|<span data-ttu-id="f9b0a-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="f9b0a-112">Attribute</span></span>|<span data-ttu-id="f9b0a-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f9b0a-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f9b0a-114">storeName</span><span class="sxs-lookup"><span data-stu-id="f9b0a-114">storeName</span></span>|<span data-ttu-id="f9b0a-115">Nome dell'archivio certificati X.509.</span><span class="sxs-lookup"><span data-stu-id="f9b0a-115">The name of the X.509 certificate store.</span></span> <span data-ttu-id="f9b0a-116">Il valore predefinito è "My".</span><span class="sxs-lookup"><span data-stu-id="f9b0a-116">The default is "My".</span></span> <span data-ttu-id="f9b0a-117">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="f9b0a-117">Optional.</span></span>|  
|<span data-ttu-id="f9b0a-118">storeLocation</span><span class="sxs-lookup"><span data-stu-id="f9b0a-118">storeLocation</span></span>|<span data-ttu-id="f9b0a-119">Valore <xref:System.Security.Cryptography.X509Certificates.StoreLocation> che specifica il percorso dell'archivio certificati X.509.</span><span class="sxs-lookup"><span data-stu-id="f9b0a-119">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the location of the X.509 certificate store.</span></span> <span data-ttu-id="f9b0a-120">Il valore predefinito è "LocalMachine".</span><span class="sxs-lookup"><span data-stu-id="f9b0a-120">The default value is "LocalMachine".</span></span> <span data-ttu-id="f9b0a-121">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="f9b0a-121">Optional.</span></span>|  
|<span data-ttu-id="f9b0a-122">x509FindType</span><span class="sxs-lookup"><span data-stu-id="f9b0a-122">x509FindType</span></span>|<span data-ttu-id="f9b0a-123">Valore <xref:System.Security.Cryptography.X509Certificates.X509FindType> che specifica il tipo di ricerca da eseguire.</span><span class="sxs-lookup"><span data-stu-id="f9b0a-123">An <xref:System.Security.Cryptography.X509Certificates.X509FindType> value that specifies the type of search that is to be executed.</span></span> <span data-ttu-id="f9b0a-124">Il valore predefinito è "FindBySubjectDistinguishedName".</span><span class="sxs-lookup"><span data-stu-id="f9b0a-124">The default is "FindBySubjectDistinguishedName".</span></span> <span data-ttu-id="f9b0a-125">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="f9b0a-125">Optional.</span></span>|  
|<span data-ttu-id="f9b0a-126">findValue</span><span class="sxs-lookup"><span data-stu-id="f9b0a-126">findValue</span></span>|<span data-ttu-id="f9b0a-127">Valore da cercare nell'archivio certificati X.509.</span><span class="sxs-lookup"><span data-stu-id="f9b0a-127">The value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="f9b0a-128">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="f9b0a-128">Optional.</span></span>|  
|<span data-ttu-id="f9b0a-129">isChainIncluded</span><span class="sxs-lookup"><span data-stu-id="f9b0a-129">isChainIncluded</span></span>|<span data-ttu-id="f9b0a-130">Specifica se la convalida deve essere eseguita utilizzando la catena di certificati.</span><span class="sxs-lookup"><span data-stu-id="f9b0a-130">Specifies whether validation should be performed by using the certificate chain.</span></span> <span data-ttu-id="f9b0a-131">Il valore predefinito è "true"; la convalida viene eseguita utilizzando la catena di certificati.</span><span class="sxs-lookup"><span data-stu-id="f9b0a-131">The default is "true"; validation is performed by using the certificate chain.</span></span> <span data-ttu-id="f9b0a-132">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="f9b0a-132">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f9b0a-133">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="f9b0a-133">Child Elements</span></span>  
 <span data-ttu-id="f9b0a-134">nessuno</span><span class="sxs-lookup"><span data-stu-id="f9b0a-134">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f9b0a-135">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="f9b0a-135">Parent Elements</span></span>  
  
|<span data-ttu-id="f9b0a-136">Elemento</span><span class="sxs-lookup"><span data-stu-id="f9b0a-136">Element</span></span>|<span data-ttu-id="f9b0a-137">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f9b0a-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f9b0a-138">\<>serviceCertificate</span><span class="sxs-lookup"><span data-stu-id="f9b0a-138">\<serviceCertificate></span></span>](servicecertificate.md)|<span data-ttu-id="f9b0a-139">Configura il certificato utilizzato per crittografare e decrittografare i token.</span><span class="sxs-lookup"><span data-stu-id="f9b0a-139">Configures the certificate that is used to encrypt and decrypt tokens.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f9b0a-140">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="f9b0a-140">Remarks</span></span>  
 <span data-ttu-id="f9b0a-141">L'elemento `<certificateReference>` specifica le impostazioni utilizzate per trovare e convalidare un certificato X.509 in un archivio certificati.</span><span class="sxs-lookup"><span data-stu-id="f9b0a-141">The `<certificateReference>` element specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span> <span data-ttu-id="f9b0a-142">Quando viene specificato come elemento `<serviceCertificate>` figlio dell'elemento, specifica il percorso e le impostazioni di verifica del certificato X.509 utilizzato per crittografare e decrittografare i token.</span><span class="sxs-lookup"><span data-stu-id="f9b0a-142">When it is specified as the child element of the `<serviceCertificate>` element, it specifies the location and verification settings of the X.509 certificate that is used to encrypt and decrypt tokens.</span></span> <span data-ttu-id="f9b0a-143">L'elemento `<certificateReference>` è <xref:System.ServiceModel.Configuration.CertificateReferenceElement> rappresentato dalla classe .</span><span class="sxs-lookup"><span data-stu-id="f9b0a-143">The `<certificateReference>` element is represented by the <xref:System.ServiceModel.Configuration.CertificateReferenceElement> class.</span></span>

---
title: <certificateReference>
ms.date: 03/30/2017
ms.assetid: 2ac8bc14-e9f1-48fb-b662-f5991558fbe4
author: BrucePerlerMS
ms.openlocfilehash: 782ca3344774b8412a18e3cf13bff5f969751ea3
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252149"
---
# <a name="certificatereference"></a><span data-ttu-id="40521-101">\<certificateReference></span><span class="sxs-lookup"><span data-stu-id="40521-101">\<certificateReference></span></span>
<span data-ttu-id="40521-102">Specifica le impostazioni utilizzate per individuare e convalidare un certificato X. 509 in un archivio certificati.</span><span class="sxs-lookup"><span data-stu-id="40521-102">Specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span>  
  
<span data-ttu-id="40521-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="40521-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="40521-104">&nbsp;&nbsp;[ **\<System. identityModel. Services >** ](system-identitymodel-services.md)</span><span class="sxs-lookup"><span data-stu-id="40521-104">&nbsp;&nbsp;[**\<system.identityModel.services>**](system-identitymodel-services.md)</span></span>\
<span data-ttu-id="40521-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> federationConfiguration**](federationconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="40521-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<federationConfiguration>**](federationconfiguration.md)</span></span>\
<span data-ttu-id="40521-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> serviceCertificate**](servicecertificate.md)</span><span class="sxs-lookup"><span data-stu-id="40521-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCertificate>**](servicecertificate.md)</span></span>\
<span data-ttu-id="40521-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> certificateReference**</span><span class="sxs-lookup"><span data-stu-id="40521-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<certificateReference>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40521-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="40521-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="40521-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="40521-109">Attributes and Elements</span></span>  
 <span data-ttu-id="40521-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="40521-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="40521-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="40521-111">Attributes</span></span>  
  
|<span data-ttu-id="40521-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="40521-112">Attribute</span></span>|<span data-ttu-id="40521-113">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="40521-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="40521-114">storeName</span><span class="sxs-lookup"><span data-stu-id="40521-114">storeName</span></span>|<span data-ttu-id="40521-115">Nome dell'archivio certificati X. 509.</span><span class="sxs-lookup"><span data-stu-id="40521-115">The name of the X.509 certificate store.</span></span> <span data-ttu-id="40521-116">Il valore predefinito è "My".</span><span class="sxs-lookup"><span data-stu-id="40521-116">The default is "My".</span></span> <span data-ttu-id="40521-117">facoltativo.</span><span class="sxs-lookup"><span data-stu-id="40521-117">Optional.</span></span>|  
|<span data-ttu-id="40521-118">storeLocation</span><span class="sxs-lookup"><span data-stu-id="40521-118">storeLocation</span></span>|<span data-ttu-id="40521-119"><xref:System.Security.Cryptography.X509Certificates.StoreLocation> Valore che specifica la posizione dell'archivio certificati X. 509.</span><span class="sxs-lookup"><span data-stu-id="40521-119">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the location of the X.509 certificate store.</span></span> <span data-ttu-id="40521-120">Il valore predefinito è "LocalMachine".</span><span class="sxs-lookup"><span data-stu-id="40521-120">The default value is "LocalMachine".</span></span> <span data-ttu-id="40521-121">facoltativo.</span><span class="sxs-lookup"><span data-stu-id="40521-121">Optional.</span></span>|  
|<span data-ttu-id="40521-122">x509FindType</span><span class="sxs-lookup"><span data-stu-id="40521-122">x509FindType</span></span>|<span data-ttu-id="40521-123"><xref:System.Security.Cryptography.X509Certificates.X509FindType> Valore che specifica il tipo di ricerca da eseguire.</span><span class="sxs-lookup"><span data-stu-id="40521-123">An <xref:System.Security.Cryptography.X509Certificates.X509FindType> value that specifies the type of search that is to be executed.</span></span> <span data-ttu-id="40521-124">Il valore predefinito è "FindBySubjectDistinguishedName".</span><span class="sxs-lookup"><span data-stu-id="40521-124">The default is "FindBySubjectDistinguishedName".</span></span> <span data-ttu-id="40521-125">facoltativo.</span><span class="sxs-lookup"><span data-stu-id="40521-125">Optional.</span></span>|  
|<span data-ttu-id="40521-126">findValue</span><span class="sxs-lookup"><span data-stu-id="40521-126">findValue</span></span>|<span data-ttu-id="40521-127">Valore da cercare nell'archivio certificati X.509.</span><span class="sxs-lookup"><span data-stu-id="40521-127">The value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="40521-128">facoltativo.</span><span class="sxs-lookup"><span data-stu-id="40521-128">Optional.</span></span>|  
|<span data-ttu-id="40521-129">isChainIncluded</span><span class="sxs-lookup"><span data-stu-id="40521-129">isChainIncluded</span></span>|<span data-ttu-id="40521-130">Specifica se la convalida deve essere eseguita utilizzando la catena di certificati.</span><span class="sxs-lookup"><span data-stu-id="40521-130">Specifies whether validation should be performed by using the certificate chain.</span></span> <span data-ttu-id="40521-131">Il valore predefinito è "true"; la convalida viene eseguita tramite la catena di certificati.</span><span class="sxs-lookup"><span data-stu-id="40521-131">The default is "true"; validation is performed by using the certificate chain.</span></span> <span data-ttu-id="40521-132">facoltativo.</span><span class="sxs-lookup"><span data-stu-id="40521-132">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="40521-133">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="40521-133">Child Elements</span></span>  
 <span data-ttu-id="40521-134">Nessuna</span><span class="sxs-lookup"><span data-stu-id="40521-134">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="40521-135">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="40521-135">Parent Elements</span></span>  
  
|<span data-ttu-id="40521-136">Elemento</span><span class="sxs-lookup"><span data-stu-id="40521-136">Element</span></span>|<span data-ttu-id="40521-137">Descrizione</span><span class="sxs-lookup"><span data-stu-id="40521-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="40521-138">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="40521-138">\<serviceCertificate></span></span>](servicecertificate.md)|<span data-ttu-id="40521-139">Configura il certificato usato per crittografare e decrittografare i token.</span><span class="sxs-lookup"><span data-stu-id="40521-139">Configures the certificate that is used to encrypt and decrypt tokens.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="40521-140">Note</span><span class="sxs-lookup"><span data-stu-id="40521-140">Remarks</span></span>  
 <span data-ttu-id="40521-141">L' `<certificateReference>` elemento specifica le impostazioni utilizzate per individuare e convalidare un certificato X. 509 in un archivio certificati.</span><span class="sxs-lookup"><span data-stu-id="40521-141">The `<certificateReference>` element specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span> <span data-ttu-id="40521-142">Quando viene specificato come elemento figlio dell' `<serviceCertificate>` elemento, specifica il percorso e le impostazioni di verifica del certificato X. 509 usato per crittografare e decrittografare i token.</span><span class="sxs-lookup"><span data-stu-id="40521-142">When it is specified as the child element of the `<serviceCertificate>` element, it specifies the location and verification settings of the X.509 certificate that is used to encrypt and decrypt tokens.</span></span> <span data-ttu-id="40521-143">L' `<certificateReference>` elemento è rappresentato <xref:System.ServiceModel.Configuration.CertificateReferenceElement> dalla classe.</span><span class="sxs-lookup"><span data-stu-id="40521-143">The `<certificateReference>` element is represented by the <xref:System.ServiceModel.Configuration.CertificateReferenceElement> class.</span></span>

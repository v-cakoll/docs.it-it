---
title: <certificateReference>
ms.date: 03/30/2017
ms.assetid: 2ac8bc14-e9f1-48fb-b662-f5991558fbe4
author: BrucePerlerMS
ms.openlocfilehash: 47d432a84d070476ddffd9b98a4ba46d8163bdc3
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "79152814"
---
# \<certificateReference>
<span data-ttu-id="9ec49-101">Specifica le impostazioni utilizzate per individuare e convalidare un certificato X. 509 in un archivio certificati.</span><span class="sxs-lookup"><span data-stu-id="9ec49-101">Specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel.services>**](system-identitymodel-services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<federationConfiguration>**](federationconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCertificate>**](servicecertificate.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<certificateReference>**  
  
## <a name="syntax"></a><span data-ttu-id="9ec49-102">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9ec49-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9ec49-103">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="9ec49-103">Attributes and Elements</span></span>  
 <span data-ttu-id="9ec49-104">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="9ec49-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9ec49-105">Attributi</span><span class="sxs-lookup"><span data-stu-id="9ec49-105">Attributes</span></span>  
  
|<span data-ttu-id="9ec49-106">Attributo</span><span class="sxs-lookup"><span data-stu-id="9ec49-106">Attribute</span></span>|<span data-ttu-id="9ec49-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9ec49-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9ec49-108">storeName</span><span class="sxs-lookup"><span data-stu-id="9ec49-108">storeName</span></span>|<span data-ttu-id="9ec49-109">Nome dell'archivio certificati X.509.</span><span class="sxs-lookup"><span data-stu-id="9ec49-109">The name of the X.509 certificate store.</span></span> <span data-ttu-id="9ec49-110">Il valore predefinito è "My".</span><span class="sxs-lookup"><span data-stu-id="9ec49-110">The default is "My".</span></span> <span data-ttu-id="9ec49-111">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="9ec49-111">Optional.</span></span>|  
|<span data-ttu-id="9ec49-112">storeLocation</span><span class="sxs-lookup"><span data-stu-id="9ec49-112">storeLocation</span></span>|<span data-ttu-id="9ec49-113"><xref:System.Security.Cryptography.X509Certificates.StoreLocation>Valore che specifica la posizione dell'archivio certificati X. 509.</span><span class="sxs-lookup"><span data-stu-id="9ec49-113">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the location of the X.509 certificate store.</span></span> <span data-ttu-id="9ec49-114">Il valore predefinito è "LocalMachine".</span><span class="sxs-lookup"><span data-stu-id="9ec49-114">The default value is "LocalMachine".</span></span> <span data-ttu-id="9ec49-115">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="9ec49-115">Optional.</span></span>|  
|<span data-ttu-id="9ec49-116">x509FindType</span><span class="sxs-lookup"><span data-stu-id="9ec49-116">x509FindType</span></span>|<span data-ttu-id="9ec49-117"><xref:System.Security.Cryptography.X509Certificates.X509FindType>Valore che specifica il tipo di ricerca da eseguire.</span><span class="sxs-lookup"><span data-stu-id="9ec49-117">An <xref:System.Security.Cryptography.X509Certificates.X509FindType> value that specifies the type of search that is to be executed.</span></span> <span data-ttu-id="9ec49-118">Il valore predefinito è "FindBySubjectDistinguishedName".</span><span class="sxs-lookup"><span data-stu-id="9ec49-118">The default is "FindBySubjectDistinguishedName".</span></span> <span data-ttu-id="9ec49-119">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="9ec49-119">Optional.</span></span>|  
|<span data-ttu-id="9ec49-120">findValue</span><span class="sxs-lookup"><span data-stu-id="9ec49-120">findValue</span></span>|<span data-ttu-id="9ec49-121">Valore da cercare nell'archivio certificati X.509.</span><span class="sxs-lookup"><span data-stu-id="9ec49-121">The value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="9ec49-122">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="9ec49-122">Optional.</span></span>|  
|<span data-ttu-id="9ec49-123">isChainIncluded</span><span class="sxs-lookup"><span data-stu-id="9ec49-123">isChainIncluded</span></span>|<span data-ttu-id="9ec49-124">Specifica se la convalida deve essere eseguita utilizzando la catena di certificati.</span><span class="sxs-lookup"><span data-stu-id="9ec49-124">Specifies whether validation should be performed by using the certificate chain.</span></span> <span data-ttu-id="9ec49-125">Il valore predefinito è "true"; la convalida viene eseguita tramite la catena di certificati.</span><span class="sxs-lookup"><span data-stu-id="9ec49-125">The default is "true"; validation is performed by using the certificate chain.</span></span> <span data-ttu-id="9ec49-126">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="9ec49-126">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9ec49-127">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="9ec49-127">Child Elements</span></span>  
 <span data-ttu-id="9ec49-128">nessuno</span><span class="sxs-lookup"><span data-stu-id="9ec49-128">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9ec49-129">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="9ec49-129">Parent Elements</span></span>  
  
|<span data-ttu-id="9ec49-130">Elemento</span><span class="sxs-lookup"><span data-stu-id="9ec49-130">Element</span></span>|<span data-ttu-id="9ec49-131">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9ec49-131">Description</span></span>|  
|-------------|-----------------|  
|[\<serviceCertificate>](servicecertificate.md)|<span data-ttu-id="9ec49-132">Configura il certificato usato per crittografare e decrittografare i token.</span><span class="sxs-lookup"><span data-stu-id="9ec49-132">Configures the certificate that is used to encrypt and decrypt tokens.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9ec49-133">Commenti</span><span class="sxs-lookup"><span data-stu-id="9ec49-133">Remarks</span></span>  
 <span data-ttu-id="9ec49-134">L' `<certificateReference>` elemento specifica le impostazioni utilizzate per individuare e convalidare un certificato X. 509 in un archivio certificati.</span><span class="sxs-lookup"><span data-stu-id="9ec49-134">The `<certificateReference>` element specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span> <span data-ttu-id="9ec49-135">Quando viene specificato come elemento figlio dell' `<serviceCertificate>` elemento, specifica il percorso e le impostazioni di verifica del certificato X. 509 usato per crittografare e decrittografare i token.</span><span class="sxs-lookup"><span data-stu-id="9ec49-135">When it is specified as the child element of the `<serviceCertificate>` element, it specifies the location and verification settings of the X.509 certificate that is used to encrypt and decrypt tokens.</span></span> <span data-ttu-id="9ec49-136">L' `<certificateReference>` elemento è rappresentato dalla <xref:System.ServiceModel.Configuration.CertificateReferenceElement> classe.</span><span class="sxs-lookup"><span data-stu-id="9ec49-136">The `<certificateReference>` element is represented by the <xref:System.ServiceModel.Configuration.CertificateReferenceElement> class.</span></span>

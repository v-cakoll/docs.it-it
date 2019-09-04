---
title: <serviceCertificate>
ms.date: 03/30/2017
ms.assetid: 42c7f291-2ec3-43c5-8872-35897ff3c660
author: BrucePerlerMS
ms.openlocfilehash: 653dd9cfadbfd33f5371b77172199b946321bc8c
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251863"
---
# <a name="servicecertificate"></a><span data-ttu-id="2995d-101">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="2995d-101">\<serviceCertificate></span></span>
<span data-ttu-id="2995d-102">Configura il certificato X. 509 usato per crittografare e decrittografare i token.</span><span class="sxs-lookup"><span data-stu-id="2995d-102">Configures the X.509 certificate that is used to encrypt and decrypt tokens.</span></span>  
  
<span data-ttu-id="2995d-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="2995d-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="2995d-104">&nbsp;&nbsp;[ **\<System. identityModel. Services >** ](system-identitymodel-services.md)</span><span class="sxs-lookup"><span data-stu-id="2995d-104">&nbsp;&nbsp;[**\<system.identityModel.services>**](system-identitymodel-services.md)</span></span>\
<span data-ttu-id="2995d-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> federationConfiguration**](federationconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="2995d-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<federationConfiguration>**](federationconfiguration.md)</span></span>\
<span data-ttu-id="2995d-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> serviceCertificate**</span><span class="sxs-lookup"><span data-stu-id="2995d-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceCertificate>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2995d-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2995d-107">Syntax</span></span>  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration>  
    <serviceCertificate>  
    </serviceCertificate>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2995d-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="2995d-108">Attributes and Elements</span></span>  
 <span data-ttu-id="2995d-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="2995d-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2995d-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="2995d-110">Attributes</span></span>  
 <span data-ttu-id="2995d-111">Nessuna</span><span class="sxs-lookup"><span data-stu-id="2995d-111">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="2995d-112">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="2995d-112">Child Elements</span></span>  
  
|<span data-ttu-id="2995d-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="2995d-113">Element</span></span>|<span data-ttu-id="2995d-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2995d-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2995d-115">\<certificateReference></span><span class="sxs-lookup"><span data-stu-id="2995d-115">\<certificateReference></span></span>](certificatereference.md)|<span data-ttu-id="2995d-116">Specifica le impostazioni utilizzate per individuare e convalidare un certificato X. 509 in un archivio certificati.</span><span class="sxs-lookup"><span data-stu-id="2995d-116">Specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2995d-117">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="2995d-117">Parent Elements</span></span>  
  
|<span data-ttu-id="2995d-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="2995d-118">Element</span></span>|<span data-ttu-id="2995d-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2995d-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2995d-120">\<federationConfiguration></span><span class="sxs-lookup"><span data-stu-id="2995d-120">\<federationConfiguration></span></span>](federationconfiguration.md)|<span data-ttu-id="2995d-121">Contiene le impostazioni che configurano <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) <xref:System.IdentityModel.Services.SessionAuthenticationModule> e (Sam).</span><span class="sxs-lookup"><span data-stu-id="2995d-121">Contains the settings that configure the <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) and the <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM).</span></span>|  
  
## <a name="example"></a><span data-ttu-id="2995d-122">Esempio</span><span class="sxs-lookup"><span data-stu-id="2995d-122">Example</span></span>  
 <span data-ttu-id="2995d-123">Nel codice XML seguente viene illustrato l'utilizzo \<dell'elemento > serviceCertificate.</span><span class="sxs-lookup"><span data-stu-id="2995d-123">The following XML shows the use of the \<serviceCertificate> element.</span></span> <span data-ttu-id="2995d-124">Il codice XML viene tratto dall' `CustomToken` esempio.</span><span class="sxs-lookup"><span data-stu-id="2995d-124">The XML is taken from the `CustomToken` sample.</span></span>  
  
```xml  
<serviceCertificate>  
  <certificateReference x509FindType="FindBySubjectName" findValue="localhost" storeLocation="LocalMachine" storeName="My"/>  
</serviceCertificate>  
```

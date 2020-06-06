---
title: <serviceCertificate>
ms.date: 03/30/2017
ms.assetid: 42c7f291-2ec3-43c5-8872-35897ff3c660
author: BrucePerlerMS
ms.openlocfilehash: 653dd9cfadbfd33f5371b77172199b946321bc8c
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70251863"
---
# \<serviceCertificate>
<span data-ttu-id="c76d9-101">Configura il certificato X. 509 usato per crittografare e decrittografare i token.</span><span class="sxs-lookup"><span data-stu-id="c76d9-101">Configures the X.509 certificate that is used to encrypt and decrypt tokens.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel.services>**](system-identitymodel-services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<federationConfiguration>**](federationconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceCertificate>**  
  
## <a name="syntax"></a><span data-ttu-id="c76d9-102">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c76d9-102">Syntax</span></span>  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration>  
    <serviceCertificate>  
    </serviceCertificate>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c76d9-103">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="c76d9-103">Attributes and Elements</span></span>  
 <span data-ttu-id="c76d9-104">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="c76d9-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c76d9-105">Attributi</span><span class="sxs-lookup"><span data-stu-id="c76d9-105">Attributes</span></span>  
 <span data-ttu-id="c76d9-106">nessuno</span><span class="sxs-lookup"><span data-stu-id="c76d9-106">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="c76d9-107">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="c76d9-107">Child Elements</span></span>  
  
|<span data-ttu-id="c76d9-108">Elemento</span><span class="sxs-lookup"><span data-stu-id="c76d9-108">Element</span></span>|<span data-ttu-id="c76d9-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c76d9-109">Description</span></span>|  
|-------------|-----------------|  
|[\<certificateReference>](certificatereference.md)|<span data-ttu-id="c76d9-110">Specifica le impostazioni utilizzate per individuare e convalidare un certificato X. 509 in un archivio certificati.</span><span class="sxs-lookup"><span data-stu-id="c76d9-110">Specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c76d9-111">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="c76d9-111">Parent Elements</span></span>  
  
|<span data-ttu-id="c76d9-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="c76d9-112">Element</span></span>|<span data-ttu-id="c76d9-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c76d9-113">Description</span></span>|  
|-------------|-----------------|  
|[\<federationConfiguration>](federationconfiguration.md)|<span data-ttu-id="c76d9-114">Contiene le impostazioni che configurano <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) e <xref:System.IdentityModel.Services.SessionAuthenticationModule> (Sam).</span><span class="sxs-lookup"><span data-stu-id="c76d9-114">Contains the settings that configure the <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) and the <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM).</span></span>|  
  
## <a name="example"></a><span data-ttu-id="c76d9-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="c76d9-115">Example</span></span>  
 <span data-ttu-id="c76d9-116">Nel codice XML seguente viene illustrato l'utilizzo dell' \<serviceCertificate> elemento.</span><span class="sxs-lookup"><span data-stu-id="c76d9-116">The following XML shows the use of the \<serviceCertificate> element.</span></span> <span data-ttu-id="c76d9-117">Il codice XML viene tratto dall' `CustomToken` esempio.</span><span class="sxs-lookup"><span data-stu-id="c76d9-117">The XML is taken from the `CustomToken` sample.</span></span>  
  
```xml  
<serviceCertificate>  
  <certificateReference x509FindType="FindBySubjectName" findValue="localhost" storeLocation="LocalMachine" storeName="My"/>  
</serviceCertificate>  
```

---
title: <serviceCertificate>
ms.date: 03/30/2017
ms.assetid: 42c7f291-2ec3-43c5-8872-35897ff3c660
author: BrucePerlerMS
ms.openlocfilehash: a3aba5618855f7225dc8a427516eaa72b45f6e8b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69942406"
---
# <a name="servicecertificate"></a><span data-ttu-id="14de5-101">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="14de5-101">\<serviceCertificate></span></span>
<span data-ttu-id="14de5-102">Configura il certificato X. 509 usato per crittografare e decrittografare i token.</span><span class="sxs-lookup"><span data-stu-id="14de5-102">Configures the X.509 certificate that is used to encrypt and decrypt tokens.</span></span>  
  
 <span data-ttu-id="14de5-103">\<system.identityModel.services></span><span class="sxs-lookup"><span data-stu-id="14de5-103">\<system.identityModel.services></span></span>  
<span data-ttu-id="14de5-104">\<federationConfiguration></span><span class="sxs-lookup"><span data-stu-id="14de5-104">\<federationConfiguration></span></span>  
<span data-ttu-id="14de5-105">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="14de5-105">\<serviceCertificate></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="14de5-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="14de5-106">Syntax</span></span>  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration>  
    <serviceCertificate>  
    </serviceCertificate>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="14de5-107">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="14de5-107">Attributes and Elements</span></span>  
 <span data-ttu-id="14de5-108">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="14de5-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="14de5-109">Attributi</span><span class="sxs-lookup"><span data-stu-id="14de5-109">Attributes</span></span>  
 <span data-ttu-id="14de5-110">Nessuna</span><span class="sxs-lookup"><span data-stu-id="14de5-110">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="14de5-111">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="14de5-111">Child Elements</span></span>  
  
|<span data-ttu-id="14de5-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="14de5-112">Element</span></span>|<span data-ttu-id="14de5-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="14de5-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="14de5-114">\<certificateReference></span><span class="sxs-lookup"><span data-stu-id="14de5-114">\<certificateReference></span></span>](certificatereference.md)|<span data-ttu-id="14de5-115">Specifica le impostazioni utilizzate per individuare e convalidare un certificato X. 509 in un archivio certificati.</span><span class="sxs-lookup"><span data-stu-id="14de5-115">Specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="14de5-116">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="14de5-116">Parent Elements</span></span>  
  
|<span data-ttu-id="14de5-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="14de5-117">Element</span></span>|<span data-ttu-id="14de5-118">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="14de5-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="14de5-119">\<federationConfiguration></span><span class="sxs-lookup"><span data-stu-id="14de5-119">\<federationConfiguration></span></span>](federationconfiguration.md)|<span data-ttu-id="14de5-120">Contiene le impostazioni che configurano <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) <xref:System.IdentityModel.Services.SessionAuthenticationModule> e (Sam).</span><span class="sxs-lookup"><span data-stu-id="14de5-120">Contains the settings that configure the <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) and the <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM).</span></span>|  
  
## <a name="example"></a><span data-ttu-id="14de5-121">Esempio</span><span class="sxs-lookup"><span data-stu-id="14de5-121">Example</span></span>  
 <span data-ttu-id="14de5-122">Nel codice XML seguente viene illustrato l'utilizzo \<dell'elemento > serviceCertificate.</span><span class="sxs-lookup"><span data-stu-id="14de5-122">The following XML shows the use of the \<serviceCertificate> element.</span></span> <span data-ttu-id="14de5-123">Il codice XML viene tratto dall' `CustomToken` esempio.</span><span class="sxs-lookup"><span data-stu-id="14de5-123">The XML is taken from the `CustomToken` sample.</span></span>  
  
```xml  
<serviceCertificate>  
  <certificateReference x509FindType="FindBySubjectName" findValue="localhost" storeLocation="LocalMachine" storeName="My"/>  
</serviceCertificate>  
```

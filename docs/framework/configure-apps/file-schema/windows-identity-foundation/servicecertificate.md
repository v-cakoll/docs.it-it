---
title: '&lt;elemento serviceCertificate&gt;'
ms.date: 03/30/2017
ms.assetid: 42c7f291-2ec3-43c5-8872-35897ff3c660
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: af59562dbf6c13970526f1665a9ba2c57c4f32ee
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
ms.locfileid: "32766777"
---
# <a name="ltservicecertificategt"></a><span data-ttu-id="39efa-102">&lt;elemento serviceCertificate&gt;</span><span class="sxs-lookup"><span data-stu-id="39efa-102">&lt;serviceCertificate&gt;</span></span>
<span data-ttu-id="39efa-103">Consente di configurare il certificato x. 509 utilizzato per crittografare e decrittografare i token.</span><span class="sxs-lookup"><span data-stu-id="39efa-103">Configures the X.509 certificate that is used to encrypt and decrypt tokens.</span></span>  
  
 <span data-ttu-id="39efa-104">\<IdentityModel ></span><span class="sxs-lookup"><span data-stu-id="39efa-104">\<system.identityModel.services></span></span>  
<span data-ttu-id="39efa-105">\<federationConfiguration ></span><span class="sxs-lookup"><span data-stu-id="39efa-105">\<federationConfiguration></span></span>  
<span data-ttu-id="39efa-106">\<elemento serviceCertificate ></span><span class="sxs-lookup"><span data-stu-id="39efa-106">\<serviceCertificate></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39efa-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="39efa-107">Syntax</span></span>  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration>  
    <serviceCertificate>  
    </serviceCertificate>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="39efa-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="39efa-108">Attributes and Elements</span></span>  
 <span data-ttu-id="39efa-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="39efa-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="39efa-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="39efa-110">Attributes</span></span>  
 <span data-ttu-id="39efa-111">Nessuno</span><span class="sxs-lookup"><span data-stu-id="39efa-111">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="39efa-112">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="39efa-112">Child Elements</span></span>  
  
|<span data-ttu-id="39efa-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="39efa-113">Element</span></span>|<span data-ttu-id="39efa-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="39efa-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="39efa-115">\<certificateReference ></span><span class="sxs-lookup"><span data-stu-id="39efa-115">\<certificateReference></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatereference.md)|<span data-ttu-id="39efa-116">Specifica le impostazioni che consentono di trovare e convalidare un certificato x. 509 nell'archivio certificati.</span><span class="sxs-lookup"><span data-stu-id="39efa-116">Specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="39efa-117">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="39efa-117">Parent Elements</span></span>  
  
|<span data-ttu-id="39efa-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="39efa-118">Element</span></span>|<span data-ttu-id="39efa-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="39efa-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="39efa-120">\<federationConfiguration></span><span class="sxs-lookup"><span data-stu-id="39efa-120">\<federationConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md)|<span data-ttu-id="39efa-121">Contiene le impostazioni che configurano il <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) e <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM).</span><span class="sxs-lookup"><span data-stu-id="39efa-121">Contains the settings that configure the <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) and the <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM).</span></span>|  
  
## <a name="example"></a><span data-ttu-id="39efa-122">Esempio</span><span class="sxs-lookup"><span data-stu-id="39efa-122">Example</span></span>  
 <span data-ttu-id="39efa-123">Il codice XML seguente viene illustrato come utilizzare il \<serviceCertificate > elemento.</span><span class="sxs-lookup"><span data-stu-id="39efa-123">The following XML shows the use of the \<serviceCertificate> element.</span></span> <span data-ttu-id="39efa-124">Il codice XML viene prelevato il `CustomToken` esempio.</span><span class="sxs-lookup"><span data-stu-id="39efa-124">The XML is taken from the `CustomToken` sample.</span></span>  
  
```xml  
<serviceCertificate>  
  <certificateReference x509FindType="FindBySubjectName" findValue="localhost" storeLocation="LocalMachine" storeName="My"/>  
</serviceCertificate>  
```

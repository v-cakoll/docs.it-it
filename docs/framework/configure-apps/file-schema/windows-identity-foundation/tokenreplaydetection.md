---
title: <tokenReplayDetection>
ms.date: 03/30/2017
ms.assetid: ac3f588e-5f75-4275-b969-2d492ecc3b47
author: BrucePerlerMS
ms.openlocfilehash: a4454042e1d97fb3cc2d6f2735104dadda6e7b5a
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251765"
---
# <a name="tokenreplaydetection"></a><span data-ttu-id="57f97-101">\<tokenReplayDetection></span><span class="sxs-lookup"><span data-stu-id="57f97-101">\<tokenReplayDetection></span></span>
<span data-ttu-id="57f97-102">Abilita il rilevamento della riproduzione dei token e specifica l'ora di scadenza per i token.</span><span class="sxs-lookup"><span data-stu-id="57f97-102">Enables token replay detection and specifies the expiration time for tokens.</span></span>  
  
<span data-ttu-id="57f97-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="57f97-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="57f97-104">&nbsp;&nbsp;[ **\<System. identityModel >** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="57f97-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="57f97-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> identityConfiguration**](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="57f97-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="57f97-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> tokenReplayDetection**</span><span class="sxs-lookup"><span data-stu-id="57f97-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<tokenReplayDetection>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="57f97-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="57f97-107">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <tokenReplayDetection enabled=xs:boolean expirationPeriod=TimeSpan>  
    </tokenReplayDetection>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="type"></a><span data-ttu-id="57f97-108">Type</span><span class="sxs-lookup"><span data-stu-id="57f97-108">Type</span></span>  
 <xref:System.IdentityModel.Configuration.TokenReplayDetectionElement>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="57f97-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="57f97-109">Attributes and Elements</span></span>  
 <span data-ttu-id="57f97-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="57f97-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="57f97-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="57f97-111">Attributes</span></span>  
  
|<span data-ttu-id="57f97-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="57f97-112">Attribute</span></span>|<span data-ttu-id="57f97-113">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="57f97-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="57f97-114">enabled</span><span class="sxs-lookup"><span data-stu-id="57f97-114">enabled</span></span>|<span data-ttu-id="57f97-115">Valore che specifica se il rilevamento della riproduzione del token è abilitato; "true" per abilitare il rilevamento della riproduzione del token.</span><span class="sxs-lookup"><span data-stu-id="57f97-115">A value that specifies whether token replay detection is enabled; "true" to enable token replay detection.</span></span>|  
|<span data-ttu-id="57f97-116">expirationPeriod</span><span class="sxs-lookup"><span data-stu-id="57f97-116">expirationPeriod</span></span>|<span data-ttu-id="57f97-117">Oggetto <xref:System.TimeSpan> che specifica l'intervallo di tempo massimo prima che un elemento venga considerato scaduto e rimosso dalla cache.</span><span class="sxs-lookup"><span data-stu-id="57f97-117">A <xref:System.TimeSpan> that specifies the maximum amount of time before an item is considered expired and removed from the cache.</span></span>  <span data-ttu-id="57f97-118">Per ulteriori informazioni su come specificare <xref:System.TimeSpan> i valori, vedere [valori TimeSpan](../windows-workflow-foundation/index.md).</span><span class="sxs-lookup"><span data-stu-id="57f97-118">For more information about how to specify <xref:System.TimeSpan> values, see [Timespan Values](../windows-workflow-foundation/index.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="57f97-119">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="57f97-119">Child Elements</span></span>  
 <span data-ttu-id="57f97-120">Nessuna</span><span class="sxs-lookup"><span data-stu-id="57f97-120">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="57f97-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="57f97-121">Parent Elements</span></span>  
  
|<span data-ttu-id="57f97-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="57f97-122">Element</span></span>|<span data-ttu-id="57f97-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="57f97-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="57f97-124">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="57f97-124">\<identityConfiguration></span></span>](identityconfiguration.md)|<span data-ttu-id="57f97-125">Specifica le impostazioni di identità a livello di servizio.</span><span class="sxs-lookup"><span data-stu-id="57f97-125">Specifies service-level identity settings.</span></span>|  
|[<span data-ttu-id="57f97-126">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="57f97-126">\<securityTokenHandlerConfiguration></span></span>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="57f97-127">Fornisce la configurazione per una raccolta di gestori di token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="57f97-127">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="57f97-128">Note</span><span class="sxs-lookup"><span data-stu-id="57f97-128">Remarks</span></span>  
 <span data-ttu-id="57f97-129">Un `<tokenReplayDetection>` elemento può essere specificato a livello di servizio `<identityConfiguration>` nell'elemento o nel livello di raccolta del gestore del token di sicurezza `<securityTokenHandlerConfiguration>` sotto l'elemento.</span><span class="sxs-lookup"><span data-stu-id="57f97-129">A `<tokenReplayDetection>` element can be specified at the service level under the `<identityConfiguration>` element or on the security token handler collection level under the `<securityTokenHandlerConfiguration>` element.</span></span> <span data-ttu-id="57f97-130">Le impostazioni in una raccolta di gestori di token eseguono l'override di quelle specificate nel servizio.</span><span class="sxs-lookup"><span data-stu-id="57f97-130">Settings on a token handler collection override those specified on the service.</span></span>  
  
 <span data-ttu-id="57f97-131">Il tipo della cache di riproduzione dei token viene specificato dall' [ \<elemento > tokenReplayCache](tokenreplaycache.md) .</span><span class="sxs-lookup"><span data-stu-id="57f97-131">The type of the token replay cache is specified by the [\<tokenReplayCache>](tokenreplaycache.md) element.</span></span>

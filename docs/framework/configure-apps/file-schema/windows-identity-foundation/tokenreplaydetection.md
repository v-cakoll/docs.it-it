---
title: '&lt;tokenReplayDetection&gt;'
ms.date: 03/30/2017
ms.assetid: ac3f588e-5f75-4275-b969-2d492ecc3b47
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 7f0cef2590bb301e6897aa4922454942ecdd0957
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="lttokenreplaydetectiongt"></a><span data-ttu-id="d5e46-102">&lt;tokenReplayDetection&gt;</span><span class="sxs-lookup"><span data-stu-id="d5e46-102">&lt;tokenReplayDetection&gt;</span></span>
<span data-ttu-id="d5e46-103">Abilita rilevamento riproduzione token e specifica l'ora di scadenza per i token.</span><span class="sxs-lookup"><span data-stu-id="d5e46-103">Enables token replay detection and specifies the expiration time for tokens.</span></span>  
  
 <span data-ttu-id="d5e46-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="d5e46-104">\<system.identityModel></span></span>  
<span data-ttu-id="d5e46-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="d5e46-105">\<identityConfiguration></span></span>  
<span data-ttu-id="d5e46-106">\<tokenReplayDetection ></span><span class="sxs-lookup"><span data-stu-id="d5e46-106">\<tokenReplayDetection></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d5e46-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d5e46-107">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <tokenReplayDetection enabled=xs:boolean expirationPeriod=TimeSpan>  
    </tokenReplayDetection>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="type"></a><span data-ttu-id="d5e46-108">Tipo</span><span class="sxs-lookup"><span data-stu-id="d5e46-108">Type</span></span>  
 <xref:System.IdentityModel.Configuration.TokenReplayDetectionElement>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d5e46-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="d5e46-109">Attributes and Elements</span></span>  
 <span data-ttu-id="d5e46-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="d5e46-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d5e46-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="d5e46-111">Attributes</span></span>  
  
|<span data-ttu-id="d5e46-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="d5e46-112">Attribute</span></span>|<span data-ttu-id="d5e46-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d5e46-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d5e46-114">enabled</span><span class="sxs-lookup"><span data-stu-id="d5e46-114">enabled</span></span>|<span data-ttu-id="d5e46-115">Un valore che specifica se il rilevamento riproduzione token è abilitato; "true" per abilitare i token di rilevamento riproduzione.</span><span class="sxs-lookup"><span data-stu-id="d5e46-115">A value that specifies whether token replay detection is enabled; "true" to enable token replay detection.</span></span>|  
|<span data-ttu-id="d5e46-116">expirationPeriod</span><span class="sxs-lookup"><span data-stu-id="d5e46-116">expirationPeriod</span></span>|<span data-ttu-id="d5e46-117">Oggetto <xref:System.TimeSpan> che specifica la quantità massima di tempo prima che un elemento viene considerato scaduto e rimossi dalla cache.</span><span class="sxs-lookup"><span data-stu-id="d5e46-117">A <xref:System.TimeSpan> that specifies the maximum amount of time before an item is considered expired and removed from the cache.</span></span>  <span data-ttu-id="d5e46-118">Per ulteriori informazioni su come specificare <xref:System.TimeSpan> valori, vedere [valori Timespan](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span><span class="sxs-lookup"><span data-stu-id="d5e46-118">For more information about how to specify <xref:System.TimeSpan> values, see [Timespan Values](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d5e46-119">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="d5e46-119">Child Elements</span></span>  
 <span data-ttu-id="d5e46-120">Nessuno</span><span class="sxs-lookup"><span data-stu-id="d5e46-120">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d5e46-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="d5e46-121">Parent Elements</span></span>  
  
|<span data-ttu-id="d5e46-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="d5e46-122">Element</span></span>|<span data-ttu-id="d5e46-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d5e46-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d5e46-124">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="d5e46-124">\<identityConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|<span data-ttu-id="d5e46-125">Specifica le impostazioni di identità a livello di servizio.</span><span class="sxs-lookup"><span data-stu-id="d5e46-125">Specifies service-level identity settings.</span></span>|  
|[<span data-ttu-id="d5e46-126">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="d5e46-126">\<securityTokenHandlerConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|<span data-ttu-id="d5e46-127">Fornisce la configurazione per una raccolta di sicurezza gestori di token.</span><span class="sxs-lookup"><span data-stu-id="d5e46-127">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d5e46-128">Note</span><span class="sxs-lookup"><span data-stu-id="d5e46-128">Remarks</span></span>  
 <span data-ttu-id="d5e46-129">A `<tokenReplayDetection>` elemento può essere specificato a livello di servizio sotto il `<identityConfiguration>` elemento o a livello di raccolta gestore dei token di sicurezza nel `<securityTokenHandlerConfiguration>` elemento.</span><span class="sxs-lookup"><span data-stu-id="d5e46-129">A `<tokenReplayDetection>` element can be specified at the service level under the `<identityConfiguration>` element or on the security token handler collection level under the `<securityTokenHandlerConfiguration>` element.</span></span> <span data-ttu-id="d5e46-130">Le impostazioni in una raccolta di gestore del token sostituiscono quelle specificate nel servizio.</span><span class="sxs-lookup"><span data-stu-id="d5e46-130">Settings on a token handler collection override those specified on the service.</span></span>  
  
 <span data-ttu-id="d5e46-131">Il tipo di cache di riproduzione token è specificato per il [ \<tokenReplayCache >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaycache.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="d5e46-131">The type of the token replay cache is specified by the [\<tokenReplayCache>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaycache.md) element.</span></span>

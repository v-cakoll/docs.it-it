---
title: <tokenReplayDetection>
ms.date: 03/30/2017
ms.assetid: ac3f588e-5f75-4275-b969-2d492ecc3b47
author: BrucePerlerMS
ms.openlocfilehash: 2e2159a73ca79fc362a8138eea95dbd173dafb11
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69944290"
---
# <a name="tokenreplaydetection"></a><span data-ttu-id="e3958-101">\<tokenReplayDetection></span><span class="sxs-lookup"><span data-stu-id="e3958-101">\<tokenReplayDetection></span></span>
<span data-ttu-id="e3958-102">Abilita il rilevamento della riproduzione dei token e specifica l'ora di scadenza per i token.</span><span class="sxs-lookup"><span data-stu-id="e3958-102">Enables token replay detection and specifies the expiration time for tokens.</span></span>  
  
 <span data-ttu-id="e3958-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="e3958-103">\<system.identityModel></span></span>  
<span data-ttu-id="e3958-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="e3958-104">\<identityConfiguration></span></span>  
<span data-ttu-id="e3958-105">\<tokenReplayDetection></span><span class="sxs-lookup"><span data-stu-id="e3958-105">\<tokenReplayDetection></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e3958-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e3958-106">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <tokenReplayDetection enabled=xs:boolean expirationPeriod=TimeSpan>  
    </tokenReplayDetection>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="type"></a><span data-ttu-id="e3958-107">Type</span><span class="sxs-lookup"><span data-stu-id="e3958-107">Type</span></span>  
 <xref:System.IdentityModel.Configuration.TokenReplayDetectionElement>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e3958-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="e3958-108">Attributes and Elements</span></span>  
 <span data-ttu-id="e3958-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="e3958-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e3958-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="e3958-110">Attributes</span></span>  
  
|<span data-ttu-id="e3958-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="e3958-111">Attribute</span></span>|<span data-ttu-id="e3958-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e3958-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e3958-113">enabled</span><span class="sxs-lookup"><span data-stu-id="e3958-113">enabled</span></span>|<span data-ttu-id="e3958-114">Valore che specifica se il rilevamento della riproduzione del token è abilitato; "true" per abilitare il rilevamento della riproduzione del token.</span><span class="sxs-lookup"><span data-stu-id="e3958-114">A value that specifies whether token replay detection is enabled; "true" to enable token replay detection.</span></span>|  
|<span data-ttu-id="e3958-115">expirationPeriod</span><span class="sxs-lookup"><span data-stu-id="e3958-115">expirationPeriod</span></span>|<span data-ttu-id="e3958-116">Oggetto <xref:System.TimeSpan> che specifica l'intervallo di tempo massimo prima che un elemento venga considerato scaduto e rimosso dalla cache.</span><span class="sxs-lookup"><span data-stu-id="e3958-116">A <xref:System.TimeSpan> that specifies the maximum amount of time before an item is considered expired and removed from the cache.</span></span>  <span data-ttu-id="e3958-117">Per ulteriori informazioni su come specificare <xref:System.TimeSpan> i valori, vedere [valori TimeSpan](../windows-workflow-foundation/index.md).</span><span class="sxs-lookup"><span data-stu-id="e3958-117">For more information about how to specify <xref:System.TimeSpan> values, see [Timespan Values](../windows-workflow-foundation/index.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e3958-118">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="e3958-118">Child Elements</span></span>  
 <span data-ttu-id="e3958-119">Nessuna</span><span class="sxs-lookup"><span data-stu-id="e3958-119">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e3958-120">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="e3958-120">Parent Elements</span></span>  
  
|<span data-ttu-id="e3958-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="e3958-121">Element</span></span>|<span data-ttu-id="e3958-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e3958-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e3958-123">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="e3958-123">\<identityConfiguration></span></span>](identityconfiguration.md)|<span data-ttu-id="e3958-124">Specifica le impostazioni di identità a livello di servizio.</span><span class="sxs-lookup"><span data-stu-id="e3958-124">Specifies service-level identity settings.</span></span>|  
|[<span data-ttu-id="e3958-125">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="e3958-125">\<securityTokenHandlerConfiguration></span></span>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="e3958-126">Fornisce la configurazione per una raccolta di gestori di token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="e3958-126">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e3958-127">Note</span><span class="sxs-lookup"><span data-stu-id="e3958-127">Remarks</span></span>  
 <span data-ttu-id="e3958-128">Un `<tokenReplayDetection>` elemento può essere specificato a livello di servizio `<identityConfiguration>` nell'elemento o nel livello di raccolta del gestore del token di sicurezza `<securityTokenHandlerConfiguration>` sotto l'elemento.</span><span class="sxs-lookup"><span data-stu-id="e3958-128">A `<tokenReplayDetection>` element can be specified at the service level under the `<identityConfiguration>` element or on the security token handler collection level under the `<securityTokenHandlerConfiguration>` element.</span></span> <span data-ttu-id="e3958-129">Le impostazioni in una raccolta di gestori di token eseguono l'override di quelle specificate nel servizio.</span><span class="sxs-lookup"><span data-stu-id="e3958-129">Settings on a token handler collection override those specified on the service.</span></span>  
  
 <span data-ttu-id="e3958-130">Il tipo della cache di riproduzione dei token viene specificato dall' [ \<elemento > tokenReplayCache](tokenreplaycache.md) .</span><span class="sxs-lookup"><span data-stu-id="e3958-130">The type of the token replay cache is specified by the [\<tokenReplayCache>](tokenreplaycache.md) element.</span></span>

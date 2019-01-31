---
title: <tokenReplayDetection>
ms.date: 03/30/2017
ms.assetid: ac3f588e-5f75-4275-b969-2d492ecc3b47
author: BrucePerlerMS
ms.openlocfilehash: 4deeb1d84f2621adb7ff1b649a505138b6856ec1
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55283075"
---
# <a name="tokenreplaydetection"></a><span data-ttu-id="99600-101">\<tokenReplayDetection></span><span class="sxs-lookup"><span data-stu-id="99600-101">\<tokenReplayDetection></span></span>
<span data-ttu-id="99600-102">Abilita rilevamento riproduzione token e specifica l'ora di scadenza per i token.</span><span class="sxs-lookup"><span data-stu-id="99600-102">Enables token replay detection and specifies the expiration time for tokens.</span></span>  
  
 <span data-ttu-id="99600-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="99600-103">\<system.identityModel></span></span>  
<span data-ttu-id="99600-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="99600-104">\<identityConfiguration></span></span>  
<span data-ttu-id="99600-105">\<tokenReplayDetection></span><span class="sxs-lookup"><span data-stu-id="99600-105">\<tokenReplayDetection></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99600-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="99600-106">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <tokenReplayDetection enabled=xs:boolean expirationPeriod=TimeSpan>  
    </tokenReplayDetection>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="type"></a><span data-ttu-id="99600-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="99600-107">Type</span></span>  
 <xref:System.IdentityModel.Configuration.TokenReplayDetectionElement>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="99600-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="99600-108">Attributes and Elements</span></span>  
 <span data-ttu-id="99600-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="99600-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="99600-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="99600-110">Attributes</span></span>  
  
|<span data-ttu-id="99600-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="99600-111">Attribute</span></span>|<span data-ttu-id="99600-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="99600-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="99600-113">enabled</span><span class="sxs-lookup"><span data-stu-id="99600-113">enabled</span></span>|<span data-ttu-id="99600-114">Un valore che specifica se il rilevamento riproduzione token è abilitato; "true" per abilitare token rilevamento riproduzione.</span><span class="sxs-lookup"><span data-stu-id="99600-114">A value that specifies whether token replay detection is enabled; "true" to enable token replay detection.</span></span>|  
|<span data-ttu-id="99600-115">expirationPeriod</span><span class="sxs-lookup"><span data-stu-id="99600-115">expirationPeriod</span></span>|<span data-ttu-id="99600-116">Oggetto <xref:System.TimeSpan> che specifica la quantità massima di tempo prima che un elemento venga considerato scaduto e venga rimosso dalla cache.</span><span class="sxs-lookup"><span data-stu-id="99600-116">A <xref:System.TimeSpan> that specifies the maximum amount of time before an item is considered expired and removed from the cache.</span></span>  <span data-ttu-id="99600-117">Per altre informazioni su come specificare <xref:System.TimeSpan> valori, vedere [valori Timespan](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span><span class="sxs-lookup"><span data-stu-id="99600-117">For more information about how to specify <xref:System.TimeSpan> values, see [Timespan Values](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="99600-118">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="99600-118">Child Elements</span></span>  
 <span data-ttu-id="99600-119">nessuno</span><span class="sxs-lookup"><span data-stu-id="99600-119">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="99600-120">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="99600-120">Parent Elements</span></span>  
  
|<span data-ttu-id="99600-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="99600-121">Element</span></span>|<span data-ttu-id="99600-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="99600-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="99600-123">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="99600-123">\<identityConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|<span data-ttu-id="99600-124">Specifica le impostazioni di identità a livello di servizio.</span><span class="sxs-lookup"><span data-stu-id="99600-124">Specifies service-level identity settings.</span></span>|  
|[<span data-ttu-id="99600-125">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="99600-125">\<securityTokenHandlerConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|<span data-ttu-id="99600-126">Fornisce la configurazione per una raccolta di sicurezza i gestori di token.</span><span class="sxs-lookup"><span data-stu-id="99600-126">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="99600-127">Note</span><span class="sxs-lookup"><span data-stu-id="99600-127">Remarks</span></span>  
 <span data-ttu-id="99600-128">Oggetto `<tokenReplayDetection>` elemento può essere specificato a livello di servizio con il `<identityConfiguration>` elemento o a livello di raccolta gestori di token di sicurezza nel `<securityTokenHandlerConfiguration>` elemento.</span><span class="sxs-lookup"><span data-stu-id="99600-128">A `<tokenReplayDetection>` element can be specified at the service level under the `<identityConfiguration>` element or on the security token handler collection level under the `<securityTokenHandlerConfiguration>` element.</span></span> <span data-ttu-id="99600-129">Le impostazioni in una raccolta di gestori di token sostituiscono quelle specificate nel servizio.</span><span class="sxs-lookup"><span data-stu-id="99600-129">Settings on a token handler collection override those specified on the service.</span></span>  
  
 <span data-ttu-id="99600-130">Il tipo di cache di riproduzione dei token è specificato per il [ \<tokenReplayCache >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaycache.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="99600-130">The type of the token replay cache is specified by the [\<tokenReplayCache>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaycache.md) element.</span></span>

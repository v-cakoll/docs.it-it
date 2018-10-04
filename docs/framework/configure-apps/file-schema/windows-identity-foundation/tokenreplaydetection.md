---
title: '&lt;tokenReplayDetection&gt;'
ms.date: 03/30/2017
ms.assetid: ac3f588e-5f75-4275-b969-2d492ecc3b47
author: BrucePerlerMS
ms.openlocfilehash: bd2272cb83dc0183d5008cfa178e11783f51ca2d
ms.sourcegitcommit: 700b9003ea6bdd83a53458bbc436c9b5778344f1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/03/2018
ms.locfileid: "48261055"
---
# <a name="lttokenreplaydetectiongt"></a><span data-ttu-id="8ba5b-102">&lt;tokenReplayDetection&gt;</span><span class="sxs-lookup"><span data-stu-id="8ba5b-102">&lt;tokenReplayDetection&gt;</span></span>
<span data-ttu-id="8ba5b-103">Abilita rilevamento riproduzione token e specifica l'ora di scadenza per i token.</span><span class="sxs-lookup"><span data-stu-id="8ba5b-103">Enables token replay detection and specifies the expiration time for tokens.</span></span>  
  
 <span data-ttu-id="8ba5b-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="8ba5b-104">\<system.identityModel></span></span>  
<span data-ttu-id="8ba5b-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="8ba5b-105">\<identityConfiguration></span></span>  
<span data-ttu-id="8ba5b-106">\<tokenReplayDetection ></span><span class="sxs-lookup"><span data-stu-id="8ba5b-106">\<tokenReplayDetection></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ba5b-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8ba5b-107">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <tokenReplayDetection enabled=xs:boolean expirationPeriod=TimeSpan>  
    </tokenReplayDetection>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="type"></a><span data-ttu-id="8ba5b-108">Tipo</span><span class="sxs-lookup"><span data-stu-id="8ba5b-108">Type</span></span>  
 <xref:System.IdentityModel.Configuration.TokenReplayDetectionElement>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8ba5b-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="8ba5b-109">Attributes and Elements</span></span>  
 <span data-ttu-id="8ba5b-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="8ba5b-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8ba5b-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="8ba5b-111">Attributes</span></span>  
  
|<span data-ttu-id="8ba5b-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="8ba5b-112">Attribute</span></span>|<span data-ttu-id="8ba5b-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8ba5b-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8ba5b-114">enabled</span><span class="sxs-lookup"><span data-stu-id="8ba5b-114">enabled</span></span>|<span data-ttu-id="8ba5b-115">Un valore che specifica se il rilevamento riproduzione token è abilitato; "true" per abilitare token rilevamento riproduzione.</span><span class="sxs-lookup"><span data-stu-id="8ba5b-115">A value that specifies whether token replay detection is enabled; "true" to enable token replay detection.</span></span>|  
|<span data-ttu-id="8ba5b-116">expirationPeriod</span><span class="sxs-lookup"><span data-stu-id="8ba5b-116">expirationPeriod</span></span>|<span data-ttu-id="8ba5b-117">Oggetto <xref:System.TimeSpan> che specifica la quantità massima di tempo prima che un elemento venga considerato scaduto e venga rimosso dalla cache.</span><span class="sxs-lookup"><span data-stu-id="8ba5b-117">A <xref:System.TimeSpan> that specifies the maximum amount of time before an item is considered expired and removed from the cache.</span></span>  <span data-ttu-id="8ba5b-118">Per altre informazioni su come specificare <xref:System.TimeSpan> valori, vedere [valori Timespan](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span><span class="sxs-lookup"><span data-stu-id="8ba5b-118">For more information about how to specify <xref:System.TimeSpan> values, see [Timespan Values](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8ba5b-119">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="8ba5b-119">Child Elements</span></span>  
 <span data-ttu-id="8ba5b-120">nessuno</span><span class="sxs-lookup"><span data-stu-id="8ba5b-120">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8ba5b-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="8ba5b-121">Parent Elements</span></span>  
  
|<span data-ttu-id="8ba5b-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="8ba5b-122">Element</span></span>|<span data-ttu-id="8ba5b-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8ba5b-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8ba5b-124">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="8ba5b-124">\<identityConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|<span data-ttu-id="8ba5b-125">Specifica le impostazioni di identità a livello di servizio.</span><span class="sxs-lookup"><span data-stu-id="8ba5b-125">Specifies service-level identity settings.</span></span>|  
|[<span data-ttu-id="8ba5b-126">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="8ba5b-126">\<securityTokenHandlerConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|<span data-ttu-id="8ba5b-127">Fornisce la configurazione per una raccolta di sicurezza i gestori di token.</span><span class="sxs-lookup"><span data-stu-id="8ba5b-127">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8ba5b-128">Note</span><span class="sxs-lookup"><span data-stu-id="8ba5b-128">Remarks</span></span>  
 <span data-ttu-id="8ba5b-129">Oggetto `<tokenReplayDetection>` elemento può essere specificato a livello di servizio con il `<identityConfiguration>` elemento o a livello di raccolta gestori di token di sicurezza nel `<securityTokenHandlerConfiguration>` elemento.</span><span class="sxs-lookup"><span data-stu-id="8ba5b-129">A `<tokenReplayDetection>` element can be specified at the service level under the `<identityConfiguration>` element or on the security token handler collection level under the `<securityTokenHandlerConfiguration>` element.</span></span> <span data-ttu-id="8ba5b-130">Le impostazioni in una raccolta di gestori di token sostituiscono quelle specificate nel servizio.</span><span class="sxs-lookup"><span data-stu-id="8ba5b-130">Settings on a token handler collection override those specified on the service.</span></span>  
  
 <span data-ttu-id="8ba5b-131">Il tipo di cache di riproduzione dei token è specificato per il [ \<tokenReplayCache >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaycache.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="8ba5b-131">The type of the token replay cache is specified by the [\<tokenReplayCache>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaycache.md) element.</span></span>

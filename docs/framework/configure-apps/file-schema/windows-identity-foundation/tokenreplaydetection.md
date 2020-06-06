---
title: <tokenReplayDetection>
ms.date: 03/30/2017
ms.assetid: ac3f588e-5f75-4275-b969-2d492ecc3b47
author: BrucePerlerMS
ms.openlocfilehash: a4454042e1d97fb3cc2d6f2735104dadda6e7b5a
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70251765"
---
# \<tokenReplayDetection>
<span data-ttu-id="24db5-101">Abilita il rilevamento della riproduzione dei token e specifica l'ora di scadenza per i token.</span><span class="sxs-lookup"><span data-stu-id="24db5-101">Enables token replay detection and specifies the expiration time for tokens.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<tokenReplayDetection>**  
  
## <a name="syntax"></a><span data-ttu-id="24db5-102">Sintassi</span><span class="sxs-lookup"><span data-stu-id="24db5-102">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <tokenReplayDetection enabled=xs:boolean expirationPeriod=TimeSpan>  
    </tokenReplayDetection>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="type"></a><span data-ttu-id="24db5-103">Tipo</span><span class="sxs-lookup"><span data-stu-id="24db5-103">Type</span></span>  
 <xref:System.IdentityModel.Configuration.TokenReplayDetectionElement>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="24db5-104">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="24db5-104">Attributes and Elements</span></span>  
 <span data-ttu-id="24db5-105">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="24db5-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="24db5-106">Attributi</span><span class="sxs-lookup"><span data-stu-id="24db5-106">Attributes</span></span>  
  
|<span data-ttu-id="24db5-107">Attributo</span><span class="sxs-lookup"><span data-stu-id="24db5-107">Attribute</span></span>|<span data-ttu-id="24db5-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="24db5-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="24db5-109">Enabled</span><span class="sxs-lookup"><span data-stu-id="24db5-109">enabled</span></span>|<span data-ttu-id="24db5-110">Valore che specifica se il rilevamento della riproduzione del token è abilitato; "true" per abilitare il rilevamento della riproduzione del token.</span><span class="sxs-lookup"><span data-stu-id="24db5-110">A value that specifies whether token replay detection is enabled; "true" to enable token replay detection.</span></span>|  
|<span data-ttu-id="24db5-111">expirationPeriod</span><span class="sxs-lookup"><span data-stu-id="24db5-111">expirationPeriod</span></span>|<span data-ttu-id="24db5-112">Oggetto <xref:System.TimeSpan> che specifica l'intervallo di tempo massimo prima che un elemento venga considerato scaduto e rimosso dalla cache.</span><span class="sxs-lookup"><span data-stu-id="24db5-112">A <xref:System.TimeSpan> that specifies the maximum amount of time before an item is considered expired and removed from the cache.</span></span>  <span data-ttu-id="24db5-113">Per ulteriori informazioni su come specificare <xref:System.TimeSpan> i valori, vedere [valori TimeSpan](../windows-workflow-foundation/index.md).</span><span class="sxs-lookup"><span data-stu-id="24db5-113">For more information about how to specify <xref:System.TimeSpan> values, see [Timespan Values](../windows-workflow-foundation/index.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="24db5-114">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="24db5-114">Child Elements</span></span>  
 <span data-ttu-id="24db5-115">nessuno</span><span class="sxs-lookup"><span data-stu-id="24db5-115">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="24db5-116">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="24db5-116">Parent Elements</span></span>  
  
|<span data-ttu-id="24db5-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="24db5-117">Element</span></span>|<span data-ttu-id="24db5-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="24db5-118">Description</span></span>|  
|-------------|-----------------|  
|[\<identityConfiguration>](identityconfiguration.md)|<span data-ttu-id="24db5-119">Specifica le impostazioni di identità a livello di servizio.</span><span class="sxs-lookup"><span data-stu-id="24db5-119">Specifies service-level identity settings.</span></span>|  
|[\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="24db5-120">Fornisce la configurazione per una raccolta di gestori di token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="24db5-120">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="24db5-121">Commenti</span><span class="sxs-lookup"><span data-stu-id="24db5-121">Remarks</span></span>  
 <span data-ttu-id="24db5-122">Un `<tokenReplayDetection>` elemento può essere specificato a livello di servizio nell' `<identityConfiguration>` elemento o nel livello di raccolta del gestore del token di sicurezza sotto l' `<securityTokenHandlerConfiguration>` elemento.</span><span class="sxs-lookup"><span data-stu-id="24db5-122">A `<tokenReplayDetection>` element can be specified at the service level under the `<identityConfiguration>` element or on the security token handler collection level under the `<securityTokenHandlerConfiguration>` element.</span></span> <span data-ttu-id="24db5-123">Le impostazioni in una raccolta di gestori di token eseguono l'override di quelle specificate nel servizio.</span><span class="sxs-lookup"><span data-stu-id="24db5-123">Settings on a token handler collection override those specified on the service.</span></span>  
  
 <span data-ttu-id="24db5-124">Il tipo della cache di riproduzione dei token viene specificato dall' [\<tokenReplayCache>](tokenreplaycache.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="24db5-124">The type of the token replay cache is specified by the [\<tokenReplayCache>](tokenreplaycache.md) element.</span></span>

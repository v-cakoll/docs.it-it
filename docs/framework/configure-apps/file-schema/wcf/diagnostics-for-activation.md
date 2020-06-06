---
title: <diagnostics>per l'attivazione
ms.date: 03/30/2017
ms.assetid: 1486e0eb-fe2a-46c3-b584-c924889477dd
ms.openlocfilehash: 33b2cd4c5ae1b4076892a61aa7e2b927efa1ddc1
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70400416"
---
# <a name="diagnostics-for-activation"></a><span data-ttu-id="8615e-102">\<diagnostics>per l'attivazione</span><span class="sxs-lookup"><span data-stu-id="8615e-102">\<diagnostics> for Activation</span></span>
<span data-ttu-id="8615e-103">Configura le funzionalità di diagnostica del listener Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="8615e-103">Configures Windows Communication Foundation (WCF) listener's diagnostics functionalities.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel.activation>**](system-servicemodel-activation.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<diagnostics>**  
  
## <a name="syntax"></a><span data-ttu-id="8615e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8615e-104">Syntax</span></span>  
  
```xml  
<configuration>
  <system.serviceModel.activation>
    <diagnostics performanceCountersEnabled="Boolean" />
  </system.serviceModel.activation>
</configuration>
```  
  
## <a name="type"></a><span data-ttu-id="8615e-105">Tipo</span><span class="sxs-lookup"><span data-stu-id="8615e-105">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8615e-106">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="8615e-106">Attributes and Elements</span></span>  
 <span data-ttu-id="8615e-107">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="8615e-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8615e-108">Attributi</span><span class="sxs-lookup"><span data-stu-id="8615e-108">Attributes</span></span>  
  
|<span data-ttu-id="8615e-109">Attributo</span><span class="sxs-lookup"><span data-stu-id="8615e-109">Attribute</span></span>|<span data-ttu-id="8615e-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8615e-110">Description</span></span>|  
|---------------|-----------------|  
|`performanceCountersEnabled`|<span data-ttu-id="8615e-111">Valore booleano che indica se sono i contatori delle prestazioni stati attivati a fini diagnostici.</span><span class="sxs-lookup"><span data-stu-id="8615e-111">A Boolean value that indicates whether performance counters are enabled for diagnostic purposes.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8615e-112">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="8615e-112">Child Elements</span></span>  
 <span data-ttu-id="8615e-113">No.</span><span class="sxs-lookup"><span data-stu-id="8615e-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8615e-114">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="8615e-114">Parent Elements</span></span>  
  
|<span data-ttu-id="8615e-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="8615e-115">Element</span></span>|<span data-ttu-id="8615e-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8615e-116">Description</span></span>|  
|-------------|-----------------|  
|[\<system.serviceModel.activation>](system-servicemodel-activation.md)|<span data-ttu-id="8615e-117">Contiene impostazioni di configurazione per il processo del listener SMSvcHost.exe.</span><span class="sxs-lookup"><span data-stu-id="8615e-117">Contains configuration settings for the listener process SMSvcHost.exe.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8615e-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8615e-118">See also</span></span>

- <xref:System.ServiceModel.Activation.Configuration.DiagnosticSection>

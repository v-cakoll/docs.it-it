---
title: <diagnostics>per l'attivazione
ms.date: 03/30/2017
ms.assetid: 1486e0eb-fe2a-46c3-b584-c924889477dd
ms.openlocfilehash: 33b2cd4c5ae1b4076892a61aa7e2b927efa1ddc1
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400416"
---
# <a name="diagnostics-for-activation"></a><span data-ttu-id="50b0f-102">\<> di diagnostica per l'attivazione</span><span class="sxs-lookup"><span data-stu-id="50b0f-102">\<diagnostics> for Activation</span></span>
<span data-ttu-id="50b0f-103">Configura le funzionalità di diagnostica del listener Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="50b0f-103">Configures Windows Communication Foundation (WCF) listener's diagnostics functionalities.</span></span>  
  
<span data-ttu-id="50b0f-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="50b0f-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="50b0f-105">&nbsp;&nbsp;[ **\<System. serviceModel. Activation >** ](system-servicemodel-activation.md)</span><span class="sxs-lookup"><span data-stu-id="50b0f-105">&nbsp;&nbsp;[**\<system.serviceModel.activation>**](system-servicemodel-activation.md)</span></span>\
<span data-ttu-id="50b0f-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<> di diagnostica**</span><span class="sxs-lookup"><span data-stu-id="50b0f-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<diagnostics>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="50b0f-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="50b0f-107">Syntax</span></span>  
  
```xml  
<configuration>
  <system.serviceModel.activation>
    <diagnostics performanceCountersEnabled="Boolean" />
  </system.serviceModel.activation>
</configuration>
```  
  
## <a name="type"></a><span data-ttu-id="50b0f-108">Type</span><span class="sxs-lookup"><span data-stu-id="50b0f-108">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="50b0f-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="50b0f-109">Attributes and Elements</span></span>  
 <span data-ttu-id="50b0f-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="50b0f-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="50b0f-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="50b0f-111">Attributes</span></span>  
  
|<span data-ttu-id="50b0f-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="50b0f-112">Attribute</span></span>|<span data-ttu-id="50b0f-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="50b0f-113">Description</span></span>|  
|---------------|-----------------|  
|`performanceCountersEnabled`|<span data-ttu-id="50b0f-114">Valore booleano che indica se sono i contatori delle prestazioni stati attivati a fini diagnostici.</span><span class="sxs-lookup"><span data-stu-id="50b0f-114">A Boolean value that indicates whether performance counters are enabled for diagnostic purposes.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="50b0f-115">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="50b0f-115">Child Elements</span></span>  
 <span data-ttu-id="50b0f-116">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="50b0f-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="50b0f-117">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="50b0f-117">Parent Elements</span></span>  
  
|<span data-ttu-id="50b0f-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="50b0f-118">Element</span></span>|<span data-ttu-id="50b0f-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="50b0f-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="50b0f-120">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="50b0f-120">\<system.serviceModel.activation></span></span>](system-servicemodel-activation.md)|<span data-ttu-id="50b0f-121">Contiene impostazioni di configurazione per il processo del listener SMSvcHost.exe.</span><span class="sxs-lookup"><span data-stu-id="50b0f-121">Contains configuration settings for the listener process SMSvcHost.exe.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="50b0f-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="50b0f-122">See also</span></span>

- <xref:System.ServiceModel.Activation.Configuration.DiagnosticSection>

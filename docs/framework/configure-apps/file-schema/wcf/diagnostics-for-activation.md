---
title: <diagnostics>per l'attivazione
ms.date: 03/30/2017
ms.assetid: 1486e0eb-fe2a-46c3-b584-c924889477dd
ms.openlocfilehash: 543c41936921eda39017e07f1c97294b268a9141
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919216"
---
# <a name="diagnostics-for-activation"></a><span data-ttu-id="1045d-102">\<> di diagnostica per l'attivazione</span><span class="sxs-lookup"><span data-stu-id="1045d-102">\<diagnostics> for Activation</span></span>
<span data-ttu-id="1045d-103">Configura le funzionalità di diagnostica del listener Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="1045d-103">Configures Windows Communication Foundation (WCF) listener's diagnostics functionalities.</span></span>  
  
 <span data-ttu-id="1045d-104">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="1045d-104">\<system.serviceModel.activation></span></span>  
<span data-ttu-id="1045d-105">\<> di diagnostica</span><span class="sxs-lookup"><span data-stu-id="1045d-105">\<diagnostics></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1045d-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1045d-106">Syntax</span></span>  
  
```xml  
<configuration>
  <system.serviceModel.activation>
    <diagnostics performanceCountersEnabled="Boolean" />
  </system.serviceModel.activation>
</configuration>
```  
  
## <a name="type"></a><span data-ttu-id="1045d-107">Type</span><span class="sxs-lookup"><span data-stu-id="1045d-107">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1045d-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="1045d-108">Attributes and Elements</span></span>  
 <span data-ttu-id="1045d-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="1045d-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1045d-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="1045d-110">Attributes</span></span>  
  
|<span data-ttu-id="1045d-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="1045d-111">Attribute</span></span>|<span data-ttu-id="1045d-112">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="1045d-112">Description</span></span>|  
|---------------|-----------------|  
|`performanceCountersEnabled`|<span data-ttu-id="1045d-113">Valore booleano che indica se sono i contatori delle prestazioni stati attivati a fini diagnostici.</span><span class="sxs-lookup"><span data-stu-id="1045d-113">A Boolean value that indicates whether performance counters are enabled for diagnostic purposes.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1045d-114">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="1045d-114">Child Elements</span></span>  
 <span data-ttu-id="1045d-115">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="1045d-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1045d-116">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="1045d-116">Parent Elements</span></span>  
  
|<span data-ttu-id="1045d-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="1045d-117">Element</span></span>|<span data-ttu-id="1045d-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1045d-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1045d-119">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="1045d-119">\<system.serviceModel.activation></span></span>](system-servicemodel-activation.md)|<span data-ttu-id="1045d-120">Contiene impostazioni di configurazione per il processo del listener SMSvcHost.exe.</span><span class="sxs-lookup"><span data-stu-id="1045d-120">Contains configuration settings for the listener process SMSvcHost.exe.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1045d-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1045d-121">See also</span></span>

- <xref:System.ServiceModel.Activation.Configuration.DiagnosticSection>

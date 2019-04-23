---
title: <diagnostics> per l'attivazione
ms.date: 03/30/2017
ms.assetid: 1486e0eb-fe2a-46c3-b584-c924889477dd
ms.openlocfilehash: 30456963a7d74a93e39bb1fddc0910daae97f039
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59203808"
---
# <a name="diagnostics-for-activation"></a><span data-ttu-id="01f40-102">\<diagnostica > per Activation</span><span class="sxs-lookup"><span data-stu-id="01f40-102">\<diagnostics> for Activation</span></span>
<span data-ttu-id="01f40-103">Configura le funzionalità di diagnostica del listener di Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="01f40-103">Configures Windows Communication Foundation (WCF) listener's diagnostics functionalities.</span></span>  
  
 <span data-ttu-id="01f40-104">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="01f40-104">\<system.serviceModel.activation></span></span>  
<span data-ttu-id="01f40-105">\<diagnostica ></span><span class="sxs-lookup"><span data-stu-id="01f40-105">\<diagnostics></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="01f40-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="01f40-106">Syntax</span></span>  
  
```xml  
<configuration>
  <system.serviceModel.activation>
    <diagnostics performanceCountersEnabled="Boolean" />
  </system.serviceModel.activation>
</configuration>
```  
  
## <a name="type"></a><span data-ttu-id="01f40-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="01f40-107">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="01f40-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="01f40-108">Attributes and Elements</span></span>  
 <span data-ttu-id="01f40-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="01f40-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="01f40-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="01f40-110">Attributes</span></span>  
  
|<span data-ttu-id="01f40-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="01f40-111">Attribute</span></span>|<span data-ttu-id="01f40-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="01f40-112">Description</span></span>|  
|---------------|-----------------|  
|`performanceCountersEnabled`|<span data-ttu-id="01f40-113">Valore booleano che indica se sono i contatori delle prestazioni stati attivati a fini diagnostici.</span><span class="sxs-lookup"><span data-stu-id="01f40-113">A Boolean value that indicates whether performance counters are enabled for diagnostic purposes.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="01f40-114">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="01f40-114">Child Elements</span></span>  
 <span data-ttu-id="01f40-115">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="01f40-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="01f40-116">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="01f40-116">Parent Elements</span></span>  
  
|<span data-ttu-id="01f40-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="01f40-117">Element</span></span>|<span data-ttu-id="01f40-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="01f40-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="01f40-119">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="01f40-119">\<system.serviceModel.activation></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel-activation.md)|<span data-ttu-id="01f40-120">Contiene impostazioni di configurazione per il processo del listener SMSvcHost.exe.</span><span class="sxs-lookup"><span data-stu-id="01f40-120">Contains configuration settings for the listener process SMSvcHost.exe.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="01f40-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="01f40-121">See also</span></span>

- <xref:System.ServiceModel.Activation.Configuration.DiagnosticSection>

---
title: <diagnostics> per l'attivazione
ms.date: 03/30/2017
ms.assetid: 1486e0eb-fe2a-46c3-b584-c924889477dd
ms.openlocfilehash: 30456963a7d74a93e39bb1fddc0910daae97f039
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59203808"
---
# <a name="diagnostics-for-activation"></a><span data-ttu-id="db82a-102">\<diagnostica > per Activation</span><span class="sxs-lookup"><span data-stu-id="db82a-102">\<diagnostics> for Activation</span></span>
<span data-ttu-id="db82a-103">Configura le funzionalità di diagnostica del listener di Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="db82a-103">Configures Windows Communication Foundation (WCF) listener's diagnostics functionalities.</span></span>  
  
 <span data-ttu-id="db82a-104">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="db82a-104">\<system.serviceModel.activation></span></span>  
<span data-ttu-id="db82a-105">\<diagnostica ></span><span class="sxs-lookup"><span data-stu-id="db82a-105">\<diagnostics></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db82a-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="db82a-106">Syntax</span></span>  
  
```xml  
<configuration>
  <system.serviceModel.activation>
    <diagnostics performanceCountersEnabled="Boolean" />
  </system.serviceModel.activation>
</configuration>
```  
  
## <a name="type"></a><span data-ttu-id="db82a-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="db82a-107">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="db82a-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="db82a-108">Attributes and Elements</span></span>  
 <span data-ttu-id="db82a-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="db82a-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="db82a-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="db82a-110">Attributes</span></span>  
  
|<span data-ttu-id="db82a-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="db82a-111">Attribute</span></span>|<span data-ttu-id="db82a-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="db82a-112">Description</span></span>|  
|---------------|-----------------|  
|`performanceCountersEnabled`|<span data-ttu-id="db82a-113">Valore booleano che indica se sono i contatori delle prestazioni stati attivati a fini diagnostici.</span><span class="sxs-lookup"><span data-stu-id="db82a-113">A Boolean value that indicates whether performance counters are enabled for diagnostic purposes.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="db82a-114">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="db82a-114">Child Elements</span></span>  
 <span data-ttu-id="db82a-115">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="db82a-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="db82a-116">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="db82a-116">Parent Elements</span></span>  
  
|<span data-ttu-id="db82a-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="db82a-117">Element</span></span>|<span data-ttu-id="db82a-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="db82a-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="db82a-119">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="db82a-119">\<system.serviceModel.activation></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel-activation.md)|<span data-ttu-id="db82a-120">Contiene impostazioni di configurazione per il processo del listener SMSvcHost.exe.</span><span class="sxs-lookup"><span data-stu-id="db82a-120">Contains configuration settings for the listener process SMSvcHost.exe.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="db82a-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="db82a-121">See also</span></span>

- <xref:System.ServiceModel.Activation.Configuration.DiagnosticSection>

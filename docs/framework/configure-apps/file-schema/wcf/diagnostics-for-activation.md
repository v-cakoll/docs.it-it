---
title: '&lt;diagnostics&gt; per Activation'
ms.date: 03/30/2017
ms.assetid: 1486e0eb-fe2a-46c3-b584-c924889477dd
ms.openlocfilehash: 28f051a7ab06dbc1b40f804c56071818eb37e88b
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2019
ms.locfileid: "54144977"
---
# <a name="ltdiagnosticsgt-for-activation"></a><span data-ttu-id="78d21-102">&lt;diagnostics&gt; per Activation</span><span class="sxs-lookup"><span data-stu-id="78d21-102">&lt;diagnostics&gt; for Activation</span></span>
<span data-ttu-id="78d21-103">Configura le funzionalità di diagnostica del listener di Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="78d21-103">Configures Windows Communication Foundation (WCF) listener's diagnostics functionalities.</span></span>  
  
 <span data-ttu-id="78d21-104">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="78d21-104">\<system.serviceModel.activation></span></span>  
<span data-ttu-id="78d21-105">\<diagnostica ></span><span class="sxs-lookup"><span data-stu-id="78d21-105">\<diagnostics></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="78d21-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="78d21-106">Syntax</span></span>  
  
```xml  
<configuration>
  <system.serviceModel.activation>
    <diagnostics performanceCountersEnabled="Boolean" />
  </system.serviceModel.activation>
</configuration>
```  
  
## <a name="type"></a><span data-ttu-id="78d21-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="78d21-107">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="78d21-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="78d21-108">Attributes and Elements</span></span>  
 <span data-ttu-id="78d21-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="78d21-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="78d21-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="78d21-110">Attributes</span></span>  
  
|<span data-ttu-id="78d21-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="78d21-111">Attribute</span></span>|<span data-ttu-id="78d21-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="78d21-112">Description</span></span>|  
|---------------|-----------------|  
|`performanceCountersEnabled`|<span data-ttu-id="78d21-113">Valore booleano che indica se sono i contatori delle prestazioni stati attivati a fini diagnostici.</span><span class="sxs-lookup"><span data-stu-id="78d21-113">A Boolean value that indicates whether performance counters are enabled for diagnostic purposes.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="78d21-114">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="78d21-114">Child Elements</span></span>  
 <span data-ttu-id="78d21-115">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="78d21-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="78d21-116">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="78d21-116">Parent Elements</span></span>  
  
|<span data-ttu-id="78d21-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="78d21-117">Element</span></span>|<span data-ttu-id="78d21-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="78d21-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="78d21-119">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="78d21-119">\<system.serviceModel.activation></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel-activation.md)|<span data-ttu-id="78d21-120">Contiene impostazioni di configurazione per il processo del listener SMSvcHost.exe.</span><span class="sxs-lookup"><span data-stu-id="78d21-120">Contains configuration settings for the listener process SMSvcHost.exe.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="78d21-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="78d21-121">See Also</span></span>  
 <xref:System.ServiceModel.Activation.Configuration.DiagnosticSection>

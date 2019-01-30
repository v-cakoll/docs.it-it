---
title: <diagnostics> per l'attivazione
ms.date: 03/30/2017
ms.assetid: 1486e0eb-fe2a-46c3-b584-c924889477dd
ms.openlocfilehash: ac235b9a3c125cd3fe63ccd899e2ff92d4d3f31b
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55278451"
---
# <a name="diagnostics-for-activation"></a><span data-ttu-id="cfb7c-102">\<diagnostica > per Activation</span><span class="sxs-lookup"><span data-stu-id="cfb7c-102">\<diagnostics> for Activation</span></span>
<span data-ttu-id="cfb7c-103">Configura le funzionalità di diagnostica del listener di Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="cfb7c-103">Configures Windows Communication Foundation (WCF) listener's diagnostics functionalities.</span></span>  
  
 <span data-ttu-id="cfb7c-104">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="cfb7c-104">\<system.serviceModel.activation></span></span>  
<span data-ttu-id="cfb7c-105">\<diagnostica ></span><span class="sxs-lookup"><span data-stu-id="cfb7c-105">\<diagnostics></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cfb7c-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cfb7c-106">Syntax</span></span>  
  
```xml  
<configuration>
  <system.serviceModel.activation>
    <diagnostics performanceCountersEnabled="Boolean" />
  </system.serviceModel.activation>
</configuration>
```  
  
## <a name="type"></a><span data-ttu-id="cfb7c-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="cfb7c-107">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cfb7c-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="cfb7c-108">Attributes and Elements</span></span>  
 <span data-ttu-id="cfb7c-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="cfb7c-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cfb7c-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="cfb7c-110">Attributes</span></span>  
  
|<span data-ttu-id="cfb7c-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="cfb7c-111">Attribute</span></span>|<span data-ttu-id="cfb7c-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cfb7c-112">Description</span></span>|  
|---------------|-----------------|  
|`performanceCountersEnabled`|<span data-ttu-id="cfb7c-113">Valore booleano che indica se sono i contatori delle prestazioni stati attivati a fini diagnostici.</span><span class="sxs-lookup"><span data-stu-id="cfb7c-113">A Boolean value that indicates whether performance counters are enabled for diagnostic purposes.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cfb7c-114">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="cfb7c-114">Child Elements</span></span>  
 <span data-ttu-id="cfb7c-115">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="cfb7c-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="cfb7c-116">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="cfb7c-116">Parent Elements</span></span>  
  
|<span data-ttu-id="cfb7c-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="cfb7c-117">Element</span></span>|<span data-ttu-id="cfb7c-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cfb7c-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cfb7c-119">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="cfb7c-119">\<system.serviceModel.activation></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel-activation.md)|<span data-ttu-id="cfb7c-120">Contiene impostazioni di configurazione per il processo del listener SMSvcHost.exe.</span><span class="sxs-lookup"><span data-stu-id="cfb7c-120">Contains configuration settings for the listener process SMSvcHost.exe.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="cfb7c-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cfb7c-121">See also</span></span>
- <xref:System.ServiceModel.Activation.Configuration.DiagnosticSection>

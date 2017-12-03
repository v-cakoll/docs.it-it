---
title: '&lt;diagnostics&gt; per Activation'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1486e0eb-fe2a-46c3-b584-c924889477dd
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 1610c77125d2820e3adc06b3c37177058c85abdd
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="ltdiagnosticsgt-for-activation"></a><span data-ttu-id="5d859-102">&lt;diagnostics&gt; per Activation</span><span class="sxs-lookup"><span data-stu-id="5d859-102">&lt;diagnostics&gt; for Activation</span></span>
<span data-ttu-id="5d859-103">Configura le funzionalità di diagnostica del listener [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5d859-103">Configures [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] listener's diagnostics functionalities.</span></span>  
  
 <span data-ttu-id="5d859-104">\<system.serviceModel.activation ></span><span class="sxs-lookup"><span data-stu-id="5d859-104">\<system.serviceModel.activation></span></span>  
<span data-ttu-id="5d859-105">\<diagnostica ></span><span class="sxs-lookup"><span data-stu-id="5d859-105">\<diagnostics></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d859-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5d859-106">Syntax</span></span>  
  
```xml  
<configuration>  
   <system.serviceModel.activation>  
       <diagnostics performanceCountersEnabled="Boolean" />  
   </system.serviceModel.activation>  
</configuration>  
```  
  
## <a name="type"></a><span data-ttu-id="5d859-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="5d859-107">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5d859-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="5d859-108">Attributes and Elements</span></span>  
 <span data-ttu-id="5d859-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="5d859-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5d859-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="5d859-110">Attributes</span></span>  
  
|<span data-ttu-id="5d859-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="5d859-111">Attribute</span></span>|<span data-ttu-id="5d859-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5d859-112">Description</span></span>|  
|---------------|-----------------|  
|`performanceCountersEnabled`|<span data-ttu-id="5d859-113">Valore booleano che indica se sono i contatori delle prestazioni stati attivati a fini diagnostici.</span><span class="sxs-lookup"><span data-stu-id="5d859-113">A Boolean value that indicates whether performance counters are enabled for diagnostic purposes.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5d859-114">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="5d859-114">Child Elements</span></span>  
 <span data-ttu-id="5d859-115">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="5d859-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5d859-116">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="5d859-116">Parent Elements</span></span>  
  
|<span data-ttu-id="5d859-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="5d859-117">Element</span></span>|<span data-ttu-id="5d859-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5d859-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5d859-119">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="5d859-119">\<system.serviceModel.activation></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel-activation.md)|<span data-ttu-id="5d859-120">Contiene impostazioni di configurazione per il processo del listener SMSvcHost.exe.</span><span class="sxs-lookup"><span data-stu-id="5d859-120">Contains configuration settings for the listener process SMSvcHost.exe.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5d859-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5d859-121">See Also</span></span>  
 <xref:System.ServiceModel.Activation.Configuration.DiagnosticSection>

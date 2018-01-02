---
title: Schema delle impostazioni Web
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Web.config configuration file [ASP.NET]
- ASP.NET configuration system, Web settings schema
- schema Web settings
- Web settings, schema [ASP.NET]
- configuration files [ASP.NET]
- configuration schema [.NET Framework], Web settings
ms.assetid: ae1ac356-267d-4753-8d7a-7a04eb45a9be
caps.latest.revision: "6"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: a4ece61330fe8e41d9afb894791f9f9e36db35f2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="web-settings-schema"></a><span data-ttu-id="3bcb5-102">Schema delle impostazioni Web</span><span class="sxs-lookup"><span data-stu-id="3bcb5-102">Web Settings Schema</span></span>
<span data-ttu-id="3bcb5-103">Le impostazioni Web specificano le impostazioni di ASP.NET a livello di CPU e di esecuzione che si applicano al comportamento a livello di processo gestito dal livello di hosting ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="3bcb5-103">Web settings specify CPU and execution-level ASP.NET settings that apply to process-wide behavior managed by the ASP.NET hosting layer.</span></span> <span data-ttu-id="3bcb5-104">Queste impostazioni differiscono dalle impostazioni di tipo dominio dell'applicazione specificate nel file Web.config di un'applicazione ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="3bcb5-104">These settings differ from application domain-type settings that are specified in the Web.config file of an ASP.NET application.</span></span>  
  
 <span data-ttu-id="3bcb5-105">Le impostazioni Web sono contenute nei file Aspnet.config, disponibili nelle cartelle di installazione per le versioni di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3bcb5-105">Web settings are contained in Aspnet.config files, which are located in the installation folders for versions of the .NET Framework.</span></span> <span data-ttu-id="3bcb5-106">Ad esempio, il file Aspnet.config per [!INCLUDE[dnprdnext](../../../../../includes/dnprdnext-md.md)] si trova nella cartella seguente:</span><span class="sxs-lookup"><span data-stu-id="3bcb5-106">For example, the Aspnet.config file for [!INCLUDE[dnprdnext](../../../../../includes/dnprdnext-md.md)] is in the following folder:</span></span>  
  
 `C:\Windows\Microsoft.NET\Framework\v2.0.50727\`  
  
 <span data-ttu-id="3bcb5-107">Le impostazioni Web non vengono usate in altri file di configurazione, ad esempio il file machine.config, il file Web.config radice o i file Web.config a livello di applicazione.</span><span class="sxs-lookup"><span data-stu-id="3bcb5-107">Web settings are not used in any other configuration files such as the machine.config file, the root Web.config, or application-level Web.config files.</span></span>  
  
 [<span data-ttu-id="3bcb5-108">Elemento \<configuration></span><span class="sxs-lookup"><span data-stu-id="3bcb5-108">\<configuration> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)  
  
 [<span data-ttu-id="3bcb5-109">Elemento \<system.web> (impostazioni Web)</span><span class="sxs-lookup"><span data-stu-id="3bcb5-109">\<system.web> Element (Web Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/web/system-web-element-web-settings.md)  
  
 [<span data-ttu-id="3bcb5-110">Elemento \<applicationPool> (impostazioni Web)</span><span class="sxs-lookup"><span data-stu-id="3bcb5-110">\<applicationPool> Element (Web Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/web/applicationpool-element-web-settings.md)  
  
|<span data-ttu-id="3bcb5-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="3bcb5-111">Element</span></span>|<span data-ttu-id="3bcb5-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3bcb5-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3bcb5-113">\<system.web></span><span class="sxs-lookup"><span data-stu-id="3bcb5-113">\<system.web></span></span>](../../../../../docs/framework/configure-apps/file-schema/web/system-web-element-web-settings.md)|<span data-ttu-id="3bcb5-114">Contiene informazioni usate dal livello di hosting ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="3bcb5-114">Contains information that the ASP.NET hosting layer uses.</span></span>|  
|[<span data-ttu-id="3bcb5-115">\<applicationPool></span><span class="sxs-lookup"><span data-stu-id="3bcb5-115">\<applicationPool></span></span>](../../../../../docs/framework/configure-apps/file-schema/web/applicationpool-element-web-settings.md)|<span data-ttu-id="3bcb5-116">Specifica le impostazioni di ASP.NET a livello di CPU e di esecuzione che si applicano al comportamento a livello di processo gestito dal livello di hosting ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="3bcb5-116">Specifies CPU and execution-level ASP.NET settings that apply to process-wide behavior managed by the ASP.NET hosting layer.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3bcb5-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3bcb5-117">See Also</span></span>  
 [<span data-ttu-id="3bcb5-118">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="3bcb5-118">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)

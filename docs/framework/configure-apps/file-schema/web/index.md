---
title: Schema delle impostazioni Web
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Web.config configuration file [ASP.NET]
- ASP.NET configuration system, Web settings schema
- schema Web settings
- Web settings, schema [ASP.NET]
- configuration files [ASP.NET]
- configuration schema [.NET Framework], Web settings
ms.assetid: ae1ac356-267d-4753-8d7a-7a04eb45a9be
caps.latest.revision: 6
author: mcleblanc
ms.author: markl
manager: markl
ms.workload:
- dotnet
ms.openlocfilehash: a4ece61330fe8e41d9afb894791f9f9e36db35f2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="web-settings-schema"></a>Schema delle impostazioni Web
Le impostazioni Web specificano le impostazioni di ASP.NET a livello di CPU e di esecuzione che si applicano al comportamento a livello di processo gestito dal livello di hosting ASP.NET. Queste impostazioni differiscono dalle impostazioni di tipo dominio dell'applicazione specificate nel file Web.config di un'applicazione ASP.NET.  
  
 Le impostazioni Web sono contenute nei file Aspnet.config, disponibili nelle cartelle di installazione per le versioni di .NET Framework. Ad esempio, il file Aspnet.config per [!INCLUDE[dnprdnext](../../../../../includes/dnprdnext-md.md)] si trova nella cartella seguente:  
  
 `C:\Windows\Microsoft.NET\Framework\v2.0.50727\`  
  
 Le impostazioni Web non vengono usate in altri file di configurazione, ad esempio il file machine.config, il file Web.config radice o i file Web.config a livello di applicazione.  
  
 [Elemento \<configuration>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)  
  
 [Elemento \<system.web> (impostazioni Web)](../../../../../docs/framework/configure-apps/file-schema/web/system-web-element-web-settings.md)  
  
 [Elemento \<applicationPool> (impostazioni Web)](../../../../../docs/framework/configure-apps/file-schema/web/applicationpool-element-web-settings.md)  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<system.web>](../../../../../docs/framework/configure-apps/file-schema/web/system-web-element-web-settings.md)|Contiene informazioni usate dal livello di hosting ASP.NET.|  
|[\<applicationPool>](../../../../../docs/framework/configure-apps/file-schema/web/applicationpool-element-web-settings.md)|Specifica le impostazioni di ASP.NET a livello di CPU e di esecuzione che si applicano al comportamento a livello di processo gestito dal livello di hosting ASP.NET.|  
  
## <a name="see-also"></a>Vedere anche  
 [Schema dei file di configurazione](../../../../../docs/framework/configure-apps/file-schema/index.md)

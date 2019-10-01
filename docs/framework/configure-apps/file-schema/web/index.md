---
title: Schema delle impostazioni Web
ms.date: 03/30/2017
helpviewer_keywords:
- Web.config configuration file [ASP.NET]
- ASP.NET configuration system, Web settings schema
- schema Web settings
- Web settings, schema [ASP.NET]
- configuration files [ASP.NET]
- configuration schema [.NET Framework], Web settings
ms.assetid: ae1ac356-267d-4753-8d7a-7a04eb45a9be
ms.openlocfilehash: 71b9e46a8c2d60c853af63ee78e2ed5dbe6e98f4
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2019
ms.locfileid: "71699143"
---
# <a name="web-settings-schema"></a>Schema delle impostazioni Web
Le impostazioni Web specificano le impostazioni di ASP.NET a livello di CPU e di esecuzione che si applicano al comportamento a livello di processo gestito dal livello di hosting ASP.NET. Queste impostazioni differiscono dalle impostazioni di tipo dominio dell'applicazione specificate nel file Web.config di un'applicazione ASP.NET.  
  
Le impostazioni Web sono contenute nei file Aspnet.config, disponibili nelle cartelle di installazione per le versioni di .NET Framework. Il file Aspnet. config per .NET Framework 2,0, ad esempio, si trova nella cartella seguente:  
  
`C:\Windows\Microsoft.NET\Framework\v2.0.50727\`  
  
Le impostazioni Web non vengono usate in altri file di configurazione, ad esempio il file machine.config, il file Web.config radice o i file Web.config a livello di applicazione.  
  
[ **\<configuration>** ](../configuration-element.md)  
&nbsp; @ no__t-1[ **@no__t -4system. Web >** ](system-web-element-web-settings.md)  
&nbsp; @ no__t-1 @ no__t-2 @ no__t-3[ **\<applicationPool >** ](applicationpool-element-web-settings.md)  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<system.web>](system-web-element-web-settings.md)|Contiene informazioni usate dal livello di hosting ASP.NET.|  
|[\<applicationPool>](applicationpool-element-web-settings.md)|Specifica le impostazioni di ASP.NET a livello di CPU e di esecuzione che si applicano al comportamento a livello di processo gestito dal livello di hosting ASP.NET.|  
  
## <a name="see-also"></a>Vedere anche

- [Schema dei file di configurazione](../index.md)

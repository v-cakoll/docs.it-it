---
title: '&lt;configurazione&gt; elemento'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration
helpviewer_keywords:
- <configuration> element
- configuration element
- container tags, <configuration> element
ms.assetid: 2ec1c9dc-2e5c-4ef0-9958-81670ab88449
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 40c0ab5f18d5aae2c99dd66747d3435f0826af8b
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/25/2018
ms.locfileid: "47171270"
---
# <a name="configuration-element"></a>\<configurazione > elemento

Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.

**\<configuration>**

## <a name="syntax"></a>Sintassi

```xml
<configuration>
  <!-- Configuration settings -->
</configuration>
```

## <a name="attributes"></a>Attributi

nessuno

## <a name="parent-element"></a>Elemento padre

nessuno

## <a name="child-elements"></a>Elementi figlio

|     | Descrizione |
| --- | ----------- |
| [**\<assemblyBinding >**](~/docs/framework/configure-apps/file-schema/assemblybinding-element-for-configuration.md) | Specifica i criteri di associazione degli assembly al livello di configurazione.|
| [**\<avvio >** Schema delle impostazioni](~/docs/framework/configure-apps/file-schema/startup/index.md) | Tutti gli elementi nello schema delle impostazioni di avvio. |
| [**\<runtime >** Schema delle impostazioni](~/docs/framework/configure-apps/file-schema/runtime/index.md) | Tutti gli elementi nello schema delle impostazioni di runtime. |
| [**\<Remoting >** Schema delle impostazioni](https://msdn.microsoft.com/dc2d1e62-9af7-4ca1-99fd-98b93bb4db9e) | Tutti gli elementi nello schema delle impostazioni di comunicazione remota. |
| [**\<system.Net >** Schema delle impostazioni](~/docs/framework/configure-apps/file-schema/network/index.md) | Tutti gli elementi nello schema delle impostazioni di rete. |
| [**\<cryptographySettings >** Schema delle impostazioni](~/docs/framework/configure-apps/file-schema/cryptography/index.md) | Tutti gli elementi nello schema delle impostazioni di crittografia. |
| [**\<configurazione >** Schema delle sezioni](~/docs/framework/configure-apps/file-schema/configuration-sections-schema.md) | Tutti gli elementi nello schema delle impostazioni di sezione di configurazione. |
| [Schema delle impostazioni di traccia e debug](~/docs/framework/configure-apps/file-schema/trace-debug/index.md) | Tutti gli elementi nello schema di impostazioni di traccia e debug. |
| [Schema delle impostazioni di configurazione ASP.NET](https://msdn.microsoft.com/library/b5ysx397(v=vs.100).aspx) | Tutti gli elementi nello schema di configurazione ASP.NET, che include gli elementi per la configurazione di applicazioni e siti Web ASP.NET. Usato nel *Web. config* file. |
| [**\<webServices >** Schema delle impostazioni](https://msdn.microsoft.com/f84d6d55-1add-4eb7-ae46-33df5833ea2e) | Tutti gli elementi nello schema delle impostazioni di servizi Web. |
| [Schema delle impostazioni Web](~/docs/framework/configure-apps/file-schema/web/index.md) | Tutti gli elementi nello schema delle impostazioni Web, che include gli elementi per la configurazione del funzionamento di ASP.NET con un'applicazione host, come IIS. Usato nel *ASPNET* file. |

## <a name="remarks"></a>Note

Ogni file di configurazione deve contenere un unico  **\<configuration >** elemento.

## <a name="see-also"></a>Vedere anche

[Schema di file di configurazione per .NET Framework](~/docs/framework/configure-apps/file-schema/index.md)

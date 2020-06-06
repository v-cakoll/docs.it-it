---
title: Elemento <configuration>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration
helpviewer_keywords:
- <configuration> element
- configuration element
- container tags, <configuration> element
ms.assetid: 2ec1c9dc-2e5c-4ef0-9958-81670ab88449
ms.openlocfilehash: 0e09ec49024b769c516fd97085904781f64b4486
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "69921242"
---
# <a name="configuration-element"></a>Elemento \<configuration>

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
| [**\<assemblyBinding>**](assemblybinding-element-for-configuration.md) | Specifica i criteri di associazione degli assembly al livello di configurazione.|
| [**\<startup>** Schema delle impostazioni](./startup/index.md) | Tutti gli elementi nello schema delle impostazioni di avvio. |
| [**\<runtime>** Schema delle impostazioni](./runtime/index.md) | Tutti gli elementi nello schema delle impostazioni di Runtime. |
| [**\<system.runtime.remoting>** Schema delle impostazioni](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/z415cf9a(v=vs.100)) | Tutti gli elementi nello schema delle impostazioni remote. |
| [**\<system.Net>** Schema delle impostazioni](./network/index.md) | Tutti gli elementi nello schema delle impostazioni di rete. |
| [**\<cryptographySettings>** Schema delle impostazioni](./cryptography/index.md) | Tutti gli elementi nello schema delle impostazioni di crittografia. |
| [**\<configuration>** Schema delle sezioni](configuration-sections-schema.md) | Tutti gli elementi nello schema delle impostazioni della sezione di configurazione. |
| [Schema delle impostazioni di traccia e debug](./trace-debug/index.md) | Tutti gli elementi nello schema delle impostazioni di traccia e debug. |
| [Schema delle impostazioni di configurazione di ASP.NET](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/b5ysx397(v=vs.100)) | Tutti gli elementi nello schema di configurazione di ASP.NET, che include elementi per la configurazione di applicazioni e siti Web di ASP.NET. Utilizzato nei file *Web. config* . |
| [**\<webServices>** Schema delle impostazioni](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cctwteet(v=vs.100)) | Tutti gli elementi nello schema delle impostazioni dei servizi Web. |
| [Schema delle impostazioni Web](./web/index.md) | Tutti gli elementi nello schema delle impostazioni Web, che include gli elementi per la configurazione del funzionamento di ASP.NET con un'applicazione host, come IIS. Utilizzato nei file *ASPNET. config* . |

## <a name="remarks"></a>Commenti

Ogni file di configurazione deve contenere esattamente un **\<configuration>** elemento.

## <a name="see-also"></a>Vedi anche

- [Schema del file di configurazione per il .NET Framework](index.md)

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
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69921242"
---
# <a name="configuration-element"></a>\<Configuration >-elemento

Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.

**\<configuration>**

## <a name="syntax"></a>Sintassi

```xml
<configuration>
  <!-- Configuration settings -->
</configuration>
```

## <a name="attributes"></a>Attributi

Nessuna

## <a name="parent-element"></a>Elemento padre

Nessuna

## <a name="child-elements"></a>Elementi figlio

|     | Descrizione |
| --- | ----------- |
| [ **\<assemblyBinding>** ](assemblybinding-element-for-configuration.md) | Specifica i criteri di associazione degli assembly al livello di configurazione.|
| [Schema delle impostazioni del > di avvio  **\<** ](./startup/index.md) | Tutti gli elementi nello schema delle impostazioni di avvio. |
| [Schema delle impostazioni del > di runtime  **\<** ](./runtime/index.md) | Tutti gli elementi nello schema delle impostazioni di Runtime. |
| [Schema delle impostazioni di **> System. Runtime. Remoting \<** ](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/z415cf9a(v=vs.100)) | Tutti gli elementi nello schema delle impostazioni remote. |
| [Schema delle impostazioni di **System .net > \<** ](./network/index.md) | Tutti gli elementi nello schema delle impostazioni di rete. |
| [Schema delle impostazioni > cryptographySettings  **\<** ](./cryptography/index.md) | Tutti gli elementi nello schema delle impostazioni di crittografia. |
| [Schema delle sezioni di > di configurazione  **\<** ](configuration-sections-schema.md) | Tutti gli elementi nello schema delle impostazioni della sezione di configurazione. |
| [Schema delle impostazioni di traccia e debug](./trace-debug/index.md) | Tutti gli elementi nello schema delle impostazioni di traccia e debug. |
| [Schema delle impostazioni di configurazione di ASP.NET](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/b5ysx397(v=vs.100)) | Tutti gli elementi nello schema di configurazione di ASP.NET, che include elementi per la configurazione di applicazioni e siti Web di ASP.NET. Utilizzato nei file *Web. config* . |
| [Schema delle impostazioni di > WebServices  **\<** ](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cctwteet(v=vs.100)) | Tutti gli elementi nello schema delle impostazioni dei servizi Web. |
| [Schema delle impostazioni Web](./web/index.md) | Tutti gli elementi nello schema delle impostazioni Web, che include gli elementi per la configurazione del funzionamento di ASP.NET con un'applicazione host, come IIS. Utilizzato nei file *ASPNET. config* . |

## <a name="remarks"></a>Note

Ogni file di configurazione deve contenere esattamente un  **\<elemento Configuration >** .

## <a name="see-also"></a>Vedere anche

- [Schema del file di configurazione per il .NET Framework](index.md)

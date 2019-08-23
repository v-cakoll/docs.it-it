---
title: Elemento <remove> per <appSettings>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings/remove
helpviewer_keywords:
- remove Element
- <remove> Element
ms.assetid: 218c4464-e007-4539-803f-7c8b0a909fd8
author: rpetrusha
ms.author: mairaw
ms.openlocfilehash: 121b1c4b124ba07ff3bd312fd3832d3da592f486
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69921286"
---
# <a name="remove-element-for-appsettings"></a>\<Rimuovi elemento > per \<appSettings >

Rimuove le impostazioni dell'applicazione personalizzata.

[ **\<configuration>** ](../configuration-element.md)   
&nbsp;&nbsp;[ **\<appSettings >** ](appsettings-element-for-configuration.md)   
&nbsp;&nbsp;&nbsp;&nbsp; **\<remove>**

## <a name="syntax"></a>Sintassi

```xml
<appSettings>
  <remove key="Key of custom setting" />
</appSettings>
```

### <a name="attribute"></a>Attributo

|         | DESCRIZIONE |
| ------- | ----------- |
| **key** | Attributo obbligatorio.<br><br>Specifica il nome della chiave da rimuovere. |

### <a name="parent-element"></a>Elemento padre

|     | Descrizione |
| --- | ----------- |
| [ **\<appSettings>** ](appsettings-element-for-configuration.md) | Contiene le impostazioni dell'applicazione personalizzate, ad esempio i percorsi di file, gli URL del servizio Web XML o qualsiasi altra informazione di configurazione personalizzata per un'applicazione. |

## <a name="child-elements"></a>Elementi figlio

Nessuna

## <a name="example"></a>Esempio

Nell'esempio seguente viene illustrato come rimuovere un'impostazione di configurazione personalizzata `ApplicationName`per:

```xml
<appSettings>
  <remove key="ApplicationName" />
</appSettings>
```

## <a name="see-also"></a>Vedere anche

- [Schema del file di configurazione per il .NET Framework](../index.md)

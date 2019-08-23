---
title: Elemento <clear> per <appSettings>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings/clear
helpviewer_keywords:
- clear Element
- <clear> Element
ms.assetid: 6d18c7be-27db-438b-8fb5-765d396b0b7b
author: rpetrusha
ms.author: mairaw
ms.openlocfilehash: 5d5da531bff3a0e9e198ba9b5ab6cf2b52bf36b5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69921305"
---
# <a name="clear-element-for-appsettings"></a>\<Cancella > elemento per \<appSettings >

Cancella le impostazioni dell'applicazione personalizzata.

[ **\<configuration>** ](../configuration-element.md)   
&nbsp;&nbsp;[ **\<appSettings >** ](appsettings-element-for-configuration.md)   
&nbsp;&nbsp;&nbsp;&nbsp; **\<clear>**

## <a name="syntax"></a>Sintassi

```xml
<appSettings>
  <clear />
</appSettings>
```

## <a name="attributes"></a>Attributi

Nessuna

## <a name="parent-element"></a>Elemento padre

|     | Descrizione |
| --- | ----------- |
| [ **\<appSettings>** ](appsettings-element-for-configuration.md) | Contiene le impostazioni dell'applicazione personalizzate, ad esempio i percorsi di file, gli URL del servizio Web XML o qualsiasi altra informazione di configurazione dell'applicazione personalizzata. |

## <a name="child-elements"></a>Elementi figlio

Nessuna

## <a name="example"></a>Esempio

Nell'esempio seguente viene illustrato come cancellare le impostazioni di configurazione personalizzate:

```xml
<appSettings>
  <clear />
</appSettings>
```

## <a name="see-also"></a>Vedere anche

- [Schema del file di configurazione per il .NET Framework](../index.md)

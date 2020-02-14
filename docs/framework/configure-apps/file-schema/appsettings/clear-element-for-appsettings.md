---
title: Elemento <clear> per <appSettings>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings/clear
helpviewer_keywords:
- clear Element
- <clear> Element
ms.assetid: 6d18c7be-27db-438b-8fb5-765d396b0b7b
ms.openlocfilehash: 266d32ccb8b322f0472e0f552f9c0fc877c9a78e
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "77214780"
---
# <a name="clear-element-for-appsettings"></a>\<elemento clear > per \<appSettings >

Cancella le impostazioni dell'applicazione personalizzata.

[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<appSettings >** ](appsettings-element-for-configuration.md)\
&nbsp;&nbsp;&nbsp;&nbsp; **\<cancella >**

## <a name="syntax"></a>Sintassi

```xml
<appSettings>
  <clear />
</appSettings>
```

## <a name="attributes"></a>Attributes

nessuno

## <a name="parent-element"></a>Elemento padre

|     | Descrizione |
| --- | ----------- |
| [ **\<appSettings>** ](appsettings-element-for-configuration.md) | Contiene le impostazioni dell'applicazione personalizzate, ad esempio i percorsi di file, gli URL del servizio Web XML o qualsiasi altra informazione di configurazione dell'applicazione personalizzata. |

## <a name="child-elements"></a>Elementi figlio

nessuno

## <a name="example"></a>Esempio

Nell'esempio seguente viene illustrato come cancellare le impostazioni di configurazione personalizzate:

```xml
<appSettings>
  <clear />
</appSettings>
```

## <a name="see-also"></a>Vedere anche

- [Schema del file di configurazione per il .NET Framework](../index.md)

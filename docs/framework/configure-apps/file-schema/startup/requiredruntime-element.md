---
title: Elemento <requiredRuntime>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#requiredRuntime
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/startup/requiredRuntime
helpviewer_keywords:
- requiredRuntime element
- <requiredRuntime> element
- container tags, <requiredRuntime> element
ms.assetid: 9fa1639e-beb8-43be-b7a4-12f7b229c34b
ms.openlocfilehash: fe96673b95f48cb75d36662a680bf56a59363f9f
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "71697491"
---
# <a name="requiredruntime-element"></a>Elemento \<requiredRuntime>

Specifica che l'applicazione supporta solo la versione 1.0 di Common Language Runtime. Questo elemento è deprecato e non deve più essere utilizzato. In [`supportedRuntime`](supportedruntime-element.md) alternativa, è necessario usare l'elemento.

[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<startup>**](startup-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;**\<requiredRuntime>**  

## <a name="syntax"></a>Sintassi

```xml
   <requiredRuntime  
version="runtime version"
safemode="true|false"/>
```

## <a name="attributes-and-elements"></a>Attributi ed elementi

Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.

### <a name="attributes"></a>Attributi

|Attributo|Descrizione|
|---------------|-----------------|
|`version`|Attributo facoltativo.<br /><br /> Valore stringa che specifica la versione del .NET Framework supportata da questa applicazione. Il valore stringa deve corrispondere al nome di directory trovato nella radice di installazione .NET Framework. Il contenuto del valore stringa non viene analizzato.|
|`safemode`|Attributo facoltativo.<br /><br /> Specifica se il codice di avvio del runtime cerca il registro di sistema per determinare la versione di Runtime.|

## <a name="safemode-attribute"></a>attributo modalità provvisoria

|Valore|Description|
|-----------|-----------------|
|`false`|Il codice di avvio runtime cerca nel registro di sistema. Si tratta del valore predefinito.|
|`true`|Il codice di avvio del runtime non cerca nel registro di sistema.|

### <a name="child-elements"></a>Elementi figlio

No.

### <a name="parent-elements"></a>Elementi padre

|Elemento|Descrizione|
|-------------|-----------------|
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|
|`startup`|Contiene l' `<requiredRuntime>` elemento.|

## <a name="remarks"></a>Commenti
 Le applicazioni compilate per supportare solo la versione 1,0 del runtime devono usare l' `<requiredRuntime>` elemento. Le applicazioni compilate con la versione 1,1 o successive del runtime devono usare l' `<supportedRuntime>` elemento.

> [!NOTE]
> Se si usa la funzione [CorBindToRuntimeByCfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md) per specificare il file di configurazione, è necessario usare l' `<requiredRuntime>` elemento per tutte le versioni del runtime. L' `<supportedRuntime>` elemento viene ignorato quando si utilizza [CorBindToRuntimeByCfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md).

 La `version` stringa dell'attributo deve corrispondere al nome della cartella di installazione per la versione specificata del .NET Framework. Questa stringa non viene interpretata. Se il codice di avvio del runtime non trova una cartella corrispondente, il runtime non viene caricato. il codice di avvio Mostra un messaggio di errore e viene chiuso.

> [!NOTE]
> Il codice di avvio per un'applicazione ospitata in Microsoft Internet Explorer ignora l' `<requiredRuntime>` elemento.

## <a name="example"></a>Esempio

Nell'esempio seguente viene illustrato come specificare la versione del runtime in un file di configurazione.

```xml
<configuration>
   <startup>
      <requiredRuntime version="v1.0.3705" safemode="true"/>
   </startup>
</configuration>
```

## <a name="see-also"></a>Vedi anche

- [Schema delle impostazioni di avvio](index.md)
- [Schema del file di configurazione](../index.md)
- [Procedura: configurare un'app per supportare .NET Framework 4 o versioni successive](../../../migration-guide/how-to-configure-an-app-to-support-net-framework-4-or-4-5.md)

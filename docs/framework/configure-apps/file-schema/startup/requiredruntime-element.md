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
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2019
ms.locfileid: "71697491"
---
# <a name="requiredruntime-element"></a>elemento > \<requiredRuntime

Specifica che l'applicazione supporta solo la versione 1.0 di Common Language Runtime. Questo elemento è deprecato e non deve più essere utilizzato. In alternativa, è necessario usare l'elemento [`supportedRuntime`](supportedruntime-element.md) .

[ **\<configuration>** ](../configuration-element.md)  
&nbsp; @ no__t-1[ **\<startup >** ](startup-element.md)  
&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 **\<requiredRuntime >**  

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

|Value|Descrizione|
|-----------|-----------------|
|`false`|Il codice di avvio runtime cerca nel registro di sistema. Rappresenta il valore predefinito.|
|`true`|Il codice di avvio del runtime non cerca nel registro di sistema.|

### <a name="child-elements"></a>Elementi figlio

No.

### <a name="parent-elements"></a>Elementi padre

|Elemento|Descrizione|
|-------------|-----------------|
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|
|`startup`|Contiene l' `<requiredRuntime>` elemento.|

## <a name="remarks"></a>Note
 Le applicazioni compilate per supportare solo la versione 1,0 del runtime devono usare l'elemento `<requiredRuntime>`. Le applicazioni compilate con la versione 1,1 o successive del runtime devono usare l'elemento `<supportedRuntime>`.

> [!NOTE]
> Se si usa la funzione [CorBindToRuntimeByCfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md) per specificare il file di configurazione, è necessario usare l'elemento `<requiredRuntime>` per tutte le versioni del runtime. L'elemento `<supportedRuntime>` viene ignorato quando si utilizza [CorBindToRuntimeByCfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md).

 La stringa dell'attributo `version` deve corrispondere al nome della cartella di installazione per la versione specificata del .NET Framework. Questa stringa non viene interpretata. Se il codice di avvio del runtime non trova una cartella corrispondente, il runtime non viene caricato. il codice di avvio Mostra un messaggio di errore e viene chiuso.

> [!NOTE]
> Il codice di avvio per un'applicazione ospitata in Microsoft Internet Explorer ignora l'elemento `<requiredRuntime>`.

## <a name="example"></a>Esempio

Nell'esempio seguente viene illustrato come specificare la versione del runtime in un file di configurazione.

```xml
<configuration>
   <startup>
      <requiredRuntime version="v1.0.3705" safemode="true"/>
   </startup>
</configuration>
```

## <a name="see-also"></a>Vedere anche

- [Schema delle impostazioni di avvio](index.md)
- [Schema dei file di configurazione](../index.md)
- [Procedura: Configurare un'app per supportare .NET Framework 4 o versioni successive](../../../migration-guide/how-to-configure-an-app-to-support-net-framework-4-or-4-5.md)

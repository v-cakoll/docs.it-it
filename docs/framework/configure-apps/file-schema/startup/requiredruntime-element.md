---
title: elemento <requiredRuntime>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#requiredRuntime
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/startup/requiredRuntime
helpviewer_keywords:
- requiredRuntime element
- <requiredRuntime> element
- container tags, <requiredRuntime> element
ms.assetid: 9fa1639e-beb8-43be-b7a4-12f7b229c34b
ms.openlocfilehash: 5e528a8b81fa3d9abc4f345d18f01e33f483a4a9
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55254730"
---
# <a name="requiredruntime-element"></a>\<requiredRuntime > elemento

Specifica che l'applicazione supporta solo la versione 1.0 di Common Language Runtime. Questo elemento è deprecato e non deve più essere utilizzato. Il [ `supportedRuntime` ](supportedruntime-element.md) elemento deve essere usato invece.

\<configuration> \<startup> \<requiredRuntime>

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
|`version`|Attributo facoltativo.<br /><br /> Valore stringa che specifica la versione di .NET Framework supportata dall'applicazione. Il valore della stringa deve corrispondere al nome di directory trovato nella directory radice di installazione di .NET Framework. Il contenuto del valore della stringa non viene analizzato.|
|`safemode`|Attributo facoltativo.<br /><br /> Specifica se il codice di avvio di runtime cerca il Registro di sistema per determinare la versione di runtime.|

## <a name="safemode-attribute"></a>attributo di modalità provvisoria

|Valore|Descrizione|
|-----------|-----------------|
|`false`|Il codice di avvio di runtime cerca nel Registro di sistema. Rappresenta il valore predefinito.|
|`true`|Il codice di avvio del runtime non cercare nel Registro di sistema.|

### <a name="child-elements"></a>Elementi figlio

Nessuno.

### <a name="parent-elements"></a>Elementi padre

|Elemento|Descrizione|
|-------------|-----------------|
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|
|`startup`|Contiene il `<requiredRuntime>` elemento.|

## <a name="remarks"></a>Note
 Le applicazioni create per supportare solo la versione 1.0 del runtime è necessario usare il `<requiredRuntime>` elemento. Le applicazioni compilate con la versione 1.1 o versione successiva del runtime devono usare il `<supportedRuntime>` elemento.

> [!NOTE]
> Se si usa la [CorBindToRuntimeByCfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md) funzione per specificare il file di configurazione, è necessario usare il `<requiredRuntime>` (elemento) per tutte le versioni del runtime. Il `<supportedRuntime>` elemento viene ignorato quando si usa [CorBindToRuntimeByCfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md).

 Il `version` stringa dell'attributo deve corrispondere al nome di cartella di installazione per la versione specificata di .NET Framework. Questa stringa non viene interpretata. Se il codice di avvio del runtime non trova una cartella corrispondente, il runtime non viene caricato; il codice di avvio Mostra un messaggio di errore e viene chiusa.

> [!NOTE]
> Il codice di avvio per un'applicazione ospitata in Microsoft Internet Explorer ignora il `<requiredRuntime>` elemento.

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
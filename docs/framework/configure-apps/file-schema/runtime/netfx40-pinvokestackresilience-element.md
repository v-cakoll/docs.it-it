---
title: Elemento < NetFx40_PInvokeStackResilience >
ms.date: 03/30/2017
helpviewer_keywords:
- <NetFx40_PInvokeStackResilience> element
- NetFx40_PInvokeStackResilience element
ms.assetid: 39fb1588-72a4-4479-af74-0605233b68bd
ms.openlocfilehash: 86f50aafe0b21d5080288e09ac7118ca1e4c939a
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "73116156"
---
# <a name="netfx40_pinvokestackresilience-element"></a>\<NetFx40_PInvokeStackResilience> Elemento

Specifica se il runtime corregge automaticamente le dichiarazioni platform invoke non corrette in fase di esecuzione, al costo di transizioni più lente tra codice gestito e quello non gestito.

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<NetFx40_PInvokeStackResilience>**  

## <a name="syntax"></a>Sintassi

```xml
<NetFx40_PInvokeStackResilience  enabled="1|0"/>
```

## <a name="attributes-and-elements"></a>Attributi ed elementi

Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.

### <a name="attributes"></a>Attributi

|Attributo|Descrizione|
|---------------|-----------------|
|`enabled`|Attributo obbligatorio.<br /><br /> Specifica se il runtime rileva dichiarazioni di platform invoke non corrette e corregge automaticamente lo stack in fase di esecuzione sulle piattaforme a 32 bit.|

## <a name="enabled-attribute"></a>Attributo enabled

|Valore|Description|
|-----------|-----------------|
|`0`|Il runtime usa l'architettura di marshalling di interoperabilità più veloce introdotta in .NET Framework 4, che non rileva e corregge platform invoke dichiarazioni non corrette. Questo è il valore predefinito.|
|`1`|Il runtime utilizza transizioni più lente che rilevano e correggono dichiarazioni di platform invoke non corrette.|

### <a name="child-elements"></a>Elementi figlio

No.

### <a name="parent-elements"></a>Elementi padre

|Elemento|Descrizione|
|-------------|-----------------|
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|
|`runtime`|Contiene informazioni sulle opzioni di inizializzazione in fase di esecuzione.|

## <a name="remarks"></a>Commenti

Questo elemento consente di effettuare il marshalling di interoperabilità più veloce per la resilienza in fase di esecuzione rispetto a dichiarazioni platform invoke non corrette.

A partire da .NET Framework 4, un'architettura di marshalling di interoperabilità semplificata offre un miglioramento significativo delle prestazioni per le transizioni dal codice gestito al codice non gestito. Nelle versioni precedenti del .NET Framework il livello di marshalling ha rilevato dichiarazioni di platform invoke non corrette sulle piattaforme a 32 bit e ha corretto automaticamente lo stack. La nuova architettura di marshalling elimina questo passaggio. Di conseguenza, le transizioni sono molto veloci, ma una dichiarazione di platform invoke non corretta può causare un errore del programma.

Per semplificare il rilevamento di dichiarazioni non corrette durante lo sviluppo, è stata migliorata l'esperienza di debug di Visual Studio. L'assistente al debug gestito [pInvokeStackImbalance](../../../debug-trace-profile/pinvokestackimbalance-mda.md) Invia notifiche di Platform Invoke non corrette quando l'applicazione è in esecuzione con il debugger collegato.

Per risolvere scenari in cui l'applicazione usa componenti che non è possibile ricompilare e che contengono dichiarazioni di platform invoke non corrette, è possibile usare l' `NetFx40_PInvokeStackResilience` elemento. L'aggiunta di questo elemento al file di configurazione dell'applicazione con `enabled="1"` opta in una modalità di compatibilità con il comportamento delle versioni precedenti del .NET Framework, a scapito delle transizioni più lente. Gli assembly compilati con versioni precedenti del .NET Framework vengono automaticamente scelti in questa modalità di compatibilità e non richiedono questo elemento.

## <a name="configuration-file"></a>File di configurazione

Questo elemento può essere utilizzato solo nel file di configurazione dell'applicazione.

## <a name="example"></a>Esempio

Nell'esempio seguente viene illustrato come scegliere una maggiore resilienza in caso di dichiarazioni di platform invoke non corrette per un'applicazione, al costo di transizioni più lente tra codice gestito e non gestito.

```xml
<configuration>
   <runtime>
      <NetFx40_PInvokeStackResilience enabled="1"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a>Vedi anche

- [Schema delle impostazioni di runtime](index.md)
- [Schema del file di configurazione](../index.md)
- [pInvokeStackImbalance](../../../debug-trace-profile/pinvokestackimbalance-mda.md)

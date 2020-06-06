---
title: Elemento <TimeSpan_LegacyFormatMode>
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- <TimeSpan_LegacyFormatMode> element
- TimeSpan_LegacyFormatMode element
ms.assetid: 865e7207-d050-4442-b574-57ea29d5e2d6
ms.openlocfilehash: 9d9eedf52f5d711412e4549e39e6ea23abb68ff3
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "73968902"
---
# <a name="timespan_legacyformatmode-element"></a>\<TimeSpan_LegacyFormatMode> Elemento

Determina se il runtime conserva il comportamento legacy nelle operazioni di formattazione con <xref:System.TimeSpan?displayProperty=nameWithType> i valori.

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<TimeSpan_LegacyFormatMode>**  

## <a name="syntax"></a>Sintassi

```xml
<TimeSpan_LegacyFormatMode
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a>Attributi ed elementi

Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.

### <a name="attributes"></a>Attributi

|Attributo|Descrizione|
|---------------|-----------------|
|`enabled`|Attributo obbligatorio.<br /><br /> Specifica se il runtime usa il comportamento di formattazione legacy con <xref:System.TimeSpan?displayProperty=nameWithType> i valori.|

## <a name="enabled-attribute"></a>Attributo enabled

|Valore|Description|
|-----------|-----------------|
|`false`|Il runtime non ripristina il comportamento di formattazione legacy.|
|`true`|Il runtime ripristina il comportamento di formattazione legacy.|

### <a name="child-elements"></a>Elementi figlio

No.

### <a name="parent-elements"></a>Elementi padre

|Elemento|Descrizione|
|-------------|-----------------|
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|
|`runtime`|Contiene informazioni sulle opzioni di inizializzazione in fase di esecuzione.|

## <a name="remarks"></a>Commenti

A partire da .NET Framework 4, la <xref:System.TimeSpan?displayProperty=nameWithType> struttura implementa l' <xref:System.IFormattable> interfaccia e supporta le operazioni di formattazione con stringhe di formato standard e personalizzate. Se un metodo di analisi rileva un identificatore di formato non supportato o una stringa di formato, viene generata un'eccezione <xref:System.FormatException> .

Nelle versioni precedenti del .NET Framework la <xref:System.TimeSpan> struttura non implementava e non <xref:System.IFormattable> supportava le stringhe di formato. Tuttavia, molti sviluppatori presumevano erroneamente che <xref:System.TimeSpan> supportivano un set di stringhe di formato e le usavano in [operazioni di formattazione composita](../../../../standard/base-types/composite-formatting.md) con metodi come <xref:System.String.Format%2A?displayProperty=nameWithType> . In genere, se un tipo implementa <xref:System.IFormattable> e supporta le stringhe di formato, le chiamate ai metodi di formattazione con stringhe di formato non supportate in genere generano una <xref:System.FormatException> . Tuttavia, poiché <xref:System.TimeSpan> non ha implementato <xref:System.IFormattable> , il runtime ignora la stringa di formato e chiama invece il <xref:System.TimeSpan.ToString?displayProperty=nameWithType> metodo. Ciò significa che, anche se le stringhe di formato non hanno effetto sull'operazione di formattazione, la loro presenza non ha restituito un <xref:System.FormatException> .

Per i casi in cui il codice legacy passa un metodo di formattazione composita e una stringa di formato non valida e tale codice non può essere ricompilato, è possibile usare l' `<TimeSpan_LegacyFormatMode>` elemento per ripristinare il <xref:System.TimeSpan> comportamento legacy. Quando si imposta l' `enabled` attributo di questo elemento su `true` , il metodo di formattazione composita genera una chiamata a <xref:System.TimeSpan.ToString?displayProperty=nameWithType> anziché <xref:System.TimeSpan.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType> e <xref:System.FormatException> non viene generata un'eccezione.

## <a name="example"></a>Esempio

Nell'esempio seguente viene creata un'istanza di un <xref:System.TimeSpan> oggetto e viene effettuato un tentativo di formattarlo con il <xref:System.String.Format%28System.String%2CSystem.Object%29?displayProperty=nameWithType> metodo utilizzando una stringa di formato standard non supportata.

[!code-csharp[TimeSpan.BreakingChanges#1](../../../../../samples/snippets/csharp/VS_Snippets_CLR/timespan.breakingchanges/cs/legacyformatmode1.cs#1)]
[!code-vb[TimeSpan.BreakingChanges#1](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR/timespan.breakingchanges/vb/legacyformatmode1.vb#1)]

Quando si esegue l'esempio in .NET Framework 3,5 o in una versione precedente, viene visualizzato l'output seguente:

```console
12:30:45
```

Questa operazione è notevolmente diversa rispetto all'output se si esegue l'esempio in .NET Framework 4 o versione successiva:

```console
Invalid Format
```

Tuttavia, se si aggiunge il file di configurazione seguente alla directory dell'esempio e quindi si esegue l'esempio in .NET Framework 4 o versione successiva, l'output sarà identico a quello prodotto dall'esempio quando viene eseguito in .NET Framework 3,5.

```xml
<?xml version ="1.0"?>
<configuration>
   <runtime>
      <TimeSpan_LegacyFormatMode enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a>Vedi anche

- [Schema delle impostazioni di runtime](index.md)
- [Schema del file di configurazione](../index.md)

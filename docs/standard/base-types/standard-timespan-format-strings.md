---
title: Stringhe di formato TimeSpan standard
description: Esaminare le stringhe di formato TimeSpan standard, che usano un singolo identificatore di formato per definire la rappresentazione testuale di un valore TimeSpan in .NET.
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- format specifiers, standard time interval
- format strings
- standard time interval format strings
- standard format strings, time intervals
- format specifiers, time intervals
- time intervals [.NET Framework], formatting
- time [.NET Framework], formatting
- formatting [.NET Framework], time
- standard TimeSpan format strings
- formatting [.NET Framework], time intervals
ms.assetid: 9f6c95eb-63ae-4dcc-9c32-f81985c75794
ms.openlocfilehash: 31e4158d42d794e830d9acfe666729846c43a1ee
ms.sourcegitcommit: 5fd4696a3e5791b2a8c449ccffda87f2cc2d4894
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/15/2020
ms.locfileid: "84768118"
---
# <a name="standard-timespan-format-strings"></a>Stringhe di formato TimeSpan standard

 Una stringa di formato <xref:System.TimeSpan> standard usa un singolo identificatore di formato per definire la rappresentazione di testo di un valore <xref:System.TimeSpan> che risulta da un'operazione di formattazione. Le stringhe di formato contenenti più caratteri alfabetici, inclusi gli spazi vuoti, vengono interpretate come stringhe di formato <xref:System.TimeSpan> personalizzato. Per altre informazioni, vedere [stringhe di formato TimeSpan personalizzate](custom-timespan-format-strings.md) .  
  
 Le rappresentazione di stringa dei valori <xref:System.TimeSpan> vengono prodotte da chiamate agli overload del metodo <xref:System.TimeSpan.ToString%2A?displayProperty=nameWithType>, nonché dai metodi che supportano la formattazione composita, come <xref:System.String.Format%2A?displayProperty=nameWithType>. Per altre informazioni, vedere [Formattazione di tipi](formatting-types.md) e [Formattazione composita](composite-formatting.md). Nell'esempio seguente viene illustrato l'utilizzo di stringhe di formato standard nelle operazioni di formattazione.  
  
 [!code-csharp[Conceptual.TimeSpan.Standard#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.standard/cs/formatexample1.cs#2)]
 [!code-vb[Conceptual.TimeSpan.Standard#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.standard/vb/formatexample1.vb#2)]  
  
 Le stringhe di formato <xref:System.TimeSpan> standard sono usate anche dai metodi <xref:System.TimeSpan.ParseExact%2A?displayProperty=nameWithType> e <xref:System.TimeSpan.TryParseExact%2A?displayProperty=nameWithType> per definire il formato richieste delle stringhe di input per le operazioni di analisi (L'analisi converte la rappresentazione di stringa di un valore in tale valore). Nell'esempio seguente viene illustrato l'utilizzo di stringhe di formato standard nelle operazioni di analisi.  
  
 [!code-csharp[Conceptual.TimeSpan.Standard#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.standard/cs/parseexample1.cs#3)]
 [!code-vb[Conceptual.TimeSpan.Standard#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.standard/vb/parseexample1.vb#3)]  
  
Nella tabella seguente sono elencati gli identificatori di formato di intervallo di tempo standard.  
  
|Identificatore di formato|Nome|Description|Esempi|  
|----------------------|----------|-----------------|--------------|  
|"c"|Formato di costante (invariante)|Questo identificatore non è dipendente dalle impostazioni cultura. Assume il formato `[-][d'.']hh':'mm':'ss['.'fffffff]`<br /><br /> (le stringhe di formato "t" e "T" producono gli stessi risultati).<br /><br /> Altre informazioni: [Identificatore di formato di costante ("c")](#the-constant-c-format-specifier).|`TimeSpan.Zero` -> 00:00:00<br /><br /> `New TimeSpan(0, 0, 30, 0)` -> 00:30:00<br /><br /> `New TimeSpan(3, 17, 25, 30, 500)` -> 3.17:25:30.5000000|  
|"g"|Formato breve generale|Questo identificatore restituisce informazioni strettamente necessarie. È basato sulle impostazioni cultura e assume il formato `[-][d':']h':'mm':'ss[.FFFFFFF]`.<br /><br /> Altre informazioni: [Identificatore di formato breve generale ("g")](#the-general-short-g-format-specifier).|`New TimeSpan(1, 3, 16, 50, 500)` -> 1:3:16:50.5 (en-US)<br /><br /> `New TimeSpan(1, 3, 16, 50, 500)` -> 1:3:16:50,5 (fr-FR)<br /><br /> `New TimeSpan(1, 3, 16, 50, 599)` -> 1:3:16:50.599 (en-US)<br /><br /> `New TimeSpan(1, 3, 16, 50, 599)` -> 1:3:16:50,599 (fr-FR)|  
|"G"|Formato esteso generale|Questo identificatore restituisce sempre giorni e sette cifre frazionarie. È basato sulle impostazioni cultura e assume il formato `[-]d':'hh':'mm':'ss.fffffff`.<br /><br /> Altre informazioni: [Identificatore di formato esteso generale ("G")](#the-general-long-g-format-specifier).|`New TimeSpan(18, 30, 0)` -> 0:18:30:00.0000000 (en-US)<br /><br /> `New TimeSpan(18, 30, 0)` -> 0:18:30:00,0000000 (fr-FR)|  

## <a name="the-constant-c-format-specifier"></a>Identificatore di formato di costante ("C").  
 L'identificatore di formato "c" restituisce la rappresentazione di stringa di un valore <xref:System.TimeSpan> nel formato seguente:  
  
 [-][*d*.]*hh*:*mm*:*ss*[.*fffffff*]  
  
 Gli elementi tra parentesi quadre ([e]) sono facoltativi. Il punto (.) e i due punti (:) sono simboli letterali. La tabella seguente descrive gli elementi rimanenti.  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|*-*|Un segno negativo facoltativo, che indica un intervallo di tempo negativo.|  
|*d*|Numero di giorni facoltativo, senza zeri iniziali.|  
|*hh*|Numero di ore, nell'intervallo compreso tra "00" e "23".|  
|*mm*|Numero di minuti, nell'intervallo compreso tra "00" e "59".|  
|*SS*|Numero di secondi, nell'intervallo compreso tra "0" e "59".|  
|*fffffff*|La parte frazionaria facoltativa di un secondo.  Il valore può variare da "0000001" (un tick oppure un decimilionesimo di secondo) e "9999999" (9.999.999 decimilionesimi di secondo, o un secondo meno di un tick).|  
  
 A differenza degli identificatori di formato "g" e "G", l'identificatore di formato "c" non è dipendente dalle impostazioni cultura. Produce la rappresentazione di stringa di un valore <xref:System.TimeSpan> invariabile e comune a tutte le versioni di .NET Framework precedenti a .NET Framework 4. "c" è la stringa di formato <xref:System.TimeSpan> predefinita; il metodo <xref:System.TimeSpan.ToString?displayProperty=nameWithType> formatta un valore di intervallo di tempo usando la stringa di formato "c".  
  
> [!NOTE]
> <xref:System.TimeSpan> supporta anche le stringhe di formato standard "t" e "T", che hanno un comportamento identico alla stringa di formato standard "c".  
  
 Nell'esempio seguente viene creata un'istanza di due oggetti <xref:System.TimeSpan>, usati per eseguire operazioni aritmetiche e viene visualizzato il risultato. In ogni caso, viene usata la formattazione composita per visualizzare il valore <xref:System.TimeSpan> con l'identificatore di formato "c".  
  
 [!code-csharp[Conceptual.TimeSpan.Standard#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.standard/cs/standardc1.cs#1)]
 [!code-vb[Conceptual.TimeSpan.Standard#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.standard/vb/standardc1.vb#1)]  

## <a name="the-general-short-g-format-specifier"></a>Identificatore di formato generale ("g")  
 L'identificatore di formato <xref:System.TimeSpan> "g" restituisce la rappresentazione di stringa di un valore <xref:System.TimeSpan> in un formato compresso includendo solo gli elementi necessari. che si presenta nel formato seguente:  
  
 [-][*d*:]*h*:*mm*:*ss*[.*FFFFFFF*]  
  
 Gli elementi tra parentesi quadre ([e]) sono facoltativi. I due punti (:) sono un simbolo letterale. La tabella seguente descrive gli elementi rimanenti.  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|*-*|Un segno negativo facoltativo, che indica un intervallo di tempo negativo.|  
|*d*|Numero di giorni facoltativo, senza zeri iniziali.|  
|*h*|Numero di ore, compreso tra "0" e "23", senza zeri iniziali.|  
|*mm*|Numero di minuti, compreso tra "00" e "59".|  
|*SS*|Numero di secondi, compreso tra "00" e "59".|  
|*.*|Il separatore dei secondi frazionari. È equivalente alla proprietà <xref:System.Globalization.NumberFormatInfo.NumberDecimalSeparator%2A> della cultura specificata senza gli override dell'utente.|  
|*FFFFFFF*|Frazioni di secondo. Viene visualizzato il minor numero di cifre possibile.|  
  
 Come l'identificatore di formato "G", l'identificatore di formato "g" viene localizzato. Il separatore delle frazioni di secondo si basa sulla cultura corrente oppure su una proprietà <xref:System.Globalization.NumberFormatInfo.NumberDecimalSeparator%2A> della cultura specificata.  
  
 Nell'esempio seguente viene creata un'istanza di due oggetti <xref:System.TimeSpan>, usati per eseguire operazioni aritmetiche e viene visualizzato il risultato. In ogni caso, viene usata la formattazione composita per visualizzare il valore <xref:System.TimeSpan> con l'identificatore di formato "g". Inoltre, formatta il valore <xref:System.TimeSpan> usando le convenzioni di formattazione della lingua corrente del sistema (ovvero, in questo caso, Inglese - Stati Uniti o en-US) e il Francese - Francia (fr-FR).  
  
 [!code-csharp[Conceptual.TimeSpan.Standard#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.standard/cs/standardshort1.cs#4)]
 [!code-vb[Conceptual.TimeSpan.Standard#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.standard/vb/standardshort1.vb#4)]  

## <a name="the-general-long-g-format-specifier"></a>Identificatore di formato esteso generale ("G")  
 L'identificatore di formato <xref:System.TimeSpan> "G" restituisce la rappresentazione di stringa di un valore <xref:System.TimeSpan> in un formato esteso che include sempre sia i giorni sia le frazioni di secondo. La stringa risultante dall'identificatore di formato standard "G" ha il seguente formato:  
  
 [-] *d*:*HH*:*mm*:*SS*. *fffffff*  
  
 Gli elementi tra parentesi quadre ([e]) sono facoltativi. I due punti (:) sono un simbolo letterale. La tabella seguente descrive gli elementi rimanenti.  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|*-*|Un segno negativo facoltativo, che indica un intervallo di tempo negativo.|  
|*d*|Il numero di giorni, senza zeri iniziali.|  
|*hh*|Numero di ore, nell'intervallo compreso tra "00" e "23".|  
|*mm*|Numero di minuti, nell'intervallo compreso tra "00" e "59".|  
|*SS*|Numero di secondi, nell'intervallo compreso tra "00" e "59".|  
|*.*|Il separatore dei secondi frazionari. È equivalente alla proprietà <xref:System.Globalization.NumberFormatInfo.NumberDecimalSeparator%2A> della cultura specificata senza gli override dell'utente.|  
|*fffffff*|Frazioni di secondo.|  
  
 Come l'identificatore di formato "G", l'identificatore di formato "g" viene localizzato. Il separatore delle frazioni di secondo si basa sulla cultura corrente oppure su una proprietà <xref:System.Globalization.NumberFormatInfo.NumberDecimalSeparator%2A> della cultura specificata.  
  
 Nell'esempio seguente viene creata un'istanza di due oggetti <xref:System.TimeSpan>, usati per eseguire operazioni aritmetiche e viene visualizzato il risultato. In ogni caso, viene usata la formattazione composita per visualizzare il valore <xref:System.TimeSpan> con l'identificatore di formato "G". Inoltre, formatta il valore <xref:System.TimeSpan> usando le convenzioni di formattazione della lingua corrente del sistema (ovvero, in questo caso, Inglese - Stati Uniti o en-US) e il Francese - Francia (fr-FR).  
  
 [!code-csharp[Conceptual.TimeSpan.Standard#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.standard/cs/standardlong1.cs#5)]
 [!code-vb[Conceptual.TimeSpan.Standard#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.standard/vb/standardlong1.vb#5)]
  
## <a name="see-also"></a>Vedere anche

- [Formattazione di tipi](formatting-types.md)
- [Stringhe di formato TimeSpan personalizzate](custom-timespan-format-strings.md)
- [Analisi di stringhe](parsing-strings.md)

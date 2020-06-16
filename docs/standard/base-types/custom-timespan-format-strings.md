---
title: Stringhe in formato TimeSpan personalizzato
description: Informazioni sulle stringhe di formato TimeSpan personalizzate in .NET. Una stringa di formato personalizzata contiene uno o più identificatori di formato TimeSpan & un numero qualsiasi di caratteri letterali.
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- format specifiers, custom time interval
- format strings
- formatting [.NET Framework], time interval
- custom time interval format strings
- formatting [.NET Framework], time
- custom TimeSpan format strings
ms.assetid: a63ebf55-7269-416b-b4f5-286f6c03bf0e
ms.openlocfilehash: 54079975b9b73844f598a7c7a7fea1a64bd6450c
ms.sourcegitcommit: 5fd4696a3e5791b2a8c449ccffda87f2cc2d4894
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/15/2020
ms.locfileid: "84768560"
---
# <a name="custom-timespan-format-strings"></a>Stringhe in formato TimeSpan personalizzato

Una stringa in formato <xref:System.TimeSpan> definisce la rappresentazione di stringa di un valore <xref:System.TimeSpan> risultante da un'operazione di formattazione. Una stringa in formato personalizzato è costituita da uno o più identificatori in formato <xref:System.TimeSpan> personalizzato con un numero qualsiasi di caratteri di tipo letterale. Qualsiasi stringa che non sia una [stringa di formato TimeSpan standard](standard-timespan-format-strings.md) viene interpretata come una <xref:System.TimeSpan> stringa di formato personalizzata.

> [!IMPORTANT]
> Gli identificatori di formato <xref:System.TimeSpan> personalizzati non includono i simboli separatori dei segnaposto, ad esempio i simboli che separano i giorni dalle ore, le ore dai minuti o i secondi dalle frazioni di secondo. Questi simboli devono essere inclusi nella stringa di formato personalizzato come valori letterali stringa. Ad esempio, in `"dd\.hh\:mm"` il punto (.) è definito come separatore tra giorni e ore e i due punti (:) come separatore tra ore e minuti.
>
> Inoltre, negli identificatori di formato <xref:System.TimeSpan> personalizzati non è incluso un segno che consente di distinguere tra intervalli di tempo negativi e positivi. Per includere un simbolo di segno, è necessario creare una stringa di formato tramite la logica condizionale. Nella sezione [altri caratteri](#other-characters) è incluso un esempio.

Le rappresentazione di stringa dei valori <xref:System.TimeSpan> vengono prodotte da chiamate agli overload del metodo <xref:System.TimeSpan.ToString%2A?displayProperty=nameWithType> e dai metodi che supportano la formattazione composita, come <xref:System.String.Format%2A?displayProperty=nameWithType>. Per altre informazioni, vedere [Formattazione di tipi](formatting-types.md) e [Formattazione composita](composite-formatting.md). Nell'esempio seguente viene illustrato l'uso di stringhe in formato personalizzato nelle operazioni di formattazione.

[!code-csharp[Conceptual.TimeSpan.Custom#1](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/customformatexample1.cs#1)]
[!code-vb[Conceptual.TimeSpan.Custom#1](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/customformatexample1.vb#1)]

Le stringhe in formato <xref:System.TimeSpan> personalizzato sono usate anche dai metodi <xref:System.TimeSpan.ParseExact%2A?displayProperty=nameWithType> e <xref:System.TimeSpan.TryParseExact%2A?displayProperty=nameWithType> per definire il formato richiesto delle stringhe di input per le operazioni di analisi (L'analisi converte la rappresentazione di stringa di un valore in tale valore). Nell'esempio seguente viene illustrato l'utilizzo di stringhe di formato standard nelle operazioni di analisi.

[!code-csharp[Conceptual.TimeSpan.Custom#2](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/customparseexample1.cs#2)]
[!code-vb[Conceptual.TimeSpan.Custom#2](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/customparseexample1.vb#2)]

<a name="table"></a> La tabella seguente descrive gli identificatori di formato di data e ora personalizzati.

| Identificatore di formato | Descrizione | Esempio |
|----------------------|-----------------|-------------|
|"d", "%d"|Il numero di giorni completi nell'intervallo di tempo.<br /><br /> Ulteriori informazioni: [identificatore di formato personalizzato "d"](#dSpecifier).|`new TimeSpan(6, 14, 32, 17, 685):`<br /><br /> `%d` --> "6"<br /><br /> `d\.hh\:mm` --> "6.14:32"|
|"dd"-"dddddddd"|Il numero di giorni completi nell'intervallo di tempo, con il numero di zeri necessari all'inizio.<br /><br /> Ulteriori informazioni: [identificatori di formato personalizzato "dd"-"dddddddd"](#ddSpecifier).|`new TimeSpan(6, 14, 32, 17, 685):`<br /><br /> `ddd` --> "006"<br /><br /> `dd\.hh\:mm` --> "06.14:32"|
|"h", "%h"|Il numero di ore complete nell'intervallo di tempo non conteggiate come parti di giorni. Le ore a una sola cifra non hanno uno zero iniziale.<br /><br /> Altre informazioni: [identificatore di formato personalizzato "h"](#hSpecifier).|`new TimeSpan(6, 14, 32, 17, 685):`<br /><br /> `%h` --> "14"<br /><br /> `hh\:mm` --> "14:32"|
|"hh"|Il numero di ore complete nell'intervallo di tempo non conteggiate come parti di giorni. Le ore a una sola cifra hanno uno zero iniziale.<br /><br /> Ulteriori informazioni: [identificatore di formato personalizzato "HH"](#hhSpecifier).|`new TimeSpan(6, 14, 32, 17, 685):`<br /><br /> `hh` --> "14"<br /><br /> `new TimeSpan(6, 8, 32, 17, 685):`<br /><br /> `hh` --> 08|
|"m", "%m"|Il numero di minuti completi nell'intervallo di tempo non conteggiati come parti di ore o di giorni. I minuti a una sola cifra non hanno uno zero iniziale.<br /><br /> Altre informazioni: [identificatore di formato personalizzato "m"](#mSpecifier).|`new TimeSpan(6, 14, 8, 17, 685):`<br /><br /> `%m` --> "8"<br /><br /> `h\:m` --> "14:8"|
|"mm"|Il numero di minuti completi nell'intervallo di tempo non conteggiati come parti di ore o di giorni. I minuti a una sola cifra hanno uno zero iniziale.<br /><br /> Altre informazioni: [identificatore di formato personalizzato "mm"](#mmSpecifier).|`new TimeSpan(6, 14, 8, 17, 685):`<br /><br /> `mm` --> "08"<br /><br /> `new TimeSpan(6, 8, 5, 17, 685):`<br /><br /> `d\.hh\:mm\:ss` --> 6.08:05:17|
|"s", "%s"|Il numero di secondi completi nell'intervallo di tempo non conteggiati come parti di minuti, ore o giorni. I secondi a una sola cifra non hanno uno zero iniziale.<br /><br /> Ulteriori informazioni: [identificatore di formato personalizzato "s"](#sSpecifier).|`TimeSpan.FromSeconds(12.965)`:<br /><br /> `%s` --> 12<br /><br /> `s\.fff` --> 12,965|
|"ss"|Il numero di secondi completi nell'intervallo di tempo non conteggiati come parti di minuti, ore o giorni.  I secondi a una sola cifra hanno uno zero iniziale.<br /><br /> Altre informazioni: [identificatore di formato personalizzato "SS"](#ssSpecifier).|`TimeSpan.FromSeconds(6.965)`:<br /><br /> `ss` --> 06<br /><br /> `ss\.fff` --> 06,965|
|"f", "%f"|I decimi di secondo in un intervallo di tempo.<br /><br /> Ulteriori informazioni: [identificatore di formato personalizzato "f"](#fSpecifier).|`TimeSpan.FromSeconds(6.895)`:<br /><br /> `f` --> 8<br /><br /> `ss\.f` --> 06,8|
|"ff"|I centesimi di secondo in un intervallo di tempo.<br /><br /> Altre informazioni: [identificatore di formato personalizzato "FF"](#ffSpecifier).|`TimeSpan.FromSeconds(6.895)`:<br /><br /> `ff` --> 89<br /><br /> `ss\.ff` --> 06,89|
|"fff"|I millisecondi in un intervallo di tempo.<br /><br /> Altre informazioni: [identificatore di formato personalizzato "fff"](#f3Specifier).|`TimeSpan.FromSeconds(6.895)`:<br /><br /> `fff` --> 895<br /><br /> `ss\.fff` --> 06,895|
|"ffff"|I decimillesimi di secondo in un intervallo di tempo.<br /><br /> Altre informazioni: [identificatore di formato personalizzato "ffff"](#f4Specifier).|`TimeSpan.Parse("0:0:6.8954321")`:<br /><br /> `ffff` --> 8954<br /><br /> `ss\.ffff` --> 06.8954|
|"fffff"|I centesimi di millesimo di secondo in un intervallo di tempo.<br /><br /> Ulteriori informazioni: [identificatore di formato personalizzato "fffff"](#f5Specifier).|`TimeSpan.Parse("0:0:6.8954321")`:<br /><br /> `fffff` --> 89543<br /><br /> `ss\.fffff` --> 06,89543|
|"ffffff"|I milionesimi di secondo in un intervallo di tempo.<br /><br /> Ulteriori informazioni: [identificatore di formato personalizzato "FFFFFF"](#f6Specifier).|`TimeSpan.Parse("0:0:6.8954321")`:<br /><br /> `ffffff` --> 895432<br /><br /> `ss\.ffffff` --> 06,895432|
|"fffffff"|I decimilionesimi di secondo (o il numero frazionario di tick) in un intervallo di tempo.<br /><br /> Ulteriori informazioni: [identificatore di formato personalizzato "fffffff"](#f7Specifier).|`TimeSpan.Parse("0:0:6.8954321")`:<br /><br /> `fffffff` --> 8954321<br /><br /> `ss\.fffffff` --> 06,8954321|
|"F", "%F"|I decimi di secondo in un intervallo di tempo. Se la cifra è zero, non viene prodotta alcuna visualizzazione.<br /><br /> Ulteriori informazioni: [identificatore di formato personalizzato "F"](#F_Specifier).|`TimeSpan.Parse("00:00:06.32")`:<br /><br /> `%F`: 3<br /><br /> `TimeSpan.Parse("0:0:3.091")`:<br /><br /> `ss\.F`: 03.|
|"FF"|I centesimi di secondo in un intervallo di tempo. Eventuali zeri finali frazionari o doppi zeri non sono inclusi.<br /><br /> Altre informazioni: [identificatore di formato personalizzato "FF"](#FF_Specifier).|`TimeSpan.Parse("00:00:06.329")`:<br /><br /> `FF`: 32<br /><br /> `TimeSpan.Parse("0:0:3.101")`:<br /><br /> `ss\.FF`: 03.1|
|"FFF"|I millisecondi in un intervallo di tempo. Eventuali zeri finali frazionari non sono inclusi.<br /><br /> Altre informazioni:|`TimeSpan.Parse("00:00:06.3291")`:<br /><br /> `FFF`: 329<br /><br /> `TimeSpan.Parse("0:0:3.1009")`:<br /><br /> `ss\.FFF`: 03.1|
|"FFFF"|I decimillesimi di secondo in un intervallo di tempo. Eventuali zeri finali frazionari non sono inclusi.<br /><br /> Altre informazioni: [identificatore di formato personalizzato "ffff"](#F4_Specifier).|`TimeSpan.Parse("00:00:06.32917")`:<br /><br /> `FFFFF`: 3291<br /><br /> `TimeSpan.Parse("0:0:3.10009")`:<br /><br /> `ss\.FFFF`: 03.1|
|"FFFFF"|I centesimi di millesimo di secondo in un intervallo di tempo. Eventuali zeri finali frazionari non sono inclusi.<br /><br /> Ulteriori informazioni: [identificatore di formato personalizzato "fffff"](#F5_Specifier).|`TimeSpan.Parse("00:00:06.329179")`:<br /><br /> `FFFFF`: 32917<br /><br /> `TimeSpan.Parse("0:0:3.100009")`:<br /><br /> `ss\.FFFFF`: 03.1|
|"FFFFFF"|I milionesimi di secondo in un intervallo di tempo. Eventuali zeri finali frazionari non sono visualizzati.<br /><br /> Ulteriori informazioni: [identificatore di formato personalizzato "FFFFFF"](#F6_Specifier).|`TimeSpan.Parse("00:00:06.3291791")`:<br /><br /> `FFFFFF`: 329179<br /><br /> `TimeSpan.Parse("0:0:3.1000009")`:<br /><br /> `ss\.FFFFFF`: 03.1|
|"FFFFFFF"|I decimilionesimi di secondo in un intervallo di tempo. Eventuali zeri finali frazionari o gruppi di sette zeri non sono visualizzati.<br /><br /> Ulteriori informazioni: [identificatore di formato personalizzato "fffffff"](#F7_Specifier).|`TimeSpan.Parse("00:00:06.3291791")`:<br /><br /> `FFFFFF`: 3291791<br /><br /> `TimeSpan.Parse("0:0:3.1900000")`:<br /><br /> `ss\.FFFFFF`: 03.19|
|'*String*'|Delimitatore di stringa letterale.<br /><br /> Altre informazioni: [altri caratteri](#other-characters).|`new TimeSpan(14, 32, 17):`<br /><br /> `hh':'mm':'ss` --> "14:32:17"|
|&#92;|Carattere di escape.<br /><br /> Altre informazioni: [altri caratteri](#other-characters).|`new TimeSpan(14, 32, 17):`<br /><br /> `hh\:mm\:ss` --> "14:32:17"|
|Qualsiasi altro carattere|Qualsiasi altro carattere senza escape viene interpretato come identificatore di formato personalizzato.<br /><br /> Altre informazioni: [altri caratteri](#other-characters).|`new TimeSpan(14, 32, 17):`<br /><br /> `hh\:mm\:ss` --> "14:32:17"|

## <a name="the-d-custom-format-specifier"></a><a name="dSpecifier"></a>Identificatore di formato personalizzato "d"

L'identificatore di formato personalizzato "d" restituisce il valore della proprietà <xref:System.TimeSpan.Days%2A?displayProperty=nameWithType>, che rappresenta il numero di giorni completi nell'intervallo di tempo. Restituisce il numero completo di giorni di un valore <xref:System.TimeSpan>, anche se il valore ha più di una cifra. Se il valore della proprietà <xref:System.TimeSpan.Days%2A?displayProperty=nameWithType> è zero, l'identificatore restituisce "0".

Se l'identificatore di formato personalizzato "d" viene usato da solo, specificare "%d" in modo che non venga interpretato erroneamente come stringa in formato standard. Di seguito ne viene illustrato un esempio.

[!code-csharp[Conceptual.TimeSpan.Custom#3](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/customexamples1.cs#3)]
[!code-vb[Conceptual.TimeSpan.Custom#3](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/customexamples1.vb#3)]

Nell'esempio seguente viene illustrato l'uso dell'identificatore di formato personalizzato "d".

[!code-csharp[Conceptual.TimeSpan.Custom#4](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/customexamples1.cs#4)]
[!code-vb[Conceptual.TimeSpan.Custom#4](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/customexamples1.vb#4)]

[Torna alla tabella](#table)

## <a name="the-dd-dddddddd-custom-format-specifiers"></a><a name="ddSpecifier"></a>Identificatori di formato personalizzato "dd"-"dddddddd"

Gli identificatori di formato personalizzato "dd", "ddd", "dddd", "ddddd", "dddddd", "ddddddd" e "dddddddd" restituiscono il valore della proprietà <xref:System.TimeSpan.Days%2A?displayProperty=nameWithType>, che rappresenta il numero di giorni completi nell'intervallo di tempo.

La stringa di output include un numero minimo di cifre specificato dal numero di caratteri "d" nell'identificatore di formato e il numero necessario di zeri iniziali. Se le cifre del numero di giorni superano il numero di caratteri "d"nell'identificatore di formato, l'output nella stringa risultato corrisponde al numero completo di giorni.

L'esempio seguente usa gli identificatori di formato per visualizzare la rappresentazione stringa di due valori <xref:System.TimeSpan>. Il valore del componente giorni del primo intervallo di tempo è zero, mentre il valore del componente dei giorni del secondo è 365.

[!code-csharp[Conceptual.TimeSpan.Custom#5](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/customexamples1.cs#5)]
[!code-vb[Conceptual.TimeSpan.Custom#5](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/customexamples1.vb#5)]

[Torna alla tabella](#table)

## <a name="the-h-custom-format-specifier"></a><a name="hSpecifier"></a>Identificatore di formato personalizzato "h"

L'identificatore di formato personalizzato "h" restituisce il valore della proprietà <xref:System.TimeSpan.Hours%2A?displayProperty=nameWithType>, che rappresenta il numero di ore complete nell'intervallo di tempo non conteggiate come parte del relativo componente giorno. Restituisce un valore stringa a una cifra se il valore della proprietà <xref:System.TimeSpan.Hours%2A?displayProperty=nameWithType> è compreso tra 0 e 9 e restituisce un valore stringa a due cifre se il valore della proprietà <xref:System.TimeSpan.Hours%2A?displayProperty=nameWithType> è compreso tra 10 e 23.

Se l'identificatore di formato personalizzato "h" viene usato da solo, specificare "%h" in modo che non venga interpretato erroneamente come stringa in formato standard. Di seguito ne viene illustrato un esempio.

[!code-csharp[Conceptual.TimeSpan.Custom#6](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/customexamples1.cs#6)]
[!code-vb[Conceptual.TimeSpan.Custom#6](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/customexamples1.vb#6)]

Normalmente in un'operazione di analisi una stringa di input che include solo un numero singolo viene interpretata come numero di giorni. Usare invece l'identificatore di formato personalizzato "%h" per interpretare la stringa numerica come numero di ore. Di seguito ne viene illustrato un esempio.

[!code-csharp[Conceptual.TimeSpan.Custom#8](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/customexamples1.cs#8)]
[!code-vb[Conceptual.TimeSpan.Custom#8](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/customexamples1.vb#8)]

Nell'esempio seguente viene illustrato l'uso dell'identificatore di formato personalizzato "h".

[!code-csharp[Conceptual.TimeSpan.Custom#7](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/customexamples1.cs#7)]
[!code-vb[Conceptual.TimeSpan.Custom#7](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/customexamples1.vb#7)]

[Torna alla tabella](#table)

## <a name="the-hh-custom-format-specifier"></a><a name="hhSpecifier"></a>Identificatore di formato personalizzato "HH"

L'identificatore di formato personalizzato "hh" restituisce il valore della proprietà <xref:System.TimeSpan.Hours%2A?displayProperty=nameWithType>, che rappresenta il numero di ore complete nell'intervallo di tempo non conteggiate come parte del relativo componente giorno. Per valori compresi tra 0 e 9, la stringa di output include uno zero iniziale.

Normalmente in un'operazione di analisi una stringa di input che include solo un numero singolo viene interpretata come numero di giorni. Usare invece l'identificatore di formato personalizzato "hh" per interpretare la stringa numerica come numero di ore. Di seguito ne viene illustrato un esempio.

[!code-csharp[Conceptual.TimeSpan.Custom#9](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/customexamples1.cs#9)]
[!code-vb[Conceptual.TimeSpan.Custom#9](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/customexamples1.vb#9)]

Nell'esempio seguente viene illustrato l'uso dell'identificatore di formato personalizzato "hh".

[!code-csharp[Conceptual.TimeSpan.Custom#10](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/customexamples1.cs#10)]
[!code-vb[Conceptual.TimeSpan.Custom#10](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/customexamples1.vb#10)]

[Torna alla tabella](#table)

## <a name="the-m-custom-format-specifier"></a><a name="mSpecifier"></a>Identificatore di formato personalizzato "m"

L'identificatore di formato personalizzato "m" restituisce il valore della proprietà <xref:System.TimeSpan.Minutes%2A?displayProperty=nameWithType>, che rappresenta il numero di minuti completi nell'intervallo di tempo non conteggiati come parte del relativo componente giorno. Restituisce un valore stringa a una cifra se il valore della proprietà <xref:System.TimeSpan.Minutes%2A?displayProperty=nameWithType> è compreso tra 0 e 9 e restituisce un valore stringa a due cifre se il valore della proprietà <xref:System.TimeSpan.Minutes%2A?displayProperty=nameWithType> è compreso tra 10 e 59.

Se l'identificatore di formato personalizzato "m" viene usato da solo, specificare "%m" in modo che non venga interpretato erroneamente come stringa in formato standard. Di seguito ne viene illustrato un esempio.

[!code-csharp[Conceptual.TimeSpan.Custom#6](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/customexamples1.cs#6)]
[!code-vb[Conceptual.TimeSpan.Custom#6](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/customexamples1.vb#6)]

Normalmente in un'operazione di analisi una stringa di input che include solo un numero singolo viene interpretata come numero di giorni. Usare invece l'identificatore di formato personalizzato "%m" per interpretare la stringa numerica come numero di minuti. Di seguito ne viene illustrato un esempio.

[!code-csharp[Conceptual.TimeSpan.Custom#11](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/customexamples1.cs#11)]
[!code-vb[Conceptual.TimeSpan.Custom#11](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/customexamples1.vb#11)]

Nell'esempio seguente viene illustrato l'uso dell'identificatore di formato personalizzato "m".

[!code-csharp[Conceptual.TimeSpan.Custom#12](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/customexamples1.cs#12)]
[!code-vb[Conceptual.TimeSpan.Custom#12](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/customexamples1.vb#12)]

[Torna alla tabella](#table)

## <a name="the-mm-custom-format-specifier"></a><a name="mmSpecifier"></a>Identificatore di formato personalizzato "mm"

L'identificatore di formato personalizzato "mm" restituisce il valore della proprietà <xref:System.TimeSpan.Minutes%2A?displayProperty=nameWithType>, che rappresenta il numero di minuti completi nell'intervallo di tempo non inclusi come parte del relativo componente ore o giorni. Per valori compresi tra 0 e 9, la stringa di output include uno zero iniziale.

Normalmente in un'operazione di analisi una stringa di input che include solo un numero singolo viene interpretata come numero di giorni. Usare invece l'identificatore di formato personalizzato "mm" per interpretare la stringa numerica come numero di minuti. Di seguito ne viene illustrato un esempio.

[!code-csharp[Conceptual.TimeSpan.Custom#13](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/customexamples1.cs#13)]
[!code-vb[Conceptual.TimeSpan.Custom#13](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/customexamples1.vb#13)]

Nell'esempio seguente viene illustrato l'uso dell'identificatore di formato personalizzato "mm".

[!code-csharp[Conceptual.TimeSpan.Custom#14](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/customexamples1.cs#14)]
[!code-vb[Conceptual.TimeSpan.Custom#14](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/customexamples1.vb#14)]

[Torna alla tabella](#table)

## <a name="the-s-custom-format-specifier"></a><a name="sSpecifier"></a>Identificatore di formato personalizzato "s"

L'identificatore di formato personalizzato "s" restituisce il valore della proprietà <xref:System.TimeSpan.Seconds%2A?displayProperty=nameWithType>, che rappresenta il numero di secondi completi nell'intervallo di tempo non inclusi come parte del relativo componente ore, giorni o minuti. Restituisce un valore stringa a una cifra se il valore della proprietà <xref:System.TimeSpan.Seconds%2A?displayProperty=nameWithType> è compreso tra 0 e 9 e restituisce un valore stringa a due cifre se il valore della proprietà <xref:System.TimeSpan.Seconds%2A?displayProperty=nameWithType> è compreso tra 10 e 59.

Se l'identificatore di formato personalizzato "s" viene usato da solo, specificare "%s" in modo che non venga interpretato erroneamente come stringa in formato standard. Di seguito ne viene illustrato un esempio.

[!code-csharp[Conceptual.TimeSpan.Custom#15](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/customexamples1.cs#15)]
[!code-vb[Conceptual.TimeSpan.Custom#15](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/customexamples1.vb#15)]

Normalmente in un'operazione di analisi una stringa di input che include solo un numero singolo viene interpretata come numero di giorni. Usare invece l'identificatore di formato personalizzato "%s" per interpretare la stringa numerica come numero di secondi. Di seguito ne viene illustrato un esempio.

[!code-csharp[Conceptual.TimeSpan.Custom#17](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/customexamples1.cs#17)]
[!code-vb[Conceptual.TimeSpan.Custom#17](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/customexamples1.vb#17)]

Nell'esempio seguente viene illustrato l'uso dell'identificatore di formato personalizzato "s".

[!code-csharp[Conceptual.TimeSpan.Custom#16](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/customexamples1.cs#16)]
[!code-vb[Conceptual.TimeSpan.Custom#16](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/customexamples1.vb#16)]

[Torna alla tabella](#table)

## <a name="the-ss-custom-format-specifier"></a><a name="ssSpecifier"></a>Identificatore di formato personalizzato "SS"

L'identificatore di formato personalizzato "ss" restituisce il valore della proprietà <xref:System.TimeSpan.Seconds%2A?displayProperty=nameWithType>, che rappresenta il numero di secondi completi nell'intervallo di tempo non inclusi come parte del relativo componente ore, giorni o minuti. Per valori compresi tra 0 e 9, la stringa di output include uno zero iniziale.

Normalmente in un'operazione di analisi una stringa di input che include solo un numero singolo viene interpretata come numero di giorni. Usare invece l'identificatore di formato personalizzato "ss" per interpretare la stringa numerica come numero di secondi. Di seguito ne viene illustrato un esempio.

[!code-csharp[Conceptual.TimeSpan.Custom#18](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/customexamples1.cs#18)]
[!code-vb[Conceptual.TimeSpan.Custom#18](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/customexamples1.vb#18)]

Nell'esempio seguente viene illustrato l'uso dell'identificatore di formato personalizzato "ss".

[!code-csharp[Conceptual.TimeSpan.Custom#19](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/customexamples1.cs#19)]
[!code-vb[Conceptual.TimeSpan.Custom#19](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/customexamples1.vb#19)]

[Torna alla tabella](#table)

## <a name="the-f-custom-format-specifier"></a><a name="fSpecifier"></a>Identificatore di formato personalizzato "f"

L'identificatore di formato personalizzato "f" restituisce i decimi di secondo in un intervallo di tempo. In un'operazione di formattazione qualsiasi cifra frazionaria rimanente viene troncata. In un'operazione di analisi che chiama il metodo <xref:System.TimeSpan.ParseExact%2A?displayProperty=nameWithType> o <xref:System.TimeSpan.TryParseExact%2A?displayProperty=nameWithType> la stringa di input deve contenere esattamente una sola cifra frazionaria.

Se l'identificatore di formato personalizzato "f" viene usato da solo, specificare "%f" in modo che non venga interpretato erroneamente come stringa in formato standard.

Nell'esempio seguente viene usato l'identificatore di formato personalizzato "f" per visualizzare i decimi di secondo in un valore <xref:System.TimeSpan>. "f" viene usato prima come unico identificatore di formato e quindi viene usato in combinazione con l'identificatore "s" in una stringa di formato personalizzato.

[!code-csharp[Conceptual.TimeSpan.Custom#20](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/fspecifiers1.cs#20)]
[!code-vb[Conceptual.TimeSpan.Custom#20](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/fspecifiers1.vb#20)]

[Torna alla tabella](#table)

## <a name="the-ff-custom-format-specifier"></a><a name="ffSpecifier"></a>Identificatore di formato personalizzato "FF"

L'identificatore di formato personalizzato "ff" restituisce i centesimi di secondo in un intervallo di tempo. In un'operazione di formattazione qualsiasi cifra frazionaria rimanente viene troncata. In un'operazione di analisi che chiama il metodo <xref:System.TimeSpan.ParseExact%2A?displayProperty=nameWithType> o <xref:System.TimeSpan.TryParseExact%2A?displayProperty=nameWithType> la stringa di input deve contenere esattamente due cifre frazionarie.

Nell'esempio seguente viene usato l'identificatore di formato personalizzato "ff" per visualizzare i centesimi di secondo in un valore <xref:System.TimeSpan>. "ff" viene usato prima come unico identificatore di formato, quindi viene usato in combinazione con l'identificatore "s" in una stringa di formato personalizzato.

[!code-csharp[Conceptual.TimeSpan.Custom#20](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/fspecifiers1.cs#20)]
[!code-vb[Conceptual.TimeSpan.Custom#20](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/fspecifiers1.vb#20)]

[Torna alla tabella](#table)

## <a name="the-fff-custom-format-specifier"></a><a name="f3Specifier"></a>Identificatore di formato personalizzato "fff"

L'identificatore di formato personalizzato "fff" (con tre caratteri "f") restituisce i millisecondi in un intervallo di tempo. In un'operazione di formattazione qualsiasi cifra frazionaria rimanente viene troncata. In un'operazione di analisi che chiama il metodo <xref:System.TimeSpan.ParseExact%2A?displayProperty=nameWithType> o <xref:System.TimeSpan.TryParseExact%2A?displayProperty=nameWithType> la stringa di input deve contenere esattamente tre cifre frazionarie.

Nell'esempio seguente viene usato l'identificatore di formato personalizzato "fff" per visualizzare i millisecondi in un valore <xref:System.TimeSpan>. "fff" viene usato prima come unico identificatore di formato e quindi viene usato in combinazione con l'identificatore "s" in una stringa di formato personalizzato.

[!code-csharp[Conceptual.TimeSpan.Custom#20](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/fspecifiers1.cs#20)]
[!code-vb[Conceptual.TimeSpan.Custom#20](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/fspecifiers1.vb#20)]

[Torna alla tabella](#table)

## <a name="the-ffff-custom-format-specifier"></a><a name="f4Specifier"></a>Identificatore di formato personalizzato "ffff"

L'identificatore di formato personalizzato "ffff" (con quattro caratteri "f") restituisce i decimillesimi di secondo in un intervallo di tempo. In un'operazione di formattazione qualsiasi cifra frazionaria rimanente viene troncata. In un'operazione di analisi che chiama il metodo <xref:System.TimeSpan.ParseExact%2A?displayProperty=nameWithType> o <xref:System.TimeSpan.TryParseExact%2A?displayProperty=nameWithType> la stringa di input deve contenere esattamente quattro cifre frazionarie.

Nell'esempio seguente viene usato l'identificatore di formato personalizzato "ffff" per visualizzare i decimillesimi di secondo in un valore <xref:System.TimeSpan>. "ffff" viene usato prima come unico identificatore di formato e quindi viene usato in combinazione con l'identificatore "s" in una stringa di formato personalizzato.

[!code-csharp[Conceptual.TimeSpan.Custom#20](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/fspecifiers1.cs#20)]
[!code-vb[Conceptual.TimeSpan.Custom#20](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/fspecifiers1.vb#20)]

[Torna alla tabella](#table)

## <a name="the-fffff-custom-format-specifier"></a><a name="f5Specifier"></a>Identificatore di formato personalizzato "fffff"

L'identificatore di formato personalizzato "fffff" (con cinque caratteri "f") restituisce i centesimi di millesimo di secondo in un intervallo di tempo. In un'operazione di formattazione qualsiasi cifra frazionaria rimanente viene troncata. In un'operazione di analisi che chiama il metodo <xref:System.TimeSpan.ParseExact%2A?displayProperty=nameWithType> o <xref:System.TimeSpan.TryParseExact%2A?displayProperty=nameWithType> la stringa di input deve contenere esattamente cinque cifre frazionarie.

Nell'esempio seguente viene usato l'identificatore di formato personalizzato "fffff" per visualizzare i centesimi di millesimo di secondo in un valore <xref:System.TimeSpan>. "fffff" viene usato prima come unico identificatore di formato e quindi viene usato in combinazione con l'identificatore "s" in una stringa di formato personalizzato.

[!code-csharp[Conceptual.TimeSpan.Custom#20](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/fspecifiers1.cs#20)]
[!code-vb[Conceptual.TimeSpan.Custom#20](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/fspecifiers1.vb#20)]

[Torna alla tabella](#table)

## <a name="the-ffffff-custom-format-specifier"></a><a name="f6Specifier"></a>Identificatore di formato personalizzato "FFFFFF"

L'identificatore di formato personalizzato "ffffff" (con sei caratteri "f") restituisce i milionesimi di secondo in un intervallo di tempo. In un'operazione di formattazione qualsiasi cifra frazionaria rimanente viene troncata. In un'operazione di analisi che chiama il metodo <xref:System.TimeSpan.ParseExact%2A?displayProperty=nameWithType> o <xref:System.TimeSpan.TryParseExact%2A?displayProperty=nameWithType> la stringa di input deve contenere esattamente sei cifre frazionarie.

Nell'esempio seguente viene usato l'identificatore di formato personalizzato "ffffff" per visualizzare i milionesimi di secondo in un valore <xref:System.TimeSpan>. Viene usato prima come unico identificatore di formato, quindi viene usato in combinazione con l'identificatore "s" in una stringa di formato personalizzato.

[!code-csharp[Conceptual.TimeSpan.Custom#20](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/fspecifiers1.cs#20)]
[!code-vb[Conceptual.TimeSpan.Custom#20](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/fspecifiers1.vb#20)]

[Torna alla tabella](#table)

## <a name="the-fffffff-custom-format-specifier"></a><a name="f7Specifier"></a>Identificatore di formato personalizzato "fffffff"

L'identificatore di formato personalizzato "fffffff" (con sette caratteri "f") restituisce i decimilionesimi di secondo (o il numero frazionario di tick) in un intervallo di tempo. In un'operazione di analisi che chiama il metodo <xref:System.TimeSpan.ParseExact%2A?displayProperty=nameWithType> o <xref:System.TimeSpan.TryParseExact%2A?displayProperty=nameWithType> la stringa di input deve contenere esattamente sette cifre frazionarie.

Nell'esempio seguente viene usato l'identificatore di formato personalizzato "fffffff" per visualizzare il numero frazionario di tick in un valore <xref:System.TimeSpan>. Viene usato prima come unico identificatore di formato, quindi viene usato in combinazione con l'identificatore "s" in una stringa di formato personalizzato.

[!code-csharp[Conceptual.TimeSpan.Custom#20](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/fspecifiers1.cs#20)]
[!code-vb[Conceptual.TimeSpan.Custom#20](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/fspecifiers1.vb#20)]

[Torna alla tabella](#table)

## <a name="the-f-custom-format-specifier"></a><a name="F_Specifier"></a>Identificatore di formato personalizzato "F"

L'identificatore di formato personalizzato "F" restituisce i decimi di secondo in un intervallo di tempo. In un'operazione di formattazione qualsiasi cifra frazionaria rimanente viene troncata. Se il valore dei decimi di secondo dell'intervallo di tempo è zero, non viene incluso nella stringa del risultato. In un'operazione di analisi che chiama il metodo <xref:System.TimeSpan.ParseExact%2A?displayProperty=nameWithType> o <xref:System.TimeSpan.TryParseExact%2A?displayProperty=nameWithType> la presenza della cifra dei decimi di secondo è facoltativa.

Se l'identificatore di formato personalizzato "F" viene usato da solo, specificare "%F" in modo che non venga interpretato erroneamente come stringa in formato standard.

Nell'esempio seguente viene usato l'identificatore di formato personalizzato "F" per visualizzare i decimi di secondo in un valore <xref:System.TimeSpan>. Questo identificatore di formato personalizzato viene usato anche in un'operazione di analisi.

[!code-csharp[Conceptual.TimeSpan.Custom#21](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/f_specifiers1.cs#21)]
[!code-vb[Conceptual.TimeSpan.Custom#21](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/f_specifiers1.vb#21)]

[Torna alla tabella](#table)

## <a name="the-ff-custom-format-specifier"></a><a name="FF_Specifier"></a>Identificatore di formato personalizzato "FF"

L'identificatore di formato personalizzato "FF" restituisce i centesimi di secondo in un intervallo di tempo. In un'operazione di formattazione qualsiasi cifra frazionaria rimanente viene troncata. Se sono presenti zeri frazionari finali, non vengono inclusi nella stringa del risultato. In un'operazione di analisi che chiama il metodo <xref:System.TimeSpan.ParseExact%2A?displayProperty=nameWithType> o <xref:System.TimeSpan.TryParseExact%2A?displayProperty=nameWithType> la presenza della cifra dei decimi e dei centesimi di secondo è facoltativa.

Nell'esempio seguente viene usato l'identificatore di formato personalizzato "FF" per visualizzare i centesimi di secondo in un valore <xref:System.TimeSpan>. Questo identificatore di formato personalizzato viene usato anche in un'operazione di analisi.

[!code-csharp[Conceptual.TimeSpan.Custom#22](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/f_specifiers1.cs#22)]
[!code-vb[Conceptual.TimeSpan.Custom#22](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/f_specifiers1.vb#22)]

[Torna alla tabella](#table)

## <a name="the-fff-custom-format-specifier"></a><a name="F3_Specifier"></a>Identificatore di formato personalizzato "FFF"

L'identificatore di formato personalizzato "FFF" (con tre caratteri "F") restituisce i millisecondi in un intervallo di tempo. In un'operazione di formattazione qualsiasi cifra frazionaria rimanente viene troncata. Se sono presenti zeri frazionari finali, non vengono inclusi nella stringa del risultato. In un'operazione di analisi che chiama il metodo <xref:System.TimeSpan.ParseExact%2A?displayProperty=nameWithType> o <xref:System.TimeSpan.TryParseExact%2A?displayProperty=nameWithType> la presenza della cifra dei decimi, dei centesimi e dei millesimi di secondo è facoltativa.

Nell'esempio seguente viene usato l'identificatore di formato personalizzato "FFF" per visualizzare i millesimi di secondo in un valore <xref:System.TimeSpan>. Questo identificatore di formato personalizzato viene usato anche in un'operazione di analisi.

[!code-csharp[Conceptual.TimeSpan.Custom#23](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/f_specifiers1.cs#23)]
[!code-vb[Conceptual.TimeSpan.Custom#23](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/f_specifiers1.vb#23)]

[Torna alla tabella](#table)

## <a name="the-ffff-custom-format-specifier"></a><a name="F4_Specifier"></a>Identificatore di formato personalizzato "FFFF"

L'identificatore di formato personalizzato "FFFF" (con quattro caratteri "F") restituisce i decimillesimi di secondo in un intervallo di tempo. In un'operazione di formattazione qualsiasi cifra frazionaria rimanente viene troncata. Se sono presenti zeri frazionari finali, non vengono inclusi nella stringa del risultato. In un'operazione di analisi che chiama il metodo <xref:System.TimeSpan.ParseExact%2A?displayProperty=nameWithType> o <xref:System.TimeSpan.TryParseExact%2A?displayProperty=nameWithType> la presenza della cifra dei decimi, dei centesimi, dei millesimi e dei decimillesimi di secondo è facoltativa.

Nell'esempio seguente viene usato l'identificatore di formato personalizzato "FFFF" per visualizzare i decimillesimi di secondo in un valore <xref:System.TimeSpan>. L'identificatore di formato personalizzato "FFFF" viene usato anche in un'operazione di analisi.

[!code-csharp[Conceptual.TimeSpan.Custom#24](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/f_specifiers1.cs#24)]
[!code-vb[Conceptual.TimeSpan.Custom#24](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/f_specifiers1.vb#24)]

[Torna alla tabella](#table)

## <a name="the-fffff-custom-format-specifier"></a><a name="F5_Specifier"></a>Identificatore di formato personalizzato "FFFFF"

L'identificatore di formato personalizzato "FFFFF" (con cinque caratteri "F") restituisce i centesimi di millesimo di secondo in un intervallo di tempo. In un'operazione di formattazione qualsiasi cifra frazionaria rimanente viene troncata. Se sono presenti zeri frazionari finali, non vengono inclusi nella stringa del risultato. In un'operazione di analisi che chiama il metodo <xref:System.TimeSpan.ParseExact%2A?displayProperty=nameWithType> o <xref:System.TimeSpan.TryParseExact%2A?displayProperty=nameWithType> la presenza della cifra dei decimi, dei centesimi, dei millesimi, dei decimillesimi e dei centesimi di millesimi di secondo è facoltativa.

Nell'esempio seguente viene usato l'identificatore di formato personalizzato "FFFFF" per visualizzare i centesimi di millesimo di secondo in un valore <xref:System.TimeSpan>. L'identificatore di formato personalizzato "FFFFF" viene usato anche in un'operazione di analisi.

[!code-csharp[Conceptual.TimeSpan.Custom#25](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/f_specifiers1.cs#25)]
[!code-vb[Conceptual.TimeSpan.Custom#25](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/f_specifiers1.vb#25)]

[Torna alla tabella](#table)

## <a name="the-ffffff-custom-format-specifier"></a><a name="F6_Specifier"></a>Identificatore di formato personalizzato "FFFFFF"

L'identificatore di formato personalizzato "FFFFFF" (con sei caratteri "F") restituisce i milionesimi di secondo in un intervallo di tempo. In un'operazione di formattazione qualsiasi cifra frazionaria rimanente viene troncata. Se sono presenti zeri frazionari finali, non vengono inclusi nella stringa del risultato. In un'operazione di analisi che chiama il metodo <xref:System.TimeSpan.ParseExact%2A?displayProperty=nameWithType> o <xref:System.TimeSpan.TryParseExact%2A?displayProperty=nameWithType> la presenza della cifra dei decimi, dei centesimi, dei millesimi, dei decimillesimi, dei centesimi di millesimi e dei milionesimi di secondo è facoltativa.

Nell'esempio seguente viene usato l'identificatore di formato personalizzato "FFFFFF" per visualizzare i milionesimi di secondo in un valore <xref:System.TimeSpan>. Questo identificatore di formato personalizzato viene usato anche in un'operazione di analisi.

[!code-csharp[Conceptual.TimeSpan.Custom#26](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/f_specifiers1.cs#26)]
[!code-vb[Conceptual.TimeSpan.Custom#26](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/f_specifiers1.vb#26)]

[Torna alla tabella](#table)

## <a name="the-fffffff-custom-format-specifier"></a><a name="F7_Specifier"></a>Identificatore di formato personalizzato "FFFFFFF"

L'identificatore di formato personalizzato "FFFFFFF" (con sette caratteri "F") restituisce i decimilionesimi di secondo (o il numero frazionario di tick) in un intervallo di tempo. Se sono presenti zeri frazionari finali, non vengono inclusi nella stringa del risultato. In un'operazione di analisi che chiama il metodo <xref:System.TimeSpan.ParseExact%2A?displayProperty=nameWithType> o <xref:System.TimeSpan.TryParseExact%2A?displayProperty=nameWithType> la presenza delle sette cifre frazionarie nella stringa di input è facoltativa.

Nell'esempio seguente viene usato l'identificatore di formato personalizzato "FFFFFFF" per visualizzare la parte frazionaria di un secondo in un valore <xref:System.TimeSpan>. Questo identificatore di formato personalizzato viene usato anche in un'operazione di analisi.

[!code-csharp[Conceptual.TimeSpan.Custom#27](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/f_specifiers1.cs#27)]
[!code-vb[Conceptual.TimeSpan.Custom#27](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/f_specifiers1.vb#27)]

[Torna alla tabella](#table)

## <a name="other-characters"></a>Altri caratteri

Qualsiasi altro carattere senza codice di escape in una stringa di formato, incluso un carattere di spazio vuoto, viene interpretato come identificatore di formato personalizzato. Nella maggior parte dei casi la presenza di qualsiasi altro carattere senza codice di escape restituisce un oggetto <xref:System.FormatException>.

È possibile includere un carattere letterale in una stringa di formato in due modi:

- Racchiudendolo tra virgolette singole (delimitatore di stringa letterale).

- Inserendo prima del carattere una barra rovesciata("\\"), interpretata come carattere di escape. In C#, pertanto, la stringa di formato deve essere @-quoted o il carattere letterale deve essere preceduto da una barra rovesciata aggiuntiva.

  In alcuni casi, potrebbe essere necessario utilizzare la logica condizionale per includere un valore letterale preceduto da una barra rovesciata in una stringa di formato. Nell'esempio seguente viene utilizzata la logica condizionale per includere un simbolo di segno per intervalli di tempo negativi.

  [!code-csharp[Conceptual.TimeSpan.Custom#29](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/negativevalues1.cs#29)]
  [!code-vb[Conceptual.TimeSpan.Custom#29](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/negativevalues1.vb#29)]

.NET non definisce una grammatica per i separatori negli intervalli di tempo. I separatori tra giorni e ore, ore e minuti, minuti e secondi e secondi e frazioni di secondo devono pertanto essere trattati come valori letterali carattere in una stringa di formato.

Nell'esempio seguente vengono usati sia il carattere di escape che la virgoletta singola per definire una stringa di formato personalizzata che include la parola "minutes" nella stringa di output.

[!code-csharp[Conceptual.TimeSpan.Custom#28](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/literal1.cs#28)]
[!code-vb[Conceptual.TimeSpan.Custom#28](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/literal1.vb#28)]

[Torna alla tabella](#table)

## <a name="see-also"></a>Vedere anche

- [Formattazione di tipi](formatting-types.md)
- [Stringhe di formato TimeSpan standard](standard-timespan-format-strings.md)

---
title: Formattazione composita
description: Informazioni sulla formattazione composita di .NET, che accetta come input un elenco di oggetti e una stringa di formato composito, che contiene testo fisso con i segnaposto indicizzati.
ms.date: 10/26/2018
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- parameter specifiers
- strings [.NET Framework], alignment
- format specifiers, composite formatting
- strings [.NET Framework], composite
- composite formatting
- objects [.NET Framework], formatting multiple objects
ms.assetid: 87b7d528-73f6-43c6-b71a-f23043039a49
ms.openlocfilehash: 36197b382c449a2570e1d5530f307c4e66b0d983
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/05/2020
ms.locfileid: "84447264"
---
# <a name="composite-formatting"></a>Formattazione composita

La funzionalità di formattazione composta di .NET consente di usare come input un elenco di oggetti e una stringa di formato composto. Una stringa di formato composto è costituita da testo fisso alternato a segnaposto indicizzati, denominati elementi di formato, che corrispondono agli oggetti dell'elenco. L'operazione di formattazione produce una stringa risultato costituita dal testo fisso originale alternato alla rappresentazione di stringa degli oggetti dell'elenco.  
  
> [!IMPORTANT]
> Invece di usare le stringhe di formato composito, è possibile usare *stringhe interpolate* se il linguaggio e la versione del linguaggio in uso le supportano. Una stringa interpolata è una stringa che contiene *espressioni interpolate*. Ogni espressione interpolata viene risolta con il valore dell'espressione e inclusa nella stringa di risultato al momento dell'assegnazione della stringa. Per altre informazioni, vedere [Interpolazione di stringhe (Riferimenti per C#)](../../csharp/language-reference/tokens/interpolated.md) e [Stringhe interpolate (Riferimenti per Visual Basic)](../../visual-basic/programming-guide/language-features/strings/interpolated-strings.md).

La funzionalità di formattazione composita è supportata da metodi quali i seguenti:  
  
- <xref:System.String.Format%2A?displayProperty=nameWithType>, che restituisce una stringa di risultato formattata.  
  
- <xref:System.Text.StringBuilder.AppendFormat%2A?displayProperty=nameWithType>, che aggiunge una stringa di risultato formattata a un oggetto <xref:System.Text.StringBuilder>.
- Alcuni overload del metodo di <xref:System.Console.WriteLine%2A?displayProperty=nameWithType>, che visualizza una stringa di risultato formattata nella console.  
  
- Alcuni overload del metodo di <xref:System.IO.TextWriter.WriteLine%2A?displayProperty=nameWithType>, che visualizza una stringa di risultato formattata in un flusso o in un file. Le classi derivate da <xref:System.IO.TextWriter>, come <xref:System.IO.StreamWriter> e <xref:System.Web.UI.HtmlTextWriter>, condividono questa funzionalità.  
  
- <xref:System.Diagnostics.Debug.WriteLine%28System.String%2CSystem.Object%5B%5D%29?displayProperty=nameWithType>, che restituisce un messaggio formattato nei listener di traccia.  
  
- Metodi <xref:System.Diagnostics.Trace.TraceError%28System.String%2CSystem.Object%5B%5D%29?displayProperty=nameWithType>, <xref:System.Diagnostics.Trace.TraceInformation%28System.String%2CSystem.Object%5B%5D%29?displayProperty=nameWithType> e <xref:System.Diagnostics.Trace.TraceWarning%28System.String%2CSystem.Object%5B%5D%29?displayProperty=nameWithType>, che restituiscono messaggi formattati nei listener di traccia.  
  
- Metodo di <xref:System.Diagnostics.TraceSource.TraceInformation%28System.String%2CSystem.Object%5B%5D%29?displayProperty=nameWithType>, che scrive un metodo informativo nei listener di traccia.  
  
## <a name="composite-format-string"></a>Stringa di formato composto  
 Una stringa di formato composto e un elenco di oggetti vengono usati come argomenti di metodi che supportano la funzionalità di formattazione composta. Una stringa di formato composto è costituita da zero o più esecuzioni di testo fisso alternate a uno o più elementi di formato. Il testo fisso corrisponde a una stringa di propria scelta e ogni elemento di formato corrisponde a un oggetto o una struttura boxed dell'elenco. La funzionalità di formattazione composta restituisce una nuova stringa risultato in cui ciascun elemento di formato viene sostituito dalla rappresentazione di stringa di origine dell'oggetto corrispondente dell'elenco.  
  
 Si consideri il frammento di codice <xref:System.String.Format%2A> riportato di seguito.  
  
 [!code-csharp[Formatting.Composite#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Composite/cs/Composite1.cs#1)]
 [!code-vb[Formatting.Composite#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Composite/vb/Composite1.vb#1)]  
  
 Il testo corretto è "`Name =`" e "`, hours =`". Gli elementi di formato sono "`{0}`", il cui indice è 0, che corrisponde all'elemento `name` dell'oggetto, e "`{1:hh}`", il cui indice è 1, che corrisponde all'elemento `DateTime.Now` dell'oggetto.  
  
## <a name="format-item-syntax"></a>Sintassi degli elementi di formato  
 Ogni elemento di formato usa il formato seguente ed è costituito dai componenti riportati di seguito:  
  
 `{`*index*[ `,` *allineamento*] [ `:` *FormatString*]`}`  
  
 Le parentesi graffe corrispondenti "{" e "}" sono obbligatorie.  
  
### <a name="index-component"></a>Componente di indice  
 Il componente obbligatorio *index*, denominato anche identificatore di parametro, corrisponde a un numero a partire da 0 che identifica un elemento corrispondente nell'elenco di oggetti. Con l'elemento di formato con identificatore di parametro 0 viene formattato il primo oggetto dell'elenco, con l'elemento di formato con identificatore di parametro 1 viene formattato il secondo oggetto dell'elenco e così via. L'esempio seguente include quattro identificatori di parametro, numerati da zero a tre, per rappresentare i numeri primi inferiori a dieci:  
  
 [!code-csharp[Formatting.Composite#7](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Composite/cs/index1.cs#7)]
 [!code-vb[Formatting.Composite#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Composite/vb/index1.vb#7)]  
  
 Più elementi di formato possono fare riferimento allo stesso elemento dell'elenco di oggetti specificando lo stesso identificatore di parametro. È ad esempio possibile formattare lo stesso valore numerico in formato esadecimale, scientifico e numerico specificando una stringa di formato composito, ad esempio "0x {0:X} {0:E} {0:N} ", come illustrato nell'esempio seguente.  
  
 [!code-csharp[Formatting.Composite#10](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Composite/cs/index1.cs#10)]
 [!code-vb[Formatting.Composite#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Composite/vb/index1.vb#10)]  
  
 Ogni elemento di formato può fare riferimento a un oggetto dell'elenco. Se ad esempio sono presenti tre oggetti, è possibile formattare il secondo, il primo e il terzo oggetto specificando una stringa di formato composita come la seguente: " {1} {0} {2} ". Gli oggetti a cui non fa riferimento un elemento di formato vengono ignorati. <xref:System.FormatException>Viene generata un'eccezione in fase di esecuzione se un identificatore di parametro designa un elemento non compreso nei limiti dell'elenco di oggetti.  
  
### <a name="alignment-component"></a>Componente di allineamento  
 Il componente facoltativo *alignment* corrisponde a un intero con segno che indica la larghezza preferita del campo formattato. Se il valore di *alignment* è inferiore alla lunghezza della stringa formattata, il componente *alignment* verrà ignorato e come larghezza del campo verrà usata la lunghezza della stringa. I dati formattati verranno allineati a destra se il valore di *alignment* è positivo e a sinistra se il valore di *alignment* è negativo. Per la spaziatura eventualmente necessaria verranno usati spazi vuoti. Se viene specificato il componente *alignment*, la virgola è obbligatoria.  
  
 L'esempio seguente definisce due matrici, una contenente i nomi dei dipendenti e l'altra contenente il numero di ore in cui hanno lavorato per un periodo di due settimane. La stringa di formato composto allinea a sinistra i nomi in un campo di 20 caratteri e allinea a destra le ore in un campo di 5 caratteri. Si noti che la stringa di formato standard "N1" viene usata anche per formattare le ore con una cifra frazionaria.  
  
 [!code-csharp[Formatting.Composite#8](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Composite/cs/alignment1.cs#8)]
 [!code-vb[Formatting.Composite#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Composite/vb/alignment1.vb#8)]  
  
### <a name="format-string-component"></a>Componente della stringa di formato  
 Il componente *formatString* facoltativo è una stringa di formato appropriata per il tipo di oggetto formattato. Specificare una stringa di formato numerico standard o personalizzata se l'oggetto corrispondente è un valore numerico, una stringa di formato di data e ora standard o personalizzata se l'oggetto corrispondente è un oggetto <xref:System.DateTime> o una [stringa di formato di enumerazione](enumeration-format-strings.md) se l'oggetto corrispondente è un valore di enumerazione. Se il componente *formatString* viene omesso, verrà usato l'identificatore di formato generale "G" per un tipo numerico, di data e ora o di enumerazione. Se viene specificato il componente *formatString*, i due punti sono obbligatori.  
  
 Nella tabella seguente sono elencati i tipi o le categorie di tipi della libreria di classi .NET Framework che supportano un set predefinito di stringhe di formato e vengono forniti collegamenti ad argomenti in cui vengono elencate le stringhe di formato supportate. Si noti che la formattazione delle stringhe è un meccanismo estendibile che consente di definire nuove stringhe di formato per tutti i tipi esistenti nonché definire un set di stringhe di formato supportate da un tipo definito dall'applicazione. Per altre informazioni, vedere gli argomenti delle interfacce <xref:System.IFormattable> e <xref:System.ICustomFormatter>.  
  
|Tipo o categoria di tipo|Vedere|  
|---------------------------|---------|  
|Tipi di data e ora (<xref:System.DateTime>, <xref:System.DateTimeOffset>)|[Stringhe di formato di data e ora standard](standard-date-and-time-format-strings.md)<br /><br /> [Stringhe di formato di data e ora personalizzato](custom-date-and-time-format-strings.md)|  
|Tipi di enumerazione (tutti derivati da <xref:System.Enum?displayProperty=nameWithType>)|[Stringhe di formato di enumerazione](enumeration-format-strings.md)|  
|Tipi numerici (<xref:System.Numerics.BigInteger>, <xref:System.Byte>, <xref:System.Decimal>, <xref:System.Double>, <xref:System.Int16>, <xref:System.Int32>, <xref:System.Int64>, <xref:System.SByte>, <xref:System.Single>, <xref:System.UInt16>, <xref:System.UInt32>, <xref:System.UInt64>)|[Stringhe di formato numerico standard](standard-numeric-format-strings.md)<br /><br /> [Stringhe di formato numerico personalizzato](custom-numeric-format-strings.md)|  
|<xref:System.Guid>|<xref:System.Guid.ToString%28System.String%29?displayProperty=nameWithType>|  
|<xref:System.TimeSpan>|[Stringhe di formato TimeSpan standard](standard-timespan-format-strings.md)<br /><br /> [Stringhe di formato TimeSpan personalizzate](custom-timespan-format-strings.md)|  
  
### <a name="escaping-braces"></a>Sequenze di escape delle parentesi graffe  
 Le parentesi graffe di apertura e di chiusura sono interpretate come l'inizio e la fine di un elemento di formato. Di conseguenza, è necessario usare una sequenza di escape per visualizzare una parentesi graffa di apertura o di chiusura letterale. Specificare due parentesi graffe di apertura ("{{") nel testo fisso per visualizzare una parentesi di apertura ("{") oppure due parentesi graffe di chiusura ("}}") per visualizzare una parentesi graffa di chiusura ("}"). Le parentesi graffe in un elemento di formato vengono interpretate sequenzialmente nell'ordine in cui sono rilevate. L'interpretazione delle parentesi graffe annidate non è supportata.  
  
 Il tipo di interpretazione delle parentesi graffe in sequenza di escape può produrre risultati imprevisti. Si consideri, ad esempio, l'elemento di formato "{{{0:D}}}", destinato alla visualizzazione di una parentesi graffa di apertura, un valore numerico formattato come numero decimale e una parentesi graffa di chiusura. L'elemento di formato viene tuttavia interpretato nel modo seguente:  
  
1. Le prime due parentesi apertura ("{{") presentano una sequenza di escape e producono una parentesi graffa di apertura.  
  
2. I tre caratteri successivi ("{0:") sono interpretati come l'inizio di un elemento di formato.  
  
3. Il carattere successivo ("D") verrebbe interpretato come identificatore del formato numerico standard Decimal, ma le due parentesi graffe successive con sequenza di escape ("}}") producono una parentesi graffa singola. Poiché la stringa risultante ("D}") non è un identificatore di un formato numerico standard, viene interpretata come una stringa di formato personalizzata che indica la visualizzazione della stringa letterale "D}".  
  
4. L'ultima parentesi graffa ("}") viene interpretata come la fine dell'elemento di formato.  
  
5. Il risultato finale visualizzato è la stringa letterale "{D}". Il valore numerico da formattare non viene visualizzato.  
  
 Per evitare di interpretare in modo errato gli elementi di formato e le parentesi graffe con sequenza di escape, è preferibile formattarli separatamente, ovvero nella prima operazione di formattazione visualizzare una parentesi graffa di apertura letterale, nella successiva operazione visualizzare il risultato dell'elemento di formato, quindi nell'ultima operazione visualizzare una parentesi graffa di chiusura letterale. Questo approccio viene illustrato nell'esempio seguente:  
  
 [!code-csharp[Formatting.Composite#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Composite/cs/Escaping1.cs#2)]
 [!code-vb[Formatting.Composite#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Composite/vb/Escaping1.vb#2)]  
  
### <a name="processing-order"></a>Ordine di elaborazione  
 Se la chiamata al metodo di formattazione composita include un argomento <xref:System.IFormatProvider> il cui valore non è `null`, il runtime chiama il metodo <xref:System.IFormatProvider.GetFormat%2A?displayProperty=nameWithType> per richiedere un'implementazione di <xref:System.ICustomFormatter>. Se il metodo è in grado di restituire un'implementazione <xref:System.ICustomFormatter>, viene memorizzata nella cache per la durata della chiamata del metodo di formattazione composita.
  
 Ogni valore nell'elenco di parametri che corrisponde a un elemento di formato viene convertito in una stringa, nel modo seguente:  
  
1. Se il valore da formattare è `null`, viene restituita una stringa vuota <xref:System.String.Empty?displayProperty=nameWithType>.  
  
2. Se l'implementazione di <xref:System.ICustomFormatter> è disponibile, il runtime chiama il metodo <xref:System.ICustomFormatter.Format%2A>. Passa al metodo il valore *formatString* dell'elemento di formato, se disponibile, o `null` in caso contrario, con l'implementazione di <xref:System.IFormatProvider>. Se la chiamata al metodo <xref:System.ICustomFormatter.Format%2A?displayProperty=nameWithType> restituisce `null`, l'esecuzione procede al passaggio successivo; in caso contrario, viene restituito il risultato della chiamata <xref:System.ICustomFormatter.Format%2A?displayProperty=nameWithType>.
  
3. Se il valore implementa l'interfaccia <xref:System.IFormattable>, verrà chiamato il relativo metodo <xref:System.IFormattable.ToString%28System.String%2CSystem.IFormatProvider%29>. Al metodo viene passato il valore *formatString*, se disponibile nell'elemento di formato, o `null` in caso contrario. L'argomento <xref:System.IFormatProvider> è determinato come segue:  
  
    - Per un valore numerico, se viene chiamato un metodo di formattazione composita con un argomento non Null <xref:System.IFormatProvider>, il runtime richiede un oggetto <xref:System.Globalization.NumberFormatInfo> dal relativo metodo <xref:System.IFormatProvider.GetFormat%2A?displayProperty=nameWithType>. Se non è in grado di fornirne uno, se il valore dell'argomento è `null` o se il metodo di formattazione composita non dispone di un parametro di <xref:System.IFormatProvider>, viene usato l'oggetto <xref:System.Globalization.NumberFormatInfo> per le impostazioni cultura del thread corrente.  
  
    - Per un valore di data e ora, se viene chiamato un metodo di formattazione composita con un argomento non Null <xref:System.IFormatProvider>, il runtime richiede un oggetto <xref:System.Globalization.DateTimeFormatInfo> dal relativo metodo <xref:System.IFormatProvider.GetFormat%2A?displayProperty=nameWithType>. Se non è in grado di fornirne uno, se il valore dell'argomento è `null` o se il metodo di formattazione composita non dispone di un parametro di <xref:System.IFormatProvider>, viene usato l'oggetto <xref:System.Globalization.DateTimeFormatInfo> per le impostazioni cultura del thread corrente.  
  
    - Per gli oggetti di altri tipi, se un metodo di formattazione composita viene chiamato con un argomento <xref:System.IFormatProvider>, il relativo valore viene passato direttamente all'implementazione di <xref:System.IFormattable.ToString%2A?displayProperty=nameWithType>. In caso contrario, `null` viene passato all'implementazione di <xref:System.IFormattable.ToString%2A?displayProperty=nameWithType>.  
  
4. Viene chiamato il metodo senza parametri `ToString` del tipo, che esegue l'override di <xref:System.Object.ToString?displayProperty=nameWithType> o eredita il comportamento della relativa classe di base. In questo caso la stringa di formato specificata dal componente *formatString* nell'elemento di formato, se presente, viene ignorata.  
  
 L'allineamento viene applicato al termine dei precedenti passaggi.  
  
## <a name="code-examples"></a>Esempi di codice  
 Nell'esempio seguente vengono illustrate una stringa creata con la formattazione composita e un'altra creata mediante il metodo `ToString` di un oggetto. Entrambi i tipi di formattazione producono risultati equivalenti.  
  
 [!code-csharp[Formatting.Composite#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Composite/cs/Composite1.cs#3)]
 [!code-vb[Formatting.Composite#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Composite/vb/Composite1.vb#3)]  
  
 Presupponendo che il giorno corrente sia un giovedì di maggio, il valore di entrambe le stringhe dell'esempio precedente sarà `Thursday May` se sono specificate le impostazioni cultura inglesi.  
  
 <xref:System.Console.WriteLine%2A?displayProperty=nameWithType> espone la stessa funzionalità di <xref:System.String.Format%2A?displayProperty=nameWithType>. L'unica differenza tra i due metodi è che <xref:System.String.Format%2A?displayProperty=nameWithType> restituisce il risultato come stringa, mentre <xref:System.Console.WriteLine%2A?displayProperty=nameWithType> scrive il risultato nel flusso di output associato all'oggetto <xref:System.Console>. Nell'esempio seguente viene utilizzato il metodo <xref:System.Console.WriteLine%2A?displayProperty=nameWithType> per formattare il valore di `MyInt` come valore di valuta.  
  
 [!code-csharp[Formatting.Composite#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Composite/cs/Composite1.cs#4)]
 [!code-vb[Formatting.Composite#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Composite/vb/Composite1.vb#4)]  
  
 Nell'esempio riportato di seguito vengono illustrate la formattazione di più oggetti e la formattazione di un oggetto in due diversi modi.  
  
 [!code-csharp[Formatting.Composite#5](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Composite/cs/Composite1.cs#5)]
 [!code-vb[Formatting.Composite#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Composite/vb/Composite1.vb#5)]  
  
 Nell'esempio seguente viene illustrato l'utilizzo dell'allineamento nella formattazione. Gli argomenti formattati sono inseriti tra barre verticali (&#124;) per evidenziare l'allineamento ottenuto.  
  
 [!code-csharp[Formatting.Composite#6](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Composite/cs/Composite1.cs#6)]
 [!code-vb[Formatting.Composite#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Composite/vb/Composite1.vb#6)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Console.WriteLine%2A>
- <xref:System.String.Format%2A?displayProperty=nameWithType>
- [Interpolazione di stringhe (C#)](../../csharp/language-reference/tokens/interpolated.md)
- [Interpolazione di stringhe (Visual Basic)](../../visual-basic/programming-guide/language-features/strings/interpolated-strings.md)
- [Formattazione di tipi](formatting-types.md)
- [Stringhe di formato numerico standard](standard-numeric-format-strings.md)
- [Stringhe di formato numerico personalizzato](custom-numeric-format-strings.md)
- [Stringhe di formato di data e ora standard](standard-date-and-time-format-strings.md)
- [Stringhe di formato di data e ora personalizzato](custom-date-and-time-format-strings.md)
- [Stringhe di formato TimeSpan standard](standard-timespan-format-strings.md)
- [Stringhe di formato TimeSpan personalizzate](custom-timespan-format-strings.md)
- [Stringhe di formato di enumerazione](enumeration-format-strings.md)

---
title: Analisi di stringhe numeriche in .NET
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- parsing strings, numeric strings
- numeric strings
- enumerations [.NET Framework], parsing strings
- base types, parsing strings
ms.assetid: e39324ee-72e5-42d4-a80d-bf3ee7fc6c59
ms.openlocfilehash: ac44282a06b2b3710d3a9e5390c7a514c1632c3a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "73127596"
---
# <a name="parsing-numeric-strings-in-net"></a>Analisi di stringhe numeriche in .NET
Tutti i tipi numerici hanno due metodi di analisi statici, `Parse` e `TryParse`, che è possibile usare per convertire la rappresentazione di stringa di un numero in un tipo numerico. Tali metodi consentono di analizzare le stringhe generate usando le stringhe di formato documentate in [Stringhe di formato numerico standard](../../../docs/standard/base-types/standard-numeric-format-strings.md) e [Stringhe di formato numerico personalizzato](../../../docs/standard/base-types/custom-numeric-format-strings.md). Per impostazione predefinita, i metodi `Parse` e `TryParse` consentono di convertire correttamente le stringhe contenenti cifre decimali integrali solo in valori integer. Consentono di convertire correttamente le stringhe che contengono cifre decimali integrali e frazionarie, separatori di gruppi e un separatore decimale in valori a virgola mobile. Il metodo `Parse` genera un'eccezione se l'operazione ha esito negativo, mentre il metodo `TryParse` restituisce `false`.  
  
## <a name="parsing-and-format-providers"></a>Analisi e provider di formato  
 In genere, le rappresentazioni di stringa dei valori numerici differiscono in base alle impostazioni cultura. Gli elementi delle stringhe numeriche, ad esempio simboli di valuta, separatori di gruppi (o migliaia) e separatori decimali, variano in base alle impostazioni cultura. I metodi di analisi usano in modo implicito o esplicito un provider di formato che riconosce le variazioni specifiche delle impostazioni cultura. Se non viene specificato alcun provider di formato in una chiamata al metodo `Parse` o `TryParse`, viene usato il provider di formato associato alle impostazioni cultura del thread corrente, ossia l'oggetto <xref:System.Globalization.NumberFormatInfo> restituito dalla proprietà <xref:System.Globalization.NumberFormatInfo.CurrentInfo%2A?displayProperty=nameWithType>.  
  
 Un provider di formato è rappresentato da un'implementazione <xref:System.IFormatProvider>. Questa interfaccia ha un singolo membro, il metodo <xref:System.IFormatProvider.GetFormat%2A>, il cui unico parametro è un oggetto <xref:System.Type> che rappresenta il tipo da formattare. Questo metodo restituisce l'oggetto che fornisce le informazioni di formattazione. .NET supporta le due implementazioni <xref:System.IFormatProvider> seguenti per l'analisi di stringhe numeriche:  
  
- Un oggetto <xref:System.Globalization.CultureInfo> il cui metodo <xref:System.Globalization.CultureInfo.GetFormat%2A?displayProperty=nameWithType> restituisce un oggetto <xref:System.Globalization.NumberFormatInfo> che fornisce informazioni di formattazione specifiche delle impostazioni cultura.  
  
- Oggetto <xref:System.Globalization.NumberFormatInfo> il cui metodo <xref:System.Globalization.NumberFormatInfo.GetFormat%2A?displayProperty=nameWithType> restituisce se stesso.  
  
 Nell'esempio seguente si tenta di convertire ogni stringa in una matrice in un valore <xref:System.Double>. Per prima cosa si tenta di analizzare la stringa usando un provider di formato che riflette le convenzioni delle impostazioni cultura Inglese (Stati Uniti). Se questa operazione genera un'eccezione <xref:System.FormatException>, si tenta di analizzare la stringa usando un provider di formato che riflette le convenzioni delle impostazioni cultura Francese (Francia).  
  
 [!code-csharp[Parsing.Numbers#1](../../../samples/snippets/csharp/VS_Snippets_CLR/parsing.numbers/cs/formatproviders1.cs#1)]
 [!code-vb[Parsing.Numbers#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/parsing.numbers/vb/formatproviders1.vb#1)]  
  
## <a name="parsing-and-numberstyles-values"></a>Analisi e valori NumberStyles  
 Gli elementi di stile, ad esempio spazi vuoti, separatori di gruppi e separatore decimale, che l'operazione di analisi è in grado di gestire sono definiti da un valore di enumerazione <xref:System.Globalization.NumberStyles>. Per impostazione predefinita, le stringhe che rappresentano i valori integer vengono analizzate usando il valore <xref:System.Globalization.NumberStyles.Integer?displayProperty=nameWithType>, che consente solo cifre numeriche, spazi vuoti iniziali e finali e un segno iniziale. Le stringhe che rappresentano valori a virgola mobile vengono analizzate usando una combinazione dei valori <xref:System.Globalization.NumberStyles.Float?displayProperty=nameWithType> e <xref:System.Globalization.NumberStyles.AllowThousands?displayProperty=nameWithType>. Questo stile composto consente cifre decimali con spazi vuoti iniziali e finali, un segno iniziale, un separatore decimale, un separatore di gruppi e un esponente. Chiamando un overload del metodo `Parse` o `TryParse` che include un parametro di tipo <xref:System.Globalization.NumberStyles> e impostando uno o più flag <xref:System.Globalization.NumberStyles>, è possibile stabilire quali elementi di stile possono essere presenti nella stringa per fare in modo che l'operazione di analisi abbia esito positivo.  
  
 Ad esempio, una stringa contenente un separatore di gruppo non può essere convertita in un valore <xref:System.Int32> tramite il metodo <xref:System.Int32.Parse%28System.String%29?displayProperty=nameWithType>. Tuttavia, la conversione viene completata correttamente se si utilizza il flag <xref:System.Globalization.NumberStyles.AllowThousands?displayProperty=nameWithType>, come illustrato nell'esempio riportato di seguito.  
  
 [!code-csharp[Parsing.Numbers#2](../../../samples/snippets/csharp/VS_Snippets_CLR/parsing.numbers/cs/styles1.cs#2)]
 [!code-vb[Parsing.Numbers#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/parsing.numbers/vb/styles1.vb#2)]  
  
> [!WARNING]
> L'operazione di analisi usa sempre le convenzioni di formattazione di determinate impostazioni cultura. Se non si specificano le impostazioni cultura passando un oggetto <xref:System.Globalization.CultureInfo> o <xref:System.Globalization.NumberFormatInfo>, vengono usate le impostazioni cultura associate al thread corrente.  
  
 Nella tabella seguente sono elencati i membri dell'enumerazione <xref:System.Globalization.NumberStyles> e viene descritto l'effetto degli stessi sull'operazione di analisi.  
  
|Valore NumberStyles|Effetto sulla stringa da analizzare|  
|------------------------|---------------------------------------|  
|<xref:System.Globalization.NumberStyles.None?displayProperty=nameWithType>|Sono consentiti solo valori numerici.|  
|<xref:System.Globalization.NumberStyles.AllowDecimalPoint?displayProperty=nameWithType>|Sono consentiti il separatore decimale e i numeri frazionari. Per i valori integer è consentito solo lo zero come numero frazionario. I separatori decimali validi sono determinati dalla proprietà <xref:System.Globalization.NumberFormatInfo.NumberDecimalSeparator%2A?displayProperty=nameWithType> o <xref:System.Globalization.NumberFormatInfo.CurrencyDecimalSeparator%2A?displayProperty=nameWithType>.|  
|<xref:System.Globalization.NumberStyles.AllowExponent?displayProperty=nameWithType>|Il carattere "e" o "E" può essere usato per indicare la notazione esponenziale. Per altre informazioni, vedere <xref:System.Globalization.NumberStyles>.|  
|<xref:System.Globalization.NumberStyles.AllowLeadingWhite?displayProperty=nameWithType>|È consentito lo spazio vuoto iniziale.|  
|<xref:System.Globalization.NumberStyles.AllowTrailingWhite?displayProperty=nameWithType>|È consentito lo spazio vuoto finale.|  
|<xref:System.Globalization.NumberStyles.AllowLeadingSign?displayProperty=nameWithType>|Un segno positivo o negativo può precedere le cifre numeriche.|  
|<xref:System.Globalization.NumberStyles.AllowTrailingSign?displayProperty=nameWithType>|Un segno positivo o negativo può seguire le cifre numeriche.|  
|<xref:System.Globalization.NumberStyles.AllowParentheses?displayProperty=nameWithType>|Si possono usare parentesi per indicare i valori negativi.|  
|<xref:System.Globalization.NumberStyles.AllowThousands?displayProperty=nameWithType>|È consentito il separatore di gruppi. Il carattere separatore di gruppi è determinato dalla proprietà <xref:System.Globalization.NumberFormatInfo.NumberGroupSeparator%2A?displayProperty=nameWithType> o <xref:System.Globalization.NumberFormatInfo.CurrencyGroupSeparator%2A?displayProperty=nameWithType>.|  
|<xref:System.Globalization.NumberStyles.AllowCurrencySymbol?displayProperty=nameWithType>|È consentito il simbolo di valuta. Il simbolo di valuta è definito dalla proprietà <xref:System.Globalization.NumberFormatInfo.CurrencySymbol%2A?displayProperty=nameWithType>.|  
|<xref:System.Globalization.NumberStyles.AllowHexSpecifier?displayProperty=nameWithType>|La stringa da analizzare viene interpretata come numero esadecimale. Può includere le cifre esadecimali 0-9, A-F e a-f. Questo flag può essere usato solo per analizzare i valori integer.|  
  
 L'enumerazione <xref:System.Globalization.NumberStyles> usa anche i stili compositi seguenti, che includono più flag <xref:System.Globalization.NumberStyles>.  
  
|Valore composito NumberStyles|Include i membri|  
|----------------------------------|----------------------|  
|<xref:System.Globalization.NumberStyles.Integer?displayProperty=nameWithType>|Include gli stili <xref:System.Globalization.NumberStyles.AllowLeadingWhite?displayProperty=nameWithType>, <xref:System.Globalization.NumberStyles.AllowTrailingWhite?displayProperty=nameWithType> e <xref:System.Globalization.NumberStyles.AllowLeadingSign?displayProperty=nameWithType>. Questo è lo stile predefinito usato per analizzare i valori integer.|  
|<xref:System.Globalization.NumberStyles.Number?displayProperty=nameWithType>|Include gli stili <xref:System.Globalization.NumberStyles.AllowLeadingWhite?displayProperty=nameWithType>, <xref:System.Globalization.NumberStyles.AllowTrailingWhite?displayProperty=nameWithType>, <xref:System.Globalization.NumberStyles.AllowLeadingSign?displayProperty=nameWithType>, <xref:System.Globalization.NumberStyles.AllowTrailingSign?displayProperty=nameWithType>, <xref:System.Globalization.NumberStyles.AllowDecimalPoint?displayProperty=nameWithType> e <xref:System.Globalization.NumberStyles.AllowThousands?displayProperty=nameWithType>.|  
|<xref:System.Globalization.NumberStyles.Float?displayProperty=nameWithType>|Include gli stili <xref:System.Globalization.NumberStyles.AllowLeadingWhite?displayProperty=nameWithType>, <xref:System.Globalization.NumberStyles.AllowTrailingWhite?displayProperty=nameWithType>, <xref:System.Globalization.NumberStyles.AllowLeadingSign?displayProperty=nameWithType>, <xref:System.Globalization.NumberStyles.AllowDecimalPoint?displayProperty=nameWithType> e <xref:System.Globalization.NumberStyles.AllowExponent?displayProperty=nameWithType>.|  
|<xref:System.Globalization.NumberStyles.Currency?displayProperty=nameWithType>|Include tutti gli stili tranne <xref:System.Globalization.NumberStyles.AllowExponent?displayProperty=nameWithType> e <xref:System.Globalization.NumberStyles.AllowHexSpecifier?displayProperty=nameWithType>.|  
|<xref:System.Globalization.NumberStyles.Any?displayProperty=nameWithType>|Include tutti gli stili tranne <xref:System.Globalization.NumberStyles.AllowHexSpecifier?displayProperty=nameWithType>.|  
|<xref:System.Globalization.NumberStyles.HexNumber?displayProperty=nameWithType>|Include gli stili <xref:System.Globalization.NumberStyles.AllowLeadingWhite?displayProperty=nameWithType>, <xref:System.Globalization.NumberStyles.AllowTrailingWhite?displayProperty=nameWithType> e <xref:System.Globalization.NumberStyles.AllowHexSpecifier?displayProperty=nameWithType>.|  
  
## <a name="parsing-and-unicode-digits"></a>Analisi e cifre Unicode  
 Lo standard Unicode definisce gli elementi di codice per le cifre in diversi sistemi di scrittura. Ad esempio, gli elementi di codice compresi tra U+0030 e U+0039 rappresentano le cifre latine di base da 0 a 9, gli elementi di codice compresi tra U+09E6 e U+09EF rappresentano le cifre bengalesi da 0 a 9 e gli elementi di codice compresi tra U+FF10 e U+FF19 rappresentano le cifre Fullwidth da 0 a 9. Tuttavia, solo cifre numeriche riconosciute dai metodi di analisi sono le cifre latine di base da 0 a 9 con elementi di codice da U+0030 a U+0039. Se a un metodo di analisi numerico viene passata una stringa che contiene altre cifre, il metodo genera un'eccezione <xref:System.FormatException>.  
  
 Nell'esempio seguente viene usato il metodo <xref:System.Int32.Parse%2A?displayProperty=nameWithType> per analizzare le stringhe costituite da cifre in diversi sistemi di scrittura. Come illustrato nell'output dell'esempio, il tentativo di analizzare le cifre latine di base ha esito positivo, mentre il tentativo di analisi delle cifre Fullwidth, indoarabiche e bengalesi ha esito negativo.  
  
 [!code-csharp[Parsing.Numbers#3](../../../samples/snippets/csharp/VS_Snippets_CLR/parsing.numbers/cs/unicode1.cs#3)]
 [!code-vb[Parsing.Numbers#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/parsing.numbers/vb/unicode1.vb#3)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Globalization.NumberStyles>
- [Parsing Strings](../../../docs/standard/base-types/parsing-strings.md)
- [Formattazione di tipi](../../../docs/standard/base-types/formatting-types.md)

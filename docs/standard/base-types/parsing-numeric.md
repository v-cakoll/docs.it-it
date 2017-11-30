---
title: Analisi di stringhe numeriche in .NET
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- parsing strings, numeric strings
- numeric strings
- enumerations [.NET Framework], parsing strings
- base types, parsing strings
ms.assetid: e39324ee-72e5-42d4-a80d-bf3ee7fc6c59
caps.latest.revision: "20"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 3c9bb58b0d7b45ca197653742844be01ac3bbe41
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="parsing-numeric-strings-in-net"></a>Analisi di stringhe numeriche in rete
Tutti i tipi numerici hanno due metodi di analisi statici, `Parse` e `TryParse`, che è possibile usare per convertire la rappresentazione di stringa di un numero in un tipo numerico. Tali metodi consentono di analizzare le stringhe generate usando le stringhe di formato documentate in [Stringhe di formato numerico standard](../../../docs/standard/base-types/standard-numeric-format-strings.md) e [Stringhe di formato numerico personalizzato](../../../docs/standard/base-types/custom-numeric-format-strings.md). Per impostazione predefinita, i metodi `Parse` e `TryParse` consentono di convertire correttamente le stringhe contenenti cifre decimali integrali solo in valori integer. Consentono di convertire correttamente le stringhe che contengono cifre decimali integrali e frazionarie, separatori di gruppi e un separatore decimale in valori a virgola mobile. Il metodo `Parse` genera un'eccezione se l'operazione ha esito negativo, mentre il metodo `TryParse` restituisce `false`.  
  
## <a name="parsing-and-format-providers"></a>Analisi e provider di formato  
 In genere, le rappresentazioni di stringa dei valori numerici differiscono in base alle impostazioni cultura. Gli elementi delle stringhe numeriche, ad esempio simboli di valuta, separatori di gruppi (o migliaia) e separatori decimali, variano in base alle impostazioni cultura. I metodi di analisi usano in modo implicito o esplicito un provider di formato che riconosce le variazioni specifiche delle impostazioni cultura. Se è specificato alcun provider di formato in una chiamata al `Parse` o `TryParse` (metodo), il provider di formato associato alle impostazioni cultura del thread corrente (il <xref:System.Globalization.NumberFormatInfo> oggetto restituito dal <xref:System.Globalization.NumberFormatInfo.CurrentInfo%2A?displayProperty=nameWithType> proprietà) viene utilizzato.  
  
 Un provider di formato è rappresentato da un <xref:System.IFormatProvider> implementazione. Questa interfaccia dispone di un singolo membro, il <xref:System.IFormatProvider.GetFormat%2A> metodo, di cui l'unico parametro è un <xref:System.Type> oggetto che rappresenta il tipo da formattare. Questo metodo restituisce l'oggetto che fornisce le informazioni di formattazione. .NET supporta i seguenti due <xref:System.IFormatProvider> implementazioni per l'analisi di stringhe numeriche:  
  
-   Oggetto <xref:System.Globalization.CultureInfo> i cui <xref:System.Globalization.CultureInfo.GetFormat%2A?displayProperty=nameWithType> metodo restituisce un <xref:System.Globalization.NumberFormatInfo> oggetto che fornisce informazioni di formattazione specifiche delle impostazioni cultura.  
  
-   Oggetto <xref:System.Globalization.NumberFormatInfo> i cui <xref:System.Globalization.NumberFormatInfo.GetFormat%2A?displayProperty=nameWithType> metodo restituisce se stesso.  
  
 Nell'esempio seguente tenta di convertire ogni stringa in una matrice a un <xref:System.Double> valore. Per prima cosa si tenta di analizzare la stringa usando un provider di formato che riflette le convenzioni delle impostazioni cultura Inglese (Stati Uniti). Se questa operazione genera un <xref:System.FormatException>, tenta di analizzare la stringa tramite un provider di formato che riflette le convenzioni delle impostazioni cultura francesi (Francia).  
  
 [!code-csharp[Parsing.Numbers#1](../../../samples/snippets/csharp/VS_Snippets_CLR/parsing.numbers/cs/formatproviders1.cs#1)]
 [!code-vb[Parsing.Numbers#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/parsing.numbers/vb/formatproviders1.vb#1)]  
  
## <a name="parsing-and-numberstyles-values"></a>Analisi e valori NumberStyles  
 Gli elementi di stile (ad esempio gli spazi vuoti, separatori di gruppi e il separatore decimale) in grado di gestire l'operazione di analisi sono definiti da un <xref:System.Globalization.NumberStyles> valore di enumerazione. Per impostazione predefinita, le stringhe che rappresentano valori interi vengono analizzate tramite il <xref:System.Globalization.NumberStyles.Integer?displayProperty=nameWithType> valore, che consente solo cifre numeriche, spazi vuoti iniziali e finali e un segno iniziale. Analisi delle stringhe che rappresentano i valori a virgola mobile utilizzando una combinazione del <xref:System.Globalization.NumberStyles.Float?displayProperty=nameWithType> e <xref:System.Globalization.NumberStyles.AllowThousands?displayProperty=nameWithType> valori; questo stile composto consente cifre insieme iniziali e finali di spazi vuoti, un segno iniziale, un separatore decimale, un gruppo separatore e un esponente. Chiamando un overload di `Parse` o `TryParse` metodo che include un parametro di tipo <xref:System.Globalization.NumberStyles> e impostazione di uno o più <xref:System.Globalization.NumberStyles> flag, è possibile controllare gli elementi di stile che possono essere presenti nella stringa per l'operazione di analisi esito positivo.  
  
 Ad esempio, una stringa contenente un separatore di gruppo non può essere convertita in un valore <xref:System.Int32> tramite il metodo <xref:System.Int32.Parse%28System.String%29?displayProperty=nameWithType>. Tuttavia, la conversione viene completata correttamente se si utilizza il flag <xref:System.Globalization.NumberStyles.AllowThousands?displayProperty=nameWithType>, come illustrato nell'esempio riportato di seguito.  
  
 [!code-csharp[Parsing.Numbers#2](../../../samples/snippets/csharp/VS_Snippets_CLR/parsing.numbers/cs/styles1.cs#2)]
 [!code-vb[Parsing.Numbers#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/parsing.numbers/vb/styles1.vb#2)]  
  
> [!WARNING]
>  L'operazione di analisi usa sempre le convenzioni di formattazione di determinate impostazioni cultura. Se non si specifica delle impostazioni cultura, passando un <xref:System.Globalization.CultureInfo> o <xref:System.Globalization.NumberFormatInfo> dell'oggetto, viene utilizzata la lingua associata al thread corrente.  
  
 Nella tabella seguente sono elencati i membri del <xref:System.Globalization.NumberStyles> enumerazione e viene descritto l'effetto che hanno sull'operazione di analisi.  
  
|Valore NumberStyles|Effetto sulla stringa da analizzare|  
|------------------------|---------------------------------------|  
|<xref:System.Globalization.NumberStyles.None?displayProperty=nameWithType>|Sono consentiti solo valori numerici.|  
|<xref:System.Globalization.NumberStyles.AllowDecimalPoint?displayProperty=nameWithType>|Sono consentiti il separatore decimale e i numeri frazionari. Per i valori integer è consentito solo lo zero come numero frazionario. Separatori decimali validi sono determinati dalle <xref:System.Globalization.NumberFormatInfo.NumberDecimalSeparator%2A?displayProperty=nameWithType> o <xref:System.Globalization.NumberFormatInfo.CurrencyDecimalSeparator%2A?displayProperty=nameWithType> proprietà.|  
|<xref:System.Globalization.NumberStyles.AllowExponent?displayProperty=nameWithType>|Il carattere "e" o "E" può essere usato per indicare la notazione esponenziale. Vedere <xref:System.Globalization.NumberStyles> per ulteriori informazioni.|  
|<xref:System.Globalization.NumberStyles.AllowLeadingWhite?displayProperty=nameWithType>|È consentito lo spazio vuoto iniziale.|  
|<xref:System.Globalization.NumberStyles.AllowTrailingWhite?displayProperty=nameWithType>|È consentito lo spazio vuoto finale.|  
|<xref:System.Globalization.NumberStyles.AllowLeadingSign?displayProperty=nameWithType>|Un segno positivo o negativo può precedere le cifre numeriche.|  
|<xref:System.Globalization.NumberStyles.AllowTrailingSign?displayProperty=nameWithType>|Un segno positivo o negativo può seguire le cifre numeriche.|  
|<xref:System.Globalization.NumberStyles.AllowParentheses?displayProperty=nameWithType>|Si possono usare parentesi per indicare i valori negativi.|  
|<xref:System.Globalization.NumberStyles.AllowThousands?displayProperty=nameWithType>|È consentito il separatore di gruppi. Il carattere separatore di gruppi è determinato dal <xref:System.Globalization.NumberFormatInfo.NumberGroupSeparator%2A?displayProperty=nameWithType> o <xref:System.Globalization.NumberFormatInfo.CurrencyGroupSeparator%2A?displayProperty=nameWithType> proprietà.|  
|<xref:System.Globalization.NumberStyles.AllowCurrencySymbol?displayProperty=nameWithType>|È consentito il simbolo di valuta. Il simbolo di valuta è definito per il <xref:System.Globalization.NumberFormatInfo.CurrencySymbol%2A?displayProperty=nameWithType> proprietà.|  
|<xref:System.Globalization.NumberStyles.AllowHexSpecifier?displayProperty=nameWithType>|La stringa da analizzare viene interpretata come numero esadecimale. Può includere le cifre esadecimali 0-9, A-F e a-f. Questo flag può essere usato solo per analizzare i valori integer.|  
  
 Inoltre, il <xref:System.Globalization.NumberStyles> enumerazione fornisce i seguenti stili compositi, che includono più <xref:System.Globalization.NumberStyles> flag.  
  
|Valore composito NumberStyles|Include i membri|  
|----------------------------------|----------------------|  
|<xref:System.Globalization.NumberStyles.Integer?displayProperty=nameWithType>|Include il <xref:System.Globalization.NumberStyles.AllowLeadingWhite?displayProperty=nameWithType>, <xref:System.Globalization.NumberStyles.AllowTrailingWhite?displayProperty=nameWithType>, e <xref:System.Globalization.NumberStyles.AllowLeadingSign?displayProperty=nameWithType> stili. Questo è lo stile predefinito usato per analizzare i valori integer.|  
|<xref:System.Globalization.NumberStyles.Number?displayProperty=nameWithType>|Include il <xref:System.Globalization.NumberStyles.AllowLeadingWhite?displayProperty=nameWithType>, <xref:System.Globalization.NumberStyles.AllowTrailingWhite?displayProperty=nameWithType>, <xref:System.Globalization.NumberStyles.AllowLeadingSign?displayProperty=nameWithType>, <xref:System.Globalization.NumberStyles.AllowTrailingSign?displayProperty=nameWithType>, <xref:System.Globalization.NumberStyles.AllowDecimalPoint?displayProperty=nameWithType>, e <xref:System.Globalization.NumberStyles.AllowThousands?displayProperty=nameWithType> stili.|  
|<xref:System.Globalization.NumberStyles.Float?displayProperty=nameWithType>|Include il <xref:System.Globalization.NumberStyles.AllowLeadingWhite?displayProperty=nameWithType>, <xref:System.Globalization.NumberStyles.AllowTrailingWhite?displayProperty=nameWithType>, <xref:System.Globalization.NumberStyles.AllowLeadingSign?displayProperty=nameWithType>, <xref:System.Globalization.NumberStyles.AllowDecimalPoint?displayProperty=nameWithType>, e <xref:System.Globalization.NumberStyles.AllowExponent?displayProperty=nameWithType> stili.|  
|<xref:System.Globalization.NumberStyles.Currency?displayProperty=nameWithType>|Include tutti gli stili tranne <xref:System.Globalization.NumberStyles.AllowExponent?displayProperty=nameWithType> e <xref:System.Globalization.NumberStyles.AllowHexSpecifier?displayProperty=nameWithType>.|  
|<xref:System.Globalization.NumberStyles.Any?displayProperty=nameWithType>|Include tutti gli stili tranne <xref:System.Globalization.NumberStyles.AllowHexSpecifier?displayProperty=nameWithType>.|  
|<xref:System.Globalization.NumberStyles.HexNumber?displayProperty=nameWithType>|Include il <xref:System.Globalization.NumberStyles.AllowLeadingWhite?displayProperty=nameWithType>, <xref:System.Globalization.NumberStyles.AllowTrailingWhite?displayProperty=nameWithType>, e <xref:System.Globalization.NumberStyles.AllowHexSpecifier?displayProperty=nameWithType> stili.|  
  
## <a name="parsing-and-unicode-digits"></a>Analisi e cifre Unicode  
 Lo standard Unicode definisce gli elementi di codice per le cifre in diversi sistemi di scrittura. Ad esempio, gli elementi di codice compresi tra U+0030 e U+0039 rappresentano le cifre latine di base da 0 a 9, gli elementi di codice compresi tra U+09E6 e U+09EF rappresentano le cifre bengalesi da 0 a 9 e gli elementi di codice compresi tra U+FF10 e U+FF19 rappresentano le cifre Fullwidth da 0 a 9. Tuttavia, solo cifre numeriche riconosciute dai metodi di analisi sono le cifre latine di base da 0 a 9 con elementi di codice da U+0030 a U+0039. Se un metodo di analisi numerico viene passato una stringa che contiene tutte le altre cifre, il metodo genera un <xref:System.FormatException>.  
  
 L'esempio seguente usa il <xref:System.Int32.Parse%2A?displayProperty=nameWithType> metodo per analizzare le stringhe costituite da cifre in diversi sistemi di scrittura. Come illustrato nell'output dell'esempio, il tentativo di analizzare le cifre latine di base ha esito positivo, mentre il tentativo di analisi delle cifre Fullwidth, indoarabiche e bengalesi ha esito negativo.  
  
 [!code-csharp[Parsing.Numbers#3](../../../samples/snippets/csharp/VS_Snippets_CLR/parsing.numbers/cs/unicode1.cs#3)]
 [!code-vb[Parsing.Numbers#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/parsing.numbers/vb/unicode1.vb#3)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Globalization.NumberStyles>  
 [Analisi di stringhe](../../../docs/standard/base-types/parsing-strings.md)  
 [Formattazione di tipi](../../../docs/standard/base-types/formatting-types.md)

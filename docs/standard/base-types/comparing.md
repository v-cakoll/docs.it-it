---
title: Confronto di stringhe in .NET
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- value comparisons of strings
- LastIndexOf method
- CompareTo method
- IndexOf method
- Compare method
- strings [.NET Framework], comparing
- CompareOrdinal method
- EndsWith method
- Equals method
- StartsWith method
ms.assetid: 977dc094-fe19-4955-98ec-d2294d04a4ba
ms.openlocfilehash: e63b2a8ac44d6171f9c48990882780ea420f8c76
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "73101663"
---
# <a name="comparing-strings-in-net"></a>Confronto di stringhe in .NET
.NET offre diversi metodi per confrontare i valori delle stringhe. La tabella seguente elenca e descrive i metodi di confronto di valori.  
  
|Nome metodo|Uso|  
|-----------------|---------|  
|<xref:System.String.Compare%2A?displayProperty=nameWithType>|Confronta i valori di due stringhe. Restituisce un valore intero.|  
|<xref:System.String.CompareOrdinal%2A?displayProperty=nameWithType>|Confronta due stringhe senza tenere in considerazione le impostazioni cultura locali. Restituisce un valore intero.|  
|<xref:System.String.CompareTo%2A?displayProperty=nameWithType>|Confronta l'oggetto stringa corrente con un'altra stringa. Restituisce un valore intero.|  
|<xref:System.String.StartsWith%2A?displayProperty=nameWithType>|Determina se una stringa inizia con la stringa passata. Restituisce un valore booleano.|  
|<xref:System.String.EndsWith%2A?displayProperty=nameWithType>|Determina se una stringa finisce con la stringa passata. Restituisce un valore booleano.|  
|<xref:System.String.Equals%2A?displayProperty=nameWithType>|Determina se due stringhe sono uguali. Restituisce un valore booleano.|  
|<xref:System.String.IndexOf%2A?displayProperty=nameWithType>|Restituisce la posizione di indice di un carattere o una stringa, a partire dall'inizio della stringa esaminata. Restituisce un valore intero.|  
|<xref:System.String.LastIndexOf%2A?displayProperty=nameWithType>|Restituisce la posizione di indice di un carattere o una stringa, a partire dalla fine della stringa esaminata. Restituisce un valore intero.|  
  
## <a name="compare"></a>Confronto  
 Il metodo statico <xref:System.String.Compare%2A?displayProperty=nameWithType> consente di confrontare due stringhe. Questo metodo fa distinzione tra le impostazioni cultura. È possibile usare questa funzione per confrontare due stringhe o le sottostringhe di due stringhe. Sono inoltre disponibili overload che consentono o meno di fare distinzione tra maiuscole e minuscole e di tenere o meno in considerazione le differenze nelle impostazioni cultura. La tabella seguente illustra i tre valori interi che questo metodo può restituire.  
  
|Valore restituito|Condizione|  
|------------------|---------------|  
|Intero negativo|La prima stringa precede la seconda stringa nella sequenza di ordinamento.<br /><br /> -oppure-<br /><br /> La prima stringa è `null`.|  
|0|La prima stringa e la seconda stringa sono uguali.<br /><br /> -oppure-<br /><br /> Entrambe le stringhe sono `null`.|  
|Numero intero positivo<br /><br /> -oppure-<br /><br /> 1|La prima stringa segue la seconda stringa nella sequenza di ordinamento.<br /><br /> -oppure-<br /><br /> La seconda stringa è `null`.|  
  
> [!IMPORTANT]
> Il metodo <xref:System.String.Compare%2A?displayProperty=nameWithType> è destinato principalmente a essere usato quando si ordinano o si dispongono le stringhe. Non usare il metodo <xref:System.String.Compare%2A?displayProperty=nameWithType> per verificare l'uguaglianza (ovvero, per cercare in modo esplicito un valore restituito pari a 0 senza considerare se una stringa è minore o maggiore di un'altra). Per determinare se due stringhe sono uguali, usare invece il metodo <xref:System.String.Equals%28System.String%2CSystem.String%2CSystem.StringComparison%29?displayProperty=nameWithType> .  
  
 L'esempio seguente usa il metodo <xref:System.String.Compare%2A?displayProperty=nameWithType> per determinare i valori relativi di due stringhe.  
  
 [!code-cpp[Conceptual.String.BasicOps#6](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/compare.cpp#6)]
 [!code-csharp[Conceptual.String.BasicOps#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/compare.cs#6)]
 [!code-vb[Conceptual.String.BasicOps#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/compare.vb#6)]  
  
 L'esempio visualizza `-1` nella console.  
  
 L'esempio precedente fa distinzione tra le impostazioni cultura per impostazione predefinita. Per eseguire un confronto tra stringhe senza fare distinzione tra le impostazioni cultura, usare un overload del metodo <xref:System.String.Compare%2A?displayProperty=nameWithType>, che consente di specificare le impostazioni cultura da usare tramite un parametro *culture*. Per un esempio che illustra come usare il metodo <xref:System.String.Compare%2A?displayProperty=nameWithType> per eseguire un confronto senza distinzione tra le impostazioni cultura, vedere [Esecuzione di confronti di stringhe indipendenti dalle impostazioni cultura](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-comparisons.md).  
  
## <a name="compareordinal"></a>CompareOrdinal  
 Il metodo <xref:System.String.CompareOrdinal%2A?displayProperty=nameWithType> confronta due oggetti stringa senza considerare le impostazioni cultura locali. I valori restituiti da questo metodo sono identici a quelli restituiti dal metodo **Compare** nella tabella precedente.  
  
> [!IMPORTANT]
> Il metodo <xref:System.String.CompareOrdinal%2A?displayProperty=nameWithType> è destinato principalmente a essere usato quando si ordinano o si dispongono le stringhe. Non usare il metodo <xref:System.String.CompareOrdinal%2A?displayProperty=nameWithType> per verificare l'uguaglianza (ovvero, per cercare in modo esplicito un valore restituito pari a 0 senza considerare se una stringa è minore o maggiore di un'altra). Per determinare se due stringhe sono uguali, usare invece il metodo <xref:System.String.Equals%28System.String%2CSystem.String%2CSystem.StringComparison%29?displayProperty=nameWithType> .  
  
 L'esempio seguente usa il metodo **CompareOrdinal** per confrontare i valori di due stringhe.  
  
 [!code-cpp[Conceptual.String.BasicOps#7](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/compare.cpp#7)]
 [!code-csharp[Conceptual.String.BasicOps#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/compare.cs#7)]
 [!code-vb[Conceptual.String.BasicOps#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/compare.vb#7)]  
  
 L'esempio visualizza `-32` nella console.  
  
## <a name="compareto"></a>CompareTo  
 Il metodo <xref:System.String.CompareTo%2A?displayProperty=nameWithType> confronta la stringa incapsulata dall'oggetto stringa corrente con un altro oggetto o stringa. I valori restituiti da questo metodo sono identici a quelli restituiti dal metodo <xref:System.String.Compare%2A?displayProperty=nameWithType> nella tabella precedente.  
  
> [!IMPORTANT]
> Il metodo <xref:System.String.CompareTo%2A?displayProperty=nameWithType> è destinato principalmente a essere usato quando si ordinano o si dispongono le stringhe. Non usare il metodo <xref:System.String.CompareTo%2A?displayProperty=nameWithType> per verificare l'uguaglianza (ovvero, per cercare in modo esplicito un valore restituito pari a 0 senza considerare se una stringa è minore o maggiore di un'altra). Per determinare se due stringhe sono uguali, usare invece il metodo <xref:System.String.Equals%28System.String%2CSystem.String%2CSystem.StringComparison%29?displayProperty=nameWithType> .  
  
 L'esempio seguente usa il metodo <xref:System.String.CompareTo%2A?displayProperty=nameWithType> per confrontare l'oggetto `string1` con l'oggetto `string2`.  
  
 [!code-cpp[Conceptual.String.BasicOps#8](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/compare.cpp#8)]
 [!code-csharp[Conceptual.String.BasicOps#8](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/compare.cs#8)]
 [!code-vb[Conceptual.String.BasicOps#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/compare.vb#8)]  
  
 L'esempio visualizza `-1` nella console.  
  
 Tutti gli overload del metodo <xref:System.String.CompareTo%2A?displayProperty=nameWithType> eseguono per impostazione predefinita confronti che fanno distinzione tra le impostazioni cultura e tra maiuscole e minuscole. Non sono disponibili overload di questo metodo per eseguire un confronto senza distinzione tra le impostazioni cultura. Per maggiore chiarezza del codice, è consigliabile usare invece il metodo **String.Compare**, specificando <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=nameWithType> per operazioni con distinzione tra le impostazioni cultura o <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType> per operazioni senza distinzione tra le impostazioni cultura. Per un esempio che illustra come usare il metodo **String.Compare** per eseguire confronti con e senza distinzione tra le impostazioni cultura, vedere [Esecuzione di confronti di stringhe indipendenti dalle impostazioni cultura](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-comparisons.md).  
  
## <a name="equals"></a>Uguale a  
 Il metodo **Equals** consente di determinare in modo semplice se due stringhe sono uguali. Questo metodo, che fa distinzione tra maiuscole e minuscole, restituisce un valore booleano **true** o **false** . Può essere usato da una classe esistente, come illustrato nell'esempio seguente. L'esempio seguente usa il metodo **Equals** per determinare se un oggetto stringa contiene la frase "Hello World".  
  
 [!code-cpp[Conceptual.String.BasicOps#9](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/compare.cpp#9)]
 [!code-csharp[Conceptual.String.BasicOps#9](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/compare.cs#9)]
 [!code-vb[Conceptual.String.BasicOps#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/compare.vb#9)]  
  
 L'esempio visualizza `True` nella console.  
  
 Questo metodo può anche essere usato come metodo statico. L'esempio seguente confronta due oggetti stringa tramite un metodo statico.  
  
 [!code-cpp[Conceptual.String.BasicOps#10](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/compare.cpp#10)]
 [!code-csharp[Conceptual.String.BasicOps#10](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/compare.cs#10)]
 [!code-vb[Conceptual.String.BasicOps#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/compare.vb#10)]  
  
 L'esempio visualizza `True` nella console.  
  
## <a name="startswith-and-endswith"></a>StartsWith ed EndsWith  
 È possibile usare il metodo **StartsWith** per determinare se un oggetto stringa inizia con gli stessi caratteri inclusi in un'altra stringa. Questo metodo, che fa distinzione tra maiuscole e minuscole, restituisce **true** se l'oggetto stringa corrente inizia con la stringa passata e **false** in caso contrario. L'esempio seguente usa questo metodo per determinare se un oggetto stringa inizia con "Hello".  
  
 [!code-cpp[Conceptual.String.BasicOps#11](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/compare.cpp#11)]
 [!code-csharp[Conceptual.String.BasicOps#11](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/compare.cs#11)]
 [!code-vb[Conceptual.String.BasicOps#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/compare.vb#11)]  
  
 L'esempio visualizza `True` nella console.  
  
 Il metodo **EndsWith** confronta una stringa passata con i caratteri presenti alla fine dell'oggetto stringa corrente. Anch'esso restituisce un valore booleano. L'esempio seguente verifica la fine di una stringa usando il metodo **EndsWith** .  
  
 [!code-cpp[Conceptual.String.BasicOps#12](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/compare.cpp#12)]
 [!code-csharp[Conceptual.String.BasicOps#12](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/compare.cs#12)]
 [!code-vb[Conceptual.String.BasicOps#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/compare.vb#12)]  
  
 L'esempio visualizza `False` nella console.  
  
## <a name="indexof-and-lastindexof"></a>IndexOf e LastIndexOf  
 È possibile usare il metodo **IndexOf** per determinare la posizione della prima occorrenza di un carattere specifico all'interno di una stringa. Questo metodo, che fa distinzione tra maiuscole e minuscole, inizia il conteggio dall'inizio di una stringa e restituisce la posizione di un carattere passato usando un indice in base zero. Se il carattere non viene trovato, viene restituito un valore -1.  
  
 L'esempio seguente usa il metodo **IndexOf** per cercare la prima occorrenza del carattere '`l`' in una stringa.  
  
 [!code-cpp[Conceptual.String.BasicOps#13](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/compare.cpp#13)]
 [!code-csharp[Conceptual.String.BasicOps#13](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/compare.cs#13)]
 [!code-vb[Conceptual.String.BasicOps#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/compare.vb#13)]  
  
 L'esempio visualizza `2` nella console.  
  
 Il metodo **LastIndexOf** è simile al metodo **IndexOf** , con la differenza che restituisce la posizione dell'ultima occorrenza di un carattere specifico all'interno di una stringa. Anch'esso fa distinzione tra maiuscole e minuscole e usa un indice in base zero.  
  
 L'esempio seguente usa il metodo **LastIndexOf** per cercare l'ultima occorrenza del carattere '`l`' in una stringa.  
  
 [!code-cpp[Conceptual.String.BasicOps#14](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/compare.cpp#14)]
 [!code-csharp[Conceptual.String.BasicOps#14](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/compare.cs#14)]
 [!code-vb[Conceptual.String.BasicOps#14](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/compare.vb#14)]  
  
 L'esempio visualizza `9` nella console.  
  
 Entrambi i metodi sono utili quando vengono usati in combinazione con il metodo **String.Remove** . È possibile usare il metodo **IndexOf** o **LastIndexOf** per recuperare la posizione di un carattere e quindi specificare tale posizione nel metodo **Remove** per rimuovere un carattere o una parola che inizia con tale carattere.  
  
## <a name="see-also"></a>Vedere anche

- [Operazioni di base sulle stringheBasic String Operations](../../../docs/standard/base-types/basic-string-operations.md)
- [Esecuzione di operazioni sulle stringhe indipendenti dalle impostazioni cultura](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations.md)
- [Sorting Weight Tables (for .NET on Windows)](https://www.microsoft.com/download/details.aspx?id=10921) (Tabelle di ordinamento spessore - Per .NET in Windows)
- [Default Unicode Collation Element Table (for .NET Core on Linux and macOS)](https://www.unicode.org/Public/UCA/latest/allkeys.txt) (Tabella degli elementi delle regole di confronto Unicode predefinite - Per .NET Core in Linux e MacOS)

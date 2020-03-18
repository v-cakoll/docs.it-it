---
title: Analisi di altre stringhe in .NET
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Char data type, parsing strings
- enumerations [.NET Framework], parsing strings
- base types, parsing strings
- parsing strings, other strings
- Boolean data type, parsing strings
ms.assetid: d139bc00-3c4e-4d78-ac9a-5c951b258d28
ms.openlocfilehash: 08e891501bbefcf8b32eff10dd7294af9d81adac
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "73127577"
---
# <a name="parsing-other-strings-in-net"></a>Analisi di altre stringhe in .NET
Oltre alle stringhe numeriche e<xref:System.DateTime> è possibile analizzare le stringhe che rappresentano i tipi <xref:System.Char>, <xref:System.Boolean> ed <xref:System.Enum> in tipi di dati.  
  
## <a name="char"></a>Char  
 Il metodo di analisi statico associato al tipo di dati **Char** è utile per la conversione di una stringa contenente un solo carattere nel valore Unicode corrispondente. Nell'esempio seguente viene analizzata una stringa in un carattere Unicode.  
  
 [!code-cpp[Conceptual.String.Parse#2](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.parse/cpp/parse.cpp#2)]
 [!code-csharp[Conceptual.String.Parse#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.parse/cs/parse.cs#2)]
 [!code-vb[Conceptual.String.Parse#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.parse/vb/parse.vb#2)]  
  
## <a name="boolean"></a>Boolean  
 Il tipo di dati **Boolean** contiene un metodo **Parse** che può essere usato per convertire una stringa che rappresenta un valore booleano in un vero e proprio tipo **Boolean**. Questo metodo non fa distinzione tra maiuscole e minuscole e consente di analizzare correttamente una stringa contenente "True" o "False". Il metodo **Parse** associato al tipo **Boolean** consente anche di analizzare stringhe precedute e seguite da spazi vuoti. Se viene passata qualsiasi altra stringa, viene generata un'eccezione <xref:System.FormatException>.  
  
 Nell'esempio di codice seguente viene usato il metodo **Parse** per convertire una stringa in un valore di tipo Boolean.  
  
 [!code-cpp[Conceptual.String.Parse#3](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.parse/cpp/parse.cpp#3)]
 [!code-csharp[Conceptual.String.Parse#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.parse/cs/parse.cs#3)]
 [!code-vb[Conceptual.String.Parse#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.parse/vb/parse.vb#3)]  
  
## <a name="enumeration"></a>Enumerazione  
 È possibile usare il metodo statico **Parse** per inizializzare un tipo di enumerazione per il valore di una stringa. Questo metodo accetta il tipo di enumerazione che si sta analizzando, la stringa da analizzare e un flag Boolean facoltativo che indica se l'analisi fa distinzione tra maiuscole e minuscole. La stringa da analizzare può contenere diversi valori separati da virgole, che possono essere preceduti o seguiti da uno o più spazi vuoti. Quando la stringa contiene più valori, il valore dell'oggetto restituito è il valore di tutti i valori specificati combinati con un'operazione OR bit per bit.  
  
 Nell'esempio seguente viene usato il metodo **Parse** per convertire una rappresentazione di stringa in un valore di enumerazione. L'enumerazione <xref:System.DayOfWeek> viene inizializzata su **Thursday** da una stringa.  
  
 [!code-cpp[Conceptual.String.Parse#4](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.parse/cpp/parse.cpp#4)]
 [!code-csharp[Conceptual.String.Parse#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.parse/cs/parse.cs#4)]
 [!code-vb[Conceptual.String.Parse#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.parse/vb/parse.vb#4)]  
  
## <a name="see-also"></a>Vedere anche

- [Parsing Strings](../../../docs/standard/base-types/parsing-strings.md)
- [Formattazione di tipi](../../../docs/standard/base-types/formatting-types.md)
- [Conversione di tipi in .NET](../../../docs/standard/base-types/type-conversion.md)

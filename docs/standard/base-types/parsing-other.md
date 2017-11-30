---
title: Analisi di altre stringhe in .NET
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
- cpp
helpviewer_keywords:
- Char data type, parsing strings
- enumerations [.NET Framework], parsing strings
- base types, parsing strings
- parsing strings, other strings
- Boolean data type, parsing strings
ms.assetid: d139bc00-3c4e-4d78-ac9a-5c951b258d28
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: edd48993f50ec8b91ba7941a682d7de9f22aa12e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="parsing-other-strings-in-net"></a>Analisi di altre stringhe in .NET
Oltre a numerico e <xref:System.DateTime> stringhe, è possibile analizzare le stringhe che rappresentano i tipi di <xref:System.Char>, <xref:System.Boolean>, e <xref:System.Enum> in tipi di dati.  
  
## <a name="char"></a>Char  
 Il metodo di analisi statico associato al tipo di dati **Char** è utile per la conversione di una stringa contenente un solo carattere nel valore Unicode corrispondente. Nell'esempio seguente viene analizzata una stringa in un carattere Unicode.  
  
 [!code-cpp[Conceptual.String.Parse#2](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.parse/cpp/parse.cpp#2)]
 [!code-csharp[Conceptual.String.Parse#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.parse/cs/parse.cs#2)]
 [!code-vb[Conceptual.String.Parse#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.parse/vb/parse.vb#2)]  
  
## <a name="boolean"></a>Booleano  
 Il **booleano** tipo di dati contiene un **analizzare** metodo che è possibile utilizzare per convertire una stringa che rappresenta un valore booleano in una vera e propria **booleano** tipo. Questo metodo non fa distinzione tra maiuscole e minuscole e consente di analizzare correttamente una stringa contenente "True" o "False". Il **analizzare** metodo associato il **booleano** tipo consente inoltre di analizzare le stringhe sono racchiusi tra spazi vuoti. Se viene passata qualsiasi altra stringa, un <xref:System.FormatException> viene generata un'eccezione.  
  
 Nell'esempio di codice viene illustrato come utilizzare il **analizzare** metodo per convertire una stringa in un valore booleano.  
  
 [!code-cpp[Conceptual.String.Parse#3](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.parse/cpp/parse.cpp#3)]
 [!code-csharp[Conceptual.String.Parse#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.parse/cs/parse.cs#3)]
 [!code-vb[Conceptual.String.Parse#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.parse/vb/parse.vb#3)]  
  
## <a name="enumeration"></a>Enumerazione  
 È possibile usare il metodo statico **Parse** per inizializzare un tipo di enumerazione per il valore di una stringa. Questo metodo accetta il tipo di enumerazione che si sta analizzando la stringa da analizzare e un flag booleano facoltativo che indica se è o meno l'analisi tra maiuscole e minuscole. La stringa da analizzare può contenere diversi valori separati da virgole, che possono essere preceduti o seguiti da uno o più spazi vuoti. Quando la stringa contiene più valori, il valore dell'oggetto restituito è il valore di tutti i valori specificati combinati con un'operazione OR bit per bit.  
  
 L'esempio seguente usa il **analizzare** metodo per convertire una rappresentazione di stringa in un valore di enumerazione. Il <xref:System.DayOfWeek> enumerazione viene inizializzata su **giovedì** da una stringa.  
  
 [!code-cpp[Conceptual.String.Parse#4](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.parse/cpp/parse.cpp#4)]
 [!code-csharp[Conceptual.String.Parse#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.parse/cs/parse.cs#4)]
 [!code-vb[Conceptual.String.Parse#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.parse/vb/parse.vb#4)]  
  
## <a name="see-also"></a>Vedere anche  
 [Analisi di stringhe](../../../docs/standard/base-types/parsing-strings.md)  
 [Formattazione di tipi](../../../docs/standard/base-types/formatting-types.md)  
 [Conversione di tipi in .NET](../../../docs/standard/base-types/type-conversion.md)

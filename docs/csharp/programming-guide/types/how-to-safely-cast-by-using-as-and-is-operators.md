---
title: 'Procedura: eseguire il cast sicuro tramite gli operatori as e is (Guida per programmatori C#)'
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- cast operators [C#], as and is operators
- as operator [C#]
- is operator [C#]
ms.assetid: c1176cea-1426-4a44-8570-3eadafa58863
caps.latest.revision: "10"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 733b67408997feb0e518db327e3eedd42f286a99
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-safely-cast-by-using-as-and-is-operators-c-programming-guide"></a>Procedura: eseguire il cast sicuro tramite gli operatori as e is (Guida per programmatori C#)
Poiché gli oggetti sono polimorfici, è possibile che una variabile di un tipo di classe di base contenga un tipo derivato. Per accedere al metodo del tipo derivato, è necessario eseguire nuovamente il cast del valore al tipo derivato. Tentare un cast semplice in questi casi comporta tuttavia il rischio di generare un'eccezione <xref:System.InvalidCastException>. Per questo motivo C# fornisce gli operatori [is](../../../csharp/language-reference/keywords/is.md) e [as](../../../csharp/language-reference/keywords/as.md). È possibile usare questi operatori per verificare se un cast riuscirà senza provocare la generazione di un'eccezione. In generale, l'operatore `as` è più efficiente perché, se è possibile effettuare il cast, ne restituisce il valore. L'operatore `is` restituisce solo un valore booleano. Si può quindi usare quando si vuole solo determinare il tipo di un oggetto ma non si deve realmente eseguirne il cast.  
  
## <a name="example"></a>Esempio  
 Gli esempi seguenti mostrano come usare gli operatori `is` e `as` per eseguire il cast da un tipo riferimento a un altro senza il rischio di generare un'eccezione. L'esempio mostra anche come usare l'operatore `as` con i tipi valore nullable.  
  
 [!code-csharp[csProgGuideTypes#40](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-safely-cast-by-using-as-and-is-operators_1.cs)]  
  
## <a name="see-also"></a>Vedere anche  
 [Tipi](../../../csharp/programming-guide/types/index.md)  
 [Cast e conversioni di tipi](../../../csharp/programming-guide/types/casting-and-type-conversions.md)  
 [Tipi nullable](../../../csharp/programming-guide/nullable-types/index.md)

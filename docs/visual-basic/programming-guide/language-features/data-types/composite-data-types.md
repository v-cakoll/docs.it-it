---
title: Tipi di dati compositi (Visual Basic)
ms.date: 04/25/2017
helpviewer_keywords:
- classes [Visual Basic], composite data types
- composite types [Visual Basic]
- composite data types [Visual Basic]
- data types [Visual Basic], composite
- arrays [Visual Basic], composite data types
- structures [Visual Basic], composite data types
- classes [Visual Basic], composite types
- types [Visual Basic], composite
ms.assetid: 62970f2e-52c0-4369-8963-613820f1f434
ms.openlocfilehash: 73867a5881db7c94d258e8716c4ff4c5b1119e71
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="composite-data-types-visual-basic"></a>Tipi di dati compositi (Visual Basic)
Oltre a disponibili in Visual Basic di tipi di dati elementare è anche possibile assemblare gli elementi di tipi diversi per creare *tipi di dati composti* come strutture, matrici e le classi. È possibile compilare i tipi di dati composti da tipi di base e da altri tipi compositi. Ad esempio, è possibile definire una matrice di elementi di struttura o una struttura con i membri della matrice.  
  
## <a name="data-types"></a>Tipi di dati  
 Un tipo composito è diverso dal tipo di dati di uno qualsiasi dei relativi componenti. Ad esempio, una matrice di `Integer` elementi non è il `Integer` tipo di dati.  
  
 In genere i dati di tipo matrice sono rappresentato utilizzando il tipo di elemento, tra parentesi e virgole in base alle esigenze. Ad esempio, una matrice unidimensionale di `String` elementi è rappresentato come `String()`e una matrice bidimensionale di `Boolean` elementi è rappresentato come `Boolean(,)`.  
  
## <a name="structure-types"></a>Tipi di struttura  
 Non vi è alcun tipo di dati singolo che comprende tutte le strutture. Ogni definizione di una struttura rappresenta invece un tipo di dati univoco, anche se due strutture definiscono elementi identici nello stesso ordine. Tuttavia, se si creano due o più istanze della stessa struttura, Visual Basic vengono considerate dello stesso tipo di dati.  
  
## <a name="tuples"></a>Tuple

Una tupla è una struttura semplice che contiene due o più campi i cui tipi sono predefiniti. Le tuple sono supportate a partire da Visual Basic 2017. Le tuple sono utilizzate principalmente per restituire più valori da una singola chiamata al metodo senza dover passare gli argomenti per riferimento o creandone un pacchetto campi restituiti in una classe più grave o struttura. Vedere il [Tuple](tuples.md) per ulteriori informazioni sulle Tuple.

## <a name="array-types"></a>Tipi di matrice  
 Non vi è alcun tipo di dati singolo che comprende tutte le matrici. Il tipo di dati di una particolare istanza di una matrice viene determinato nel modo seguente:  
  
-   Il fatto di essere una matrice  
  
-   La classificazione (numero di dimensioni) della matrice  
  
-   Il tipo di elemento della matrice  
  
 In particolare, la lunghezza di una determinata dimensione non fa parte dell'istanza tipo di dati. Questa condizione è illustrata nell'esempio seguente.  
  
```  
Dim arrayA( ) As Byte = New Byte(12) {}  
Dim arrayB( ) As Byte = New Byte(100) {}  
Dim arrayC( ) As Short = New Short(100) {}  
Dim arrayD( , ) As Short  
Dim arrayE( , ) As Short = New Short(4, 10) {}  
```  
  
 Nell'esempio precedente, le variabili di matrice `arrayA` e `arrayB` vengono considerati dello stesso tipo di dati, ovvero `Byte()` , anche se vengono inizializzate su lunghezze diverse. Le variabili `arrayB` e `arrayC` non sono dello stesso tipo perché i relativi tipi di elemento sono diversi. Le variabili `arrayC` e `arrayD` non sono dello stesso tipo perché i relativi indici sono differenti. Le variabili `arrayD` e `arrayE` hanno lo stesso tipo, ovvero `Short(,)` , perché le classificazioni e i tipi di elemento sono gli stessi, anche se `arrayD` non ancora inizializzato.  
  
 Per ulteriori informazioni sulle matrici, vedere [matrici](../../../../visual-basic/programming-guide/language-features/arrays/index.md).  
  
## <a name="class-types"></a>Tipi di classe  
 Non vi è alcun tipo di dati singolo che comprende tutte le classi. Anche se una classe può ereditare da un'altra classe, ognuno è un tipo di dati separato. Più istanze della stessa classe sono dello stesso tipo di dati. Se si assegna una variabile di istanza di classe a un altro, non solo se hanno gli stessi dati di tipo, entrambe puntano alla stessa istanza di classe in memoria.  
  
 Per ulteriori informazioni sulle classi, vedere [oggetti e classi](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Tipi di dati](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 [Tipi di dati elementari](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)  
 [Tipi generici in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)  
 [Tipi valore e tipi riferimento](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)  
 [Conversioni di tipi in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)  
 [Strutture](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [Risoluzione dei problemi relativi ai tipi di dati](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [Procedura: Inserire più valori in una variabile](../../../../visual-basic/programming-guide/language-features/data-types/how-to-hold-more-than-one-value-in-a-variable.md)

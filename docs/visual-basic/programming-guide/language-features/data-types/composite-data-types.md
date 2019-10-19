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
ms.openlocfilehash: 768559c7a6caf064f7529786675e51ce19667d6b
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2019
ms.locfileid: "72581719"
---
# <a name="composite-data-types-visual-basic"></a>Tipi di dati compositi (Visual Basic)
Oltre ai tipi di dati elementari Visual Basic fornisce, è anche possibile assemblare elementi di tipi diversi per creare *tipi di dati compositi* , ad esempio strutture, matrici e classi. È possibile compilare tipi di dati compositi da tipi elementari e da altri tipi compositi. Ad esempio, è possibile definire una matrice di elementi della struttura o una struttura con membri di matrice.  
  
## <a name="data-types"></a>Tipi di dati  
 Un tipo composito è diverso dal tipo di dati di uno dei relativi componenti. Una matrice di elementi `Integer`, ad esempio, non è del tipo di dati `Integer`.  
  
 Un tipo di dati di matrice viene in genere rappresentato utilizzando il tipo di elemento, le parentesi e le virgole secondo necessità. Ad esempio, una matrice unidimensionale di elementi `String` viene rappresentata come `String()` e una matrice bidimensionale di elementi `Boolean` viene rappresentata come `Boolean(,)`.  
  
## <a name="structure-types"></a>Tipi di struttura  
 Non esiste un singolo tipo di dati costituito da tutte le strutture. Al contrario, ogni definizione di una struttura rappresenta un tipo di dati univoco, anche se due strutture definiscono elementi identici nello stesso ordine. Tuttavia, se si creano due o più istanze della stessa struttura, Visual Basic considera che siano dello stesso tipo di dati.  
  
## <a name="tuples"></a>Tuple

Una tupla è una struttura leggera che contiene due o più campi i cui tipi sono predefiniti. Le tuple sono supportate a partire da Visual Basic 2017. Le tuple vengono in genere utilizzate per restituire più valori da una singola chiamata al metodo senza dover passare argomenti per riferimento o per comprimere i campi restituiti in una classe o una struttura più pesante. Per ulteriori informazioni sulle tuple, vedere l'argomento [Tuple](tuples.md) .

## <a name="array-types"></a>Tipi di matrice  
 Non esiste un singolo tipo di dati costituito da tutte le matrici. Il tipo di dati di una determinata istanza di una matrice è determinato dai seguenti elementi:  
  
- Il fatto di essere una matrice  
  
- Rango (numero di dimensioni) della matrice  
  
- Tipo di elemento della matrice.  
  
 In particolare, la lunghezza di una determinata dimensione non fa parte del tipo di dati dell'istanza. Questa condizione è illustrata nell'esempio seguente.  
  
```vb  
Dim arrayA( ) As Byte = New Byte(12) {}  
Dim arrayB( ) As Byte = New Byte(100) {}  
Dim arrayC( ) As Short = New Short(100) {}  
Dim arrayD( , ) As Short  
Dim arrayE( , ) As Short = New Short(4, 10) {}  
```  
  
 Nell'esempio precedente, le variabili di matrice `arrayA` e `arrayB` sono considerate dello stesso tipo di dati, `Byte()`, anche se vengono inizializzate su lunghezze diverse. Le variabili `arrayB` e `arrayC` non sono dello stesso tipo perché i tipi di elemento sono diversi. Le variabili `arrayC` e `arrayD` non sono dello stesso tipo perché le relative dimensioni sono diverse. Le variabili `arrayD` e `arrayE` hanno lo stesso tipo, `Short(,)`, perché i relativi tipi di rango e di elemento sono gli stessi, anche se `arrayD` non è ancora inizializzato.  
  
 Per ulteriori informazioni sulle matrici, vedere [matrici](../../../../visual-basic/programming-guide/language-features/arrays/index.md).  
  
## <a name="class-types"></a>Tipi di classe  
 Non esiste un singolo tipo di dati costituito da tutte le classi. Sebbene una classe possa ereditare da un'altra classe, ognuno è un tipo di dati separato. Più istanze della stessa classe sono dello stesso tipo di dati. Se si assegna una variabile di istanza di classe a un'altra, non solo i tipi di dati hanno lo stesso tipo di dati, fanno riferimento alla stessa istanza della classe in memoria.  
  
 Per ulteriori informazioni sulle classi, vedere [oggetti e classi](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md).  
  
## <a name="see-also"></a>Vedere anche

- [Tipi di dati](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [Tipi di dati elementari](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)
- [Generic Types in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [Tipi valore e tipi di riferimento](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
- [Conversioni di tipi in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [Strutture](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [Risoluzione dei problemi relativi ai tipi di dati](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [Procedura: Inserire più valori in una variabile](../../../../visual-basic/programming-guide/language-features/data-types/how-to-hold-more-than-one-value-in-a-variable.md)

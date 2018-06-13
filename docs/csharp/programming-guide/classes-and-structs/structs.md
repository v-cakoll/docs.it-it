---
title: Struct (Guida per programmatori C#)
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, structs
- structs [C#]
ms.assetid: b7cf4ff2-0eb7-4e5c-93d5-b2196b4f5d89
ms.openlocfilehash: ffb5b8da6c72056620cf890f38af4e7a8116ab3e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33322988"
---
# <a name="structs-c-programming-guide"></a>Struct (Guida per programmatori C#)
Per la definizione degli struct viene usata la parola chiave [struct](../../../csharp/language-reference/keywords/struct.md), ad esempio:  
  
 [!code-csharp[csProgGuideObjects#39](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/structs_1.cs)]  
  
 Gli struct condividono la maggior parte della sintassi delle classi, anche sono più limitati rispetto alle classi:  
  
-   All'interno di una dichiarazione di struct, è possibile inizializzare i campi solo se sono stati dichiarati come const o static.  
  
-   Uno struct non può dichiarare un finalizzatore o un costruttore, ovvero un costruttore senza parametri, predefinito.  
  
-   Gli struct vengono copiati su assegnazione. Quando uno struct viene assegnato a una nuova variabile, tutti i dati vengono copiati e qualsiasi modifica alla nuova copia non modifica i dati nella copia originale. È importante ricordare questo aspetto quando si lavora con raccolte di tipi valore come Dictionary\<string, myStruct>.  
  
-   Gli struct sono tipi valore e le classi sono tipi di riferimento.  
  
-   A differenza delle classi, è possibile creare istanze di struct senza usare un operatore `new`.  
  
-   Gli struct possono dichiarare costruttori con parametri.  
  
-   Uno struct non può ereditare da un altro struct o da una classe e non può essere la base di una classe. Tutti gli struct ereditano direttamente da `System.ValueType`, che eredita da `System.Object`.  
  
-   Uno struct può implementare le interfacce.  
  
-   Uno struct può essere usato come tipo nullable e può ricevere l'assegnazione di un valore Null.  
  
## <a name="related-sections"></a>Sezioni correlate  
 Per ulteriori informazioni:  
  
-   [Uso di struct](../../../csharp/programming-guide/classes-and-structs/using-structs.md)  
  
-   [Costruttori](../../../csharp/programming-guide/classes-and-structs/constructors.md)  
  
-   [Tipi nullable](../../../csharp/programming-guide/nullable-types/index.md)  
  
-   [Procedura: Differenza tra il passaggio di uno struct e il passaggio del riferimento a una classe a un metodo](../../../csharp/programming-guide/classes-and-structs/how-to-know-the-difference-passing-a-struct-and-passing-a-class-to-a-method.md)  
  
-   [Procedura: Implementare conversioni tra struct definite dall'utente](../../../csharp/programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)  
  
## <a name="see-also"></a>Vedere anche  
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
 [Classi e struct](../../../csharp/programming-guide/classes-and-structs/index.md)  
 [Classi](../../../csharp/programming-guide/classes-and-structs/classes.md)

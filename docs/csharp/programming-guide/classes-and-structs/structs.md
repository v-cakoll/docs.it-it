---
title: Struct - Guida per programmatori C#
ms.date: 08/21/2018
helpviewer_keywords:
- C# language, structs
- structs [C#]
ms.assetid: b7cf4ff2-0eb7-4e5c-93d5-b2196b4f5d89
ms.openlocfilehash: 5150ff2d6edde0ac91bc6548fd499b76af614007
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75705418"
---
# <a name="structs-c-programming-guide"></a>Struct (Guida per programmatori C#)

Per la definizione degli struct viene usata la parola chiave [struct](../../language-reference/keywords/struct.md), ad esempio:  
  
 [!code-csharp[csProgGuideObjects#39](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#39)]  
  
Gli struct condividono la maggior parte della sintassi come classi. Il nome della struct deve essere un [nome di identificatore](../inside-a-program/identifier-names.md) C# valido. Gli struct sono più limitati rispetto alle classi nei modi seguenti:  
  
- All'interno di una dichiarazione di struct, è possibile inizializzare i campi solo se sono stati dichiarati come const o static.  
- Uno struct non può dichiarare un costruttore senza parametri o un finalizzatore.  
- Gli struct vengono copiati su assegnazione. Quando uno struct viene assegnato a una nuova variabile, tutti i dati vengono copiati e qualsiasi modifica alla nuova copia non modifica i dati nella copia originale. È importante ricordare questo aspetto quando si usano raccolte di tipi valore come `Dictionary<string, myStruct>`.  
- Gli struct sono tipi valore che, a differenza delle classi, sono tipi riferimento.  
- A differenza delle classi, è possibile creare istanze di struct senza usare un operatore `new`.  
- Gli struct possono dichiarare costruttori con parametri.
- Uno struct non può ereditare da un altro struct o da una classe e non può essere la base di una classe. Tutti gli struct ereditano direttamente da <xref:System.ValueType>, che eredita da <xref:System.Object>.  
- Uno struct può implementare le interfacce.
- Uno struct non può essere `null`e non è possibile assegnare una variabile struct `null` a meno che la variabile non sia dichiarata come tipo di valore Nullable.
  
## <a name="see-also"></a>Vedere anche

- [Guida per programmatori C#](../index.md)
- [Classi e struct](index.md)
- [Classi](classes.md)
- [Tipi valore nullable](../../language-reference/builtin-types/nullable-value-types.md)
- [Nomi di identificatore](../inside-a-program/identifier-names.md)
- [Uso di struct](using-structs.md)
- [Come stabilire la differenza tra il passaggio di uno struct e il passaggio di un riferimento a una classe a un metodo](how-to-know-the-difference-passing-a-struct-and-passing-a-class-to-a-method.md)

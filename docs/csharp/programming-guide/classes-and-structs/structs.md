---
title: Struct - Guida per programmatori C#
ms.custom: seodec18
ms.date: 08/21/2018
helpviewer_keywords:
- C# language, structs
- structs [C#]
ms.assetid: b7cf4ff2-0eb7-4e5c-93d5-b2196b4f5d89
ms.openlocfilehash: 3f19d0485939e1923c479c1c9fdeb06572a11e14
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/11/2018
ms.locfileid: "53240385"
---
# <a name="structs-c-programming-guide"></a>Struct (Guida per programmatori C#)

Per la definizione degli struct viene usata la parola chiave [struct](../../language-reference/keywords/struct.md), ad esempio:  
  
[!code-csharp[csProgGuideObjects#39](./codesnippet/CSharp/structs_1.cs)]  
  
Gli struct condividono la maggior parte della sintassi come classi. Il nome della struct deve essere un [nome di identificatore](../inside-a-program/identifier-names.md) C# valido. Gli struct sono più limitati rispetto alle classi nei modi seguenti:  
  
- All'interno di una dichiarazione di struct, è possibile inizializzare i campi solo se sono stati dichiarati come const o static.  
- Uno struct non può dichiarare un finalizzatore o un costruttore, ovvero un costruttore senza parametri, predefinito.  
- Gli struct vengono copiati su assegnazione. Quando uno struct viene assegnato a una nuova variabile, tutti i dati vengono copiati e qualsiasi modifica alla nuova copia non modifica i dati nella copia originale. È importante ricordare questo aspetto quando si usano raccolte di tipi valore come `Dictionary<string, myStruct>`.  
- Gli struct sono tipi valore che, a differenza delle classi, sono tipi riferimento.  
- A differenza delle classi, è possibile creare istanze di struct senza usare un operatore `new`.  
- Gli struct possono dichiarare costruttori con parametri. 
- Uno struct non può ereditare da un altro struct o da una classe e non può essere la base di una classe. Tutti gli struct ereditano direttamente da <xref:System.ValueType>, che eredita da <xref:System.Object>.  
- Uno struct può implementare le interfacce.  
- Uno struct può essere usato come tipo nullable e può ricevere l'assegnazione di un valore Null.  
  
## <a name="related-sections"></a>Sezioni correlate  

Per ulteriori informazioni:  
  
- [Uso di struct](using-structs.md)
- [Costruttori](constructors.md)
- [Tipi nullable](../nullable-types/index.md)
- [Procedura: Differenza tra il passaggio di uno struct e il passaggio del riferimento a una classe a un metodo](how-to-know-the-difference-passing-a-struct-and-passing-a-class-to-a-method.md)
- [Procedura: Implementare conversioni tra struct definite dall'utente](../statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)

## <a name="see-also"></a>Vedere anche

- [Guida per programmatori C#](../index.md)
- [Classi e struct](index.md)
- [Classi](classes.md)
- [Nomi di identificatore](../inside-a-program/identifier-names.md)

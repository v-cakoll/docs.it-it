---
title: Struct - Guida per programmatori C#
ms.custom: seodec18
ms.date: 08/21/2018
helpviewer_keywords:
- C# language, structs
- structs [C#]
ms.assetid: b7cf4ff2-0eb7-4e5c-93d5-b2196b4f5d89
ms.openlocfilehash: 6c260408b7cdbb7bd55477a57ca879d89c3c0144
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "56977032"
---
# <a name="structs-c-programming-guide"></a>Struct (Guida per programmatori C#)

Per la definizione degli struct viene usata la parola chiave [struct](../../language-reference/keywords/struct.md), ad esempio:  
  
 [!code-csharp[csProgGuideObjects#39](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#39)]  
  
Gli struct condividono la maggior parte della sintassi come classi. Il nome della struct deve essere un [nome di identificatore](../inside-a-program/identifier-names.md) C# valido. Gli struct sono più limitati rispetto alle classi nei modi seguenti:  
  
- All'interno di una dichiarazione di struct, è possibile inizializzare i campi solo se sono stati dichiarati come const o static.  
- Uno struct non può dichiarare un finalizzatore o un costruttore, ovvero un costruttore senza parametri, predefinito.  
- Gli struct vengono copiati su assegnazione. Quando uno struct viene assegnato a una nuova variabile, tutti i dati vengono copiati e qualsiasi modifica alla nuova copia non modifica i dati nella copia originale. È importante ricordare questo aspetto quando si usano raccolte di tipi valore come `Dictionary<string, myStruct>`.  
- Gli struct sono tipi valore che, a differenza delle classi, sono tipi riferimento.  
- A differenza delle classi, è possibile creare istanze di struct senza usare un operatore `new`.  
- Gli struct possono dichiarare costruttori con parametri. 
- Uno struct non può ereditare da un altro struct o da una classe e non può essere la base di una classe. Tutti gli struct ereditano direttamente da <xref:System.ValueType>, che eredita da <xref:System.Object>.  
- Uno struct può implementare le interfacce. 
- Uno struct non può essere `null` e non è possibile assegnare `null` a una variabile struct, a meno che la variabile non sia dichiarata come tipo nullable.
  
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

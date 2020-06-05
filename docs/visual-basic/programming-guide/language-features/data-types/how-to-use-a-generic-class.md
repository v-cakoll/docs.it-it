---
title: 'Procedura: Usare una classe generica'
ms.date: 07/20/2015
helpviewer_keywords:
- type parameters [Visual Basic], defining
- data type arguments [Visual Basic], defining
- arguments [Visual Basic], data types
- Of keyword [Visual Basic], using
- generic parameters
- data type parameters
- generics [Visual Basic], about generics
- data types [Visual Basic], as parameters
- data types [Visual Basic], as arguments
- parameters [Visual Basic], type
- types [Visual Basic], generic
- parameters [Visual Basic], generic
- generics [Visual Basic], creating generic types
- data type arguments
- parameters [Visual Basic], data type
- data type parameters [Visual Basic], defining
- type arguments [Visual Basic], defining
- arguments [Visual Basic], type
ms.assetid: 242dd2a6-86c4-4ce7-83f2-f2661803f752
ms.openlocfilehash: 01f1f7ef5963feeb3fe2b5390244e4e516773bad
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84393844"
---
# <a name="how-to-use-a-generic-class-visual-basic"></a>Procedura: utilizzare una classe generica (Visual Basic)
Una classe che accetta *parametri di tipo* è chiamato *classe generica*. Se si usa una classe generica, è possibile generare una *classe costruita* da essa fornendo un *argomento di tipo* per ciascuno di questi parametri. È possibile quindi dichiarare una variabile del tipo di classe costruita, creare un'istanza della classe costruita e assegnarla alla variabile.  
  
 Oltre alle classi, è possibile definire e usare anche strutture, interfacce, routine e delegati generici.  
  
 La procedura seguente accetta una classe generica definita nell'.NET Framework e ne crea un'istanza.  
  
### <a name="to-use-a-class-that-takes-a-type-parameter"></a>Per usare una classe che accetta un parametro di tipo  
  
1. All'inizio del file di origine, includere un' [istruzione Imports (tipo e spazio dei nomi .NET)](../../../language-reference/statements/imports-statement-net-namespace-and-type.md) per importare lo <xref:System.Collections.Generic?displayProperty=nameWithType> spazio dei nomi. In questo modo è possibile fare riferimento alla classe <xref:System.Collections.Generic.Queue%601?displayProperty=nameWithType> senza doverla specificare completamente per differenziarla da altre classi queue come <xref:System.Collections.Queue?displayProperty=nameWithType>.  
  
2. Creare l'oggetto in modo normale, ma aggiungere `(Of type)` immediatamente dopo il nome della classe.  
  
     L'esempio seguente usa la stessa classe (<xref:System.Collections.Generic.Queue%601?displayProperty=nameWithType>) per creare due oggetti queue che contengono elementi con tipi di dati diversi. Aggiunge gli elementi alla fine di ogni coda e quindi rimuove e visualizza gli elementi dall'inizio di ogni coda.  
  
     [!code-vb[VbVbalrDataTypes#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#9)]  
  
## <a name="see-also"></a>Vedere anche

- [Tipi di dati](index.md)
- [Generic Types in Visual Basic](generic-types.md)
- [Indipendenza del linguaggio e componenti indipendenti dal linguaggio](../../../../standard/language-independence-and-language-independent-components.md)
- [Di](../../../language-reference/statements/of-clause.md)
- [Istruzione Imports (tipo e spazio dei nomi .NET)](../../../language-reference/statements/imports-statement-net-namespace-and-type.md)
- [Procedura: Definire una classe in grado di fornire funzionalità identiche con tipi di dati diversi](how-to-define-a-class-that-can-provide-identical-functionality.md)
- [Iterators](../../concepts/iterators.md)

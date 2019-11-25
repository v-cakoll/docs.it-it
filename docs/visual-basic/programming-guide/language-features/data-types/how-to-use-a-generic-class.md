---
title: 'Procedura: utilizzare una classe generica'
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
ms.openlocfilehash: 87ca0da5095484615666cda505b4f7678d8160de
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350052"
---
# <a name="how-to-use-a-generic-class-visual-basic"></a>Procedura: utilizzare una classe generica (Visual Basic)
Una classe che accetta *parametri di tipo* è chiamato *classe generica*. Se si usa una classe generica, è possibile generare una *classe costruita* da essa fornendo un *argomento di tipo* per ciascuno di questi parametri. È possibile quindi dichiarare una variabile del tipo di classe costruita, creare un'istanza della classe costruita e assegnarla alla variabile.  
  
 Oltre alle classi, è possibile definire e usare anche strutture, interfacce, routine e delegati generici.  
  
 The following procedure takes a generic class defined in the .NET Framework and creates an instance from it.  
  
### <a name="to-use-a-class-that-takes-a-type-parameter"></a>Per usare una classe che accetta un parametro di tipo  
  
1. At the beginning of your source file, include an [Imports Statement (.NET Namespace and Type)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) to import the <xref:System.Collections.Generic?displayProperty=nameWithType> namespace. In questo modo è possibile fare riferimento alla classe <xref:System.Collections.Generic.Queue%601?displayProperty=nameWithType> senza doverla specificare completamente per differenziarla da altre classi queue come <xref:System.Collections.Queue?displayProperty=nameWithType>.  
  
2. Create the object in the normal way, but add `(Of type)` immediately after the class name.  
  
     L'esempio seguente usa la stessa classe (<xref:System.Collections.Generic.Queue%601?displayProperty=nameWithType>) per creare due oggetti queue che contengono elementi con tipi di dati diversi. Aggiunge gli elementi alla fine di ogni coda e quindi rimuove e visualizza gli elementi dall'inizio di ogni coda.  
  
     [!code-vb[VbVbalrDataTypes#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#9)]  
  
## <a name="see-also"></a>Vedere anche

- [Tipi di dati](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [Generic Types in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [Indipendenza del linguaggio e componenti indipendenti dal linguaggio](../../../../standard/language-independence-and-language-independent-components.md)
- [Of](../../../../visual-basic/language-reference/statements/of-clause.md)
- [Istruzione Imports (tipo e spazio dei nomi .NET)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
- [Procedura: Definire una classe in grado di fornire funzionalità identiche con tipi di dati diversi](../../../../visual-basic/programming-guide/language-features/data-types/how-to-define-a-class-that-can-provide-identical-functionality.md)
- [Iteratori](../../../../visual-basic/programming-guide/concepts/iterators.md)

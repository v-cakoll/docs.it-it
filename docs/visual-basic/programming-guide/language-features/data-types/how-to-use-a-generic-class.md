---
title: 'Procedura: utilizzare una classe generica (Visual Basic)'
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
ms.openlocfilehash: 108532e5b765fa918fa894199ef710a9f52db4e4
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/15/2018
ms.locfileid: "45658574"
---
# <a name="how-to-use-a-generic-class-visual-basic"></a>Procedura: utilizzare una classe generica (Visual Basic)
Una classe che accetta *parametri di tipo* è chiamato *classe generica*. Se si usa una classe generica, è possibile generare una *classe costruita* da essa fornendo un *argomento di tipo* per ciascuno di questi parametri. È possibile quindi dichiarare una variabile del tipo di classe costruita, creare un'istanza della classe costruita e assegnarla alla variabile.  
  
 Oltre alle classi, è possibile definire e usare anche strutture, interfacce, routine e delegati generici.  
  
 La procedura seguente accetta una classe generica definita in [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] e crea un'istanza da essa.  
  
### <a name="to-use-a-class-that-takes-a-type-parameter"></a>Per usare una classe che accetta un parametro di tipo  
  
1.  All'inizio del file di origine, includere un' [istruzione Imports (tipo e Namespace .NET)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) per importare il <xref:System.Collections.Generic?displayProperty=nameWithType> dello spazio dei nomi. In questo modo è possibile fare riferimento alla classe <xref:System.Collections.Generic.Queue%601?displayProperty=nameWithType> senza doverla specificare completamente per differenziarla da altre classi queue come <xref:System.Collections.Queue?displayProperty=nameWithType>.  
  
2.  Creare l'oggetto in modo normale, ma aggiungere `(Of` `type``)` immediatamente dopo il nome della classe.  
  
     L'esempio seguente usa la stessa classe (<xref:System.Collections.Generic.Queue%601?displayProperty=nameWithType>) per creare due oggetti queue che contengono elementi con tipi di dati diversi. Aggiunge gli elementi alla fine di ogni coda e quindi rimuove e visualizza gli elementi dall'inizio di ogni coda.  
  
     [!code-vb[VbVbalrDataTypes#9](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/how-to-use-a-generic-class_1.vb)]  
  
## <a name="see-also"></a>Vedere anche

- [Tipi di dati](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
- [Tipi generici in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)  
- [Indipendenza del linguaggio e componenti indipendenti dal linguaggio](../../../../standard/language-independence-and-language-independent-components.md)  
- [Of](../../../../visual-basic/language-reference/statements/of-clause.md)  
- [Istruzione Imports (tipo e spazio dei nomi .NET)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)  
- [Procedura: Definire una classe in grado di fornire funzionalità identiche con tipi di dati diversi](../../../../visual-basic/programming-guide/language-features/data-types/how-to-define-a-class-that-can-provide-identical-functionality.md)  
- [Iteratori](../../../../visual-basic/programming-guide/concepts/iterators.md)

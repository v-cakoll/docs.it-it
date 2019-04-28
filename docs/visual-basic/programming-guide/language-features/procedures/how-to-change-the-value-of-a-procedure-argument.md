---
title: 'Procedura: Modificare il valore di un argomento di routine (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], arguments
- procedures [Visual Basic], parameters
- procedure arguments
- arguments [Visual Basic], passing by reference
- Visual Basic code, procedures
- arguments [Visual Basic], ByVal
- arguments [Visual Basic], passing by value
- procedure parameters
- arguments [Visual Basic], ByRef
- arguments [Visual Basic], changing value
ms.assetid: 6fad2368-5da7-4c07-8bf8-0f4e65a1be67
ms.openlocfilehash: a56bdf888163c9559b87e857abb33522c547ed45
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61665832"
---
# <a name="how-to-change-the-value-of-a-procedure-argument-visual-basic"></a>Procedura: Modificare il valore di un argomento di routine (Visual Basic)
Quando si chiama una routine, ogni argomento che è fornire corrisponde a uno dei parametri definiti nella procedura. In alcuni casi, il codice della routine può modificare il valore sottostante a un argomento nel codice chiamante. In altri casi, la routine può modificare solo la copia locale di un argomento.  
  
 Quando si chiama la routine, Visual Basic effettua una copia locale di ogni argomento che viene passato [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md). Per ogni argomento passato [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), Visual Basic fornisce il codice della routine un riferimento diretto all'elemento di programmazione sottostante all'argomento nel codice chiamante.  
  
 Se l'elemento sottostante nel codice chiamante è modificabile e viene passato l'argomento `ByRef`, il riferimento diretto utilizzabili dal codice della procedura per modificare il valore dell'elemento nel codice chiamante.  
  
## <a name="changing-the-underlying-value"></a>La modifica del valore sottostante  
  
#### <a name="to-change-the-underlying-value-of-a-procedure-argument-in-the-calling-code"></a>Per modificare il valore sottostante di un argomento di routine nel codice chiamante  
  
1. Nella dichiarazione di routine, specificare [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) per il parametro corrisponde all'argomento.  
  
2. Nel codice chiamante, passare un elemento di programmazione modificabile come argomento.  
  
3. Nel codice chiamante, non racchiudere l'argomento racchiuso tra parentesi nell'elenco di argomenti.  
  
4. Nel codice della procedura, usare il nome del parametro per assegnare un valore per l'elemento sottostante nel codice chiamante.  
  
 Vedere l'esempio più avanti per una dimostrazione.  
  
## <a name="changing-local-copies"></a>Modifica delle copie locali  
 Se l'elemento sottostante nel codice chiamante non è modificabile o se viene passato l'argomento `ByVal`, la procedura non è possibile modificarne il valore nel codice chiamante. Tuttavia, la procedura è possibile modificare la copia locale di questo tipo di argomento.  
  
#### <a name="to-change-the-copy-of-a-procedure-argument-in-the-procedure-code"></a>Per modificare la copia di un argomento di routine nel codice della procedura  
  
1. Nella dichiarazione di routine, specificare [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) per il parametro corrisponde all'argomento.  
  
     -oppure-  
  
     Nel codice chiamante, racchiudere l'argomento racchiuso tra parentesi nell'elenco di argomenti. In tal modo Visual Basic per passare l'argomento per valore, anche se il parametro corrispondente specifica `ByRef`.  
  
2. Nel codice della procedura, usare il nome del parametro per assegnare un valore per la copia locale dell'argomento. Il valore sottostante nel codice chiamante non viene modificato.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente illustra due procedure che accettano una variabile di matrice e operano sui relativi elementi. Il `increase` procedure aggiunge semplicemente uno per ogni elemento. Il `replace` procedure assegna una nuova matrice al parametro `a()` , quindi aggiunge uno per ogni elemento.  
  
 [!code-vb[VbVbcnProcedures#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#35)]  
  
 [!code-vb[VbVbcnProcedures#36](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#36)]  
  
 [!code-vb[VbVbcnProcedures#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#37)]  
  
 Il primo `MsgBox` chiamata viene visualizzato "dopo aver Increase (n): 11, 21, 31, 41". Perché la matrice `n` è un tipo di riferimento `replace` possono modificare i relativi membri, anche se è il meccanismo di passaggio `ByVal`.  
  
 Il secondo `MsgBox` chiamata viene visualizzato "dopo Replace (n): 101, 201, 301". In quanto `n` viene passato `ByRef`, `replace` può modificare la variabile `n` nel codice chiamante e assegnare una nuova matrice a esso. In quanto `n` è un tipo riferimento, `replace` inoltre possibile modificare i relativi membri.  
  
 È possibile impedire la procedura di modifica la variabile nel codice chiamante. Vedere [How to: Proteggere un argomento di routine modifica del valore](./how-to-protect-a-procedure-argument-against-value-changes.md).  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 Quando si passa una variabile per riferimento, è necessario usare il `ByRef` parola chiave per specificare questo meccanismo.  
  
 L'impostazione predefinita in Visual Basic consiste nel passare argomenti per valore. Tuttavia, è buona norma includere il [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) oppure [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) parola chiave with ogni parametro dichiarato. Questo rende il codice più facile da leggere.  
  
## <a name="net-framework-security"></a>Sicurezza di .NET Framework  
 È sempre un potenziale rischio per consentire a una stored procedure per modificare il valore sottostante a un argomento nel codice chiamante. Assicurarsi che si prevede che questo valore per essere modificato e prepararsi a verificare la validità prima di poterla usare.  
  
## <a name="see-also"></a>Vedere anche

- [Routine](./index.md)
- [Parametri e argomenti delle routine](./procedure-parameters-and-arguments.md)
- [Procedura: Passare argomenti a una routine](./how-to-pass-arguments-to-a-procedure.md)
- [Passaggio di argomenti per valore e per riferimento](./passing-arguments-by-value-and-by-reference.md)
- [Differenze tra argomenti modificabili e non modificabili](./differences-between-modifiable-and-nonmodifiable-arguments.md)
- [Differenze tra il passaggio di un argomento per valore e per riferimento](./differences-between-passing-an-argument-by-value-and-by-reference.md)
- [Procedura: Proteggere un argomento di routine modifica del valore](./how-to-protect-a-procedure-argument-against-value-changes.md)
- [Procedura: Forzare un argomento da passare per valore](./how-to-force-an-argument-to-be-passed-by-value.md)
- [Passaggio di argomenti in base alla posizione e al nome](./passing-arguments-by-position-and-by-name.md)
- [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)

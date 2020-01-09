---
title: 'Procedura: cambiare il valore di un argomento di routine'
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
ms.openlocfilehash: deac87ca4690990a4d00f63d0ea9b843c3f9a9c4
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75344481"
---
# <a name="how-to-change-the-value-of-a-procedure-argument-visual-basic"></a>Procedura: cambiare il valore di un argomento di routine (Visual Basic)
Quando si chiama una routine, ogni argomento fornito corrisponde a uno dei parametri definiti nella stored procedure. In alcuni casi, il codice della procedura può modificare il valore sottostante un argomento nel codice chiamante. In altri casi, la procedura può modificare solo la copia locale di un argomento.  
  
 Quando si chiama la stored procedure, Visual Basic esegue una copia locale di ogni argomento passato [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md). Per ogni argomento passato [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), Visual Basic assegna al codice della procedura un riferimento diretto all'elemento di programmazione sottostante l'argomento nel codice chiamante.  
  
 Se l'elemento sottostante nel codice chiamante è un elemento modificabile e l'argomento viene passato `ByRef`, il codice della procedura può utilizzare il riferimento diretto per modificare il valore dell'elemento nel codice chiamante.  
  
## <a name="changing-the-underlying-value"></a>Modifica del valore sottostante  
  
#### <a name="to-change-the-underlying-value-of-a-procedure-argument-in-the-calling-code"></a>Per modificare il valore sottostante di un argomento di routine nel codice chiamante  
  
1. Nella dichiarazione di routine specificare [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) per il parametro corrispondente all'argomento.  
  
2. Nel codice chiamante passare un elemento di programmazione modificabile come argomento.  
  
3. Nel codice chiamante, non racchiudere l'argomento tra parentesi nell'elenco di argomenti.  
  
4. Nel codice della procedura usare il nome del parametro per assegnare un valore all'elemento sottostante nel codice chiamante.  
  
 Per una dimostrazione, vedere l'esempio più avanti.  
  
## <a name="changing-local-copies"></a>Modifica di copie locali  
 Se l'elemento sottostante nel codice chiamante è un elemento non modificabile o se l'argomento viene passato `ByVal`, la stored procedure non può modificarne il valore nel codice chiamante. Tuttavia, la procedura può modificare la copia locale di tale argomento.  
  
#### <a name="to-change-the-copy-of-a-procedure-argument-in-the-procedure-code"></a>Per modificare la copia di un argomento di routine nel codice della procedura  
  
1. Nella dichiarazione di routine specificare [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) per il parametro corrispondente all'argomento.  
  
     oppure  
  
     Nel codice chiamante racchiudere l'argomento tra parentesi nell'elenco di argomenti. Questa operazione impone Visual Basic di passare l'argomento per valore, anche se il parametro corrispondente specifica `ByRef`.  
  
2. Nel codice della procedura usare il nome del parametro per assegnare un valore alla copia locale dell'argomento. Il valore sottostante nel codice chiamante non viene modificato.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente vengono illustrate due procedure che accettano una variabile di matrice e operano sui relativi elementi. La procedura `increase` aggiunge semplicemente una a ogni elemento. La procedura `replace` assegna una nuova matrice al parametro `a()` e quindi ne aggiunge una a ogni elemento.  
  
 [!code-vb[VbVbcnProcedures#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#35)]  
  
 [!code-vb[VbVbcnProcedures#36](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#36)]  
  
 [!code-vb[VbVbcnProcedures#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#37)]  
  
 La prima chiamata di `MsgBox` Visualizza "After increase (n): 11, 21, 31, 41". Poiché la matrice `n` è un tipo di riferimento, `replace` possibile modificarne i membri, anche se il meccanismo di passaggio è `ByVal`.  
  
 La seconda chiamata di `MsgBox` Visualizza "dopo Replace (n): 101, 201, 301". Poiché `n` viene passato `ByRef`, `replace` possibile modificare la variabile `n` nel codice chiamante e assegnarvi una nuova matrice. Poiché `n` è un tipo di riferimento, `replace` possono anche modificare i relativi membri.  
  
 È possibile impedire la modifica della variabile nel codice chiamante da parte della stored procedure. Vedere [procedura: proteggere un argomento di routine in base alle modifiche del valore](./how-to-protect-a-procedure-argument-against-value-changes.md).  
  
## <a name="compile-the-code"></a>Compilare il codice  
 Quando si passa una variabile in base al riferimento, è necessario usare la parola chiave `ByRef` per specificare questo meccanismo.  
  
 Il valore predefinito in Visual Basic consiste nel passare gli argomenti per valore. Tuttavia, è consigliabile includere la parola chiave [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) o [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) con tutti i parametri dichiarati. Questo rende il codice più facile da leggere.  
  
## <a name="net-framework-security"></a>Sicurezza di .NET Framework  
 Esiste sempre un potenziale rischio nel consentire a una procedura di modificare il valore sottostante un argomento nel codice chiamante. Verificare che questo valore sia stato modificato e che sia stato preparato per verificarne la validità prima di usarlo.  
  
## <a name="see-also"></a>Vedere anche

- [Routine](./index.md)
- [Parametri e argomenti delle routine](./procedure-parameters-and-arguments.md)
- [Procedura: Passare argomenti a una routine](./how-to-pass-arguments-to-a-procedure.md)
- [Passaggio di argomenti per valore e per riferimento](./passing-arguments-by-value-and-by-reference.md)
- [Differenze tra argomenti modificabili e non modificabili](./differences-between-modifiable-and-nonmodifiable-arguments.md)
- [Differenze tra il passaggio di un argomento per valore e per riferimento](./differences-between-passing-an-argument-by-value-and-by-reference.md)
- [Procedura: impedire la modifica del valore di un argomento di una routine](./how-to-protect-a-procedure-argument-against-value-changes.md)
- [Procedura: forzare il passaggio di un argomento per valore](./how-to-force-an-argument-to-be-passed-by-value.md)
- [Passaggio di argomenti in base alla posizione e al nome](./passing-arguments-by-position-and-by-name.md)
- [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)

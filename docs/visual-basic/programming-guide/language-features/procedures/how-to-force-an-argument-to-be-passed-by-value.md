---
title: 'Procedura: Forzare un argomento può essere passato per valore (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], arguments
- procedures [Visual Basic], parameters
- procedure arguments
- Visual Basic code, procedures
- arguments [Visual Basic], ByVal
- arguments [Visual Basic], passing by value
- procedure parameters
- procedures [Visual Basic], calling
- arguments [Visual Basic], in parentheses
- procedure arguments [Visual Basic], in parentheses
- arguments [Visual Basic], changing value
ms.assetid: 77b4f2d2-1055-4c2f-a521-874d1db86946
ms.openlocfilehash: 7bd78772b35e3f336f49c1d39b5f56a3a2076c30
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "56970285"
---
# <a name="how-to-force-an-argument-to-be-passed-by-value-visual-basic"></a>Procedura: Forzare un argomento può essere passato per valore (Visual Basic)
La dichiarazione di routine determina il meccanismo di passaggio. Se un parametro dichiarato [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), Visual Basic prevede di passare l'argomento corrispondente per riferimento. In questo modo la procedura modificare il valore dell'elemento di programmazione sottostante all'argomento nel codice chiamante. Se si vuole proteggere l'elemento sottostante da tali modifiche, è possibile eseguire l'override di `ByRef` meccanismo di passaggio della procedura chiamata racchiudendo il nome dell'argomento racchiuso tra parentesi. Tali parentesi vengono aggiunte le parentesi che racchiudono l'elenco di argomenti nella chiamata.  
  
 Il codice chiamante non è possibile sostituire un [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) meccanismo.  
  
### <a name="to-force-an-argument-to-be-passed-by-value"></a>Per forzare un argomento da passare per valore  
  
-   Se viene dichiarato il parametro corrispondente `ByVal` nella procedura, non è necessario eseguire passaggi aggiuntivi. Visual Basic prevede già passare l'argomento per valore.  
  
-   Se viene dichiarato il parametro corrispondente `ByRef` nella procedura, racchiudere l'argomento racchiuso tra parentesi nella chiamata di procedura.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente esegue l'override di un `ByRef` dichiarazione del parametro. Nella chiamata che forza `ByVal`, notare i due livelli di parentesi.  
  
 [!code-vb[VbVbcnProcedures#39](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#39)]  
  
 [!code-vb[VbVbcnProcedures#40](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#40)]  
  
 Quando `str` è racchiuso tra parentesi aggiuntive nell'elenco degli argomenti, il `setNewString` procedure non è possibile modificarne il valore nel codice chiamante, e `MsgBox` Visualizza "Non può essere sostituito se viene passato ByVal". Quando `str` non è racchiuso tra parentesi aggiuntive, la routine può modificarlo, e `MsgBox` viene visualizzato "This is a un nuovo valore per l'argomento inString".  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 Quando si passa una variabile per riferimento, è necessario usare il `ByRef` parola chiave per specificare questo meccanismo.  
  
 L'impostazione predefinita in Visual Basic consiste nel passare argomenti per valore. Tuttavia, è buona norma includere il [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) oppure [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) parola chiave with ogni parametro dichiarato. Questo rende il codice più facile da leggere.  
  
## <a name="robust-programming"></a>Programmazione efficiente  
 Se una procedura dichiara un parametro [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), l'esecuzione corretta del codice potrebbe dipendere la possibilità di modificare l'elemento sottostante nel codice chiamante. Se il codice chiamante esegue l'override di questo meccanismo di chiamata racchiudendo l'argomento racchiuso tra parentesi o se passa un argomento non è modificabile, la procedura non è possibile modificare l'elemento sottostante. Ciò potrebbe produrre risultati imprevisti nel codice chiamante.  
  
## <a name="net-framework-security"></a>Sicurezza di .NET Framework  
 È sempre un potenziale rischio per consentire a una stored procedure per modificare il valore sottostante a un argomento nel codice chiamante. Assicurarsi che si prevede che questo valore per essere modificato e prepararsi a verificare la validità prima di poterla usare.  
  
## <a name="see-also"></a>Vedere anche
- [Routine](./index.md)
- [Parametri e argomenti delle routine](./procedure-parameters-and-arguments.md)
- [Procedura: Passare argomenti a una routine](./how-to-pass-arguments-to-a-procedure.md)
- [Passaggio di argomenti per valore e per riferimento](./passing-arguments-by-value-and-by-reference.md)
- [Differenze tra argomenti modificabili e non modificabili](./differences-between-modifiable-and-nonmodifiable-arguments.md)
- [Differenze tra il passaggio di un argomento per valore e per riferimento](./differences-between-passing-an-argument-by-value-and-by-reference.md)
- [Procedura: Modificare il valore di un argomento di routine](./how-to-change-the-value-of-a-procedure-argument.md)
- [Procedura: Proteggere un argomento di routine modifica del valore](./how-to-protect-a-procedure-argument-against-value-changes.md)
- [Passaggio di argomenti in base alla posizione e al nome](./passing-arguments-by-position-and-by-name.md)
- [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)

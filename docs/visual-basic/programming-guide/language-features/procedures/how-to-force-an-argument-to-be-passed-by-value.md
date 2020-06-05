---
title: 'Procedura: forzare il passaggio di un argomento per valore'
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
ms.openlocfilehash: 48f7d7afebd76916cba11459532d89d71871c79b
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84387967"
---
# <a name="how-to-force-an-argument-to-be-passed-by-value-visual-basic"></a>Procedura: forzare il passaggio di un argomento per valore (Visual Basic)
La dichiarazione di routine determina il meccanismo di passaggio. Se un parametro è dichiarato [ByRef](../../../language-reference/modifiers/byref.md), Visual Basic prevede di passare l'argomento corrispondente per riferimento. Ciò consente alla routine di modificare il valore dell'elemento di programmazione sottostante l'argomento nel codice chiamante. Se si desidera proteggere l'elemento sottostante da tale modifica, è possibile eseguire l'override del `ByRef` meccanismo di passaggio nella chiamata di procedura racchiudendo tra parentesi il nome dell'argomento. Queste parentesi si aggiungono alle parentesi che racchiudono l'elenco di argomenti nella chiamata.  
  
 Il codice chiamante non può eseguire l'override di un meccanismo [ByVal](../../../language-reference/modifiers/byval.md) .  
  
### <a name="to-force-an-argument-to-be-passed-by-value"></a>Per forzare il passaggio di un argomento per valore  
  
- Se il parametro corrispondente viene dichiarato `ByVal` nella procedura, non è necessario eseguire ulteriori passaggi. Visual Basic prevede di passare l'argomento per valore.  
  
- Se il parametro corrispondente viene dichiarato `ByRef` nella procedura, racchiudere l'argomento tra parentesi nella chiamata di procedura.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene eseguito l'override di una `ByRef` dichiarazione di parametro. Nella chiamata che forza `ByVal` , prendere nota dei due livelli di parentesi.  
  
 [!code-vb[VbVbcnProcedures#39](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#39)]  
  
 [!code-vb[VbVbcnProcedures#40](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#40)]  
  
 Quando `str` è racchiuso tra parentesi aggiuntive all'interno dell'elenco di argomenti, la `setNewString` procedura non può modificare il valore nel codice chiamante e `MsgBox` Visualizza "non può essere sostituito se passato ByVal". Quando `str` non è racchiuso tra parentesi aggiuntive, la procedura può modificarla e `MsgBox` Visualizza "questo è un nuovo valore per l'argomento inString".  
  
## <a name="compile-the-code"></a>Compilare il codice  
 Quando si passa una variabile in base al riferimento, è necessario usare la `ByRef` parola chiave per specificare questo meccanismo.  
  
 Il valore predefinito in Visual Basic consiste nel passare gli argomenti per valore. Tuttavia, è consigliabile includere la parola chiave [ByVal](../../../language-reference/modifiers/byval.md) o [ByRef](../../../language-reference/modifiers/byref.md) con tutti i parametri dichiarati. Questo rende il codice più facile da leggere.  
  
## <a name="robust-programming"></a>Programmazione efficiente  
 Se una routine dichiara un parametro [ByRef](../../../language-reference/modifiers/byref.md), l'esecuzione corretta del codice potrebbe dipendere dalla possibilità di modificare l'elemento sottostante nel codice chiamante. Se il codice chiamante esegue l'override di questo meccanismo chiamante racchiudendo l'argomento tra parentesi o se passa un argomento non modificabile, la procedura non può modificare l'elemento sottostante. Questo potrebbe produrre risultati imprevisti nel codice chiamante.  
  
## <a name="net-framework-security"></a>Sicurezza di .NET Framework  
 Esiste sempre un potenziale rischio nel consentire a una procedura di modificare il valore sottostante un argomento nel codice chiamante. Verificare che questo valore sia stato modificato e che sia stato preparato per verificarne la validità prima di usarlo.  
  
## <a name="see-also"></a>Vedere anche

- [Procedure](./index.md)
- [Parametri e argomenti delle routine](./procedure-parameters-and-arguments.md)
- [Procedura: passare argomenti a una routine](./how-to-pass-arguments-to-a-procedure.md)
- [Passaggio di argomenti per valore e per riferimento](./passing-arguments-by-value-and-by-reference.md)
- [Differenze tra argomenti modificabili e non modificabili](./differences-between-modifiable-and-nonmodifiable-arguments.md)
- [Differenze tra il passaggio di un argomento per valore e per riferimento](./differences-between-passing-an-argument-by-value-and-by-reference.md)
- [Procedura: cambiare il valore di un argomento di routine](./how-to-change-the-value-of-a-procedure-argument.md)
- [Procedura: impedire la modifica del valore di un argomento di una routine](./how-to-protect-a-procedure-argument-against-value-changes.md)
- [Passaggio di argomenti in base alla posizione e al nome](./passing-arguments-by-position-and-by-name.md)
- [Value Types and Reference Types](../data-types/value-types-and-reference-types.md)

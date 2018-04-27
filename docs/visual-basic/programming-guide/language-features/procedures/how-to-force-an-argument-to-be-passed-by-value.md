---
title: 'Procedura: forzare il passaggio di un argomento per valore (Visual Basic)'
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
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
caps.latest.revision: 16
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 30f5e5fe7b9c92f90673dc99a0e299136a38305b
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-force-an-argument-to-be-passed-by-value-visual-basic"></a>Procedura: forzare il passaggio di un argomento per valore (Visual Basic)
La dichiarazione di routine determina il meccanismo di passaggio. Se un parametro è dichiarato [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), Visual Basic è previsto passare all'argomento corrispondente per riferimento. In questo modo la procedura modificare il valore dell'elemento di programmazione sottostante all'argomento nel codice chiamante. Se si desidera proteggere l'elemento sottostante da tale modifica, è possibile eseguire l'override di `ByRef` meccanismo di passaggio della procedura chiamata racchiudendo il nome dell'argomento tra parentesi. Tali parentesi vengono aggiunte le parentesi che racchiude l'elenco di argomenti nella chiamata.  
  
 Il codice chiamante non è possibile sostituire un [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) meccanismo.  
  
### <a name="to-force-an-argument-to-be-passed-by-value"></a>Per forzare un argomento sia passati per valore  
  
-   Se il parametro corrispondente viene dichiarato `ByVal` nella procedura, non è necessario eseguire passaggi aggiuntivi. Visual Basic già prevede di passare l'argomento per valore.  
  
-   Se il parametro corrispondente viene dichiarato `ByRef` nella procedura, racchiudere l'argomento tra parentesi nella chiamata di procedura.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente esegue l'override di un `ByRef` dichiarazione di parametro. Nella chiamata che forza `ByVal`, tenere presente i due livelli di parentesi.  
  
 [!code-vb[VbVbcnProcedures#39](./codesnippet/VisualBasic/how-to-force-an-argument-to-be-passed-by-value_1.vb)]  
  
 [!code-vb[VbVbcnProcedures#40](./codesnippet/VisualBasic/how-to-force-an-argument-to-be-passed-by-value_2.vb)]  
  
 Quando `str` è racchiuso tra parentesi aggiuntive nell'elenco degli argomenti, il `setNewString` routine non può modificare il valore nel codice chiamante, e `MsgBox` Visualizza "Non può essere sostituito se passato ByVal". Quando `str` non viene racchiusa tra parentesi aggiuntive, la routine può modificarlo, e `MsgBox` Visualizza "This is a un nuovo valore per l'argomento inString".  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 Quando si passa una variabile per riferimento, è necessario utilizzare il `ByRef` (parola chiave) per specificare tale meccanismo.  
  
 Il valore predefinito in Visual Basic consiste nel passare gli argomenti per valore. Tuttavia, è buona norma includere una programmazione di [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) o [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) (parola chiave) con ogni parametro dichiarato. Questo rende il codice più facile da leggere.  
  
## <a name="robust-programming"></a>Programmazione efficiente  
 Se una routine dichiara un parametro [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), la corretta esecuzione del codice potrebbe dipendere in grado di modificare l'elemento sottostante nel codice chiamante. Se il codice chiamante esegue l'override di questo meccanismo di chiamata racchiudendo l'argomento tra parentesi, o se passa un argomento non modificabile, la procedura non è possibile modificare l'elemento sottostante. Ciò potrebbe produrre risultati imprevisti nel codice chiamante.  
  
## <a name="net-framework-security"></a>Sicurezza di .NET Framework  
 È sempre un potenziale rischio per consentire a una stored procedure per modificare il valore sottostante a un argomento nel codice chiamante. Verificare che si prevede che questo valore da modificare e prepararsi a verificare la validità prima di utilizzarlo.  
  
## <a name="see-also"></a>Vedere anche  
 [Routine](./index.md)  
 [Parametri e argomenti delle routine](./procedure-parameters-and-arguments.md)  
 [Procedura: Passare argomenti a una routine](./how-to-pass-arguments-to-a-procedure.md)  
 [Passaggio di argomenti per valore e per riferimento](./passing-arguments-by-value-and-by-reference.md)  
 [Differenze tra argomenti modificabili e non modificabili](./differences-between-modifiable-and-nonmodifiable-arguments.md)  
 [Differenze tra il passaggio di un argomento per valore e per riferimento](./differences-between-passing-an-argument-by-value-and-by-reference.md)  
 [Procedura: cambiare il valore di un argomento di routine](./how-to-change-the-value-of-a-procedure-argument.md)  
 [Procedura: impedire la modifica del valore di un argomento di una routine](./how-to-protect-a-procedure-argument-against-value-changes.md)  
 [Passaggio di argomenti in base alla posizione e al nome](./passing-arguments-by-position-and-by-name.md)  
 [Tipi valore e tipi riferimento](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)

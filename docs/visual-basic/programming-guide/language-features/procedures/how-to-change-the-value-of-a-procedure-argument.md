---
title: 'Procedura: cambiare il valore di un argomento di routine (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ba23c8f0b4b0b6e751546019af902a6305b9ef53
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-change-the-value-of-a-procedure-argument-visual-basic"></a>Procedura: cambiare il valore di un argomento di routine (Visual Basic)
Quando si chiama una routine, ogni argomento che è fornire corrisponde a uno dei parametri definiti nella procedura. In alcuni casi, il codice della stored procedure può modificare il valore sottostante a un argomento nel codice chiamante. In altri casi, la routine può modificare solo la copia locale di un argomento.  
  
 Quando si chiama la routine, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] crea una copia locale di ogni argomento passato [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md). Per ogni argomento passato [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] fornisce il codice della routine un riferimento diretto all'elemento di programmazione sottostante all'argomento nel codice chiamante.  
  
 Se l'elemento sottostante nel codice chiamante è modificabile e viene passato l'argomento `ByRef`, il codice della stored procedure è possibile utilizzare il riferimento diretto per modificare il valore dell'elemento nel codice chiamante.  
  
## <a name="changing-the-underlying-value"></a>La modifica del valore sottostante  
  
#### <a name="to-change-the-underlying-value-of-a-procedure-argument-in-the-calling-code"></a>Per modificare il valore sottostante di un argomento di routine nel codice chiamante  
  
1.  Nella dichiarazione di routine, specificare [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) per il parametro corrisponde all'argomento.  
  
2.  Nel codice chiamante, passare un elemento di programmazione modificabile come argomento.  
  
3.  Nel codice chiamante, non racchiudere l'argomento tra parentesi nell'elenco di argomenti.  
  
4.  Nel codice della procedura, utilizzare il nome del parametro per assegnare un valore per l'elemento sottostante nel codice chiamante.  
  
 Vedere l'esempio più in basso per una dimostrazione.  
  
## <a name="changing-local-copies"></a>Modifica delle copie locali  
 Se l'elemento sottostante nel codice chiamante non è modificabile, o se l'argomento viene passato `ByVal`, la procedura non è possibile modificarne il valore nel codice chiamante. Tuttavia, la procedura è possibile modificare la copia locale di questo tipo di argomento.  
  
#### <a name="to-change-the-copy-of-a-procedure-argument-in-the-procedure-code"></a>Per modificare la copia di un argomento di routine nel codice della procedura  
  
1.  Nella dichiarazione di routine, specificare [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) per il parametro corrisponde all'argomento.  
  
     -oppure-  
  
     Nel codice chiamante, racchiudere l'argomento tra parentesi nell'elenco di argomenti. In questo modo [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] per passare l'argomento per valore, anche se il parametro corrispondente specifica `ByRef`.  
  
2.  Nel codice della procedura, utilizzare il nome del parametro per assegnare un valore per la copia locale dell'argomento. Il valore sottostante nel codice chiamante non è stato modificato.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente mostra due procedure che accettano una variabile di matrice e operano sui relativi elementi. Il `increase` procedura aggiunge semplicemente uno per ogni elemento. Il `replace` procedure assegna una nuova matrice al parametro `a()` , quindi aggiunge uno per ogni elemento.  
  
 [!code-vb[VbVbcnProcedures#35](./codesnippet/VisualBasic/how-to-change-the-value-of-a-procedure-argument_1.vb)]  
  
 [!code-vb[VbVbcnProcedures#36](./codesnippet/VisualBasic/how-to-change-the-value-of-a-procedure-argument_2.vb)]  
  
 [!code-vb[VbVbcnProcedures#37](./codesnippet/VisualBasic/how-to-change-the-value-of-a-procedure-argument_3.vb)]  
  
 Il primo `MsgBox` chiamata viene visualizzato "dopo Increase (n): 11, 21, 31, 41". Poiché la matrice `n` è un tipo riferimento, `replace` possibile modificare i relativi membri, anche se è il meccanismo di passaggio `ByVal`.  
  
 Il secondo `MsgBox` chiamata viene visualizzato "dopo Replace (n): 101, 201, 301". Poiché `n` viene passato `ByRef`, `replace` possibile modificare la variabile `n` nel codice chiamante e assegnare una nuova matrice. Poiché `n` è un tipo riferimento, `replace` inoltre possibile modificare i relativi membri.  
  
 È possibile impedire la procedura di modifica la variabile nel codice chiamante. Vedere [procedura: proteggere un argomento di routine modifica del valore](./how-to-protect-a-procedure-argument-against-value-changes.md).  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 Quando si passa una variabile per riferimento, è necessario utilizzare il `ByRef` (parola chiave) per specificare tale meccanismo.  
  
 Il valore predefinito in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] gli argomenti vengono passati per valore. Tuttavia, è buona norma includere una programmazione di [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) o [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) (parola chiave) con ogni parametro dichiarato. Questo rende il codice più facile da leggere.  
  
## <a name="net-framework-security"></a>Sicurezza di .NET Framework  
 È sempre un potenziale rischio per consentire a una stored procedure per modificare il valore sottostante a un argomento nel codice chiamante. Verificare che si prevede che questo valore da modificare e prepararsi a verificare la validità prima di utilizzarlo.  
  
## <a name="see-also"></a>Vedere anche  
 [Routine](./index.md)  
 [Parametri e argomenti delle routine](./procedure-parameters-and-arguments.md)  
 [Procedura: Passare argomenti a una routine](./how-to-pass-arguments-to-a-procedure.md)  
 [Passaggio di argomenti per valore e per riferimento](./passing-arguments-by-value-and-by-reference.md)  
 [Differenze tra argomenti modificabili e non modificabili](./differences-between-modifiable-and-nonmodifiable-arguments.md)  
 [Differenze tra il passaggio di un argomento per valore e per riferimento](./differences-between-passing-an-argument-by-value-and-by-reference.md)  
 [Procedura: impedire la modifica del valore di un argomento di una routine](./how-to-protect-a-procedure-argument-against-value-changes.md)  
 [Procedura: forzare il passaggio di un argomento per valore](./how-to-force-an-argument-to-be-passed-by-value.md)  
 [Passaggio di argomenti in base alla posizione e al nome](./passing-arguments-by-position-and-by-name.md)  
 [Tipi valore e tipi riferimento](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)

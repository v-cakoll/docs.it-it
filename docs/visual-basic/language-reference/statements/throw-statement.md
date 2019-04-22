---
title: Istruzione Throw (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Throw
helpviewer_keywords:
- structured exception handling, throw statements
- try-catch exception handling, throw statements
- throw statement [Visual Basic], about throw statements
- throwing exceptions, throw statement
- exception handling, throw statement
- On Error statement [Visual Basic], throwing exceptions
- throwing exceptions
- exception handling, unstructured
- throw statement [Visual Basic]
ms.assetid: a6e07406-5c8a-4498-87a2-8339f3651d62
ms.openlocfilehash: 2494eac2f61f112f3ba6321ada7404f8cd618049
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "58821390"
---
# <a name="throw-statement-visual-basic"></a>Istruzione Throw (Visual Basic)
Genera un'eccezione all'interno di una routine.  
  
## <a name="syntax"></a>Sintassi  
  
```  
Throw [ expression ]  
```  
  
## <a name="part"></a>Parte  
 `expression`  
 Vengono fornite informazioni sull'eccezione generata. Facoltativo quando che risiedono un `Catch` istruzione, in caso contrario, è necessario.  
  
## <a name="remarks"></a>Note  
 Il `Throw` istruzione genera un'eccezione che è possibile gestire con un codice di gestione delle eccezioni strutturata (`Try`... `Catch`... `Finally`) o il codice di gestione delle eccezioni non strutturato (`On Error GoTo`). È possibile usare il `Throw` istruzione per intercettare gli errori all'interno del codice perché Visual Basic sposta verso l'alto nello stack di chiamate fino a individuare il codice di gestione delle eccezioni appropriato.  
  
 Oggetto `Throw` istruzione senza un'espressione può essere usata solo un `Catch` istruzione, in cui l'istruzione case genera nuovamente l'eccezione attualmente gestita dal `Catch` istruzione.  
  
 Il `Throw` istruzione Reimposta lo stack di chiamate per il `expression` eccezione. Se `expression` non viene specificato, lo stack di chiamate viene lasciata invariata. È possibile accedere lo stack di chiamate dell'eccezione mediante il <xref:System.Exception.StackTrace%2A> proprietà.  
  
## <a name="example"></a>Esempio  
 Il codice seguente usa il `Throw` istruzione per generare un'eccezione:  
  
 [!code-vb[VbVbalrStatements#84](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#84)]  
  
## <a name="requirements"></a>Requisiti  
 **Spazio dei nomi:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)  
  
 **Modulo:** `Interaction`  
  
 **Assembly:** Visual Basic Runtime Library (in Microsoft.VisualBasic.dll)  
  
## <a name="see-also"></a>Vedere anche

- [Istruzione Try...Catch...Finally](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [Istruzione On Error](../../../visual-basic/language-reference/statements/on-error-statement.md)

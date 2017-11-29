---
title: 'Procedura: creare una stringa da una matrice di valori Char (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- examples [Visual Basic], arrays
- examples [Visual Basic], Char data type
ms.assetid: 69f94e85-d57c-4ccc-a62a-426e829f5c5e
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 06e5c6923c26f3cb84b38475d6680523853d727d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-string-from-an-array-of-char-values-visual-basic"></a>Procedura: creare una stringa da una matrice di valori Char (Visual Basic)
Questo esempio crea la stringa "abcd" da singoli caratteri.  
  
## <a name="example"></a>Esempio  
 [!code-vb[VbVbalrStrings#61](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-create-a-string-from-an-array-of-char-values_1.vb)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 Questo metodo non ha presenta requisiti speciali.  
  
 La sintassi `"a"c`, in cui un singolo `c` segue un singolo carattere tra virgolette, viene utilizzato per creare un carattere letterale.  
  
## <a name="robust-programming"></a>Programmazione efficiente  
 Caratteri null (equivalente a `Chr(0)`) nella stringa di produrre risultati imprevisti quando si utilizza la stringa. Il carattere null sarà incluso nella stringa, ma non caratteri che seguono il carattere null verranno visualizzati in alcune situazioni.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.String>  
 [Tipo di dati Char](../../../../visual-basic/language-reference/data-types/char-data-type.md)  
 [Tipi di dati](../../../../visual-basic/programming-guide/language-features/data-types/index.md)

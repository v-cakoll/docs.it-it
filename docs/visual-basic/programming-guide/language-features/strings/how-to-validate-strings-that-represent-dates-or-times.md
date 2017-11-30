---
title: 'Procedura: convalidare le stringhe che rappresentano date o ore (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- strings [Visual Basic], validating
- String data type [Visual Basic], validation
ms.assetid: ae7d4b29-3436-4032-bdbf-4650eb1c8e19
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ed3201ef2bbef97eebbafa5ef128ca015adac013
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-validate-strings-that-represent-dates-or-times-visual-basic"></a>Procedura: convalidare le stringhe che rappresentano date o ore (Visual Basic)
Nell'esempio di codice viene impostata una `Boolean` valore che indica se una stringa rappresenta una data valida o un'ora.  
  
## <a name="example"></a>Esempio  
 [!code-vb[VbVbcnRegEx#2](../../../../visual-basic/programming-guide/language-features/strings/codesnippet/VisualBasic/how-to-validate-strings-that-represent-dates-or-times_1.vb)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 Sostituire `("01/01/03")` e `"9:30 PM"` con la data e ora che si desidera convalidare. È possibile sostituire la stringa con un'altra stringa hardcoded, con un `String` o variabile, con un metodo che restituisce una stringa, ad esempio `InputBox`.  
  
## <a name="robust-programming"></a>Programmazione efficiente  
 Utilizzare questo metodo per convalidare la stringa prima di provare a convertire la `String` per un `DateTime` variabile. Controllando innanzitutto la data o ora, è possibile evitare la generazione di un'eccezione in fase di esecuzione.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:Microsoft.VisualBasic.Information.IsDate%2A>  
 <xref:Microsoft.VisualBasic.Interaction.InputBox%2A>  
 [Convalida delle stringhe in Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/validating-strings.md)

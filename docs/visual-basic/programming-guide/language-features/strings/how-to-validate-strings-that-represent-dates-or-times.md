---
title: 'Procedura: convalidare le stringhe che rappresentano date o ore (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], validating
- String data type [Visual Basic], validation
ms.assetid: ae7d4b29-3436-4032-bdbf-4650eb1c8e19
ms.openlocfilehash: 411c8517783421b2472c3e4aa77287f8252f179b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33647862"
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

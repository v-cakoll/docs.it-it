---
title: 'Procedura: Convalidare le stringhe che rappresentano date o ore (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], validating
- String data type [Visual Basic], validation
ms.assetid: ae7d4b29-3436-4032-bdbf-4650eb1c8e19
ms.openlocfilehash: 1a838d9d156ad9c05a70a4d4d72db1a288731c9b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54685399"
---
# <a name="how-to-validate-strings-that-represent-dates-or-times-visual-basic"></a>Procedura: Convalidare le stringhe che rappresentano date o ore (Visual Basic)
I seguente esempio di codice impostare un `Boolean` valore che indica se una stringa rappresenta una data valida o un'ora.  
  
## <a name="example"></a>Esempio  
 [!code-vb[VbVbcnRegEx#2](../../../../visual-basic/programming-guide/language-features/strings/codesnippet/VisualBasic/how-to-validate-strings-that-represent-dates-or-times_1.vb)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 Sostituire `("01/01/03")` e `"9:30 PM"` con la data e ora che si desidera convalidare. È possibile sostituire la stringa con un'altra stringa hardcoded, con un `String` variabile, o con un metodo che restituisce una stringa, ad esempio `InputBox`.  
  
## <a name="robust-programming"></a>Programmazione efficiente  
 Usare questo metodo per convalidare la stringa prima di tentare di convertire le `String` a un `DateTime` variabile. Controllando la data o ora prima di tutto, è possibile evitare la generazione di un'eccezione in fase di esecuzione.  
  
## <a name="see-also"></a>Vedere anche
- <xref:Microsoft.VisualBasic.Information.IsDate%2A>
- <xref:Microsoft.VisualBasic.Interaction.InputBox%2A>
- [Convalida delle stringhe in Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/validating-strings.md)

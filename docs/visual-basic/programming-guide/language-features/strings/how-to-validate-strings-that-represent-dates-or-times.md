---
title: 'Procedura: convalidare le stringhe che rappresentano date o ore'
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], validating
- String data type [Visual Basic], validation
ms.assetid: ae7d4b29-3436-4032-bdbf-4650eb1c8e19
ms.openlocfilehash: 34af6dffeb0d05eaeed38354f8007554b60e91b0
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344348"
---
# <a name="how-to-validate-strings-that-represent-dates-or-times-visual-basic"></a>Procedura: convalidare le stringhe che rappresentano date o ore (Visual Basic)
Nell'esempio di codice seguente viene impostato un valore `Boolean` che indica se una stringa rappresenta una data o un'ora valida.  
  
## <a name="example"></a>Esempio  
 [!code-vb[VbVbcnRegEx#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnRegEx/VB/Class1.vb#2)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 Sostituire `("01/01/03")` e `"9:30 PM"` con la data e l'ora che si desidera convalidare. È possibile sostituire la stringa con un'altra stringa hardcoded, con una `String` variabile o con un metodo che restituisce una stringa, ad esempio `InputBox`.  
  
## <a name="robust-programming"></a>Programmazione efficiente  
 Utilizzare questo metodo per convalidare la stringa prima di provare a convertire il `String` in una variabile `DateTime`. Controllando prima di tutto la data o l'ora, è possibile evitare di generare un'eccezione in fase di esecuzione.  
  
## <a name="see-also"></a>Vedere anche

- <xref:Microsoft.VisualBasic.Information.IsDate%2A>
- <xref:Microsoft.VisualBasic.Interaction.InputBox%2A>
- [Convalida delle stringhe in Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/validating-strings.md)

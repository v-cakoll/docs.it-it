---
title: 'Procedura: convalidare le stringhe che rappresentano date o ore'
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], validating
- String data type [Visual Basic], validation
ms.assetid: ae7d4b29-3436-4032-bdbf-4650eb1c8e19
ms.openlocfilehash: 5d153ac29039375386b3cd5f03609b1e4bd1d5bf
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410567"
---
# <a name="how-to-validate-strings-that-represent-dates-or-times-visual-basic"></a>Procedura: convalidare le stringhe che rappresentano date o ore (Visual Basic)
Nell'esempio di codice seguente viene impostato un `Boolean` valore che indica se una stringa rappresenta una data o un'ora valida.  
  
## <a name="example"></a>Esempio  
 [!code-vb[VbVbcnRegEx#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnRegEx/VB/Class1.vb#2)]  
  
## <a name="compile-the-code"></a>Compilare il codice  
 Sostituire `("01/01/03")` e `"9:30 PM"` con la data e l'ora in cui si desidera eseguire la convalida. È possibile sostituire la stringa con un'altra stringa hardcoded, con una `String` variabile o con un metodo che restituisce una stringa, ad esempio `InputBox` .  
  
## <a name="robust-programming"></a>Programmazione efficiente  
 Utilizzare questo metodo per convalidare la stringa prima di provare a convertire `String` in una `DateTime` variabile. Controllando prima di tutto la data o l'ora, è possibile evitare di generare un'eccezione in fase di esecuzione.  
  
## <a name="see-also"></a>Vedere anche

- <xref:Microsoft.VisualBasic.Information.IsDate%2A>
- <xref:Microsoft.VisualBasic.Interaction.InputBox%2A>
- [Convalida delle stringhe in Visual Basic](validating-strings.md)

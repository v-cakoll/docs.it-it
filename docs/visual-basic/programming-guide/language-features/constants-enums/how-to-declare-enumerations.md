---
title: 'Procedura: dichiarare enumerazioni (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- declarations [Visual Basic], enumerations
- enumerations [Visual Basic], declaring
- declaring enumerations [Visual Basic]
ms.assetid: db4ca1c3-f429-4c81-ae81-29e0157b29fd
caps.latest.revision: "24"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 938550ebbfcf099729db3de96b809549cb234d81
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-declare-enumerations-visual-basic"></a>Procedura: dichiarare enumerazioni (Visual Basic)
Per creare un'enumerazione con la `Enum` istruzione nella sezione delle dichiarazioni di una classe o modulo. È possibile dichiarare un'enumerazione con un metodo. Per specificare il livello di accesso appropriato, utilizzare `Private`, `Protected`, `Friend`, o `Public`.  
  
 Un `Enum` tipo ha un nome, un tipo sottostante e un set di campi, ognuno dei quali rappresenta una costante. Il nome deve essere un qualificatore di Visual Basic .NET valido. Il tipo sottostante deve essere uno dei tipi integer:`Byte`, `Short`, `Long` o `Integer`. Il valore predefinito è `Integer`. Le enumerazioni sono sempre fortemente tipizzate e non sono interscambiabili con tipi di numeri integer.  
  
 Enumerazioni non possono avere valori a virgola mobile. Se un'enumerazione viene assegnato un valore a virgola mobile con `Option Strict On`, si verificherà un errore del compilatore. Se `Option Strict` è `Off`, il valore viene convertito automaticamente nel `Enum` tipo.  
  
 Per informazioni sui nomi e su come utilizzare il `Imports` istruzione per evitare la qualificazione di nomi, vedere [qualifica di nomi ed enumerazioni](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md).  
  
### <a name="to-declare-an-enumeration"></a>Per dichiarare un'enumerazione  
  
1.  Scrivere una dichiarazione che include un livello di accesso di codice, il `Enum` (parola chiave) e un nome valido, come negli esempi seguenti, ognuno dei quali viene dichiarata una differente `Enum`.  
  
     [!code-vb[VbEnumsTask#3](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-enumerations_1.vb)]  
  
2.  Definire le costanti dell'enumerazione. Per impostazione predefinita, la prima costante di enumerazione è inizializzata su `0`, e le costanti successive vengono inizializzate su un valore di un altro rispetto alla costante precedente. Ad esempio, l'enumerazione seguente `Days`, contiene una costante denominata `Sunday` con il valore `0`, una costante denominata `Monday` con il valore `1`, una costante denominata `Tuesday` con il valore di `2`e così via.  
  
     [!code-vb[VbEnumsTask#4](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-enumerations_2.vb)]  
  
3.  In modo esplicito, è possibile assegnare valori alle costanti di enumerazione utilizzando un'istruzione di assegnazione. È possibile assegnare qualsiasi valore intero, inclusi i numeri negativi. Ad esempio, si consiglia di costanti con i valori minori di zero per rappresentare le condizioni di errore. Nell'enumerazione seguente, la costante `Invalid` viene assegnato in modo esplicito il valore `–1`e la costante `Sunday` viene assegnato il valore `0`. Perché è la prima costante nell'enumerazione, `Saturday` viene inoltre inizializzata sul valore `0`. Il valore di `Monday` è `1` (uno più il valore di `Sunday`); il valore di `Tuesday` è `2`e così via.  
  
     [!code-vb[VbEnumsTask#5](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-enumerations_3.vb)]  
  
### <a name="to-declare-an-enumeration-as-an-explicit-type"></a>Per dichiarare un'enumerazione come un tipo esplicito  
  
-   Specificare il tipo di enumerazione utilizzando il `As` clausola, come illustrato nell'esempio seguente.  
  
     [!code-vb[VbEnumsTask#6](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-enumerations_4.vb)]  
  
## <a name="see-also"></a>Vedere anche  
 [Qualifica di nomi ed enumerazioni](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)  
 [Procedura: Fare riferimento a un membro di enumerazione](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)  
 [Procedura: scorrere un'enumerazione in Visual Basic](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md)  
 [Procedura: Determinare la stringa associata a un valore di enumerazione](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)  
 [Quando usare un'enumerazione](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)  
 [Cenni preliminari sulle costanti](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)  
 [Tipi di dati costanti e letterali](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)  
 [Costanti ed enumerazioni](../../../../visual-basic/language-reference/constants-and-enumerations.md)

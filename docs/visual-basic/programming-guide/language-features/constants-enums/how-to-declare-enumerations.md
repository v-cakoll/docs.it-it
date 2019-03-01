---
title: 'Procedura: Dichiarare enumerazioni (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- declarations [Visual Basic], enumerations
- enumerations [Visual Basic], declaring
- declaring enumerations [Visual Basic]
ms.assetid: db4ca1c3-f429-4c81-ae81-29e0157b29fd
ms.openlocfilehash: 2654860269bc57cf6aed814760414c6ccb6383da
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "56968764"
---
# <a name="how-to-declare-enumerations-visual-basic"></a>Procedura: Dichiarare enumerazioni (Visual Basic)
Per creare un'enumerazione con i `Enum` istruzione nella sezione delle dichiarazioni di una classe o modulo. È possibile dichiarare un'enumerazione all'interno di un metodo. Per specificare il livello di accesso appropriato, usare `Private`, `Protected`, `Friend`, o `Public`.  
  
 Un `Enum` tipo ha un nome di un tipo sottostante e un set di campi, ognuno dei quali rappresenta una costante. Il nome deve essere un qualificatore di Visual Basic .NET valido. Il tipo sottostante deve essere uno dei tipi di numero intero, ovvero`Byte`, `Short`, `Long` o `Integer`. Il valore predefinito è `Integer`. Le enumerazioni sono sempre fortemente tipizzate e non sono intercambiabili tra tipi numerici integer.  
  
 Le enumerazioni non possono avere valori a virgola mobile. Se l'enumerazione viene assegnata un valore a virgola mobile con `Option Strict On`, si verificherà un errore del compilatore. Se `Option Strict` viene `Off`, il valore viene convertito automaticamente nel `Enum` tipo.  
  
 Per informazioni sui nomi e su come usare il `Imports` istruzione per rendere la qualificazione di nomi non necessari, vedere [qualifica di nomi ed enumerazioni](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md).  
  
### <a name="to-declare-an-enumeration"></a>Per dichiarare un'enumerazione  
  
1.  Scrivere una dichiarazione che include un livello di accesso di codice, il `Enum` parola chiave e un nome valido, come negli esempi seguenti, ognuno dei quali viene dichiarato un diverso `Enum`.  
  
     [!code-vb[VbEnumsTask#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#3)]  
  
2.  Definire le costanti nell'enumerazione. Per impostazione predefinita, la prima costante di enumerazione viene inizializzata a `0`, e le costanti successive vengono inizializzate sul valore uno oltre la costante precedente. Ad esempio, l'enumerazione seguente `Days`, contiene una costante denominata `Sunday` con il valore `0`, una costante denominata `Monday` con il valore `1`, una costante denominata `Tuesday` con il valore di `2`e così via.  
  
     [!code-vb[VbEnumsTask#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#4)]  
  
3.  In modo esplicito, è possibile assegnare valori alle costanti di enumerazione utilizzando un'istruzione di assegnazione. È possibile assegnare qualsiasi valore intero, inclusi i numeri negativi. Ad esempio, è possibile che le costanti con i valori minori di zero per rappresentare le condizioni di errore. Nell'enumerazione seguente, la costante `Invalid` viene assegnato in modo esplicito il valore `–1`e la costante `Sunday` viene assegnato il valore `0`. Perché è la prima costante nell'enumerazione `Saturday` viene inoltre inizializzata sul valore `0`. Il valore di `Monday` viene `1` (uno oltre il valore di `Sunday`); il valore di `Tuesday` è `2`e così via.  
  
     [!code-vb[VbEnumsTask#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#5)]  
  
### <a name="to-declare-an-enumeration-as-an-explicit-type"></a>Per dichiarare un'enumerazione come un tipo esplicito  
  
-   Specificare il tipo di enumerazione utilizzando il `As` clausola, come illustrato nell'esempio seguente.  
  
     [!code-vb[VbEnumsTask#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#6)]  
  
## <a name="see-also"></a>Vedere anche
- [Qualifica di nomi ed enumerazioni](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)
- [Procedura: Fare riferimento a un membro di enumerazione](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)
- [Procedura: Scorrere un'enumerazione in Visual Basic](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md)
- [Procedura: Determinare la stringa associata a un valore di enumerazione](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)
- [Quando usare un'enumerazione](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)
- [Cenni preliminari sulle costanti](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)
- [Tipi di dati costanti e letterali](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)
- [Costanti ed enumerazioni](../../../../visual-basic/language-reference/constants-and-enumerations.md)

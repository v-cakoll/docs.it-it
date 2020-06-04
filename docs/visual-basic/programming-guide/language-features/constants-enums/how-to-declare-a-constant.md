---
title: 'Procedura: dichiarare una costante'
ms.date: 07/20/2015
f1_keywords:
- vb.constant
helpviewer_keywords:
- Integer data type [Visual Basic], declaring constants
- Single data type [Visual Basic], declaring constants
- Const statement [Visual Basic], declaring constants
- procedures [Visual Basic], declaration
- data types [Visual Basic], constants
- Long data type [Visual Basic], declaring constants
- Visual Basic code, declaring variables and constants
- Double data type [Visual Basic], declaring constants
- Boolean data type [Visual Basic], declaring constants
- modules, declaring constants
- Byte data type [Visual Basic], declaring constants
- constants [Visual Basic], declaring
- Date data type [Visual Basic], declaring constants
- String data type [Visual Basic], declaring constants
- declaring constants [Visual Basic], const keyword
- Currency data type [Visual Basic], declaring constants and variants
- module-level constants and variables
- Object data type [Visual Basic], declaring constants
ms.assetid: f901b4fa-481f-4621-822e-427060577ad1
ms.openlocfilehash: ffaa98f6af3d4b276f5c0b1153841acdea0809d7
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84414479"
---
# <a name="how-to-declare-a-constant-visual-basic"></a>Procedura: dichiarare una costante (Visual Basic)
Usare l' `Const` istruzione per dichiarare una costante e impostarne il valore. Dichiarando una costante, si assegna un nome significativo a un valore. Una volta dichiarata una costante, non è possibile modificarla o assegnarle un nuovo valore.  
  
 Viene dichiarata una costante all'interno di una routine o nella sezione delle dichiarazioni di un modulo, una classe o una struttura. Le costanti a livello di classe o di struttura sono `Private` per impostazione predefinita, ma possono anche essere dichiarate come `Public` , `Friend` , `Protected` o `Protected Friend` per il livello di accesso al codice appropriato.  
  
 La costante deve avere un nome simbolico valido (le regole sono le stesse di quelle per la creazione di nomi di variabili) e un'espressione costituita da costanti e operatori numerici o di stringa (ma nessuna chiamata di funzione).  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-declare-a-constant"></a>Per dichiarare una costante  
  
- Scrivere una dichiarazione che includa un identificatore di accesso, la `Const` parola chiave e un'espressione, come negli esempi seguenti:  
  
     [!code-vb[VbEnumsTask#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#8)]  
  
     Quando [Option deduce](../../../language-reference/statements/option-infer-statement.md) è `Off` e [Option Strict](../../../language-reference/statements/option-strict-statement.md) è `On` , è necessario dichiarare una costante in modo esplicito specificando un tipo di dati ( `Boolean` ,, `Byte` `Char` , `DateTime` , `Decimal` , `Double` , `Integer` , `Long` , `Short` , `Single` o `String` ).  
  
     Quando `Option Infer` è `On` o `Option Strict` è `Off` , è possibile dichiarare una costante senza specificare un tipo di dati con una `As` clausola. Il compilatore determina il tipo della costante dal tipo dell'espressione. Per altre informazioni, vedere [tipi di dati costanti e letterali](constant-and-literal-data-types.md).  
  
### <a name="to-declare-a-constant-that-has-an-explicitly-stated-data-type"></a>Per dichiarare una costante con un tipo di dati dichiarato in modo esplicito  
  
- Scrivere una dichiarazione che includa la `As` parola chiave e un tipo di dati esplicito, come negli esempi seguenti:  
  
     [!code-vb[VbEnumsTask#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#9)]  
  
     È possibile dichiarare più costanti su una sola riga, anche se il codice è più leggibile se si dichiara una sola costante per riga. Se si dichiarano più costanti su una sola riga, devono avere lo stesso livello di accesso ( `Public` , `Private` , `Friend` , `Protected` o `Protected Friend` ).  
  
### <a name="to-declare-multiple-constants-on-a-single-line"></a>Per dichiarare più costanti su una sola riga  
  
- Separare le dichiarazioni con una virgola e uno spazio, come nell'esempio seguente:  
  
    ```vb  
    Public Const Four As Integer = 4, Five As Integer = 5, Six As Integer = 44  
    ```  
  
## <a name="see-also"></a>Vedere anche

- [Istruzione Const](../../../language-reference/statements/const-statement.md)
- [Tipi di dati costanti e letterali](constant-and-literal-data-types.md)
- [Cenni preliminari sulle costanti](constants-overview.md)
- [Procedura: dichiarare una costante](how-to-declare-a-constant.md)
- [Costanti definite dall'utente](user-defined-constants.md)
- [Tipi di dati costanti e letterali](constant-and-literal-data-types.md)
- [Procedura: raggruppare i valori delle costanti correlate](how-to-group-related-constant-values-together.md)
- [Cenni preliminari sulle enumerazioni](enumerations-overview.md)
- [Procedura: Dichiarare un'enumerazione](how-to-declare-enumerations.md)
- [Procedura: fare riferimento a un membro di enumerazione](how-to-refer-to-an-enumeration-member.md)
- [Qualifica di nomi ed enumerazioni](enumerations-and-name-qualification.md)
- [Procedura: Scorrere un'enumerazione](how-to-iterate-through-an-enumeration.md)
- [Procedura: determinare la stringa associata a un valore di enumerazione](how-to-determine-the-string-associated-with-an-enumeration-value.md)
- [Quando utilizzare un'enumerazione](when-to-use-an-enumeration.md)

- [Cenni preliminari sulle enumerazioni](enumerations-overview.md)
- [Cenni preliminari sulle costanti](constants-overview.md)
- [Procedura: dichiarare un'enumerazione](how-to-declare-enumerations.md)
- [Qualifica di nomi ed enumerazioni](enumerations-and-name-qualification.md)
- [Option Strict Statement](../../../language-reference/statements/option-strict-statement.md)
- [Costanti ed enumerazioni](../../../language-reference/constants-and-enumerations.md)

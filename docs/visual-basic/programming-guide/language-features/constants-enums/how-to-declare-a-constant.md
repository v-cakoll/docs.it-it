---
title: 'Procedura: Dichiarare una costante (Visual Basic)'
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
ms.openlocfilehash: b84afe4e354d4029bc61ba67bc93bd36a3430de4
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64610604"
---
# <a name="how-to-declare-a-constant-visual-basic"></a>Procedura: Dichiarare una costante (Visual Basic)
Si utilizza il `Const` istruzione per dichiarare una costante e impostarne il valore. Dichiarando una costante, si assegna un nome significativo su un valore. Una volta che viene dichiarata una costante, non può essere modificato o assegnato un nuovo valore.  
  
 Consente di dichiarare una costante all'interno di una routine o nella sezione delle dichiarazioni di un modulo, classe o struttura. Classe o le costanti a livello di struttura vengono `Private` per impostazione predefinita, ma possono anche essere dichiarati come `Public`, `Friend`, `Protected`, o `Protected Friend` per il livello di accesso di codice appropriato.  
  
 La costante deve avere un nome simbolico valido (le regole sono identici a quelli per la creazione di nomi di variabile) e un'espressione costituita da numerica o stringa costanti e operatori (ma non le chiamate di funzione).  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-declare-a-constant"></a>Per dichiarare una costante  
  
- Scrivere una dichiarazione che include un identificatore di accesso, il `Const` (parola chiave) e un'espressione, come negli esempi seguenti:  
  
     [!code-vb[VbEnumsTask#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#8)]  
  
     Quando [Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md) viene `Off` e [Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md) viene `On`, è necessario dichiarare una costante in modo esplicito specificando un tipo di dati (`Boolean`, `Byte`, `Char`, `DateTime`, `Decimal`, `Double`, `Integer`, `Long`, `Short`, `Single`, o `String`).  
  
     Quando `Option Infer` viene `On` oppure `Option Strict` viene `Off`, è possibile dichiarare una costante senza specificare un tipo di dati con un `As` clausola. Il compilatore determina il tipo della costante dal tipo dell'espressione. Per altre informazioni, vedere [costante e tipi di dati letterali](constant-and-literal-data-types.md).  
  
### <a name="to-declare-a-constant-that-has-an-explicitly-stated-data-type"></a>Per dichiarare una costante con un tipo di dati specificata in modo esplicito  
  
- Scrivere una dichiarazione che include il `As` digita parola chiave e una data esplicita, come negli esempi seguenti:  
  
     [!code-vb[VbEnumsTask#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#9)]  
  
     È possibile dichiarare più costanti in una singola riga, anche se quest'ultima è più leggibili se si dichiara una sola costante per ogni riga. Se si dichiarano più le costanti in una singola riga, devono tutti avere lo stesso livello di accesso (`Public`, `Private`, `Friend`, `Protected`, o `Protected Friend`).  
  
### <a name="to-declare-multiple-constants-on-a-single-line"></a>Per dichiarare le costanti di più su una singola riga  
  
- Separare le dichiarazioni con una virgola e uno spazio, come nell'esempio seguente:  
  
    ```  
    Public Const Four As Integer = 4, Five As Integer = 5, Six As Integer = 44  
    ```  
  
## <a name="see-also"></a>Vedere anche

- [Istruzione Const](../../../../visual-basic/language-reference/statements/const-statement.md)
- [Tipi di dati costanti e letterali](constant-and-literal-data-types.md)
- [Cenni preliminari sulle costanti](constants-overview.md)
- [Procedura: Dichiarare una costante](how-to-declare-a-constant.md)
- [Costanti definite dall'utente](user-defined-constants.md)
- [Tipi di dati costanti e letterali](constant-and-literal-data-types.md)
- [Procedura: Raggruppare i valori costanti correlate](how-to-group-related-constant-values-together.md)
- [Cenni preliminari sulle enumerazioni](enumerations-overview.md)
- [Procedura: Dichiarare un'enumerazione](how-to-declare-enumerations.md)
- [Procedura: Fare riferimento a un membro di enumerazione](how-to-refer-to-an-enumeration-member.md)
- [Qualifica di nomi ed enumerazioni](enumerations-and-name-qualification.md)
- [Procedura: Scorrere un'enumerazione](how-to-iterate-through-an-enumeration.md)
- [Procedura: Determinare la stringa associata a un valore di enumerazione](how-to-determine-the-string-associated-with-an-enumeration-value.md)
- [Quando usare un'enumerazione](when-to-use-an-enumeration.md)

- [Cenni preliminari sulle enumerazioni](enumerations-overview.md)
- [Cenni preliminari sulle costanti](constants-overview.md)
- [Procedura: Dichiarare un'enumerazione](how-to-declare-enumerations.md)
- [Qualifica di nomi ed enumerazioni](enumerations-and-name-qualification.md)
- [Istruzione Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [Costanti ed enumerazioni](../../../../visual-basic/language-reference/constants-and-enumerations.md)

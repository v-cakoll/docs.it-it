---
title: 'Procedura: dichiarare una costante (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
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
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 554f659e060087228fb43efd8b9d06103e21e980
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-declare-a-constant-visual-basic"></a>Procedura: dichiarare una costante (Visual Basic)
Utilizzare il `Const` istruzione per dichiarare una costante e impostarne il valore. Dichiarando una costante, assegnare un nome significativo su un valore. Dopo aver dichiarata una costante, non può essere modificato o assegnare un nuovo valore.  
  
 Dichiarare una costante all'interno di una stored procedure o nella sezione delle dichiarazioni di modulo, classe o struttura. Classe o le costanti a livello di struttura sono `Private` per impostazione predefinita, ma possono anche essere dichiarate come `Public`, `Friend`, `Protected`, o `Protected Friend` per il livello di accesso di codice appropriato.  
  
 La costante deve avere un nome simbolico valido (le regole sono gli stessi di quelli per la creazione di nomi di variabile) e un'espressione costituita da numerico o stringa costanti e operatori (ma non chiamate di funzioni).  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-declare-a-constant"></a>Per dichiarare una costante  
  
-   Scrivere una dichiarazione che include un identificatore di accesso, il `Const` (parola chiave) e un'espressione, come negli esempi seguenti:  
  
     [!code-vb[VbEnumsTask#8](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-a-constant_1.vb)]  
  
     Quando [Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md) è `Off` e [Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md) è `On`, è necessario dichiarare una costante in modo esplicito specificando un tipo di dati (`Boolean`, `Byte`, `Char`, `DateTime`, `Decimal`, `Double`, `Integer`, `Long`, `Short`, `Single`, o `String`).  
  
     Quando `Option Infer` è `On` o `Option Strict` è `Off`, è possibile dichiarare una costante senza specificare un tipo di dati con un `As` clausola. Il compilatore determina il tipo della costante dal tipo dell'espressione. Per ulteriori informazioni, vedere [costante e tipi di dati letterali](constant-and-literal-data-types.md).  
  
### <a name="to-declare-a-constant-that-has-an-explicitly-stated-data-type"></a>Per dichiarare una costante con un tipo di dati specificata in modo esplicito  
  
-   Scrivere una dichiarazione che include il `As` (parola chiave) e dati espliciti di un tipo, come negli esempi seguenti:  
  
     [!code-vb[VbEnumsTask#9](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-a-constant_2.vb)]  
  
     È possibile dichiarare più costanti in una singola riga, anche se il codice più leggibile se si dichiara una sola costante per ogni riga. Se si dichiarano più costanti in una singola riga, devono tutti avere lo stesso livello di accesso (`Public`, `Private`, `Friend`, `Protected`, o `Protected Friend`).  
  
### <a name="to-declare-multiple-constants-on-a-single-line"></a>Per dichiarare più costanti in una singola riga  
  
-   Le dichiarazioni, separarli con una virgola e uno spazio, come nell'esempio seguente:  
  
    ```  
    Public Const Four As Integer = 4, Five As Integer = 5, Six As Integer = 44  
    ```  
  
## <a name="see-also"></a>Vedere anche  
 [Istruzione Const](../../../../visual-basic/language-reference/statements/const-statement.md)  
 [Tipi di dati costanti e letterali](constant-and-literal-data-types.md)  
 [Cenni preliminari sulle costanti](constants-overview.md) [procedura: dichiarare una costante](how-to-declare-a-constant.md) [costanti definite dall'utente](user-defined-constants.md) [tipi di dati costanti e letterali](constant-and-literal-data-types.md) [come: gruppo Valori costanti correlate](how-to-group-related-constant-values-together.md) [Cenni preliminari sulle enumerazioni](enumerations-overview.md) [procedura: dichiarare enumerazioni](how-to-declare-enumerations.md) [procedura: fare riferimento a un membro di enumerazione](how-to-refer-to-an-enumeration-member.md) [Qualifica di nomi ed enumerazioni](enumerations-and-name-qualification.md) [procedura: scorrere un'enumerazione](how-to-iterate-through-an-enumeration.md) [procedura: determinare la stringa associata a un valore di enumerazione](how-to-determine-the-string-associated-with-an-enumeration-value.md) [Quando utilizzare un'enumerazione](when-to-use-an-enumeration.md)

 [Cenni preliminari sulle enumerazioni](enumerations-overview.md)  
 [Cenni preliminari sulle costanti](constants-overview.md)  
 [Procedura: dichiarare un'enumerazione](how-to-declare-enumerations.md)  
 [Qualifica di nomi ed enumerazioni](enumerations-and-name-qualification.md)  
 [Istruzione Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md)  
 [Costanti ed enumerazioni](../../../../visual-basic/language-reference/constants-and-enumerations.md)

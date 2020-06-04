---
title: "Procedura: Dichiarare un'enumerazione"
ms.date: 07/20/2015
helpviewer_keywords:
- declarations [Visual Basic], enumerations
- enumerations [Visual Basic], declaring
- declaring enumerations [Visual Basic]
ms.assetid: db4ca1c3-f429-4c81-ae81-29e0157b29fd
ms.openlocfilehash: c8f228c205c93adf7f2f555dc840a7daac61950b
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84414453"
---
# <a name="how-to-declare-enumerations-visual-basic"></a>Procedura: dichiarare enumerazioni (Visual Basic)
Si crea un'enumerazione con l' `Enum` istruzione nella sezione delle dichiarazioni di una classe o di un modulo. Non è possibile dichiarare un'enumerazione all'interno di un metodo. Per specificare il livello di accesso appropriato, utilizzare `Private` , `Protected` , `Friend` o `Public` .  
  
 Un `Enum` tipo ha un nome, un tipo sottostante e un set di campi, ognuno dei quali rappresenta una costante. Il nome deve essere un qualificatore di Visual Basic .NET valido. Il tipo sottostante deve essere uno dei tipi Integer, ovvero `Byte` , `Short` `Long` o `Integer` . Il valore predefinito è `Integer`. Le enumerazioni sono sempre fortemente tipizzate e non sono intercambiabili con i tipi di numeri interi.  
  
 Le enumerazioni non possono avere valori a virgola mobile. Se a un'enumerazione viene assegnato un valore a virgola mobile con `Option Strict On` , viene restituito un errore del compilatore. Se `Option Strict` è `Off` , il valore viene convertito automaticamente nel `Enum` tipo.  
  
 Per informazioni sui nomi e su come usare l' `Imports` istruzione per rendere non necessaria la qualificazione del nome, vedere [enumerazioni e qualificazione del nome](enumerations-and-name-qualification.md).  
  
### <a name="to-declare-an-enumeration"></a>Per dichiarare un'enumerazione  
  
1. Scrivere una dichiarazione che includa un livello di accesso al codice, la `Enum` parola chiave e un nome valido, come negli esempi seguenti, ciascuno dei quali dichiara un oggetto diverso `Enum` .  
  
     [!code-vb[VbEnumsTask#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#3)]  
  
2. Definire le costanti nell'enumerazione. Per impostazione predefinita, la prima costante in un'enumerazione viene inizializzata su `0` e le costanti successive vengono inizializzate su un valore maggiore di quello della costante precedente. L'enumerazione seguente,, ad esempio, `Days` contiene una costante denominata `Sunday` con il valore `0` , una costante denominata `Monday` con il valore `1` , una costante denominata `Tuesday` con il valore `2` e così via.  
  
     [!code-vb[VbEnumsTask#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#4)]  
  
3. È possibile assegnare in modo esplicito valori alle costanti in un'enumerazione usando un'istruzione di assegnazione. È possibile assegnare qualsiasi valore intero, inclusi i numeri negativi. È ad esempio possibile che si desideri che le costanti con valori minori di zero rappresentino le condizioni di errore. Nell'enumerazione seguente alla costante `Invalid` viene assegnato in modo esplicito il valore `–1` e alla costante `Sunday` viene assegnato il valore `0` . Poiché è la prima costante nell'enumerazione, `Saturday` viene inizializzata anche sul valore `0` . Il valore di `Monday` è `1` (uno più del valore di `Sunday` ), il valore di `Tuesday` è `2` e così via.  
  
     [!code-vb[VbEnumsTask#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#5)]  
  
### <a name="to-declare-an-enumeration-as-an-explicit-type"></a>Per dichiarare un'enumerazione come un tipo esplicito  
  
- Specificare il tipo di enum usando la `As` clausola, come illustrato nell'esempio seguente.  
  
     [!code-vb[VbEnumsTask#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#6)]  
  
## <a name="see-also"></a>Vedere anche

- [Qualifica di nomi ed enumerazioni](enumerations-and-name-qualification.md)
- [Procedura: fare riferimento a un membro di enumerazione](how-to-refer-to-an-enumeration-member.md)
- [Procedura: scorrere un'enumerazione in Visual Basic](how-to-iterate-through-an-enumeration.md)
- [Procedura: determinare la stringa associata a un valore di enumerazione](how-to-determine-the-string-associated-with-an-enumeration-value.md)
- [Quando utilizzare un'enumerazione](when-to-use-an-enumeration.md)
- [Cenni preliminari sulle costanti](constants-overview.md)
- [Tipi di dati costanti e letterali](constant-and-literal-data-types.md)
- [Costanti ed enumerazioni](../../../language-reference/constants-and-enumerations.md)

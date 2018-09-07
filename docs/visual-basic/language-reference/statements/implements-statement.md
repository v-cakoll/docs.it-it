---
title: Istruzione Implements (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Implements
- Implements
helpviewer_keywords:
- Implements statement [Visual Basic], syntax
- Implements statement [Visual Basic]
- interface implementation [Visual Basic], Implements statement
ms.assetid: 1fafb83f-f55a-4215-8ea9-681e8622613d
ms.openlocfilehash: 805813506b957afb326c71ee4bbb15837726e4e5
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2018
ms.locfileid: "44076319"
---
# <a name="implements-statement"></a>Istruzione Implements
Specifica uno o più interfacce, o i membri di interfaccia, che devono essere implementati nella classe o definizione della struttura in cui è presente.  
  
## <a name="syntax"></a>Sintassi  
  
```  
Implements interfacename [, ...]  
-or-  
Implements interfacename.interfacemember [, ...]  
```  
  
## <a name="parts"></a>Parti  
 `interfacename`  
 Obbligatorio. Interfaccia la cui proprietà, procedure e gli eventi devono essere implementati dai membri corrispondenti nella classe o struttura.  
  
 `interfacemember`  
 Obbligatorio. Il membro di interfaccia implementato.  
  
## <a name="remarks"></a>Note  
 Un'interfaccia è una raccolta di prototipi che rappresentano i membri (proprietà, routine ed eventi) in essa contenuti. Le interfacce contengono solo le dichiarazioni per i membri. le classi e strutture di implementano questi membri. Per altre informazioni, vedere [Interfacce](../../../visual-basic/programming-guide/language-features/interfaces/index.md).  
  
 Il `Implements` istruzione deve seguire immediatamente la `Class` o `Structure` istruzione.  
  
 Quando si implementa un'interfaccia, è necessario implementare tutti i membri dichiarati nell'interfaccia. Omissione di un membro viene considerato un errore di sintassi. Per implementare un singolo membro, si specifica la [Implements](../../../visual-basic/language-reference/statements/implements-clause.md) parola chiave (che si distinguono dal `Implements` istruzione) quando si dichiara il membro nella classe o struttura. Per altre informazioni, vedere [Interfacce](../../../visual-basic/programming-guide/language-features/interfaces/index.md).  
  
 Le classi possono utilizzare [privato](../../../visual-basic/language-reference/modifiers/private.md) implementazioni di proprietà e routine, ma questi membri sono accessibili solo tramite il casting di un'istanza della classe di implementazione in una variabile dichiarata di tipo dell'interfaccia.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come utilizzare il `Implements` istruzione per implementare i membri di un'interfaccia. Definisce un'interfaccia denominata `ICustomerInfo` con un evento, una proprietà e una procedura. La classe `customerInfo` implementa tutti i membri definiti nell'interfaccia.  
  
 [!code-vb[VbVbalrStatements#33](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/implements-statement_1.vb)]  
  
 Si noti che la classe `customerInfo` utilizza le `Implements` istruzione in una riga di codice sorgente separato per indicare che la classe implementa tutti i membri del `ICustomerInfo` interfaccia. Ogni membro nella classe Usa quindi il `Implements` (parola chiave) come parte della relativa dichiarazione di membro per indicare che l'implementazione di tale membro di interfaccia.  
  
## <a name="example"></a>Esempio  
 Le due procedure seguenti illustrano come è possibile usare l'interfaccia implementata nell'esempio precedente. Per testare l'implementazione, aggiungere queste procedure per il progetto e la chiamata di `testImplements` procedure.  
  
 [!code-vb[VbVbalrStatements#34](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/implements-statement_2.vb)]  
  
## <a name="see-also"></a>Vedere anche  
 [Implements](../../../visual-basic/language-reference/statements/implements-clause.md)  
 [Istruzione Interface](../../../visual-basic/language-reference/statements/interface-statement.md)  
 [Interfacce](../../../visual-basic/programming-guide/language-features/interfaces/index.md)

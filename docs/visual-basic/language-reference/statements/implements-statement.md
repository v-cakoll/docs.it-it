---
title: Istruzione Implements
ms.date: 07/20/2015
f1_keywords:
- vb.Implements
- Implements
helpviewer_keywords:
- Implements statement [Visual Basic], syntax
- Implements statement [Visual Basic]
- interface implementation [Visual Basic], Implements statement
ms.assetid: 1fafb83f-f55a-4215-8ea9-681e8622613d
ms.openlocfilehash: 7fb43934d8c200ff29b1caf63cec830b2c6633ce
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404550"
---
# <a name="implements-statement"></a>Istruzione Implements
Specifica una o più interfacce o membri di interfaccia che devono essere implementati nella definizione della classe o della struttura in cui vengono visualizzati.  
  
## <a name="syntax"></a>Sintassi  
  
```vb  
Implements interfacename [, ...]  
' -or-  
Implements interfacename.interfacemember [, ...]  
```  
  
## <a name="parts"></a>Parti  
 `interfacename`  
 Obbligatorio. Interfaccia le cui proprietà, routine ed eventi devono essere implementati dai membri corrispondenti nella classe o nella struttura.  
  
 `interfacemember`  
 Obbligatorio. Membro di un'interfaccia implementata.  
  
## <a name="remarks"></a>Commenti  
 Un'interfaccia è una raccolta di prototipi che rappresentano i membri (proprietà, routine ed eventi) che l'interfaccia incapsula. Le interfacce contengono solo le dichiarazioni per i membri; le classi e le strutture implementano questi membri. Per ulteriori informazioni, vedi [Interfacce](../../programming-guide/language-features/interfaces/index.md).  
  
 L' `Implements` istruzione deve seguire immediatamente l' `Class` `Structure` istruzione o.  
  
 Quando si implementa un'interfaccia, è necessario implementare tutti i membri dichiarati nell'interfaccia. L'omissione di qualsiasi membro viene considerato un errore di sintassi. Per implementare un singolo membro, è necessario specificare la parola chiave [Implements](implements-clause.md) , che è separata dall' `Implements` istruzione, quando si dichiara il membro nella classe o nella struttura. Per ulteriori informazioni, vedi [Interfacce](../../programming-guide/language-features/interfaces/index.md).  
  
 Le classi possono usare implementazioni [private](../modifiers/private.md) di proprietà e procedure, ma questi membri sono accessibili solo eseguendo il cast di un'istanza della classe di implementazione in una variabile dichiarata come tipo dell'interfaccia.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come utilizzare l' `Implements` istruzione per implementare i membri di un'interfaccia. Definisce un'interfaccia denominata `ICustomerInfo` con un evento, una proprietà e una routine. La classe `customerInfo` implementa tutti i membri definiti nell'interfaccia.  
  
 [!code-vb[VbVbalrStatements#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#33)]  
  
 Si noti che la classe `customerInfo` Usa l' `Implements` istruzione in una riga separata del codice sorgente per indicare che la classe implementa tutti i membri dell' `ICustomerInfo` interfaccia. Ogni membro della classe usa quindi la `Implements` parola chiave come parte della dichiarazione del membro per indicare che implementa il membro di interfaccia.  
  
## <a name="example"></a>Esempio  
 Le due procedure seguenti illustrano come usare l'interfaccia implementata nell'esempio precedente. Per testare l'implementazione, aggiungere queste procedure al progetto e chiamare la `testImplements` procedura.  
  
 [!code-vb[VbVbalrStatements#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#34)]  
  
## <a name="see-also"></a>Vedere anche

- [Implementazioni](implements-clause.md)
- [Istruzione Interface](interface-statement.md)
- [Interfacce](../../programming-guide/language-features/interfaces/index.md)

---
title: '#Const (direttiva) (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vb.#Const
- '#vb.Const'
- '#Const'
helpviewer_keywords:
- '#Const directive'
- conditional compilation [Visual Basic], directives
- Const directive (#Const)
- Visual Basic compiler, compiler directives
- constants [Visual Basic], Const directive
- constants [Visual Basic], declaring
- Const statement [Visual Basic], directive (#Const)
- 'declaring constants [Visual Basic], #const directive'
ms.assetid: 707669e5-23f9-4f17-8622-a0d534429386
ms.openlocfilehash: fb937a5a9d4688730085829350cb20172db50e97
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "56967048"
---
# <a name="const-directive"></a>Direttiva #Const
Definisce le costanti del compilatore condizionale per Visual Basic.  
  
## <a name="syntax"></a>Sintassi  
  
```  
#Const constname = expression  
```  
  
## <a name="parts"></a>Parti  
 `constname`  
 Obbligatorio. Nome della costante da definire.  
  
 `expression`  
 Obbligatorio. Valore letterale, altra costante di compilazione condizionale o qualsiasi combinazione che include uno o tutti gli operatori aritmetici o logici, tranne `Is`.  
  
## <a name="remarks"></a>Note  
 Costanti del compilatore condizionale sono sempre private per il file in cui vengono visualizzati. Non è possibile creare le costanti del compilatore pubblico usando il `#Const` direttiva; è possibile creare solo nell'interfaccia utente o con il `/define` opzione del compilatore.  
  
 È possibile utilizzare solo costanti del compilatore condizionale e i valori letterali in `expression`. Utilizzo di una costante di standard definita con `Const` provoca un errore. Al contrario, è possibile utilizzare costanti definite con la `#Const` parola chiave solo per la compilazione condizionale. Costanti può anche essere indefinito, nel qual caso hanno un valore di `Nothing`.  
  
## <a name="example"></a>Esempio  
 In questo esempio viene usata la direttiva `#Const`.  
  
 [!code-vb[VbVbalrConditionalComp#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConditionalComp/VB/Class1.vb#3)]  
  
## <a name="see-also"></a>Vedere anche
- [/define (Visual Basic)](../../../visual-basic/reference/command-line-compiler/define.md)
- [Direttive #If...Then...#Else](../../../visual-basic/language-reference/directives/if-then-else-directives.md)
- [Istruzione Const](../../../visual-basic/language-reference/statements/const-statement.md)
- [Compilazione condizionale](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
- [Istruzione If...Then...Else](../../../visual-basic/language-reference/statements/if-then-else-statement.md)

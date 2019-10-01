---
title: '#Direttiva Const (Visual Basic)'
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
ms.openlocfilehash: 9b8d2da2158a8244b4533eb6ef49049949417216
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2019
ms.locfileid: "71696850"
---
# <a name="const-directive"></a>Direttiva #Const
Definisce le costanti del compilatore condizionale per Visual Basic.  
  
## <a name="syntax"></a>Sintassi  
  
```vb  
#Const constname = expression  
```  
  
## <a name="parts"></a>Parti  
 `constname`  
 Obbligatorio. Nome della costante da definire.  
  
 `expression`  
 Obbligatorio. Valore letterale, altra costante del compilatore condizionale o qualsiasi combinazione che includa uno o tutti gli operatori aritmetici o logici tranne `Is`.  
  
## <a name="remarks"></a>Note  
 Le costanti del compilatore condizionale sono sempre private per il file in cui sono visualizzate. Non è possibile creare costanti del compilatore pubbliche usando la direttiva `#Const`; è possibile crearli solo nell'interfaccia utente o con l'opzione del compilatore `/define`.  
  
 È possibile utilizzare solo le costanti e i valori letterali del compilatore condizionale in `expression`. Se si utilizza una costante standard definita con `Const`, viene generato un errore. Viceversa, è possibile utilizzare le costanti definite con la parola chiave `#Const` solo per la compilazione condizionale. Le costanti possono anche essere indefinite, nel qual caso hanno un valore pari a `Nothing`.  
  
## <a name="example"></a>Esempio  
 In questo esempio viene usata la direttiva `#Const`.  
  
 [!code-vb[VbVbalrConditionalComp#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConditionalComp/VB/Class1.vb#3)]  
  
## <a name="see-also"></a>Vedere anche

- [/define (Visual Basic)](../../../visual-basic/reference/command-line-compiler/define.md)
- [Direttive #If...Then...#Else](../../../visual-basic/language-reference/directives/if-then-else-directives.md)
- [Istruzione Const](../../../visual-basic/language-reference/statements/const-statement.md)
- [Compilazione condizionale](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
- [Istruzione If...Then...Else](../../../visual-basic/language-reference/statements/if-then-else-statement.md)

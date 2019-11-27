---
title: '#Direttiva Const'
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
ms.openlocfilehash: 278219edb1bb5d1c0bb015611d69cbe4ae70014b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343838"
---
# <a name="const-directive"></a>Direttiva #Const

Definisce le costanti del compilatore condizionale per Visual Basic.  
  
## <a name="syntax"></a>Sintassi  
  
```vb  
#Const constname = expression  
```  
  
## <a name="parts"></a>Parti  

 `constname`  
 Obbligatoria. Nome della costante da definire.  
  
 `expression`  
 Obbligatoria. Valore letterale, altra costante del compilatore condizionale o qualsiasi combinazione che includa tutti gli operatori aritmetici o logici eccetto `Is`.  
  
## <a name="remarks"></a>Osservazioni  

 Le costanti del compilatore condizionale sono sempre private per il file in cui sono visualizzate. Non è possibile creare costanti del compilatore pubbliche usando la direttiva `#Const`; è possibile crearli solo nell'interfaccia utente o con l'opzione del compilatore `/define`.  
  
 È possibile utilizzare solo le costanti e i valori letterali del compilatore condizionale in `expression`. L'uso di una costante standard definita con `Const` causa un errore. Viceversa, è possibile utilizzare le costanti definite con la parola chiave `#Const` solo per la compilazione condizionale. Le costanti possono anche essere indefinite, nel qual caso hanno il valore `Nothing`.  
  
## <a name="example"></a>Esempio  

 In questo esempio viene usata la direttiva `#Const`.  
  
 [!code-vb[VbVbalrConditionalComp#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConditionalComp/VB/Class1.vb#3)]  
  
## <a name="see-also"></a>Vedere anche

- [-define (Visual Basic)](../../../visual-basic/reference/command-line-compiler/define.md)
- [Direttive #If...Then...#Else](../../../visual-basic/language-reference/directives/if-then-else-directives.md)
- [Istruzione Const](../../../visual-basic/language-reference/statements/const-statement.md)
- [Compilazione condizionale](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
- [Istruzione If...Then...Else](../../../visual-basic/language-reference/statements/if-then-else-statement.md)

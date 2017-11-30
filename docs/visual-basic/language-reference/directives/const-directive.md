---
title: '#<a name="const-directive"></a>Const (direttiva)'
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a6e162b01dc5c99fb7708337d259f9e66ddd6b64
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="const-directive"></a>Direttiva #Const
Definisce le costanti del compilatore condizionale per Visual Basic.  
  
## <a name="syntax"></a>Sintassi  
  
```  
#Const constname = expression  
```  
  
## <a name="parts"></a>Parti  
 `constname`  
 Obbligatorio. Nome della costante definita.  
  
 `expression`  
 Obbligatorio. Valore letterale, altra costante di compilazione condizionale o qualsiasi combinazione che include qualsiasi o tutti gli operatori aritmetici o logici, ad eccezione di `Is`.  
  
## <a name="remarks"></a>Note  
 Costanti del compilatore condizionale sono sempre private per il file in cui appaiono. Non è possibile creare costanti del compilatore pubblica utilizzando il `#Const` direttiva; è possibile creare solo nell'interfaccia utente o con il `/define` l'opzione del compilatore.  
  
 È possibile utilizzare solo costanti di compilazione condizionale e valori letterali in `expression`. Utilizzo di una costante standard definita con `Const` causa un errore. Al contrario, è possibile utilizzare costanti definite con la `#Const` parola chiave solo per la compilazione condizionale. Costanti possono anche essere non definite, nel qual caso hanno un valore di `Nothing`.  
  
## <a name="example"></a>Esempio  
 In questo esempio viene usata la direttiva `#Const`.  
  
 [!code-vb[VbVbalrConditionalComp#3](../../../visual-basic/language-reference/directives/codesnippet/VisualBasic/const-directive_1.vb)]  
  
## <a name="see-also"></a>Vedere anche  
 [/define (Visual Basic)](../../../visual-basic/reference/command-line-compiler/define.md)  
 [Direttive #If...Then...#Else](../../../visual-basic/language-reference/directives/if-then-else-directives.md)  
 [Istruzione Const](../../../visual-basic/language-reference/statements/const-statement.md)  
 [Compilazione condizionale](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)  
 [Istruzione If...Then...Else](../../../visual-basic/language-reference/statements/if-then-else-statement.md)

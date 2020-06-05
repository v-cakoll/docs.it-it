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
ms.openlocfilehash: 91152771a4ef5ec74a7408511ccc2afe28dd442e
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84415466"
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
 Obbligatorio. Valore letterale, altra costante del compilatore condizionale o qualsiasi combinazione che includa tutti gli operatori aritmetici o logici eccetto `Is` .  
  
## <a name="remarks"></a>Commenti  

 Le costanti del compilatore condizionale sono sempre private per il file in cui sono visualizzate. Non è possibile creare costanti del compilatore pubbliche usando la `#Const` direttiva. è possibile crearle solo nell'interfaccia utente o con l' `/define` opzione del compilatore.  
  
 È possibile utilizzare solo le costanti del compilatore condizionale e i valori letterali in `expression` . L'uso di una costante standard definita con `Const` causa un errore. Viceversa, è possibile utilizzare le costanti definite con la `#Const` parola chiave solo per la compilazione condizionale. Le costanti possono anche essere indefinite, nel qual caso hanno un valore di `Nothing` .  
  
## <a name="example"></a>Esempio  

 In questo esempio viene usata la direttiva `#Const`.  
  
 [!code-vb[VbVbalrConditionalComp#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConditionalComp/VB/Class1.vb#3)]  
  
## <a name="see-also"></a>Vedere anche

- [-define (Visual Basic)](../../reference/command-line-compiler/define.md)
- [#If... Direttive then... #Else](if-then-else-directives.md)
- [Istruzione Const](../statements/const-statement.md)
- [Compilazione condizionale](../../programming-guide/program-structure/conditional-compilation.md)
- [Istruzione If...Then...Else](../statements/if-then-else-statement.md)

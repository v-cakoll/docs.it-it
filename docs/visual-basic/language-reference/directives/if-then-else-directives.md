---
title: '#If... Then... #Else direttive (Visual Basic)'
ms.date: 04/11/2018
f1_keywords:
- vb.#EndIf
- '#End If'
- '#Then'
- '#ElseIf'
- vb.#ElseIf
- vb.#Else
- vb.#If
helpviewer_keywords:
- Visual Basic code, compiling
- '#If directive [Visual Basic]'
- conditional compilation [Visual Basic], directives
- '#End if directive [Visual Basic]'
- selective compiling
- else directive (#else)
- '#Else directive [Visual Basic]'
ms.assetid: 10bba104-e3fd-451b-b672-faa472530502
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 05aac9109e49897d1c4dbbad60d807eb3e47798d
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2018
ms.locfileid: "44081950"
---
# <a name="ifthenelse-directives"></a>Direttive #If...Then...#Else
Viene compilata in modo condizionale selezionati blocchi di codice Visual Basic.  
  
## <a name="syntax"></a>Sintassi  
  
```  
#If expression Then  
   statements  
[ #ElseIf expression Then  
   [ statements ]  
...  
#ElseIf expression Then  
   [ statements ] ]  
[ #Else  
   [ statements ] ]  
#End If  
```  
  
## <a name="parts"></a>Parti  
 `expression`  
 Obbligatorio per `#If` e `#ElseIf` istruzioni facoltative in un' posizione. Qualsiasi espressione, costituito esclusivamente da uno o più costanti del compilatore condizionale, i valori letterali e gli operatori, che restituisce `True` o `False`.  
  
 `statements`  
 Obbligatorio per `#If` istruzione blocco, facoltativo in un' posizione. Righe programma Visual Basic o le direttive del compilatore che vengono compilate se l'espressione associata viene valutata `True`.  
  
 `#End If`  
 Termina il `#If` blocco di istruzioni.  
  
## <a name="remarks"></a>Note  
 Nell'area di, il comportamento dei `#If...Then...#Else` direttive viene visualizzato lo stesso del `If...Then...Else` istruzioni. Tuttavia, il `#If...Then...#Else` direttive valutano ciò che viene compilato dal compilatore, mentre il `If...Then...Else` le istruzioni vengono valutate le condizioni in fase di esecuzione.  
  
 Compilazione condizionale viene in genere utilizzata per la compilazione del programma stesso per le diverse piattaforme. Viene inoltre usato per impedire il debug del codice venga visualizzato in un file eseguibile. Codice escluso durante la compilazione condizionale viene omesso completamente dal file eseguibile finale, in modo che non ha alcun effetto sulla dimensione o delle prestazioni.  
  
 Indipendentemente dal risultato di qualsiasi valutazione, tutte le espressioni vengono valutate usando `Option Compare Binary`. Il `Option Compare` istruzione non ha effetto sulle espressioni nelle `#If` e `#ElseIf` istruzioni.  
  
> [!NOTE]
>  Nessun formato a riga singola del `#If`, `#Else`, `#ElseIf`, e `#End If` direttive esiste. Nessun altro codice può apparire sulla stessa riga come una delle direttive. 

Le istruzioni all'interno di un blocco di compilazione condizionale devono includere istruzioni logiche completate. Ad esempio, non è possibile compilare in modo condizionale solo gli attributi di una funzione, ma è possibile dichiarare in modo condizionale la funzione insieme ai relativi attributi:

```vb
   #If DEBUG Then
   <WebMethod()>
   Public Function SomeFunction() As String
   #Else
   <WebMethod(CacheDuration:=86400)>
   Public Function SomeFunction() As String
   #End If
```

## <a name="example"></a>Esempio
 Questo esempio viene usato il `#If...Then...#Else` costrutto per determinare se si desidera compilare alcune istruzioni.  
  
 [!code-vb[VbVbalrConditionalComp#1](../../../visual-basic/language-reference/directives/codesnippet/VisualBasic/if-then-else-directives_1.vb)]  
  
## <a name="see-also"></a>Vedere anche  
[Direttiva #Const](../../../visual-basic/language-reference/directives/const-directive.md)  
[Istruzione If...Then...Else](../../../visual-basic/language-reference/statements/if-then-else-statement.md)  
[Compilazione condizionale](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)   
<xref:System.Diagnostics.ConditionalAttribute?displayProperty=nameWithType>   



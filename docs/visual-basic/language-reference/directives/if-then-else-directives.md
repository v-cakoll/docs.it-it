---
title: '#Se... Then... #Else direttive'
ms.date: 04/11/2018
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
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
ms.openlocfilehash: 884c7ed6f0a346f2d35f01006cea23e47907d13f
ms.sourcegitcommit: 9a4fe1a1c37b26532654b4bbe22d702237950009
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/16/2018
---
# <a name="ifthenelse-directives"></a>Direttive #If...Then...#Else
Consente di compilare in modo condizionale blocchi di codice Visual Basic selezionati.  
  
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
 Necessario per `#If` e `#ElseIf` istruzioni, facoltative in un' posizione. Qualsiasi espressione, costituita esclusivamente da uno o più costanti del compilatore condizionale, valori letterali e operatori, che restituisce `True` o `False`.  
  
 `statements`  
 Necessario per `#If` blocco di istruzioni, facoltativo in un' posizione. Righe di programma Visual Basic o le direttive del compilatore che vengono compilate se l'espressione associata restituisce `True`.  
  
 `#End If`  
 Termina il `#If` blocco di istruzioni.  
  
## <a name="remarks"></a>Note  
 Nell'area di, il comportamento del `#If...Then...#Else` direttive viene visualizzato lo stesso di quello del `If...Then...Else` istruzioni. Tuttavia, il `#If...Then...#Else` valutano ciò che viene compilato dal compilatore, mentre il `If...Then...Else` istruzioni valutano le condizioni in fase di esecuzione.  
  
 Compilazione condizionale viene in genere utilizzata per la compilazione del programma stesso per le diverse piattaforme. Viene inoltre utilizzato per impedire il debug del codice venga visualizzato in un file eseguibile. Codice escluso durante la compilazione condizionale viene omesso completamente dal file eseguibile finale, in modo non ha alcun effetto su dimensioni e prestazioni.  
  
 Indipendentemente dal risultato di ogni valutazione, tutte le espressioni vengono valutate utilizzando `Option Compare Binary`. Il `Option Compare` istruzione non ha effetto sulle espressioni in `#If` e `#ElseIf` istruzioni.  
  
> [!NOTE]
>  Nessuna forma a riga singola del `#If`, `#Else`, `#ElseIf`, e `#End If` direttive esiste. Nessun altro codice può trovarsi nella stessa riga come una delle direttive. 

Le istruzioni all'interno di un blocco di compilazione condizionale devono essere istruzioni logiche completate. Ad esempio, non è possibile compilare in modo condizionale solo gli attributi di una funzione, ma è possibile dichiarare in modo condizionale la funzione insieme ai relativi attributi:

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
 Questo esempio viene utilizzato il `#If...Then...#Else` costrutto per determinare se alcune istruzioni di compilazione.  
  
 [!code-vb[VbVbalrConditionalComp#1](../../../visual-basic/language-reference/directives/codesnippet/VisualBasic/if-then-else-directives_1.vb)]  
  
## <a name="see-also"></a>Vedere anche  
[Direttiva #Const](../../../visual-basic/language-reference/directives/const-directive.md)  
[Istruzione If...Then...Else](../../../visual-basic/language-reference/statements/if-then-else-statement.md)  
[Compilazione condizionale](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)   
<xref:System.Diagnostics.ConditionalAttribute?displayProperty=nameWithType>   



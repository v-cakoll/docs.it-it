---
title: '#Direttive If...Then...#Else'
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
ms.openlocfilehash: 7054a6ada4583c5d89e020437eb622a59d3eb17a
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410010"
---
# <a name="ifthenelse-directives"></a>Direttive #If...Then...#Else

Compila in modo condizionale i blocchi selezionati del codice Visual Basic.

## <a name="syntax"></a>Sintassi

```vb
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
Obbligatorio per `#If` le `#ElseIf` istruzioni e, facoltativo altrove. Qualsiasi espressione, costituita esclusivamente da una o più costanti del compilatore condizionali, valori letterali e operatori, che restituiscono `True` o `False` .

`statements`  
Obbligatorio per il `#If` blocco di istruzioni, facoltativo altrove. Visual Basic linee di programma o direttive del compilatore compilate se l'espressione associata restituisce `True` .

`#End If`  
Termina il `#If` blocco di istruzioni.

## <a name="remarks"></a>Commenti

Nell'area, il comportamento delle `#If...Then...#Else` direttive appare come quello delle `If...Then...Else` istruzioni. Tuttavia, le `#If...Then...#Else` direttive valutano gli elementi compilati dal compilatore, mentre le `If...Then...Else` istruzioni valutano le condizioni in fase di esecuzione.

La compilazione condizionale viene in genere utilizzata per compilare lo stesso programma per piattaforme diverse. Viene inoltre usato per impedire che il codice di debug venga visualizzato in un file eseguibile. Il codice escluso durante la compilazione condizionale viene omesso completamente dal file eseguibile finale, quindi non ha alcun effetto sulle dimensioni o sulle prestazioni.

Indipendentemente dal risultato di una valutazione, tutte le espressioni vengono valutate mediante `Option Compare Binary` . L' `Option Compare` istruzione non influisce sulle espressioni `#If` nelle `#ElseIf` istruzioni e.

> [!NOTE]
> Non esiste alcuna forma a riga singola `#If` delle `#Else` `#ElseIf` direttive,, e `#End If` . Non è possibile visualizzare altro codice nella stessa riga delle direttive.

Le istruzioni all'interno di un blocco di compilazione condizionale devono essere istruzioni logiche complete. Ad esempio, non è possibile compilare in modo condizionale solo gli attributi di una funzione, ma è possibile dichiarare la funzione in modo condizionale insieme ai relativi attributi:

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

Questo esempio usa il `#If...Then...#Else` costrutto per determinare se compilare determinate istruzioni.

[!code-vb[VbVbalrConditionalComp#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConditionalComp/VB/Class1.vb#1)]

## <a name="see-also"></a>Vedere anche

- [#Const (direttiva)](const-directive.md)
- [Istruzione If...Then...Else](../statements/if-then-else-statement.md)
- [Compilazione condizionale](../../programming-guide/program-structure/conditional-compilation.md)
- <xref:System.Diagnostics.ConditionalAttribute?displayProperty=nameWithType>

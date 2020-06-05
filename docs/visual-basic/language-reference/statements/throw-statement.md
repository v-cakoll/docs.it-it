---
title: Istruzione Throw
ms.date: 07/20/2015
f1_keywords:
- vb.Throw
helpviewer_keywords:
- structured exception handling, throw statements
- try-catch exception handling, throw statements
- throw statement [Visual Basic], about throw statements
- throwing exceptions, throw statement
- exception handling, throw statement
- On Error statement [Visual Basic], throwing exceptions
- throwing exceptions
- exception handling, unstructured
- throw statement [Visual Basic]
ms.assetid: a6e07406-5c8a-4498-87a2-8339f3651d62
ms.openlocfilehash: 95572b1739490e90f53da6b6ec283bfb532c46d3
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404135"
---
# <a name="throw-statement-visual-basic"></a>Istruzione Throw (Visual Basic)

Genera un'eccezione all'interno di una routine.

## <a name="syntax"></a>Sintassi

```vb
Throw [ expression ]
```

## <a name="part"></a>Parte

`expression`\
Fornisce informazioni sull'eccezione da generare. Facoltativo quando si trova in un' `Catch` istruzione, in caso contrario obbligatorio.

## <a name="remarks"></a>Commenti

L' `Throw` istruzione genera un'eccezione che può essere gestita con codice di gestione delle eccezioni strutturato ( `Try` ... `Catch` ...`Finally`) o codice di gestione delle eccezioni non strutturato ( `On Error GoTo` ). È possibile usare l' `Throw` istruzione per intercettare gli errori all'interno del codice perché Visual Basic sposta lo stack di chiamate fino a trovare il codice di gestione delle eccezioni appropriato.

Un'istruzione `Throw` senza espressione può essere utilizzata solo in un' `Catch` istruzione, nel qual caso l'istruzione genera nuovamente l'eccezione attualmente gestita dall' `Catch` istruzione.

L' `Throw` istruzione Reimposta lo stack di chiamate per l' `expression` eccezione. Se `expression` non viene specificato, lo stack di chiamate viene lasciato invariato. È possibile accedere allo stack di chiamate per l'eccezione tramite la <xref:System.Exception.StackTrace%2A> Proprietà.

## <a name="example"></a>Esempio

Nel codice seguente viene utilizzata l' `Throw` istruzione per generare un'eccezione:

[!code-vb[VbVbalrStatements#84](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#84)]

## <a name="see-also"></a>Vedere anche

- [Istruzione Try...Catch...Finally](try-catch-finally-statement.md)
- [Istruzione On Error](on-error-statement.md)

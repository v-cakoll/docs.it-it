---
title: Istruzione Throw (Visual Basic)
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
ms.openlocfilehash: 9680700267f17c8e316de351fead61f1dc4aded0
ms.sourcegitcommit: 9ee6cd851b6e176a5811ea28ed0d5935c71950f9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/09/2019
ms.locfileid: "68869014"
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

## <a name="remarks"></a>Note

L' `Throw` istruzione genera un'eccezione che può essere gestita con codice di gestione delle eccezioni strutturato (`Try`... `Catch`... ) o codice di gestione delle eccezioni non strutturato`On Error GoTo`(). `Finally` È possibile usare l' `Throw` istruzione per intercettare gli errori all'interno del codice perché Visual Basic sposta lo stack di chiamate fino a trovare il codice di gestione delle eccezioni appropriato.

Un' `Throw` istruzione senza espressione può essere utilizzata solo in un' `Catch` istruzione, nel qual caso l'istruzione genera nuovamente l'eccezione `Catch` attualmente gestita dall'istruzione.

L' `Throw` istruzione Reimposta lo stack di chiamate per l' `expression` eccezione. Se `expression` non viene specificato, lo stack di chiamate viene lasciato invariato. È possibile accedere allo stack di chiamate per l'eccezione tramite <xref:System.Exception.StackTrace%2A> la proprietà.

## <a name="example"></a>Esempio

Nel codice seguente viene utilizzata `Throw` l'istruzione per generare un'eccezione:

[!code-vb[VbVbalrStatements#84](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#84)]

## <a name="see-also"></a>Vedere anche

- [Istruzione Try...Catch...Finally](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [Istruzione On Error](../../../visual-basic/language-reference/statements/on-error-statement.md)

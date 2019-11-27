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
ms.openlocfilehash: 147345990b625e034e651e69b322bc098d0bd8de
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352788"
---
# <a name="throw-statement-visual-basic"></a>Istruzione Throw (Visual Basic)

Genera un'eccezione all'interno di una routine.

## <a name="syntax"></a>Sintassi

```vb
Throw [ expression ]
```

## <a name="part"></a>Parte

`expression`\
Fornisce informazioni sull'eccezione da generare. Facoltativo quando si trova in un'istruzione `Catch`; in caso contrario, obbligatorio.

## <a name="remarks"></a>Note

L'istruzione `Throw` genera un'eccezione che è possibile gestire con il codice di gestione delle eccezioni strutturato (`Try`...`Catch`...`Finally`) o il codice di gestione delle eccezioni non strutturato (`On Error GoTo`). È possibile usare l'istruzione `Throw` per intercettare gli errori all'interno del codice perché Visual Basic sposta lo stack di chiamate fino a trovare il codice di gestione delle eccezioni appropriato.

Un'istruzione `Throw` senza espressione può essere utilizzata solo in un'istruzione `Catch`, nel qual caso l'istruzione genera nuovamente l'eccezione attualmente gestita dall'istruzione `Catch`.

L'istruzione `Throw` Reimposta lo stack di chiamate per l'eccezione `expression`. Se `expression` non viene specificato, lo stack di chiamate viene lasciato invariato. È possibile accedere allo stack di chiamate per l'eccezione tramite la proprietà <xref:System.Exception.StackTrace%2A>.

## <a name="example"></a>Esempio

Nel codice seguente viene utilizzata l'istruzione `Throw` per generare un'eccezione:

[!code-vb[VbVbalrStatements#84](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#84)]

## <a name="see-also"></a>Vedere anche

- [Istruzione Try...Catch...Finally](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [Istruzione On Error](../../../visual-basic/language-reference/statements/on-error-statement.md)

---
title: 'Operatore :: - Riferimenti per C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- ::_CSharpKeyword
helpviewer_keywords:
- ':: operator [C#]'
- 'namespaces [C#], :: operator'
- namespace alias qualifier operator (::) [C#]
ms.assetid: 698b5a73-85cf-4e0e-9e8e-6496887f8527
ms.openlocfilehash: 0b456ed3ce9965ef389d8ce40167afa4ac33da18
ms.sourcegitcommit: 10986410e59ff29f2ec55c6759bde3eb4d1a00cb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/31/2019
ms.locfileid: "66422531"
---
# <a name="-operator-c-reference"></a>Operatore :: (Riferimenti per C#)

Il qualificatore di alias dello spazio dei nomi (`::`) viene usato per cercare gli identificatori. Viene sempre posizionato tra due identificatori, come nell'esempio seguente:

[!code-csharp[csRefOperators#27](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#27)]

L'operatore `::` può anche essere usato con una *direttiva using alias*:

```csharp
// using Col=System.Collections.Generic;
var numbers = new Col::List<int> { 1, 2, 3 };
```

## <a name="remarks"></a>Osservazioni

Il qualificatore di alias dello spazio dei nomi può essere `global`. In questo modo viene richiamata una ricerca nello spazio dei nomi globale anziché in uno spazio dei nomi con alias.

## <a name="for-more-information"></a>Per altre informazioni

Per un esempio di utilizzo dell'operatore `::`, vedere la seguente sezione:

- [Procedura: Usare l'alias dello spazio dei nomi globale](../../programming-guide/namespaces/how-to-use-the-global-namespace-alias.md)

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../index.md)
- [Guida per programmatori C#](../../programming-guide/index.md)
- [Operatori C#](index.md)
- [Operatore .](member-access-operators.md#member-access-operator-)
- [alias extern](../keywords/extern-alias.md)

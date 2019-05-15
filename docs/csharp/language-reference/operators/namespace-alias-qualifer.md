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
ms.openlocfilehash: 324f6711cdec478e5647b05d84c281f79e95f036
ms.sourcegitcommit: 4c10802ad003374641a2c2373b8a92e3c88babc8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/08/2019
ms.locfileid: "65452357"
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
- [Parole chiave per gli spazi dei nomi](../keywords/namespace-keywords.md)
- [Operatore .](member-access-operators.md#member-access-operator-)
- [alias extern](../keywords/extern-alias.md)
---
title: Gestire valori null nelle espressioni di query (LINQ in C#)
description: Informazioni su come gestire i valori Null nelle espressioni di query LINQ in C#.
ms.date: 12/01/2016
ms.assetid: ac63ae8b-724d-4251-9334-528f4e884ae7
ms.openlocfilehash: 3da490b72bd518df7be8c14b34655af8c6f84929
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/25/2020
ms.locfileid: "80249305"
---
# <a name="handle-null-values-in-query-expressions"></a>Gestire i valori Null nelle espressioni di query

In questo esempio viene illustrato come gestire i possibili valori Null nelle raccolte di origine. Una raccolta di oggetti, ad esempio <xref:System.Collections.Generic.IEnumerable%601>, può contenere elementi il cui valore è [Null](../language-reference/keywords/null.md). Se una raccolta di origine è Null o contiene un elemento il cui valore è Null e la query non gestisce valori Null, verrà generata un'eccezione <xref:System.NullReferenceException> quando si esegue la query.

## <a name="example"></a>Esempio

È possibile codificare in modo sicuro per evitare un'eccezione di riferimento Null come illustrato nell'esempio seguente:

[!code-csharp[csProgGuideLINQ#82](~/samples/snippets/csharp/concepts/linq/how-to-handle-null-values-in-query-expressions_1.cs)]

Nell'esempio precedente la clausola `where` esclude tutti gli elementi Null nella sequenza di categorie. Questa tecnica è indipendente dal controllo Null nella clausola join. In questo esempio è possibile usare l'espressione condizionale con Null poiché `Products.CategoryID` è di tipo `int?`, vale a dire una sintassi abbreviata di `Nullable<int>`.

## <a name="example"></a>Esempio

In una clausola join, se solo una delle chiavi di confronto è un tipo di valore nullable, è possibile eseguire il cast dell'altro a un tipo di valore nullable nell'espressione di query. Nell'esempio seguente si supponga che `EmployeeID` sia una colonna contenente valori di tipo `int?`:

[!code-csharp[csProgGuideLINQ#83](~/samples/snippets/csharp/concepts/linq/how-to-handle-null-values-in-query-expressions_2.cs)]

## <a name="see-also"></a>Vedere anche

- <xref:System.Nullable%601>
- [Language Integrated Query (LINQ)](index.md)
- [Tipi valore nullable](../language-reference/builtin-types/nullable-value-types.md)

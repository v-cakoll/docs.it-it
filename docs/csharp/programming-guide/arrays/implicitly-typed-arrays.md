---
title: Matrici tipizzate in modo implicito - Guida per programmatori C#
description: Il tipo di una matrice tipizzata in modo implicito in C# viene dedotto dagli elementi nell'inizializzatore di matrice. Utilizzare matrici tipizzate in modo implicito nelle espressioni di query.
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [C#], implicitly-typed
- implicitly-typed arrays [C#]
- C# language, implicitly typed arrays
ms.assetid: e05be95c-6732-403d-ae42-b35f057cbbea
ms.openlocfilehash: 1f14f68207dfb79c92eaa01ac2a8ffaa08facc03
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/20/2020
ms.locfileid: "86474709"
---
# <a name="implicitly-typed-arrays-c-programming-guide"></a>Matrici tipizzate in modo implicito (Guida per programmatori C#)

È possibile creare una matrice tipizzata in modo implicito in cui il tipo dell'istanza della matrice viene derivato tramite inferenza dagli elementi specificati nell'inizializzatore di matrice. Le regole per qualsiasi variabile tipizzata in modo implicito si applicano anche alle matrici tipizzate in modo implicito. Per altre informazioni, vedere [Variabili locali tipizzate in modo implicito](../classes-and-structs/implicitly-typed-local-variables.md).

Le matrici tipizzate in modo implicito vengono in genere usate nelle espressioni di query insieme ai tipi anonimi e agli inizializzatori di oggetto e di raccolta.

Gli esempi seguenti illustrano come creare una matrice tipizzata in modo implicito:

[!code-csharp[csProgGuideLINQ#37](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideLINQ/CS/csRef30LangFeatures_2.cs#37)]

Nell'esempio precedente si noti che con le matrici tipizzate in modo implicito, non vengono usate parentesi quadre sul lato sinistro dell'istruzione di inizializzazione. Si noti anche che le matrici di matrici vengono inizializzate usando `new []` esattamente come le matrici unidimensionali.

## <a name="implicitly-typed-arrays-in-object-initializers"></a>Matrici tipizzate in modo implicito negli inizializzatori di oggetto

Quando si crea un tipo anonimo che contiene una matrice, la matrice deve essere tipizzata in modo implicito nell'inizializzatore di oggetto del tipo. Nell'esempio seguente `contacts` è una matrice tipizzata in modo implicito di tipi anonimi, ognuno dei quali contiene una matrice denominata `PhoneNumbers`. Si noti che la parola chiave `var` non viene usata negli inizializzatori di oggetto.

[!code-csharp[csProgGuideLINQ#38](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideLINQ/CS/csRef30LangFeatures_2.cs#38)]

## <a name="see-also"></a>Vedere anche

- [Guida per programmatori C#](../index.md)
- [Variabili locali tipizzate in modo implicito](../classes-and-structs/implicitly-typed-local-variables.md)
- [Matrici](./index.md)
- [Tipi anonimi](../classes-and-structs/anonymous-types.md)
- [Inizializzatori di oggetto e di raccolta](../classes-and-structs/object-and-collection-initializers.md)
- [var](../../language-reference/keywords/var.md)
- [LINQ in C#](../../linq/index.md)

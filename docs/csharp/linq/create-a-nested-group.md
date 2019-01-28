---
title: Creare un gruppo annidato (LINQ in C#)
description: Informazioni su come creare un gruppo annidato in un'espressione di query LINQ in C#.
ms.date: 12/01/2016
ms.assetid: e9f00708-362e-4d13-98c5-d77549347ba0
ms.openlocfilehash: 7d056c9e215ccc7ca24d621b64e2328bed79f22e
ms.sourcegitcommit: 5dcfeb59179e81071f54840d4902cbe00b184294
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2019
ms.locfileid: "54857671"
---
# <a name="create-a-nested-group"></a>Creare un gruppo annidato

Nell'esempio seguente viene illustrato come creare gruppi annidati in un'espressione di query LINQ. Ogni gruppo creato in base all'anno o al livello degli studenti viene ulteriormente suddiviso in gruppi in base ai nomi delle persone.

## <a name="example"></a>Esempio

> [!NOTE]
> Questo esempio contiene riferimenti a oggetti definiti nel codice di esempio in [Eseguire una query su una raccolta di oggetti](query-a-collection-of-objects.md).

[!code-csharp[csProgGuideLINQ#24](~/samples/snippets/csharp/concepts/linq/how-to-create-a-nested-group_1.cs)]

Si noti che sono necessari tre cicli `foreach` annidati per eseguire l'iterazione degli elementi interni di un gruppo annidato.

## <a name="see-also"></a>Vedere anche

- [LINQ (Language-Integrated Query)](index.md)

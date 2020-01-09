---
title: into - Riferimenti per C#
ms.date: 07/20/2015
f1_keywords:
- into_CSharpKeyword
- into
helpviewer_keywords:
- into keyword [C#]
ms.assetid: 81ec62c1-f0b1-4755-8a31-959876e77f65
ms.openlocfilehash: f0f5ff1e56a65e83385f814df2fadd957f53561e
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75713631"
---
# <a name="into-c-reference"></a>into (Riferimenti per C#)

La parola chiave contestuale `into` può essere usata per creare un identificatore temporaneo al fine di archiviare i risultati di una clausola [group](group-clause.md), [join](join-clause.md) o [select](select-clause.md) in un nuovo identificatore. Questo identificatore può essere un generatore per altri comandi di query. Se usato in una clausola `group` o `select`, l'utilizzo del nuovo identificatore viene talvolta definito *continuazione*.

## <a name="example"></a>Esempio

Nell'esempio seguente viene illustrato l'utilizzo della parola chiave `into` per attivare un identificatore temporaneo `fruitGroup` che contiene un tipo dedotto di `IGrouping`. Usando l'identificatore, è possibile richiamare il metodo <xref:System.Linq.Enumerable.Count%2A> su ogni gruppo e selezionare solo i gruppi che contengono due o più parole.

[!code-csharp[cscsrefQueryKeywords#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Into.cs#18)]

L'utilizzo di `into` in una clausola `group` è necessario solo quando si vuole eseguire operazioni di query aggiuntive in ogni gruppo. Per altre informazioni, vedere [Clausola group](group-clause.md).

Per un esempio di utilizzo di `into` in una clausola `join`, vedere [Clausola join](join-clause.md).

## <a name="see-also"></a>Vedere anche

- [Parole chiave di query (LINQ)](query-keywords.md)
- [LINQ in C#](../../linq/index.md)
- [Clausola group](group-clause.md)

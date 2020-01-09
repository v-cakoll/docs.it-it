---
title: Clausola from (Riferimento C#)
ms.date: 07/20/2015
f1_keywords:
- from_CSharpKeyword
- from
helpviewer_keywords:
- from clause [C#]
- from keyword [C#]
ms.assetid: 1aefd18c-1314-47f8-99ec-9bcefb09e699
ms.openlocfilehash: 388b9c0245b112d619fc173f6019b3f7dbf59940
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75715284"
---
# <a name="from-clause-c-reference"></a>Clausola from (Riferimento C#)

Un'espressione di query deve iniziare con una clausola `from`. Inoltre, un'espressione di query può contenere sottoquery che iniziano anch'esse con una clausola `from`. La clausola `from` specifica gli elementi seguenti:

- Origine dati su cui verrà eseguita la query o la sottoquery.

- *Variabile di intervallo* locale che rappresenta ogni elemento nella sequenza di origine.

Sia la variabile di intervallo che l'origine dati sono fortemente tipizzate. L'origine dati a cui si fa riferimento nella clausola `from` deve essere di tipo <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601> o di un tipo derivato, <xref:System.Linq.IQueryable%601>.

Nell'esempio seguente `numbers` è l'origine dati e `num` è la variabile di intervallo. Si noti che entrambe le variabili sono fortemente tipizzate anche se viene usata la parola chiave [var](var.md).

[!code-csharp[cscsrefQueryKeywords#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/From.cs#1)]

## <a name="the-range-variable"></a>Variabile di intervallo

Tramite l'inferenza, il compilatore deriva il tipo della variabile di intervallo quando l'origine dati implementa <xref:System.Collections.Generic.IEnumerable%601>. Se, ad esempio, l'origine è di tipo `IEnumerable<Customer>`, la variabile di intervallo derivata tramite inferenza sarà `Customer`. È necessario specificare il tipo in modo esplicito solo quando l'origine è un tipo `IEnumerable` non generico, ad esempio <xref:System.Collections.ArrayList>. Per ulteriori informazioni, vedere [come eseguire una query su un ArrayList con LINQ](../../programming-guide/concepts/linq/how-to-query-an-arraylist-with-linq.md).

Nell'esempio precedente si deriva tramite inferenza che `num` è di tipo `int`. Poiché la variabile di intervallo è fortemente tipizzata, è possibile chiamare metodi su di essa o usarla in altre operazioni. Ad esempio, invece di scrivere `select num`, è possibile scrivere `select num.ToString()` per fare in modo che l'espressione di query restituisca una sequenza di stringhe invece che di numeri interi. Oppure è possibile scrivere `select num + 10` per fare in modo che l'espressione restituisca la sequenza 14, 11, 13, 12 10. Per altre informazioni, vedere [Clausola select](select-clause.md).

La variabile di intervallo è analoga a una variabile di iterazione in un'istruzione [foreach](foreach-in.md) eccetto che per una differenza molto importante: una variabile di intervallo non archivia effettivamente mai i dati dall'origine. Si tratta semplicemente di un pratico aspetto sintattico che consente alla query di descrivere ciò che si verificherà alla sua esecuzione. Per altre informazioni, vedere [Introduzione alle query LINQ (C#)](../../programming-guide/concepts/linq/introduction-to-linq-queries.md).

## <a name="compound-from-clauses"></a>Clausole from composte

In alcuni casi, ogni elemento nella sequenza di origine può essere esso stesso una sequenza o contenere una sequenza. Ad esempio, l'origine dati può essere un oggetto `IEnumerable<Student>` in cui ogni oggetto studente della sequenza contiene un elenco di punteggi dei test. Per accedere all'elenco interno in ogni elemento `Student` è possibile usare clausole `from` composte. La tecnica è analoga all'uso di istruzioni [foreach](foreach-in.md) nidificate. È possibile aggiungere clausole [where](partial-method.md) o [orderby](orderby-clause.md) a una delle due clausole `from` per filtrare i risultati. L'esempio seguente mostra una sequenza di oggetti `Student`, ognuno dei quali contiene un oggetto `List` interno di numeri interi che rappresentano i punteggi dei test. Per accedere all'elenco interno, usare una clausola `from` composta. Se necessario, è possibile inserire clausole tra le due clausole `from`.

[!code-csharp[cscsrefQueryKeywords#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/From.cs#2)]

## <a name="using-multiple-from-clauses-to-perform-joins"></a>Uso di più clausole from per eseguire join

Una clausola `from` composta viene usata per accedere a raccolte interne in una singola origine dati. Una query può tuttavia contenere anche più clausole `from` che generano query supplementari da origini dati indipendenti. Questa tecnica consente di eseguire determinati tipi di operazioni di join che non sono possibili usando la [clausola join](join-clause.md).

L'esempio seguente mostra in che modo due clausole `from` possono essere usate per formare un cross join completo di due origini dati.

[!code-csharp[cscsrefQueryKeywords#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/From.cs#3)]

Per altre informazioni sulle operazioni di join che usano più clausole `from`, vedere [Eseguire left outer join](../../linq/perform-left-outer-joins.md).

## <a name="see-also"></a>Vedere anche

- [Parole chiave di query (LINQ)](query-keywords.md)
- [LINQ (Language-Integrated Query)](../../linq/index.md)

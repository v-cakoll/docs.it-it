---
title: Eseguire join raggruppati (LINQ in C#)
description: Informazioni su come eseguire join raggruppati usando LINQ in C#.
ms.date: 12/01/2016
ms.assetid: 9667daf9-a5fd-4b43-a5c4-a9c2b744000e
ms.openlocfilehash: dfb75b55336d8ca486d5f10b187e955d20cd06fd
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "61689138"
---
# <a name="perform-grouped-joins"></a>Eseguire join raggruppati

Il join di gruppo è utile per produrre strutture di dati gerarchiche. Abbina ogni elemento della prima raccolta con un set di elementi correlati della seconda raccolta.

Ad esempio, una classe o una tabella di database relazionale denominata `Student` potrebbe contenere due campi: `Id` e `Name`. Un'altra classe o tabella di database relazionale denominata `Course` potrebbe contenere due campi: `StudentId` e `CourseTitle`. Un join di gruppo di queste due origini dati, basato sulla corrispondenza di `Student.Id` e `Course.StudentId` raggrupperebbe ogni `Student` con una raccolta di oggetti `Course` (che può essere vuota).

> [!NOTE]
> Ogni elemento della prima raccolta viene visualizzato nel set di risultati di un join di gruppo indipendentemente dal fatto che gli elementi correlati vengano trovati nella seconda raccolta. Nel caso in cui non venga trovato alcun elemento correlato, la sequenza di elementi correlati per l'elemento è vuota. Il selettore del risultato ha pertanto accesso a ogni elemento della prima raccolta. È diverso dal selettore del risultato in un join non di gruppo, che non può accedere a elementi della prima raccolta che non hanno corrispondenza nella seconda raccolta.

Il primo esempio in questo articolo illustra come eseguire un join di gruppo. Il secondo esempio descrive come usare un join di gruppo per creare elementi XML.

## <a name="example---group-join"></a>Esempio - Join di gruppo

L'esempio seguente esegue un join di gruppo di oggetti di tipo `Person` e `Pet` basato su `Person` corrispondente alla proprietà `Pet.Owner`. Diversamente da un join non di gruppo che produrrebbe una coppia di elementi per ogni corrispondenza, il join di gruppo produce un solo oggetto risultante per ogni elemento della prima raccolta, che in questo esempio è un oggetto `Person`. Gli elementi corrispondenti della seconda raccolta, che in questo esempio sono oggetti `Pet` vengono raggruppati in una raccolta. La funzione del selettore del risultato crea infine un tipo anonimo per ogni corrispondenza costituita da `Person.FirstName` e una raccolta di oggetti `Pet`.

[!code-csharp[CsLINQProgJoining#5](~/samples/snippets/csharp/concepts/linq/how-to-perform-grouped-joins_1.cs)]

## <a name="example---group-join-to-create-xml"></a>Esempio - Join di gruppo per la creazione di XML

I join di gruppo sono ideali per la creazione di XML tramite LINQ to XML. L'esempio seguente è simile a quello precedente tranne per il fatto che, invece di creare tipi anonimi, la funzione del selettore del risultato crea elementi XML che rappresentano gli oggetti uniti in join.

[!code-csharp[CsLINQProgJoining#6](~/samples/snippets/csharp/concepts/linq/how-to-perform-grouped-joins_2.cs)]

## <a name="see-also"></a>Vedere anche

- <xref:System.Linq.Enumerable.Join%2A>
- <xref:System.Linq.Enumerable.GroupJoin%2A>
- [Eseguire inner join](perform-inner-joins.md)
- [Eseguire outer join a sinistra](perform-left-outer-joins.md)
- [Tipi anonimi](../programming-guide/classes-and-structs/anonymous-types.md)

---
title: Proprietà dell'interfaccia - Guida per programmatori C#
description: Le proprietà possono essere dichiarate in un'interfaccia in C#. In questo esempio viene dichiarata una funzione di accesso della proprietà di interfaccia.
ms.date: 01/31/2020
helpviewer_keywords:
- properties [C#], on interfaces
- interfaces [C#], properties
ms.assetid: 6503e9ed-33d7-44ec-b4c1-cc16c084b795
ms.openlocfilehash: 920381ae804a6a968bfd667171269377f3d7e448
ms.sourcegitcommit: 3d84eac0818099c9949035feb96bbe0346358504
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/21/2020
ms.locfileid: "86864969"
---
# <a name="interface-properties-c-programming-guide"></a>Proprietà dell'interfaccia (Guida per programmatori C#)

Le proprietà possono essere dichiarate su una [interfaccia](../../language-reference/keywords/interface.md). Nell'esempio seguente viene dichiarata una funzione di accesso alla proprietà di interfaccia:

[!code-csharp[DeclareProperties](~/samples/snippets/csharp/interfaces/properties.cs#DeclareInterfaceProperties)]

Le proprietà dell'interfaccia in genere non dispongono di un corpo. Le funzioni di accesso indicano se la proprietà è di lettura/scrittura, di sola lettura o di sola scrittura. Diversamente dalle classi e dagli struct, la dichiarazione delle funzioni di accesso senza un corpo non dichiara una [proprietà implementata automaticamente](auto-implemented-properties.md). A partire da C# 8,0, un'interfaccia può definire un'implementazione predefinita per i membri, incluse le proprietà. La definizione di un'implementazione predefinita per una proprietà in un'interfaccia è rara poiché le interfacce potrebbero non definire campi dati dell'istanza.

## <a name="example"></a>Esempio

Nell'esempio seguente l'interfaccia `IEmployee` include una proprietà in lettura-scrittura, `Name`, e una proprietà in sola lettura, `Counter`. La classe `Employee` implementa l'interfaccia `IEmployee` e usa le due proprietà. Il programma legge il nome di un nuovo dipendente e il numero corrente di dipendenti e quindi visualizza il nome del dipendente e il relativo numero calcolato.

È possibile usare il nome completo della proprietà, che fa riferimento all'interfaccia in cui il membro è dichiarato. ad esempio:

[!code-csharp[ExplicitProperties](~/samples/snippets/csharp/interfaces/properties.cs#ExplicitImplementation)]

Nell'esempio precedente viene illustrata l' [implementazione esplicita dell'interfaccia](../interfaces/explicit-interface-implementation.md). Se la classe `Employee` implementa, ad esempio, due interfacce, `ICitizen` e `IEmployee`, ed entrambe le interfacce includono la proprietà `Name`, sarà necessaria l'implementazione esplicita del membro dell'interfaccia. In altre parole, la dichiarazione di proprietà seguente:

[!code-csharp[ExplicitProperties](~/samples/snippets/csharp/interfaces/properties.cs#ExplicitImplementation)]

implementa la proprietà `Name` nell'interfaccia `IEmployee`, mentre la dichiarazione seguente:

[!code-csharp[ExplicitProperties](~/samples/snippets/csharp/interfaces/properties.cs#CitizenImplementation)]

implementa la proprietà `Name` nell'interfaccia `ICitizen`.

[!code-csharp[Example](~/samples/snippets/csharp/interfaces/properties.cs#PropertyExample)]
[!code-csharp[Example](~/samples/snippets/csharp/interfaces/properties.cs#UseProperty)]

**`210 Hazem Abolrous`**

## <a name="sample-output"></a>Output di esempio

```console
Enter number of employees: 210
Enter the name of the new employee: Hazem Abolrous
The employee information:
Employee number: 211
Employee name: Hazem Abolrous
```

## <a name="see-also"></a>Vedi anche

- [Guida per programmatori C#](../index.md)
- [Proprietà](./properties.md)
- [Utilizzo delle proprietà](./using-properties.md)
- [Confronto tra proprietà e indicizzatori](../indexers/comparison-between-properties-and-indexers.md)
- [Indicizzatori](../indexers/index.md)
- [Interfacce](../interfaces/index.md)

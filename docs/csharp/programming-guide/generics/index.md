---
title: Generics - Guida per programmatori C#
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, generics
- generics [C#]
ms.assetid: 75ea8509-a4ea-4e7a-a2b3-cf72482e9282
ms.openlocfilehash: c7252180c9c98a8ca99c8cc6b3faaf8b1b8f0749
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "79167492"
---
# <a name="generics-c-programming-guide"></a>Generics (Guida per programmatori C#)

I generics introducono il concetto di parametri di tipo in .NET Framework, che consentono di progettare classi e metodi che rinviano la specifica di uno o più tipi fino a quando la classe o il metodo non viene dichiarata e creata un'istanza dal codice client. Ad esempio, utilizzando un `T`parametro di tipo generico , è possibile scrivere una singola classe che può essere utilizzata da altro codice client senza incorrere nel costo o nel rischio di eseguire cast di runtime o operazioni di boxing, come illustrato di seguito:

[!code-csharp[csProgGuideGenerics#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#1)]

Le classi e i metodi generici combinano riusabilità, indipendenza dai tipi ed efficienza in un modo che le loro controparti non generiche non possono. I generics sono in genere usati con le raccolte e i metodi che operano su di essi. Lo <xref:System.Collections.Generic> spazio dei nomi contiene diverse classi di raccolte basate su generici. Le raccolte non generiche, ad <xref:System.Collections.ArrayList> esempio non sono consigliate e vengono mantenute per motivi di compatibilità. Per altre informazioni, vedere [Generics in .NET](../../../standard/generics/index.md).

Naturalmente, è anche possibile creare tipi e metodi generici personalizzati per offrire le proprie soluzioni e schemi progettuali generalizzati che sono indipendenti dai tipi ed efficienti. Nell'esempio di codice riportato di seguito viene illustrata una classe di elenco collegato generica semplice a scopo dimostrativo. Nella maggior parte dei casi, è consigliabile utilizzare la <xref:System.Collections.Generic.List%601> classe fornita dalla libreria di classi .NET Framework anziché crearne una personalizzata. Il parametro `T` type viene utilizzato in diverse posizioni in cui un tipo concreto viene in genere utilizzato per indicare il tipo di elemento archiviato nell'elenco. In particolare, viene usato nei seguenti modi:

- Come tipo di un parametro del metodo nel metodo `AddHead`.
- Come tipo restituito della proprietà `Data` nella classe `Node` annidata.
- Come tipo del membro privato `data` nella classe annidata.

 Si `T` noti che `Node` è disponibile per la classe annidata. Quando si crea un'istanza di `GenericList<T>` con un tipo concreto, ad esempio `GenericList<int>`, ogni occorrenza di `T` verrà sostituita con `int`.

[!code-csharp[csProgGuideGenerics#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#2)]

Nell'esempio di codice riportato di seguito viene illustrato come il codice client usa la classe generica `GenericList<T>` per creare un elenco di interi. Cambiando semplicemente l'argomento relativo al tipo, è possibile modificare il codice riportato di seguito per creare elenchi di stringhe o di qualsiasi altro tipo personalizzato:

[!code-csharp[csProgGuideGenerics#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#3)]

## <a name="generics-overview"></a>Panoramica dei generici

- Usare i tipi generici per ottimizzare il riutilizzo del codice, l'indipendenza dai tipi e le prestazioni.
- L'uso più comune dei generics consiste nel creare classi di raccolte.
- La libreria di classi .NET Framework contiene diverse nuove classi di raccolte generiche nello spazio dei nomi <xref:System.Collections.Generic>. Queste classi devono essere usate ogni volta che sia possibile al posto di classi come <xref:System.Collections.ArrayList> nello spazio dei nomi <xref:System.Collections>.
- È possibile creare interfacce, classi, metodi, eventi e delegati generici personalizzati.
- Le classi generiche possono essere limitate in modo da abilitare l'accesso ai metodi per particolari tipi di dati.
- Le informazioni sui tipi usati in un tipo di dati generico possono essere ottenute usando la reflection in fase di esecuzione.

## <a name="related-sections"></a>Sezioni correlate

- [Parametri di tipo generico](generic-type-parameters.md)
- [Vincoli sui parametri di tipo](constraints-on-type-parameters.md)
- [Classi genericheGeneric Classes](generic-classes.md)
- [Interfacce generiche](generic-interfaces.md)
- [Metodi Generic](generic-methods.md)
- [Delegati generici](generic-delegates.md)
- [Differenze tra modelli C++ e generics C#](differences-between-cpp-templates-and-csharp-generics.md)
- [Generics e reflection](generics-and-reflection.md)
- [Generics in fase di esecuzione](generics-in-the-run-time.md)

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

Per ulteriori informazioni, vedere la [specifica del linguaggio C .](~/_csharplang/spec/types.md#constructed-types)

## <a name="see-also"></a>Vedere anche

- <xref:System.Collections.Generic>
- [Guida per programmatori C#](../index.md)
- [Tipi](../types/index.md)
- [\<>typeparam](../xmldoc/typeparam.md)
- [\<>typeparamref](../xmldoc/typeparamref.md)
- [Generics in .NET](../../../standard/generics/index.md)

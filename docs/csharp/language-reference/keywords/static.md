---
title: Modificatore static - Riferimenti per C#
ms.date: 01/22/2020
f1_keywords:
- static
- static_CSharpKeyword
helpviewer_keywords:
- static keyword [C#]
ms.assetid: 5509e215-2183-4da3-bab4-6b7e607a4fdf
ms.openlocfilehash: e7671e9db488a7b50f4ed736864d6fa8d95eef1a
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744656"
---
# <a name="static-c-reference"></a>static (Riferimenti per C#)

Usare il modificatore `static` per dichiarare un membro statico, che appartiene allo stesso tipo invece che a un oggetto specifico. È possibile utilizzare il modificatore `static` per dichiarare classi `static`. In classi, interfacce e struct è possibile aggiungere il modificatore `static` a campi, metodi, proprietà, operatori, eventi e costruttori. Impossibile utilizzare il modificatore `static` con gli indicizzatori o i finalizzatori. Per altre informazioni, vedere [Classi statiche e membri di classi statiche](../../programming-guide/classes-and-structs/static-classes-and-static-class-members.md).

## <a name="example"></a>Esempio

La classe seguente viene dichiarata come `static` e contiene solo metodi `static`:

[!code-csharp[csrefKeywordsModifiers#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#18)]

Una costante o una dichiarazione di tipo è implicitamente un membro `static`. Non è possibile fare riferimento A un membro `static` tramite un'istanza. Al contrario, viene fatto riferimento tramite il nome del tipo. Si consideri ad esempio la classe seguente:

[!code-csharp[csrefKeywordsModifiers#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#19)]

Per fare riferimento al `x``static` membri, utilizzare il nome completo, `MyBaseC.MyStruct.x`, a meno che il membro non sia accessibile dallo stesso ambito:

```csharp
Console.WriteLine(MyBaseC.MyStruct.x);
```

Mentre un'istanza di una classe contiene una copia separata di tutti i campi di istanza della classe, è presente una sola copia di ogni campo `static`.

Non è possibile usare [`this`](this.md) per fare riferimento a `static` metodi o alle funzioni di accesso alle proprietà.

Se la parola chiave `static` viene applicata a una classe, tutti i membri della classe devono essere `static`.

Classi, interfacce e classi di `static` possono avere costruttori di `static`. Un costruttore di `static` viene chiamato in un determinato punto tra l'avvio del programma e la creazione di un'istanza della classe.

> [!NOTE]
> La parola chiave `static` ha un uso più limitato rispetto a C++. Per un confronto con la parola chiave di C++, vedere [Classi di archiviazione (C++)](/cpp/cpp/storage-classes-cpp#static).

Per illustrare i membri `static`, prendere in considerazione una classe che rappresenta un dipendente della società. Si supponga che la classe contenga un metodo di conteggio dei dipendenti e un campo per memorizzare il numero dei dipendenti. Sia il metodo che il campo non appartengono ad alcuna istanza di un dipendente. Appartengono invece alla classe di dipendenti nel suo complesso. Devono essere dichiarati come membri `static` della classe.

## <a name="example"></a>Esempio

Questo esempio legge il nome e l'ID di un nuovo dipendente, il contatore dipendente viene incrementato di uno e vengono visualizzate le informazioni per il nuovo dipendente e il nuovo numero di dipendenti. Questo programma legge il numero corrente di dipendenti dalla tastiera.

[!code-csharp[csrefKeywordsModifiers#20](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#20)]  

## <a name="example"></a>Esempio

Questo esempio mostra che è possibile inizializzare un campo di `static` usando un altro campo `static` non ancora dichiarato. I risultati non saranno definiti fino a quando non si assegna in modo esplicito un valore al campo `static`.

[!code-csharp[csrefKeywordsModifiers#21](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#21)]  

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../index.md)
- [Guida per programmatori C#](../../programming-guide/index.md)
- [Parole chiave di C#](index.md)
- [Modificatori](index.md)
- [Classi statiche e membri di classi statiche](../../programming-guide/classes-and-structs/static-classes-and-static-class-members.md)

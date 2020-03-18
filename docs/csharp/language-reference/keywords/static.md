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
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "76744656"
---
# <a name="static-c-reference"></a>static (Riferimenti per C#)

Usare il modificatore `static` per dichiarare un membro statico, che appartiene allo stesso tipo invece che a un oggetto specifico. Il `static` modificatore può `static` essere utilizzato per dichiarare le classi. Nelle classi, interfacce e struct è `static` possibile aggiungere il modificatore a campi, metodi, proprietà, operatori, eventi e costruttori. Il `static` modificatore non può essere utilizzato con gli indicizzatori o i finalizzatori. Per ulteriori informazioni, vedere [Classi statiche e Membri di classi statiche](../../programming-guide/classes-and-structs/static-classes-and-static-class-members.md).

## <a name="example"></a>Esempio

La classe seguente viene dichiarata come `static` e contiene solo metodi `static`:

[!code-csharp[csrefKeywordsModifiers#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#18)]

Una dichiarazione di tipo `static` o costante è implicitamente un membro. Non `static` è possibile fare riferimento a un membro tramite un'istanza. Al contrario, viene fatto riferimento tramite il nome del tipo. Si consideri ad esempio la classe seguente:

[!code-csharp[csrefKeywordsModifiers#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#19)]

Per fare `static` riferimento `x`al membro , `MyBaseC.MyStruct.x`utilizzare il nome completo, , a meno che il membro non sia accessibile dallo stesso ambito:

```csharp
Console.WriteLine(MyBaseC.MyStruct.x);
```

Mentre un'istanza di una classe contiene una copia separata di tutti i `static` campi di istanza della classe, è disponibile una sola copia di ogni campo.

Non è possibile usare [`this`](this.md) metodi `static` di riferimento o funzioni di accesso alle proprietà.

Se `static` la parola chiave viene applicata a una `static`classe, tutti i membri della classe devono essere .

Le classi, le `static` interfacce `static` e le classi possono avere costruttori. Un `static` costruttore viene chiamato a un certo punto tra l'avvio del programma e la classe viene creata un'istanza.

> [!NOTE]
> La parola chiave `static` ha un uso più limitato rispetto a C++. Per un confronto con la parola chiave di C++, vedere [Classi di archiviazione (C++)](/cpp/cpp/storage-classes-cpp#static).

Per `static` illustrare i membri, prendere in considerazione una classe che rappresenta un dipendente dell'azienda. Si supponga che la classe contenga un metodo di conteggio dei dipendenti e un campo per memorizzare il numero dei dipendenti. Sia il metodo che il campo non appartengono a nessuna istanza del dipendente. Appartengono invece alla classe dei dipendenti nel suo complesso. Devono essere dichiarati come `static` membri della classe.

## <a name="example"></a>Esempio

Questo esempio legge il nome e l'ID di un nuovo dipendente, il contatore dipendente viene incrementato di uno e vengono visualizzate le informazioni per il nuovo dipendente e il nuovo numero di dipendenti. Questo programma legge il numero corrente di dipendenti dalla tastiera.

[!code-csharp[csrefKeywordsModifiers#20](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#20)]  

## <a name="example"></a>Esempio

In questo esempio viene `static` illustrato che `static` è possibile inizializzare un campo utilizzando un altro campo non ancora dichiarato. I risultati rimarranno indefiniti fino a `static` quando non si assegna esplicitamente un valore al campo.

[!code-csharp[csrefKeywordsModifiers#21](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#21)]  

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Vedere anche

- [Guida di riferimento a C](../index.md)
- [Guida per programmatori C#](../../programming-guide/index.md)
- [Parole chiave di C#](index.md)
- [Modificatori](index.md)
- [Classi statiche e membri di classi statiche](../../programming-guide/classes-and-structs/static-classes-and-static-class-members.md)

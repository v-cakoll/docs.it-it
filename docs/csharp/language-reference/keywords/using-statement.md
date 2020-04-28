---
title: Istruzione using - Riferimenti per C#
ms.date: 04/07/2020
helpviewer_keywords:
- using statement [C#]
ms.assetid: afc355e6-f0b9-4240-94dd-0d93f17d9fc3
ms.openlocfilehash: 3c479faeeb66865b8c368edba881429a7cb956ec
ms.sourcegitcommit: 5988e9a29cedb8757320817deda3c08c6f44a6aa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2020
ms.locfileid: "82199677"
---
# <a name="using-statement-c-reference"></a>Istruzione using (Riferimenti per C#)

Offre una comoda sintassi che verifica l'uso corretto degli oggetti <xref:System.IDisposable>. A partire da C# 8,0, `using` l'istruzione assicura l'uso corretto <xref:System.IAsyncDisposable> degli oggetti.

## <a name="example"></a>Esempio

L'esempio seguente mostra come usare l'istruzione `using`.

:::code language="csharp" source="snippets/usings.cs" id="SnippetFirstExample":::

A partire da C# 8,0, è possibile usare la sintassi alternativa seguente per `using` l'istruzione che non richiede parentesi graffe:

:::code language="csharp" source="snippets/usings.cs" id="SnippetModernUsing":::

## <a name="remarks"></a>Osservazioni

<xref:System.IO.File> e <xref:System.Drawing.Font> sono esempi di tipi gestiti che accedono a risorse non gestite (in questo caso handle di file e contesti di dispositivo). Esistono molti altri tipi di risorse non gestite e tipi della libreria di classi che le incapsulano. Tutti questi tipi devono implementare l' <xref:System.IDisposable> interfaccia o l' <xref:System.IAsyncDisposable> interfaccia.

Quando la durata di un oggetto `IDisposable` è limitata a un singolo metodo, è necessario dichiararlo e creare un'istanza nell'istruzione `using`. L'istruzione `using` chiama il metodo <xref:System.IDisposable.Dispose%2A> sull'oggetto in modo corretto e, quando viene usata come illustrato in precedenza, fa in modo che l'oggetto stesso esca dall'ambito non appena viene chiamato il metodo <xref:System.IDisposable.Dispose%2A>. All'interno `using` del blocco l'oggetto è di sola lettura e non può essere modificato o riassegnato. Se l'oggetto implementa `IAsyncDisposable` anziché `IDisposable`, l' `using` istruzione chiama <xref:System.IAsyncDisposable.DisposeAsync%2A> e `awaits` l'oggetto restituito. <xref:System.Threading.Tasks.Task>

L' `using` istruzione garantisce che <xref:System.IDisposable.Dispose%2A> (o <xref:System.IAsyncDisposable.DisposeAsync%2A>) venga chiamato anche se si verifica un'eccezione all' `using` interno del blocco. È possibile ottenere lo stesso risultato inserendo l'oggetto all'interno di `try` un blocco e chiamando <xref:System.IDisposable.Dispose%2A> (o <xref:System.IAsyncDisposable.DisposeAsync%2A>) in un `finally` blocco; in realtà, questo è il modo `using` in cui l'istruzione viene convertita dal compilatore. L'esempio di codice precedente si espande al codice seguente in fase di compilazione (si notino le parentesi graffe aggiuntive per creare l'ambito limitato per l'oggetto):

:::code language="csharp" source="snippets/usings.cs" id="SnippetTryFinallyExample":::

La sintassi `using` dell'istruzione più recente si traduce in codice simile. Il `try` blocco viene aperto in cui viene dichiarata la variabile. Il `finally` blocco viene aggiunto alla chiusura del blocco di inclusione, in genere alla fine di un metodo.

Per ulteriori `try` - `finally` informazioni sull'istruzione, vedere l'articolo [try-finally](try-finally.md) .

Più istanze di un tipo possono essere dichiarate in `using` una singola istruzione, come illustrato nell'esempio seguente. Si noti che non è possibile usare variabili tipizzate`var`in modo implicito () quando si dichiarano più variabili in un'unica istruzione:

:::code language="csharp" source="snippets/usings.cs" id="SnippetDeclareMultipleVariables":::

È possibile combinare più dichiarazioni dello stesso tipo usando la nuova sintassi introdotta anche con C# 8, come illustrato nell'esempio seguente:

:::code language="csharp" source="snippets/usings.cs" id="SnippetModernMultipleVariables":::

È possibile creare un'istanza dell'oggetto risorsa e quindi passare la variabile all' `using` istruzione, ma questa non è una procedura consigliata. In questo caso l'oggetto rimane nell'ambito quando il controllo lascia il blocco `using`, anche se probabilmente non avrà più accesso alle relative risorse non gestite. In altre parole, non è più completamente inizializzato. Se si tenta di usare l'oggetto di fuori del blocco `using`, si rischia di causare la generazione di un'eccezione. Per questo motivo, è preferibile creare un'istanza dell'oggetto nell' `using` istruzione e limitarne l'ambito al `using` blocco.

:::code language="csharp" source="snippets/usings.cs" id="SnippetDeclareBeforeUsing":::

Per altre informazioni sull'eliminazione degli oggetti `IDisposable`, vedere [Uso di oggetti che implementano IDisposable](../../../standard/garbage-collection/using-objects.md).

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

Per altre informazioni, vedere [Istruzione using](~/_csharplang/spec/statements.md#the-using-statement) nella [specifica del linguaggio C#](/dotnet/csharp/language-reference/language-specification/introduction). La specifica del linguaggio costituisce il riferimento ufficiale principale per la sintassi e l'uso di C#.

## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../index.md)
- [Guida per programmatori C#](../../programming-guide/index.md)
- [Parole chiave di C#](index.md)
- [Direttiva using](using-directive.md)
- [Garbage Collection](../../../standard/garbage-collection/index.md)
- [Uso di oggetti che implementano IDisposable](../../../standard/garbage-collection/using-objects.md)
- [Interfaccia IDisposable](xref:System.IDisposable)
- [istruzione using in C# 8,0](~/_csharplang/proposals/csharp-8.0/using.md)

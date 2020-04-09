---
title: Istruzione using - Riferimenti per C#
ms.date: 04/07/2020
helpviewer_keywords:
- using statement [C#]
ms.assetid: afc355e6-f0b9-4240-94dd-0d93f17d9fc3
ms.openlocfilehash: a237a90b4782e0460857c3d5d887771bcc8ccaaf
ms.sourcegitcommit: e3cbf26d67f7e9286c7108a2752804050762d02d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2020
ms.locfileid: "80989181"
---
# <a name="using-statement-c-reference"></a>Istruzione using (Riferimenti per C#)

Offre una comoda sintassi che verifica l'uso corretto degli oggetti <xref:System.IDisposable>. A partire dalla versione 8.0 di C, l'istruzione `using` garantisce l'utilizzo corretto degli <xref:System.IAsyncDisposable> oggetti.

## <a name="example"></a>Esempio

L'esempio seguente mostra come usare l'istruzione `using`.

:::code language="csharp" source="snippets/usings.cs" id="SnippetFirstExample":::

A partire dalla versione 8.0 di C, `using` è possibile usare la sintassi alternativa seguente per l'istruzione che non richiede parentesi graffe:

:::code language="csharp" source="snippets/usings.cs" id="SnippetModernUsing":::

## <a name="remarks"></a>Osservazioni

<xref:System.IO.File> e <xref:System.Drawing.Font> sono esempi di tipi gestiti che accedono a risorse non gestite (in questo caso handle di file e contesti di dispositivo). Esistono molti altri tipi di risorse non gestite e tipi della libreria di classi che le incapsulano. Tutti questi tipi <xref:System.IDisposable> devono implementare <xref:System.IAsyncDisposable> l'interfaccia o l'interfaccia.

Quando la durata di un oggetto `IDisposable` è limitata a un singolo metodo, è necessario dichiararlo e creare un'istanza nell'istruzione `using`. L'istruzione `using` chiama il metodo <xref:System.IDisposable.Dispose%2A> sull'oggetto in modo corretto e, quando viene usata come illustrato in precedenza, fa in modo che l'oggetto stesso esca dall'ambito non appena viene chiamato il metodo <xref:System.IDisposable.Dispose%2A>. All'interno del `using` blocco, l'oggetto è di sola lettura e non può essere modificato o riassegnato. Se `IAsyncDisposable` l'oggetto `IDisposable`implementa `using` anziché <xref:System.IAsyncDisposable.DisposeAsync%2A> , `awaits` l'istruzione chiama e viene restituito <xref:System.Threading.Tasks.Task>.

L'istruzione `using` garantisce che <xref:System.IDisposable.Dispose%2A> (o <xref:System.IAsyncDisposable.DisposeAsync%2A>) venga chiamato `using` anche se si verifica un'eccezione all'interno del blocco. È possibile ottenere lo stesso risultato `try` inserendo l'oggetto all'interno di un blocco e quindi <xref:System.IDisposable.Dispose%2A> chiamando (o <xref:System.IAsyncDisposable.DisposeAsync%2A> in un `finally` blocco; infatti, questo è il modo in cui l'istruzione `using` viene convertita dal compilatore. L'esempio di codice precedente si espande al codice seguente in fase di compilazione (si notino le parentesi graffe aggiuntive per creare l'ambito limitato per l'oggetto):

:::code language="csharp" source="snippets/usings.cs" id="SnippetTryFinallyExample":::

La sintassi dell'istruzione più recente `using` viene convertita in codice simile. Il `try` blocco si apre dove viene dichiarata la variabile. Il `finally` blocco viene aggiunto alla chiusura del blocco di inclusione, in genere alla fine di un metodo.

Per altre informazioni `try` - `finally` sull'istruzione, vedere l'articolo [try-finally.](try-finally.md)

È possibile dichiarare più istanze `using` di un tipo in una singola istruzione, come illustrato nell'esempio seguente. Si noti che non è possibile`var`utilizzare variabili tipizzate in modo implicito ( ) quando si dichiarano più variabili in una singola istruzione:Notice that you can't use implicitly typed variables ( ) when you declare multiple variables in a single statement:

:::code language="csharp" source="snippets/usings.cs" id="SnippetDeclareMultipleVariables":::

È possibile combinare più dichiarazioni dello stesso tipo usando anche la nuova sintassi introdotta con C .

:::code language="csharp" source="snippets/usings.cs" id="SnippetModernMultipleVariables":::

È possibile creare un'istanza dell'oggetto `using` risorsa e quindi passare la variabile all'istruzione, ma questa non è una procedura consigliata. In questo caso l'oggetto rimane nell'ambito quando il controllo lascia il blocco `using`, anche se probabilmente non avrà più accesso alle relative risorse non gestite. In altre parole, non è più completamente inizializzato. Se si tenta di usare l'oggetto di fuori del blocco `using`, si rischia di causare la generazione di un'eccezione. Per questo motivo, è preferibile creare `using` un'istanza dell'oggetto nell'istruzione e limitarne l'ambito `using` al blocco.

:::code language="csharp" source="snippets/usings.cs" id="SnippetDeclareBeforeUsing":::

Per altre informazioni sull'eliminazione degli oggetti `IDisposable`, vedere [Uso di oggetti che implementano IDisposable](../../../standard/garbage-collection/using-objects.md).

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

Per altre informazioni, vedere [Istruzione using](~/_csharplang/spec/statements.md#the-using-statement) nella [specifica del linguaggio C#](/dotnet/csharp/language-reference/language-specification/introduction). La specifica del linguaggio costituisce il riferimento ufficiale principale per la sintassi e l'uso di C#.

## <a name="see-also"></a>Vedere anche

- [Guida di riferimento a C](../index.md)
- [Guida alla programmazione in C](../../programming-guide/index.md)
- [Parole chiave di C](index.md)
- [Direttiva using](using-directive.md)
- [Garbage Collection](../../../standard/garbage-collection/index.md)
- [Uso di oggetti che implementano IDisposable](../../../standard/garbage-collection/using-objects.md)
- [Interfaccia IDisposable](xref:System.IDisposable)
- [Using (istruzione) in C .](~/_csharplang/proposals/csharp-8.0/using.md)

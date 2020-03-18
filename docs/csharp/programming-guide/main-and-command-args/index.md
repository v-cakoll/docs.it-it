---
title: Main() e argomenti della riga di comando - Guida per programmatori C#
ms.date: 08/02/2017
f1_keywords:
- CS5001
- main_CSharpKeyword
- Main
helpviewer_keywords:
- Main method [C#]
- C# language, command-line arguments
- arguments [C#], command-line
- command line [C#], arguments
- command-line arguments [C#], Main method
ms.assetid: 73a17231-cf96-44ea-aa8a-54807c6fb1f4
ms.openlocfilehash: 0571ec6dbc42f103ec922a6b2b13a52510640a78
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "75700601"
---
# <a name="main-and-command-line-arguments-c-programming-guide"></a>Main() e argomenti della riga di comando (Guida per programmatori C#)

Il metodo `Main` è il punto di ingresso di un'applicazione C#. Le librerie e i `Main` servizi non richiedono un metodo come punto di ingresso. Quando l'applicazione viene `Main` avviata, il metodo è il primo metodo che viene richiamato.

 In un programma C# può essere presente un solo punto di ingresso. Se sono presenti più classi con un metodo `Main`, è necessario compilare il programma con l'opzione del compilatore **/main** per specificare quale metodo `Main` deve essere usato come punto di ingresso. Per altre informazioni, vedere [-main (opzioni del compilatore C)](../../language-reference/compiler-options/main-compiler-option.md).

[!code-csharp[csProgGuideMain#17](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class1.cs#17)]

## <a name="overview"></a>Panoramica

- Il metodo `Main` è il punto di ingresso di un programma eseguibile, ovvero il punto in cui il controllo del programma inizia e termina.
- `Main` viene dichiarato in una classe o in un tipo struct. `Main` deve essere [static](../../language-reference/keywords/static.md) e non [public](../../language-reference/keywords/public.md). Nell'esempio precedente, riceve l'accesso predefinito di [private](../../language-reference/keywords/private.md).) Non è necessario che la classe o lo struct che lo contiene sia statico.
- Il tipo restituito da `Main` può essere `void`, `int` o, a partire da C# 7.1, `Task` o `Task<int>`.
- Se e `Main` solo `Task` se `Task<int>`restituisce `Main` o , [`async`](../../language-reference/keywords/async.md) la dichiarazione di può includere il modificatore . Si noti che questo esclude specificamente un metodo `async void Main`.
- Il metodo `Main` può essere dichiarato con o senza un parametro `string[]` contenente argomenti della riga di comando. Quando si utilizza Visual Studio per creare applicazioni Windows, <xref:System.Environment.GetCommandLineArgs> è possibile aggiungere il parametro manualmente oppure utilizzare il metodo per ottenere gli argomenti della riga di [comando.](command-line-arguments.md) I parametri vengono letti come argomenti della riga di comando a indice zero. A differenza di C e C, il nome del programma non viene `args` considerato come il primo argomento <xref:System.Environment.GetCommandLineArgs> della riga di comando nella matrice, ma è il primo elemento del metodo.

Di seguito è riportato un elenco di firme valide: `Main`

```csharp
public static void Main() { }
public static int Main() { }
public static void Main(string[] args) { }
public static int Main(string[] args) { }
public static async Task Main() { }
public static async Task<int> Main() { }
public static async Task Main(string[] args) { }
public static async Task<int> Main(string[] args) { }
```

L'aggiunta dei tipi restituiti `async`, `Task` e `Task<int>` semplifica il codice del programma quando è necessario avviare le applicazioni console e per operazioni asincrone `await` in `Main`.

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Vedere anche

- [Compilazione dalla riga di comando con csc.exe](../../language-reference/compiler-options/command-line-building-with-csc-exe.md)
- [Guida per programmatori C#](../index.md)
- [Metodi](../classes-and-structs/methods.md)
- [Contenuto di un programma C#](../inside-a-program/index.md)

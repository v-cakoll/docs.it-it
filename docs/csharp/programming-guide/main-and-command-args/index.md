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
ms.openlocfilehash: 190216b01ea416aedbca270a6d7a5acbf0c2e797
ms.sourcegitcommit: 5988e9a29cedb8757320817deda3c08c6f44a6aa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2020
ms.locfileid: "82200119"
---
# <a name="main-and-command-line-arguments-c-programming-guide"></a>Main() e argomenti della riga di comando (Guida per programmatori C#)

Il metodo `Main` è il punto di ingresso di un'applicazione C#. (Le librerie e i servizi non richiedono `Main` un metodo come punto di ingresso). Quando l'applicazione viene avviata, `Main` il metodo è il primo metodo richiamato.

 In un programma C# può essere presente un solo punto di ingresso. Se sono presenti più classi con un metodo `Main`, è necessario compilare il programma con l'opzione del compilatore **/main** per specificare quale metodo `Main` deve essere usato come punto di ingresso. Per ulteriori informazioni, vedere [-Main (opzioni del compilatore C#)](../../language-reference/compiler-options/main-compiler-option.md).

[!code-csharp[csProgGuideMain#17](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class1.cs#17)]

## <a name="overview"></a>Panoramica

- Il metodo `Main` è il punto di ingresso di un programma eseguibile, ovvero il punto in cui il controllo del programma inizia e termina.
- `Main` viene dichiarato in una classe o in un tipo struct. `Main` deve essere [static](../../language-reference/keywords/static.md) e non [public](../../language-reference/keywords/public.md). Nell'esempio precedente riceve l'accesso predefinito di [private](../../language-reference/keywords/private.md). La classe o lo struct contenitore non deve essere statico.
- Il tipo restituito da `Main` può essere `void`, `int` o, a partire da C# 7.1, `Task` o `Task<int>`.
- Se e solo se `Main` restituisce `Task` o `Task<int>`, la dichiarazione di `Main` può includere il [`async`](../../language-reference/keywords/async.md) modificatore. Si noti che questo esclude specificamente un metodo `async void Main`.
- Il metodo `Main` può essere dichiarato con o senza un parametro `string[]` contenente argomenti della riga di comando. Quando si usa Visual Studio per creare applicazioni Windows, è possibile aggiungere il parametro manualmente oppure usare il <xref:System.Environment.GetCommandLineArgs> metodo per ottenere gli [argomenti della riga di comando](command-line-arguments.md). I parametri vengono letti come argomenti della riga di comando a indice zero. Diversamente da C e C++, il nome del programma non viene trattato come primo argomento della riga di comando nella `args` matrice, ma è il primo elemento del <xref:System.Environment.GetCommandLineArgs> metodo.

Di seguito è riportato un elenco di `Main` firme valide:

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

Negli esempi precedenti viene usato il modificatore della funzione di accesso public. Tipico, ma non obbligatorio.

L'aggiunta dei tipi restituiti `async`, `Task` e `Task<int>` semplifica il codice del programma quando è necessario avviare le applicazioni console e per operazioni asincrone `await` in `Main`.

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Vedere anche

- [Compilazione dalla riga di comando con csc.exe](../../language-reference/compiler-options/command-line-building-with-csc-exe.md)
- [Guida per programmatori C#](../index.md)
- [Metodi](../classes-and-structs/methods.md)
- [All'interno di un programma C#](../inside-a-program/index.md)

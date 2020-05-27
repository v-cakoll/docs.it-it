---
title: Argomenti della riga di comando - Guida per programmatori C#
ms.date: 07/20/2015
helpviewer_keywords:
- command-line arguments [C#]
ms.assetid: 0e597e0d-ea7a-41ba-a38a-0198122f3c26
ms.openlocfilehash: c203716d9bb8298c934a999a496793c294949ddb
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007754"
---
# <a name="command-line-arguments-c-programming-guide"></a>Argomenti della riga di comando (Guida per programmatori C#)

È possibile inviare argomenti al metodo `Main` definendo il metodo in uno dei modi seguenti:

[!code-csharp[csProgGuideMain#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class3.cs#2)]  

[!code-csharp[csProgGuideMain#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class3.cs#3)]

> [!NOTE]
> Per abilitare gli argomenti della riga di comando nel `Main` metodo in una Windows Forms Application, è necessario modificare manualmente la firma di `Main` in *Program.cs*. Il codice generato da Progettazione Windows Form crea un `Main` senza un parametro di input. È anche possibile usare <xref:System.Environment.CommandLine%2A?displayProperty=nameWithType> o <xref:System.Environment.GetCommandLineArgs%2A?displayProperty=nameWithType> per accedere agli argomenti della riga di comando da qualsiasi punto in un'applicazione console o Windows.

Il parametro del metodo `Main` è una matrice <xref:System.String> che rappresenta gli argomenti della riga di comando. In genere si determina se gli argomenti esistono eseguendo il test della proprietà `Length`, ad esempio:

[!code-csharp[csProgGuideMain#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class3.cs#4)]

> [!TIP]
> La `args` matrice non può essere null. Quindi, è sicuro accedere alla `Length` proprietà senza il controllo null.

È anche possibile convertire gli argomenti stringa in tipi numerici con la classe <xref:System.Convert> o il metodo `Parse`. Ad esempio, l'istruzione seguente converte `string` in un numero `long` con il metodo <xref:System.Int64.Parse%2A>:

```csharp
long num = Int64.Parse(args[0]);
```

È anche possibile usare il tipo C# `long`, che fa da alias per `Int64`:

```csharp
long num = long.Parse(args[0]);
```

Nella classe `Convert` il metodo `ToInt64` consente di eseguire la stessa operazione:

```csharp
long num = Convert.ToInt64(s);
```

Per altre informazioni, vedere <xref:System.Int64.Parse%2A> e <xref:System.Convert>.

## <a name="example"></a>Esempio

L'esempio seguente illustra come usare gli argomenti della riga di comando in un'applicazione console. L'applicazione accetta un argomento in fase di esecuzione, lo converte in un numero intero e calcola il fattoriale del numero. Se non viene specificato nessun argomento, l'applicazione produce un messaggio che descrive l'uso corretto del programma.

Per compilare ed eseguire l'applicazione al prompt dei comandi, seguire questa procedura:

1. Incollare il codice seguente in qualsiasi editor di testo, quindi salvare il file come file di testo con il nome *Factorial.cs*.

     [!code-csharp[csProgGuideMain#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class1.cs#16)]

2. Dalla schermata **Start** o dal menu **Start**, aprire una finestra **Prompt dei comandi per gli sviluppatori** di Visual Studio e selezionare la cartella contenente il file appena creato.

3. Immettere il seguente comando per compilare l'applicazione.
  
     `csc Factorial.cs`  
  
     Se l'applicazione non presenta errori di compilazione, viene creato un file eseguibile denominato *fattoriale. exe* .
  
4. Immettere il comando seguente per calcolare il fattoriale di 3:
  
     `Factorial 3`  
  
5. Il comando produce il seguente output: `The factorial of 3 is 6.`

> [!NOTE]
> Quando si esegue un'applicazione in Visual Studio, è possibile specificare argomenti della riga di comando nella [Pagina Debug, Progettazione progetti](/visualstudio/ide/reference/debug-page-project-designer).

## <a name="see-also"></a>Vedere anche

- <xref:System.Environment?displayProperty=nameWithType>
- [Guida per programmatori C#](../index.md)
- [Main () e argomenti della riga di comando](index.md)
- [Come visualizzare gli argomenti della riga di comando](how-to-display-command-line-arguments.md)
- [Valori restituiti da Main()](main-return-values.md)
- [Classi](../classes-and-structs/classes.md)

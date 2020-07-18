---
title: Valori restituiti da Main() - Guida per programmatori C#
ms.date: 08/02/2017
helpviewer_keywords:
- Main method [C#], return values
ms.assetid: c2f5a1d8-1676-4bea-bc7e-44a97e72d5bc
ms.openlocfilehash: a3e29903448c3eb5e0b7dda027677d1785a445e7
ms.sourcegitcommit: 3492dafceb5d4183b6b0d2f3bdf4a1abc4d5ed8c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/16/2020
ms.locfileid: "86416296"
---
# <a name="main-return-values-c-programming-guide"></a>Valori restituiti da Main() (Guida per programmatori C#)

Il metodo `Main` può restituire `void`:

 [!code-csharp[csProgGuideMain#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class3.cs#12)]

Può anche restituire `int`:

 [!code-csharp[csProgGuideMain#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class3.cs#13)]

Se il valore restituito da `Main` non viene usato, la restituzione di `void` consente di semplificare leggermente il codice. Tuttavia, la restituzione di un valore intero consente al programma di comunicare le informazioni sullo stato ad altri programmi o script che richiamano il file eseguibile. Il valore restituito da `Main` viene considerato come codice di uscita per il processo. Se `void` viene restituito da `Main` , il codice di uscita sarà implicitamente `0` . L'esempio seguente illustra come è possibile accedere al valore restituito da `Main`.

## <a name="example"></a>Esempio

In questo esempio vengono usati gli strumenti da riga di comando di [.NET Core](../../../core/index.yml) . Se non si ha familiarità con gli strumenti da riga di comando di .NET Core, è possibile ottenere informazioni su di essi in questo [articolo introduttivo](../../../core/tutorials/with-visual-studio-code.md).

Convertire il metodo `Main` in *program.cs* come indicato di seguito:

 [!code-csharp[csProgGuideMain#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class3.cs#14)]

Quando si esegue un programma in ambiente Windows, qualsiasi valore restituito dalla funzione `Main` viene archiviato in una variabile di ambiente. Questa variabile di ambiente può essere recuperata mediante `ERRORLEVEL` da un file batch o mediante `$LastExitCode` da PowerShell.

È possibile compilare l'applicazione usando il comando [dotnet CLI](../../../core/tools/dotnet.md) `dotnet build`.

Quindi creare uno script di PowerShell per eseguire l'applicazione e visualizzare il risultato. Incollare il codice seguente in un file di testo e salvarlo come `test.ps1` nella cartella che contiene il progetto. Eseguire lo script di PowerShell digitando `test.ps1` al prompt di PowerShell.

Poiché il codice restituisce zero, il file batch indicherà un esito positivo. Tuttavia, se si modifica MainReturnValTest.cs per restituire un valore diverso da zero e quindi si ricompila il programma, l'esecuzione successiva dello script di PowerShell segnalerà un errore.

```dotnetcli
dotnet run
```

```powershell
if ($LastExitCode -eq 0) {
    Write-Host "Execution succeeded"
} else
{
    Write-Host "Execution Failed"
}
Write-Host "Return value = " $LastExitCode
```

## <a name="sample-output"></a>Output di esempio

```txt
Execution succeeded
Return value = 0
```

## <a name="async-main-return-values"></a>Valori restituiti da Async Main

I valori restituiti da Async Main trasferiscono il codice boilerplate necessario per la chiamata di metodi asincroni in `Main` a codice generato dal compilatore. In precedenza era necessario scrivere questo costrutto per chiamare codice asincrono e verificare che il programma rimanesse in esecuzione fino al completamento dell'operazione asincrona:

```csharp
public static void Main()
{
    AsyncConsoleWork().GetAwaiter().GetResult();
}

private static async Task<int> AsyncConsoleWork()
{
    // Main body here
    return 0;
}
```

Ora è possibile usare la sintassi seguente:

[!code-csharp[AsyncMain](../../../../samples/snippets/csharp/main-arguments/program.cs#AsyncMain)]

Il vantaggio della nuova sintassi è che il compilatore genera sempre il codice corretto.

## <a name="compiler-generated-code"></a>Codice generato dal compilatore

Quando il punto di ingresso dell'applicazione restituisce `Task` o `Task<int>` il compilatore genera un nuovo punto di ingresso che chiama il metodo del punto di ingresso dichiarato nel codice dell'applicazione. Supponendo che questo punto di ingresso sia denominato `$GeneratedMain`, il compilatore genera il codice seguente per questi punti di ingresso:

- `static Task Main()`: il compilatore produce l'equivalente di `private static void $GeneratedMain() => Main().GetAwaiter().GetResult();`
- `static Task Main(string[])`: il compilatore produce l'equivalente di `private static void $GeneratedMain(string[] args) => Main(args).GetAwaiter().GetResult();`
- `static Task<int> Main()`: il compilatore produce l'equivalente di `private static int $GeneratedMain() => Main().GetAwaiter().GetResult();`
- `static Task<int> Main(string[])`: il compilatore produce l'equivalente di `private static int $GeneratedMain(string[] args) => Main(args).GetAwaiter().GetResult();`

> [!NOTE]
>Se negli esempi si fosse usato il modificatore `async` sul metodo `Main` il compilatore avrebbe generato lo stesso codice.

## <a name="see-also"></a>Vedere anche

- [Guida per programmatori C#](../index.md)
- [Riferimenti per C#](../index.md)
- [Main () e argomenti della riga di comando](index.md)
- [Come visualizzare gli argomenti della riga di comando](./how-to-display-command-line-arguments.md)

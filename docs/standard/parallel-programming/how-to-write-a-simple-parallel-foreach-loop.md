---
title: Scrivere un semplice programma parallelo usando Parallel.ForEach
ms.date: 02/14/2019
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- foreach, parallel version
- parallel programming, foreach
ms.assetid: cb5fab92-1c19-499e-ae91-8b7525dd875f
ms.openlocfilehash: 528e22d6b54179181d1479f4feaedfbf82933c58
ms.sourcegitcommit: cdf5084648bf5e77970cbfeaa23f1cab3e6e234e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/01/2020
ms.locfileid: "76921196"
---
# <a name="how-to-write-a-simple-parallelforeach-loop"></a>Procedura: scrivere un ciclo Parallel. ForEach semplice

Questo esempio mostra come usare un ciclo <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> per abilitare il parallelismo dei dati in un'origine dati <xref:System.Collections.IEnumerable?displayProperty=nameWithType> o <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>.

> [!NOTE]
> Le espressioni lambda sono usate nella documentazione per definire i delegati in PLINQ. Se non si ha familiarità con le espressioni lambda in C# o Visual Basic, vedere [Espressioni lambda in PLINQ e TPL](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md).

## <a name="example"></a>Esempio

Questo esempio presuppone che diversi file con estensione jpg siano presenti in una cartella *C:\Users\Public\Pictures\Sample Pictures* e crea una nuova sottocartella con nome *Modified*. Quando si esegue l'esempio, il codice ruota ogni immagine con estensione jpg in *Sample Pictures* e la salva in *Modified*. È possibile modificare i due percorsi in base alle esigenze.

[!code-csharp[TPL_Parallel#03](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_parallel/cs/simpleforeach.cs#03)]
[!code-vb[TPL_Parallel#03](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_parallel/vb/simpleforeach.vb#03)]

Un ciclo <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> funziona come un ciclo <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType>. Il ciclo esegue il partizionamento della raccolta di origine e pianifica il lavoro in più thread in base all'ambiente di sistema. Più processori ci sono nel sistema, più velocemente viene eseguito il metodo parallelo. Per alcune raccolte di origine può risultare più veloce un ciclo sequenziale, a seconda delle dimensioni dell'origine e del tipo di attività svolta dal ciclo. Per ulteriori informazioni sulle prestazioni, vedere [potenziali trappole nel parallelismo di dati e attività](potential-pitfalls-in-data-and-task-parallelism.md).

Per altre informazioni sui cicli paralleli, vedere [procedura: scrivere un ciclo Parallel. for semplice](../../../docs/standard/parallel-programming/how-to-write-a-simple-parallel-for-loop.md).

Per usare <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> con una raccolta non generica, è possibile usare il metodo di estensione <xref:System.Linq.Enumerable.Cast%2A?displayProperty=nameWithType> per convertire la raccolta in una generica, come illustrato nell'esempio seguente:

[!code-csharp[TPL_Parallel#07](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_parallel/cs/nongeneric.cs#07)]
[!code-vb[TPL_Parallel#07](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_parallel/vb/nongeneric.vb#07)]

È anche possibile usare Parallel LINQ (PLINQ) per parallelizzare l'elaborazione di origini dati <xref:System.Collections.Generic.IEnumerable%601>. PLINQ consente di usare la sintassi di query dichiarativa per esprimere il comportamento di ciclo. Per altre informazioni, vedere [Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md).

## <a name="compile-and-run-the-code"></a>Compilare ed eseguire il codice

È possibile compilare il codice come applicazione console per .NET Framework o come applicazione console per .NET Core.

In Visual Studio esistono modelli di applicazione console Visual Basic e C# per Windows Desktop e .NET Core.

Dalla riga di comando è possibile usare i comandi di interfaccia della riga di comando di .NET Core, ad esempio `dotnet new console` o `dotnet new console -lang vb`, oppure è possibile creare il file e usare il compilatore da riga di comando per un'applicazione .NET Framework.

Per un progetto .NET Core è necessario fare riferimento al pacchetto NuGet **System.Drawing.Common**. In Visual Studio usare Gestione pacchetti NuGet per installare il pacchetto. In alternativa, è possibile aggiungere un riferimento al pacchetto nel file con estensione \*.csproj o \*.vbproj:
 
```xml
<ItemGroup>
     <PackageReference Include="System.Drawing.Common" Version="4.5.1" />
</ItemGroup>
```

Per eseguire un'applicazione console .NET Core dalla riga di comando, usare `dotnet run` dalla cartella che contiene l'applicazione.

Per eseguire l'applicazione console da Visual Studio, premere **F5**.

## <a name="see-also"></a>Vedere anche

- [Parallelismo dei dati](../../../docs/standard/parallel-programming/data-parallelism-task-parallel-library.md)
- [Programmazione parallela](../../../docs/standard/parallel-programming/index.md)
- [Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)

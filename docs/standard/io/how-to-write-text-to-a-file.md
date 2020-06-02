---
title: 'Procedura: scrivere testo in un file'
ms.date: 01/04/2019
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- writing text to files
- I/O [.NET Framework], writing text to files
- streams, writing text to files
- data streams, writing text to files
ms.assetid: 060cbe06-2adf-4337-9e7b-961a5c840208
ms.openlocfilehash: 395344accf5be416fbcc527e51ba83408f9c5810
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84291734"
---
# <a name="how-to-write-text-to-a-file"></a>Procedura: scrivere testo in un file
Questo argomento illustra diversi modi per scrivere testo in un file per un'app .NET.

Per scrivere un testo in un file vengono in genere usati le classi e i metodi seguenti:  
  
- <xref:System.IO.StreamWriter> contiene metodi per scrivere in un file in modo sincrono (<xref:System.IO.StreamWriter.Write%2A> e <xref:System.IO.TextWriter.WriteLine%2A>) o asincrono (<xref:System.IO.StreamWriter.WriteAsync%2A> e <xref:System.IO.StreamWriter.WriteLineAsync%2A>).  
  
- <xref:System.IO.File> specifica metodi statici per scrivere un testo in un file, ad esempio <xref:System.IO.File.WriteAllLines%2A> e <xref:System.IO.File.WriteAllText%2A> o per accodare testo a un file, ad esempio <xref:System.IO.File.AppendAllLines%2A>, <xref:System.IO.File.AppendAllText%2A> e <xref:System.IO.File.AppendText%2A>.  
  
- <xref:System.IO.Path> è destinato alle stringhe che contengono informazioni sul percorso di file o directory. Contiene il metodo <xref:System.IO.Path.Combine%2A> e in .NET Core 2.1 e versioni successive i metodi <xref:System.IO.Path.Join%2A> e <xref:System.IO.Path.TryJoin%2A>, che consentono la concatenazione di stringhe per compilare un percorso di file o directory.

> [!NOTE]
> Gli esempi seguenti visualizzano solo la quantità minima di codice necessario. Un'applicazione reale include in genere procedure di controllo degli errori e di gestione delle eccezioni più efficaci.  
  
## <a name="example-synchronously-write-text-with-streamwriter"></a>Esempio: scrivere testo in modo sincrono con StreamWriter

L'esempio seguente illustra come usare la classe <xref:System.IO.StreamWriter> per scrivere un testo in modo sincrono una riga alla volta in un nuovo file. Poiché l'oggetto <xref:System.IO.StreamWriter> viene dichiarato in un'istruzione `using` in cui viene creata anche un'istanza dell'oggetto stesso, viene chiamato il metodo <xref:System.IO.StreamWriter.Dispose%2A> che scarica e chiude automaticamente il flusso.  

[!code-csharp[Conceptual.BasicIO.TextFiles#WriteLine](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/write.cs)]
[!code-vb[Conceptual.BasicIO.TextFiles#WriteLine](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/write.vb)]  

[!INCLUDE [localized code comments](../../../includes/code-comments-loc.md)]

## <a name="example-synchronously-append-text-with-streamwriter"></a>Esempio: accodare in modo sincrono il testo con StreamWriter

L'esempio seguente illustra come usare la classe <xref:System.IO.StreamWriter> per accodare testo in modo sincrono al file di testo creato nel primo esempio.

[!code-csharp[Conceptual.BasicIO.TextFiles#WriteLine](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/append.cs)]
[!code-vb[Conceptual.BasicIO.TextFiles#WriteLine](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/append.vb)]  

## <a name="example-asynchronously-write-text-with-streamwriter"></a>Esempio: scrivere in modo asincrono un testo con StreamWriter

L'esempio seguente illustra come scrivere in modo asincrono un testo in un nuovo file usando la classe <xref:System.IO.StreamWriter> . Per chiamare il metodo <xref:System.IO.StreamWriter.WriteAsync%2A>, la chiamata al metodo deve essere inclusa in un metodo `async`. L'esempio C# richiede C# 7.1 o versioni successive, che aggiunge il supporto per il modificatore `async` nel punto di ingresso del programma.

[!code-csharp[Conceptual.BasicIO.TextFiles#WriteLine](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/async.cs)]
[!code-vb[Conceptual.BasicIO.TextFiles#WriteLine](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/async.vb)]  

## <a name="example-write-and-append-text-with-the-file-class"></a>Esempio: scrivere e aggiungere testo con la classe file

L'esempio seguente illustra come scrivere un testo in un nuovo file e aggiungere nuove righe di testo nello stesso file usando la classe <xref:System.IO.File> . I metodi <xref:System.IO.File.WriteAllText%2A> e <xref:System.IO.File.AppendAllLines%2A> aprono e chiudono automaticamente il file. Se il percorso specificato per il metodo <xref:System.IO.File.WriteAllText%2A> esiste già, il file viene sovrascritto.  

[!code-csharp[Conceptual.BasicIO.TextFiles#WriteLine](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/file.cs)]
[!code-vb[Conceptual.BasicIO.TextFiles#WriteLine](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/file.vb)]  

## <a name="see-also"></a>Vedere anche

- <xref:System.IO.StreamWriter>
- <xref:System.IO.Path>
- <xref:System.IO.File.CreateText%2A?displayProperty=nameWithType>
- [Procedura: enumerare directory e file](how-to-enumerate-directories-and-files.md)
- [Procedura: leggere e scrivere in un file di dati appena creato](how-to-read-and-write-to-a-newly-created-data-file.md)
- [Procedura: aprire e accodare un file di log](how-to-open-and-append-to-a-log-file.md)
- [Procedura: leggere testo da un file](how-to-read-text-from-a-file.md)
- [I/O di file e di flussi](index.md)

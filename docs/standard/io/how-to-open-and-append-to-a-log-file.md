---
title: 'Procedura: Aprire e accodare un file di log'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- log files, opening
- streams, opening and appending to log file
- log files, appending to
- I/O [.NET Framework], log files
ms.assetid: 74423362-1721-49cb-aa0a-e04005f72a06
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 35a7d481cf82818054a852f7c2e142f615022fcb
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2018
ms.locfileid: "44271715"
---
# <a name="how-to-open-and-append-to-a-log-file"></a>Procedura: Aprire e accodare un file di log
<xref:System.IO.StreamWriter> e <xref:System.IO.StreamReader> scrivono e leggono i caratteri nei flussi. L'esempio di codice seguente apre il file `log.txt` per l'input oppure crea il file, se non esiste già, e aggiunge le informazioni alla fine del file. Il contenuto del file viene quindi scritto nell'output standard per la visualizzazione. In alternativa a questo esempio, è possibile archiviare le informazioni come un'unica stringa o matrice di stringhe e usare il metodo <xref:System.IO.File.WriteAllText%2A> o <xref:System.IO.File.WriteAllLines%2A> per ottenere la stessa funzionalità.  
  
> [!NOTE]
>  Gli utenti di Visual Basic possono scegliere di usare i metodi e le proprietà forniti dalla classe <xref:Microsoft.VisualBasic.Logging.Log> o dalla classe <xref:Microsoft.VisualBasic.FileIO.FileSystem> per creare file di log o scrivere al loro interno.  
  
## <a name="example"></a>Esempio  
 [!code-csharp[Conceptual.BasicIO.TextFiles#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/source2.cs#2)]
 [!code-vb[Conceptual.BasicIO.TextFiles#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/source2.vb#2)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.IO.StreamWriter>  
- <xref:System.IO.StreamReader>  
- <xref:System.IO.File.AppendText%2A?displayProperty=nameWithType>  
- <xref:System.IO.File.OpenText%2A?displayProperty=nameWithType>  
- <xref:System.IO.StreamReader.ReadLine%2A?displayProperty=nameWithType>  
- [Procedura: Enumerare directory e file](../../../docs/standard/io/how-to-enumerate-directories-and-files.md)  
- [Procedura: Leggere e scrivere su un file di dati appena creato](../../../docs/standard/io/how-to-read-and-write-to-a-newly-created-data-file.md)  
- [Procedura: Leggere testo da un file](../../../docs/standard/io/how-to-read-text-from-a-file.md)  
- [Procedura: Scrivere un testo in un file](../../../docs/standard/io/how-to-write-text-to-a-file.md)  
- [Procedura: Leggere caratteri da una stringa](../../../docs/standard/io/how-to-read-characters-from-a-string.md)  
- [Procedura: Scrivere caratteri in una stringa](../../../docs/standard/io/how-to-write-characters-to-a-string.md)  
- [I/O di file e di flussi](../../../docs/standard/io/index.md)

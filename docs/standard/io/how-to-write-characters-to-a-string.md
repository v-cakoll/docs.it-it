---
title: 'Procedura: Scrivere caratteri in una stringa'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data streams, writing characters to string
- writing characters to strings
- streams, writing characters to strings
- I/O [.NET Framework], writing characters to strings
ms.assetid: 1222cbeb-0760-44bf-9888-914a2a37174b
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 969a511f6b3d93450866d7a85cf2bcb198d2581e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33572034"
---
# <a name="how-to-write-characters-to-a-string"></a>Procedura: Scrivere caratteri in una stringa
Gli esempi di codice seguenti illustrano come scrivere i caratteri in modo sincrono e asincrono da una matrice di caratteri a una stringa.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente scrive 5 caratteri in modo sincrono da una matrice a una stringa.  
  
 [!code-csharp[Conceptual.StringBuilder#9](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/example2.cs#9)]
 [!code-vb[Conceptual.StringBuilder#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/example2.vb#9)]  
  
## <a name="example"></a>Esempio  
 L'esempio seguente legge tutti i caratteri in modo asincrono da un controllo <xref:System.Windows.Controls.TextBox> e li archivia in una matrice. Scrive quindi in modo asincrono ogni lettera o spazio su una riga separata seguita da un'interruzione di riga in un controllo <xref:System.Windows.Controls.TextBlock>.  
  
 [!code-csharp[Conceptual.StringReader#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.stringreader/cs/source2.cs#2)]
 [!code-vb[Conceptual.StringReader#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.stringreader/vb/source2.vb#2)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.IO.StringWriter>  
 <xref:System.IO.StringWriter.Write%2A?displayProperty=nameWithType>  
 <xref:System.Text.StringBuilder>  
 [I/O di file e di flussi](../../../docs/standard/io/index.md)  
 [I/O di file asincrono](../../../docs/standard/io/asynchronous-file-i-o.md)  
 [Procedura: Enumerare directory e file](../../../docs/standard/io/how-to-enumerate-directories-and-files.md)  
 [Procedura: Leggere e scrivere su un file di dati appena creato](../../../docs/standard/io/how-to-read-and-write-to-a-newly-created-data-file.md)  
 [Procedura: Aprire e accodare un file di log](../../../docs/standard/io/how-to-open-and-append-to-a-log-file.md)  
 [Procedura: Leggere testo da un file](../../../docs/standard/io/how-to-read-text-from-a-file.md)  
 [Procedura: Scrivere un testo in un file](../../../docs/standard/io/how-to-write-text-to-a-file.md)  
 [Procedura: Leggere caratteri da una stringa](../../../docs/standard/io/how-to-read-characters-from-a-string.md)

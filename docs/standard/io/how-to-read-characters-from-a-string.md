---
title: 'Procedura: Leggere caratteri da una stringa'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- reading characters from strings
- data streams, reading characters from string
- I/O [.NET Framework], reading characters from strings
- reading data, strings
- streams, reading characters from string
ms.assetid: 27ea5e52-6db8-42d8-980a-50bcfc7fd270
author: mairaw
ms.author: mairaw
ms.openlocfilehash: cbf213c783d1688e9168265cedc27d2ac7a5a96d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54504811"
---
# <a name="how-to-read-characters-from-a-string"></a>Procedura: Leggere caratteri da una stringa
Gli esempi di codice seguenti illustrano come leggere i caratteri in modo sincrono e asincrono da una stringa.  
  
## <a name="example"></a>Esempio  
 Questo esempio legge 13 caratteri in modo sincrono da una stringa, li archivia in una matrice e li visualizza. Legge quindi i caratteri rimanenti nella stringa, li archivia nella matrice a partire dal sesto elemento e visualizza il contenuto della matrice.  
  
 [!code-cpp[Conceptual.StringReader#1](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.stringreader/cpp/source.cpp#1)]
 [!code-csharp[Conceptual.StringReader#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.stringreader/cs/source.cs#1)]
 [!code-vb[Conceptual.StringReader#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.stringreader/vb/source.vb#1)]  
  
## <a name="example"></a>Esempio  
 L'esempio seguente legge tutti i caratteri in modo asincrono da un controllo <xref:System.Windows.Controls.TextBox> e li archivia in una matrice. Scrive quindi in modo asincrono ogni lettera o spazio su una riga separata seguita da un'interruzione di riga in un controllo <xref:System.Windows.Controls.TextBlock>.  
  
 [!code-csharp[Conceptual.StringReader#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.stringreader/cs/source2.cs#2)]
 [!code-vb[Conceptual.StringReader#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.stringreader/vb/source2.vb#2)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.IO.StringReader>
- <xref:System.IO.StringReader.Read%2A?displayProperty=nameWithType>
- [Asynchronous File I/O](../../../docs/standard/io/asynchronous-file-i-o.md)
- [NIB: Procedura: Creare una visualizzazione directory](https://msdn.microsoft.com/library/4d2772b1-b991-4532-a8a6-6ef733277e69)
- [Procedura: Leggere e scrivere su un file di dati appena creato](../../../docs/standard/io/how-to-read-and-write-to-a-newly-created-data-file.md)
- [Procedura: Aprire e accodare un file di log](../../../docs/standard/io/how-to-open-and-append-to-a-log-file.md)
- [Procedura: Leggere testo da un file](../../../docs/standard/io/how-to-read-text-from-a-file.md)
- [Procedura: Scrivere testo in un file](../../../docs/standard/io/how-to-write-text-to-a-file.md)
- [Procedura: Scrivere caratteri in una stringa](../../../docs/standard/io/how-to-write-characters-to-a-string.md)
- [I/O di file e di flussi](../../../docs/standard/io/index.md)

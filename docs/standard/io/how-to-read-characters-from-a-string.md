---
title: 'Procedura: Leggere caratteri da una stringa'
ms.date: 01/21/2019
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
ms.openlocfilehash: 01d5fb2e4f785a4a510715b58e95d310a6ffa4e2
ms.sourcegitcommit: b8ace47d839f943f785b89e2fff8092b0bf8f565
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2019
ms.locfileid: "55675348"
---
# <a name="how-to-read-characters-from-a-string"></a>Procedura: Leggere caratteri da una stringa
Gli esempi di codice seguenti illustrano come leggere i caratteri in modo sincrono o asincrono da una stringa.  
  
## <a name="example-read-characters-synchronously"></a>Esempio: Leggere i caratteri in modo sincrono 
 Questo esempio legge 13 caratteri in modo sincrono da una stringa, li archivia in una matrice e li visualizza. Legge quindi i caratteri rimanenti nella stringa, li archivia nella matrice a partire dal sesto elemento e visualizza il contenuto della matrice.  
  
 [!code-csharp[Conceptual.StringReader#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.stringreader/cs/source.cs#1)]
 [!code-vb[Conceptual.StringReader#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.stringreader/vb/source.vb#1)]  
  
## <a name="example-read-characters-asynchronously"></a>Esempio: Leggere i caratteri in modo asincrono  
 L'esempio successivo è il code-behind di un'app WPF. Al caricamento della finestra, l'esempio legge in modo asincrono tutti i caratteri da un controllo <xref:System.Windows.Controls.TextBox> e li archivia in una matrice. Scrive quindi in modo asincrono ogni lettera o spazio su una riga separata di un controllo <xref:System.Windows.Controls.TextBlock>.  
  
 [!code-csharp[Conceptual.StringReader#2](../../../samples/snippets/csharp/VS_Snippets_Wpf/StringReaderWriter/MainWindow.xaml.cs)]
 [!code-vb[Conceptual.StringReader#2](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StringReaderWriter/MainWindow.xaml.vb)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.IO.StringReader>  
- <xref:System.IO.StringReader.Read%2A?displayProperty=nameWithType>  
- [I/O di file asincrono](../../../docs/standard/io/asynchronous-file-i-o.md)  
- [Procedura: Creare una visualizzazione directory](https://msdn.microsoft.com/library/4d2772b1-b991-4532-a8a6-6ef733277e69)  
- [Procedura: Leggere e scrivere in un file di dati appena creato](../../../docs/standard/io/how-to-read-and-write-to-a-newly-created-data-file.md)  
- [Procedura: Aprire e accodare un file di log](../../../docs/standard/io/how-to-open-and-append-to-a-log-file.md)  
- [Procedura: Leggere testo da un file](../../../docs/standard/io/how-to-read-text-from-a-file.md)  
- [Procedura: Scrivere testo in un file](../../../docs/standard/io/how-to-write-text-to-a-file.md)  
- [Procedura: Scrivere caratteri in una stringa](../../../docs/standard/io/how-to-write-characters-to-a-string.md)  
- [I/O di file e di flussi](../../../docs/standard/io/index.md)

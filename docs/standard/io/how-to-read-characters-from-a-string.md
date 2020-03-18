---
title: 'Procedura: leggere caratteri da una stringaHow to: Read characters from a string'
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
ms.openlocfilehash: ed267ad62e46f6216c94906df1bcefb0684ab51b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "78155763"
---
# <a name="how-to-read-characters-from-a-string"></a>Procedura: leggere caratteri da una stringaHow to: Read characters from a string
Gli esempi di codice seguenti illustrano come leggere i caratteri in modo sincrono o asincrono da una stringa.  
  
## <a name="example-read-characters-synchronously"></a>Esempio: leggere i caratteri in modo sincronoExample: Read characters synchronously
 Questo esempio legge 13 caratteri in modo sincrono da una stringa, li archivia in una matrice e li visualizza. Legge quindi i caratteri rimanenti nella stringa, li archivia nella matrice a partire dal sesto elemento e visualizza il contenuto della matrice.  
  
 [!code-csharp[Conceptual.StringReader#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.stringreader/cs/source.cs#1)]
 [!code-vb[Conceptual.StringReader#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.stringreader/vb/source.vb#1)]  
  
## <a name="example-read-characters-asynchronously"></a>Esempio: leggere i caratteri in modo asincronoExample: Read characters asynchronously  
 L'esempio successivo è il code-behind di un'app WPF. Al caricamento della finestra, l'esempio legge in modo asincrono tutti i caratteri da un controllo <xref:System.Windows.Controls.TextBox> e li archivia in una matrice. Scrive quindi in modo asincrono ogni lettera o spazio su una riga separata di un controllo <xref:System.Windows.Controls.TextBlock>.  
  
 [!code-csharp[Conceptual.StringReader#2](../../../samples/snippets/csharp/VS_Snippets_Wpf/StringReaderWriter/MainWindow.xaml.cs)]
 [!code-vb[Conceptual.StringReader#2](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StringReaderWriter/MainWindow.xaml.vb)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.IO.StringReader>  
- <xref:System.IO.StringReader.Read%2A?displayProperty=nameWithType>  
- [I/O di file asincroni](../../../docs/standard/io/asynchronous-file-i-o.md)  
- [Procedura: Creare un elenco di directoryHow to: Create a directory listing](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/5cf8zcfh(v=vs.100))  
- [Procedura: leggere e scrivere in un file di dati appena creatoHow to: Read and write to a newly created data file](../../../docs/standard/io/how-to-read-and-write-to-a-newly-created-data-file.md)  
- [Procedura: aprire e aggiungere a un file di registroHow to: Open and append to a log file](../../../docs/standard/io/how-to-open-and-append-to-a-log-file.md)  
- [Procedura: leggere testo da un fileHow to: Read Text from a file](../../../docs/standard/io/how-to-read-text-from-a-file.md)  
- [Procedura: scrivere testo in un fileHow to: Write text to a file](../../../docs/standard/io/how-to-write-text-to-a-file.md)  
- [Procedura: scrivere caratteri in una stringaHow to: Write characters to a string](../../../docs/standard/io/how-to-write-characters-to-a-string.md)  
- [I/O di file e di flussi](../../../docs/standard/io/index.md)

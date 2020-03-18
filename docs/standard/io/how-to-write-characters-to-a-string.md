---
title: 'Procedura: scrivere caratteri in una stringaHow to: Write characters to a string'
ms.date: 01/21/2019
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
ms.openlocfilehash: ecbfa2de2c21ff79df269f74eeddfa0738e7e25c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "78160280"
---
# <a name="how-to-write-characters-to-a-string"></a>Procedura: scrivere caratteri in una stringaHow to: Write characters to a string
Gli esempi di codice seguenti illustrano come scrivere i caratteri in modo sincrono o asincrono da una matrice di caratteri in una stringa.  
  
## <a name="example-write-characters-synchronously-in-a-console-app"></a>Esempio: scrivere caratteri in modo sincrono in un'app consoleExample: Write characters synchronously in a console app  
 L'esempio seguente usa <xref:System.IO.StringWriter> per scrivere cinque caratteri in modo sincrono in un oggetto <xref:System.Text.StringBuilder>.
  
 [!code-csharp[Conceptual.StringBuilder#9](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/example2.cs#9)]
 [!code-vb[Conceptual.StringBuilder#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/example2.vb#9)]  
  
## <a name="example-write-characters-asynchronously-in-a-wpf-app"></a>Esempio: scrivere caratteri in modo asincrono in un'app WPFExample: Write characters asynchronously in a WPF app
 L'esempio successivo è il code-behind di un'app WPF. Al caricamento della finestra, l'esempio legge in modo asincrono tutti i caratteri da un controllo <xref:System.Windows.Controls.TextBox> e li archivia in una matrice. Scrive quindi in modo asincrono ogni lettera o spazio su una riga separata di un controllo <xref:System.Windows.Controls.TextBlock>.  
  
 [!code-csharp[StreamReaderWriter](../../../samples/snippets/csharp/VS_Snippets_Wpf/StringReaderWriter/MainWindow.xaml.cs)]
 [!code-vb[StreamReaderWriter](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StringReaderWriter/MainWindow.xaml.vb)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.IO.StringWriter>  
- <xref:System.IO.StringWriter.Write%2A?displayProperty=nameWithType>  
- <xref:System.Text.StringBuilder>  
- [I/O di file e di flussi](../../../docs/standard/io/index.md)  
- [I/O di file asincroni](../../../docs/standard/io/asynchronous-file-i-o.md)  
- [Procedura: enumerare directory e file](../../../docs/standard/io/how-to-enumerate-directories-and-files.md)  
- [Procedura: leggere e scrivere in un file di dati appena creatoHow to: Read and write to a newly created data file](../../../docs/standard/io/how-to-read-and-write-to-a-newly-created-data-file.md)  
- [Procedura: aprire e aggiungere a un file di registroHow to: Open and append to a log file](../../../docs/standard/io/how-to-open-and-append-to-a-log-file.md)  
- [Procedura: leggere testo da un fileHow to: Read Text from a file](../../../docs/standard/io/how-to-read-text-from-a-file.md)  
- [Procedura: scrivere testo in un fileHow to: Write text to a file](../../../docs/standard/io/how-to-write-text-to-a-file.md)  
- [Procedura: leggere caratteri da una stringaHow to: Read characters from a string](../../../docs/standard/io/how-to-read-characters-from-a-string.md)

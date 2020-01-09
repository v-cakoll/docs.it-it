---
title: Comporre flussi
ms.date: 01/21/2019
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- streams, base streams
- I/O [.NET Framework], composing streams
- Stream class, composing streams
- base streams
- streams, backing stores
ms.assetid: da761658-a535-4f26-a452-b30df47f73d5
ms.openlocfilehash: 689cc9537cd7a5fe6a677d42e5790bbcf1b3aefa
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75708148"
---
# <a name="compose-streams"></a>Comporre flussi
Un *archivio di backup* è un supporto di archiviazione, ad esempio un disco o la memoria. Ogni tipo di archivio di backup implementa il flusso come implementazione della classe <xref:System.IO.Stream>. 

Ogni tipo di flusso legge e scrive i byte da e nel relativo archivio di backup. I flussi che si connettono agli archivi di backup sono chiamati *flussi di base*. I flussi di base hanno costruttori con i parametri necessari per connettere il flusso all'archivio di backup. <xref:System.IO.FileStream>, ad esempio, ha costruttori che specificano un parametro del percorso, che specifica come il file verrà condiviso dai processi.  

La progettazione delle classi <xref:System.IO> consente una composizione dei flussi semplificata. I flussi di base possono essere associati a uno o più flussi pass-through che forniscono la funzionalità desiderata. Un lettore o un writer può essere collegato alla fine della catena, in modo che i tipi preferiti possano essere letti o scritti facilmente.  

Gli esempi di codice seguenti creano un **FileStream** per il file esistente *MyFile.txt* in modo da inserire nel buffer *MyFile.txt*. Si noti che gli elementi **FileStream** vengono memorizzati nel buffer per impostazione predefinita.

>[!IMPORTANT]
>Gli esempi presuppongono che un file denominato *MyFile.txt* esista già nella stessa cartella dell'app.  

## <a name="example-use-streamreader"></a>Esempio: usare StreamReader
L'esempio seguente crea un elemento <xref:System.IO.StreamReader> per leggere i caratteri da **FileStream**, che viene passato a **StreamReader** come argomento del costruttore. <xref:System.IO.StreamReader.ReadLine%2A?displayProperty=nameWithType> legge finché <xref:System.IO.StreamReader.Peek%2A?displayProperty=nameWithType> non trova più caratteri.  
  
 [!code-csharp[System.IO.StreamReader#20](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.StreamReader/CS/source2.cs#20)]
 [!code-vb[System.IO.StreamReader#20](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.StreamReader/VB/source2.vb#20)]  
  
## <a name="example-use-binaryreader"></a>Esempio: usare BinaryReader
L'esempio seguente crea un elemento <xref:System.IO.BinaryReader> per leggere i byte da **FileStream**, che viene passato a **BinaryReader** come argomento del costruttore. <xref:System.IO.BinaryReader.ReadByte%2A> legge finché <xref:System.IO.BinaryReader.PeekChar%2A> non trova più byte.  
  
 [!code-csharp[System.IO.StreamReader#21](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.StreamReader/CS/source3.cs#21)]
 [!code-vb[System.IO.StreamReader#21](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.StreamReader/VB/source3.vb#21)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.IO.StreamReader>
- <xref:System.IO.StreamReader.ReadLine%2A?displayProperty=nameWithType>
- <xref:System.IO.StreamReader.Peek%2A?displayProperty=nameWithType>
- <xref:System.IO.FileStream>
- <xref:System.IO.BinaryReader>
- <xref:System.IO.BinaryReader.ReadByte%2A?displayProperty=nameWithType>
- <xref:System.IO.BinaryReader.PeekChar%2A?displayProperty=nameWithType>

---
title: Composizione dei flussi
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 75800210a52620c5b08a01c5f8fa888bf40843fe
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="composing-streams"></a>Composizione dei flussi
Un archivio di backup è un supporto di archiviazione, ad esempio un disco o memoria. Ogni archivio di backup diversi implementa il flusso come un'implementazione del <xref:System.IO.Stream> classe. Ogni tipo di flusso legge e scrive byte da e in un archivio di backup specificato. Flussi di connettono ad archivi di backup vengono chiamati i flussi di base. Flussi di base hanno costruttori che accettano i presentano per il flusso di connettersi all'archivio di backup. Ad esempio, <xref:System.IO.FileStream> dispone di costruttori che specificano un parametro di percorso che specifica come il file verrà condiviso dai processi e così via.  
  
 La progettazione della <xref:System.IO> classi fornisce la composizione di flussi. Flussi di base possono essere collegati a uno o più flussi di pass-through che forniscono la funzionalità desiderata. Un lettore o writer può essere collegato alla fine della catena in modo che i tipi Preferiti possono essere letto o scritti facilmente.  
  
 L'esempio di codice seguente crea un **FileStream** intorno esistente `MyFile.txt` per inserire nel buffer `MyFile.txt`. (Si noti che **FileStream** vengono memorizzati nel buffer per impostazione predefinita.) Successivamente, un <xref:System.IO.StreamReader> viene creato per leggere caratteri dal **FileStream**, che viene passato al **StreamReader** come argomento del costruttore. <xref:System.IO.StreamReader.ReadLine%2A>legge fino a quando <xref:System.IO.StreamReader.Peek%2A> non trova più caratteri.  
  
 [!code-cpp[System.IO.StreamReader#20](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.IO.StreamReader/CPP/source2.cpp#20)]
 [!code-csharp[System.IO.StreamReader#20](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.StreamReader/CS/source2.cs#20)]
 [!code-vb[System.IO.StreamReader#20](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.StreamReader/VB/source2.vb#20)]  
  
 L'esempio di codice seguente crea un **FileStream** intorno esistente `MyFile.txt` per inserire nel buffer `MyFile.txt`. (Si noti che **FileStream** vengono memorizzati nel buffer per impostazione predefinita.) Successivamente, un **BinaryReader** viene creato per leggere i byte dal **FileStream**, che viene passato al **BinaryReader** come argomento del costruttore. <xref:System.IO.BinaryReader.ReadByte%2A>legge fino a quando <xref:System.IO.BinaryReader.PeekChar%2A> non trova più byte.  
  
 [!code-cpp[System.IO.StreamReader#21](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.IO.StreamReader/CPP/source3.cpp#21)]
 [!code-csharp[System.IO.StreamReader#21](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.StreamReader/CS/source3.cs#21)]
 [!code-vb[System.IO.StreamReader#21](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.StreamReader/VB/source3.vb#21)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.IO.StreamReader>  
 <xref:System.IO.StreamReader.ReadLine%2A?displayProperty=nameWithType>  
 <xref:System.IO.StreamReader.Peek%2A?displayProperty=nameWithType>  
 <xref:System.IO.FileStream>  
 <xref:System.IO.BinaryReader>  
 <xref:System.IO.BinaryReader.ReadByte%2A?displayProperty=nameWithType>  
 <xref:System.IO.BinaryReader.PeekChar%2A?displayProperty=nameWithType>

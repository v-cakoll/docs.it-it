---
title: Composizione dei flussi
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5e52b827f337892c33ec61b9affa1cc646a759c5
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/17/2018
ms.locfileid: "45676824"
---
# <a name="composing-streams"></a>Composizione dei flussi
Un archivio di backup è un supporto di archiviazione, ad esempio un disco o la memoria. Ogni tipo di archivio di backup implementa il flusso come implementazione della classe <xref:System.IO.Stream>. Ogni tipo di flusso legge e scrive i byte da e nel relativo archivio di backup. I flussi che si connettono agli archivi di backup sono chiamati flussi di base. I flusso di base hanno costruttori con i parametri necessari per connettere il flusso all'archivio di backup. <xref:System.IO.FileStream>, ad esempio, ha costruttori che specificano un parametro del percorso, che specifica come il file verrà condiviso dai processi e così via.  
  
 La progettazione delle classi <xref:System.IO> consente una composizione dei flussi semplificata. I flussi di base possono essere collegati a uno o più flussi pass-through che forniscono la funzionalità desiderata. Un reader o un writer può essere accodato alla fine della catena in modo che i tipi preferiti possano essere letti o scritti facilmente.  
  
 L'esempio di codice seguente crea un elemento **FileStream** attorno all'elemento `MyFile.txt` esistente per memorizzare nel buffer `MyFile.txt`. Si noti che gli elementi **FileStream** vengono memorizzati nel buffer per impostazione predefinita. Viene quindi creato un elemento <xref:System.IO.StreamReader> per leggere i caratteri dal **FileStream**, che viene passato allo **StreamReader** come argomento del costruttore. <xref:System.IO.StreamReader.ReadLine%2A> legge finché <xref:System.IO.StreamReader.Peek%2A> non trova più caratteri.  
  
 [!code-cpp[System.IO.StreamReader#20](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.IO.StreamReader/CPP/source2.cpp#20)]
 [!code-csharp[System.IO.StreamReader#20](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.StreamReader/CS/source2.cs#20)]
 [!code-vb[System.IO.StreamReader#20](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.StreamReader/VB/source2.vb#20)]  
  
 L'esempio di codice seguente crea un elemento **FileStream** attorno all'elemento `MyFile.txt` esistente per memorizzare nel buffer `MyFile.txt`. Si noti che gli elementi **FileStream** vengono memorizzati nel buffer per impostazione predefinita. Viene quindi creato un **BinaryReader** per leggere i byte dal **FileStream**, che viene passato al **BinaryReader** come argomento del costruttore. <xref:System.IO.BinaryReader.ReadByte%2A> legge finché <xref:System.IO.BinaryReader.PeekChar%2A> non trova più byte.  
  
 [!code-cpp[System.IO.StreamReader#21](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.IO.StreamReader/CPP/source3.cpp#21)]
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

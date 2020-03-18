---
title: Annullamento cooperativo di thread
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- threads, cancellation
ms.assetid: d2d6d5fd-e263-4fa0-847b-2fc3e0d82337
ms.openlocfilehash: 1d1433ecf39974bf9e68fe07b9d0818ac16fb544
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "73138132"
---
# <a name="canceling-threads-cooperatively"></a>Annullamento cooperativo di thread

Nelle versioni precedenti a .NET Framework 4, .NET Framework non offriva alcun metodo incorporato per annullare un thread in modo cooperativo dopo l'avvio dello stesso. Tuttavia, a partire dalla versione .NET Framework 4, è possibile usare <xref:System.Threading.CancellationToken?displayProperty=nameWithType> per annullare i thread, nello stesso modo in cui è possibile usarli per annullare oggetti <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> o query PLINQ. Anche se la classe <xref:System.Threading.Thread?displayProperty=nameWithType> non offre supporto predefinito per i token di annullamento, è possibile passare un token a una routine del thread usando il costruttore <xref:System.Threading.Thread> che accetta un delegato <xref:System.Threading.ParameterizedThreadStart>. Nell'esempio riportato di seguito viene illustrato come procedere.  
  
 [!code-csharp[Cancellation#14](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/CooperativeThreads.cs#14)]
 [!code-vb[Cancellation#14](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/CooperativeThreads.vb#14)]  
  
## <a name="see-also"></a>Vedere anche

- [Utilizzo di thread e threading](using-threads-and-threading.md)

---
title: "Procedura: eseguire il wrapping di modelli EAP in un'attività"
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tasks, how to wrap EAP patterns
ms.assetid: f11ed467-af2f-4504-8a2e-299a6c36d44e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a4287879bd95f7bc1e1dc99f74fa0d7cc0fe737f
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2018
ms.locfileid: "44270304"
---
# <a name="how-to-wrap-eap-patterns-in-a-task"></a>Procedura: eseguire il wrapping di modelli EAP in un'attività
Nell'esempio seguente viene illustrato come esporre una sequenza arbitraria di operazioni del modello asincrono basato su eventi (EAP) come un'unica attività tramite un oggetto <xref:System.Threading.Tasks.TaskCompletionSource%601>. L'esempio mostra anche come usare un oggetto <xref:System.Threading.CancellationToken> per richiamare i metodi di annullamento predefiniti sugli oggetti <xref:System.Net.WebClient>.  
  
## <a name="example"></a>Esempio  
 [!code-csharp[FromAsync#08](../../../samples/snippets/csharp/VS_Snippets_Misc/fromasync/cs/fromasync.cs#08)]
 [!code-vb[FromAsync#08](../../../samples/snippets/visualbasic/VS_Snippets_Misc/fromasync/vb/module1.vb#08)]  
  
## <a name="see-also"></a>Vedere anche

- [Task Parallel Library e programmazione asincrona .NET Framework tradizionale](../../../docs/standard/parallel-programming/tpl-and-traditional-async-programming.md)

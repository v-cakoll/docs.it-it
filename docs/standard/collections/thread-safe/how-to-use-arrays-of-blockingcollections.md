---
title: 'Procedura: utilizzare matrici di raccolte di blocco in una pipeline'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- thread-safe collections, blocking collections in pipeline
ms.assetid: a39c7ec3-3ad7-4f4d-8fe4-b3e9dbabe2ed
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9313f1064534702fdc2d239eb7f0f69a470329e2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33567770"
---
# <a name="how-to-use-arrays-of-blocking-collections-in-a-pipeline"></a><span data-ttu-id="fe102-102">Procedura: utilizzare matrici di raccolte di blocco in una pipeline</span><span class="sxs-lookup"><span data-stu-id="fe102-102">How to: Use Arrays of Blocking Collections in a Pipeline</span></span>
<span data-ttu-id="fe102-103">L'esempio seguente illustra come usare matrici di oggetti <xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=nameWithType> con metodi statici, ad esempio <xref:System.Collections.Concurrent.BlockingCollection%601.TryAddToAny%2A> e <xref:System.Collections.Concurrent.BlockingCollection%601.TryTakeFromAny%2A>, per implementare un trasferimento di dati rapido e flessibile tra componenti.</span><span class="sxs-lookup"><span data-stu-id="fe102-103">The following example shows how to use arrays of <xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=nameWithType> objects with static methods such as <xref:System.Collections.Concurrent.BlockingCollection%601.TryAddToAny%2A> and <xref:System.Collections.Concurrent.BlockingCollection%601.TryTakeFromAny%2A> to implement fast and flexible data transfer between components.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fe102-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="fe102-104">Example</span></span>  
 <span data-ttu-id="fe102-105">L'esempio seguente illustra un'implementazione della pipeline di base in cui ogni oggetto preleva simultaneamente dati dalla raccolta di input, li trasforma e li passa alla raccolta di output.</span><span class="sxs-lookup"><span data-stu-id="fe102-105">The following example demonstrates a basic pipeline implementation in which each object is concurrently taking data from the input collection, transforming it, and passing it to the output collection.</span></span>  
  
 [!code-csharp[CDS_BlockingCollection#07](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds_blockingcollection/cs/example07.cs#07)]
 [!code-vb[CDS_BlockingCollection#07](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_blockingcollection/vb/bcpipeline.vb#07)]  
  
## <a name="see-also"></a><span data-ttu-id="fe102-106">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fe102-106">See Also</span></span>  
 <xref:System.Collections.Concurrent?displayProperty=nameWithType>  
 [<span data-ttu-id="fe102-107">Raccolte thread-safe</span><span class="sxs-lookup"><span data-stu-id="fe102-107">Thread-Safe Collections</span></span>](../../../../docs/standard/collections/thread-safe/index.md)

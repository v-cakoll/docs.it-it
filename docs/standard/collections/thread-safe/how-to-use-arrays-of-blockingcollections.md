---
title: 'Procedura: utilizzare matrici di raccolte di blocco in una pipeline'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- thread-safe collections, blocking collections in pipeline
ms.assetid: a39c7ec3-3ad7-4f4d-8fe4-b3e9dbabe2ed
caps.latest.revision: 8
author: mairaw
ms.author: mairaw
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 8dda929df8e3de907c228bbef85749cba5cabc25
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-use-arrays-of-blocking-collections-in-a-pipeline"></a><span data-ttu-id="d38c5-102">Procedura: utilizzare matrici di raccolte di blocco in una pipeline</span><span class="sxs-lookup"><span data-stu-id="d38c5-102">How to: Use Arrays of Blocking Collections in a Pipeline</span></span>
<span data-ttu-id="d38c5-103">L'esempio seguente illustra come usare matrici di oggetti <xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=fullName> con metodi statici, ad esempio <xref:System.Collections.Concurrent.BlockingCollection%601.TryAddToAny%2A> e <xref:System.Collections.Concurrent.BlockingCollection%601.TryTakeFromAny%2A>, per implementare un trasferimento di dati rapido e flessibile tra componenti.</span><span class="sxs-lookup"><span data-stu-id="d38c5-103">The following example shows how to use arrays of <xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=fullName> objects with static methods such as <xref:System.Collections.Concurrent.BlockingCollection%601.TryAddToAny%2A> and <xref:System.Collections.Concurrent.BlockingCollection%601.TryTakeFromAny%2A> to implement fast and flexible data transfer between components.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d38c5-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="d38c5-104">Example</span></span>  
 <span data-ttu-id="d38c5-105">L'esempio seguente illustra un'implementazione della pipeline di base in cui ogni oggetto preleva simultaneamente dati dalla raccolta di input, li trasforma e li passa alla raccolta di output.</span><span class="sxs-lookup"><span data-stu-id="d38c5-105">The following example demonstrates a basic pipeline implementation in which each object is concurrently taking data from the input collection, transforming it, and passing it to the output collection.</span></span>  
  
 <span data-ttu-id="d38c5-106">[!code-csharp[CDS_BlockingCollection#07](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds_blockingcollection/cs/example07.cs#07)] [!code-vb[CDS_BlockingCollection#07](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_blockingcollection/vb/bcpipeline.vb#07)]</span><span class="sxs-lookup"><span data-stu-id="d38c5-106">[!code-csharp[CDS_BlockingCollection#07](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds_blockingcollection/cs/example07.cs#07)] [!code-vb[CDS_BlockingCollection#07](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_blockingcollection/vb/bcpipeline.vb#07)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d38c5-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d38c5-107">See Also</span></span>  
 <span data-ttu-id="d38c5-108"><xref:System.Collections.Concurrent?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="d38c5-108"><xref:System.Collections.Concurrent?displayProperty=fullName></span></span>   
 [<span data-ttu-id="d38c5-109">Raccolte thread-safe</span><span class="sxs-lookup"><span data-stu-id="d38c5-109">Thread-Safe Collections</span></span>](../../../../docs/standard/collections/thread-safe/index.md)


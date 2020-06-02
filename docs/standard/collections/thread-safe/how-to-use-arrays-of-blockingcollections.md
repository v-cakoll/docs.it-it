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
ms.openlocfilehash: 2309676435a6603aaa9bbbd95953c0179b908622
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84287831"
---
# <a name="how-to-use-arrays-of-blocking-collections-in-a-pipeline"></a><span data-ttu-id="65844-102">Procedura: utilizzare matrici di raccolte di blocco in una pipeline</span><span class="sxs-lookup"><span data-stu-id="65844-102">How to: Use Arrays of Blocking Collections in a Pipeline</span></span>
<span data-ttu-id="65844-103">L'esempio seguente illustra come usare matrici di oggetti <xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=nameWithType> con metodi statici, ad esempio <xref:System.Collections.Concurrent.BlockingCollection%601.TryAddToAny%2A> e <xref:System.Collections.Concurrent.BlockingCollection%601.TryTakeFromAny%2A>, per implementare un trasferimento di dati rapido e flessibile tra componenti.</span><span class="sxs-lookup"><span data-stu-id="65844-103">The following example shows how to use arrays of <xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=nameWithType> objects with static methods such as <xref:System.Collections.Concurrent.BlockingCollection%601.TryAddToAny%2A> and <xref:System.Collections.Concurrent.BlockingCollection%601.TryTakeFromAny%2A> to implement fast and flexible data transfer between components.</span></span>  
  
## <a name="example"></a><span data-ttu-id="65844-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="65844-104">Example</span></span>  
 <span data-ttu-id="65844-105">L'esempio seguente illustra un'implementazione della pipeline di base in cui ogni oggetto preleva simultaneamente dati dalla raccolta di input, li trasforma e li passa alla raccolta di output.</span><span class="sxs-lookup"><span data-stu-id="65844-105">The following example demonstrates a basic pipeline implementation in which each object is concurrently taking data from the input collection, transforming it, and passing it to the output collection.</span></span>  
  
 [!code-csharp[CDS_BlockingCollection#07](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds_blockingcollection/cs/example07.cs#07)]
 [!code-vb[CDS_BlockingCollection#07](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_blockingcollection/vb/bcpipeline.vb#07)]  
  
## <a name="see-also"></a><span data-ttu-id="65844-106">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="65844-106">See also</span></span>

- <xref:System.Collections.Concurrent?displayProperty=nameWithType>
- [<span data-ttu-id="65844-107">Raccolte thread-safe</span><span class="sxs-lookup"><span data-stu-id="65844-107">Thread-Safe Collections</span></span>](index.md)

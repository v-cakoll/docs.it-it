---
title: Funzionalità non supportata
ms.date: 03/30/2017
ms.assetid: e480cfb5-697e-42c8-bed5-9264c945c4f9
ms.openlocfilehash: 18a1a8f33a9360b4299648bcd329f4c5f2e7de88
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61917558"
---
# <a name="unsupported-functionality"></a><span data-ttu-id="d1f74-102">Funzionalità non supportata</span><span class="sxs-lookup"><span data-stu-id="d1f74-102">Unsupported Functionality</span></span>
<span data-ttu-id="d1f74-103">In LINQ to SQL non è possibile esporre la funzionalità SQL seguente tramite la conversione di costrutti CLR (Common Language Runtime) e .NET Framework esistenti:</span><span class="sxs-lookup"><span data-stu-id="d1f74-103">In LINQ to SQL, the following SQL functionality cannot be exposed through translation of existing common language runtime (CLR) and .NET Framework constructs:</span></span>  
  
- `STDDEV`  
  
- `LIKE`  
  
     <span data-ttu-id="d1f74-104">Sebbene `LIKE` non sia supportato tramite conversione diretta, una funzionalità analoga esiste nella classe <xref:System.Data.Linq.SqlClient.SqlMethods>.</span><span class="sxs-lookup"><span data-stu-id="d1f74-104">Although `LIKE` is not supported through direct translation, similar functionality exists in the <xref:System.Data.Linq.SqlClient.SqlMethods> class.</span></span> <span data-ttu-id="d1f74-105">Per altre informazioni, vedere <xref:System.Data.Linq.SqlClient.SqlMethods.Like%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="d1f74-105">For more information, see <xref:System.Data.Linq.SqlClient.SqlMethods.Like%2A?displayProperty=nameWithType>.</span></span>  
  
- `DATEDIFF`  
  
     <span data-ttu-id="d1f74-106">LINQ to SQL dispone di un supporto limitato per `DATEDIFF`.</span><span class="sxs-lookup"><span data-stu-id="d1f74-106">LINQ to SQL has limited support for `DATEDIFF`.</span></span> <span data-ttu-id="d1f74-107">Una funzionalità analoga è presente nella classe <xref:System.Data.Linq.SqlClient.SqlMethods>.</span><span class="sxs-lookup"><span data-stu-id="d1f74-107">Similar functionality exists in the <xref:System.Data.Linq.SqlClient.SqlMethods> class.</span></span>  
  
- `ROUND`  
  
     <span data-ttu-id="d1f74-108">LINQ to SQL dispone di un supporto limitato per `ROUND`.</span><span class="sxs-lookup"><span data-stu-id="d1f74-108">LINQ to SQL has limited support for `ROUND`.</span></span> <span data-ttu-id="d1f74-109">Per altre informazioni, vedere [metodi System. Math](system-math-methods.md).</span><span class="sxs-lookup"><span data-stu-id="d1f74-109">For more information, see [System.Math Methods](system-math-methods.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1f74-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d1f74-110">See also</span></span>

- [<span data-ttu-id="d1f74-111">Tipi di dati e funzioni</span><span class="sxs-lookup"><span data-stu-id="d1f74-111">Data Types and Functions</span></span>](data-types-and-functions.md)

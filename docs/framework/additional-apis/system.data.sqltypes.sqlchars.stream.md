---
title: Proprietà SqlChars.Stream (System.Data.SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/19/2018
ms.technology:
- dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlChars.Stream
- System.Data.SqlTypes.SqlChars.get_Stream
- System.Data.SqlTypes.SqlChars.set_Stream
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: 36a6b3f45f0832ed651dc0a613f50e7170517497
ms.sourcegitcommit: 3500c4845f96a91a438a02ef2c6b4eef45a5e2af
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/07/2019
ms.locfileid: "55827682"
---
# <a name="sqlcharsstream-property"></a><span data-ttu-id="335c4-102">Proprietà SqlChars.Stream</span><span class="sxs-lookup"><span data-stu-id="335c4-102">SqlChars.Stream Property</span></span>

<span data-ttu-id="335c4-103">Ottiene o imposta il flusso di caratteri.</span><span class="sxs-lookup"><span data-stu-id="335c4-103">Gets or sets the character stream.</span></span> <span data-ttu-id="335c4-104">L'assembly che contiene questa proprietà ha una relazione di tipo friend SQLAccess.</span><span class="sxs-lookup"><span data-stu-id="335c4-104">The assembly that contains this property has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="335c4-105">Si tratta per l'uso da SQL Server.</span><span class="sxs-lookup"><span data-stu-id="335c4-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="335c4-106">Per altri database, usare il meccanismo di hosting fornito da tale database.</span><span class="sxs-lookup"><span data-stu-id="335c4-106">For other databases, use the hosting mechanism provided by that database.</span></span>

```csharp
internal SqlStreamChars Stream { get; set; }
```

## <a name="property-value"></a><span data-ttu-id="335c4-107">Valore della proprietà</span><span class="sxs-lookup"><span data-stu-id="335c4-107">Property value</span></span>

`System.Data.SqlTypes.SqlStreamChars`\
<span data-ttu-id="335c4-108">Il flusso di caratteri.</span><span class="sxs-lookup"><span data-stu-id="335c4-108">The character stream.</span></span>

## <a name="remarks"></a><span data-ttu-id="335c4-109">Note</span><span class="sxs-lookup"><span data-stu-id="335c4-109">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="335c4-110">Il `SqlChars.Stream` proprietà sono interna e non deve essere utilizzato direttamente nel codice.</span><span class="sxs-lookup"><span data-stu-id="335c4-110">The `SqlChars.Stream` property is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="335c4-111">Microsoft non supporta l'uso di questa proprietà in un'applicazione di produzione in alcuna circostanza.</span><span class="sxs-lookup"><span data-stu-id="335c4-111">Microsoft does not support the use of this property in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="335c4-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="335c4-112">Requirements</span></span>

<span data-ttu-id="335c4-113">**Spazio dei nomi:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="335c4-113">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="335c4-114">**Assembly:** System. Data (in System)</span><span class="sxs-lookup"><span data-stu-id="335c4-114">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="335c4-115">**Versioni di .NET framework:** Disponibile dalla 2.0.</span><span class="sxs-lookup"><span data-stu-id="335c4-115">**.NET Framework versions:** Available since 2.0.</span></span>
---
title: Metodo SqlStreamChars.SetLength(Int64) (System.Data.SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/20/2018
ms.technology:
- dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.SetLength
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: 750b46c2050228f630eaa6be31922869bff15e0a
ms.sourcegitcommit: 3500c4845f96a91a438a02ef2c6b4eef45a5e2af
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/07/2019
ms.locfileid: "55827344"
---
# <a name="sqlstreamcharssetlengthint64-method"></a><span data-ttu-id="e085a-102">Metodo SqlStreamChars.SetLength(Int64)</span><span class="sxs-lookup"><span data-stu-id="e085a-102">SqlStreamChars.SetLength(Int64) Method</span></span>

<span data-ttu-id="e085a-103">Quando sottoposto a override in una classe derivata, rilascia le risorse usate dal flusso.</span><span class="sxs-lookup"><span data-stu-id="e085a-103">When overridden in a derived class, releases the resources used by the stream.</span></span> <span data-ttu-id="e085a-104">L'assembly contenente questo metodo ha una relazione di tipo friend SQLAccess.</span><span class="sxs-lookup"><span data-stu-id="e085a-104">The assembly that contains this method has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="e085a-105">Si tratta per l'uso da SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e085a-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="e085a-106">Per altri database, usare il meccanismo di hosting fornito da tale database.</span><span class="sxs-lookup"><span data-stu-id="e085a-106">For other databases, use the hosting mechanism provided by that database.</span></span>

```csharp
public abstract void SetLength (long value);
```

## <a name="parameters"></a><span data-ttu-id="e085a-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="e085a-107">Parameters</span></span>

`value`\
<span data-ttu-id="e085a-108">Lunghezza desiderata del flusso corrente in byte.</span><span class="sxs-lookup"><span data-stu-id="e085a-108">The desired length of the current stream in bytes.</span></span>

## <a name="remarks"></a><span data-ttu-id="e085a-109">Note</span><span class="sxs-lookup"><span data-stu-id="e085a-109">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="e085a-110">Il `SqlStreamChars.SetLength` metodo è privato e non deve essere utilizzato direttamente nel codice.</span><span class="sxs-lookup"><span data-stu-id="e085a-110">The `SqlStreamChars.SetLength` method is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="e085a-111">Microsoft non supporta l'uso di questo campo in un'applicazione di produzione in alcuna circostanza.</span><span class="sxs-lookup"><span data-stu-id="e085a-111">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="e085a-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e085a-112">Requirements</span></span>

<span data-ttu-id="e085a-113">**Spazio dei nomi:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="e085a-113">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="e085a-114">**Assembly:** System. Data (in System)</span><span class="sxs-lookup"><span data-stu-id="e085a-114">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="e085a-115">**Versioni di .NET framework:** Disponibile dalla 2.0.</span><span class="sxs-lookup"><span data-stu-id="e085a-115">**.NET Framework versions:** Available since 2.0.</span></span>
---
title: Metodo SqlStreamChars.Dispose(Boolean) (System.Data.SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/20/2018
ms.technology: dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.Dispose
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: cc8df68a608000d89dd322b0d396504483bbf372
ms.sourcegitcommit: d938c39afb9216db377d0f0ecdaa53936a851059
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/29/2019
ms.locfileid: "58633725"
---
# <a name="sqlstreamcharsdisposeboolean-method"></a><span data-ttu-id="e2817-102">Metodo SqlStreamChars.Dispose(Boolean)</span><span class="sxs-lookup"><span data-stu-id="e2817-102">SqlStreamChars.Dispose(Boolean) Method</span></span>

<span data-ttu-id="e2817-103">Quando sottoposto a override in una classe derivata, rilascia le risorse usate dal flusso.</span><span class="sxs-lookup"><span data-stu-id="e2817-103">When overridden in a derived class, releases the resources used by the stream.</span></span> <span data-ttu-id="e2817-104">L'assembly contenente questo metodo ha una relazione di tipo friend SQLAccess.</span><span class="sxs-lookup"><span data-stu-id="e2817-104">The assembly that contains this method has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="e2817-105">Si tratta per l'uso da SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e2817-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="e2817-106">Per altri database, usare il meccanismo di hosting fornito da tale database.</span><span class="sxs-lookup"><span data-stu-id="e2817-106">For other databases, use the hosting mechanism provided by that database.</span></span>

```csharp
protected virtual void Dispose (bool disposing);
```

## <a name="parameters"></a><span data-ttu-id="e2817-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="e2817-107">Parameters</span></span>

`disposing`\
<span data-ttu-id="e2817-108">`true` per rilasciare sia le risorse gestite sia quelle non gestite; `false` per rilasciare solo le risorse non gestite.</span><span class="sxs-lookup"><span data-stu-id="e2817-108">`true` to release both managed and unmanaged resources; `false` to release only unmanaged resources.</span></span>

## <a name="remarks"></a><span data-ttu-id="e2817-109">Note</span><span class="sxs-lookup"><span data-stu-id="e2817-109">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="e2817-110">Il `SqlStreamChars.Dispose` metodo è privato e non deve essere utilizzato direttamente nel codice.</span><span class="sxs-lookup"><span data-stu-id="e2817-110">The `SqlStreamChars.Dispose` method is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="e2817-111">Microsoft non supporta l'uso di questo campo in un'applicazione di produzione in alcuna circostanza.</span><span class="sxs-lookup"><span data-stu-id="e2817-111">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="e2817-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e2817-112">Requirements</span></span>

<span data-ttu-id="e2817-113">**Spazio dei nomi:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="e2817-113">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="e2817-114">**Assembly:** System. Data (in System)</span><span class="sxs-lookup"><span data-stu-id="e2817-114">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="e2817-115">**Versioni di .NET framework:** Disponibile dalla 2.0.</span><span class="sxs-lookup"><span data-stu-id="e2817-115">**.NET Framework versions:** Available since 2.0.</span></span>
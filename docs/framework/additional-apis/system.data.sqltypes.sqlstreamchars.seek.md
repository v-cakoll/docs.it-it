---
title: Metodo SqlStreamChars.Seek (Int64, SeekOrigin) (System.Data.SqlTypes)
author: douglaslMS
ms.author: douglasl
ms.date: 12/20/2018
ms.technology:
- dotnet-data
api_name:
- System.Data.SqlTypes.SqlStreamChars.Seek
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: aab3195ec0d300a7f001f98f2d646c85be939356
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2019
ms.locfileid: "54152554"
---
# <a name="sqlstreamcharsseekint64-seekorigin-method"></a><span data-ttu-id="85585-102">Metodo SqlStreamChars.Seek (Int64, SeekOrigin)</span><span class="sxs-lookup"><span data-stu-id="85585-102">SqlStreamChars.Seek(Int64, SeekOrigin) Method</span></span>

<span data-ttu-id="85585-103">Quando ne viene eseguito l'override in una classe derivata, imposta la posizione all'interno del flusso corrente.</span><span class="sxs-lookup"><span data-stu-id="85585-103">When overridden in a derived class, sets the position within the current stream.</span></span> <span data-ttu-id="85585-104">L'assembly contenente questo metodo ha una relazione di tipo friend SQLAccess.</span><span class="sxs-lookup"><span data-stu-id="85585-104">The assembly that contains this method has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="85585-105">Si tratta per l'uso da SQL Server.</span><span class="sxs-lookup"><span data-stu-id="85585-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="85585-106">Per altri database, usare il meccanismo di hosting fornito da tale database.</span><span class="sxs-lookup"><span data-stu-id="85585-106">For other databases, use the hosting mechanism provided by that database.</span></span>

```csharp
public abstract long Seek (long offset, System.IO.SeekOrigin origin);
```

## <a name="parameters"></a><span data-ttu-id="85585-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="85585-107">Parameters</span></span>

`offset`\
<span data-ttu-id="85585-108">Offset dei byte rispetto a `origin`.</span><span class="sxs-lookup"><span data-stu-id="85585-108">A byte offset relative to `origin`.</span></span>

`origin`\
<span data-ttu-id="85585-109">Uno dei valori di enumerazione che indica il punto di riferimento da cui ottenere la nuova posizione.</span><span class="sxs-lookup"><span data-stu-id="85585-109">One of the enumeration values that indicates the reference point from which to obtain the new position.</span></span>

## <a name="returns"></a><span data-ttu-id="85585-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="85585-110">Returns</span></span>

<xref:System.Int32>\
<span data-ttu-id="85585-111">Nuova posizione all'interno del flusso corrente.</span><span class="sxs-lookup"><span data-stu-id="85585-111">The new position within the current stream.</span></span>

## <a name="remarks"></a><span data-ttu-id="85585-112">Note</span><span class="sxs-lookup"><span data-stu-id="85585-112">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="85585-113">Il `SqlStreamChars.Seek` metodo è privato e non deve essere utilizzato direttamente nel codice.</span><span class="sxs-lookup"><span data-stu-id="85585-113">The `SqlStreamChars.Seek` method is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="85585-114">Microsoft non supporta l'uso di questo campo in un'applicazione di produzione in alcuna circostanza.</span><span class="sxs-lookup"><span data-stu-id="85585-114">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="85585-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="85585-115">Requirements</span></span>

<span data-ttu-id="85585-116">**Spazio dei nomi:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="85585-116">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="85585-117">**Assembly:** System. Data (in System)</span><span class="sxs-lookup"><span data-stu-id="85585-117">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="85585-118">**Versioni di .NET framework:** Disponibile dalla 2.0.</span><span class="sxs-lookup"><span data-stu-id="85585-118">**.NET Framework versions:** Available since 2.0.</span></span>
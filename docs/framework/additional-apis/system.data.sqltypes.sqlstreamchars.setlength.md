---
title: Metodo SqlStreamChars.SetLength(Int64) (System.Data.SqlTypes)
author: douglaslMS
ms.author: douglasl
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
ms.openlocfilehash: c7199cbd08e62b1f0391437a0c1864cb9036fe1f
ms.sourcegitcommit: a36cfc9dbbfc04bd88971f96e8a3f8e283c15d42
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/11/2019
ms.locfileid: "54222699"
---
# <a name="sqlstreamcharssetlengthint64-method"></a><span data-ttu-id="73a68-102">Metodo SqlStreamChars.SetLength(Int64)</span><span class="sxs-lookup"><span data-stu-id="73a68-102">SqlStreamChars.SetLength(Int64) Method</span></span>

<span data-ttu-id="73a68-103">Quando sottoposto a override in una classe derivata, rilascia le risorse usate dal flusso.</span><span class="sxs-lookup"><span data-stu-id="73a68-103">When overridden in a derived class, releases the resources used by the stream.</span></span> <span data-ttu-id="73a68-104">L'assembly contenente questo metodo ha una relazione di tipo friend SQLAccess.</span><span class="sxs-lookup"><span data-stu-id="73a68-104">The assembly that contains this method has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="73a68-105">Si tratta per l'uso da SQL Server.</span><span class="sxs-lookup"><span data-stu-id="73a68-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="73a68-106">Per altri database, usare il meccanismo di hosting fornito da tale database.</span><span class="sxs-lookup"><span data-stu-id="73a68-106">For other databases, use the hosting mechanism provided by that database.</span></span>

```csharp
public abstract void SetLength (long value);
```

## <a name="parameters"></a><span data-ttu-id="73a68-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="73a68-107">Parameters</span></span>

`value`\
<span data-ttu-id="73a68-108">Lunghezza desiderata del flusso corrente in byte.</span><span class="sxs-lookup"><span data-stu-id="73a68-108">The desired length of the current stream in bytes.</span></span>

## <a name="remarks"></a><span data-ttu-id="73a68-109">Note</span><span class="sxs-lookup"><span data-stu-id="73a68-109">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="73a68-110">Il `SqlStreamChars.SetLength` metodo è privato e non deve essere utilizzato direttamente nel codice.</span><span class="sxs-lookup"><span data-stu-id="73a68-110">The `SqlStreamChars.SetLength` method is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="73a68-111">Microsoft non supporta l'uso di questo campo in un'applicazione di produzione in alcuna circostanza.</span><span class="sxs-lookup"><span data-stu-id="73a68-111">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="73a68-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="73a68-112">Requirements</span></span>

<span data-ttu-id="73a68-113">**Spazio dei nomi:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="73a68-113">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="73a68-114">**Assembly:** System. Data (in System)</span><span class="sxs-lookup"><span data-stu-id="73a68-114">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="73a68-115">**Versioni di .NET framework:** Disponibile dalla 2.0.</span><span class="sxs-lookup"><span data-stu-id="73a68-115">**.NET Framework versions:** Available since 2.0.</span></span>
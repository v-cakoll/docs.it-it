---
title: Metodo SqlStreamChars.SetLength(Int64) (System.Data.SqlTypes)
author: douglaslMS
ms.author: douglasl
ms.date: 12/20/2018
ms.technology:
- dotnet-data
api_name:
- System.Data.SqlTypes.SqlStreamChars.SetLength
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: 7eb2b1bfe0a3d180b54c41cbca1d645dfb402be7
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2019
ms.locfileid: "54152764"
---
# <a name="sqlstreamcharssetlengthint64-method"></a><span data-ttu-id="d7793-102">Metodo SqlStreamChars.SetLength(Int64)</span><span class="sxs-lookup"><span data-stu-id="d7793-102">SqlStreamChars.SetLength(Int64) Method</span></span>

<span data-ttu-id="d7793-103">Quando sottoposto a override in una classe derivata, rilascia le risorse usate dal flusso.</span><span class="sxs-lookup"><span data-stu-id="d7793-103">When overridden in a derived class, releases the resources used by the stream.</span></span> <span data-ttu-id="d7793-104">L'assembly contenente questo metodo ha una relazione di tipo friend SQLAccess.</span><span class="sxs-lookup"><span data-stu-id="d7793-104">The assembly that contains this method has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="d7793-105">Si tratta per l'uso da SQL Server.</span><span class="sxs-lookup"><span data-stu-id="d7793-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="d7793-106">Per altri database, usare il meccanismo di hosting fornito da tale database.</span><span class="sxs-lookup"><span data-stu-id="d7793-106">For other databases, use the hosting mechanism provided by that database.</span></span>

```csharp
public abstract void SetLength (long value);
```

## <a name="parameters"></a><span data-ttu-id="d7793-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="d7793-107">Parameters</span></span>

`value`\
<span data-ttu-id="d7793-108">Lunghezza desiderata del flusso corrente in byte.</span><span class="sxs-lookup"><span data-stu-id="d7793-108">The desired length of the current stream in bytes.</span></span>

## <a name="remarks"></a><span data-ttu-id="d7793-109">Note</span><span class="sxs-lookup"><span data-stu-id="d7793-109">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="d7793-110">Il `SqlStreamChars.SetLength` metodo è privato e non deve essere utilizzato direttamente nel codice.</span><span class="sxs-lookup"><span data-stu-id="d7793-110">The `SqlStreamChars.SetLength` method is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="d7793-111">Microsoft non supporta l'uso di questo campo in un'applicazione di produzione in alcuna circostanza.</span><span class="sxs-lookup"><span data-stu-id="d7793-111">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="d7793-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d7793-112">Requirements</span></span>

<span data-ttu-id="d7793-113">**Spazio dei nomi:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="d7793-113">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="d7793-114">**Assembly:** System. Data (in System)</span><span class="sxs-lookup"><span data-stu-id="d7793-114">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="d7793-115">**Versioni di .NET framework:** Disponibile dalla 2.0.</span><span class="sxs-lookup"><span data-stu-id="d7793-115">**.NET Framework versions:** Available since 2.0.</span></span>
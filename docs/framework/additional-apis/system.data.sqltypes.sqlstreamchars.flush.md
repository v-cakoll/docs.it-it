---
title: Metodo SqlStreamChars.Flush (System.Data.SqlTypes)
author: douglaslMS
ms.author: douglasl
ms.date: 12/20/2018
ms.technology:
- dotnet-data
api_name:
- System.Data.SqlTypes.SqlStreamChars.Flush
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: ecaf7932a4e832a88b883ceac4746afe6140b38e
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2019
ms.locfileid: "54152744"
---
# <a name="sqlstreamcharsflush-method"></a><span data-ttu-id="55110-102">Metodo SqlStreamChars.Flush</span><span class="sxs-lookup"><span data-stu-id="55110-102">SqlStreamChars.Flush Method</span></span>

<span data-ttu-id="55110-103">Quando ne viene eseguito l'override in una classe derivata, cancella tutti i buffer del flusso e determina la scrittura dei dati memorizzati nel buffer nel dispositivo sottostante.</span><span class="sxs-lookup"><span data-stu-id="55110-103">When overridden in a derived class, clears all buffers for this stream and causes any buffered data to be written to the underlying device.</span></span> <span data-ttu-id="55110-104">L'assembly contenente questo metodo ha una relazione di tipo friend SQLAccess.</span><span class="sxs-lookup"><span data-stu-id="55110-104">The assembly that contains this method has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="55110-105">Si tratta per l'uso da SQL Server.</span><span class="sxs-lookup"><span data-stu-id="55110-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="55110-106">Per altri database, usare il meccanismo di hosting fornito da tale database.</span><span class="sxs-lookup"><span data-stu-id="55110-106">For other databases, use the hosting mechanism provided by that database.</span></span>

## <a name="syntax"></a><span data-ttu-id="55110-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="55110-107">Syntax</span></span>

```csharp
public abstract void Flush ();
```

## <a name="remarks"></a><span data-ttu-id="55110-108">Note</span><span class="sxs-lookup"><span data-stu-id="55110-108">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="55110-109">Il `SqlStreamChars.Flush` metodo è privato e non deve essere utilizzato direttamente nel codice.</span><span class="sxs-lookup"><span data-stu-id="55110-109">The `SqlStreamChars.Flush` method is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="55110-110">Microsoft non supporta l'uso di questo campo in un'applicazione di produzione in alcuna circostanza.</span><span class="sxs-lookup"><span data-stu-id="55110-110">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="55110-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="55110-111">Requirements</span></span>

<span data-ttu-id="55110-112">**Spazio dei nomi:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="55110-112">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="55110-113">**Assembly:** System. Data (in System)</span><span class="sxs-lookup"><span data-stu-id="55110-113">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="55110-114">**Versioni di .NET framework:** Disponibile dalla 2.0.</span><span class="sxs-lookup"><span data-stu-id="55110-114">**.NET Framework versions:** Available since 2.0.</span></span>
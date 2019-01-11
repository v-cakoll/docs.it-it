---
title: Metodo SqlStreamChars.Flush (System.Data.SqlTypes)
author: douglaslMS
ms.author: douglasl
ms.date: 12/20/2018
ms.technology:
- dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.Flush
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: 13c4b9424b5fc16648628e2b1022a7f1621dee88
ms.sourcegitcommit: a36cfc9dbbfc04bd88971f96e8a3f8e283c15d42
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/11/2019
ms.locfileid: "54221362"
---
# <a name="sqlstreamcharsflush-method"></a><span data-ttu-id="0e623-102">Metodo SqlStreamChars.Flush</span><span class="sxs-lookup"><span data-stu-id="0e623-102">SqlStreamChars.Flush Method</span></span>

<span data-ttu-id="0e623-103">Quando ne viene eseguito l'override in una classe derivata, cancella tutti i buffer del flusso e determina la scrittura dei dati memorizzati nel buffer nel dispositivo sottostante.</span><span class="sxs-lookup"><span data-stu-id="0e623-103">When overridden in a derived class, clears all buffers for this stream and causes any buffered data to be written to the underlying device.</span></span> <span data-ttu-id="0e623-104">L'assembly contenente questo metodo ha una relazione di tipo friend SQLAccess.</span><span class="sxs-lookup"><span data-stu-id="0e623-104">The assembly that contains this method has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="0e623-105">Si tratta per l'uso da SQL Server.</span><span class="sxs-lookup"><span data-stu-id="0e623-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="0e623-106">Per altri database, usare il meccanismo di hosting fornito da tale database.</span><span class="sxs-lookup"><span data-stu-id="0e623-106">For other databases, use the hosting mechanism provided by that database.</span></span>

## <a name="syntax"></a><span data-ttu-id="0e623-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0e623-107">Syntax</span></span>

```csharp
public abstract void Flush ();
```

## <a name="remarks"></a><span data-ttu-id="0e623-108">Note</span><span class="sxs-lookup"><span data-stu-id="0e623-108">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="0e623-109">Il `SqlStreamChars.Flush` metodo è privato e non deve essere utilizzato direttamente nel codice.</span><span class="sxs-lookup"><span data-stu-id="0e623-109">The `SqlStreamChars.Flush` method is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="0e623-110">Microsoft non supporta l'uso di questo campo in un'applicazione di produzione in alcuna circostanza.</span><span class="sxs-lookup"><span data-stu-id="0e623-110">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="0e623-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0e623-111">Requirements</span></span>

<span data-ttu-id="0e623-112">**Spazio dei nomi:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="0e623-112">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="0e623-113">**Assembly:** System. Data (in System)</span><span class="sxs-lookup"><span data-stu-id="0e623-113">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="0e623-114">**Versioni di .NET framework:** Disponibile dalla 2.0.</span><span class="sxs-lookup"><span data-stu-id="0e623-114">**.NET Framework versions:** Available since 2.0.</span></span>
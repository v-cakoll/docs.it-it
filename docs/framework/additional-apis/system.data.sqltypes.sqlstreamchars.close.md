---
title: Metodo SqlStreamChars.Close (System.Data.SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/20/2018
ms.technology: dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.Close
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: d0c29bbc5c6bea98cf36e3c2b6bf7825d6843ccc
ms.sourcegitcommit: d938c39afb9216db377d0f0ecdaa53936a851059
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/29/2019
ms.locfileid: "58634024"
---
# <a name="sqlstreamcharsclose-method"></a><span data-ttu-id="c9c76-102">Metodo SqlStreamChars.Close</span><span class="sxs-lookup"><span data-stu-id="c9c76-102">SqlStreamChars.Close Method</span></span>

<span data-ttu-id="c9c76-103">Chiude il flusso corrente e rilascia le risorse di sistema associate al flusso.</span><span class="sxs-lookup"><span data-stu-id="c9c76-103">Closes the current stream and releases any system resources associated with the stream.</span></span> <span data-ttu-id="c9c76-104">L'assembly contenente questo metodo ha una relazione di tipo friend SQLAccess.</span><span class="sxs-lookup"><span data-stu-id="c9c76-104">The assembly that contains this method has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="c9c76-105">Si tratta per l'uso da SQL Server.</span><span class="sxs-lookup"><span data-stu-id="c9c76-105">It's intended for use by SQL Server.</span></span><span data-ttu-id="c9c76-106"> Per altri database, usare il meccanismo di hosting fornito da tale database.</span><span class="sxs-lookup"><span data-stu-id="c9c76-106"> For other databases, use the hosting mechanism provided by that database.</span></span>

```csharp
public virtual void Close ();
```

## <a name="remarks"></a><span data-ttu-id="c9c76-107">Note</span><span class="sxs-lookup"><span data-stu-id="c9c76-107">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="c9c76-108">Il `SqlStreamChars.Close` metodo è privato e non deve essere utilizzato direttamente nel codice.</span><span class="sxs-lookup"><span data-stu-id="c9c76-108">The `SqlStreamChars.Close` method is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="c9c76-109">Microsoft non supporta l'uso di questo campo in un'applicazione di produzione in alcuna circostanza.</span><span class="sxs-lookup"><span data-stu-id="c9c76-109">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="c9c76-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c9c76-110">Requirements</span></span>

<span data-ttu-id="c9c76-111">**Spazio dei nomi:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="c9c76-111">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="c9c76-112">**Assembly:** System. Data (in System)</span><span class="sxs-lookup"><span data-stu-id="c9c76-112">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="c9c76-113">**Versioni di .NET framework:** Disponibile dalla 2.0.</span><span class="sxs-lookup"><span data-stu-id="c9c76-113">**.NET Framework versions:** Available since 2.0.</span></span>
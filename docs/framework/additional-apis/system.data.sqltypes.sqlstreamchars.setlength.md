---
title: Metodo SqlStreamChars. selength (Int64) (System. Data. SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/20/2018
ms.technology: dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.SetLength
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: 291d6e9395581f2370dafc728521a314d54a686d
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2019
ms.locfileid: "72395729"
---
# <a name="sqlstreamcharssetlengthint64-method"></a><span data-ttu-id="66a36-102">Metodo SqlStreamChars. selength (Int64)</span><span class="sxs-lookup"><span data-stu-id="66a36-102">SqlStreamChars.SetLength(Int64) Method</span></span>

<span data-ttu-id="66a36-103">Quando sottoposto a override in una classe derivata, rilascia le risorse usate dal flusso.</span><span class="sxs-lookup"><span data-stu-id="66a36-103">When overridden in a derived class, releases the resources used by the stream.</span></span> <span data-ttu-id="66a36-104">L'assembly che contiene questo metodo ha una relazione friend con SQLAccess. dll.</span><span class="sxs-lookup"><span data-stu-id="66a36-104">The assembly that contains this method has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="66a36-105">È destinato all'uso da SQL Server.</span><span class="sxs-lookup"><span data-stu-id="66a36-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="66a36-106">Per gli altri database, utilizzare il meccanismo di hosting fornito da tale database.</span><span class="sxs-lookup"><span data-stu-id="66a36-106">For other databases, use the hosting mechanism provided by that database.</span></span>

```csharp
public abstract void SetLength (long value);
```

## <a name="parameters"></a><span data-ttu-id="66a36-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="66a36-107">Parameters</span></span>

`value`\
<span data-ttu-id="66a36-108">Lunghezza desiderata del flusso corrente in byte.</span><span class="sxs-lookup"><span data-stu-id="66a36-108">The desired length of the current stream in bytes.</span></span>

## <a name="remarks"></a><span data-ttu-id="66a36-109">Note</span><span class="sxs-lookup"><span data-stu-id="66a36-109">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="66a36-110">Il metodo `SqlStreamChars.SetLength` è privato e non è destinato a essere usato direttamente nel codice.</span><span class="sxs-lookup"><span data-stu-id="66a36-110">The `SqlStreamChars.SetLength` method is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="66a36-111">Microsoft non supporta l'utilizzo di questo metodo in un'applicazione di produzione in qualsiasi circostanza.</span><span class="sxs-lookup"><span data-stu-id="66a36-111">Microsoft does not support the use of this method in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="66a36-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="66a36-112">Requirements</span></span>

<span data-ttu-id="66a36-113">**Spazio dei nomi:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="66a36-113">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="66a36-114">**Assembly:** System. Data (in System. Data. dll)</span><span class="sxs-lookup"><span data-stu-id="66a36-114">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="66a36-115">**Versioni .NET Framework:** Disponibile a partire da 2,0.</span><span class="sxs-lookup"><span data-stu-id="66a36-115">**.NET Framework versions:** Available since 2.0.</span></span>

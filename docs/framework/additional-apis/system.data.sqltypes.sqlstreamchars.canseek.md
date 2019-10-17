---
title: Proprietà SqlStreamChars. CanSeek (System. Data. SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/19/2018
ms.technology: dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.CanSeek
- System.Data.SqlTypes.SqlStreamChars.get_CanSeek
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: eb32978f62b7d46f0abf715e2bca347592c0fda8
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2019
ms.locfileid: "72395770"
---
# <a name="sqlstreamcharscanseek-property"></a><span data-ttu-id="65d1f-102">Proprietà SqlStreamChars. CanSeek</span><span class="sxs-lookup"><span data-stu-id="65d1f-102">SqlStreamChars.CanSeek Property</span></span>

<span data-ttu-id="65d1f-103">Sottoposta a override in una classe derivata, ottiene un valore che indica se il vapore corrente supporta l'operazione di ricerca.</span><span class="sxs-lookup"><span data-stu-id="65d1f-103">When overridden in a derived class, gets a value that indicates whether the current steam supports the seek operation.</span></span> <span data-ttu-id="65d1f-104">L'assembly che contiene questa proprietà ha una relazione friend con SQLAccess. dll.</span><span class="sxs-lookup"><span data-stu-id="65d1f-104">The assembly that contains this property has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="65d1f-105">È destinato all'uso da SQL Server.</span><span class="sxs-lookup"><span data-stu-id="65d1f-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="65d1f-106">Per gli altri database, utilizzare il meccanismo di hosting fornito da tale database.</span><span class="sxs-lookup"><span data-stu-id="65d1f-106">For other databases, use the hosting mechanism provided by that database.</span></span>

```csharp
public abstract bool CanSeek { get; }
```

## <a name="property-value"></a><span data-ttu-id="65d1f-107">Valore proprietà</span><span class="sxs-lookup"><span data-stu-id="65d1f-107">Property value</span></span>

<xref:System.Boolean>\
<span data-ttu-id="65d1f-108">`true` se il vapore corrente supporta l'operazione di ricerca; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="65d1f-108">`true` if the current steam supports the seek operation; otherwise, `false`.</span></span>

## <a name="remarks"></a><span data-ttu-id="65d1f-109">Note</span><span class="sxs-lookup"><span data-stu-id="65d1f-109">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="65d1f-110">La proprietà `SqlStreamChars.CanSeek` è privata e non può essere utilizzata direttamente nel codice.</span><span class="sxs-lookup"><span data-stu-id="65d1f-110">The `SqlStreamChars.CanSeek` property is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="65d1f-111">Microsoft non supporta l'utilizzo di questa proprietà in un'applicazione di produzione in qualsiasi circostanza.</span><span class="sxs-lookup"><span data-stu-id="65d1f-111">Microsoft does not support the use of this property in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="65d1f-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="65d1f-112">Requirements</span></span>

<span data-ttu-id="65d1f-113">**Spazio dei nomi:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="65d1f-113">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="65d1f-114">**Assembly:** System. Data (in System. Data. dll)</span><span class="sxs-lookup"><span data-stu-id="65d1f-114">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="65d1f-115">**Versioni .NET Framework:** Disponibile a partire da 2,0.</span><span class="sxs-lookup"><span data-stu-id="65d1f-115">**.NET Framework versions:** Available since 2.0.</span></span>

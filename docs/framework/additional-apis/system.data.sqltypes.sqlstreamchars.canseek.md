---
title: Proprietà SqlStreamChars.CanSeek (System.Data.SqlTypes)
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
ms.openlocfilehash: 52f88a3551e20c74d7a1144c3cd6859a023980db
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61675181"
---
# <a name="sqlstreamcharscanseek-property"></a><span data-ttu-id="0c816-102">Proprietà SqlStreamChars.CanSeek</span><span class="sxs-lookup"><span data-stu-id="0c816-102">SqlStreamChars.CanSeek Property</span></span>

<span data-ttu-id="0c816-103">Quando sottoposto a override in una classe derivata, ottiene un valore che indica se il flusso corrente supporta l'operazione di ricerca.</span><span class="sxs-lookup"><span data-stu-id="0c816-103">When overridden in a derived class, gets a value that indicates whether the current steam supports the seek operation.</span></span> <span data-ttu-id="0c816-104">L'assembly che contiene questa proprietà ha una relazione di tipo friend SQLAccess.</span><span class="sxs-lookup"><span data-stu-id="0c816-104">The assembly that contains this property has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="0c816-105">Si tratta per l'uso da SQL Server.</span><span class="sxs-lookup"><span data-stu-id="0c816-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="0c816-106">Per altri database, usare il meccanismo di hosting fornito da tale database.</span><span class="sxs-lookup"><span data-stu-id="0c816-106">For other databases, use the hosting mechanism provided by that database.</span></span>

```csharp
public abstract bool CanSeek { get; }
```

## <a name="property-value"></a><span data-ttu-id="0c816-107">Valore della proprietà</span><span class="sxs-lookup"><span data-stu-id="0c816-107">Property value</span></span>

<xref:System.Boolean>\
<span data-ttu-id="0c816-108">`true` Se il flusso corrente supporta l'operazione di ricerca; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="0c816-108">`true` if the current steam supports the seek operation; otherwise, `false`.</span></span>

## <a name="remarks"></a><span data-ttu-id="0c816-109">Note</span><span class="sxs-lookup"><span data-stu-id="0c816-109">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="0c816-110">Il `SqlStreamChars.CanSeek` proprietà è privato e non deve essere utilizzato direttamente nel codice.</span><span class="sxs-lookup"><span data-stu-id="0c816-110">The `SqlStreamChars.CanSeek` property is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="0c816-111">Microsoft non supporta l'uso di questo campo in un'applicazione di produzione in alcuna circostanza.</span><span class="sxs-lookup"><span data-stu-id="0c816-111">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="0c816-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0c816-112">Requirements</span></span>

<span data-ttu-id="0c816-113">**Spazio dei nomi:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="0c816-113">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="0c816-114">**Assembly:** System. Data (in System)</span><span class="sxs-lookup"><span data-stu-id="0c816-114">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="0c816-115">**Versioni di .NET framework:** Disponibile dalla 2.0.</span><span class="sxs-lookup"><span data-stu-id="0c816-115">**.NET Framework versions:** Available since 2.0.</span></span>
---
title: Proprietà SqlStreamChars.Length (System.Data.SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/19/2018
ms.technology:
- dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.Length
- System.Data.SqlTypes.SqlStreamChars.get_Length
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: 3b4e5828a90de7d2f874010b79a9ddbcb8e12341
ms.sourcegitcommit: 3500c4845f96a91a438a02ef2c6b4eef45a5e2af
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/07/2019
ms.locfileid: "55827695"
---
# <a name="sqlstreamcharslength-property"></a><span data-ttu-id="a0c24-102">Proprietà SqlStreamChars.Length</span><span class="sxs-lookup"><span data-stu-id="a0c24-102">SqlStreamChars.Length Property</span></span>

<span data-ttu-id="a0c24-103">Quando sottoposto a override in una classe derivata, ottiene la lunghezza del flusso corrente.</span><span class="sxs-lookup"><span data-stu-id="a0c24-103">When overridden in a derived class, gets the length of the current stream.</span></span> <span data-ttu-id="a0c24-104">L'assembly che contiene questa proprietà ha una relazione di tipo friend SQLAccess.</span><span class="sxs-lookup"><span data-stu-id="a0c24-104">The assembly that contains this property has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="a0c24-105">Si tratta per l'uso da SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a0c24-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="a0c24-106">Per altri database, usare il meccanismo di hosting fornito da tale database.</span><span class="sxs-lookup"><span data-stu-id="a0c24-106">For other databases, use the hosting mechanism provided by that database.</span></span>

## <a name="syntax"></a><span data-ttu-id="a0c24-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a0c24-107">Syntax</span></span>

```csharp
public abstract long Length { get; }
```

## <a name="property-value"></a><span data-ttu-id="a0c24-108">Valore della proprietà</span><span class="sxs-lookup"><span data-stu-id="a0c24-108">Property value</span></span>

<xref:System.Int64>\
<span data-ttu-id="a0c24-109">Lunghezza del flusso.</span><span class="sxs-lookup"><span data-stu-id="a0c24-109">The length of the stream.</span></span>

## <a name="remarks"></a><span data-ttu-id="a0c24-110">Note</span><span class="sxs-lookup"><span data-stu-id="a0c24-110">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="a0c24-111">Il `SqlStreamChars.Length` proprietà è privato e non deve essere utilizzato direttamente nel codice.</span><span class="sxs-lookup"><span data-stu-id="a0c24-111">The `SqlStreamChars.Length` property is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="a0c24-112">Microsoft non supporta l'uso di questo campo in un'applicazione di produzione in alcuna circostanza.</span><span class="sxs-lookup"><span data-stu-id="a0c24-112">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="a0c24-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a0c24-113">Requirements</span></span>

<span data-ttu-id="a0c24-114">**Spazio dei nomi:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="a0c24-114">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="a0c24-115">**Assembly:** System. Data (in System)</span><span class="sxs-lookup"><span data-stu-id="a0c24-115">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="a0c24-116">**Versioni di .NET framework:** Disponibile dalla 2.0.</span><span class="sxs-lookup"><span data-stu-id="a0c24-116">**.NET Framework versions:** Available since 2.0.</span></span>
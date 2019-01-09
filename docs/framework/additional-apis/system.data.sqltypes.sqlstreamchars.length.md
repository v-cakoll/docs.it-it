---
title: Proprietà SqlStreamChars.Length (System.Data.SqlTypes)
author: douglaslMS
ms.author: douglasl
ms.date: 12/19/2018
ms.technology:
- dotnet-data
api_name:
- System.Data.SqlTypes.SqlStreamChars.Length
- System.Data.SqlTypes.SqlStreamChars.get_Length
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: 1ee15641e697a9d5d146f921640c73ff84a5c335
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2019
ms.locfileid: "54152714"
---
# <a name="sqlstreamcharslength-property"></a><span data-ttu-id="36f57-102">Proprietà SqlStreamChars.Length</span><span class="sxs-lookup"><span data-stu-id="36f57-102">SqlStreamChars.Length Property</span></span>

<span data-ttu-id="36f57-103">Quando sottoposto a override in una classe derivata, ottiene la lunghezza del flusso corrente.</span><span class="sxs-lookup"><span data-stu-id="36f57-103">When overridden in a derived class, gets the length of the current stream.</span></span> <span data-ttu-id="36f57-104">L'assembly che contiene questa proprietà ha una relazione di tipo friend SQLAccess.</span><span class="sxs-lookup"><span data-stu-id="36f57-104">The assembly that contains this property has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="36f57-105">Si tratta per l'uso da SQL Server.</span><span class="sxs-lookup"><span data-stu-id="36f57-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="36f57-106">Per altri database, usare il meccanismo di hosting fornito da tale database.</span><span class="sxs-lookup"><span data-stu-id="36f57-106">For other databases, use the hosting mechanism provided by that database.</span></span>

## <a name="syntax"></a><span data-ttu-id="36f57-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="36f57-107">Syntax</span></span>

```csharp
public abstract long Length { get; }
```

## <a name="property-value"></a><span data-ttu-id="36f57-108">Valore della proprietà</span><span class="sxs-lookup"><span data-stu-id="36f57-108">Property value</span></span>

<xref:System.Int64>\
<span data-ttu-id="36f57-109">Lunghezza del flusso.</span><span class="sxs-lookup"><span data-stu-id="36f57-109">The length of the stream.</span></span>

## <a name="remarks"></a><span data-ttu-id="36f57-110">Note</span><span class="sxs-lookup"><span data-stu-id="36f57-110">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="36f57-111">Il `SqlStreamChars.Length` proprietà è privato e non deve essere utilizzato direttamente nel codice.</span><span class="sxs-lookup"><span data-stu-id="36f57-111">The `SqlStreamChars.Length` property is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="36f57-112">Microsoft non supporta l'uso di questo campo in un'applicazione di produzione in alcuna circostanza.</span><span class="sxs-lookup"><span data-stu-id="36f57-112">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="36f57-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="36f57-113">Requirements</span></span>

<span data-ttu-id="36f57-114">**Spazio dei nomi:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="36f57-114">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="36f57-115">**Assembly:** System. Data (in System)</span><span class="sxs-lookup"><span data-stu-id="36f57-115">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="36f57-116">**Versioni di .NET framework:** Disponibile dalla 2.0.</span><span class="sxs-lookup"><span data-stu-id="36f57-116">**.NET Framework versions:** Available since 2.0.</span></span>
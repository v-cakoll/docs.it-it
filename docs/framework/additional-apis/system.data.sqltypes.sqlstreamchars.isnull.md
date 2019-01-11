---
title: Proprietà SqlStreamChars.IsNull (System.Data.SqlTypes)
author: douglaslMS
ms.author: douglasl
ms.date: 12/19/2018
ms.technology:
- dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.IsNull
- System.Data.SqlTypes.SqlStreamChars.get_IsNull
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: 7bef26119e31658b8495df402bbc07341cd84cf7
ms.sourcegitcommit: a36cfc9dbbfc04bd88971f96e8a3f8e283c15d42
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/11/2019
ms.locfileid: "54222558"
---
# <a name="sqlstreamcharsisnull-property"></a><span data-ttu-id="67ca5-102">Proprietà SqlStreamChars.IsNull</span><span class="sxs-lookup"><span data-stu-id="67ca5-102">SqlStreamChars.IsNull Property</span></span>

<span data-ttu-id="67ca5-103">Quando sottoposto a override in una classe derivata, ottiene un valore che indica se il flusso è `null`.</span><span class="sxs-lookup"><span data-stu-id="67ca5-103">When overridden in a derived class, gets a value that indicates whether the stream is `null`.</span></span> <span data-ttu-id="67ca5-104">L'assembly che contiene questa proprietà ha una relazione di tipo friend SQLAccess.</span><span class="sxs-lookup"><span data-stu-id="67ca5-104">The assembly that contains this property has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="67ca5-105">Si tratta per l'uso da SQL Server.</span><span class="sxs-lookup"><span data-stu-id="67ca5-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="67ca5-106">Per altri database, usare il meccanismo di hosting fornito da tale database.</span><span class="sxs-lookup"><span data-stu-id="67ca5-106">For other databases, use the hosting mechanism provided by that database.</span></span>

## <a name="syntax"></a><span data-ttu-id="67ca5-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="67ca5-107">Syntax</span></span>

```csharp
public abstract bool IsNull { get; }
```

## <a name="property-value"></a><span data-ttu-id="67ca5-108">Valore della proprietà</span><span class="sxs-lookup"><span data-stu-id="67ca5-108">Property value</span></span>

<xref:System.Boolean>\
<span data-ttu-id="67ca5-109">`true` Se il flusso `null`; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="67ca5-109">`true` if the stream is `null`; otherwise, `false`.</span></span>

## <a name="remarks"></a><span data-ttu-id="67ca5-110">Note</span><span class="sxs-lookup"><span data-stu-id="67ca5-110">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="67ca5-111">Il `SqlStreamChars.IsNull` proprietà è privato e non deve essere utilizzato direttamente nel codice.</span><span class="sxs-lookup"><span data-stu-id="67ca5-111">The `SqlStreamChars.IsNull` property is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="67ca5-112">Microsoft non supporta l'uso di questo campo in un'applicazione di produzione in alcuna circostanza.</span><span class="sxs-lookup"><span data-stu-id="67ca5-112">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="67ca5-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="67ca5-113">Requirements</span></span>

<span data-ttu-id="67ca5-114">**Spazio dei nomi:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="67ca5-114">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="67ca5-115">**Assembly:** System. Data (in System)</span><span class="sxs-lookup"><span data-stu-id="67ca5-115">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="67ca5-116">**Versioni di .NET framework:** Disponibile dalla 2.0.</span><span class="sxs-lookup"><span data-stu-id="67ca5-116">**.NET Framework versions:** Available since 2.0.</span></span>
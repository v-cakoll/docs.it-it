---
title: Proprietà SqlStreamChars. IsNull (System. Data. SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/19/2018
ms.technology: dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.IsNull
- System.Data.SqlTypes.SqlStreamChars.get_IsNull
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: d80f653724b3ef0a1cadb69a5f72b1d9455597d6
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2019
ms.locfileid: "72395739"
---
# <a name="sqlstreamcharsisnull-property"></a><span data-ttu-id="601df-102">Proprietà SqlStreamChars. IsNull</span><span class="sxs-lookup"><span data-stu-id="601df-102">SqlStreamChars.IsNull Property</span></span>

<span data-ttu-id="601df-103">Sottoposta a override in una classe derivata, ottiene un valore che indica se il flusso è `null`.</span><span class="sxs-lookup"><span data-stu-id="601df-103">When overridden in a derived class, gets a value that indicates whether the stream is `null`.</span></span> <span data-ttu-id="601df-104">L'assembly che contiene questa proprietà ha una relazione friend con SQLAccess. dll.</span><span class="sxs-lookup"><span data-stu-id="601df-104">The assembly that contains this property has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="601df-105">È destinato all'uso da SQL Server.</span><span class="sxs-lookup"><span data-stu-id="601df-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="601df-106">Per gli altri database, utilizzare il meccanismo di hosting fornito da tale database.</span><span class="sxs-lookup"><span data-stu-id="601df-106">For other databases, use the hosting mechanism provided by that database.</span></span>

## <a name="syntax"></a><span data-ttu-id="601df-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="601df-107">Syntax</span></span>

```csharp
public abstract bool IsNull { get; }
```

## <a name="property-value"></a><span data-ttu-id="601df-108">Valore proprietà</span><span class="sxs-lookup"><span data-stu-id="601df-108">Property value</span></span>

<xref:System.Boolean>\
<span data-ttu-id="601df-109">`true` se il flusso è `null`; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="601df-109">`true` if the stream is `null`; otherwise, `false`.</span></span>

## <a name="remarks"></a><span data-ttu-id="601df-110">Note</span><span class="sxs-lookup"><span data-stu-id="601df-110">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="601df-111">La proprietà `SqlStreamChars.IsNull` è privata e non può essere utilizzata direttamente nel codice.</span><span class="sxs-lookup"><span data-stu-id="601df-111">The `SqlStreamChars.IsNull` property is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="601df-112">Microsoft non supporta l'utilizzo di questa proprietà in un'applicazione di produzione in qualsiasi circostanza.</span><span class="sxs-lookup"><span data-stu-id="601df-112">Microsoft does not support the use of this property in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="601df-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="601df-113">Requirements</span></span>

<span data-ttu-id="601df-114">**Spazio dei nomi:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="601df-114">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="601df-115">**Assembly:** System. Data (in System. Data. dll)</span><span class="sxs-lookup"><span data-stu-id="601df-115">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="601df-116">**Versioni .NET Framework:** Disponibile a partire da 2,0.</span><span class="sxs-lookup"><span data-stu-id="601df-116">**.NET Framework versions:** Available since 2.0.</span></span>

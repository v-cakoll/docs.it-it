---
title: Proprietà SqlStreamChars. length (System. Data. SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/19/2018
ms.technology: dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.Length
- System.Data.SqlTypes.SqlStreamChars.get_Length
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: 2171b10d1c0eb7bcad894cc44c5103bdab18b0a5
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2019
ms.locfileid: "72395613"
---
# <a name="sqlstreamcharslength-property"></a><span data-ttu-id="433df-102">Proprietà SqlStreamChars. length</span><span class="sxs-lookup"><span data-stu-id="433df-102">SqlStreamChars.Length Property</span></span>

<span data-ttu-id="433df-103">Quando sottoposto a override in una classe derivata, ottiene la lunghezza del flusso corrente.</span><span class="sxs-lookup"><span data-stu-id="433df-103">When overridden in a derived class, gets the length of the current stream.</span></span> <span data-ttu-id="433df-104">L'assembly che contiene questa proprietà ha una relazione friend con SQLAccess. dll.</span><span class="sxs-lookup"><span data-stu-id="433df-104">The assembly that contains this property has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="433df-105">È destinato all'uso da SQL Server.</span><span class="sxs-lookup"><span data-stu-id="433df-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="433df-106">Per gli altri database, utilizzare il meccanismo di hosting fornito da tale database.</span><span class="sxs-lookup"><span data-stu-id="433df-106">For other databases, use the hosting mechanism provided by that database.</span></span>

## <a name="syntax"></a><span data-ttu-id="433df-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="433df-107">Syntax</span></span>

```csharp
public abstract long Length { get; }
```

## <a name="property-value"></a><span data-ttu-id="433df-108">Valore proprietà</span><span class="sxs-lookup"><span data-stu-id="433df-108">Property value</span></span>

<xref:System.Int64>\
<span data-ttu-id="433df-109">Lunghezza del flusso.</span><span class="sxs-lookup"><span data-stu-id="433df-109">The length of the stream.</span></span>

## <a name="remarks"></a><span data-ttu-id="433df-110">Note</span><span class="sxs-lookup"><span data-stu-id="433df-110">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="433df-111">La proprietà `SqlStreamChars.Length` è privata e non può essere utilizzata direttamente nel codice.</span><span class="sxs-lookup"><span data-stu-id="433df-111">The `SqlStreamChars.Length` property is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="433df-112">Microsoft non supporta l'utilizzo di questa proprietà in un'applicazione di produzione in qualsiasi circostanza.</span><span class="sxs-lookup"><span data-stu-id="433df-112">Microsoft does not support the use of this property in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="433df-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="433df-113">Requirements</span></span>

<span data-ttu-id="433df-114">**Spazio dei nomi:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="433df-114">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="433df-115">**Assembly:** System. Data (in System. Data. dll)</span><span class="sxs-lookup"><span data-stu-id="433df-115">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="433df-116">**Versioni .NET Framework:** Disponibile a partire da 2,0.</span><span class="sxs-lookup"><span data-stu-id="433df-116">**.NET Framework versions:** Available since 2.0.</span></span>

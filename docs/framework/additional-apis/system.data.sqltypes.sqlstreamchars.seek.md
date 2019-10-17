---
title: Metodo SqlStreamChars. Seek (Int64, SeekOrigin) (System. Data. SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/20/2018
ms.technology: dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.Seek
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: db8aba0a86c140ba62af8056011226532d415951
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2019
ms.locfileid: "72395588"
---
# <a name="sqlstreamcharsseekint64-seekorigin-method"></a><span data-ttu-id="1c67c-102">Metodo SqlStreamChars. Seek (Int64, SeekOrigin)</span><span class="sxs-lookup"><span data-stu-id="1c67c-102">SqlStreamChars.Seek(Int64, SeekOrigin) Method</span></span>

<span data-ttu-id="1c67c-103">Quando ne viene eseguito l'override in una classe derivata, imposta la posizione all'interno del flusso corrente.</span><span class="sxs-lookup"><span data-stu-id="1c67c-103">When overridden in a derived class, sets the position within the current stream.</span></span> <span data-ttu-id="1c67c-104">L'assembly che contiene questo metodo ha una relazione friend con SQLAccess. dll.</span><span class="sxs-lookup"><span data-stu-id="1c67c-104">The assembly that contains this method has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="1c67c-105">È destinato all'uso da SQL Server.</span><span class="sxs-lookup"><span data-stu-id="1c67c-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="1c67c-106">Per gli altri database, utilizzare il meccanismo di hosting fornito da tale database.</span><span class="sxs-lookup"><span data-stu-id="1c67c-106">For other databases, use the hosting mechanism provided by that database.</span></span>

```csharp
public abstract long Seek (long offset, System.IO.SeekOrigin origin);
```

## <a name="parameters"></a><span data-ttu-id="1c67c-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="1c67c-107">Parameters</span></span>

`offset`\
<span data-ttu-id="1c67c-108">Offset di byte relativo a `origin`.</span><span class="sxs-lookup"><span data-stu-id="1c67c-108">A byte offset relative to `origin`.</span></span>

`origin`\
<span data-ttu-id="1c67c-109">Uno dei valori di enumerazione che indica il punto di riferimento dal quale ottenere la nuova posizione.</span><span class="sxs-lookup"><span data-stu-id="1c67c-109">One of the enumeration values that indicates the reference point from which to obtain the new position.</span></span>

## <a name="returns"></a><span data-ttu-id="1c67c-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="1c67c-110">Returns</span></span>

<xref:System.Int32>\
<span data-ttu-id="1c67c-111">Nuova posizione all'interno del flusso corrente.</span><span class="sxs-lookup"><span data-stu-id="1c67c-111">The new position within the current stream.</span></span>

## <a name="remarks"></a><span data-ttu-id="1c67c-112">Note</span><span class="sxs-lookup"><span data-stu-id="1c67c-112">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="1c67c-113">Il metodo `SqlStreamChars.Seek` è privato e non è destinato a essere usato direttamente nel codice.</span><span class="sxs-lookup"><span data-stu-id="1c67c-113">The `SqlStreamChars.Seek` method is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="1c67c-114">Microsoft non supporta l'utilizzo di questo metodo in un'applicazione di produzione in qualsiasi circostanza.</span><span class="sxs-lookup"><span data-stu-id="1c67c-114">Microsoft does not support the use of this method in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="1c67c-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1c67c-115">Requirements</span></span>

<span data-ttu-id="1c67c-116">**Spazio dei nomi:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="1c67c-116">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="1c67c-117">**Assembly:** System. Data (in System. Data. dll)</span><span class="sxs-lookup"><span data-stu-id="1c67c-117">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="1c67c-118">**Versioni .NET Framework:** Disponibile a partire da 2,0.</span><span class="sxs-lookup"><span data-stu-id="1c67c-118">**.NET Framework versions:** Available since 2.0.</span></span>

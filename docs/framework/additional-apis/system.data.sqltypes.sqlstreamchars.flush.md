---
title: Metodo SqlStreamChars. Flush (System. Data. SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/20/2018
ms.technology: dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.Flush
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: 38ade5ce38cfe5003b2d06c0d8bb2db1a20bc05b
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2019
ms.locfileid: "72395621"
---
# <a name="sqlstreamcharsflush-method"></a><span data-ttu-id="63912-102">Metodo SqlStreamChars. Flush</span><span class="sxs-lookup"><span data-stu-id="63912-102">SqlStreamChars.Flush Method</span></span>

<span data-ttu-id="63912-103">Quando ne viene eseguito l'override in una classe derivata, cancella tutti i buffer del flusso e determina la scrittura dei dati memorizzati nel buffer nel dispositivo sottostante.</span><span class="sxs-lookup"><span data-stu-id="63912-103">When overridden in a derived class, clears all buffers for this stream and causes any buffered data to be written to the underlying device.</span></span> <span data-ttu-id="63912-104">L'assembly che contiene questo metodo ha una relazione friend con SQLAccess. dll.</span><span class="sxs-lookup"><span data-stu-id="63912-104">The assembly that contains this method has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="63912-105">È destinato all'uso da SQL Server.</span><span class="sxs-lookup"><span data-stu-id="63912-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="63912-106">Per gli altri database, utilizzare il meccanismo di hosting fornito da tale database.</span><span class="sxs-lookup"><span data-stu-id="63912-106">For other databases, use the hosting mechanism provided by that database.</span></span>

## <a name="syntax"></a><span data-ttu-id="63912-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="63912-107">Syntax</span></span>

```csharp
public abstract void Flush ();
```

## <a name="remarks"></a><span data-ttu-id="63912-108">Note</span><span class="sxs-lookup"><span data-stu-id="63912-108">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="63912-109">Il metodo `SqlStreamChars.Flush` è privato e non è destinato a essere usato direttamente nel codice.</span><span class="sxs-lookup"><span data-stu-id="63912-109">The `SqlStreamChars.Flush` method is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="63912-110">Microsoft non supporta l'utilizzo di questo metodo in un'applicazione di produzione in qualsiasi circostanza.</span><span class="sxs-lookup"><span data-stu-id="63912-110">Microsoft does not support the use of this method in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="63912-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="63912-111">Requirements</span></span>

<span data-ttu-id="63912-112">**Spazio dei nomi:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="63912-112">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="63912-113">**Assembly:** System. Data (in System. Data. dll)</span><span class="sxs-lookup"><span data-stu-id="63912-113">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="63912-114">**Versioni .NET Framework:** Disponibile a partire da 2,0.</span><span class="sxs-lookup"><span data-stu-id="63912-114">**.NET Framework versions:** Available since 2.0.</span></span>

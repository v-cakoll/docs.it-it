---
title: Metodo SqlStreamChars. Read (Char [], Int32, Int32) (System. Data. SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/20/2018
ms.technology: dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.Read
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: 9c8a1526e75fdc304022e74a7cc52506762489ea
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2019
ms.locfileid: "72395748"
---
# <a name="sqlstreamcharsreadchar-int32-int32-method"></a><span data-ttu-id="e1ee7-102">Metodo SqlStreamChars. Read (Char [], Int32, Int32)</span><span class="sxs-lookup"><span data-stu-id="e1ee7-102">SqlStreamChars.Read(Char[], Int32, Int32) Method</span></span>

<span data-ttu-id="e1ee7-103">Quando ne viene eseguito l'override in una classe derivata, legge il set successivo di caratteri dal flusso di input.</span><span class="sxs-lookup"><span data-stu-id="e1ee7-103">When overridden in a derived class, reads the next set of characters from the input stream.</span></span> <span data-ttu-id="e1ee7-104">L'assembly che contiene questo metodo ha una relazione friend con SQLAccess. dll.</span><span class="sxs-lookup"><span data-stu-id="e1ee7-104">The assembly that contains this method has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="e1ee7-105">È destinato all'uso da SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e1ee7-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="e1ee7-106">Per gli altri database, utilizzare il meccanismo di hosting fornito da tale database.</span><span class="sxs-lookup"><span data-stu-id="e1ee7-106">For other databases, use the hosting mechanism provided by that database.</span></span>

```csharp
public abstract int Read (char[] buffer, int offset, int count);
```

## <a name="parameters"></a><span data-ttu-id="e1ee7-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="e1ee7-107">Parameters</span></span>

`buffer`\
<span data-ttu-id="e1ee7-108">Matrice di caratteri da leggere.</span><span class="sxs-lookup"><span data-stu-id="e1ee7-108">A char array to read.</span></span>

`offset`\
<span data-ttu-id="e1ee7-109">Offset relativo all'origine.</span><span class="sxs-lookup"><span data-stu-id="e1ee7-109">An offset relative to origin.</span></span>

`count`\
<span data-ttu-id="e1ee7-110">Numero di caratteri da leggere dal flusso corrente.</span><span class="sxs-lookup"><span data-stu-id="e1ee7-110">The number of characters to be read from the current stream.</span></span>

## <a name="returns"></a><span data-ttu-id="e1ee7-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="e1ee7-111">Returns</span></span>

<xref:System.Int32>\
<span data-ttu-id="e1ee7-112">Numero complessivo di caratteri letti nel buffer.</span><span class="sxs-lookup"><span data-stu-id="e1ee7-112">The total number of characters read into the buffer.</span></span>

## <a name="remarks"></a><span data-ttu-id="e1ee7-113">Note</span><span class="sxs-lookup"><span data-stu-id="e1ee7-113">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="e1ee7-114">Il metodo `SqlStreamChars.Read` è privato e non è destinato a essere usato direttamente nel codice.</span><span class="sxs-lookup"><span data-stu-id="e1ee7-114">The `SqlStreamChars.Read` method is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="e1ee7-115">Microsoft non supporta l'utilizzo di questo metodo in un'applicazione di produzione in qualsiasi circostanza.</span><span class="sxs-lookup"><span data-stu-id="e1ee7-115">Microsoft does not support the use of this method in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="e1ee7-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e1ee7-116">Requirements</span></span>

<span data-ttu-id="e1ee7-117">**Spazio dei nomi:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="e1ee7-117">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="e1ee7-118">**Assembly:** System. Data (in System. Data. dll)</span><span class="sxs-lookup"><span data-stu-id="e1ee7-118">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="e1ee7-119">**Versioni .NET Framework:** Disponibile a partire da 2,0.</span><span class="sxs-lookup"><span data-stu-id="e1ee7-119">**.NET Framework versions:** Available since 2.0.</span></span>

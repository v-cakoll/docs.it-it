---
title: Metodo SqlStreamChars.Write (Char [], Int32, Int32) (System.Data.SqlTypes)
author: douglaslMS
ms.author: douglasl
ms.date: 12/20/2018
ms.technology:
- dotnet-data
api_name:
- System.Data.SqlTypes.SqlStreamChars.Write
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: e8c8ee7ab7a744c1a1d18212f1c7f9788c91ea0d
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2019
ms.locfileid: "54152574"
---
# <a name="sqlstreamcharswritechar-int32-int32-method"></a><span data-ttu-id="a3750-102">Metodo SqlStreamChars.Write (Char [], Int32, Int32)</span><span class="sxs-lookup"><span data-stu-id="a3750-102">SqlStreamChars.Write(Char[], Int32, Int32) Method</span></span>

<span data-ttu-id="a3750-103">Quando sottoposto a override in una classe derivata, scrive una sequenza di caratteri nel flusso corrente e fa avanzare la posizione corrente all'interno di questo flusso del numero di caratteri scritti.</span><span class="sxs-lookup"><span data-stu-id="a3750-103">When overridden in a derived class, writes a sequence of characters to the current stream and advances the current position within this stream by the number of characters written.</span></span> <span data-ttu-id="a3750-104">L'assembly contenente questo metodo ha una relazione di tipo friend SQLAccess.</span><span class="sxs-lookup"><span data-stu-id="a3750-104">The assembly that contains this method has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="a3750-105">Si tratta per l'uso da SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a3750-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="a3750-106">Per altri database, usare il meccanismo di hosting fornito da tale database.</span><span class="sxs-lookup"><span data-stu-id="a3750-106">For other databases, use the hosting mechanism provided by that database.</span></span>

```csharp
public abstract void Write (char[] buffer, int offset, int count);
```

## <a name="parameters"></a><span data-ttu-id="a3750-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="a3750-107">Parameters</span></span>

`buffer`  
<span data-ttu-id="a3750-108">Matrice di caratteri da scrivere.</span><span class="sxs-lookup"><span data-stu-id="a3750-108">A char array to write.</span></span>

`offset`  
<span data-ttu-id="a3750-109">Un offset relativo all'origine.</span><span class="sxs-lookup"><span data-stu-id="a3750-109">An offset relative to origin.</span></span>

`count`  
<span data-ttu-id="a3750-110">Il numero di caratteri da scrivere nel flusso corrente.</span><span class="sxs-lookup"><span data-stu-id="a3750-110">The number of characters to be written to the current stream.</span></span>

## <a name="remarks"></a><span data-ttu-id="a3750-111">Note</span><span class="sxs-lookup"><span data-stu-id="a3750-111">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="a3750-112">Il `SqlStreamChars.Write` metodo è privato e non deve essere utilizzato direttamente nel codice.</span><span class="sxs-lookup"><span data-stu-id="a3750-112">The `SqlStreamChars.Write` method is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="a3750-113">Microsoft non supporta l'uso di questo campo in un'applicazione di produzione in alcuna circostanza.</span><span class="sxs-lookup"><span data-stu-id="a3750-113">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="a3750-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a3750-114">Requirements</span></span>

<span data-ttu-id="a3750-115">**Spazio dei nomi:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="a3750-115">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="a3750-116">**Assembly:** System. Data (in System)</span><span class="sxs-lookup"><span data-stu-id="a3750-116">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="a3750-117">**Versioni di .NET framework:** Disponibile dalla 2.0.</span><span class="sxs-lookup"><span data-stu-id="a3750-117">**.NET Framework versions:** Available since 2.0.</span></span>
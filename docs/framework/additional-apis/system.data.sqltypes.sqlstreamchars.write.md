---
title: Metodo SqlStreamChars. Write (Char [], Int32, Int32) (System. Data. SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/20/2018
ms.technology: dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.Write
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: 9d952041122ceb3824712bd81cab7ce4789c9db8
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2019
ms.locfileid: "72395584"
---
# <a name="sqlstreamcharswritechar-int32-int32-method"></a><span data-ttu-id="da022-102">Metodo SqlStreamChars. Write (Char [], Int32, Int32)</span><span class="sxs-lookup"><span data-stu-id="da022-102">SqlStreamChars.Write(Char[], Int32, Int32) Method</span></span>

<span data-ttu-id="da022-103">Quando ne viene eseguito l'override in una classe derivata, scrive una sequenza di caratteri nel flusso corrente e sposta in avanti la posizione corrente all'interno del flusso in base al numero di caratteri scritti.</span><span class="sxs-lookup"><span data-stu-id="da022-103">When overridden in a derived class, writes a sequence of characters to the current stream and advances the current position within this stream by the number of characters written.</span></span> <span data-ttu-id="da022-104">L'assembly che contiene questo metodo ha una relazione friend con SQLAccess. dll.</span><span class="sxs-lookup"><span data-stu-id="da022-104">The assembly that contains this method has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="da022-105">È destinato all'uso da SQL Server.</span><span class="sxs-lookup"><span data-stu-id="da022-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="da022-106">Per gli altri database, utilizzare il meccanismo di hosting fornito da tale database.</span><span class="sxs-lookup"><span data-stu-id="da022-106">For other databases, use the hosting mechanism provided by that database.</span></span>

```csharp
public abstract void Write (char[] buffer, int offset, int count);
```

## <a name="parameters"></a><span data-ttu-id="da022-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="da022-107">Parameters</span></span>

`buffer`  
<span data-ttu-id="da022-108">Matrice di caratteri da scrivere.</span><span class="sxs-lookup"><span data-stu-id="da022-108">A char array to write.</span></span>

`offset`  
<span data-ttu-id="da022-109">Offset relativo all'origine.</span><span class="sxs-lookup"><span data-stu-id="da022-109">An offset relative to origin.</span></span>

`count`  
<span data-ttu-id="da022-110">Numero di caratteri da scrivere nel flusso corrente.</span><span class="sxs-lookup"><span data-stu-id="da022-110">The number of characters to be written to the current stream.</span></span>

## <a name="remarks"></a><span data-ttu-id="da022-111">Note</span><span class="sxs-lookup"><span data-stu-id="da022-111">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="da022-112">Il metodo `SqlStreamChars.Write` è privato e non è destinato a essere usato direttamente nel codice.</span><span class="sxs-lookup"><span data-stu-id="da022-112">The `SqlStreamChars.Write` method is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="da022-113">Microsoft non supporta l'utilizzo di questo metodo per scrivere in un'applicazione di produzione in qualsiasi circostanza.</span><span class="sxs-lookup"><span data-stu-id="da022-113">Microsoft does not support the use of this method write in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="da022-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="da022-114">Requirements</span></span>

<span data-ttu-id="da022-115">**Spazio dei nomi:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="da022-115">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="da022-116">**Assembly:** System. Data (in System. Data. dll)</span><span class="sxs-lookup"><span data-stu-id="da022-116">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="da022-117">**Versioni .NET Framework:** Disponibile a partire da 2,0.</span><span class="sxs-lookup"><span data-stu-id="da022-117">**.NET Framework versions:** Available since 2.0.</span></span>

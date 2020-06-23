---
title: Metodo Exception. PrepForRemoting (System)
description: Esaminare il metodo Exception. PrepForRemoting in .NET. Il metodo aggiunge l'analisi dello stack sul lato server al messaggio prima che l'eccezione venga rigenerata nel client.
ms.date: 10/08/2019
topic_type:
- apiref
api_name:
- System.Exception.PrepForRemoting
api_location:
- mscorlib.dll
api_type:
- Assembly
ms.openlocfilehash: 9ceb73499ae3bb308975e6db5b961bfe40165ba3
ms.sourcegitcommit: 1c37a894c923bea021a3cc38ce7cba946357bbe1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/19/2020
ms.locfileid: "85105266"
---
# <a name="exceptionprepforremoting-method"></a><span data-ttu-id="e0823-104">Metodo Exception.PrepForRemoting</span><span class="sxs-lookup"><span data-stu-id="e0823-104">Exception.PrepForRemoting Method</span></span>

<span data-ttu-id="e0823-105">Conserva la traccia dello stack sul lato server aggiungendola al messaggio prima che l'eccezione venga rigenerata nel sito di chiamata del client.</span><span class="sxs-lookup"><span data-stu-id="e0823-105">Preserves the server-side stack trace by appending it to the message before the exception is rethrown at the client call site.</span></span>

```csharp
internal Exception PrepForRemoting();
```

## <a name="returns"></a><span data-ttu-id="e0823-106">Restituisce</span><span class="sxs-lookup"><span data-stu-id="e0823-106">Returns</span></span>

<xref:System.Exception>  
<span data-ttu-id="e0823-107">Istanza corrente di <xref:System.Exception>.</span><span class="sxs-lookup"><span data-stu-id="e0823-107">This <xref:System.Exception> instance.</span></span>

## <a name="remarks"></a><span data-ttu-id="e0823-108">Commenti</span><span class="sxs-lookup"><span data-stu-id="e0823-108">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="e0823-109">Il `Exception.PrepForRemoting` metodo è interno e non è destinato a essere utilizzato direttamente nel codice.</span><span class="sxs-lookup"><span data-stu-id="e0823-109">The `Exception.PrepForRemoting` method is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="e0823-110">Microsoft non supporta l'utilizzo di questo metodo in un'applicazione di produzione in qualsiasi circostanza.</span><span class="sxs-lookup"><span data-stu-id="e0823-110">Microsoft does not support the use of this method in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="e0823-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e0823-111">Requirements</span></span>

<span data-ttu-id="e0823-112">**Spazio dei nomi:** <xref:System></span><span class="sxs-lookup"><span data-stu-id="e0823-112">**Namespace:** <xref:System></span></span>

<span data-ttu-id="e0823-113">**Assembly:** mscorlib.dll (in mscorlib.dll)</span><span class="sxs-lookup"><span data-stu-id="e0823-113">**Assembly:** mscorlib.dll (in mscorlib.dll)</span></span>

<span data-ttu-id="e0823-114">**Versioni .NET Framework:** Disponibile a partire da 1,0.</span><span class="sxs-lookup"><span data-stu-id="e0823-114">**.NET Framework versions:** Available since 1.0.</span></span>

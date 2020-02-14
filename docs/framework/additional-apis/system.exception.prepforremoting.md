---
title: Metodo Exception. PrepForRemoting (System)
ms.date: 10/08/2019
topic_type:
- apiref
api_name:
- System.Exception.PrepForRemoting
api_location:
- mscorlib.dll
api_type:
- Assembly
ms.openlocfilehash: ce1c24578690a1643b7f5af0e44eaae95ed7b0a2
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "77214890"
---
# <a name="exceptionprepforremoting-method"></a><span data-ttu-id="c24da-102">Metodo Exception.PrepForRemoting</span><span class="sxs-lookup"><span data-stu-id="c24da-102">Exception.PrepForRemoting Method</span></span>

<span data-ttu-id="c24da-103">Conserva la traccia dello stack sul lato server aggiungendola al messaggio prima che l'eccezione venga rigenerata nel sito di chiamata del client.</span><span class="sxs-lookup"><span data-stu-id="c24da-103">Preserves the server-side stack trace by appending it to the message before the exception is rethrown at the client call site.</span></span>

```csharp
internal Exception PrepForRemoting();
```

## <a name="returns"></a><span data-ttu-id="c24da-104">Valori di codice restituiti</span><span class="sxs-lookup"><span data-stu-id="c24da-104">Returns</span></span>

<xref:System.Exception>  
<span data-ttu-id="c24da-105">Istanza corrente di <xref:System.Exception>.</span><span class="sxs-lookup"><span data-stu-id="c24da-105">This <xref:System.Exception> instance.</span></span>

## <a name="remarks"></a><span data-ttu-id="c24da-106">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="c24da-106">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="c24da-107">Il `Exception.PrepForRemoting` metodo è interno e non deve essere usato direttamente nel codice.</span><span class="sxs-lookup"><span data-stu-id="c24da-107">The `Exception.PrepForRemoting` method is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="c24da-108">Microsoft non supporta l'utilizzo di questo metodo in un'applicazione di produzione in qualsiasi circostanza.</span><span class="sxs-lookup"><span data-stu-id="c24da-108">Microsoft does not support the use of this method in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="c24da-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c24da-109">Requirements</span></span>

<span data-ttu-id="c24da-110">**Spazio dei nomi:** <xref:System></span><span class="sxs-lookup"><span data-stu-id="c24da-110">**Namespace:** <xref:System></span></span>

<span data-ttu-id="c24da-111">**Assembly:** mscorlib. dll (in mscorlib. dll)</span><span class="sxs-lookup"><span data-stu-id="c24da-111">**Assembly:** mscorlib.dll (in mscorlib.dll)</span></span>

<span data-ttu-id="c24da-112">**Versioni .NET Framework:** Disponibile a partire da 1,0.</span><span class="sxs-lookup"><span data-stu-id="c24da-112">**.NET Framework versions:** Available since 1.0.</span></span>

---
title: Metodo IXCLRDataMethodInstance::GetRepresentativeEntryAddress
ms.date: 02/01/2019
api.name:
- IXCLRDataMethodInstance::GetRepresentativeEntryAddress
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataMethodInstance::GetRepresentativeEntryAddress
helpviewer.keywords:
- IXCLRDataMethodInstance::GetRepresentativeEntryAddress Method [.NET Framework debugging]
topic_type:
- apiref
author: hoyosjs
ms.author: juhoyosa
ms.openlocfilehash: 5c79e916a06e796fc87b57eb949cccda77b8a9bd
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67744657"
---
# <a name="ixclrdatamethodinstancegetrepresentativeentryaddress-method"></a><span data-ttu-id="6b9c8-102">Metodo IXCLRDataMethodInstance::GetRepresentativeEntryAddress</span><span class="sxs-lookup"><span data-stu-id="6b9c8-102">IXCLRDataMethodInstance::GetRepresentativeEntryAddress Method</span></span>

<span data-ttu-id="6b9c8-103">Ottiene l'indirizzo del punto di ingresso più significativo per la compilazione nativa di tutti i punti di ingresso possibili per un metodo.</span><span class="sxs-lookup"><span data-stu-id="6b9c8-103">Gets the most representative entry point address for the native compilation of all the possible entry points for a method.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="6b9c8-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6b9c8-104">Syntax</span></span>

```cpp
HRESULT GetRepresentativeEntryAddress(
    [out] CLRDATA_ADDRESS* addr
);
```

## <a name="parameters"></a><span data-ttu-id="6b9c8-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="6b9c8-105">Parameters</span></span>

`addr`\
<span data-ttu-id="6b9c8-106">[out] L'indirizzo del punto di ingresso nativo più rappresentativo per il metodo.</span><span class="sxs-lookup"><span data-stu-id="6b9c8-106">[out] The address of the most representative native entry point for the method.</span></span>

## <a name="remarks"></a><span data-ttu-id="6b9c8-107">Note</span><span class="sxs-lookup"><span data-stu-id="6b9c8-107">Remarks</span></span>

<span data-ttu-id="6b9c8-108">Il metodo specificato fa parte di [ `IXCLRDataMethodInstance` interfaccia](ixclrdatamethodinstance-interface.md) e corrisponde al 19 slot della tabella di metodo virtuale.</span><span class="sxs-lookup"><span data-stu-id="6b9c8-108">The provided method is part of the [`IXCLRDataMethodInstance` interface](ixclrdatamethodinstance-interface.md) and corresponds to the 19th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="6b9c8-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6b9c8-109">Requirements</span></span>

<span data-ttu-id="6b9c8-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6b9c8-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="6b9c8-111">**Intestazione:** nessuno</span><span class="sxs-lookup"><span data-stu-id="6b9c8-111">**Header:** None</span></span>  
<span data-ttu-id="6b9c8-112">**Libreria:** nessuno</span><span class="sxs-lookup"><span data-stu-id="6b9c8-112">**Library:** None</span></span>  
<span data-ttu-id="6b9c8-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="6b9c8-113">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="6b9c8-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6b9c8-114">See also</span></span>

- [<span data-ttu-id="6b9c8-115">Debug</span><span class="sxs-lookup"><span data-stu-id="6b9c8-115">Debugging</span></span>](index.md)
- [<span data-ttu-id="6b9c8-116">Interfaccia IXCLRDataMethodInstance</span><span class="sxs-lookup"><span data-stu-id="6b9c8-116">IXCLRDataMethodInstance Interface</span></span>](ixclrdatamethodinstance-interface.md)

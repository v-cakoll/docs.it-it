---
title: 'Metodo IXCLRDataMethodInstance:: GetRepresentativeEntryAddress'
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
ms.openlocfilehash: d9f9e16d243c0f3b45ac24776caea5bb9c32dcc1
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2020
ms.locfileid: "83395747"
---
# <a name="ixclrdatamethodinstancegetrepresentativeentryaddress-method"></a><span data-ttu-id="562fc-102">Metodo IXCLRDataMethodInstance:: GetRepresentativeEntryAddress</span><span class="sxs-lookup"><span data-stu-id="562fc-102">IXCLRDataMethodInstance::GetRepresentativeEntryAddress Method</span></span>

<span data-ttu-id="562fc-103">Ottiene l'indirizzo del punto di ingresso più rappresentativo per la compilazione nativa di tutti i punti di ingresso possibili per un metodo.</span><span class="sxs-lookup"><span data-stu-id="562fc-103">Gets the most representative entry point address for the native compilation of all the possible entry points for a method.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="562fc-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="562fc-104">Syntax</span></span>

```cpp
HRESULT GetRepresentativeEntryAddress(
    [out] CLRDATA_ADDRESS* addr
);
```

## <a name="parameters"></a><span data-ttu-id="562fc-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="562fc-105">Parameters</span></span>

`addr`\
<span data-ttu-id="562fc-106">out Indirizzo del punto di ingresso nativo più rappresentativo per il metodo.</span><span class="sxs-lookup"><span data-stu-id="562fc-106">[out] The address of the most representative native entry point for the method.</span></span>

## <a name="remarks"></a><span data-ttu-id="562fc-107">Commenti</span><span class="sxs-lookup"><span data-stu-id="562fc-107">Remarks</span></span>

<span data-ttu-id="562fc-108">Il metodo fornito fa parte dell' [ `IXCLRDataMethodInstance` interfaccia](ixclrdatamethodinstance-interface.md) e corrisponde al ventesimo slot della tabella del metodo virtuale.</span><span class="sxs-lookup"><span data-stu-id="562fc-108">The provided method is part of the [`IXCLRDataMethodInstance` interface](ixclrdatamethodinstance-interface.md) and corresponds to the 20th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="562fc-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="562fc-109">Requirements</span></span>

<span data-ttu-id="562fc-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="562fc-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="562fc-111">**Intestazione:** Nessuno</span><span class="sxs-lookup"><span data-stu-id="562fc-111">**Header:** None</span></span>  
<span data-ttu-id="562fc-112">**Libreria:** Nessuno</span><span class="sxs-lookup"><span data-stu-id="562fc-112">**Library:** None</span></span>  
<span data-ttu-id="562fc-113">**Versioni .NET Framework:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="562fc-113">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="562fc-114">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="562fc-114">See also</span></span>

- [<span data-ttu-id="562fc-115">Debug</span><span class="sxs-lookup"><span data-stu-id="562fc-115">Debugging</span></span>](index.md)
- [<span data-ttu-id="562fc-116">Interfaccia IXCLRDataMethodInstance</span><span class="sxs-lookup"><span data-stu-id="562fc-116">IXCLRDataMethodInstance Interface</span></span>](ixclrdatamethodinstance-interface.md)

---
title: Metodo ISOSDacInterface::GetMethodDescData
ms.date: 01/16/2019
api.name:
- ISOSDacInterface::GetMethodDescData Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- ISOSDacInterface::GetMethodDescData Method
helpviewer.keywords:
- ISOSDacInterface::GetMethodDescData Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: e56f837c4d3362ec6e71030e4fb475df42b9fba4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54639952"
---
# <a name="isosdacinterfacegetmethoddescdata-method"></a><span data-ttu-id="41506-102">Metodo ISOSDacInterface::GetMethodDescData</span><span class="sxs-lookup"><span data-stu-id="41506-102">ISOSDacInterface::GetMethodDescData Method</span></span>

<span data-ttu-id="41506-103">Ottiene i dati per il dato [MethodDesc](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md).</span><span class="sxs-lookup"><span data-stu-id="41506-103">Gets the data for the given [MethodDesc](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md).</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="41506-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="41506-104">Syntax</span></span>

```
HRESULT GetMethodDescData(
    CLRDATA_ADDRESS            methodDesc,
    CLRDATA_ADDRESS            ip,
    void                       *data,
    ULONG                      cRevertedRejitVersions,
    void                      *rgRevertedRejitData,
    void                      *pcNeededRevertedRejitData
);
```

### <a name="parameters"></a><span data-ttu-id="41506-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="41506-105">Parameters</span></span>

<span data-ttu-id="41506-106">`methodDesc` [in] L'indirizzo del MethodDesc.</span><span class="sxs-lookup"><span data-stu-id="41506-106">`methodDesc` [in] The address of the MethodDesc.</span></span>

<span data-ttu-id="41506-107">`ip` [in] L'indirizzo IP del metodo.</span><span class="sxs-lookup"><span data-stu-id="41506-107">`ip` [in] The IP address of the method.</span></span>

<span data-ttu-id="41506-108">`data` [out] I dati associati con la MethodDesc come restituito dall'API interne.</span><span class="sxs-lookup"><span data-stu-id="41506-108">`data` [out] The data associated with the MethodDesc as returned from the internal APIs.</span></span> <span data-ttu-id="41506-109">La struttura deve almeno 168 byte.</span><span class="sxs-lookup"><span data-stu-id="41506-109">The structure needs at least 168 bytes.</span></span>

<span data-ttu-id="41506-110">`cRevertedRejitVersions` [out] Il numero di versioni rejit ripristinato.</span><span class="sxs-lookup"><span data-stu-id="41506-110">`cRevertedRejitVersions` [out] The number of reverted rejit versions.</span></span>

<span data-ttu-id="41506-111">`rgRevertedRejitData` [out] I dati associati con le versioni rejit ripristinato come restituito dall'API interne.</span><span class="sxs-lookup"><span data-stu-id="41506-111">`rgRevertedRejitData` [out] The data associated with the reverted rejit versions as returned from the internal APIs.</span></span> <span data-ttu-id="41506-112">La struttura deve almeno 24 byte.</span><span class="sxs-lookup"><span data-stu-id="41506-112">The structure needs at least 24 bytes.</span></span>

<span data-ttu-id="41506-113">`pcNeededRevertedRejitData` [out] Il numero di byte necessari per archiviare i dati associati con le versioni ReJit ripristinate.</span><span class="sxs-lookup"><span data-stu-id="41506-113">`pcNeededRevertedRejitData` [out] The number of bytes required to store the data associated with the reverted ReJit versions.</span></span>

## <a name="remarks"></a><span data-ttu-id="41506-114">Note</span><span class="sxs-lookup"><span data-stu-id="41506-114">Remarks</span></span>

<span data-ttu-id="41506-115">Il metodo specificato fa parte di `ISOSDacInterface` interfaccia e corrisponde al 20 ° slot della tabella di metodo virtuale.</span><span class="sxs-lookup"><span data-stu-id="41506-115">The provided method is part of the `ISOSDacInterface` interface and corresponds to the 20th slot of the virtual method table.</span></span> <span data-ttu-id="41506-116">Anche il `CLRDATA_ADDRESS` sono valori integer senza segno a 64 bit.</span><span class="sxs-lookup"><span data-stu-id="41506-116">Also the `CLRDATA_ADDRESS` are 64-bit unsigned integer.</span></span>

## <a name="requirements"></a><span data-ttu-id="41506-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="41506-117">Requirements</span></span>

<span data-ttu-id="41506-118">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="41506-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="41506-119">**Intestazione:** nessuno</span><span class="sxs-lookup"><span data-stu-id="41506-119">**Header:** None</span></span>  
<span data-ttu-id="41506-120">**Libreria:** nessuno</span><span class="sxs-lookup"><span data-stu-id="41506-120">**Library:** None</span></span>  
<span data-ttu-id="41506-121">**Versioni di .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="41506-121">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="41506-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="41506-122">See also</span></span>

- [<span data-ttu-id="41506-123">Debug</span><span class="sxs-lookup"><span data-stu-id="41506-123">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="41506-124">Interfaccia ISOSDacInterface</span><span class="sxs-lookup"><span data-stu-id="41506-124">ISOSDacInterface Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/isosdacinterface-interface.md)

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
ms.openlocfilehash: 47cea4810b764005e87d00966c15cf138f5913a7
ms.sourcegitcommit: 3500c4845f96a91a438a02ef2c6b4eef45a5e2af
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/07/2019
ms.locfileid: "55825953"
---
# <a name="isosdacinterfacegetmethoddescdata-method"></a><span data-ttu-id="cce42-102">Metodo ISOSDacInterface::GetMethodDescData</span><span class="sxs-lookup"><span data-stu-id="cce42-102">ISOSDacInterface::GetMethodDescData Method</span></span>

<span data-ttu-id="cce42-103">Ottiene i dati per il puntatore MethodDesc specificato.</span><span class="sxs-lookup"><span data-stu-id="cce42-103">Gets the data for the given MethodDesc pointer.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="cce42-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cce42-104">Syntax</span></span>

```
HRESULT GetMethodDescData(
    CLRDATA_ADDRESS            methodDesc,
    CLRDATA_ADDRESS            ip,
    DacpMethodDescData *data,
    ULONG                      cRevertedRejitVersions,
    DacpReJitData      *rgRevertedRejitData,
    void                      *pcNeededRevertedRejitData
);
```

### <a name="parameters"></a><span data-ttu-id="cce42-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="cce42-105">Parameters</span></span>

<span data-ttu-id="cce42-106">`methodDesc` [in] L'indirizzo del MethodDesc.</span><span class="sxs-lookup"><span data-stu-id="cce42-106">`methodDesc` [in] The address of the MethodDesc.</span></span>

<span data-ttu-id="cce42-107">`ip` [in] L'indirizzo IP del metodo.</span><span class="sxs-lookup"><span data-stu-id="cce42-107">`ip` [in] The IP address of the method.</span></span>

<span data-ttu-id="cce42-108">`data` [out] I dati associati con la MethodDesc come restituito dall'API interne.</span><span class="sxs-lookup"><span data-stu-id="cce42-108">`data` [out] The data associated with the MethodDesc as returned from the internal APIs.</span></span>

<span data-ttu-id="cce42-109">`cRevertedRejitVersions` [out] Il numero di versioni rejit ripristinato.</span><span class="sxs-lookup"><span data-stu-id="cce42-109">`cRevertedRejitVersions` [out] The number of reverted rejit versions.</span></span>

<span data-ttu-id="cce42-110">`rgRevertedRejitData` [out] I dati associati con le versioni rejit ripristinato come restituito dall'API interne.</span><span class="sxs-lookup"><span data-stu-id="cce42-110">`rgRevertedRejitData` [out] The data associated with the reverted rejit versions as returned from the internal APIs.</span></span>

<span data-ttu-id="cce42-111">`pcNeededRevertedRejitData` [out] Il numero di byte necessari per archiviare i dati associati con le versioni ReJit ripristinate.</span><span class="sxs-lookup"><span data-stu-id="cce42-111">`pcNeededRevertedRejitData` [out] The number of bytes required to store the data associated with the reverted ReJit versions.</span></span>

## <a name="remarks"></a><span data-ttu-id="cce42-112">Note</span><span class="sxs-lookup"><span data-stu-id="cce42-112">Remarks</span></span>

<span data-ttu-id="cce42-113">Il metodo specificato fa parte di `ISOSDacInterface` interfaccia e corrisponde al 20 ° slot della tabella di metodo virtuale.</span><span class="sxs-lookup"><span data-stu-id="cce42-113">The provided method is part of the `ISOSDacInterface` interface and corresponds to the 20th slot of the virtual method table.</span></span> <span data-ttu-id="cce42-114">Per poter utilizzarli [ `CLRDATA_ADDRESS` ](../common-data-types-unmanaged-api-reference.md) deve essere definito come un intero senza segno a 64 bit.</span><span class="sxs-lookup"><span data-stu-id="cce42-114">To be able to use them, [`CLRDATA_ADDRESS`](../common-data-types-unmanaged-api-reference.md) must be defined as a 64-bit unsigned integer.</span></span>

## <a name="requirements"></a><span data-ttu-id="cce42-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="cce42-115">Requirements</span></span>

<span data-ttu-id="cce42-116">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cce42-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="cce42-117">**Intestazione:** nessuno</span><span class="sxs-lookup"><span data-stu-id="cce42-117">**Header:** None</span></span>  
<span data-ttu-id="cce42-118">**Libreria:** nessuno</span><span class="sxs-lookup"><span data-stu-id="cce42-118">**Library:** None</span></span>  
<span data-ttu-id="cce42-119">**Versioni di .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="cce42-119">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="cce42-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cce42-120">See also</span></span>

- [<span data-ttu-id="cce42-121">Debug</span><span class="sxs-lookup"><span data-stu-id="cce42-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="cce42-122">Interfaccia ISOSDacInterface</span><span class="sxs-lookup"><span data-stu-id="cce42-122">ISOSDacInterface Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/isosdacinterface-interface.md)

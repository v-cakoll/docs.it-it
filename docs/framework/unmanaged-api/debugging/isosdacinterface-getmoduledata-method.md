---
title: Metodo ISOSDacInterface::GetModuleData
ms.date: 02/01/2019
api.name:
- ISOSDacInterface::GetModuleData Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- ISOSDacInterface::GetModuleData Method
helpviewer.keywords:
- ISOSDacInterface::GetModuleData Method [.NET Framework debugging]
topic_type:
- apiref
author: hoyosjs
ms.author: juhoyosa
ms.openlocfilehash: 80b15f076dfe7a7bbbe7e28d9d68f01255e47202
ms.sourcegitcommit: 3500c4845f96a91a438a02ef2c6b4eef45a5e2af
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/07/2019
ms.locfileid: "55828609"
---
# <a name="isosdacinterfacegetmoduledata-method"></a><span data-ttu-id="55354-102">Metodo ISOSDacInterface::GetModuleData</span><span class="sxs-lookup"><span data-stu-id="55354-102">ISOSDacInterface::GetModuleData Method</span></span>

<span data-ttu-id="55354-103">Recupera i dati corrispondenti al modulo caricato in un determinato indirizzo.</span><span class="sxs-lookup"><span data-stu-id="55354-103">Fetches the data corresponding to the module loaded at a given address.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="55354-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="55354-104">Syntax</span></span>

```
HRESULT GetModuleData(
    CLRDATA_ADDRESS moduleAddr,
    DacpModuleData *data
);
```

### <a name="parameters"></a><span data-ttu-id="55354-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="55354-105">Parameters</span></span>

<span data-ttu-id="55354-106">`moduleAddr` [in] L'indirizzo del modulo per recuperare informazioni per.</span><span class="sxs-lookup"><span data-stu-id="55354-106">`moduleAddr` [in] The address of the module to retrieve information for.</span></span>

<span data-ttu-id="55354-107">`data` [out] Il [DacpModuleData struttura](dacpmoduledata-structure.md) per contenere le informazioni del modulo caricato.</span><span class="sxs-lookup"><span data-stu-id="55354-107">`data` [out] The [DacpModuleData structure](dacpmoduledata-structure.md) to hold the information of the loaded module.</span></span>


## <a name="remarks"></a><span data-ttu-id="55354-108">Note</span><span class="sxs-lookup"><span data-stu-id="55354-108">Remarks</span></span>

<span data-ttu-id="55354-109">Il metodo specificato fa parte di `ISOSDacInterface` interfaccia e corrisponde al 13 slot della tabella di metodo virtuale.</span><span class="sxs-lookup"><span data-stu-id="55354-109">The provided method is part of the `ISOSDacInterface` interface and corresponds to the 13th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="55354-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="55354-110">Requirements</span></span>

<span data-ttu-id="55354-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="55354-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="55354-112">**Intestazione:** nessuno</span><span class="sxs-lookup"><span data-stu-id="55354-112">**Header:** None</span></span>  
<span data-ttu-id="55354-113">**Libreria:** nessuno</span><span class="sxs-lookup"><span data-stu-id="55354-113">**Library:** None</span></span>  
<span data-ttu-id="55354-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="55354-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="55354-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="55354-115">See also</span></span>

- [<span data-ttu-id="55354-116">Debug</span><span class="sxs-lookup"><span data-stu-id="55354-116">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="55354-117">Interfaccia ISOSDacInterface</span><span class="sxs-lookup"><span data-stu-id="55354-117">ISOSDacInterface Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/isosdacinterface-interface.md)

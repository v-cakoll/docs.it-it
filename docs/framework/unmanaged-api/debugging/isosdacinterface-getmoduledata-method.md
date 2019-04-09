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
ms.openlocfilehash: 128af261c429228c97d952f1f8d382f46306f711
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59229316"
---
# <a name="isosdacinterfacegetmoduledata-method"></a><span data-ttu-id="efa92-102">Metodo ISOSDacInterface::GetModuleData</span><span class="sxs-lookup"><span data-stu-id="efa92-102">ISOSDacInterface::GetModuleData Method</span></span>

<span data-ttu-id="efa92-103">Recupera i dati corrispondenti al modulo caricato in un determinato indirizzo.</span><span class="sxs-lookup"><span data-stu-id="efa92-103">Fetches the data corresponding to the module loaded at a given address.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="efa92-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="efa92-104">Syntax</span></span>

```
HRESULT GetModuleData(
    CLRDATA_ADDRESS moduleAddr,
    DacpModuleData *data
);
```

## <a name="parameters"></a><span data-ttu-id="efa92-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="efa92-105">Parameters</span></span>

`moduleAddr`\
<span data-ttu-id="efa92-106">[in] L'indirizzo del modulo per recuperare informazioni per.</span><span class="sxs-lookup"><span data-stu-id="efa92-106">[in] The address of the module to retrieve information for.</span></span>

`data`\
<span data-ttu-id="efa92-107">[out] Il [DacpModuleData struttura](dacpmoduledata-structure.md) per contenere le informazioni del modulo caricato.</span><span class="sxs-lookup"><span data-stu-id="efa92-107">[out] The [DacpModuleData structure](dacpmoduledata-structure.md) to hold the information of the loaded module.</span></span>

## <a name="remarks"></a><span data-ttu-id="efa92-108">Note</span><span class="sxs-lookup"><span data-stu-id="efa92-108">Remarks</span></span>

<span data-ttu-id="efa92-109">Il metodo specificato fa parte di `ISOSDacInterface` interfaccia e corrisponde al 13 slot della tabella di metodo virtuale.</span><span class="sxs-lookup"><span data-stu-id="efa92-109">The provided method is part of the `ISOSDacInterface` interface and corresponds to the 13th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="efa92-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="efa92-110">Requirements</span></span>

<span data-ttu-id="efa92-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="efa92-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="efa92-112">**Intestazione:** nessuno</span><span class="sxs-lookup"><span data-stu-id="efa92-112">**Header:** None</span></span>  
<span data-ttu-id="efa92-113">**Libreria:** nessuno</span><span class="sxs-lookup"><span data-stu-id="efa92-113">**Library:** None</span></span>  
**<span data-ttu-id="efa92-114">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="efa92-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a><span data-ttu-id="efa92-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="efa92-115">See also</span></span>

- [<span data-ttu-id="efa92-116">Debug</span><span class="sxs-lookup"><span data-stu-id="efa92-116">Debugging</span></span>](index.md)
- [<span data-ttu-id="efa92-117">Interfaccia ISOSDacInterface</span><span class="sxs-lookup"><span data-stu-id="efa92-117">ISOSDacInterface Interface</span></span>](isosdacinterface-interface.md)
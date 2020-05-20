---
title: 'Metodo ISOSDacInterface:: GetModuleData'
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
ms.openlocfilehash: b302100eb6cbfa83896cd358762c496ea01f7509
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420981"
---
# <a name="isosdacinterfacegetmoduledata-method"></a><span data-ttu-id="8c417-102">Metodo ISOSDacInterface:: GetModuleData</span><span class="sxs-lookup"><span data-stu-id="8c417-102">ISOSDacInterface::GetModuleData Method</span></span>

<span data-ttu-id="8c417-103">Recupera i dati corrispondenti al modulo caricato a un indirizzo specificato.</span><span class="sxs-lookup"><span data-stu-id="8c417-103">Fetches the data corresponding to the module loaded at a given address.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="8c417-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8c417-104">Syntax</span></span>

```cpp
HRESULT GetModuleData(
    CLRDATA_ADDRESS moduleAddr,
    DacpModuleData *data
);
```

## <a name="parameters"></a><span data-ttu-id="8c417-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="8c417-105">Parameters</span></span>

`moduleAddr`\
<span data-ttu-id="8c417-106">in Indirizzo del modulo per il quale recuperare le informazioni.</span><span class="sxs-lookup"><span data-stu-id="8c417-106">[in] The address of the module to retrieve information for.</span></span>

`data`\
<span data-ttu-id="8c417-107">out [Struttura DacpModuleData](dacpmoduledata-structure.md) che consente di conservare le informazioni del modulo caricato.</span><span class="sxs-lookup"><span data-stu-id="8c417-107">[out] The [DacpModuleData structure](dacpmoduledata-structure.md) to hold the information of the loaded module.</span></span>

## <a name="remarks"></a><span data-ttu-id="8c417-108">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="8c417-108">Remarks</span></span>

<span data-ttu-id="8c417-109">Il metodo fornito fa parte dell' `ISOSDacInterface` interfaccia e corrisponde al quattordicesimo slot della tabella del metodo virtuale.</span><span class="sxs-lookup"><span data-stu-id="8c417-109">The provided method is part of the `ISOSDacInterface` interface and corresponds to the 14th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="8c417-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8c417-110">Requirements</span></span>

<span data-ttu-id="8c417-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8c417-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="8c417-112">**Intestazione:** Nessuno</span><span class="sxs-lookup"><span data-stu-id="8c417-112">**Header:** None</span></span>  
<span data-ttu-id="8c417-113">**Libreria:** Nessuno</span><span class="sxs-lookup"><span data-stu-id="8c417-113">**Library:** None</span></span>  
<span data-ttu-id="8c417-114">**Versioni .NET Framework:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="8c417-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="8c417-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8c417-115">See also</span></span>

- [<span data-ttu-id="8c417-116">Debug</span><span class="sxs-lookup"><span data-stu-id="8c417-116">Debugging</span></span>](index.md)
- [<span data-ttu-id="8c417-117">Interfaccia ISOSDacInterface</span><span class="sxs-lookup"><span data-stu-id="8c417-117">ISOSDacInterface Interface</span></span>](isosdacinterface-interface.md)

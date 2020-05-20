---
title: 'Metodo IXCLRDataProcess:: StartEnumModules'
ms.date: 01/16/2019
api.name:
- IXCLRDataProcess::StartEnumModules Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataProcess::StartEnumModules Method
helpviewer.keywords:
- IXCLRDataProcess::StartEnumModules Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: d55b07ea3fada73237919bf677163a9096d5ad04
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420721"
---
# <a name="ixclrdataprocessstartenummodules-method"></a><span data-ttu-id="65f50-102">Metodo IXCLRDataProcess:: StartEnumModules</span><span class="sxs-lookup"><span data-stu-id="65f50-102">IXCLRDataProcess::StartEnumModules Method</span></span>

<span data-ttu-id="65f50-103">Fornisce un handle per enumerare i moduli di un processo.</span><span class="sxs-lookup"><span data-stu-id="65f50-103">Provides a handle to enumerate the modules of a process.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="65f50-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="65f50-104">Syntax</span></span>

```cpp
HRESULT StartEnumModules(
    [out] CLRDATA_ENUM *handle
);
```

## <a name="parameters"></a><span data-ttu-id="65f50-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="65f50-105">Parameters</span></span>

`handle`\
<span data-ttu-id="65f50-106">out Handle per l'enumerazione dei moduli.</span><span class="sxs-lookup"><span data-stu-id="65f50-106">[out] A handle for enumerating the modules.</span></span>

## <a name="remarks"></a><span data-ttu-id="65f50-107">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="65f50-107">Remarks</span></span>

<span data-ttu-id="65f50-108">Il metodo fornito fa parte dell' `IXCLRDataProcess` interfaccia e corrisponde al ventiquattresimo slot della tabella del metodo virtuale.</span><span class="sxs-lookup"><span data-stu-id="65f50-108">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 24th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="65f50-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="65f50-109">Requirements</span></span>

<span data-ttu-id="65f50-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="65f50-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="65f50-111">**Intestazione:** Nessuno</span><span class="sxs-lookup"><span data-stu-id="65f50-111">**Header:** None</span></span>  
<span data-ttu-id="65f50-112">**Libreria:** Nessuno</span><span class="sxs-lookup"><span data-stu-id="65f50-112">**Library:** None</span></span>  
<span data-ttu-id="65f50-113">**Versioni .NET Framework:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="65f50-113">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="65f50-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="65f50-114">See also</span></span>

- [<span data-ttu-id="65f50-115">Enumerazione CLRDataSourceType</span><span class="sxs-lookup"><span data-stu-id="65f50-115">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="65f50-116">Debug</span><span class="sxs-lookup"><span data-stu-id="65f50-116">Debugging</span></span>](index.md)
- [<span data-ttu-id="65f50-117">Interfaccia IXCLRDataProcess</span><span class="sxs-lookup"><span data-stu-id="65f50-117">IXCLRDataProcess Interface</span></span>](ixclrdataprocess-interface.md)

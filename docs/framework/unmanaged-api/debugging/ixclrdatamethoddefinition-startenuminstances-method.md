---
title: 'Metodo IXCLRDataMethodDefinition:: StartEnumInstances'
ms.date: 01/16/2019
api.name:
- IXCLRDataMethodDefinition::StartEnumInstances Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataMethodDefinition::StartEnumInstances Method
helpviewer.keywords:
- IXCLRDataMethodDefinition::StartEnumInstances Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: b0c37c666f23f04239ed827246b87c43ee8d5ad9
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420929"
---
# <a name="ixclrdatamethoddefinitionstartenuminstances-method"></a><span data-ttu-id="5b960-102">Metodo IXCLRDataMethodDefinition:: StartEnumInstances</span><span class="sxs-lookup"><span data-stu-id="5b960-102">IXCLRDataMethodDefinition::StartEnumInstances Method</span></span>

<span data-ttu-id="5b960-103">Fornisce un handle per l'enumerazione delle istanze del metodo per un oggetto specificato `IXCLRDataAppDomain` .</span><span class="sxs-lookup"><span data-stu-id="5b960-103">Provides a handle for the enumeration of method instances for a given `IXCLRDataAppDomain`.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="5b960-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5b960-104">Syntax</span></span>

```cpp
HRESULT StartEnumInstances(
    [in] IXCLRDataAppDomain* appDomain,
    [out] CLRDATA_ENUM *handle
);
```

## <a name="parameters"></a><span data-ttu-id="5b960-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="5b960-105">Parameters</span></span>

`appDomain`\
<span data-ttu-id="5b960-106">in AppDomain per l'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="5b960-106">[in] An AppDomain for the enumeration.</span></span>

`handle`\
<span data-ttu-id="5b960-107">out Handle per l'enumerazione delle istanze.</span><span class="sxs-lookup"><span data-stu-id="5b960-107">[out] A handle for enumerating the instances.</span></span>

## <a name="remarks"></a><span data-ttu-id="5b960-108">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="5b960-108">Remarks</span></span>

<span data-ttu-id="5b960-109">Il metodo fornito fa parte dell' `IXCLRDataMethodDefinition` interfaccia e corrisponde al quinto slot della tabella del metodo virtuale.</span><span class="sxs-lookup"><span data-stu-id="5b960-109">The provided method is part of the `IXCLRDataMethodDefinition` interface and corresponds to the 5th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="5b960-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5b960-110">Requirements</span></span>

<span data-ttu-id="5b960-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5b960-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="5b960-112">**Intestazione:** Nessuno</span><span class="sxs-lookup"><span data-stu-id="5b960-112">**Header:** None</span></span>  
<span data-ttu-id="5b960-113">**Libreria:** Nessuno</span><span class="sxs-lookup"><span data-stu-id="5b960-113">**Library:** None</span></span>  
<span data-ttu-id="5b960-114">**Versioni .NET Framework:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="5b960-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="5b960-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5b960-115">See also</span></span>

- [<span data-ttu-id="5b960-116">Enumerazione CLRDataSourceType</span><span class="sxs-lookup"><span data-stu-id="5b960-116">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="5b960-117">Debug</span><span class="sxs-lookup"><span data-stu-id="5b960-117">Debugging</span></span>](index.md)
- [<span data-ttu-id="5b960-118">Interfaccia IXCLRDataMethodDefinition</span><span class="sxs-lookup"><span data-stu-id="5b960-118">IXCLRDataMethodDefinition Interface</span></span>](ixclrdatamethoddefinition-interface.md)

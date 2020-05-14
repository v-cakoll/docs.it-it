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
ms.openlocfilehash: 84e0ad392c5fee8377115427482d80543454fff3
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2020
ms.locfileid: "83397202"
---
# <a name="ixclrdatamethoddefinitionstartenuminstances-method"></a><span data-ttu-id="5ae75-102">Metodo IXCLRDataMethodDefinition:: StartEnumInstances</span><span class="sxs-lookup"><span data-stu-id="5ae75-102">IXCLRDataMethodDefinition::StartEnumInstances Method</span></span>

<span data-ttu-id="5ae75-103">Fornisce un handle per l'enumerazione delle istanze del metodo per un oggetto specificato `IXCLRDataAppDomain` .</span><span class="sxs-lookup"><span data-stu-id="5ae75-103">Provides a handle for the enumeration of method instances for a given `IXCLRDataAppDomain`.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="5ae75-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5ae75-104">Syntax</span></span>

```cpp
HRESULT StartEnumInstances(
    [in] IXCLRDataAppDomain* appDomain,
    [out] CLRDATA_ENUM *handle
);
```

## <a name="parameters"></a><span data-ttu-id="5ae75-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="5ae75-105">Parameters</span></span>

`appDomain`\
<span data-ttu-id="5ae75-106">in AppDomain per l'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="5ae75-106">[in] An AppDomain for the enumeration.</span></span>

`handle`\
<span data-ttu-id="5ae75-107">out Handle per l'enumerazione delle istanze.</span><span class="sxs-lookup"><span data-stu-id="5ae75-107">[out] A handle for enumerating the instances.</span></span>

## <a name="remarks"></a><span data-ttu-id="5ae75-108">Commenti</span><span class="sxs-lookup"><span data-stu-id="5ae75-108">Remarks</span></span>

<span data-ttu-id="5ae75-109">Il metodo fornito fa parte dell' `IXCLRDataMethodDefinition` interfaccia e corrisponde al quinto slot della tabella del metodo virtuale.</span><span class="sxs-lookup"><span data-stu-id="5ae75-109">The provided method is part of the `IXCLRDataMethodDefinition` interface and corresponds to the 5th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="5ae75-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5ae75-110">Requirements</span></span>

<span data-ttu-id="5ae75-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5ae75-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="5ae75-112">**Intestazione:** Nessuno</span><span class="sxs-lookup"><span data-stu-id="5ae75-112">**Header:** None</span></span>  
<span data-ttu-id="5ae75-113">**Libreria:** Nessuno</span><span class="sxs-lookup"><span data-stu-id="5ae75-113">**Library:** None</span></span>  
<span data-ttu-id="5ae75-114">**Versioni .NET Framework:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="5ae75-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="5ae75-115">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="5ae75-115">See also</span></span>

- [<span data-ttu-id="5ae75-116">Enumerazione CLRDataSourceType</span><span class="sxs-lookup"><span data-stu-id="5ae75-116">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="5ae75-117">Debug</span><span class="sxs-lookup"><span data-stu-id="5ae75-117">Debugging</span></span>](index.md)
- [<span data-ttu-id="5ae75-118">Interfaccia IXCLRDataMethodDefinition</span><span class="sxs-lookup"><span data-stu-id="5ae75-118">IXCLRDataMethodDefinition Interface</span></span>](ixclrdatamethoddefinition-interface.md)

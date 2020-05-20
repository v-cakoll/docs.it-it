---
title: 'Metodo IXCLRDataProcess:: EndEnumMethodInstancesByAddress'
ms.date: 01/16/2019
api.name:
- IXCLRDataProcess::EndEnumMethodInstancesByAddress Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataProcess::EndEnumMethodInstancesByAddress Method
helpviewer.keywords:
- IXCLRDataProcess::EndEnumMethodInstancesByAddress Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 5960d08ccfc09010a20d28a22c2e2f3f5b339c7d
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420825"
---
# <a name="ixclrdataprocessendenummethodinstancesbyaddress-method"></a><span data-ttu-id="7eaa6-102">Metodo IXCLRDataProcess:: EndEnumMethodInstancesByAddress</span><span class="sxs-lookup"><span data-stu-id="7eaa6-102">IXCLRDataProcess::EndEnumMethodInstancesByAddress Method</span></span>

<span data-ttu-id="7eaa6-103">Rilascia le risorse utilizzate dagli iteratori interni utilizzati durante l'enumerazione dell'istanza.</span><span class="sxs-lookup"><span data-stu-id="7eaa6-103">Releases the resources used by internal iterators used during instance enumeration.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="7eaa6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7eaa6-104">Syntax</span></span>

```cpp
HRESULT EndEnumMethodInstancesByAddress(
    [in] CLRDATA_ENUM handle
);
```

## <a name="parameters"></a><span data-ttu-id="7eaa6-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="7eaa6-105">Parameters</span></span>

`handle`\
<span data-ttu-id="7eaa6-106">out Handle per l'enumerazione delle istanze del metodo.</span><span class="sxs-lookup"><span data-stu-id="7eaa6-106">[out] A handle for enumerating the method instances.</span></span>

## <a name="remarks"></a><span data-ttu-id="7eaa6-107">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="7eaa6-107">Remarks</span></span>

<span data-ttu-id="7eaa6-108">Il metodo fornito fa parte dell' `IXCLRDataProcess` interfaccia e corrisponde al trentesimo slot della tabella del metodo virtuale.</span><span class="sxs-lookup"><span data-stu-id="7eaa6-108">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 30th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="7eaa6-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7eaa6-109">Requirements</span></span>

<span data-ttu-id="7eaa6-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7eaa6-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="7eaa6-111">**Intestazione:** Nessuno</span><span class="sxs-lookup"><span data-stu-id="7eaa6-111">**Header:** None</span></span>  
<span data-ttu-id="7eaa6-112">**Libreria:** Nessuno</span><span class="sxs-lookup"><span data-stu-id="7eaa6-112">**Library:** None</span></span>  
<span data-ttu-id="7eaa6-113">**Versioni .NET Framework:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="7eaa6-113">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="7eaa6-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7eaa6-114">See also</span></span>

- [<span data-ttu-id="7eaa6-115">Enumerazione CLRDataSourceType</span><span class="sxs-lookup"><span data-stu-id="7eaa6-115">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="7eaa6-116">Debug</span><span class="sxs-lookup"><span data-stu-id="7eaa6-116">Debugging</span></span>](index.md)
- [<span data-ttu-id="7eaa6-117">Interfaccia IXCLRDataProcess</span><span class="sxs-lookup"><span data-stu-id="7eaa6-117">IXCLRDataProcess Interface</span></span>](ixclrdataprocess-interface.md)

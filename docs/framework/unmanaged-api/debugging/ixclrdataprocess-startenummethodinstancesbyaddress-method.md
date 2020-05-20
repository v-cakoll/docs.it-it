---
title: 'Metodo IXCLRDataProcess:: StartEnumMethodInstancesByAddress'
ms.date: 01/16/2019
api.name:
- IXCLRDataProcess::StartEnumMethodInstancesByAddress Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataProcess::StartEnumMethodInstancesByAddress Method
helpviewer.keywords:
- IXCLRDataProcess::StartEnumMethodInstancesByAddress Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 52d533f1c86b34b7b9febade8590e7ab58d8221e
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420734"
---
# <a name="ixclrdataprocessstartenummethodinstancesbyaddress-method"></a><span data-ttu-id="32528-102">Metodo IXCLRDataProcess:: StartEnumMethodInstancesByAddress</span><span class="sxs-lookup"><span data-stu-id="32528-102">IXCLRDataProcess::StartEnumMethodInstancesByAddress Method</span></span>

<span data-ttu-id="32528-103">Fornisce un handle per enumerare le istanze del metodo di a `AppDomain` partire da un indirizzo specificato.</span><span class="sxs-lookup"><span data-stu-id="32528-103">Provides a handle to enumerate the method instances of `AppDomain` starting at a given address.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="32528-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="32528-104">Syntax</span></span>

```cpp
HRESULT StartEnumMethodInstancesByAddress(
    [in] CLRDATA_ADDRESS     address,
    [in] IXCLRDataAppDomain *appDomain,
    [out] CLRDATA_ENUM      *handle
);
```

## <a name="parameters"></a><span data-ttu-id="32528-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="32528-105">Parameters</span></span>

`address`\
<span data-ttu-id="32528-106">in Indirizzo dell'istanza del primo metodo.</span><span class="sxs-lookup"><span data-stu-id="32528-106">[in] The address of the first method instance.</span></span>

`appDomain`\
<span data-ttu-id="32528-107">in AppDomain delle istanze del metodo.</span><span class="sxs-lookup"><span data-stu-id="32528-107">[in] The AppDomain of the method instances.</span></span>

`handle`\
<span data-ttu-id="32528-108">out Handle per l'enumerazione delle istanze del metodo.</span><span class="sxs-lookup"><span data-stu-id="32528-108">[out] A handle for enumerating the method instances.</span></span>

## <a name="remarks"></a><span data-ttu-id="32528-109">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="32528-109">Remarks</span></span>

<span data-ttu-id="32528-110">Il metodo fornito fa parte dell' `IXCLRDataProcess` interfaccia e corrisponde al ventottesimo slot della tabella del metodo virtuale.</span><span class="sxs-lookup"><span data-stu-id="32528-110">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 28th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="32528-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="32528-111">Requirements</span></span>

<span data-ttu-id="32528-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="32528-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="32528-113">**Intestazione:** Nessuno</span><span class="sxs-lookup"><span data-stu-id="32528-113">**Header:** None</span></span>  
<span data-ttu-id="32528-114">**Libreria:** Nessuno</span><span class="sxs-lookup"><span data-stu-id="32528-114">**Library:** None</span></span>  
<span data-ttu-id="32528-115">**Versioni .NET Framework:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="32528-115">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="32528-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="32528-116">See also</span></span>

- [<span data-ttu-id="32528-117">Enumerazione CLRDataSourceType</span><span class="sxs-lookup"><span data-stu-id="32528-117">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="32528-118">Debug</span><span class="sxs-lookup"><span data-stu-id="32528-118">Debugging</span></span>](index.md)
- [<span data-ttu-id="32528-119">Interfaccia IXCLRDataProcess</span><span class="sxs-lookup"><span data-stu-id="32528-119">IXCLRDataProcess Interface</span></span>](ixclrdataprocess-interface.md)

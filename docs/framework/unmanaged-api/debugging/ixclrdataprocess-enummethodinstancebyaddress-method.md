---
title: 'Metodo IXCLRDataProcess:: EnumMethodInstanceByAddress'
ms.date: 01/16/2019
api.name:
- IXCLRDataProcess::EnumMethodInstanceByAddress Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataProcess::EnumMethodInstanceByAddress Method
helpviewer.keywords:
- IXCLRDataProcess::EnumMethodInstanceByAddress Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 142099ae5cf9637cc28e8c82aabcd831cc8f0f52
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420799"
---
# <a name="ixclrdataprocessenummethodinstancebyaddress-method"></a><span data-ttu-id="b568d-102">Metodo IXCLRDataProcess:: EnumMethodInstanceByAddress</span><span class="sxs-lookup"><span data-stu-id="b568d-102">IXCLRDataProcess::EnumMethodInstanceByAddress Method</span></span>

<span data-ttu-id="b568d-103">Enumera le istanze del metodo di questo processo a partire da un offset di indirizzo.</span><span class="sxs-lookup"><span data-stu-id="b568d-103">Enumerates the method instances of this process starting at an address offset.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="b568d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b568d-104">Syntax</span></span>

```cpp
HRESULT EnumMethodInstanceByAddress(
    [in] CLRDATA_ENUM              *handle,
    [out] IXCLRDataMethodInstance **method
);
```

## <a name="parameters"></a><span data-ttu-id="b568d-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="b568d-105">Parameters</span></span>

`handle`\
<span data-ttu-id="b568d-106">in Handle per l'enumerazione delle istanze del metodo.</span><span class="sxs-lookup"><span data-stu-id="b568d-106">[in] A handle for enumerating the method instances.</span></span>

`mod`\
<span data-ttu-id="b568d-107">out Istanza del metodo enumerata.</span><span class="sxs-lookup"><span data-stu-id="b568d-107">[out] The enumerated method instance.</span></span>

## <a name="remarks"></a><span data-ttu-id="b568d-108">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="b568d-108">Remarks</span></span>

<span data-ttu-id="b568d-109">Il metodo fornito fa parte dell' `IXCLRDataProcess` interfaccia e corrisponde al ventinovesimo slot della tabella del metodo virtuale.</span><span class="sxs-lookup"><span data-stu-id="b568d-109">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 29th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="b568d-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b568d-110">Requirements</span></span>

<span data-ttu-id="b568d-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b568d-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>
<span data-ttu-id="b568d-112">**Intestazione:** Nessuna **libreria:** nessuna **.NET Framework versioni:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="b568d-112">**Header:** None **Library:** None **.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="b568d-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b568d-113">See also</span></span>

- [<span data-ttu-id="b568d-114">Enumerazione CLRDataSourceType</span><span class="sxs-lookup"><span data-stu-id="b568d-114">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="b568d-115">Debug</span><span class="sxs-lookup"><span data-stu-id="b568d-115">Debugging</span></span>](index.md)
- [<span data-ttu-id="b568d-116">Interfaccia IXCLRDataProcess</span><span class="sxs-lookup"><span data-stu-id="b568d-116">IXCLRDataProcess Interface</span></span>](ixclrdataprocess-interface.md)

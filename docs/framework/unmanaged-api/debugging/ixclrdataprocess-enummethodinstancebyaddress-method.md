---
title: Metodo IXCLRDataProcess::EnumMethodInstanceByAddress
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
ms.openlocfilehash: 89b89a0cb056a0515bf0859069455a73f62aae4a
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67769625"
---
# <a name="ixclrdataprocessenummethodinstancebyaddress-method"></a><span data-ttu-id="05a94-102">Metodo IXCLRDataProcess::EnumMethodInstanceByAddress</span><span class="sxs-lookup"><span data-stu-id="05a94-102">IXCLRDataProcess::EnumMethodInstanceByAddress Method</span></span>

<span data-ttu-id="05a94-103">Enumera le istanze di metodo di questo processo iniziando in corrispondenza di un offset di indirizzo.</span><span class="sxs-lookup"><span data-stu-id="05a94-103">Enumerates the method instances of this process starting at an address offset.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="05a94-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="05a94-104">Syntax</span></span>

```cpp
HRESULT EnumMethodInstanceByAddress(
    [in] CLRDATA_ENUM              *handle,
    [out] IXCLRDataMethodInstance **method
);
```

## <a name="parameters"></a><span data-ttu-id="05a94-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="05a94-105">Parameters</span></span>

`handle`\
<span data-ttu-id="05a94-106">[in] Handle per l'enumerazione delle istanze di metodo.</span><span class="sxs-lookup"><span data-stu-id="05a94-106">[in] A handle for enumerating the method instances.</span></span>

`mod`\
<span data-ttu-id="05a94-107">[out] L'istanza del metodo enumerate.</span><span class="sxs-lookup"><span data-stu-id="05a94-107">[out] The enumerated method instance.</span></span>

## <a name="remarks"></a><span data-ttu-id="05a94-108">Note</span><span class="sxs-lookup"><span data-stu-id="05a94-108">Remarks</span></span>

<span data-ttu-id="05a94-109">Il metodo specificato fa parte di `IXCLRDataProcess` interfaccia e corrisponde al 28 slot della tabella di metodo virtuale.</span><span class="sxs-lookup"><span data-stu-id="05a94-109">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 28th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="05a94-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="05a94-110">Requirements</span></span>

<span data-ttu-id="05a94-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="05a94-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>   
<span data-ttu-id="05a94-112">**Intestazione:** nessuno</span><span class="sxs-lookup"><span data-stu-id="05a94-112">**Header:** None</span></span>   
<span data-ttu-id="05a94-113">**Libreria:** nessuno</span><span class="sxs-lookup"><span data-stu-id="05a94-113">**Library:** None</span></span>   
<span data-ttu-id="05a94-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="05a94-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>   
 
## <a name="see-also"></a><span data-ttu-id="05a94-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="05a94-115">See also</span></span>

- [<span data-ttu-id="05a94-116">Enumerazione CLRDataSourceType</span><span class="sxs-lookup"><span data-stu-id="05a94-116">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="05a94-117">Debug</span><span class="sxs-lookup"><span data-stu-id="05a94-117">Debugging</span></span>](index.md)
- [<span data-ttu-id="05a94-118">IXCLRDataProcess Interface</span><span class="sxs-lookup"><span data-stu-id="05a94-118">IXCLRDataProcess Interface</span></span>](ixclrdataprocess-interface.md)

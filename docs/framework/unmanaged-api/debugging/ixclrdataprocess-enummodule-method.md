---
title: Metodo IXCLRDataProcess::EnumModule
ms.date: 01/16/2019
api.name:
- IXCLRDataProcess::EnumModule Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataProcess::EnumModule Method
helpviewer.keywords:
- IXCLRDataProcess::EnumModule Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: fa1e41985444324627c6b66a109b4619d85fc57f
ms.sourcegitcommit: b56d59ad42140d277f2acbd003b74d655fdbc9f1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2019
ms.locfileid: "54416680"
---
# <a name="ixclrdataprocessenummodule-method"></a><span data-ttu-id="85919-102">Metodo IXCLRDataProcess::EnumModule</span><span class="sxs-lookup"><span data-stu-id="85919-102">IXCLRDataProcess::EnumModule Method</span></span>

<span data-ttu-id="85919-103">Enumera i moduli di questo processo.</span><span class="sxs-lookup"><span data-stu-id="85919-103">Enumerates the modules of this process.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="85919-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="85919-104">Syntax</span></span>

```
HRESULT EnumModule(
    [in, out] CLRDATA_ENUM  *handle,
    [out] IXCLRDataModule  **mod
);
```

### <a name="parameters"></a><span data-ttu-id="85919-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="85919-105">Parameters</span></span>

<span data-ttu-id="85919-106">`handle` [in, out] Handle per l'enumerazione dei moduli.</span><span class="sxs-lookup"><span data-stu-id="85919-106">`handle` [in, out] A handle for enumerating the modules.</span></span>

<span data-ttu-id="85919-107">`mod` [out] Il modulo enumerato.</span><span class="sxs-lookup"><span data-stu-id="85919-107">`mod` [out] The enumerated module.</span></span>

## <a name="remarks"></a><span data-ttu-id="85919-108">Note</span><span class="sxs-lookup"><span data-stu-id="85919-108">Remarks</span></span>

<span data-ttu-id="85919-109">Il metodo specificato fa parte di `IXCLRDataProcess` interfaccia e corrisponde al 25 slot della tabella di metodo virtuale.</span><span class="sxs-lookup"><span data-stu-id="85919-109">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 25th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="85919-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="85919-110">Requirements</span></span>

<span data-ttu-id="85919-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="85919-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="85919-112">**Intestazione:** nessuno</span><span class="sxs-lookup"><span data-stu-id="85919-112">**Header:** None</span></span>  
<span data-ttu-id="85919-113">**Libreria:** nessuno</span><span class="sxs-lookup"><span data-stu-id="85919-113">**Library:** None</span></span>  
<span data-ttu-id="85919-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="85919-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="85919-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="85919-115">See Also</span></span>

- [<span data-ttu-id="85919-116">Enumerazione CLRDataSourceType</span><span class="sxs-lookup"><span data-stu-id="85919-116">CLRDataSourceType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="85919-117">Debug</span><span class="sxs-lookup"><span data-stu-id="85919-117">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="85919-118">Interfaccia IXCLRDataModule</span><span class="sxs-lookup"><span data-stu-id="85919-118">IXCLRDataModule Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamodule-interface.md)
- [<span data-ttu-id="85919-119">IXCLRDataProcess Interface</span><span class="sxs-lookup"><span data-stu-id="85919-119">IXCLRDataProcess Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdataprocess-interface.md)

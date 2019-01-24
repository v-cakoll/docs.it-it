---
title: Metodo IXCLRDataModule::GetVersionId
ms.date: 01/16/2019
api.name:
- IXCLRDataModule::GetVersionId Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataModule::GetVersionId Method
helpviewer.keywords:
- IXCLRDataModule::GetVersionId Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 5184db00b10b53011f24c5096b470608e84546b6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54567425"
---
# <a name="ixclrdatamodulegetversionid-method"></a><span data-ttu-id="c6f5f-102">Metodo IXCLRDataModule::GetVersionId</span><span class="sxs-lookup"><span data-stu-id="c6f5f-102">IXCLRDataModule::GetVersionId Method</span></span>

<span data-ttu-id="c6f5f-103">Ottiene l'identificatore di versione del modulo.</span><span class="sxs-lookup"><span data-stu-id="c6f5f-103">Gets the module's version identifier.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="c6f5f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c6f5f-104">Syntax</span></span>

```
HRESULT GetVersionId(
    [out] GUID* vid
);
```

### <a name="parameters"></a><span data-ttu-id="c6f5f-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="c6f5f-105">Parameters</span></span>

<span data-ttu-id="c6f5f-106">`vid` [out] Identificatore della versione del modulo.</span><span class="sxs-lookup"><span data-stu-id="c6f5f-106">`vid` [out] The module's version identifier.</span></span>

## <a name="remarks"></a><span data-ttu-id="c6f5f-107">Note</span><span class="sxs-lookup"><span data-stu-id="c6f5f-107">Remarks</span></span>

<span data-ttu-id="c6f5f-108">Il metodo specificato fa parte di `IXCLRDataModule` interfaccia e corrisponde al 40 ° slot della tabella di metodo virtuale.</span><span class="sxs-lookup"><span data-stu-id="c6f5f-108">The provided method is part of the `IXCLRDataModule` interface and corresponds to the 40th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="c6f5f-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c6f5f-109">Requirements</span></span>

<span data-ttu-id="c6f5f-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c6f5f-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="c6f5f-111">**Intestazione:** nessuno</span><span class="sxs-lookup"><span data-stu-id="c6f5f-111">**Header:** None</span></span>  
<span data-ttu-id="c6f5f-112">**Libreria:** nessuno</span><span class="sxs-lookup"><span data-stu-id="c6f5f-112">**Library:** None</span></span>  
<span data-ttu-id="c6f5f-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="c6f5f-113">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="c6f5f-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c6f5f-114">See also</span></span>

- [<span data-ttu-id="c6f5f-115">Debug</span><span class="sxs-lookup"><span data-stu-id="c6f5f-115">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="c6f5f-116">Interfaccia IXCLRDataModule</span><span class="sxs-lookup"><span data-stu-id="c6f5f-116">IXCLRDataModule Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamodule-interface.md)

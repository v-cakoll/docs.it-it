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
ms.openlocfilehash: ac4111abdf6a471aca1eca72a86e33698debbff6
ms.sourcegitcommit: b56d59ad42140d277f2acbd003b74d655fdbc9f1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2019
ms.locfileid: "54416560"
---
# <a name="ixclrdatamodulegetversionid-method"></a><span data-ttu-id="eda5a-102">Metodo IXCLRDataModule::GetVersionId</span><span class="sxs-lookup"><span data-stu-id="eda5a-102">IXCLRDataModule::GetVersionId Method</span></span>

<span data-ttu-id="eda5a-103">Ottiene l'identificatore di versione del modulo.</span><span class="sxs-lookup"><span data-stu-id="eda5a-103">Gets the module's version identifier.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="eda5a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="eda5a-104">Syntax</span></span>

```
HRESULT GetVersionId(
    [out] GUID* vid
);
```

### <a name="parameters"></a><span data-ttu-id="eda5a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="eda5a-105">Parameters</span></span>

<span data-ttu-id="eda5a-106">`vid` [out] Identificatore della versione del modulo.</span><span class="sxs-lookup"><span data-stu-id="eda5a-106">`vid` [out] The module's version identifier.</span></span>

## <a name="remarks"></a><span data-ttu-id="eda5a-107">Note</span><span class="sxs-lookup"><span data-stu-id="eda5a-107">Remarks</span></span>

<span data-ttu-id="eda5a-108">Il metodo specificato fa parte di `IXCLRDataModule` interfaccia e corrisponde al 40 ° slot della tabella di metodo virtuale.</span><span class="sxs-lookup"><span data-stu-id="eda5a-108">The provided method is part of the `IXCLRDataModule` interface and corresponds to the 40th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="eda5a-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="eda5a-109">Requirements</span></span>

<span data-ttu-id="eda5a-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eda5a-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="eda5a-111">**Intestazione:** nessuno</span><span class="sxs-lookup"><span data-stu-id="eda5a-111">**Header:** None</span></span>  
<span data-ttu-id="eda5a-112">**Libreria:** nessuno</span><span class="sxs-lookup"><span data-stu-id="eda5a-112">**Library:** None</span></span>  
<span data-ttu-id="eda5a-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="eda5a-113">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="eda5a-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="eda5a-114">See Also</span></span>

- [<span data-ttu-id="eda5a-115">Debug</span><span class="sxs-lookup"><span data-stu-id="eda5a-115">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="eda5a-116">Interfaccia IXCLRDataModule</span><span class="sxs-lookup"><span data-stu-id="eda5a-116">IXCLRDataModule Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamodule-interface.md)

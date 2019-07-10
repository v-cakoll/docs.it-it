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
ms.openlocfilehash: 5bd84f784ea92e7b2ce2465e64972dc84e16a16c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67744697"
---
# <a name="ixclrdatamodulegetversionid-method"></a><span data-ttu-id="6f003-102">Metodo IXCLRDataModule::GetVersionId</span><span class="sxs-lookup"><span data-stu-id="6f003-102">IXCLRDataModule::GetVersionId Method</span></span>

<span data-ttu-id="6f003-103">Ottiene l'identificatore di versione del modulo.</span><span class="sxs-lookup"><span data-stu-id="6f003-103">Gets the module's version identifier.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="6f003-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6f003-104">Syntax</span></span>

```cpp
HRESULT GetVersionId(
    [out] GUID* vid
);
```

## <a name="parameters"></a><span data-ttu-id="6f003-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="6f003-105">Parameters</span></span>

`vid`\
<span data-ttu-id="6f003-106">[out] Identificatore della versione del modulo.</span><span class="sxs-lookup"><span data-stu-id="6f003-106">[out] The module's version identifier.</span></span>

## <a name="remarks"></a><span data-ttu-id="6f003-107">Note</span><span class="sxs-lookup"><span data-stu-id="6f003-107">Remarks</span></span>

<span data-ttu-id="6f003-108">Il metodo specificato fa parte di `IXCLRDataModule` interfaccia e corrisponde al 40 ° slot della tabella di metodo virtuale.</span><span class="sxs-lookup"><span data-stu-id="6f003-108">The provided method is part of the `IXCLRDataModule` interface and corresponds to the 40th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="6f003-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6f003-109">Requirements</span></span>

<span data-ttu-id="6f003-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6f003-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="6f003-111">**Intestazione:** nessuno</span><span class="sxs-lookup"><span data-stu-id="6f003-111">**Header:** None</span></span>  
<span data-ttu-id="6f003-112">**Libreria:** nessuno</span><span class="sxs-lookup"><span data-stu-id="6f003-112">**Library:** None</span></span>  
<span data-ttu-id="6f003-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="6f003-113">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="6f003-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6f003-114">See also</span></span>

- [<span data-ttu-id="6f003-115">Debug</span><span class="sxs-lookup"><span data-stu-id="6f003-115">Debugging</span></span>](index.md)
- [<span data-ttu-id="6f003-116">Interfaccia IXCLRDataModule</span><span class="sxs-lookup"><span data-stu-id="6f003-116">IXCLRDataModule Interface</span></span>](ixclrdatamodule-interface.md)

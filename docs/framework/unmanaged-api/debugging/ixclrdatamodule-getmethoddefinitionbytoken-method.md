---
title: Metodo IXCLRDataModule::GetMethodDefinitionByToken
ms.date: 01/16/2019
api.name:
- IXCLRDataModule::GetMethodDefinitionByToken Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataModule::GetMethodDefinitionByToken Method
helpviewer.keywords:
- IXCLRDataModule::GetMethodDefinitionByToken Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 1371b86f30324908a639b3b1bbae0ae007ba590a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54708090"
---
# <a name="ixclrdatamodulegetmethoddefinitionbytoken-method"></a><span data-ttu-id="4ddac-102">Metodo IXCLRDataModule::GetMethodDefinitionByToken</span><span class="sxs-lookup"><span data-stu-id="4ddac-102">IXCLRDataModule::GetMethodDefinitionByToken Method</span></span>

<span data-ttu-id="4ddac-103">Ottiene la definizione del metodo corrispondente a un token di metadati specificato.</span><span class="sxs-lookup"><span data-stu-id="4ddac-103">Gets the method definition corresponding to a given metadata token.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="4ddac-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4ddac-104">Syntax</span></span>

```
HRESULT GetMethodDefinitionByToken(
    [in] mdMethodDef token,
    [out] IXCLRDataMethodDefinition** methodDefinition
);
```

### <a name="parameters"></a><span data-ttu-id="4ddac-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="4ddac-105">Parameters</span></span>

<span data-ttu-id="4ddac-106">`token` [in] Il token del metodo.</span><span class="sxs-lookup"><span data-stu-id="4ddac-106">`token` [in] The method token.</span></span>

<span data-ttu-id="4ddac-107">`methodDefinition` [out] La definizione del metodo.</span><span class="sxs-lookup"><span data-stu-id="4ddac-107">`methodDefinition` [out] The method definition.</span></span>

## <a name="remarks"></a><span data-ttu-id="4ddac-108">Note</span><span class="sxs-lookup"><span data-stu-id="4ddac-108">Remarks</span></span>

<span data-ttu-id="4ddac-109">Il metodo specificato fa parte di `IXCLRDataModule` interfaccia e corrisponde al 25 slot della tabella di metodo virtuale.</span><span class="sxs-lookup"><span data-stu-id="4ddac-109">The provided method is part of the `IXCLRDataModule` interface and corresponds to the 25th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="4ddac-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4ddac-110">Requirements</span></span>

<span data-ttu-id="4ddac-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4ddac-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="4ddac-112">**Intestazione:** nessuno</span><span class="sxs-lookup"><span data-stu-id="4ddac-112">**Header:** None</span></span>  
<span data-ttu-id="4ddac-113">**Libreria:** nessuno</span><span class="sxs-lookup"><span data-stu-id="4ddac-113">**Library:** None</span></span>  
<span data-ttu-id="4ddac-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="4ddac-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  
 
## <a name="see-also"></a><span data-ttu-id="4ddac-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4ddac-115">See also</span></span>

- [<span data-ttu-id="4ddac-116">Debug</span><span class="sxs-lookup"><span data-stu-id="4ddac-116">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="4ddac-117">Interfaccia IXCLRDataModule</span><span class="sxs-lookup"><span data-stu-id="4ddac-117">IXCLRDataModule Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamodule-interface.md)

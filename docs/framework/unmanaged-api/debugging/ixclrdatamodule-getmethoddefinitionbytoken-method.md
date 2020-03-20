---
title: Metodo IXCLRDataModule::GetMethodDefinitionByTokenIXCLRDataModule::GetMethodDefinitionByToken Method
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
ms.openlocfilehash: 294c5340caf2217f9337d654a11a63a43d46febd
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176669"
---
# <a name="ixclrdatamodulegetmethoddefinitionbytoken-method"></a><span data-ttu-id="5ffa1-102">Metodo IXCLRDataModule::GetMethodDefinitionByTokenIXCLRDataModule::GetMethodDefinitionByToken Method</span><span class="sxs-lookup"><span data-stu-id="5ffa1-102">IXCLRDataModule::GetMethodDefinitionByToken Method</span></span>

<span data-ttu-id="5ffa1-103">Ottiene la definizione del metodo corrispondente a un token di metadati specificato.</span><span class="sxs-lookup"><span data-stu-id="5ffa1-103">Gets the method definition corresponding to a given metadata token.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="5ffa1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5ffa1-104">Syntax</span></span>

```cpp
HRESULT GetMethodDefinitionByToken(
    [in] mdMethodDef token,
    [out] IXCLRDataMethodDefinition** methodDefinition
);
```

## <a name="parameters"></a><span data-ttu-id="5ffa1-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="5ffa1-105">Parameters</span></span>

`token`\
<span data-ttu-id="5ffa1-106">[in] Token del metodo.</span><span class="sxs-lookup"><span data-stu-id="5ffa1-106">[in] The method token.</span></span>

`methodDefinition`\
<span data-ttu-id="5ffa1-107">[fuori] Definizione del metodo.</span><span class="sxs-lookup"><span data-stu-id="5ffa1-107">[out] The method definition.</span></span>

## <a name="remarks"></a><span data-ttu-id="5ffa1-108">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="5ffa1-108">Remarks</span></span>

<span data-ttu-id="5ffa1-109">Il metodo fornito fa `IXCLRDataModule` parte dell'interfaccia e corrisponde al venticinquesimo slot della tabella dei metodi virtuali.</span><span class="sxs-lookup"><span data-stu-id="5ffa1-109">The provided method is part of the `IXCLRDataModule` interface and corresponds to the 25th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="5ffa1-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5ffa1-110">Requirements</span></span>

<span data-ttu-id="5ffa1-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5ffa1-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="5ffa1-112">**Intestazione:** Nessuno</span><span class="sxs-lookup"><span data-stu-id="5ffa1-112">**Header:** None</span></span>  
<span data-ttu-id="5ffa1-113">**Biblioteca:** Nessuno</span><span class="sxs-lookup"><span data-stu-id="5ffa1-113">**Library:** None</span></span>  
<span data-ttu-id="5ffa1-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="5ffa1-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="5ffa1-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5ffa1-115">See also</span></span>

- [<span data-ttu-id="5ffa1-116">Debug</span><span class="sxs-lookup"><span data-stu-id="5ffa1-116">Debugging</span></span>](index.md)
- [<span data-ttu-id="5ffa1-117">Interfaccia IXCLRDataModule</span><span class="sxs-lookup"><span data-stu-id="5ffa1-117">IXCLRDataModule Interface</span></span>](ixclrdatamodule-interface.md)

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
ms.openlocfilehash: 727005437289b4bc66ab90f280b80a79f4db06db
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57359315"
---
# <a name="ixclrdatamodulegetmethoddefinitionbytoken-method"></a><span data-ttu-id="7cac1-102">Metodo IXCLRDataModule::GetMethodDefinitionByToken</span><span class="sxs-lookup"><span data-stu-id="7cac1-102">IXCLRDataModule::GetMethodDefinitionByToken Method</span></span>

<span data-ttu-id="7cac1-103">Ottiene la definizione del metodo corrispondente a un token di metadati specificato.</span><span class="sxs-lookup"><span data-stu-id="7cac1-103">Gets the method definition corresponding to a given metadata token.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="7cac1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7cac1-104">Syntax</span></span>

```
HRESULT GetMethodDefinitionByToken(
    [in] mdMethodDef token,
    [out] IXCLRDataMethodDefinition** methodDefinition
);
```

## <a name="parameters"></a><span data-ttu-id="7cac1-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="7cac1-105">Parameters</span></span>

`token`\
<span data-ttu-id="7cac1-106">[in] Il token del metodo.</span><span class="sxs-lookup"><span data-stu-id="7cac1-106">[in] The method token.</span></span>

`methodDefinition`\
<span data-ttu-id="7cac1-107">[out] La definizione del metodo.</span><span class="sxs-lookup"><span data-stu-id="7cac1-107">[out] The method definition.</span></span>

## <a name="remarks"></a><span data-ttu-id="7cac1-108">Note</span><span class="sxs-lookup"><span data-stu-id="7cac1-108">Remarks</span></span>

<span data-ttu-id="7cac1-109">Il metodo specificato fa parte di `IXCLRDataModule` interfaccia e corrisponde al 25 slot della tabella di metodo virtuale.</span><span class="sxs-lookup"><span data-stu-id="7cac1-109">The provided method is part of the `IXCLRDataModule` interface and corresponds to the 25th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="7cac1-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7cac1-110">Requirements</span></span>

<span data-ttu-id="7cac1-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7cac1-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="7cac1-112">**Intestazione:** nessuno</span><span class="sxs-lookup"><span data-stu-id="7cac1-112">**Header:** None</span></span>  
<span data-ttu-id="7cac1-113">**Libreria:** nessuno</span><span class="sxs-lookup"><span data-stu-id="7cac1-113">**Library:** None</span></span>  
<span data-ttu-id="7cac1-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="7cac1-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  
 
## <a name="see-also"></a><span data-ttu-id="7cac1-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7cac1-115">See also</span></span>

- [<span data-ttu-id="7cac1-116">Debug</span><span class="sxs-lookup"><span data-stu-id="7cac1-116">Debugging</span></span>](index.md)
- [<span data-ttu-id="7cac1-117">Interfaccia IXCLRDataModule</span><span class="sxs-lookup"><span data-stu-id="7cac1-117">IXCLRDataModule Interface</span></span>](ixclrdatamodule-interface.md)

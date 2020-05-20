---
title: 'Metodo IXCLRDataModule:: GetMethodDefinitionByToken'
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
ms.openlocfilehash: 074949145be588fc34266a9f2ee501caeeffb9d3
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420877"
---
# <a name="ixclrdatamodulegetmethoddefinitionbytoken-method"></a><span data-ttu-id="f9cd0-102">Metodo IXCLRDataModule:: GetMethodDefinitionByToken</span><span class="sxs-lookup"><span data-stu-id="f9cd0-102">IXCLRDataModule::GetMethodDefinitionByToken Method</span></span>

<span data-ttu-id="f9cd0-103">Ottiene la definizione del metodo corrispondente a un token di metadati specificato.</span><span class="sxs-lookup"><span data-stu-id="f9cd0-103">Gets the method definition corresponding to a given metadata token.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="f9cd0-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f9cd0-104">Syntax</span></span>

```cpp
HRESULT GetMethodDefinitionByToken(
    [in] mdMethodDef token,
    [out] IXCLRDataMethodDefinition** methodDefinition
);
```

## <a name="parameters"></a><span data-ttu-id="f9cd0-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f9cd0-105">Parameters</span></span>

`token`\
<span data-ttu-id="f9cd0-106">in Token del metodo.</span><span class="sxs-lookup"><span data-stu-id="f9cd0-106">[in] The method token.</span></span>

`methodDefinition`\
<span data-ttu-id="f9cd0-107">out Definizione del metodo.</span><span class="sxs-lookup"><span data-stu-id="f9cd0-107">[out] The method definition.</span></span>

## <a name="remarks"></a><span data-ttu-id="f9cd0-108">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="f9cd0-108">Remarks</span></span>

<span data-ttu-id="f9cd0-109">Il metodo fornito fa parte dell' `IXCLRDataModule` interfaccia e corrisponde allo slot 26 della tabella del metodo virtuale.</span><span class="sxs-lookup"><span data-stu-id="f9cd0-109">The provided method is part of the `IXCLRDataModule` interface and corresponds to the 26th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="f9cd0-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f9cd0-110">Requirements</span></span>

<span data-ttu-id="f9cd0-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f9cd0-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="f9cd0-112">**Intestazione:** Nessuno</span><span class="sxs-lookup"><span data-stu-id="f9cd0-112">**Header:** None</span></span>  
<span data-ttu-id="f9cd0-113">**Libreria:** Nessuno</span><span class="sxs-lookup"><span data-stu-id="f9cd0-113">**Library:** None</span></span>  
<span data-ttu-id="f9cd0-114">**Versioni .NET Framework:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="f9cd0-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="f9cd0-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f9cd0-115">See also</span></span>

- [<span data-ttu-id="f9cd0-116">Debug</span><span class="sxs-lookup"><span data-stu-id="f9cd0-116">Debugging</span></span>](index.md)
- [<span data-ttu-id="f9cd0-117">Interfaccia IXCLRDataModule</span><span class="sxs-lookup"><span data-stu-id="f9cd0-117">IXCLRDataModule Interface</span></span>](ixclrdatamodule-interface.md)

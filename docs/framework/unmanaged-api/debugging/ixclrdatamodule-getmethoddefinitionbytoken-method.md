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
ms.openlocfilehash: c70920205b27376d453bdd0a13223c6a5569075b
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2020
ms.locfileid: "83395290"
---
# <a name="ixclrdatamodulegetmethoddefinitionbytoken-method"></a><span data-ttu-id="b44d5-102">Metodo IXCLRDataModule:: GetMethodDefinitionByToken</span><span class="sxs-lookup"><span data-stu-id="b44d5-102">IXCLRDataModule::GetMethodDefinitionByToken Method</span></span>

<span data-ttu-id="b44d5-103">Ottiene la definizione del metodo corrispondente a un token di metadati specificato.</span><span class="sxs-lookup"><span data-stu-id="b44d5-103">Gets the method definition corresponding to a given metadata token.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="b44d5-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b44d5-104">Syntax</span></span>

```cpp
HRESULT GetMethodDefinitionByToken(
    [in] mdMethodDef token,
    [out] IXCLRDataMethodDefinition** methodDefinition
);
```

## <a name="parameters"></a><span data-ttu-id="b44d5-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="b44d5-105">Parameters</span></span>

`token`\
<span data-ttu-id="b44d5-106">in Token del metodo.</span><span class="sxs-lookup"><span data-stu-id="b44d5-106">[in] The method token.</span></span>

`methodDefinition`\
<span data-ttu-id="b44d5-107">out Definizione del metodo.</span><span class="sxs-lookup"><span data-stu-id="b44d5-107">[out] The method definition.</span></span>

## <a name="remarks"></a><span data-ttu-id="b44d5-108">Commenti</span><span class="sxs-lookup"><span data-stu-id="b44d5-108">Remarks</span></span>

<span data-ttu-id="b44d5-109">Il metodo fornito fa parte dell' `IXCLRDataModule` interfaccia e corrisponde allo slot 26 della tabella del metodo virtuale.</span><span class="sxs-lookup"><span data-stu-id="b44d5-109">The provided method is part of the `IXCLRDataModule` interface and corresponds to the 26th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="b44d5-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b44d5-110">Requirements</span></span>

<span data-ttu-id="b44d5-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b44d5-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="b44d5-112">**Intestazione:** Nessuno</span><span class="sxs-lookup"><span data-stu-id="b44d5-112">**Header:** None</span></span>  
<span data-ttu-id="b44d5-113">**Libreria:** Nessuno</span><span class="sxs-lookup"><span data-stu-id="b44d5-113">**Library:** None</span></span>  
<span data-ttu-id="b44d5-114">**Versioni .NET Framework:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="b44d5-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="b44d5-115">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="b44d5-115">See also</span></span>

- [<span data-ttu-id="b44d5-116">Debug</span><span class="sxs-lookup"><span data-stu-id="b44d5-116">Debugging</span></span>](index.md)
- [<span data-ttu-id="b44d5-117">Interfaccia IXCLRDataModule</span><span class="sxs-lookup"><span data-stu-id="b44d5-117">IXCLRDataModule Interface</span></span>](ixclrdatamodule-interface.md)

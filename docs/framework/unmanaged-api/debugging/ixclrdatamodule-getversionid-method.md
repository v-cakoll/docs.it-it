---
title: 'Metodo IXCLRDataModule:: GetVersionId'
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
ms.openlocfilehash: ff8ccf42d1131fb15d7473ae12ecefde9d55177f
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2020
ms.locfileid: "83395284"
---
# <a name="ixclrdatamodulegetversionid-method"></a><span data-ttu-id="4d973-102">Metodo IXCLRDataModule:: GetVersionId</span><span class="sxs-lookup"><span data-stu-id="4d973-102">IXCLRDataModule::GetVersionId Method</span></span>

<span data-ttu-id="4d973-103">Ottiene l'identificatore di versione del modulo.</span><span class="sxs-lookup"><span data-stu-id="4d973-103">Gets the module's version identifier.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="4d973-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4d973-104">Syntax</span></span>

```cpp
HRESULT GetVersionId(
    [out] GUID* vid
);
```

## <a name="parameters"></a><span data-ttu-id="4d973-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="4d973-105">Parameters</span></span>

`vid`\
<span data-ttu-id="4d973-106">out Identificatore di versione del modulo.</span><span class="sxs-lookup"><span data-stu-id="4d973-106">[out] The module's version identifier.</span></span>

## <a name="remarks"></a><span data-ttu-id="4d973-107">Commenti</span><span class="sxs-lookup"><span data-stu-id="4d973-107">Remarks</span></span>

<span data-ttu-id="4d973-108">Il metodo fornito fa parte dell' `IXCLRDataModule` interfaccia e corrisponde allo slot 41 della tabella del metodo virtuale.</span><span class="sxs-lookup"><span data-stu-id="4d973-108">The provided method is part of the `IXCLRDataModule` interface and corresponds to the 41st slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="4d973-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4d973-109">Requirements</span></span>

<span data-ttu-id="4d973-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4d973-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="4d973-111">**Intestazione:** Nessuno</span><span class="sxs-lookup"><span data-stu-id="4d973-111">**Header:** None</span></span>  
<span data-ttu-id="4d973-112">**Libreria:** Nessuno</span><span class="sxs-lookup"><span data-stu-id="4d973-112">**Library:** None</span></span>  
<span data-ttu-id="4d973-113">**Versioni .NET Framework:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="4d973-113">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="4d973-114">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="4d973-114">See also</span></span>

- [<span data-ttu-id="4d973-115">Debug</span><span class="sxs-lookup"><span data-stu-id="4d973-115">Debugging</span></span>](index.md)
- [<span data-ttu-id="4d973-116">Interfaccia IXCLRDataModule</span><span class="sxs-lookup"><span data-stu-id="4d973-116">IXCLRDataModule Interface</span></span>](ixclrdatamodule-interface.md)

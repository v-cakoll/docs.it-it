---
title: Metodo IAssemblyName::SetProperty
ms.date: 03/30/2017
api_name:
- IAssemblyName.SetProperty
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyName::SetProperty
helpviewer_keywords:
- IAssemblyName::SetProperty method [.NET Framework fusion]
- SetProperty method [.NET Framework fusion]
ms.assetid: 496c3add-f60b-4073-943f-d1bcf33330cb
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 17e96f56c57d896397489e27bcc072d8e7df05ec
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796535"
---
# <a name="iassemblynamesetproperty-method"></a><span data-ttu-id="3100e-102">Metodo IAssemblyName::SetProperty</span><span class="sxs-lookup"><span data-stu-id="3100e-102">IAssemblyName::SetProperty Method</span></span>
<span data-ttu-id="3100e-103">Imposta il valore della proprietà a cui fa riferimento l'identificatore di proprietà specificato.</span><span class="sxs-lookup"><span data-stu-id="3100e-103">Sets the value of the property referenced by the specified property identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3100e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3100e-104">Syntax</span></span>  
  
```cpp  
HRESULT SetProperty (  
    [in] DWORD  PropertyId,  
    [in] LPVOID pvProperty,  
    [in] DWORD  cbProperty  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3100e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="3100e-105">Parameters</span></span>  
 `PropertyId`  
 <span data-ttu-id="3100e-106">in Identificatore univoco della proprietà il cui valore verrà impostato.</span><span class="sxs-lookup"><span data-stu-id="3100e-106">[in] The unique identifier of the property whose value will be set.</span></span>  
  
 `pvProperty`  
 <span data-ttu-id="3100e-107">in Valore a cui impostare la proprietà a cui fa riferimento `PropertyId`.</span><span class="sxs-lookup"><span data-stu-id="3100e-107">[in] The value to which to set the property referenced by `PropertyId`.</span></span>  
  
 `cbProperty`  
 <span data-ttu-id="3100e-108">in Dimensione, in byte, di `pvProperty`.</span><span class="sxs-lookup"><span data-stu-id="3100e-108">[in] The size, in bytes, of `pvProperty`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3100e-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3100e-109">Requirements</span></span>  
 <span data-ttu-id="3100e-110">**Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3100e-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3100e-111">**Intestazione:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="3100e-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="3100e-112">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3100e-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3100e-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3100e-113">See also</span></span>

- [<span data-ttu-id="3100e-114">Interfaccia IAssemblyName</span><span class="sxs-lookup"><span data-stu-id="3100e-114">IAssemblyName Interface</span></span>](iassemblyname-interface.md)

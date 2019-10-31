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
ms.openlocfilehash: ffa1fa2f5e141728a56f1b598a1aae9602b2ac86
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73108211"
---
# <a name="iassemblynamesetproperty-method"></a><span data-ttu-id="25668-102">Metodo IAssemblyName::SetProperty</span><span class="sxs-lookup"><span data-stu-id="25668-102">IAssemblyName::SetProperty Method</span></span>
<span data-ttu-id="25668-103">Imposta il valore della proprietà a cui fa riferimento l'identificatore di proprietà specificato.</span><span class="sxs-lookup"><span data-stu-id="25668-103">Sets the value of the property referenced by the specified property identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="25668-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="25668-104">Syntax</span></span>  
  
```cpp  
HRESULT SetProperty (  
    [in] DWORD  PropertyId,  
    [in] LPVOID pvProperty,  
    [in] DWORD  cbProperty  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="25668-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="25668-105">Parameters</span></span>  
 `PropertyId`  
 <span data-ttu-id="25668-106">in Identificatore univoco della proprietà il cui valore verrà impostato.</span><span class="sxs-lookup"><span data-stu-id="25668-106">[in] The unique identifier of the property whose value will be set.</span></span>  
  
 `pvProperty`  
 <span data-ttu-id="25668-107">in Valore a cui impostare la proprietà a cui fa riferimento `PropertyId`.</span><span class="sxs-lookup"><span data-stu-id="25668-107">[in] The value to which to set the property referenced by `PropertyId`.</span></span>  
  
 `cbProperty`  
 <span data-ttu-id="25668-108">in Dimensione, in byte, del `pvProperty`.</span><span class="sxs-lookup"><span data-stu-id="25668-108">[in] The size, in bytes, of `pvProperty`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="25668-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="25668-109">Requirements</span></span>  
 <span data-ttu-id="25668-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="25668-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="25668-111">**Intestazione:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="25668-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="25668-112">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="25668-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25668-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="25668-113">See also</span></span>

- [<span data-ttu-id="25668-114">Interfaccia IAssemblyName</span><span class="sxs-lookup"><span data-stu-id="25668-114">IAssemblyName Interface</span></span>](iassemblyname-interface.md)

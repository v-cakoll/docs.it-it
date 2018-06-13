---
title: Metodo IAssemblyName::GetDisplayName
ms.date: 03/30/2017
api_name:
- IAssemblyName.GetDisplayName
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyName::GetDisplayName
helpviewer_keywords:
- GetDisplayName method, IAssemblyName interface [.NET Framework fusion]
- IAssemblyName::GetDisplayName method [.NET Framework fusion]
ms.assetid: 9a26547a-9a34-4284-a463-78a7d4b496cf
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 00a95646323a5ee08d6758b0f6a7c493c661705d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33431776"
---
# <a name="iassemblynamegetdisplayname-method"></a><span data-ttu-id="51ddd-102">Metodo IAssemblyName::GetDisplayName</span><span class="sxs-lookup"><span data-stu-id="51ddd-102">IAssemblyName::GetDisplayName Method</span></span>
<span data-ttu-id="51ddd-103">Ottiene il nome leggibile dell'assembly a cui fa riferimento questo [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) oggetto.</span><span class="sxs-lookup"><span data-stu-id="51ddd-103">Gets the human-readable name of the assembly referenced by this [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="51ddd-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="51ddd-104">Syntax</span></span>  
  
```  
HRESULT GetDisplayName (  
        [out]      LPOLESTR  szDisplayName,  
        [in, out]  LPDWORD   pccDisplayName,  
        [in]       DWORD     dwDisplayFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="51ddd-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="51ddd-105">Parameters</span></span>  
 `szDisplayName`  
 <span data-ttu-id="51ddd-106">[out] Buffer di stringa che contiene il nome dell'assembly di riferimento.</span><span class="sxs-lookup"><span data-stu-id="51ddd-106">[out] The string buffer that contains the name of the referenced assembly.</span></span>  
  
 `pccDisplayName`  
 <span data-ttu-id="51ddd-107">[in, out] Le dimensioni di `szDisplayName` in caratteri wide, incluso il carattere di terminazione null.</span><span class="sxs-lookup"><span data-stu-id="51ddd-107">[in, out] The size of `szDisplayName` in wide characters, including a null terminator character.</span></span>  
  
 `dwDisplayFlags`  
 <span data-ttu-id="51ddd-108">[in] Combinazione bit per bit di [ASM_DISPLAY_FLAGS](../../../../docs/framework/unmanaged-api/fusion/asm-display-flags-enumeration.md) valori che influenzano le funzionalità di `szDisplayName`.</span><span class="sxs-lookup"><span data-stu-id="51ddd-108">[in] A bitwise combination of [ASM_DISPLAY_FLAGS](../../../../docs/framework/unmanaged-api/fusion/asm-display-flags-enumeration.md) values that influence the features of `szDisplayName`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="51ddd-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="51ddd-109">Requirements</span></span>  
 <span data-ttu-id="51ddd-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="51ddd-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="51ddd-111">**Intestazione:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="51ddd-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="51ddd-112">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="51ddd-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51ddd-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="51ddd-113">See Also</span></span>  
 [<span data-ttu-id="51ddd-114">Interfaccia IAssemblyName</span><span class="sxs-lookup"><span data-stu-id="51ddd-114">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)  
 [<span data-ttu-id="51ddd-115">Enumerazioni Fusion</span><span class="sxs-lookup"><span data-stu-id="51ddd-115">Fusion Enumerations</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-enumerations.md)

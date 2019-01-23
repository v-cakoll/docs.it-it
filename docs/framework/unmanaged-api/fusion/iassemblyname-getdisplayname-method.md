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
ms.openlocfilehash: 2d8cbc540377c8f2a26b8fafef35c19e94a59c51
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54536009"
---
# <a name="iassemblynamegetdisplayname-method"></a><span data-ttu-id="9bcfa-102">Metodo IAssemblyName::GetDisplayName</span><span class="sxs-lookup"><span data-stu-id="9bcfa-102">IAssemblyName::GetDisplayName Method</span></span>
<span data-ttu-id="9bcfa-103">Ottiene il nome leggibile dell'assembly a cui fa riferimento [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) oggetto.</span><span class="sxs-lookup"><span data-stu-id="9bcfa-103">Gets the human-readable name of the assembly referenced by this [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9bcfa-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9bcfa-104">Syntax</span></span>  
  
```  
HRESULT GetDisplayName (  
        [out]      LPOLESTR  szDisplayName,  
        [in, out]  LPDWORD   pccDisplayName,  
        [in]       DWORD     dwDisplayFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9bcfa-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="9bcfa-105">Parameters</span></span>  
 `szDisplayName`  
 <span data-ttu-id="9bcfa-106">[out] Il buffer di stringa che contiene il nome dell'assembly di riferimento.</span><span class="sxs-lookup"><span data-stu-id="9bcfa-106">[out] The string buffer that contains the name of the referenced assembly.</span></span>  
  
 `pccDisplayName`  
 <span data-ttu-id="9bcfa-107">[in, out] Le dimensioni di `szDisplayName` in caratteri "wide", incluso il carattere di terminazione null.</span><span class="sxs-lookup"><span data-stu-id="9bcfa-107">[in, out] The size of `szDisplayName` in wide characters, including a null terminator character.</span></span>  
  
 `dwDisplayFlags`  
 <span data-ttu-id="9bcfa-108">[in] Una combinazione bit per bit di [ASM_DISPLAY_FLAGS](../../../../docs/framework/unmanaged-api/fusion/asm-display-flags-enumeration.md) i valori che determinano le caratteristiche di `szDisplayName`.</span><span class="sxs-lookup"><span data-stu-id="9bcfa-108">[in] A bitwise combination of [ASM_DISPLAY_FLAGS](../../../../docs/framework/unmanaged-api/fusion/asm-display-flags-enumeration.md) values that influence the features of `szDisplayName`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9bcfa-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9bcfa-109">Requirements</span></span>  
 <span data-ttu-id="9bcfa-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9bcfa-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9bcfa-111">**Intestazione:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="9bcfa-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="9bcfa-112">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9bcfa-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9bcfa-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9bcfa-113">See also</span></span>
- [<span data-ttu-id="9bcfa-114">Interfaccia IAssemblyName</span><span class="sxs-lookup"><span data-stu-id="9bcfa-114">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)
- [<span data-ttu-id="9bcfa-115">Enumerazioni Fusion</span><span class="sxs-lookup"><span data-stu-id="9bcfa-115">Fusion Enumerations</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-enumerations.md)

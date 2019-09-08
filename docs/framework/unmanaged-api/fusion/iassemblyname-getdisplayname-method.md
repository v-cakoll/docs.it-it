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
ms.openlocfilehash: 38f48f2d95829d2c8111065e5f4ede4e43a16d63
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796657"
---
# <a name="iassemblynamegetdisplayname-method"></a><span data-ttu-id="ea6be-102">Metodo IAssemblyName::GetDisplayName</span><span class="sxs-lookup"><span data-stu-id="ea6be-102">IAssemblyName::GetDisplayName Method</span></span>
<span data-ttu-id="ea6be-103">Ottiene il nome leggibile dell'assembly a cui fa riferimento questo oggetto [IAssemblyName](iassemblyname-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="ea6be-103">Gets the human-readable name of the assembly referenced by this [IAssemblyName](iassemblyname-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea6be-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ea6be-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDisplayName (  
        [out]      LPOLESTR  szDisplayName,  
        [in, out]  LPDWORD   pccDisplayName,  
        [in]       DWORD     dwDisplayFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ea6be-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ea6be-105">Parameters</span></span>  
 `szDisplayName`  
 <span data-ttu-id="ea6be-106">out Buffer di stringa che contiene il nome dell'assembly a cui si fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="ea6be-106">[out] The string buffer that contains the name of the referenced assembly.</span></span>  
  
 `pccDisplayName`  
 <span data-ttu-id="ea6be-107">[in, out] Dimensioni in caratteri `szDisplayName` Wide, incluso un carattere di terminazione null.</span><span class="sxs-lookup"><span data-stu-id="ea6be-107">[in, out] The size of `szDisplayName` in wide characters, including a null terminator character.</span></span>  
  
 `dwDisplayFlags`  
 <span data-ttu-id="ea6be-108">in Combinazione bit per bit di valori [ASM_DISPLAY_FLAGS](asm-display-flags-enumeration.md) che influenzano le `szDisplayName`funzionalità di.</span><span class="sxs-lookup"><span data-stu-id="ea6be-108">[in] A bitwise combination of [ASM_DISPLAY_FLAGS](asm-display-flags-enumeration.md) values that influence the features of `szDisplayName`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ea6be-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ea6be-109">Requirements</span></span>  
 <span data-ttu-id="ea6be-110">**Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ea6be-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ea6be-111">**Intestazione:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="ea6be-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="ea6be-112">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ea6be-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea6be-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ea6be-113">See also</span></span>

- [<span data-ttu-id="ea6be-114">Interfaccia IAssemblyName</span><span class="sxs-lookup"><span data-stu-id="ea6be-114">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
- [<span data-ttu-id="ea6be-115">Enumerazioni Fusion</span><span class="sxs-lookup"><span data-stu-id="ea6be-115">Fusion Enumerations</span></span>](fusion-enumerations.md)

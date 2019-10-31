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
ms.openlocfilehash: 5dbb5dc483bc5a08c59606654d55b5a62266e509
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134376"
---
# <a name="iassemblynamegetdisplayname-method"></a><span data-ttu-id="c9175-102">Metodo IAssemblyName::GetDisplayName</span><span class="sxs-lookup"><span data-stu-id="c9175-102">IAssemblyName::GetDisplayName Method</span></span>
<span data-ttu-id="c9175-103">Ottiene il nome leggibile dell'assembly a cui fa riferimento questo oggetto [IAssemblyName](iassemblyname-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="c9175-103">Gets the human-readable name of the assembly referenced by this [IAssemblyName](iassemblyname-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c9175-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c9175-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDisplayName (  
        [out]      LPOLESTR  szDisplayName,  
        [in, out]  LPDWORD   pccDisplayName,  
        [in]       DWORD     dwDisplayFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c9175-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="c9175-105">Parameters</span></span>  
 `szDisplayName`  
 <span data-ttu-id="c9175-106">out Buffer di stringa che contiene il nome dell'assembly a cui si fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="c9175-106">[out] The string buffer that contains the name of the referenced assembly.</span></span>  
  
 `pccDisplayName`  
 <span data-ttu-id="c9175-107">[in, out] Dimensioni del `szDisplayName` in caratteri wide, incluso un carattere di terminazione null.</span><span class="sxs-lookup"><span data-stu-id="c9175-107">[in, out] The size of `szDisplayName` in wide characters, including a null terminator character.</span></span>  
  
 `dwDisplayFlags`  
 <span data-ttu-id="c9175-108">in Combinazione bit per bit di valori [ASM_DISPLAY_FLAGS](asm-display-flags-enumeration.md) che influenzano le funzionalità di `szDisplayName`.</span><span class="sxs-lookup"><span data-stu-id="c9175-108">[in] A bitwise combination of [ASM_DISPLAY_FLAGS](asm-display-flags-enumeration.md) values that influence the features of `szDisplayName`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c9175-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c9175-109">Requirements</span></span>  
 <span data-ttu-id="c9175-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c9175-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c9175-111">**Intestazione:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="c9175-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="c9175-112">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c9175-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9175-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c9175-113">See also</span></span>

- [<span data-ttu-id="c9175-114">Interfaccia IAssemblyName</span><span class="sxs-lookup"><span data-stu-id="c9175-114">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
- [<span data-ttu-id="c9175-115">Enumerazioni Fusion</span><span class="sxs-lookup"><span data-stu-id="c9175-115">Fusion Enumerations</span></span>](fusion-enumerations.md)

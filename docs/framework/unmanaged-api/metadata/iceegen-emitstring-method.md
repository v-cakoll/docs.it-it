---
title: Metodo ICeeGen::EmitString
ms.date: 03/30/2017
api_name:
- ICeeGen.EmitString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::EmitString
helpviewer_keywords:
- EmitString method [.NET Framework metadata]
- ICeeGen::EmitString method [.NET Framework metadata]
ms.assetid: ad2710a7-edb8-4493-8619-3fce235e3334
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1dccb2a3a3f3aaf0f209c8f3543056ab81c562dd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33443899"
---
# <a name="iceegenemitstring-method"></a><span data-ttu-id="4ebff-102">Metodo ICeeGen::EmitString</span><span class="sxs-lookup"><span data-stu-id="4ebff-102">ICeeGen::EmitString Method</span></span>
<span data-ttu-id="4ebff-103">Genera la stringa specificata nella codebase.</span><span class="sxs-lookup"><span data-stu-id="4ebff-103">Emits the specified string into the code base.</span></span>  
  
 <span data-ttu-id="4ebff-104">Questo metodo è obsoleto e non deve essere utilizzato.</span><span class="sxs-lookup"><span data-stu-id="4ebff-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4ebff-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4ebff-105">Syntax</span></span>  
  
```  
HRESULT EmitString (  
    [in]  LPWSTR    lpString,  
    [out] ULONG     *RVA  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4ebff-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="4ebff-106">Parameters</span></span>  
 `lpString`  
 <span data-ttu-id="4ebff-107">[in] Stringa da generare.</span><span class="sxs-lookup"><span data-stu-id="4ebff-107">[in] The string to emit.</span></span>  
  
 `RVA`  
 <span data-ttu-id="4ebff-108">[out] L'indirizzo virtuale relativo, della stringa generata.</span><span class="sxs-lookup"><span data-stu-id="4ebff-108">[out] The relative virtual address of the emitted string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4ebff-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4ebff-109">Requirements</span></span>  
 <span data-ttu-id="4ebff-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4ebff-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4ebff-111">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="4ebff-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4ebff-112">**Libreria:** usata come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="4ebff-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="4ebff-113">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4ebff-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ebff-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4ebff-114">See Also</span></span>  
 [<span data-ttu-id="4ebff-115">Interfaccia ICeeGen</span><span class="sxs-lookup"><span data-stu-id="4ebff-115">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)

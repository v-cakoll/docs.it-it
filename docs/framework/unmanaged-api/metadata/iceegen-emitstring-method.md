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
ms.openlocfilehash: 1eabf5631fcfe7a187d0e203d64c7a7f4f5a819a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59209957"
---
# <a name="iceegenemitstring-method"></a><span data-ttu-id="79824-102">Metodo ICeeGen::EmitString</span><span class="sxs-lookup"><span data-stu-id="79824-102">ICeeGen::EmitString Method</span></span>
<span data-ttu-id="79824-103">Genera la stringa specificata nella codebase.</span><span class="sxs-lookup"><span data-stu-id="79824-103">Emits the specified string into the code base.</span></span>  
  
 <span data-ttu-id="79824-104">Questo metodo è obsoleto e non deve essere utilizzato.</span><span class="sxs-lookup"><span data-stu-id="79824-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="79824-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="79824-105">Syntax</span></span>  
  
```  
HRESULT EmitString (  
    [in]  LPWSTR    lpString,  
    [out] ULONG     *RVA  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="79824-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="79824-106">Parameters</span></span>  
 `lpString`  
 <span data-ttu-id="79824-107">[in] Stringa da generare.</span><span class="sxs-lookup"><span data-stu-id="79824-107">[in] The string to emit.</span></span>  
  
 `RVA`  
 <span data-ttu-id="79824-108">[out] L'indirizzo virtuale relativo della stringa generata.</span><span class="sxs-lookup"><span data-stu-id="79824-108">[out] The relative virtual address of the emitted string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="79824-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="79824-109">Requirements</span></span>  
 <span data-ttu-id="79824-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="79824-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="79824-111">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="79824-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="79824-112">**Libreria:** Usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="79824-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="79824-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="79824-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79824-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="79824-114">See also</span></span>

- [<span data-ttu-id="79824-115">Interfaccia ICeeGen</span><span class="sxs-lookup"><span data-stu-id="79824-115">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)

---
title: Metodo ICeeGen::EmitString
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICeeGen.EmitString
api_location: mscoree.dll
api_type: COM
f1_keywords: ICeeGen::EmitString
helpviewer_keywords:
- EmitString method [.NET Framework metadata]
- ICeeGen::EmitString method [.NET Framework metadata]
ms.assetid: ad2710a7-edb8-4493-8619-3fce235e3334
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 89c53f41595416a6bb4b8d373c7d3dbcea4c4faa
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="iceegenemitstring-method"></a><span data-ttu-id="ccbcd-102">Metodo ICeeGen::EmitString</span><span class="sxs-lookup"><span data-stu-id="ccbcd-102">ICeeGen::EmitString Method</span></span>
<span data-ttu-id="ccbcd-103">Genera la stringa specificata nella codebase.</span><span class="sxs-lookup"><span data-stu-id="ccbcd-103">Emits the specified string into the code base.</span></span>  
  
 <span data-ttu-id="ccbcd-104">Questo metodo è obsoleto e non deve essere utilizzato.</span><span class="sxs-lookup"><span data-stu-id="ccbcd-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ccbcd-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ccbcd-105">Syntax</span></span>  
  
```  
HRESULT EmitString (  
    [in]  LPWSTR    lpString,  
    [out] ULONG     *RVA  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ccbcd-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="ccbcd-106">Parameters</span></span>  
 `lpString`  
 <span data-ttu-id="ccbcd-107">[in] Stringa da generare.</span><span class="sxs-lookup"><span data-stu-id="ccbcd-107">[in] The string to emit.</span></span>  
  
 `RVA`  
 <span data-ttu-id="ccbcd-108">[out] L'indirizzo virtuale relativo, della stringa generata.</span><span class="sxs-lookup"><span data-stu-id="ccbcd-108">[out] The relative virtual address of the emitted string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ccbcd-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ccbcd-109">Requirements</span></span>  
 <span data-ttu-id="ccbcd-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ccbcd-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ccbcd-111">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="ccbcd-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ccbcd-112">**Libreria:** usata come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ccbcd-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ccbcd-113">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ccbcd-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ccbcd-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ccbcd-114">See Also</span></span>  
 [<span data-ttu-id="ccbcd-115">Interfaccia ICeeGen</span><span class="sxs-lookup"><span data-stu-id="ccbcd-115">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)

---
title: Metodo ICeeGen::TruncateSection
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICeeGen.TruncateSection
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::TruncateSection
helpviewer_keywords:
- TruncateSection method [.NET Framework metadata]
- ICeeGen::TruncateSection method [.NET Framework metadata]
ms.assetid: 0451d752-1e5c-4c9a-8bad-6cd35b7ba3df
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 8e7deaaab58f1ee51bd3675faec892db5228c787
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="iceegentruncatesection-method"></a><span data-ttu-id="82610-102">Metodo ICeeGen::TruncateSection</span><span class="sxs-lookup"><span data-stu-id="82610-102">ICeeGen::TruncateSection Method</span></span>
<span data-ttu-id="82610-103">Tronca la sezione di codice specificati dalla lunghezza specificata.</span><span class="sxs-lookup"><span data-stu-id="82610-103">Truncates the specified code section by the specified length.</span></span>  
  
 <span data-ttu-id="82610-104">Questo metodo è obsoleto e non deve essere utilizzato.</span><span class="sxs-lookup"><span data-stu-id="82610-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="82610-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="82610-105">Syntax</span></span>  
  
```  
HRESULT TruncateSection (  
    [in]  HCEESECTION     section,  
    [in]  ULONG           len  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="82610-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="82610-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="82610-107">[in] La sezione da troncare.</span><span class="sxs-lookup"><span data-stu-id="82610-107">[in] The section to truncate.</span></span>  
  
 `len`  
 <span data-ttu-id="82610-108">[in] La lunghezza in byte, da cui si desidera troncare la sezione.</span><span class="sxs-lookup"><span data-stu-id="82610-108">[in] The length, in bytes, by which to truncate the section.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="82610-109">Note</span><span class="sxs-lookup"><span data-stu-id="82610-109">Remarks</span></span>  
 <span data-ttu-id="82610-110">Chiamare `TruncateSection` solo se sono necessari requisiti speciali di sezione che non sono gestiti da altri metodi.</span><span class="sxs-lookup"><span data-stu-id="82610-110">Call `TruncateSection` only if you have special section requirements that are not handled by other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="82610-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="82610-111">Requirements</span></span>  
 <span data-ttu-id="82610-112">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="82610-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="82610-113">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="82610-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="82610-114">**Libreria:** usata come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="82610-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="82610-115">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="82610-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82610-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="82610-116">See Also</span></span>  
 [<span data-ttu-id="82610-117">Interfaccia ICeeGen</span><span class="sxs-lookup"><span data-stu-id="82610-117">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)

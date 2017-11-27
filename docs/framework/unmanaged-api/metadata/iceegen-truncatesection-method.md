---
title: Metodo ICeeGen::TruncateSection
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICeeGen.TruncateSection
api_location: mscoree.dll
api_type: COM
f1_keywords: ICeeGen::TruncateSection
helpviewer_keywords:
- TruncateSection method [.NET Framework metadata]
- ICeeGen::TruncateSection method [.NET Framework metadata]
ms.assetid: 0451d752-1e5c-4c9a-8bad-6cd35b7ba3df
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 204c71b55c4ba2ec1e3b137137d8f08845b12e49
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="iceegentruncatesection-method"></a><span data-ttu-id="7fc97-102">Metodo ICeeGen::TruncateSection</span><span class="sxs-lookup"><span data-stu-id="7fc97-102">ICeeGen::TruncateSection Method</span></span>
<span data-ttu-id="7fc97-103">Tronca la sezione di codice specificati dalla lunghezza specificata.</span><span class="sxs-lookup"><span data-stu-id="7fc97-103">Truncates the specified code section by the specified length.</span></span>  
  
 <span data-ttu-id="7fc97-104">Questo metodo è obsoleto e non deve essere utilizzato.</span><span class="sxs-lookup"><span data-stu-id="7fc97-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7fc97-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7fc97-105">Syntax</span></span>  
  
```  
HRESULT TruncateSection (  
    [in]  HCEESECTION     section,  
    [in]  ULONG           len  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7fc97-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="7fc97-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="7fc97-107">[in] La sezione da troncare.</span><span class="sxs-lookup"><span data-stu-id="7fc97-107">[in] The section to truncate.</span></span>  
  
 `len`  
 <span data-ttu-id="7fc97-108">[in] La lunghezza in byte, da cui si desidera troncare la sezione.</span><span class="sxs-lookup"><span data-stu-id="7fc97-108">[in] The length, in bytes, by which to truncate the section.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7fc97-109">Note</span><span class="sxs-lookup"><span data-stu-id="7fc97-109">Remarks</span></span>  
 <span data-ttu-id="7fc97-110">Chiamare `TruncateSection` solo se sono necessari requisiti speciali di sezione che non sono gestiti da altri metodi.</span><span class="sxs-lookup"><span data-stu-id="7fc97-110">Call `TruncateSection` only if you have special section requirements that are not handled by other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7fc97-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7fc97-111">Requirements</span></span>  
 <span data-ttu-id="7fc97-112">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7fc97-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7fc97-113">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="7fc97-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7fc97-114">**Libreria:** usata come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7fc97-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7fc97-115">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7fc97-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7fc97-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7fc97-116">See Also</span></span>  
 [<span data-ttu-id="7fc97-117">ICeeGen (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="7fc97-117">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)

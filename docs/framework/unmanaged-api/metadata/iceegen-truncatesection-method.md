---
title: Metodo ICeeGen::TruncateSection
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a7b21179faec0b6f37b8084c9ee8a0bfd327193e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33443564"
---
# <a name="iceegentruncatesection-method"></a><span data-ttu-id="bd217-102">Metodo ICeeGen::TruncateSection</span><span class="sxs-lookup"><span data-stu-id="bd217-102">ICeeGen::TruncateSection Method</span></span>
<span data-ttu-id="bd217-103">Tronca la sezione di codice specificati dalla lunghezza specificata.</span><span class="sxs-lookup"><span data-stu-id="bd217-103">Truncates the specified code section by the specified length.</span></span>  
  
 <span data-ttu-id="bd217-104">Questo metodo è obsoleto e non deve essere utilizzato.</span><span class="sxs-lookup"><span data-stu-id="bd217-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd217-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bd217-105">Syntax</span></span>  
  
```  
HRESULT TruncateSection (  
    [in]  HCEESECTION     section,  
    [in]  ULONG           len  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bd217-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="bd217-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="bd217-107">[in] La sezione da troncare.</span><span class="sxs-lookup"><span data-stu-id="bd217-107">[in] The section to truncate.</span></span>  
  
 `len`  
 <span data-ttu-id="bd217-108">[in] La lunghezza in byte, da cui si desidera troncare la sezione.</span><span class="sxs-lookup"><span data-stu-id="bd217-108">[in] The length, in bytes, by which to truncate the section.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bd217-109">Note</span><span class="sxs-lookup"><span data-stu-id="bd217-109">Remarks</span></span>  
 <span data-ttu-id="bd217-110">Chiamare `TruncateSection` solo se sono necessari requisiti speciali di sezione che non sono gestiti da altri metodi.</span><span class="sxs-lookup"><span data-stu-id="bd217-110">Call `TruncateSection` only if you have special section requirements that are not handled by other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bd217-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="bd217-111">Requirements</span></span>  
 <span data-ttu-id="bd217-112">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bd217-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bd217-113">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="bd217-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="bd217-114">**Libreria:** usata come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="bd217-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="bd217-115">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bd217-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd217-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bd217-116">See Also</span></span>  
 [<span data-ttu-id="bd217-117">Interfaccia ICeeGen</span><span class="sxs-lookup"><span data-stu-id="bd217-117">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)

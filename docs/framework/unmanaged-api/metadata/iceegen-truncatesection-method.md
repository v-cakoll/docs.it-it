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
ms.openlocfilehash: 69f536e6add43d664eba436e185275632dc0063a
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57479350"
---
# <a name="iceegentruncatesection-method"></a><span data-ttu-id="2aded-102">Metodo ICeeGen::TruncateSection</span><span class="sxs-lookup"><span data-stu-id="2aded-102">ICeeGen::TruncateSection Method</span></span>
<span data-ttu-id="2aded-103">Tronca la sezione di codice specificato per la lunghezza specificata.</span><span class="sxs-lookup"><span data-stu-id="2aded-103">Truncates the specified code section by the specified length.</span></span>  
  
 <span data-ttu-id="2aded-104">Questo metodo è obsoleto e non deve essere utilizzato.</span><span class="sxs-lookup"><span data-stu-id="2aded-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2aded-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2aded-105">Syntax</span></span>  
  
```  
HRESULT TruncateSection (  
    [in]  HCEESECTION     section,  
    [in]  ULONG           len  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2aded-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="2aded-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="2aded-107">[in] La sezione da troncare.</span><span class="sxs-lookup"><span data-stu-id="2aded-107">[in] The section to truncate.</span></span>  
  
 `len`  
 <span data-ttu-id="2aded-108">[in] La lunghezza, espressa in byte, da cui si desidera troncare la sezione.</span><span class="sxs-lookup"><span data-stu-id="2aded-108">[in] The length, in bytes, by which to truncate the section.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2aded-109">Note</span><span class="sxs-lookup"><span data-stu-id="2aded-109">Remarks</span></span>  
 <span data-ttu-id="2aded-110">Chiamare `TruncateSection` solo se si hanno requisiti di sezione speciale che non sono gestiti tramite altri metodi.</span><span class="sxs-lookup"><span data-stu-id="2aded-110">Call `TruncateSection` only if you have special section requirements that are not handled by other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2aded-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2aded-111">Requirements</span></span>  
 <span data-ttu-id="2aded-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2aded-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2aded-113">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="2aded-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2aded-114">**Libreria:** Usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="2aded-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="2aded-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2aded-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2aded-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2aded-116">See also</span></span>
- [<span data-ttu-id="2aded-117">Interfaccia ICeeGen</span><span class="sxs-lookup"><span data-stu-id="2aded-117">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)

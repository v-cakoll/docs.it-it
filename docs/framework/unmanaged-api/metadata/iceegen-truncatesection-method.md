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
ms.openlocfilehash: 994f6668de3040cc9f2381356d6db06c18c9e984
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67745878"
---
# <a name="iceegentruncatesection-method"></a><span data-ttu-id="0206f-102">Metodo ICeeGen::TruncateSection</span><span class="sxs-lookup"><span data-stu-id="0206f-102">ICeeGen::TruncateSection Method</span></span>
<span data-ttu-id="0206f-103">Tronca la sezione di codice specificato per la lunghezza specificata.</span><span class="sxs-lookup"><span data-stu-id="0206f-103">Truncates the specified code section by the specified length.</span></span>  
  
 <span data-ttu-id="0206f-104">Questo metodo è obsoleto e non deve essere utilizzato.</span><span class="sxs-lookup"><span data-stu-id="0206f-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0206f-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0206f-105">Syntax</span></span>  
  
```cpp  
HRESULT TruncateSection (  
    [in]  HCEESECTION     section,  
    [in]  ULONG           len  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0206f-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="0206f-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="0206f-107">[in] La sezione da troncare.</span><span class="sxs-lookup"><span data-stu-id="0206f-107">[in] The section to truncate.</span></span>  
  
 `len`  
 <span data-ttu-id="0206f-108">[in] La lunghezza, espressa in byte, da cui si desidera troncare la sezione.</span><span class="sxs-lookup"><span data-stu-id="0206f-108">[in] The length, in bytes, by which to truncate the section.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0206f-109">Note</span><span class="sxs-lookup"><span data-stu-id="0206f-109">Remarks</span></span>  
 <span data-ttu-id="0206f-110">Chiamare `TruncateSection` solo se si hanno requisiti di sezione speciale che non sono gestiti tramite altri metodi.</span><span class="sxs-lookup"><span data-stu-id="0206f-110">Call `TruncateSection` only if you have special section requirements that are not handled by other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0206f-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0206f-111">Requirements</span></span>  
 <span data-ttu-id="0206f-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0206f-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0206f-113">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="0206f-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0206f-114">**Libreria:** Usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="0206f-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0206f-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0206f-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0206f-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0206f-116">See also</span></span>

- [<span data-ttu-id="0206f-117">Interfaccia ICeeGen</span><span class="sxs-lookup"><span data-stu-id="0206f-117">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)

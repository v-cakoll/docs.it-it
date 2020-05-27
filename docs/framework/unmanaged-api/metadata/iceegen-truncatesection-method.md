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
ms.openlocfilehash: 387f5f01f2d2589c0b34e50b69398e1feb0e77e0
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008248"
---
# <a name="iceegentruncatesection-method"></a><span data-ttu-id="78710-102">Metodo ICeeGen::TruncateSection</span><span class="sxs-lookup"><span data-stu-id="78710-102">ICeeGen::TruncateSection Method</span></span>
<span data-ttu-id="78710-103">Tronca la sezione di codice specificata in base alla lunghezza specificata.</span><span class="sxs-lookup"><span data-stu-id="78710-103">Truncates the specified code section by the specified length.</span></span>  
  
 <span data-ttu-id="78710-104">Questo metodo è obsoleto e non deve essere utilizzato.</span><span class="sxs-lookup"><span data-stu-id="78710-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="78710-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="78710-105">Syntax</span></span>  
  
```cpp  
HRESULT TruncateSection (  
    [in]  HCEESECTION     section,  
    [in]  ULONG           len  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="78710-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="78710-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="78710-107">in Sezione da troncare.</span><span class="sxs-lookup"><span data-stu-id="78710-107">[in] The section to truncate.</span></span>  
  
 `len`  
 <span data-ttu-id="78710-108">in Lunghezza, in byte, in base alla quale troncare la sezione.</span><span class="sxs-lookup"><span data-stu-id="78710-108">[in] The length, in bytes, by which to truncate the section.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="78710-109">Commenti</span><span class="sxs-lookup"><span data-stu-id="78710-109">Remarks</span></span>  
 <span data-ttu-id="78710-110">Chiamare `TruncateSection` solo se si dispone di requisiti speciali per la sezione che non sono gestiti da altri metodi.</span><span class="sxs-lookup"><span data-stu-id="78710-110">Call `TruncateSection` only if you have special section requirements that are not handled by other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="78710-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="78710-111">Requirements</span></span>  
 <span data-ttu-id="78710-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="78710-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="78710-113">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="78710-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="78710-114">**Libreria:** Usato come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="78710-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="78710-115">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="78710-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78710-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="78710-116">See also</span></span>

- [<span data-ttu-id="78710-117">Interfaccia ICeeGen</span><span class="sxs-lookup"><span data-stu-id="78710-117">ICeeGen Interface</span></span>](iceegen-interface.md)

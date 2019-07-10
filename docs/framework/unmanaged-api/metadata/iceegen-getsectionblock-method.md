---
title: Metodo ICeeGen::GetSectionBlock
ms.date: 03/30/2017
api_name:
- ICeeGen.GetSectionBlock
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::GetSectionBlock
helpviewer_keywords:
- GetSectionBlock method [.NET Framework metadata]
- ICeeGen::GetSectionBlock method [.NET Framework metadata]
ms.assetid: 05c78aaf-5bbd-497e-9ae2-55f4fae0c5fb
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 84ccbd7a8be7d90a541fb2d54baa3d7f66d3d31e
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67746122"
---
# <a name="iceegengetsectionblock-method"></a><span data-ttu-id="9c713-102">Metodo ICeeGen::GetSectionBlock</span><span class="sxs-lookup"><span data-stu-id="9c713-102">ICeeGen::GetSectionBlock Method</span></span>
<span data-ttu-id="9c713-103">Ottiene un blocco di sezione del codice di base.</span><span class="sxs-lookup"><span data-stu-id="9c713-103">Gets a section block of the code base.</span></span>  
  
 <span data-ttu-id="9c713-104">Questo metodo è obsoleto e non deve essere utilizzato.</span><span class="sxs-lookup"><span data-stu-id="9c713-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9c713-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9c713-105">Syntax</span></span>  
  
```cpp  
HRESULT GetSectionBlock (  
    [in]  HCEESECTION    section,     
    [in]  ULONG          len,  
    [in]  ULONG          align     = 1,  
    [out] void           **ppBytes = 0  
);   
```  
  
## <a name="parameters"></a><span data-ttu-id="9c713-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="9c713-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="9c713-107">[in] La sezione da cui recuperare un blocco di base di codice.</span><span class="sxs-lookup"><span data-stu-id="9c713-107">[in] The section from which to retrieve a block of the code base.</span></span>  
  
 `len`  
 <span data-ttu-id="9c713-108">[in] La lunghezza del blocco da recuperare.</span><span class="sxs-lookup"><span data-stu-id="9c713-108">[in] The length of the block to be retrieved.</span></span>  
  
 `align`  
 <span data-ttu-id="9c713-109">[in] Byte, rispetto all'inizio della sezione, con la quale allineare il primo byte del blocco.</span><span class="sxs-lookup"><span data-stu-id="9c713-109">[in] The byte, relative to the beginning of the section, with which to align the first byte of the block.</span></span> <span data-ttu-id="9c713-110">Questa è la posizione del blocco all'interno della sezione.</span><span class="sxs-lookup"><span data-stu-id="9c713-110">This is the position of the block within the section.</span></span>  
  
 `ppBytes`  
 <span data-ttu-id="9c713-111">[out] Puntatore a una posizione che riceve l'indirizzo del blocco recuperato.</span><span class="sxs-lookup"><span data-stu-id="9c713-111">[out] A pointer to a location that receives the address of the retrieved block.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9c713-112">Note</span><span class="sxs-lookup"><span data-stu-id="9c713-112">Remarks</span></span>  
 <span data-ttu-id="9c713-113">Chiamare `GetSectionBlock` solo se si hanno requisiti di sezione speciale che non sono gestiti tramite altri metodi.</span><span class="sxs-lookup"><span data-stu-id="9c713-113">Call `GetSectionBlock` only if you have special section requirements that are not handled by other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9c713-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9c713-114">Requirements</span></span>  
 <span data-ttu-id="9c713-115">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9c713-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9c713-116">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="9c713-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9c713-117">**Libreria:** Usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="9c713-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="9c713-118">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9c713-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c713-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9c713-119">See also</span></span>

- [<span data-ttu-id="9c713-120">Interfaccia ICeeGen</span><span class="sxs-lookup"><span data-stu-id="9c713-120">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)

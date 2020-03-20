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
ms.openlocfilehash: a494b1aaa762549528e92ab93d18929ef73eb8da
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176084"
---
# <a name="iceegengetsectionblock-method"></a><span data-ttu-id="4cff8-102">Metodo ICeeGen::GetSectionBlock</span><span class="sxs-lookup"><span data-stu-id="4cff8-102">ICeeGen::GetSectionBlock Method</span></span>
<span data-ttu-id="4cff8-103">Ottiene un blocco di sezione della base di codice.</span><span class="sxs-lookup"><span data-stu-id="4cff8-103">Gets a section block of the code base.</span></span>  
  
 <span data-ttu-id="4cff8-104">Questo metodo è obsoleto e non deve essere utilizzato.</span><span class="sxs-lookup"><span data-stu-id="4cff8-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4cff8-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4cff8-105">Syntax</span></span>  
  
```cpp  
HRESULT GetSectionBlock (  
    [in]  HCEESECTION    section,
    [in]  ULONG          len,  
    [in]  ULONG          align     = 1,  
    [out] void           **ppBytes = 0  
);
```  
  
## <a name="parameters"></a><span data-ttu-id="4cff8-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="4cff8-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="4cff8-107">[in] Sezione da cui recuperare un blocco della base di codice.</span><span class="sxs-lookup"><span data-stu-id="4cff8-107">[in] The section from which to retrieve a block of the code base.</span></span>  
  
 `len`  
 <span data-ttu-id="4cff8-108">[in] Lunghezza del blocco da recuperare.</span><span class="sxs-lookup"><span data-stu-id="4cff8-108">[in] The length of the block to be retrieved.</span></span>  
  
 `align`  
 <span data-ttu-id="4cff8-109">[in] Byte, relativo all'inizio della sezione, con cui allineare il primo byte del blocco.</span><span class="sxs-lookup"><span data-stu-id="4cff8-109">[in] The byte, relative to the beginning of the section, with which to align the first byte of the block.</span></span> <span data-ttu-id="4cff8-110">Questa è la posizione del blocco all'interno della sezione.</span><span class="sxs-lookup"><span data-stu-id="4cff8-110">This is the position of the block within the section.</span></span>  
  
 `ppBytes`  
 <span data-ttu-id="4cff8-111">[fuori] Puntatore a una posizione che riceve l'indirizzo del blocco recuperato.</span><span class="sxs-lookup"><span data-stu-id="4cff8-111">[out] A pointer to a location that receives the address of the retrieved block.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4cff8-112">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="4cff8-112">Remarks</span></span>  
 <span data-ttu-id="4cff8-113">Chiamare `GetSectionBlock` solo se si dispone di requisiti di sezione speciali che non sono gestiti da altri metodi.</span><span class="sxs-lookup"><span data-stu-id="4cff8-113">Call `GetSectionBlock` only if you have special section requirements that are not handled by other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4cff8-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4cff8-114">Requirements</span></span>  
 <span data-ttu-id="4cff8-115">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4cff8-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4cff8-116">**Intestazione:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="4cff8-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4cff8-117">**Biblioteca:** Utilizzato come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4cff8-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="4cff8-118">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4cff8-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4cff8-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4cff8-119">See also</span></span>

- [<span data-ttu-id="4cff8-120">Interfaccia ICeeGen</span><span class="sxs-lookup"><span data-stu-id="4cff8-120">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)

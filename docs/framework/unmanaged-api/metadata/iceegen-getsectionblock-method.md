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
ms.openlocfilehash: 7e600f29a9036bb28031bd7854bc8cbb34c4566a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59200649"
---
# <a name="iceegengetsectionblock-method"></a><span data-ttu-id="f4326-102">Metodo ICeeGen::GetSectionBlock</span><span class="sxs-lookup"><span data-stu-id="f4326-102">ICeeGen::GetSectionBlock Method</span></span>
<span data-ttu-id="f4326-103">Ottiene un blocco di sezione del codice di base.</span><span class="sxs-lookup"><span data-stu-id="f4326-103">Gets a section block of the code base.</span></span>  
  
 <span data-ttu-id="f4326-104">Questo metodo è obsoleto e non deve essere utilizzato.</span><span class="sxs-lookup"><span data-stu-id="f4326-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f4326-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f4326-105">Syntax</span></span>  
  
```  
HRESULT GetSectionBlock (  
    [in]  HCEESECTION    section,     
    [in]  ULONG          len,  
    [in]  ULONG          align     = 1,  
    [out] void           **ppBytes = 0  
);   
```  
  
## <a name="parameters"></a><span data-ttu-id="f4326-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="f4326-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="f4326-107">[in] La sezione da cui recuperare un blocco di base di codice.</span><span class="sxs-lookup"><span data-stu-id="f4326-107">[in] The section from which to retrieve a block of the code base.</span></span>  
  
 `len`  
 <span data-ttu-id="f4326-108">[in] La lunghezza del blocco da recuperare.</span><span class="sxs-lookup"><span data-stu-id="f4326-108">[in] The length of the block to be retrieved.</span></span>  
  
 `align`  
 <span data-ttu-id="f4326-109">[in] Byte, rispetto all'inizio della sezione, con la quale allineare il primo byte del blocco.</span><span class="sxs-lookup"><span data-stu-id="f4326-109">[in] The byte, relative to the beginning of the section, with which to align the first byte of the block.</span></span> <span data-ttu-id="f4326-110">Questa è la posizione del blocco all'interno della sezione.</span><span class="sxs-lookup"><span data-stu-id="f4326-110">This is the position of the block within the section.</span></span>  
  
 `ppBytes`  
 <span data-ttu-id="f4326-111">[out] Puntatore a una posizione che riceve l'indirizzo del blocco recuperato.</span><span class="sxs-lookup"><span data-stu-id="f4326-111">[out] A pointer to a location that receives the address of the retrieved block.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f4326-112">Note</span><span class="sxs-lookup"><span data-stu-id="f4326-112">Remarks</span></span>  
 <span data-ttu-id="f4326-113">Chiamare `GetSectionBlock` solo se si hanno requisiti di sezione speciale che non sono gestiti tramite altri metodi.</span><span class="sxs-lookup"><span data-stu-id="f4326-113">Call `GetSectionBlock` only if you have special section requirements that are not handled by other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f4326-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f4326-114">Requirements</span></span>  
 <span data-ttu-id="f4326-115">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f4326-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f4326-116">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="f4326-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f4326-117">**Libreria:** Usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="f4326-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="f4326-118">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="f4326-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f4326-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f4326-119">See also</span></span>

- [<span data-ttu-id="f4326-120">Interfaccia ICeeGen</span><span class="sxs-lookup"><span data-stu-id="f4326-120">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)

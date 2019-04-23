---
title: Metodo ICeeGen::AllocateMethodBuffer
ms.date: 03/30/2017
api_name:
- ICeeGen.AllocateMethodBuffer
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::AllocateMethodBuffer
helpviewer_keywords:
- AllocateMethodBuffer method [.NET Framework metadata]
- ICeeGen::AllocateMethodBuffer method [.NET Framework metadata]
ms.assetid: 845ab77e-9639-47f5-99fb-f3b619e3e779
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7be1bd2934fbb2e09a39c3042fa9ae314e89d629
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59083764"
---
# <a name="iceegenallocatemethodbuffer-method"></a><span data-ttu-id="bac2e-102">Metodo ICeeGen::AllocateMethodBuffer</span><span class="sxs-lookup"><span data-stu-id="bac2e-102">ICeeGen::AllocateMethodBuffer Method</span></span>
<span data-ttu-id="bac2e-103">Crea un buffer della dimensione specificata per un metodo e ottiene l'indirizzo virtuale relativo del metodo.</span><span class="sxs-lookup"><span data-stu-id="bac2e-103">Creates a buffer of the specified size for a method, and gets the relative virtual address of the method.</span></span>  
  
 <span data-ttu-id="bac2e-104">Questo metodo è obsoleto e non deve essere utilizzato.</span><span class="sxs-lookup"><span data-stu-id="bac2e-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bac2e-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bac2e-105">Syntax</span></span>  
  
```  
HRESULT AllocateMethodBuffer (   
    [in]  ULONG    cchBuffer,   
    [out] UCHAR    **lpBuffer,  
    [out] ULONG    *RVA  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bac2e-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="bac2e-106">Parameters</span></span>  
 `cchBuffer`  
 <span data-ttu-id="bac2e-107">[in] La lunghezza del buffer da creare.</span><span class="sxs-lookup"><span data-stu-id="bac2e-107">[in] The length of the buffer to create.</span></span>  
  
 `lpBuffer`  
 <span data-ttu-id="bac2e-108">[out] Il buffer restituito.</span><span class="sxs-lookup"><span data-stu-id="bac2e-108">[out] The returned buffer.</span></span>  
  
 `RVA`  
 <span data-ttu-id="bac2e-109">[out] L'indirizzo virtuale relativo del metodo.</span><span class="sxs-lookup"><span data-stu-id="bac2e-109">[out] The relative virtual address of the method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bac2e-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="bac2e-110">Requirements</span></span>  
 <span data-ttu-id="bac2e-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bac2e-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bac2e-112">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="bac2e-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="bac2e-113">**Libreria:** Usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="bac2e-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="bac2e-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bac2e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bac2e-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bac2e-115">See also</span></span>

- [<span data-ttu-id="bac2e-116">Interfaccia ICeeGen</span><span class="sxs-lookup"><span data-stu-id="bac2e-116">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)

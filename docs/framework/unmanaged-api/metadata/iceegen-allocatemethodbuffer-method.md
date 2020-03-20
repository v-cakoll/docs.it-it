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
ms.openlocfilehash: 38b9ea2ffab439f55f0a6d34d7f42c7669629168
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177919"
---
# <a name="iceegenallocatemethodbuffer-method"></a><span data-ttu-id="5a7f8-102">Metodo ICeeGen::AllocateMethodBuffer</span><span class="sxs-lookup"><span data-stu-id="5a7f8-102">ICeeGen::AllocateMethodBuffer Method</span></span>
<span data-ttu-id="5a7f8-103">Crea un buffer della dimensione specificata per un metodo e ottiene l'indirizzo virtuale relativo del metodo.</span><span class="sxs-lookup"><span data-stu-id="5a7f8-103">Creates a buffer of the specified size for a method, and gets the relative virtual address of the method.</span></span>  
  
 <span data-ttu-id="5a7f8-104">Questo metodo è obsoleto e non deve essere utilizzato.</span><span class="sxs-lookup"><span data-stu-id="5a7f8-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a7f8-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5a7f8-105">Syntax</span></span>  
  
```cpp  
HRESULT AllocateMethodBuffer (
    [in]  ULONG    cchBuffer,
    [out] UCHAR    **lpBuffer,  
    [out] ULONG    *RVA  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5a7f8-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="5a7f8-106">Parameters</span></span>  
 `cchBuffer`  
 <span data-ttu-id="5a7f8-107">[in] Lunghezza del buffer da creare.</span><span class="sxs-lookup"><span data-stu-id="5a7f8-107">[in] The length of the buffer to create.</span></span>  
  
 `lpBuffer`  
 <span data-ttu-id="5a7f8-108">[fuori] Buffer restituito.</span><span class="sxs-lookup"><span data-stu-id="5a7f8-108">[out] The returned buffer.</span></span>  
  
 `RVA`  
 <span data-ttu-id="5a7f8-109">[fuori] Indirizzo virtuale relativo del metodo.</span><span class="sxs-lookup"><span data-stu-id="5a7f8-109">[out] The relative virtual address of the method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5a7f8-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5a7f8-110">Requirements</span></span>  
 <span data-ttu-id="5a7f8-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5a7f8-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5a7f8-112">**Intestazione:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="5a7f8-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5a7f8-113">**Biblioteca:** Utilizzato come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5a7f8-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5a7f8-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5a7f8-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a7f8-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5a7f8-115">See also</span></span>

- [<span data-ttu-id="5a7f8-116">Interfaccia ICeeGen</span><span class="sxs-lookup"><span data-stu-id="5a7f8-116">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)

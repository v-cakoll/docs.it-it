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
ms.openlocfilehash: f56376d4400f4e24aefe2d1e5d4ad504b1d281cf
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33446004"
---
# <a name="iceegenallocatemethodbuffer-method"></a><span data-ttu-id="40f6a-102">Metodo ICeeGen::AllocateMethodBuffer</span><span class="sxs-lookup"><span data-stu-id="40f6a-102">ICeeGen::AllocateMethodBuffer Method</span></span>
<span data-ttu-id="40f6a-103">Crea un buffer della dimensione specificata per un metodo e ottiene l'indirizzo virtuale relativo del metodo.</span><span class="sxs-lookup"><span data-stu-id="40f6a-103">Creates a buffer of the specified size for a method, and gets the relative virtual address of the method.</span></span>  
  
 <span data-ttu-id="40f6a-104">Questo metodo è obsoleto e non deve essere utilizzato.</span><span class="sxs-lookup"><span data-stu-id="40f6a-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40f6a-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="40f6a-105">Syntax</span></span>  
  
```  
HRESULT AllocateMethodBuffer (   
    [in]  ULONG    cchBuffer,   
    [out] UCHAR    **lpBuffer,  
    [out] ULONG    *RVA  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="40f6a-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="40f6a-106">Parameters</span></span>  
 `cchBuffer`  
 <span data-ttu-id="40f6a-107">[in] La lunghezza del buffer da creare.</span><span class="sxs-lookup"><span data-stu-id="40f6a-107">[in] The length of the buffer to create.</span></span>  
  
 `lpBuffer`  
 <span data-ttu-id="40f6a-108">[out] Il buffer restituito.</span><span class="sxs-lookup"><span data-stu-id="40f6a-108">[out] The returned buffer.</span></span>  
  
 `RVA`  
 <span data-ttu-id="40f6a-109">[out] L'indirizzo virtuale relativo del metodo.</span><span class="sxs-lookup"><span data-stu-id="40f6a-109">[out] The relative virtual address of the method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="40f6a-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="40f6a-110">Requirements</span></span>  
 <span data-ttu-id="40f6a-111">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="40f6a-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="40f6a-112">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="40f6a-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="40f6a-113">**Libreria:** usata come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="40f6a-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="40f6a-114">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="40f6a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40f6a-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="40f6a-115">See Also</span></span>  
 [<span data-ttu-id="40f6a-116">Interfaccia ICeeGen</span><span class="sxs-lookup"><span data-stu-id="40f6a-116">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)

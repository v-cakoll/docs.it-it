---
title: Metodo ICeeGen::GetMethodBuffer
ms.date: 03/30/2017
api_name:
- ICeeGen.GetMethodBuffer
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::GetMethodBuffer
helpviewer_keywords:
- ICeeGen::GetMethodBuffer method [.NET Framework metadata]
- GetMethodBuffer method [.NET Framework metadata]
ms.assetid: c7c5b39a-d4ac-41f1-9d1e-44163f563a49
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c0aea6185095a30aae9197c875aa9b9ac581d406
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59121537"
---
# <a name="iceegengetmethodbuffer-method"></a><span data-ttu-id="94691-102">Metodo ICeeGen::GetMethodBuffer</span><span class="sxs-lookup"><span data-stu-id="94691-102">ICeeGen::GetMethodBuffer Method</span></span>
<span data-ttu-id="94691-103">Ottiene un buffer di dimensione appropriata per il metodo in corrispondenza dell'indirizzo virtuale relativo specificato.</span><span class="sxs-lookup"><span data-stu-id="94691-103">Gets a buffer of the appropriate size for the method at the specified relative virtual address.</span></span>  
  
 <span data-ttu-id="94691-104">Questo metodo è obsoleto e non deve essere utilizzato.</span><span class="sxs-lookup"><span data-stu-id="94691-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="94691-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="94691-105">Syntax</span></span>  
  
```  
HRESULT GetMethodBuffer (  
    [in]  ULONG       RVA,  
    [out] UCHAR       **lpBuffer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="94691-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="94691-106">Parameters</span></span>  
 `RVA`  
 <span data-ttu-id="94691-107">[in] L'indirizzo virtuale relativo del metodo per cui restituire un buffer.</span><span class="sxs-lookup"><span data-stu-id="94691-107">[in] The relative virtual address of the method for which to return a buffer.</span></span>  
  
 `lpBuffer`  
 <span data-ttu-id="94691-108">[out] Puntatore al buffer restituito.</span><span class="sxs-lookup"><span data-stu-id="94691-108">[out] A pointer to the returned buffer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="94691-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="94691-109">Requirements</span></span>  
 <span data-ttu-id="94691-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="94691-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="94691-111">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="94691-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="94691-112">**Libreria:** Usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="94691-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="94691-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="94691-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94691-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="94691-114">See also</span></span>

- [<span data-ttu-id="94691-115">Interfaccia ICeeGen</span><span class="sxs-lookup"><span data-stu-id="94691-115">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)

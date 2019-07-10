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
ms.openlocfilehash: 14ea8dab2c4258fe490ef362fd527d80bd8a0178
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67746099"
---
# <a name="iceegengetmethodbuffer-method"></a><span data-ttu-id="2f615-102">Metodo ICeeGen::GetMethodBuffer</span><span class="sxs-lookup"><span data-stu-id="2f615-102">ICeeGen::GetMethodBuffer Method</span></span>
<span data-ttu-id="2f615-103">Ottiene un buffer di dimensione appropriata per il metodo in corrispondenza dell'indirizzo virtuale relativo specificato.</span><span class="sxs-lookup"><span data-stu-id="2f615-103">Gets a buffer of the appropriate size for the method at the specified relative virtual address.</span></span>  
  
 <span data-ttu-id="2f615-104">Questo metodo è obsoleto e non deve essere utilizzato.</span><span class="sxs-lookup"><span data-stu-id="2f615-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f615-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2f615-105">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodBuffer (  
    [in]  ULONG       RVA,  
    [out] UCHAR       **lpBuffer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2f615-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="2f615-106">Parameters</span></span>  
 `RVA`  
 <span data-ttu-id="2f615-107">[in] L'indirizzo virtuale relativo del metodo per cui restituire un buffer.</span><span class="sxs-lookup"><span data-stu-id="2f615-107">[in] The relative virtual address of the method for which to return a buffer.</span></span>  
  
 `lpBuffer`  
 <span data-ttu-id="2f615-108">[out] Puntatore al buffer restituito.</span><span class="sxs-lookup"><span data-stu-id="2f615-108">[out] A pointer to the returned buffer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2f615-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2f615-109">Requirements</span></span>  
 <span data-ttu-id="2f615-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2f615-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2f615-111">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="2f615-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2f615-112">**Libreria:** Usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="2f615-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="2f615-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2f615-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f615-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2f615-114">See also</span></span>

- [<span data-ttu-id="2f615-115">Interfaccia ICeeGen</span><span class="sxs-lookup"><span data-stu-id="2f615-115">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)

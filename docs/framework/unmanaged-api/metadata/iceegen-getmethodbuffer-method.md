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
ms.openlocfilehash: a093b18f72cc99c53951b3dc588ce0cff3c7fefd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33442608"
---
# <a name="iceegengetmethodbuffer-method"></a><span data-ttu-id="d8348-102">Metodo ICeeGen::GetMethodBuffer</span><span class="sxs-lookup"><span data-stu-id="d8348-102">ICeeGen::GetMethodBuffer Method</span></span>
<span data-ttu-id="d8348-103">Ottiene un buffer di dimensioni appropriate per il metodo all'indirizzo virtuale relativo specificato.</span><span class="sxs-lookup"><span data-stu-id="d8348-103">Gets a buffer of the appropriate size for the method at the specified relative virtual address.</span></span>  
  
 <span data-ttu-id="d8348-104">Questo metodo è obsoleto e non deve essere utilizzato.</span><span class="sxs-lookup"><span data-stu-id="d8348-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8348-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d8348-105">Syntax</span></span>  
  
```  
HRESULT GetMethodBuffer (  
    [in]  ULONG       RVA,  
    [out] UCHAR       **lpBuffer  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d8348-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="d8348-106">Parameters</span></span>  
 `RVA`  
 <span data-ttu-id="d8348-107">[in] L'indirizzo virtuale relativo del metodo per cui restituire un buffer.</span><span class="sxs-lookup"><span data-stu-id="d8348-107">[in] The relative virtual address of the method for which to return a buffer.</span></span>  
  
 `lpBuffer`  
 <span data-ttu-id="d8348-108">[out] Puntatore al buffer restituito.</span><span class="sxs-lookup"><span data-stu-id="d8348-108">[out] A pointer to the returned buffer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d8348-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d8348-109">Requirements</span></span>  
 <span data-ttu-id="d8348-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d8348-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d8348-111">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="d8348-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d8348-112">**Libreria:** usata come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="d8348-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d8348-113">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d8348-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8348-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d8348-114">See Also</span></span>  
 [<span data-ttu-id="d8348-115">Interfaccia ICeeGen</span><span class="sxs-lookup"><span data-stu-id="d8348-115">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)

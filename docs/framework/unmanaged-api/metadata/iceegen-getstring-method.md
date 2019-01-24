---
title: Metodo ICeeGen::GetString
ms.date: 03/30/2017
api_name:
- ICeeGen.GetString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::GetString
helpviewer_keywords:
- ICeeGen::GetString method [.NET Framework metadata]
- GetString method, ICeeGen interface [.NET Framework metadata]
ms.assetid: 7cc22562-128c-440a-9147-55ff20f173d7
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3d8d6a0ebecb4fbb9ba277844710c775d80648e5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54716817"
---
# <a name="iceegengetstring-method"></a><span data-ttu-id="0e7b8-102">Metodo ICeeGen::GetString</span><span class="sxs-lookup"><span data-stu-id="0e7b8-102">ICeeGen::GetString Method</span></span>
<span data-ttu-id="0e7b8-103">Ottiene la stringa archiviata all'indirizzo virtuale relativo specificato.</span><span class="sxs-lookup"><span data-stu-id="0e7b8-103">Gets the string stored at the specified relative virtual address.</span></span>  
  
 <span data-ttu-id="0e7b8-104">Questo metodo è obsoleto e non deve essere utilizzato.</span><span class="sxs-lookup"><span data-stu-id="0e7b8-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0e7b8-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0e7b8-105">Syntax</span></span>  
  
```  
HRESULT GetString (  
    [in]  ULONG      RVA,   
    [out] LPWSTR     *lpString  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0e7b8-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="0e7b8-106">Parameters</span></span>  
 `RVA`  
 <span data-ttu-id="0e7b8-107">[in] L'indirizzo virtuale relativo della stringa da restituire.</span><span class="sxs-lookup"><span data-stu-id="0e7b8-107">[in] The relative virtual address of the string to return.</span></span>  
  
 `lpString`  
 <span data-ttu-id="0e7b8-108">[out] La stringa restituita.</span><span class="sxs-lookup"><span data-stu-id="0e7b8-108">[out] The returned string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0e7b8-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0e7b8-109">Requirements</span></span>  
 <span data-ttu-id="0e7b8-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0e7b8-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0e7b8-111">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="0e7b8-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0e7b8-112">**Libreria:** Usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="0e7b8-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0e7b8-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0e7b8-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e7b8-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0e7b8-114">See also</span></span>
- [<span data-ttu-id="0e7b8-115">Interfaccia ICeeGen</span><span class="sxs-lookup"><span data-stu-id="0e7b8-115">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)

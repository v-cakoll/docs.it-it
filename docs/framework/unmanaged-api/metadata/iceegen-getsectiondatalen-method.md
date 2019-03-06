---
title: Metodo ICeeGen::GetSectionDataLen
ms.date: 03/30/2017
api_name:
- ICeeGen.GetSectionDataLen
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::GetSectionDataLen
helpviewer_keywords:
- ICeeGen::GetSectionDataLen method [.NET Framework metadata]
- GetSectionDataLen method [.NET Framework metadata]
ms.assetid: e2a06ee4-b8ee-49c7-935a-c1031a29eef2
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3983916f56e8451e7628db3902001bd13f503114
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57487928"
---
# <a name="iceegengetsectiondatalen-method"></a><span data-ttu-id="3d4c1-102">Metodo ICeeGen::GetSectionDataLen</span><span class="sxs-lookup"><span data-stu-id="3d4c1-102">ICeeGen::GetSectionDataLen Method</span></span>
<span data-ttu-id="3d4c1-103">Ottiene la lunghezza della sezione specificata.</span><span class="sxs-lookup"><span data-stu-id="3d4c1-103">Gets the length of the specified section.</span></span>  
  
 <span data-ttu-id="3d4c1-104">Questo metodo è obsoleto e non deve essere utilizzato.</span><span class="sxs-lookup"><span data-stu-id="3d4c1-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d4c1-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3d4c1-105">Syntax</span></span>  
  
```  
HRESULT GetSectionDataLen (  
    [in]  HCEESECTION  section,  
    [out] ULONG        *dataLen  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3d4c1-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="3d4c1-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="3d4c1-107">[in] La sezione di dati verrà recuperata la cui lunghezza.</span><span class="sxs-lookup"><span data-stu-id="3d4c1-107">[in] The data section whose length will be retrieved.</span></span>  
  
 `dataLen`  
 <span data-ttu-id="3d4c1-108">[out] La lunghezza restituita della sezione specificata.</span><span class="sxs-lookup"><span data-stu-id="3d4c1-108">[out] The returned length of the specified section.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3d4c1-109">Note</span><span class="sxs-lookup"><span data-stu-id="3d4c1-109">Remarks</span></span>  
 <span data-ttu-id="3d4c1-110">Chiamare `GetSectionDataLen` solo se si hanno requisiti di sezione speciale che non sono gestiti tramite altri metodi.</span><span class="sxs-lookup"><span data-stu-id="3d4c1-110">Call `GetSectionDataLen` only if you have special section requirements that are not handled by other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3d4c1-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3d4c1-111">Requirements</span></span>  
 <span data-ttu-id="3d4c1-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3d4c1-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3d4c1-113">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="3d4c1-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3d4c1-114">**Libreria:** Usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="3d4c1-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3d4c1-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3d4c1-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d4c1-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3d4c1-116">See also</span></span>
- [<span data-ttu-id="3d4c1-117">Interfaccia ICeeGen</span><span class="sxs-lookup"><span data-stu-id="3d4c1-117">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)

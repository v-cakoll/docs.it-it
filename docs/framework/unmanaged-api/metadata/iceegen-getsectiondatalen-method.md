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
ms.openlocfilehash: b85cdee4a65e91c51fdb014bdcc4797b99214daf
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33446131"
---
# <a name="iceegengetsectiondatalen-method"></a><span data-ttu-id="17b49-102">Metodo ICeeGen::GetSectionDataLen</span><span class="sxs-lookup"><span data-stu-id="17b49-102">ICeeGen::GetSectionDataLen Method</span></span>
<span data-ttu-id="17b49-103">Ottiene la lunghezza della sezione specificata.</span><span class="sxs-lookup"><span data-stu-id="17b49-103">Gets the length of the specified section.</span></span>  
  
 <span data-ttu-id="17b49-104">Questo metodo è obsoleto e non deve essere utilizzato.</span><span class="sxs-lookup"><span data-stu-id="17b49-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="17b49-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="17b49-105">Syntax</span></span>  
  
```  
HRESULT GetSectionDataLen (  
    [in]  HCEESECTION  section,  
    [out] ULONG        *dataLen  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="17b49-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="17b49-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="17b49-107">[in] La sezione di dati la cui lunghezza verrà recuperata.</span><span class="sxs-lookup"><span data-stu-id="17b49-107">[in] The data section whose length will be retrieved.</span></span>  
  
 `dataLen`  
 <span data-ttu-id="17b49-108">[out] La lunghezza restituita della sezione specificata.</span><span class="sxs-lookup"><span data-stu-id="17b49-108">[out] The returned length of the specified section.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="17b49-109">Note</span><span class="sxs-lookup"><span data-stu-id="17b49-109">Remarks</span></span>  
 <span data-ttu-id="17b49-110">Chiamare `GetSectionDataLen` solo se sono necessari requisiti speciali di sezione che non sono gestiti da altri metodi.</span><span class="sxs-lookup"><span data-stu-id="17b49-110">Call `GetSectionDataLen` only if you have special section requirements that are not handled by other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="17b49-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="17b49-111">Requirements</span></span>  
 <span data-ttu-id="17b49-112">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="17b49-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="17b49-113">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="17b49-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="17b49-114">**Libreria:** usata come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="17b49-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="17b49-115">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="17b49-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17b49-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="17b49-116">See Also</span></span>  
 [<span data-ttu-id="17b49-117">Interfaccia ICeeGen</span><span class="sxs-lookup"><span data-stu-id="17b49-117">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)

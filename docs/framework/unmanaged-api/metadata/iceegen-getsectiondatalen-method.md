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
ms.openlocfilehash: 277e2584049fae397cf91281a65d05b0b49d9454
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448084"
---
# <a name="iceegengetsectiondatalen-method"></a><span data-ttu-id="a7f69-102">Metodo ICeeGen::GetSectionDataLen</span><span class="sxs-lookup"><span data-stu-id="a7f69-102">ICeeGen::GetSectionDataLen Method</span></span>
<span data-ttu-id="a7f69-103">Gets the length of the specified section.</span><span class="sxs-lookup"><span data-stu-id="a7f69-103">Gets the length of the specified section.</span></span>  
  
 <span data-ttu-id="a7f69-104">This method is obsolete and should not be used.</span><span class="sxs-lookup"><span data-stu-id="a7f69-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7f69-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a7f69-105">Syntax</span></span>  
  
```cpp  
HRESULT GetSectionDataLen (  
    [in]  HCEESECTION  section,  
    [out] ULONG        *dataLen  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a7f69-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="a7f69-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="a7f69-107">[in] The data section whose length will be retrieved.</span><span class="sxs-lookup"><span data-stu-id="a7f69-107">[in] The data section whose length will be retrieved.</span></span>  
  
 `dataLen`  
 <span data-ttu-id="a7f69-108">[out] The returned length of the specified section.</span><span class="sxs-lookup"><span data-stu-id="a7f69-108">[out] The returned length of the specified section.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a7f69-109">Note</span><span class="sxs-lookup"><span data-stu-id="a7f69-109">Remarks</span></span>  
 <span data-ttu-id="a7f69-110">Call `GetSectionDataLen` only if you have special section requirements that are not handled by other methods.</span><span class="sxs-lookup"><span data-stu-id="a7f69-110">Call `GetSectionDataLen` only if you have special section requirements that are not handled by other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a7f69-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a7f69-111">Requirements</span></span>  
 <span data-ttu-id="a7f69-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a7f69-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a7f69-113">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="a7f69-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a7f69-114">**Library:** Used as a resource in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a7f69-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a7f69-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a7f69-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7f69-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a7f69-116">See also</span></span>

- [<span data-ttu-id="a7f69-117">Interfaccia ICeeGen</span><span class="sxs-lookup"><span data-stu-id="a7f69-117">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)

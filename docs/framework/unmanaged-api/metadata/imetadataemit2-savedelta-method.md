---
title: Metodo IMetaDataEmit2::SaveDelta
ms.date: 03/30/2017
api_name:
- IMetaDataEmit2.SaveDelta
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit2::SaveDelta
helpviewer_keywords:
- IMetaDataEmit2::SaveDelta method [.NET Framework metadata]
- SaveDelta method [.NET Framework metadata]
ms.assetid: b95739fe-d2fa-4776-ae0d-31d9707ef799
topic_type:
- apiref
ms.openlocfilehash: d3e25f271fc434785e25e7b226ad98f86b5f8dfc
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84492785"
---
# <a name="imetadataemit2savedelta-method"></a><span data-ttu-id="805b3-102">Metodo IMetaDataEmit2::SaveDelta</span><span class="sxs-lookup"><span data-stu-id="805b3-102">IMetaDataEmit2::SaveDelta Method</span></span>
<span data-ttu-id="805b3-103">Salva le modifiche dalla sessione di modifica e continuazione corrente nel file specificato.</span><span class="sxs-lookup"><span data-stu-id="805b3-103">Saves changes from the current edit-and-continue session to the specified file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="805b3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="805b3-104">Syntax</span></span>  
  
```cpp  
HRESULT SaveDelta (  
    [in] LPCWSTR     szFile,
    [in] DWORD       dwSaveFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="805b3-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="805b3-105">Parameters</span></span>  
 `szFile`  
 <span data-ttu-id="805b3-106">in Nome file in cui salvare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="805b3-106">[in] The file name under which to save changes.</span></span>  
  
 `dwSaveFlags`  
 <span data-ttu-id="805b3-107">[in] Riservato.</span><span class="sxs-lookup"><span data-stu-id="805b3-107">[in] Reserved.</span></span> <span data-ttu-id="805b3-108">Deve essere zero.</span><span class="sxs-lookup"><span data-stu-id="805b3-108">Must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="805b3-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="805b3-109">Requirements</span></span>  
 <span data-ttu-id="805b3-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="805b3-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="805b3-111">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="805b3-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="805b3-112">**Libreria:** Usato come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="805b3-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="805b3-113">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="805b3-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="805b3-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="805b3-114">See also</span></span>

- [<span data-ttu-id="805b3-115">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="805b3-115">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
- [<span data-ttu-id="805b3-116">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="805b3-116">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)

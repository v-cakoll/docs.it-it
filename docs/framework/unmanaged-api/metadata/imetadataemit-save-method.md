---
title: Metodo IMetaDataEmit::Save
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.Save
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::Save
helpviewer_keywords:
- Save method, IMetaDataEmit interface [.NET Framework metadata]
- IMetaDataEmit::Save method [.NET Framework metadata]
ms.assetid: c1de8400-adfe-4a71-b828-a1d0cc1ea505
topic_type:
- apiref
ms.openlocfilehash: 23f6a301c4c11be92e05dbac0d4f69817d857a28
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84003951"
---
# <a name="imetadataemitsave-method"></a><span data-ttu-id="ec5d1-102">Metodo IMetaDataEmit::Save</span><span class="sxs-lookup"><span data-stu-id="ec5d1-102">IMetaDataEmit::Save Method</span></span>
<span data-ttu-id="ec5d1-103">Salva tutti i metadati nell'ambito corrente nel file in corrispondenza dell'indirizzo specificato.</span><span class="sxs-lookup"><span data-stu-id="ec5d1-103">Saves all metadata in the current scope to the file at the specified address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec5d1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ec5d1-104">Syntax</span></span>  
  
```cpp  
HRESULT Save (
    [in]  LPCWSTR     szFile,
    [in]  DWORD       dwSaveFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ec5d1-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ec5d1-105">Parameters</span></span>  
 `wzFile`  
 <span data-ttu-id="ec5d1-106">in Nome del file in cui salvare.</span><span class="sxs-lookup"><span data-stu-id="ec5d1-106">[in] The name of the file to save to.</span></span> <span data-ttu-id="ec5d1-107">Se questo valore è null, la copia in memoria verrà salvata nell'ultima posizione utilizzata.</span><span class="sxs-lookup"><span data-stu-id="ec5d1-107">If this value is null, the in-memory copy will be saved to the last location that was used.</span></span>  
  
 `dwSaveFlags`  
 <span data-ttu-id="ec5d1-108">[in] Riservato.</span><span class="sxs-lookup"><span data-stu-id="ec5d1-108">[in] Reserved.</span></span> <span data-ttu-id="ec5d1-109">Deve essere zero.</span><span class="sxs-lookup"><span data-stu-id="ec5d1-109">Must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ec5d1-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ec5d1-110">Requirements</span></span>  
 <span data-ttu-id="ec5d1-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ec5d1-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ec5d1-112">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="ec5d1-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ec5d1-113">**Libreria:** Usato come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="ec5d1-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ec5d1-114">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ec5d1-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec5d1-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ec5d1-115">See also</span></span>

- [<span data-ttu-id="ec5d1-116">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="ec5d1-116">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="ec5d1-117">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="ec5d1-117">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)

---
title: Metodo IMetaDataTables::GetGuidHeapSize
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetGuidHeapSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetGuidHeapSize
helpviewer_keywords:
- GetGuidHeapSize method [.NET Framework metadata]
- IMetaDataTables::GetGuidHeapSize method [.NET Framework metadata]
ms.assetid: e875cbee-1ad9-4f1a-bf03-38cdb8ff371a
topic_type:
- apiref
ms.openlocfilehash: 71a75defa72e4fe3594b4d0ceff45273b3a35395
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84490354"
---
# <a name="imetadatatablesgetguidheapsize-method"></a><span data-ttu-id="c6445-102">Metodo IMetaDataTables::GetGuidHeapSize</span><span class="sxs-lookup"><span data-stu-id="c6445-102">IMetaDataTables::GetGuidHeapSize Method</span></span>
<span data-ttu-id="c6445-103">Ottiene la dimensione, in byte, dell'heap GUID.</span><span class="sxs-lookup"><span data-stu-id="c6445-103">Gets the size, in bytes, of the GUID heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6445-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c6445-104">Syntax</span></span>  
  
```cpp  
HRESULT GetGuidHeapSize (  
    [out] ULONG   *pcbGuids  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c6445-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="c6445-105">Parameters</span></span>  
 `pcbGuids`  
 <span data-ttu-id="c6445-106">out Puntatore alla dimensione, in byte, dell'heap GUID.</span><span class="sxs-lookup"><span data-stu-id="c6445-106">[out] A pointer to the size, in bytes, of the GUID heap.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c6445-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c6445-107">Requirements</span></span>  
 <span data-ttu-id="c6445-108">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c6445-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c6445-109">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="c6445-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c6445-110">**Libreria:** Usato come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="c6445-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c6445-111">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c6445-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6445-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c6445-112">See also</span></span>

- [<span data-ttu-id="c6445-113">Interfaccia IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="c6445-113">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
- [<span data-ttu-id="c6445-114">Interfaccia IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="c6445-114">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)

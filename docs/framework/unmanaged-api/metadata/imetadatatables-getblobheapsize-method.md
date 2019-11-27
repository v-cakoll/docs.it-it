---
title: Metodo IMetaDataTables::GetBlobHeapSize
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetBlobHeapSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetBlobHeapSize
helpviewer_keywords:
- GetBlobHeapSize method [.NET Framework metadata]
- IMetaDataTables::GetBlobHeapSize method [.NET Framework metadata]
ms.assetid: 6330a9ee-8cd5-4299-86f1-b4de2c701a0d
topic_type:
- apiref
ms.openlocfilehash: 715456317b880de89b6abdf1fa82acd040d17ced
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74442035"
---
# <a name="imetadatatablesgetblobheapsize-method"></a><span data-ttu-id="b1515-102">Metodo IMetaDataTables::GetBlobHeapSize</span><span class="sxs-lookup"><span data-stu-id="b1515-102">IMetaDataTables::GetBlobHeapSize Method</span></span>
<span data-ttu-id="b1515-103">Ottiene la dimensione, in byte, dell'heap di oggetti binari di grandi dimensioni (BLOB).</span><span class="sxs-lookup"><span data-stu-id="b1515-103">Gets the size, in bytes, of the binary large object (BLOB) heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b1515-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b1515-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBlobHeapSize (  
    [out] ULONG     *pcbBlobs  
);   
```  
  
## <a name="parameters"></a><span data-ttu-id="b1515-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="b1515-105">Parameters</span></span>  
 `pcbBlobs`  
 <span data-ttu-id="b1515-106">out Puntatore alla dimensione, in byte, dell'heap BLOB.</span><span class="sxs-lookup"><span data-stu-id="b1515-106">[out] A pointer to the size, in bytes, of the BLOB heap.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b1515-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b1515-107">Requirements</span></span>  
 <span data-ttu-id="b1515-108">**Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b1515-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b1515-109">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="b1515-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b1515-110">**Libreria:** Usato come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="b1515-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b1515-111">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b1515-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1515-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b1515-112">See also</span></span>

- [<span data-ttu-id="b1515-113">Interfaccia IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="b1515-113">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="b1515-114">Interfaccia IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="b1515-114">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)

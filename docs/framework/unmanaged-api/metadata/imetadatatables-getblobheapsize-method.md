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
ms.openlocfilehash: c32407c3fc0bc5a045b80ec48937699826d981af
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177169"
---
# <a name="imetadatatablesgetblobheapsize-method"></a><span data-ttu-id="c8405-102">Metodo IMetaDataTables::GetBlobHeapSize</span><span class="sxs-lookup"><span data-stu-id="c8405-102">IMetaDataTables::GetBlobHeapSize Method</span></span>
<span data-ttu-id="c8405-103">Ottiene le dimensioni, in byte, dell'heap BLOB (Binary Large Object).</span><span class="sxs-lookup"><span data-stu-id="c8405-103">Gets the size, in bytes, of the binary large object (BLOB) heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8405-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c8405-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBlobHeapSize (  
    [out] ULONG     *pcbBlobs  
);
```  
  
## <a name="parameters"></a><span data-ttu-id="c8405-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="c8405-105">Parameters</span></span>  
 `pcbBlobs`  
 <span data-ttu-id="c8405-106">[fuori] Puntatore alla dimensione, in byte, dell'heap BLOB.</span><span class="sxs-lookup"><span data-stu-id="c8405-106">[out] A pointer to the size, in bytes, of the BLOB heap.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c8405-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c8405-107">Requirements</span></span>  
 <span data-ttu-id="c8405-108">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c8405-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c8405-109">**Intestazione:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="c8405-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c8405-110">**Biblioteca:** Utilizzato come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c8405-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c8405-111">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c8405-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8405-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c8405-112">See also</span></span>

- [<span data-ttu-id="c8405-113">Interfaccia IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="c8405-113">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="c8405-114">Interfaccia IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="c8405-114">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)

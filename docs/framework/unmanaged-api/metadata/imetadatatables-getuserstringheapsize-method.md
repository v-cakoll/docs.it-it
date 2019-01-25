---
title: Metodo IMetaDataTables::GetUserStringHeapSize
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetUserStringHeapSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetUserStringHeapSize
helpviewer_keywords:
- IMetaDataTables::GetUserStringHeapSize method [.NET Framework metadata]
- GetUserStringHeapSize method [.NET Framework metadata]
ms.assetid: cba9e4d6-9461-4420-9614-96ff7039ec9c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 64634f961064feb3d2db11d421fea920f1e2d16b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54669055"
---
# <a name="imetadatatablesgetuserstringheapsize-method"></a><span data-ttu-id="1d999-102">Metodo IMetaDataTables::GetUserStringHeapSize</span><span class="sxs-lookup"><span data-stu-id="1d999-102">IMetaDataTables::GetUserStringHeapSize Method</span></span>
<span data-ttu-id="1d999-103">Ottiene la dimensione, espressa in byte, dell'heap delle stringhe utente.</span><span class="sxs-lookup"><span data-stu-id="1d999-103">Gets the size, in bytes, of the user string heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1d999-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1d999-104">Syntax</span></span>  
  
```  
HRESULT GetUserStringHeapSize (  
    [out] ULONG   *pcbBlobs  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1d999-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="1d999-105">Parameters</span></span>  
 `pcbBlobs`  
 <span data-ttu-id="1d999-106">[out] Un puntatore alla dimensione, espressa in byte, dell'heap delle stringhe utente.</span><span class="sxs-lookup"><span data-stu-id="1d999-106">[out] A pointer to the size, in bytes, of the user string heap.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1d999-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1d999-107">Requirements</span></span>  
 <span data-ttu-id="1d999-108">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1d999-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1d999-109">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="1d999-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1d999-110">**Libreria:** Usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="1d999-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="1d999-111">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1d999-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d999-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1d999-112">See also</span></span>
- [<span data-ttu-id="1d999-113">Interfaccia IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="1d999-113">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="1d999-114">Interfaccia IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="1d999-114">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)

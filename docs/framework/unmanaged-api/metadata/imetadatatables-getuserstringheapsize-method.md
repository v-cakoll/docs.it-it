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
ms.openlocfilehash: a217a835e258052ace5b59a70cbc0fa31691d78e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33452846"
---
# <a name="imetadatatablesgetuserstringheapsize-method"></a><span data-ttu-id="ca958-102">Metodo IMetaDataTables::GetUserStringHeapSize</span><span class="sxs-lookup"><span data-stu-id="ca958-102">IMetaDataTables::GetUserStringHeapSize Method</span></span>
<span data-ttu-id="ca958-103">Ottiene le dimensioni, in byte, dell'heap delle stringhe utente.</span><span class="sxs-lookup"><span data-stu-id="ca958-103">Gets the size, in bytes, of the user string heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca958-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ca958-104">Syntax</span></span>  
  
```  
HRESULT GetUserStringHeapSize (  
    [out] ULONG   *pcbBlobs  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ca958-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ca958-105">Parameters</span></span>  
 `pcbBlobs`  
 <span data-ttu-id="ca958-106">[out] Puntatore alla dimensione, in byte, dell'heap delle stringhe utente.</span><span class="sxs-lookup"><span data-stu-id="ca958-106">[out] A pointer to the size, in bytes, of the user string heap.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ca958-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ca958-107">Requirements</span></span>  
 <span data-ttu-id="ca958-108">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ca958-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ca958-109">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="ca958-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ca958-110">**Libreria:** usata come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="ca958-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ca958-111">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ca958-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca958-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ca958-112">See Also</span></span>  
 [<span data-ttu-id="ca958-113">Interfaccia IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="ca958-113">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)  
 [<span data-ttu-id="ca958-114">Interfaccia IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="ca958-114">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)

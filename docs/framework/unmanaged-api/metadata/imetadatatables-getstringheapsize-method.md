---
title: Metodo IMetaDataTables::GetStringHeapSize
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetStringHeapSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetStringHeapSize
helpviewer_keywords:
- IMetaDataTables::GetStringHeapSize method [.NET Framework metadata]
- GetStringHeapSize method [.NET Framework metadata]
ms.assetid: ed8f6335-81f5-4c09-81a9-2a909fc530c9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b842fb4d0853f473ae8e237a42e800cf0af8dc11
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781379"
---
# <a name="imetadatatablesgetstringheapsize-method"></a><span data-ttu-id="4afaf-102">Metodo IMetaDataTables::GetStringHeapSize</span><span class="sxs-lookup"><span data-stu-id="4afaf-102">IMetaDataTables::GetStringHeapSize Method</span></span>
<span data-ttu-id="4afaf-103">Ottiene la dimensione, espressa in byte, dell'heap delle stringhe.</span><span class="sxs-lookup"><span data-stu-id="4afaf-103">Gets the size, in bytes, of the string heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4afaf-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4afaf-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStringHeapSize (  
    [out] ULONG   *pcbStrings  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4afaf-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="4afaf-105">Parameters</span></span>  
 `pcbStrings`  
 <span data-ttu-id="4afaf-106">[out] Un puntatore alla dimensione, espressa in byte, dell'heap delle stringhe.</span><span class="sxs-lookup"><span data-stu-id="4afaf-106">[out] A pointer to the size, in bytes, of the string heap.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4afaf-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4afaf-107">Requirements</span></span>  
 <span data-ttu-id="4afaf-108">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4afaf-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4afaf-109">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="4afaf-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4afaf-110">**Libreria:** Usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="4afaf-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="4afaf-111">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4afaf-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4afaf-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4afaf-112">See also</span></span>

- [<span data-ttu-id="4afaf-113">Interfaccia IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="4afaf-113">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="4afaf-114">Interfaccia IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="4afaf-114">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)

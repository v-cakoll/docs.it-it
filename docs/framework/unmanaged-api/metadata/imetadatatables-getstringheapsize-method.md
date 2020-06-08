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
ms.openlocfilehash: 1aa7853602c1aaf484ef89d9c4fb06464e135f80
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501167"
---
# <a name="imetadatatablesgetstringheapsize-method"></a><span data-ttu-id="d68e6-102">Metodo IMetaDataTables::GetStringHeapSize</span><span class="sxs-lookup"><span data-stu-id="d68e6-102">IMetaDataTables::GetStringHeapSize Method</span></span>
<span data-ttu-id="d68e6-103">Ottiene la dimensione, in byte, dell'heap delle stringhe.</span><span class="sxs-lookup"><span data-stu-id="d68e6-103">Gets the size, in bytes, of the string heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d68e6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d68e6-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStringHeapSize (  
    [out] ULONG   *pcbStrings  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d68e6-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d68e6-105">Parameters</span></span>  
 `pcbStrings`  
 <span data-ttu-id="d68e6-106">out Puntatore alla dimensione, in byte, dell'heap delle stringhe.</span><span class="sxs-lookup"><span data-stu-id="d68e6-106">[out] A pointer to the size, in bytes, of the string heap.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d68e6-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d68e6-107">Requirements</span></span>  
 <span data-ttu-id="d68e6-108">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d68e6-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d68e6-109">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="d68e6-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d68e6-110">**Libreria:** Usato come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="d68e6-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d68e6-111">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d68e6-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d68e6-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d68e6-112">See also</span></span>

- [<span data-ttu-id="d68e6-113">Interfaccia IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="d68e6-113">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
- [<span data-ttu-id="d68e6-114">Interfaccia IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="d68e6-114">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)

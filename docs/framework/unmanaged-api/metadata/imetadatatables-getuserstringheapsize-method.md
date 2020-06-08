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
ms.openlocfilehash: 1aea017f17e29544e9288e1f57e6f84f9a2f6dae
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501105"
---
# <a name="imetadatatablesgetuserstringheapsize-method"></a><span data-ttu-id="696be-102">Metodo IMetaDataTables::GetUserStringHeapSize</span><span class="sxs-lookup"><span data-stu-id="696be-102">IMetaDataTables::GetUserStringHeapSize Method</span></span>
<span data-ttu-id="696be-103">Ottiene la dimensione, in byte, dell'heap delle stringhe utente.</span><span class="sxs-lookup"><span data-stu-id="696be-103">Gets the size, in bytes, of the user string heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="696be-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="696be-104">Syntax</span></span>  
  
```cpp  
HRESULT GetUserStringHeapSize (  
    [out] ULONG   *pcbBlobs  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="696be-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="696be-105">Parameters</span></span>  
 `pcbBlobs`  
 <span data-ttu-id="696be-106">out Puntatore alla dimensione, in byte, dell'heap delle stringhe utente.</span><span class="sxs-lookup"><span data-stu-id="696be-106">[out] A pointer to the size, in bytes, of the user string heap.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="696be-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="696be-107">Requirements</span></span>  
 <span data-ttu-id="696be-108">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="696be-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="696be-109">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="696be-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="696be-110">**Libreria:** Usato come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="696be-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="696be-111">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="696be-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="696be-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="696be-112">See also</span></span>

- [<span data-ttu-id="696be-113">Interfaccia IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="696be-113">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
- [<span data-ttu-id="696be-114">Interfaccia IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="696be-114">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)

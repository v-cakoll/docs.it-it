---
title: Metodo IMetaDataTables::GetNextString
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IMetaDataTables.GetNextString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetNextString
helpviewer_keywords:
- IMetaDataTables::GetNextString method [.NET Framework metadata]
- GetNextString method [.NET Framework metadata]
ms.assetid: d9720428-c353-4f07-a7e8-899e106a1b37
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e2bf16f6debd50729a95a4e887a01c1158b7a937
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="imetadatatablesgetnextstring-method"></a><span data-ttu-id="95705-102">Metodo IMetaDataTables::GetNextString</span><span class="sxs-lookup"><span data-stu-id="95705-102">IMetaDataTables::GetNextString Method</span></span>
<span data-ttu-id="95705-103">Ottiene l'indice della stringa successiva nella colonna della tabella corrente.</span><span class="sxs-lookup"><span data-stu-id="95705-103">Gets the index of the next string in the current table column.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95705-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="95705-104">Syntax</span></span>  
  
```  
HRESULT GetNextString (   
    [in]  ULONG   ixString,  
    [out] ULONG   *pNext  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="95705-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="95705-105">Parameters</span></span>  
 `ixString`  
 <span data-ttu-id="95705-106">[in] Il valore di indice da una colonna di tabella della stringa.</span><span class="sxs-lookup"><span data-stu-id="95705-106">[in] The index value from a string table column.</span></span>  
  
 `pNext`  
 <span data-ttu-id="95705-107">[out] Un puntatore all'indice della stringa nella colonna successiva.</span><span class="sxs-lookup"><span data-stu-id="95705-107">[out] A pointer to the index of the next string in the column.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="95705-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="95705-108">Requirements</span></span>  
 <span data-ttu-id="95705-109">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="95705-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="95705-110">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="95705-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="95705-111">**Libreria:** usata come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="95705-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="95705-112">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="95705-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95705-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="95705-113">See Also</span></span>  
 [<span data-ttu-id="95705-114">Interfaccia IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="95705-114">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)  
 [<span data-ttu-id="95705-115">Interfaccia IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="95705-115">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)

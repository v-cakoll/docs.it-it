---
title: Metodo IMapToken::Map
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
- IMapToken.Map
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMapToken::Map
helpviewer_keywords:
- IMapToken::Map method [.NET Framework metadata]
- Map method [.NET Framework metadata]
ms.assetid: b9b4bf2f-1098-43d6-9619-a99b4bda1940
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: fe034d2bc6d70e820fa3ad5de8140afa9a19a6bf
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="imaptokenmap-method"></a><span data-ttu-id="a892e-102">Metodo IMapToken::Map</span><span class="sxs-lookup"><span data-stu-id="a892e-102">IMapToken::Map Method</span></span>
<span data-ttu-id="a892e-103">Esegue il mapping di una relazione tra gli assembly che utilizzano le firme di metadati.</span><span class="sxs-lookup"><span data-stu-id="a892e-103">Maps a relationship between the assemblies using metadata signatures.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a892e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a892e-104">Syntax</span></span>  
  
```  
HRESULT Map (  
    [in]  mdToken tkImp,   
    [in]  mdToken tkEmit  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a892e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a892e-105">Parameters</span></span>  
 `tkImp`  
 <span data-ttu-id="a892e-106">[in] Il token di metadati che rappresenta l'oggetto codice importato.</span><span class="sxs-lookup"><span data-stu-id="a892e-106">[in] The metadata token that represents the imported code object.</span></span>  
  
 `tkEmit`  
 <span data-ttu-id="a892e-107">[in] Il token di metadati che rappresenta l'oggetto di codice generato.</span><span class="sxs-lookup"><span data-stu-id="a892e-107">[in] The metadata token that represents the emitted code object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a892e-108">Note</span><span class="sxs-lookup"><span data-stu-id="a892e-108">Remarks</span></span>  
 <span data-ttu-id="a892e-109">Quando il nuovo mapping dei token si verifica durante un'operazione di unione, il token originale è un ambito nell'ambito dei metadati importati (origine) e il nuovo token di ambito è nell'ambito dei metadati generato (destinazione).</span><span class="sxs-lookup"><span data-stu-id="a892e-109">When the token re-map occurs during a merge, the original token is scoped in the imported (source) metadata scope and the new token is scoped in the emitted (target) metadata scope.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a892e-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a892e-110">Requirements</span></span>  
 <span data-ttu-id="a892e-111">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a892e-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a892e-112">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="a892e-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a892e-113">**Libreria:** usata come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a892e-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a892e-114">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a892e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a892e-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a892e-115">See Also</span></span>  
 [<span data-ttu-id="a892e-116">Interfaccia IMapToken</span><span class="sxs-lookup"><span data-stu-id="a892e-116">IMapToken Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md)

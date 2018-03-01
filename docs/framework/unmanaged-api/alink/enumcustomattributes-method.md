---
title: Metodo EnumCustomAttributes
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
- EnumCustomAttributes
- IALink.EnumCustomAttributes
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EnumCustomAttributes
helpviewer_keywords:
- EnumCustomAttributes method
ms.assetid: 08dff60c-f01b-4050-8865-ea3f95361c9f
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d616babb47ac0282ef56d119ab448a94fd24c7c5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="enumcustomattributes-method"></a><span data-ttu-id="8c8d4-102">Metodo EnumCustomAttributes</span><span class="sxs-lookup"><span data-stu-id="8c8d4-102">EnumCustomAttributes Method</span></span>
<span data-ttu-id="8c8d4-103">Recupera gli attributi personalizzati a livello di assembly.</span><span class="sxs-lookup"><span data-stu-id="8c8d4-103">Retrieves assembly-level custom attributes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c8d4-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8c8d4-104">Syntax</span></span>  
  
```  
HRESULT EnumCustomAttributes(  
    HALINKENUM hEnum,  
    mdToken tkType,  
    mdCustomAttribute rCustomValues[],  
    ULONG cMax,  
    ULONG* pcCustomValues  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8c8d4-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="8c8d4-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="8c8d4-106">Handle dell'enumeratore.</span><span class="sxs-lookup"><span data-stu-id="8c8d4-106">Handle of enumerator.</span></span>  
  
 `tkType`  
 <span data-ttu-id="8c8d4-107">Tipo degli attributi da enumerare.</span><span class="sxs-lookup"><span data-stu-id="8c8d4-107">Type of attributes to be enumerated.</span></span> <span data-ttu-id="8c8d4-108">Utilizzare `mdTokenNill` per tutti gli attributi.</span><span class="sxs-lookup"><span data-stu-id="8c8d4-108">Use `mdTokenNill` for all attributes.</span></span>  
  
 `rCustomValues`  
 <span data-ttu-id="8c8d4-109">Riceve i token di attributi personalizzati.</span><span class="sxs-lookup"><span data-stu-id="8c8d4-109">Receives custom attributes tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="8c8d4-110">Specifica le dimensioni di `rCustomValues` matrice.</span><span class="sxs-lookup"><span data-stu-id="8c8d4-110">Specifies size of `rCustomValues` array.</span></span>  
  
 `pcCustomValues`  
 <span data-ttu-id="8c8d4-111">Facoltativamente riceve il numero di valori token.</span><span class="sxs-lookup"><span data-stu-id="8c8d4-111">Optionally receives count of token values.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8c8d4-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="8c8d4-112">Return Value</span></span>  
 <span data-ttu-id="8c8d4-113">Se il metodo ha esito positivo, restituisce S_OK.</span><span class="sxs-lookup"><span data-stu-id="8c8d4-113">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8c8d4-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8c8d4-114">Requirements</span></span>  
 <span data-ttu-id="8c8d4-115">Richiede alink.h</span><span class="sxs-lookup"><span data-stu-id="8c8d4-115">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c8d4-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8c8d4-116">See Also</span></span>  
 [<span data-ttu-id="8c8d4-117">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="8c8d4-117">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="8c8d4-118">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="8c8d4-118">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="8c8d4-119">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="8c8d4-119">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)

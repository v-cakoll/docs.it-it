---
title: Metodo EnumCustomAttributes
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- EnumCustomAttributes
- IALink.EnumCustomAttributes
api_location: alink.dll
api_type: COM
f1_keywords: EnumCustomAttributes
helpviewer_keywords: EnumCustomAttributes method
ms.assetid: 08dff60c-f01b-4050-8865-ea3f95361c9f
topic_type: apiref
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: febaba5155753e9d60a3708582f4f58bd7861ec7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="enumcustomattributes-method"></a><span data-ttu-id="94b7c-102">Metodo EnumCustomAttributes</span><span class="sxs-lookup"><span data-stu-id="94b7c-102">EnumCustomAttributes Method</span></span>
<span data-ttu-id="94b7c-103">Recupera gli attributi personalizzati a livello di assembly.</span><span class="sxs-lookup"><span data-stu-id="94b7c-103">Retrieves assembly-level custom attributes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="94b7c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="94b7c-104">Syntax</span></span>  
  
```  
HRESULT EnumCustomAttributes(  
    HALINKENUM hEnum,  
    mdToken tkType,  
    mdCustomAttribute rCustomValues[],  
    ULONG cMax,  
    ULONG* pcCustomValues  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="94b7c-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="94b7c-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="94b7c-106">Handle dell'enumeratore.</span><span class="sxs-lookup"><span data-stu-id="94b7c-106">Handle of enumerator.</span></span>  
  
 `tkType`  
 <span data-ttu-id="94b7c-107">Tipo degli attributi da enumerare.</span><span class="sxs-lookup"><span data-stu-id="94b7c-107">Type of attributes to be enumerated.</span></span> <span data-ttu-id="94b7c-108">Utilizzare `mdTokenNill` per tutti gli attributi.</span><span class="sxs-lookup"><span data-stu-id="94b7c-108">Use `mdTokenNill` for all attributes.</span></span>  
  
 `rCustomValues`  
 <span data-ttu-id="94b7c-109">Riceve i token di attributi personalizzati.</span><span class="sxs-lookup"><span data-stu-id="94b7c-109">Receives custom attributes tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="94b7c-110">Specifica le dimensioni di `rCustomValues` matrice.</span><span class="sxs-lookup"><span data-stu-id="94b7c-110">Specifies size of `rCustomValues` array.</span></span>  
  
 `pcCustomValues`  
 <span data-ttu-id="94b7c-111">Facoltativamente riceve il numero di valori token.</span><span class="sxs-lookup"><span data-stu-id="94b7c-111">Optionally receives count of token values.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="94b7c-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="94b7c-112">Return Value</span></span>  
 <span data-ttu-id="94b7c-113">Se il metodo ha esito positivo, restituisce S_OK.</span><span class="sxs-lookup"><span data-stu-id="94b7c-113">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="94b7c-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="94b7c-114">Requirements</span></span>  
 <span data-ttu-id="94b7c-115">Richiede alink.h</span><span class="sxs-lookup"><span data-stu-id="94b7c-115">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94b7c-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="94b7c-116">See Also</span></span>  
 [<span data-ttu-id="94b7c-117">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="94b7c-117">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="94b7c-118">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="94b7c-118">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="94b7c-119">ALink (API)</span><span class="sxs-lookup"><span data-stu-id="94b7c-119">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)

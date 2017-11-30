---
title: Metodo CloseEnum
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- CloseEnum
- IALink.CloseEnum
api_location: alink.dll
api_type: COM
f1_keywords: CloseEnum
helpviewer_keywords: CloseEnum method
ms.assetid: aa4a091e-13fe-4264-91de-e12f1c767c87
topic_type: apiref
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 6ade939969069fb35221d83f8c7e4e380e903a00
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="closeenum-method"></a><span data-ttu-id="b9667-102">Metodo CloseEnum</span><span class="sxs-lookup"><span data-stu-id="b9667-102">CloseEnum Method</span></span>
<span data-ttu-id="b9667-103">Chiude l'enumerazione indicata e libera le risorse associate.</span><span class="sxs-lookup"><span data-stu-id="b9667-103">Closes the indicated enumeration and frees associated resources.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9667-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b9667-104">Syntax</span></span>  
  
```  
HRESULT CloseEnum(  
    HALINKENUM hEnum  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b9667-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="b9667-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="b9667-106">Handle di enumerazione per essere chiuso.</span><span class="sxs-lookup"><span data-stu-id="b9667-106">Handle of enumeration to be closed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b9667-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="b9667-107">Return Value</span></span>  
 <span data-ttu-id="b9667-108">Se il metodo ha esito positivo, restituisce S_OK.</span><span class="sxs-lookup"><span data-stu-id="b9667-108">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b9667-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b9667-109">Requirements</span></span>  
 <span data-ttu-id="b9667-110">Richiede alink.h</span><span class="sxs-lookup"><span data-stu-id="b9667-110">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9667-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b9667-111">See Also</span></span>  
 [<span data-ttu-id="b9667-112">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="b9667-112">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="b9667-113">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="b9667-113">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="b9667-114">ALink (API)</span><span class="sxs-lookup"><span data-stu-id="b9667-114">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)

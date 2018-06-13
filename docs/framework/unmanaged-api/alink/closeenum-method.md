---
title: Metodo CloseEnum
ms.date: 03/30/2017
api_name:
- CloseEnum
- IALink.CloseEnum
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- CloseEnum
helpviewer_keywords:
- CloseEnum method
ms.assetid: aa4a091e-13fe-4264-91de-e12f1c767c87
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e5c3185dc6d488223d5882f543f0c690d82261b5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33402444"
---
# <a name="closeenum-method"></a><span data-ttu-id="986ef-102">Metodo CloseEnum</span><span class="sxs-lookup"><span data-stu-id="986ef-102">CloseEnum Method</span></span>
<span data-ttu-id="986ef-103">Chiude l'enumerazione indicata e libera le risorse associate.</span><span class="sxs-lookup"><span data-stu-id="986ef-103">Closes the indicated enumeration and frees associated resources.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="986ef-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="986ef-104">Syntax</span></span>  
  
```  
HRESULT CloseEnum(  
    HALINKENUM hEnum  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="986ef-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="986ef-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="986ef-106">Handle di enumerazione per essere chiuso.</span><span class="sxs-lookup"><span data-stu-id="986ef-106">Handle of enumeration to be closed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="986ef-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="986ef-107">Return Value</span></span>  
 <span data-ttu-id="986ef-108">Se il metodo ha esito positivo, restituisce S_OK.</span><span class="sxs-lookup"><span data-stu-id="986ef-108">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="986ef-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="986ef-109">Requirements</span></span>  
 <span data-ttu-id="986ef-110">Richiede alink.h</span><span class="sxs-lookup"><span data-stu-id="986ef-110">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="986ef-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="986ef-111">See Also</span></span>  
 [<span data-ttu-id="986ef-112">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="986ef-112">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="986ef-113">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="986ef-113">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="986ef-114">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="986ef-114">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)

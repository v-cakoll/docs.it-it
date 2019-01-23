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
ms.openlocfilehash: 009f7d20dfd6efc279b3187af8f5c95132ae51e7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54525235"
---
# <a name="closeenum-method"></a><span data-ttu-id="a04e0-102">Metodo CloseEnum</span><span class="sxs-lookup"><span data-stu-id="a04e0-102">CloseEnum Method</span></span>
<span data-ttu-id="a04e0-103">Chiude l'enumerazione indicata e libera le risorse associate.</span><span class="sxs-lookup"><span data-stu-id="a04e0-103">Closes the indicated enumeration and frees associated resources.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a04e0-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a04e0-104">Syntax</span></span>  
  
```  
HRESULT CloseEnum(  
    HALINKENUM hEnum  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a04e0-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a04e0-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="a04e0-106">Handle di enumerazione per essere chiuso.</span><span class="sxs-lookup"><span data-stu-id="a04e0-106">Handle of enumeration to be closed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a04e0-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="a04e0-107">Return Value</span></span>  
 <span data-ttu-id="a04e0-108">Restituisce S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="a04e0-108">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a04e0-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a04e0-109">Requirements</span></span>  
 <span data-ttu-id="a04e0-110">Richiede alink.h</span><span class="sxs-lookup"><span data-stu-id="a04e0-110">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a04e0-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a04e0-111">See also</span></span>
- [<span data-ttu-id="a04e0-112">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="a04e0-112">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="a04e0-113">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="a04e0-113">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="a04e0-114">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="a04e0-114">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)

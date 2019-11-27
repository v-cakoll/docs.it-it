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
ms.openlocfilehash: 018af6929ad4023c70bfb975b9be010912415dd7
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446570"
---
# <a name="closeenum-method"></a><span data-ttu-id="6de8f-102">Metodo CloseEnum</span><span class="sxs-lookup"><span data-stu-id="6de8f-102">CloseEnum Method</span></span>
<span data-ttu-id="6de8f-103">Chiude l'enumerazione indicata e libera le risorse associate.</span><span class="sxs-lookup"><span data-stu-id="6de8f-103">Closes the indicated enumeration and frees associated resources.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6de8f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6de8f-104">Syntax</span></span>  
  
```cpp  
HRESULT CloseEnum(  
    HALINKENUM hEnum  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="6de8f-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="6de8f-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="6de8f-106">Handle di enumerazione da chiudere.</span><span class="sxs-lookup"><span data-stu-id="6de8f-106">Handle of enumeration to be closed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6de8f-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="6de8f-107">Return Value</span></span>  
 <span data-ttu-id="6de8f-108">Restituisce S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="6de8f-108">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6de8f-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6de8f-109">Requirements</span></span>  
 <span data-ttu-id="6de8f-110">Richiede ALink. h</span><span class="sxs-lookup"><span data-stu-id="6de8f-110">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6de8f-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6de8f-111">See also</span></span>

- [<span data-ttu-id="6de8f-112">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="6de8f-112">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="6de8f-113">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="6de8f-113">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="6de8f-114">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="6de8f-114">ALink API</span></span>](index.md)

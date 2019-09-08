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
ms.openlocfilehash: 8d9529022eb04c81152dced5c63f255c510851a0
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70777469"
---
# <a name="closeenum-method"></a><span data-ttu-id="370ad-102">Metodo CloseEnum</span><span class="sxs-lookup"><span data-stu-id="370ad-102">CloseEnum Method</span></span>
<span data-ttu-id="370ad-103">Chiude l'enumerazione indicata e libera le risorse associate.</span><span class="sxs-lookup"><span data-stu-id="370ad-103">Closes the indicated enumeration and frees associated resources.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="370ad-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="370ad-104">Syntax</span></span>  
  
```cpp  
HRESULT CloseEnum(  
    HALINKENUM hEnum  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="370ad-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="370ad-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="370ad-106">Handle di enumerazione da chiudere.</span><span class="sxs-lookup"><span data-stu-id="370ad-106">Handle of enumeration to be closed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="370ad-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="370ad-107">Return Value</span></span>  
 <span data-ttu-id="370ad-108">Restituisce S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="370ad-108">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="370ad-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="370ad-109">Requirements</span></span>  
 <span data-ttu-id="370ad-110">Richiede ALink. h</span><span class="sxs-lookup"><span data-stu-id="370ad-110">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="370ad-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="370ad-111">See also</span></span>

- [<span data-ttu-id="370ad-112">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="370ad-112">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="370ad-113">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="370ad-113">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="370ad-114">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="370ad-114">ALink API</span></span>](index.md)

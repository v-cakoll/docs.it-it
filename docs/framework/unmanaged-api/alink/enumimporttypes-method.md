---
title: Metodo EnumImportTypes
ms.date: 03/30/2017
api_name:
- EnumImportTypes
- IALink.EnumImportTypes
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EnumImportTypes
helpviewer_keywords:
- EnumImportTypes method
ms.assetid: 83a0e4e7-ec06-40cb-9b63-700b9695bb04
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4e437868138d7ae31d233853ecc0f709de3ee39d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54512723"
---
# <a name="enumimporttypes-method"></a><span data-ttu-id="01134-102">Metodo EnumImportTypes</span><span class="sxs-lookup"><span data-stu-id="01134-102">EnumImportTypes Method</span></span>
<span data-ttu-id="01134-103">Enumera ogni tipo in ogni ambito.</span><span class="sxs-lookup"><span data-stu-id="01134-103">Enumerates each type in each scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="01134-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="01134-104">Syntax</span></span>  
  
```  
HRESULT EnumImportTypes(  
    HALINKENUM   hEnum,  
    DWORD        dwMax,  
    mdTypeDef    aTypeDefs[],  
    DWORD*       pdwCount  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="01134-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="01134-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="01134-106">Handle per l'enumeratore.</span><span class="sxs-lookup"><span data-stu-id="01134-106">Handle for enumerator.</span></span>  
  
 `dwMax`  
 <span data-ttu-id="01134-107">Numero massimo di tipi da recuperare.</span><span class="sxs-lookup"><span data-stu-id="01134-107">Maximum number of types to retrieve.</span></span>  
  
 `aTypeDefs`  
 <span data-ttu-id="01134-108">Riceve i token, non deve superare di tipo `dwMax`.</span><span class="sxs-lookup"><span data-stu-id="01134-108">Recieves type tokens, not to exceed `dwMax`.</span></span>  
  
 `pdwCount`  
 <span data-ttu-id="01134-109">Riceve il numero effettivo di tipo in `aTypeDefs`.</span><span class="sxs-lookup"><span data-stu-id="01134-109">Receives actual number of type in `aTypeDefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="01134-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="01134-110">Return Value</span></span>  
 <span data-ttu-id="01134-111">Restituisce S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="01134-111">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="01134-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="01134-112">Requirements</span></span>  
 <span data-ttu-id="01134-113">Richiede alink.h</span><span class="sxs-lookup"><span data-stu-id="01134-113">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01134-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="01134-114">See also</span></span>
- [<span data-ttu-id="01134-115">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="01134-115">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="01134-116">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="01134-116">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="01134-117">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="01134-117">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)

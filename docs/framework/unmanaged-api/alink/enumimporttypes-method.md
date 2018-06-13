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
ms.openlocfilehash: 90319886dfe149a3d2d76451c1a8526299cf5b89
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33401648"
---
# <a name="enumimporttypes-method"></a><span data-ttu-id="56f79-102">Metodo EnumImportTypes</span><span class="sxs-lookup"><span data-stu-id="56f79-102">EnumImportTypes Method</span></span>
<span data-ttu-id="56f79-103">Enumera ogni tipo di ogni ambito.</span><span class="sxs-lookup"><span data-stu-id="56f79-103">Enumerates each type in each scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="56f79-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="56f79-104">Syntax</span></span>  
  
```  
HRESULT EnumImportTypes(  
    HALINKENUM   hEnum,  
    DWORD        dwMax,  
    mdTypeDef    aTypeDefs[],  
    DWORD*       pdwCount  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="56f79-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="56f79-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="56f79-106">Handle per l'enumeratore.</span><span class="sxs-lookup"><span data-stu-id="56f79-106">Handle for enumerator.</span></span>  
  
 `dwMax`  
 <span data-ttu-id="56f79-107">Numero massimo di tipi da recuperare.</span><span class="sxs-lookup"><span data-stu-id="56f79-107">Maximum number of types to retrieve.</span></span>  
  
 `aTypeDefs`  
 <span data-ttu-id="56f79-108">Riceve token di tipo, non deve superare `dwMax`.</span><span class="sxs-lookup"><span data-stu-id="56f79-108">Recieves type tokens, not to exceed `dwMax`.</span></span>  
  
 `pdwCount`  
 <span data-ttu-id="56f79-109">Riceve il numero effettivo di tipo in `aTypeDefs`.</span><span class="sxs-lookup"><span data-stu-id="56f79-109">Receives actual number of type in `aTypeDefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="56f79-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="56f79-110">Return Value</span></span>  
 <span data-ttu-id="56f79-111">Se il metodo ha esito positivo, restituisce S_OK.</span><span class="sxs-lookup"><span data-stu-id="56f79-111">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="56f79-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="56f79-112">Requirements</span></span>  
 <span data-ttu-id="56f79-113">Richiede alink.h</span><span class="sxs-lookup"><span data-stu-id="56f79-113">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56f79-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="56f79-114">See Also</span></span>  
 [<span data-ttu-id="56f79-115">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="56f79-115">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="56f79-116">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="56f79-116">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="56f79-117">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="56f79-117">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)

---
title: Metodo EmitInternalExportedTypes
ms.date: 03/30/2017
api_name:
- EmitInternalExportedTypes
- IALink2.EmitInternalExportedTypes
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EmitInternalExportedTypes
helpviewer_keywords:
- EmitInternalExportedTypes method
ms.assetid: 28c8b00d-2c14-40b4-aed5-a1db0e2428eb
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 15174480c4345f2514572701a5525f0f192ad120
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67742097"
---
# <a name="emitinternalexportedtypes-method"></a><span data-ttu-id="217c5-102">Metodo EmitInternalExportedTypes</span><span class="sxs-lookup"><span data-stu-id="217c5-102">EmitInternalExportedTypes Method</span></span>
<span data-ttu-id="217c5-103">Genera tipi aggiunti all'assembly.</span><span class="sxs-lookup"><span data-stu-id="217c5-103">Emits types added to the assembly.</span></span> <span data-ttu-id="217c5-104">Chiamare questo metodo una volta noto sono stati aggiunti i tipi interni.</span><span class="sxs-lookup"><span data-stu-id="217c5-104">Call this method after known internal types have been added.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="217c5-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="217c5-105">Syntax</span></span>  
  
```cpp  
HRESULT EmitInternalExportedTypes(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="217c5-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="217c5-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="217c5-107">ID dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="217c5-107">ID of assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="217c5-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="217c5-108">Return Value</span></span>  
 <span data-ttu-id="217c5-109">Restituisce S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="217c5-109">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="217c5-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="217c5-110">Requirements</span></span>  
 <span data-ttu-id="217c5-111">Richiede alink.h</span><span class="sxs-lookup"><span data-stu-id="217c5-111">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="217c5-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="217c5-112">See also</span></span>

- [<span data-ttu-id="217c5-113">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="217c5-113">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="217c5-114">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="217c5-114">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="217c5-115">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="217c5-115">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)

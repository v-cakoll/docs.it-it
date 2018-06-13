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
ms.openlocfilehash: 55b9d185804f25c7431f2696d67753cc3ba02d1f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33402041"
---
# <a name="emitinternalexportedtypes-method"></a><span data-ttu-id="26248-102">Metodo EmitInternalExportedTypes</span><span class="sxs-lookup"><span data-stu-id="26248-102">EmitInternalExportedTypes Method</span></span>
<span data-ttu-id="26248-103">Genera tipi aggiunti all'assembly.</span><span class="sxs-lookup"><span data-stu-id="26248-103">Emits types added to the assembly.</span></span> <span data-ttu-id="26248-104">Chiamare questo metodo una volta noto tipi interni sono stati aggiunti.</span><span class="sxs-lookup"><span data-stu-id="26248-104">Call this method after known internal types have been added.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="26248-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="26248-105">Syntax</span></span>  
  
```  
HRESULT EmitInternalExportedTypes(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="26248-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="26248-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="26248-107">ID dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="26248-107">ID of assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="26248-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="26248-108">Return Value</span></span>  
 <span data-ttu-id="26248-109">Se il metodo ha esito positivo, restituisce S_OK.</span><span class="sxs-lookup"><span data-stu-id="26248-109">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="26248-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="26248-110">Requirements</span></span>  
 <span data-ttu-id="26248-111">Richiede alink.h</span><span class="sxs-lookup"><span data-stu-id="26248-111">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26248-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="26248-112">See Also</span></span>  
 [<span data-ttu-id="26248-113">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="26248-113">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="26248-114">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="26248-114">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="26248-115">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="26248-115">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)

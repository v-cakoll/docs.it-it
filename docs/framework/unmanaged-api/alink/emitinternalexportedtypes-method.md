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
ms.openlocfilehash: 68373e9277a9d87bba6941259588f25a92af90a3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54710547"
---
# <a name="emitinternalexportedtypes-method"></a><span data-ttu-id="fbdca-102">Metodo EmitInternalExportedTypes</span><span class="sxs-lookup"><span data-stu-id="fbdca-102">EmitInternalExportedTypes Method</span></span>
<span data-ttu-id="fbdca-103">Genera tipi aggiunti all'assembly.</span><span class="sxs-lookup"><span data-stu-id="fbdca-103">Emits types added to the assembly.</span></span> <span data-ttu-id="fbdca-104">Chiamare questo metodo una volta noto sono stati aggiunti i tipi interni.</span><span class="sxs-lookup"><span data-stu-id="fbdca-104">Call this method after known internal types have been added.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fbdca-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fbdca-105">Syntax</span></span>  
  
```  
HRESULT EmitInternalExportedTypes(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fbdca-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="fbdca-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="fbdca-107">ID dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="fbdca-107">ID of assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fbdca-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="fbdca-108">Return Value</span></span>  
 <span data-ttu-id="fbdca-109">Restituisce S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="fbdca-109">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fbdca-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="fbdca-110">Requirements</span></span>  
 <span data-ttu-id="fbdca-111">Richiede alink.h</span><span class="sxs-lookup"><span data-stu-id="fbdca-111">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fbdca-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fbdca-112">See also</span></span>
- [<span data-ttu-id="fbdca-113">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="fbdca-113">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="fbdca-114">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="fbdca-114">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="fbdca-115">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="fbdca-115">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)

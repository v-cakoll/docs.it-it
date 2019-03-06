---
title: Metodo EmitAssembly
ms.date: 03/30/2017
api_name:
- IALink2.EmitAssembly
- EmitAssembly
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EmitAssembly
helpviewer_keywords:
- EmitAssembly method
ms.assetid: 605ff39e-e5cc-4bff-8196-e8d68a9715b9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b1cdcfcaf29cc2b0ec6da1108e0ecd91710db36c
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57487306"
---
# <a name="emitassembly-method"></a><span data-ttu-id="52a4a-102">Metodo EmitAssembly</span><span class="sxs-lookup"><span data-stu-id="52a4a-102">EmitAssembly Method</span></span>
<span data-ttu-id="52a4a-103">Crea l'assembly.</span><span class="sxs-lookup"><span data-stu-id="52a4a-103">Creates the assembly.</span></span> <span data-ttu-id="52a4a-104">Chiamare questo metodo dopo la chiusura di tutti gli altri file tranne il file di assembly.</span><span class="sxs-lookup"><span data-stu-id="52a4a-104">Call this method after all other files are closed except for the assembly file.</span></span> <span data-ttu-id="52a4a-105">Non chiamare questo metodo quando si generano i moduli non associati.</span><span class="sxs-lookup"><span data-stu-id="52a4a-105">Do not call this method when producing unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52a4a-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="52a4a-106">Syntax</span></span>  
  
```  
HRESULT EmitAssembly(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="52a4a-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="52a4a-107">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="52a4a-108">ID dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="52a4a-108">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="52a4a-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="52a4a-109">Return Value</span></span>  
 <span data-ttu-id="52a4a-110">Restituisce S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="52a4a-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="52a4a-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="52a4a-111">Requirements</span></span>  
 <span data-ttu-id="52a4a-112">Richiede alink.h</span><span class="sxs-lookup"><span data-stu-id="52a4a-112">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52a4a-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="52a4a-113">See also</span></span>
- [<span data-ttu-id="52a4a-114">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="52a4a-114">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="52a4a-115">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="52a4a-115">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="52a4a-116">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="52a4a-116">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)

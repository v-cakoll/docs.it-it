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
ms.openlocfilehash: d73c158fa9d7b5574e4f875b8d51e932e30041b0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54572240"
---
# <a name="emitassembly-method"></a><span data-ttu-id="37ddb-102">Metodo EmitAssembly</span><span class="sxs-lookup"><span data-stu-id="37ddb-102">EmitAssembly Method</span></span>
<span data-ttu-id="37ddb-103">Crea l'assembly.</span><span class="sxs-lookup"><span data-stu-id="37ddb-103">Creates the assembly.</span></span> <span data-ttu-id="37ddb-104">Chiamare questo metodo dopo la chiusura di tutti gli altri file tranne il file di assembly.</span><span class="sxs-lookup"><span data-stu-id="37ddb-104">Call this method after all other files are closed except for the assembly file.</span></span> <span data-ttu-id="37ddb-105">Non chiamare questo metodo quando si generano i moduli non associati.</span><span class="sxs-lookup"><span data-stu-id="37ddb-105">Do not call this method when producing unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="37ddb-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="37ddb-106">Syntax</span></span>  
  
```  
HRESULT EmitAssembly(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="37ddb-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="37ddb-107">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="37ddb-108">ID dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="37ddb-108">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="37ddb-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="37ddb-109">Return Value</span></span>  
 <span data-ttu-id="37ddb-110">Restituisce S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="37ddb-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="37ddb-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="37ddb-111">Requirements</span></span>  
 <span data-ttu-id="37ddb-112">Richiede alink.h</span><span class="sxs-lookup"><span data-stu-id="37ddb-112">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37ddb-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="37ddb-113">See also</span></span>
- [<span data-ttu-id="37ddb-114">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="37ddb-114">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="37ddb-115">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="37ddb-115">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="37ddb-116">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="37ddb-116">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)

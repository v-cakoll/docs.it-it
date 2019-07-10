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
ms.openlocfilehash: b0e6250987997b8d1c833b7b33a985900510fb03
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67742143"
---
# <a name="emitassembly-method"></a><span data-ttu-id="5ecf5-102">Metodo EmitAssembly</span><span class="sxs-lookup"><span data-stu-id="5ecf5-102">EmitAssembly Method</span></span>
<span data-ttu-id="5ecf5-103">Crea l'assembly.</span><span class="sxs-lookup"><span data-stu-id="5ecf5-103">Creates the assembly.</span></span> <span data-ttu-id="5ecf5-104">Chiamare questo metodo dopo la chiusura di tutti gli altri file tranne il file di assembly.</span><span class="sxs-lookup"><span data-stu-id="5ecf5-104">Call this method after all other files are closed except for the assembly file.</span></span> <span data-ttu-id="5ecf5-105">Non chiamare questo metodo quando si generano i moduli non associati.</span><span class="sxs-lookup"><span data-stu-id="5ecf5-105">Do not call this method when producing unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ecf5-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5ecf5-106">Syntax</span></span>  
  
```cpp  
HRESULT EmitAssembly(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="5ecf5-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="5ecf5-107">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="5ecf5-108">ID dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="5ecf5-108">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5ecf5-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="5ecf5-109">Return Value</span></span>  
 <span data-ttu-id="5ecf5-110">Restituisce S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="5ecf5-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5ecf5-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5ecf5-111">Requirements</span></span>  
 <span data-ttu-id="5ecf5-112">Richiede alink.h</span><span class="sxs-lookup"><span data-stu-id="5ecf5-112">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ecf5-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5ecf5-113">See also</span></span>

- [<span data-ttu-id="5ecf5-114">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="5ecf5-114">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="5ecf5-115">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="5ecf5-115">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="5ecf5-116">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="5ecf5-116">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)

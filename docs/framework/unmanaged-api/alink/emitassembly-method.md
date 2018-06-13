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
ms.openlocfilehash: 1cd1c077a8f2a5fe3b2b46c2e1da2e92b5a797a6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33402057"
---
# <a name="emitassembly-method"></a><span data-ttu-id="da2d1-102">Metodo EmitAssembly</span><span class="sxs-lookup"><span data-stu-id="da2d1-102">EmitAssembly Method</span></span>
<span data-ttu-id="da2d1-103">Crea l'assembly.</span><span class="sxs-lookup"><span data-stu-id="da2d1-103">Creates the assembly.</span></span> <span data-ttu-id="da2d1-104">Chiamare questo metodo dopo la chiusura di tutti gli altri file ad eccezione del file di assembly.</span><span class="sxs-lookup"><span data-stu-id="da2d1-104">Call this method after all other files are closed except for the assembly file.</span></span> <span data-ttu-id="da2d1-105">Non chiamare questo metodo durante la creazione di moduli non associati.</span><span class="sxs-lookup"><span data-stu-id="da2d1-105">Do not call this method when producing unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da2d1-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="da2d1-106">Syntax</span></span>  
  
```  
HRESULT EmitAssembly(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="da2d1-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="da2d1-107">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="da2d1-108">ID dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="da2d1-108">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="da2d1-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="da2d1-109">Return Value</span></span>  
 <span data-ttu-id="da2d1-110">Se il metodo ha esito positivo, restituisce S_OK.</span><span class="sxs-lookup"><span data-stu-id="da2d1-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="da2d1-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="da2d1-111">Requirements</span></span>  
 <span data-ttu-id="da2d1-112">Richiede alink.h</span><span class="sxs-lookup"><span data-stu-id="da2d1-112">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da2d1-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="da2d1-113">See Also</span></span>  
 [<span data-ttu-id="da2d1-114">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="da2d1-114">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="da2d1-115">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="da2d1-115">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="da2d1-116">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="da2d1-116">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)

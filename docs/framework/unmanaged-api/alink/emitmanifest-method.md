---
title: Metodo EmitManifest
ms.date: 03/30/2017
api_name:
- EmitManifest
- IALink.EmitManifest
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EmitManifest
helpviewer_keywords:
- EmitManifest method
ms.assetid: fdebc1f3-b62e-4d9e-b775-8ccaa8ecb250
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9217a045a8ddf6ad41adcc71a9568a05fe3fb334
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54565543"
---
# <a name="emitmanifest-method"></a><span data-ttu-id="1ac47-102">Metodo EmitManifest</span><span class="sxs-lookup"><span data-stu-id="1ac47-102">EmitManifest Method</span></span>
<span data-ttu-id="1ac47-103">Crea il manifesto finale.</span><span class="sxs-lookup"><span data-stu-id="1ac47-103">Emits the final manifest.</span></span> <span data-ttu-id="1ac47-104">Chiamare questo metodo dopo l'importazione di tutti gli altri file e tutte le opzioni di impostazione.</span><span class="sxs-lookup"><span data-stu-id="1ac47-104">Call this method after importing all other files and setting all options.</span></span> <span data-ttu-id="1ac47-105">Non chiamare questo metodo per i moduli non associati.</span><span class="sxs-lookup"><span data-stu-id="1ac47-105">Do not call this method for unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1ac47-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1ac47-106">Syntax</span></span>  
  
```  
HRESULT EmitManifest(  
    mdAssembly   AssemblyID,  
    DWORD*       pdwReserveSize,  
    mdAssembly*  ptkManifest  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1ac47-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="1ac47-107">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="1ac47-108">ID dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="1ac47-108">ID of the assembly.</span></span>  
  
 `pdwReserveSize`  
 <span data-ttu-id="1ac47-109">Riceve le dimensioni da riservare nel file di assembly, recuperarne [funzione StrongNameSignatureSize](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturesize-function.md).</span><span class="sxs-lookup"><span data-stu-id="1ac47-109">Receives the size to reserve in the assembly file, retrieved from [StrongNameSignatureSize Function](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturesize-function.md).</span></span>  
  
 `ptkManifest`  
 <span data-ttu-id="1ac47-110">Facoltativamente riceve il token del manifesto dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="1ac47-110">Optionally receives the assembly manifest token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1ac47-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="1ac47-111">Return Value</span></span>  
 <span data-ttu-id="1ac47-112">Restituisce S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="1ac47-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1ac47-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1ac47-113">Requirements</span></span>  
 <span data-ttu-id="1ac47-114">Richiede alink.h.</span><span class="sxs-lookup"><span data-stu-id="1ac47-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ac47-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1ac47-115">See also</span></span>
- [<span data-ttu-id="1ac47-116">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="1ac47-116">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="1ac47-117">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="1ac47-117">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="1ac47-118">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="1ac47-118">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)

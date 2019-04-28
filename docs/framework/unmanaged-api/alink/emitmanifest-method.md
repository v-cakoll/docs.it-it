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
ms.openlocfilehash: 051b5f47db05301f3a3326a2cc4cc5cf5c8b1ec2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61790000"
---
# <a name="emitmanifest-method"></a><span data-ttu-id="72f20-102">Metodo EmitManifest</span><span class="sxs-lookup"><span data-stu-id="72f20-102">EmitManifest Method</span></span>
<span data-ttu-id="72f20-103">Crea il manifesto finale.</span><span class="sxs-lookup"><span data-stu-id="72f20-103">Emits the final manifest.</span></span> <span data-ttu-id="72f20-104">Chiamare questo metodo dopo l'importazione di tutti gli altri file e tutte le opzioni di impostazione.</span><span class="sxs-lookup"><span data-stu-id="72f20-104">Call this method after importing all other files and setting all options.</span></span> <span data-ttu-id="72f20-105">Non chiamare questo metodo per i moduli non associati.</span><span class="sxs-lookup"><span data-stu-id="72f20-105">Do not call this method for unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72f20-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="72f20-106">Syntax</span></span>  
  
```  
HRESULT EmitManifest(  
    mdAssembly   AssemblyID,  
    DWORD*       pdwReserveSize,  
    mdAssembly*  ptkManifest  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="72f20-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="72f20-107">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="72f20-108">ID dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="72f20-108">ID of the assembly.</span></span>  
  
 `pdwReserveSize`  
 <span data-ttu-id="72f20-109">Riceve le dimensioni da riservare nel file di assembly, recuperarne [funzione StrongNameSignatureSize](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturesize-function.md).</span><span class="sxs-lookup"><span data-stu-id="72f20-109">Receives the size to reserve in the assembly file, retrieved from [StrongNameSignatureSize Function](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturesize-function.md).</span></span>  
  
 `ptkManifest`  
 <span data-ttu-id="72f20-110">Facoltativamente riceve il token del manifesto dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="72f20-110">Optionally receives the assembly manifest token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="72f20-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="72f20-111">Return Value</span></span>  
 <span data-ttu-id="72f20-112">Restituisce S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="72f20-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="72f20-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="72f20-113">Requirements</span></span>  
 <span data-ttu-id="72f20-114">Richiede alink.h.</span><span class="sxs-lookup"><span data-stu-id="72f20-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72f20-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="72f20-115">See also</span></span>

- [<span data-ttu-id="72f20-116">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="72f20-116">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="72f20-117">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="72f20-117">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="72f20-118">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="72f20-118">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)

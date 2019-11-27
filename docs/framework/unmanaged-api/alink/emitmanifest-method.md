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
ms.openlocfilehash: f3bb978b8358992fd9aa7da922e28efc1ed1a951
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446488"
---
# <a name="emitmanifest-method"></a><span data-ttu-id="ba3d3-102">Metodo EmitManifest</span><span class="sxs-lookup"><span data-stu-id="ba3d3-102">EmitManifest Method</span></span>
<span data-ttu-id="ba3d3-103">Genera il manifesto finale.</span><span class="sxs-lookup"><span data-stu-id="ba3d3-103">Emits the final manifest.</span></span> <span data-ttu-id="ba3d3-104">Chiamare questo metodo dopo l'importazione di tutti gli altri file e l'impostazione di tutte le opzioni.</span><span class="sxs-lookup"><span data-stu-id="ba3d3-104">Call this method after importing all other files and setting all options.</span></span> <span data-ttu-id="ba3d3-105">Non chiamare questo metodo per i moduli non associati.</span><span class="sxs-lookup"><span data-stu-id="ba3d3-105">Do not call this method for unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba3d3-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ba3d3-106">Syntax</span></span>  
  
```cpp  
HRESULT EmitManifest(  
    mdAssembly   AssemblyID,  
    DWORD*       pdwReserveSize,  
    mdAssembly*  ptkManifest  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="ba3d3-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="ba3d3-107">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="ba3d3-108">ID dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="ba3d3-108">ID of the assembly.</span></span>  
  
 `pdwReserveSize`  
 <span data-ttu-id="ba3d3-109">Riceve le dimensioni da riservare nel file di assembly, recuperate dalla [funzione StrongNameSignatureSize](../strong-naming/strongnamesignaturesize-function.md).</span><span class="sxs-lookup"><span data-stu-id="ba3d3-109">Receives the size to reserve in the assembly file, retrieved from [StrongNameSignatureSize Function](../strong-naming/strongnamesignaturesize-function.md).</span></span>  
  
 `ptkManifest`  
 <span data-ttu-id="ba3d3-110">Riceve facoltativamente il token del manifesto dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="ba3d3-110">Optionally receives the assembly manifest token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ba3d3-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="ba3d3-111">Return Value</span></span>  
 <span data-ttu-id="ba3d3-112">Restituisce S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="ba3d3-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ba3d3-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ba3d3-113">Requirements</span></span>  
 <span data-ttu-id="ba3d3-114">Richiede ALink. h.</span><span class="sxs-lookup"><span data-stu-id="ba3d3-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba3d3-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ba3d3-115">See also</span></span>

- [<span data-ttu-id="ba3d3-116">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="ba3d3-116">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="ba3d3-117">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="ba3d3-117">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="ba3d3-118">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="ba3d3-118">ALink API</span></span>](index.md)

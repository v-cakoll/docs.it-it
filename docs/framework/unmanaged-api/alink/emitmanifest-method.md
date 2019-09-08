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
ms.openlocfilehash: bdab1fd10be8fd245f4348798232964721b4487a
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70777334"
---
# <a name="emitmanifest-method"></a><span data-ttu-id="3078f-102">Metodo EmitManifest</span><span class="sxs-lookup"><span data-stu-id="3078f-102">EmitManifest Method</span></span>
<span data-ttu-id="3078f-103">Genera il manifesto finale.</span><span class="sxs-lookup"><span data-stu-id="3078f-103">Emits the final manifest.</span></span> <span data-ttu-id="3078f-104">Chiamare questo metodo dopo l'importazione di tutti gli altri file e l'impostazione di tutte le opzioni.</span><span class="sxs-lookup"><span data-stu-id="3078f-104">Call this method after importing all other files and setting all options.</span></span> <span data-ttu-id="3078f-105">Non chiamare questo metodo per i moduli non associati.</span><span class="sxs-lookup"><span data-stu-id="3078f-105">Do not call this method for unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3078f-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3078f-106">Syntax</span></span>  
  
```cpp  
HRESULT EmitManifest(  
    mdAssembly   AssemblyID,  
    DWORD*       pdwReserveSize,  
    mdAssembly*  ptkManifest  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="3078f-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="3078f-107">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="3078f-108">ID dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="3078f-108">ID of the assembly.</span></span>  
  
 `pdwReserveSize`  
 <span data-ttu-id="3078f-109">Riceve le dimensioni da riservare nel file di assembly, recuperate dalla [funzione StrongNameSignatureSize](../strong-naming/strongnamesignaturesize-function.md).</span><span class="sxs-lookup"><span data-stu-id="3078f-109">Receives the size to reserve in the assembly file, retrieved from [StrongNameSignatureSize Function](../strong-naming/strongnamesignaturesize-function.md).</span></span>  
  
 `ptkManifest`  
 <span data-ttu-id="3078f-110">Riceve facoltativamente il token del manifesto dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="3078f-110">Optionally receives the assembly manifest token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3078f-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="3078f-111">Return Value</span></span>  
 <span data-ttu-id="3078f-112">Restituisce S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="3078f-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3078f-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3078f-113">Requirements</span></span>  
 <span data-ttu-id="3078f-114">Richiede ALink. h.</span><span class="sxs-lookup"><span data-stu-id="3078f-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3078f-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3078f-115">See also</span></span>

- [<span data-ttu-id="3078f-116">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="3078f-116">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="3078f-117">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="3078f-117">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="3078f-118">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="3078f-118">ALink API</span></span>](index.md)

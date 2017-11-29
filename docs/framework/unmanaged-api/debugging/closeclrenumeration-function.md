---
title: Funzione CloseCLREnumeration
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CloseCLREnumeration
api_location: dbgshim.dll
api_type: COM
f1_keywords: CloseCLREnumeration
helpviewer_keywords:
- debugging API [Silverlight]
- Silverlight, debugging
- CloseCLR Enumeration function
ms.assetid: 5e3c3958-80bb-43b1-a96b-dd3e6dbd9cd7
topic_type: apiref
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d9f14b851795c92c3ce0c1e7536a4ff78fbdf927
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="closeclrenumeration-function"></a><span data-ttu-id="9b71e-102">Funzione CloseCLREnumeration</span><span class="sxs-lookup"><span data-stu-id="9b71e-102">CloseCLREnumeration Function</span></span>
<span data-ttu-id="9b71e-103">Chiude qualsiasi valido common language runtime (CLR) continuano l'avvio gli eventi che si trova in una matrice di handle restituita dal [funzione EnumerateCLRs](../../../../docs/framework/unmanaged-api/debugging/enumerateclrs-function.md)e libera la memoria per le matrici del percorso stringa e di handle.</span><span class="sxs-lookup"><span data-stu-id="9b71e-103">Closes any valid common language runtime (CLR) continue-startup events located in an array of handles returned by the [EnumerateCLRs function](../../../../docs/framework/unmanaged-api/debugging/enumerateclrs-function.md), and frees the memory for the handle and string path arrays.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b71e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9b71e-104">Syntax</span></span>  
  
```  
HRESULT CloseCLREnumeration (  
    [in]  DWORD      pHandleArray,  
    [in]  LPWSTR**   pStringArray,  
    [in]  DWORD*     dwArrayLength  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9b71e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="9b71e-105">Parameters</span></span>  
 `pHandleArray`  
 <span data-ttu-id="9b71e-106">[in] Puntatore alla matrice di handle di evento restituito dal [funzione EnumerateCLRs](../../../../docs/framework/unmanaged-api/debugging/enumerateclrs-function.md).</span><span class="sxs-lookup"><span data-stu-id="9b71e-106">[in] Pointer to the array of event handles returned from the [EnumerateCLRs function](../../../../docs/framework/unmanaged-api/debugging/enumerateclrs-function.md).</span></span>  
  
 `pStringArray`  
 <span data-ttu-id="9b71e-107">[in] Puntatore alla matrice di percorsi di stringa CLR restituiti dal [funzione EnumerateCLRs](../../../../docs/framework/unmanaged-api/debugging/enumerateclrs-function.md).</span><span class="sxs-lookup"><span data-stu-id="9b71e-107">[in] Pointer to the array of CLR string paths returned from the [EnumerateCLRs function](../../../../docs/framework/unmanaged-api/debugging/enumerateclrs-function.md).</span></span>  
  
 `dwArrayLength`  
 <span data-ttu-id="9b71e-108">[in] DWORD contenente la dimensione (lunghezza) di `pHandleArray` o `pStringArray` (sono uguali).</span><span class="sxs-lookup"><span data-stu-id="9b71e-108">[in] DWORD that contains the size (length) of either `pHandleArray` or `pStringArray` (they are the same).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9b71e-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="9b71e-109">Return Value</span></span>  
 <span data-ttu-id="9b71e-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="9b71e-110">S_OK</span></span>  
 <span data-ttu-id="9b71e-111">Gli handle aperti per la [funzione EnumerateCLRs](../../../../docs/framework/unmanaged-api/debugging/enumerateclrs-function.md) vengono chiusi, e viene liberata la memoria allocata per le matrici di tipo stringa e di handle.</span><span class="sxs-lookup"><span data-stu-id="9b71e-111">Handles opened by the [EnumerateCLRs function](../../../../docs/framework/unmanaged-api/debugging/enumerateclrs-function.md) are closed, and memory allocated for the handle and string arrays is freed.</span></span>  
  
 <span data-ttu-id="9b71e-112">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="9b71e-112">E_INVALIDARG</span></span>  
 <span data-ttu-id="9b71e-113">La lunghezza di `pHandleArray` non corrisponde alla lunghezza passata in `dwArrayLength`.</span><span class="sxs-lookup"><span data-stu-id="9b71e-113">The length of `pHandleArray` does not match the length that is passed in `dwArrayLength`.</span></span>  
  
 <span data-ttu-id="9b71e-114">E_FAIL (o altri codici E_ restituiti)</span><span class="sxs-lookup"><span data-stu-id="9b71e-114">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="9b71e-115">La funzione non è in grado di liberare la memoria per `pHandleArray` ed `pStringArray`.</span><span class="sxs-lookup"><span data-stu-id="9b71e-115">The function is unable to free the memory for `pHandleArray` and `pStringArray`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9b71e-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9b71e-116">Requirements</span></span>  
 <span data-ttu-id="9b71e-117">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9b71e-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9b71e-118">**Intestazione:** dbgshim. h</span><span class="sxs-lookup"><span data-stu-id="9b71e-118">**Header:** dbgshim.h</span></span>  
  
 <span data-ttu-id="9b71e-119">**Libreria:** dbgshim.dll</span><span class="sxs-lookup"><span data-stu-id="9b71e-119">**Library:** dbgshim.dll</span></span>  
  
 <span data-ttu-id="9b71e-120">**Versioni di .NET framework:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="9b71e-120">**.NET Framework Versions:** 3.5 SP1</span></span>

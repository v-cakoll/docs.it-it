---
title: Metodo ICorDebugMergedAssemblyRecord::GetCulture
ms.date: 03/30/2017
ms.assetid: 030b2f8c-8c21-40b7-855d-3afa78975a17
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ee20ddd337e99836e74fe95e88e9e49a9a783ea7
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57466063"
---
# <a name="icordebugmergedassemblyrecordgetculture-method"></a><span data-ttu-id="d4487-102">Metodo ICorDebugMergedAssemblyRecord::GetCulture</span><span class="sxs-lookup"><span data-stu-id="d4487-102">ICorDebugMergedAssemblyRecord::GetCulture Method</span></span>
<span data-ttu-id="d4487-103">Ottiene la stringa del nome delle impostazioni cultura dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="d4487-103">Gets the culture name string of the assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4487-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d4487-104">Syntax</span></span>  
  
```  
HRESULT GetCulture(  
   [in] ULONG32 cchCulture,   
   [out] ULONG32 *pcchCulture,   
   [out, size_is(cchCulture), length_is(*pcchCulture)] WCHAR szCulture[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d4487-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d4487-105">Parameters</span></span>  
 `cchCulture`  
 <span data-ttu-id="d4487-106">[in] Numero di caratteri nel buffer `szCulture`.</span><span class="sxs-lookup"><span data-stu-id="d4487-106">[in] The number of characters in the `szCulture` buffer.</span></span>  
  
 `pcchCulture`  
 <span data-ttu-id="d4487-107">[out] Numero di byte effettivamente scritti nel buffer `szCulture`.</span><span class="sxs-lookup"><span data-stu-id="d4487-107">[out] The number of characters actually written to the `szCulture` buffer.</span></span>  
  
 `szCulture`  
 <span data-ttu-id="d4487-108">[out] Matrice di caratteri che contiene il nome delle impostazioni cultura.</span><span class="sxs-lookup"><span data-stu-id="d4487-108">[out] A character array that contains the culture name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d4487-109">Note</span><span class="sxs-lookup"><span data-stu-id="d4487-109">Remarks</span></span>  
 <span data-ttu-id="d4487-110">Il nome delle impostazioni cultura è rappresentato da una stringa univoca che identifica delle impostazioni cultura, ad esempio "en-US" per le impostazioni cultura inglese (Stati Uniti) o "neutral" per impostazioni cultura non associate ad alcun paese.</span><span class="sxs-lookup"><span data-stu-id="d4487-110">The culture name is a unique string that identifies a culture, such as "en-US" (for the English (United States) culture), or "neutral" (for a neutral culture).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d4487-111">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="d4487-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d4487-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d4487-112">Requirements</span></span>  
 <span data-ttu-id="d4487-113">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d4487-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d4487-114">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d4487-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d4487-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d4487-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d4487-116">**Versioni di .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d4487-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4487-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d4487-117">See also</span></span>
- [<span data-ttu-id="d4487-118">Interfaccia ICorDebugMergedAssemblyRecord</span><span class="sxs-lookup"><span data-stu-id="d4487-118">ICorDebugMergedAssemblyRecord Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md)
- [<span data-ttu-id="d4487-119">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="d4487-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

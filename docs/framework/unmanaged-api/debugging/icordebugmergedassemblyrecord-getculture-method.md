---
title: Metodo ICorDebugMergedAssemblyRecord::GetCulture
ms.date: 03/30/2017
ms.assetid: 030b2f8c-8c21-40b7-855d-3afa78975a17
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2f2336c89a32b202c4226f1ed194d786be6fa020
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33415357"
---
# <a name="icordebugmergedassemblyrecordgetculture-method"></a><span data-ttu-id="81922-102">Metodo ICorDebugMergedAssemblyRecord::GetCulture</span><span class="sxs-lookup"><span data-stu-id="81922-102">ICorDebugMergedAssemblyRecord::GetCulture Method</span></span>
<span data-ttu-id="81922-103">Ottiene la stringa del nome delle impostazioni cultura dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="81922-103">Gets the culture name string of the assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="81922-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="81922-104">Syntax</span></span>  
  
```  
HRESULT GetCulture(  
   [in] ULONG32 cchCulture,   
   [out] ULONG32 *pcchCulture,   
   [out, size_is(cchCulture), length_is(*pcchCulture)] WCHAR szCulture[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="81922-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="81922-105">Parameters</span></span>  
 `cchCulture`  
 <span data-ttu-id="81922-106">[in] Numero di caratteri nel buffer `szCulture`.</span><span class="sxs-lookup"><span data-stu-id="81922-106">[in] The number of characters in the `szCulture` buffer.</span></span>  
  
 `pcchCulture`  
 <span data-ttu-id="81922-107">[out] Numero di byte effettivamente scritti nel buffer `szCulture`.</span><span class="sxs-lookup"><span data-stu-id="81922-107">[out] The number of characters actually written to the `szCulture` buffer.</span></span>  
  
 `szCulture`  
 <span data-ttu-id="81922-108">[out] Matrice di caratteri che contiene il nome delle impostazioni cultura.</span><span class="sxs-lookup"><span data-stu-id="81922-108">[out] A character array that contains the culture name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="81922-109">Note</span><span class="sxs-lookup"><span data-stu-id="81922-109">Remarks</span></span>  
 <span data-ttu-id="81922-110">Il nome delle impostazioni cultura è rappresentato da una stringa univoca che identifica delle impostazioni cultura, ad esempio "en-US" per le impostazioni cultura inglese (Stati Uniti) o "neutral" per impostazioni cultura non associate ad alcun paese.</span><span class="sxs-lookup"><span data-stu-id="81922-110">The culture name is a unique string that identifies a culture, such as "en-US" (for the English (United States) culture), or "neutral" (for a neutral culture).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="81922-111">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="81922-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="81922-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="81922-112">Requirements</span></span>  
 <span data-ttu-id="81922-113">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="81922-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="81922-114">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="81922-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="81922-115">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="81922-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="81922-116">**Versioni di .NET framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="81922-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81922-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="81922-117">See Also</span></span>  
 [<span data-ttu-id="81922-118">Interfaccia ICorDebugMergedAssemblyRecord</span><span class="sxs-lookup"><span data-stu-id="81922-118">ICorDebugMergedAssemblyRecord Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md)  
 [<span data-ttu-id="81922-119">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="81922-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

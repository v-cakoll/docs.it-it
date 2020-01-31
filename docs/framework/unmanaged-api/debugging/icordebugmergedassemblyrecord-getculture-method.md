---
title: Metodo ICorDebugMergedAssemblyRecord::GetCulture
ms.date: 03/30/2017
ms.assetid: 030b2f8c-8c21-40b7-855d-3afa78975a17
ms.openlocfilehash: 77ad8ee7977096e87b9fd2e131920a042243560e
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793150"
---
# <a name="icordebugmergedassemblyrecordgetculture-method"></a><span data-ttu-id="02842-102">Metodo ICorDebugMergedAssemblyRecord::GetCulture</span><span class="sxs-lookup"><span data-stu-id="02842-102">ICorDebugMergedAssemblyRecord::GetCulture Method</span></span>
<span data-ttu-id="02842-103">Ottiene la stringa del nome delle impostazioni cultura dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="02842-103">Gets the culture name string of the assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02842-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="02842-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCulture(  
   [in] ULONG32 cchCulture,   
   [out] ULONG32 *pcchCulture,   
   [out, size_is(cchCulture), length_is(*pcchCulture)] WCHAR szCulture[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="02842-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="02842-105">Parameters</span></span>  
 `cchCulture`  
 <span data-ttu-id="02842-106">[in] Numero di caratteri nel buffer `szCulture`.</span><span class="sxs-lookup"><span data-stu-id="02842-106">[in] The number of characters in the `szCulture` buffer.</span></span>  
  
 `pcchCulture`  
 <span data-ttu-id="02842-107">[out] Numero di byte effettivamente scritti nel buffer `szCulture`.</span><span class="sxs-lookup"><span data-stu-id="02842-107">[out] The number of characters actually written to the `szCulture` buffer.</span></span>  
  
 `szCulture`  
 <span data-ttu-id="02842-108">[out] Matrice di caratteri che contiene il nome delle impostazioni cultura.</span><span class="sxs-lookup"><span data-stu-id="02842-108">[out] A character array that contains the culture name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="02842-109">Note</span><span class="sxs-lookup"><span data-stu-id="02842-109">Remarks</span></span>  
 <span data-ttu-id="02842-110">Il nome delle impostazioni cultura è rappresentato da una stringa univoca che identifica delle impostazioni cultura, ad esempio "en-US" per le impostazioni cultura inglese (Stati Uniti) o "neutral" per impostazioni cultura non associate ad alcun paese.</span><span class="sxs-lookup"><span data-stu-id="02842-110">The culture name is a unique string that identifies a culture, such as "en-US" (for the English (United States) culture), or "neutral" (for a neutral culture).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="02842-111">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="02842-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="02842-112">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="02842-112">Requirements</span></span>  
 <span data-ttu-id="02842-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="02842-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="02842-114">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="02842-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="02842-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="02842-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="02842-116">**Versioni .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="02842-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02842-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="02842-117">See also</span></span>

- [<span data-ttu-id="02842-118">Interfaccia ICorDebugMergedAssemblyRecord</span><span class="sxs-lookup"><span data-stu-id="02842-118">ICorDebugMergedAssemblyRecord Interface</span></span>](icordebugmergedassemblyrecord-interface.md)
- [<span data-ttu-id="02842-119">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="02842-119">Debugging Interfaces</span></span>](debugging-interfaces.md)

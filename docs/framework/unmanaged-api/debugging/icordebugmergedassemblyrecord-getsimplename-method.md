---
title: Metodo ICorDebugMergedAssemblyRecord::GetSimpleName
ms.date: 03/30/2017
ms.assetid: bc3410f6-ebca-4bca-9b45-fc38c74fa9cb
ms.openlocfilehash: f6c6682c8bb23143d308aa4f1a6887b28ea82fcd
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83209708"
---
# <a name="icordebugmergedassemblyrecordgetsimplename-method"></a><span data-ttu-id="fdb3b-102">Metodo ICorDebugMergedAssemblyRecord::GetSimpleName</span><span class="sxs-lookup"><span data-stu-id="fdb3b-102">ICorDebugMergedAssemblyRecord::GetSimpleName Method</span></span>
<span data-ttu-id="fdb3b-103">Ottiene il nome semplice dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="fdb3b-103">Gets the simple name of the assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fdb3b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fdb3b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSimpleName(  
   [in] ULONG32 cchName,
   [out] ULONG32 *pcchName,
   [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fdb3b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="fdb3b-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="fdb3b-106">[in] Numero di caratteri nel buffer `szName`.</span><span class="sxs-lookup"><span data-stu-id="fdb3b-106">[in] The number of characters in the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="fdb3b-107">[out] Puntatore al numero di caratteri effettivamente scritti nel buffer `szName`.</span><span class="sxs-lookup"><span data-stu-id="fdb3b-107">[out] A pointer to the number of characters actually written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="fdb3b-108">Puntatore a una matrice di caratteri.</span><span class="sxs-lookup"><span data-stu-id="fdb3b-108">A pointer to a character array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fdb3b-109">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="fdb3b-109">Remarks</span></span>  
 <span data-ttu-id="fdb3b-110">Questo metodo recupera il nome semplice di un assembly, ad esempio "System. Collections", senza estensione di file, versione, impostazioni cultura o token di chiave pubblica.</span><span class="sxs-lookup"><span data-stu-id="fdb3b-110">This method retrieves the simple name of an assembly (such as "System.Collections"), without a file extension, version, culture, or public key token.</span></span> <span data-ttu-id="fdb3b-111">Corrisponde alla proprietà <xref:System.Reflection.AssemblyName.Name%2A?displayProperty=nameWithType> nel codice gestito.</span><span class="sxs-lookup"><span data-stu-id="fdb3b-111">It corresponds to the <xref:System.Reflection.AssemblyName.Name%2A?displayProperty=nameWithType> property in managed code.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fdb3b-112">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="fdb3b-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fdb3b-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="fdb3b-113">Requirements</span></span>  
 <span data-ttu-id="fdb3b-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fdb3b-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fdb3b-115">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fdb3b-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fdb3b-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fdb3b-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fdb3b-117">**Versioni .NET Framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fdb3b-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fdb3b-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fdb3b-118">See also</span></span>

- [<span data-ttu-id="fdb3b-119">Interfaccia ICorDebugMergedAssemblyRecord</span><span class="sxs-lookup"><span data-stu-id="fdb3b-119">ICorDebugMergedAssemblyRecord Interface</span></span>](icordebugmergedassemblyrecord-interface.md)
- [<span data-ttu-id="fdb3b-120">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="fdb3b-120">Debugging Interfaces</span></span>](debugging-interfaces.md)

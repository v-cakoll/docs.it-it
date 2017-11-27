---
title: Funzione CompareAssemblyIdentity
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CompareAssemblyIdentity
api_location:
- fusion.dll
- clr.dll
api_type: COM
f1_keywords: CompareAssemblyIdentity
helpviewer_keywords: CompareAssemblyIdentity function [.NET Framework fusion]
ms.assetid: 8b364ae1-8efa-4744-a7da-81fd093d84d6
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9d9d7b4934d4295ee799fb13d3d749e6b977e644
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="compareassemblyidentity-function"></a><span data-ttu-id="459af-102">Funzione CompareAssemblyIdentity</span><span class="sxs-lookup"><span data-stu-id="459af-102">CompareAssemblyIdentity Function</span></span>
<span data-ttu-id="459af-103">Confronta due identità di assembly per determinare se sono equivalenti.</span><span class="sxs-lookup"><span data-stu-id="459af-103">Compares two assembly identities to determine whether they are equivalent.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="459af-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="459af-104">Syntax</span></span>  
  
```  
STDAPI CompareAssemblyIdentity (  
    [in]  LPCWSTR                  pwzAssemblyIdentity1,  
    [in]  BOOL                     fUnified1,  
    [in]  LPCWSTR                  pwzAssemblyIdentity2,  
    [in]  BOOL                     fUnified2,  
    [out] BOOL                     *pfEquivalent,  
    [out] AssemblyComparisonResult *pResult  
 );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="459af-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="459af-105">Parameters</span></span>  
 `pwzAssemblyIdentity1`  
 <span data-ttu-id="459af-106">[in] Identità testuale del primo assembly nel confronto.</span><span class="sxs-lookup"><span data-stu-id="459af-106">[in] The textual identity of the first assembly in the comparison.</span></span>  
  
 `fUnified1`  
 <span data-ttu-id="459af-107">[in] Flag booleano che indica l'unificazione specificata dall'utente per `pwzAssemblyIdentity1`.</span><span class="sxs-lookup"><span data-stu-id="459af-107">[in] A Boolean flag that indicates user-specified unification for `pwzAssemblyIdentity1`.</span></span>  
  
 `pwzAssemblyIdentity2`  
 <span data-ttu-id="459af-108">[in] Identità testuale del secondo assembly nel confronto.</span><span class="sxs-lookup"><span data-stu-id="459af-108">[in] The textual identity of the second assembly in the comparison.</span></span>  
  
 `fUnified2`  
 <span data-ttu-id="459af-109">[in] Flag booleano che indica l'unificazione specificata dall'utente per `pwzAssemblyIdentity2`.</span><span class="sxs-lookup"><span data-stu-id="459af-109">[in] A Boolean flag that indicates user-specified unification for `pwzAssemblyIdentity2`.</span></span>  
  
 `pfEquivalent`  
 <span data-ttu-id="459af-110">[out] Flag booleano che indica se i due assembly sono equivalenti.</span><span class="sxs-lookup"><span data-stu-id="459af-110">[out] A Boolean flag that indicates whether the two assemblies are equivalent.</span></span>  
  
 `pResult`  
 <span data-ttu-id="459af-111">[out] Un [AssemblyComparisonResult](../../../../docs/framework/unmanaged-api/fusion/assemblycomparisonresult-enumeration.md) enumerazione che contiene informazioni dettagliate sul confronto.</span><span class="sxs-lookup"><span data-stu-id="459af-111">[out] An [AssemblyComparisonResult](../../../../docs/framework/unmanaged-api/fusion/assemblycomparisonresult-enumeration.md) enumeration that contains detailed information about the comparison.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="459af-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="459af-112">Return Value</span></span>  
 <span data-ttu-id="459af-113">`pfEquivalent`Restituisce un valore booleano che indica se i due assembly sono equivalenti.</span><span class="sxs-lookup"><span data-stu-id="459af-113">`pfEquivalent` returns a Boolean value that indicates whether the two assemblies are equivalent.</span></span> <span data-ttu-id="459af-114">`pResult`Restituisce uno del `AssemblyComparisonResult` valori, per fornire più dettagliate sul motivo per il valore di `pfEquivalent`.</span><span class="sxs-lookup"><span data-stu-id="459af-114">`pResult` returns one of the `AssemblyComparisonResult` values, to give a more detailed reason for the value of `pfEquivalent`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="459af-115">Note</span><span class="sxs-lookup"><span data-stu-id="459af-115">Remarks</span></span>  
 <span data-ttu-id="459af-116">`CompareAssemblyIdentity`Controlla se `pwzAssemblyIdentity1` e `pwzAssemblyIdentity2` sono equivalenti.</span><span class="sxs-lookup"><span data-stu-id="459af-116">`CompareAssemblyIdentity` checks whether `pwzAssemblyIdentity1` and `pwzAssemblyIdentity2` are equivalent.</span></span> <span data-ttu-id="459af-117">`pfEquivalent`è impostato su `true` in uno o più delle condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="459af-117">`pfEquivalent` is set to `true` under one or more of the following conditions:</span></span>  
  
-   <span data-ttu-id="459af-118">Le due identità assembly sono equivalenti.</span><span class="sxs-lookup"><span data-stu-id="459af-118">The two assembly identities are equivalent.</span></span> <span data-ttu-id="459af-119">Per l'assembly con nome sicuro, equivalenza richiede il nome dell'assembly, versione, token di chiave pubblica e impostazioni cultura in modo identico.</span><span class="sxs-lookup"><span data-stu-id="459af-119">For strongly named assemblies, equivalency requires the assembly name, version, public key token, and culture to be identical.</span></span> <span data-ttu-id="459af-120">Per l'assembly con nome semplice, equivalenza richiede una corrispondenza nel nome dell'assembly e delle impostazioni cultura.</span><span class="sxs-lookup"><span data-stu-id="459af-120">For simply named assemblies, equivalency requires a match on the assembly name and culture.</span></span>  
  
-   <span data-ttu-id="459af-121">Entrambe le identità assembly fare riferimento ad assembly in esecuzione su .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="459af-121">Both assembly identities refer to assemblies that run on the .NET Framework.</span></span> <span data-ttu-id="459af-122">Questa condizione restituisce `true` anche se i numeri di versione di assembly non corrispondono.</span><span class="sxs-lookup"><span data-stu-id="459af-122">This condition returns `true` even if the assembly version numbers do not match.</span></span>  
  
-   <span data-ttu-id="459af-123">I due assembly non sono gestiti, ma `fUnified1` o `fUnified2` è stato impostato su `true`.</span><span class="sxs-lookup"><span data-stu-id="459af-123">The two assemblies are not managed assemblies, but `fUnified1` or `fUnified2` was set to `true`.</span></span>  
  
 <span data-ttu-id="459af-124">Il `fUnified` flag indica che tutti i numeri di versione fino al numero di versione di assembly con nome sicuro sono considerati equivalenti all'assembly con nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="459af-124">The `fUnified` flag indicates that all version numbers up to the version number of the strongly named assembly are considered equivalent to the strongly named assembly.</span></span> <span data-ttu-id="459af-125">Ad esempio, se il valore di `pwzAssemblyIndentity1` è "MyAssembly, versione = 3.0.0.0, culture = neutral, publicKeyToken =..." e il valore di `fUnified1` è `true`, ciò indica che tutte le versioni di MyAssembly tra 0.0.0.0 e 3.0.0.0 devono essere considerati equivalenti.</span><span class="sxs-lookup"><span data-stu-id="459af-125">For example, if the value of `pwzAssemblyIndentity1` is "MyAssembly, version=3.0.0.0, culture=neutral, publicKeyToken=....", and the value of `fUnified1` is `true`, this indicates that all versions of MyAssembly from version 0.0.0.0 to 3.0.0.0 should be treated as equivalent.</span></span> <span data-ttu-id="459af-126">In tal caso, se `pwzAssemblyIndentity2` fa riferimento allo stesso assembly come `pwzAssemblyIndentity1`, ad eccezione del fatto che disponga di un numero di versione, `pfEquivalent` è impostato su `true`.</span><span class="sxs-lookup"><span data-stu-id="459af-126">In such a case, if `pwzAssemblyIndentity2` refers to the same assembly as `pwzAssemblyIndentity1`, except that it has a lower version number, `pfEquivalent` is set to `true`.</span></span> <span data-ttu-id="459af-127">Se `pwzAssemblyIdentity2` fa riferimento a un numero di versione superiore, `pfEquivalent` è impostato su `true` solo se il valore di `fUnified2` è `true`.</span><span class="sxs-lookup"><span data-stu-id="459af-127">If `pwzAssemblyIdentity2` refers to a higher version number, `pfEquivalent` is set to `true` only if the value of `fUnified2` is `true`.</span></span>  
  
 <span data-ttu-id="459af-128">Il `pResult` parametro contiene informazioni specifiche sui motivi per cui i due assembly sono considerati equivalente o non è equivalente.</span><span class="sxs-lookup"><span data-stu-id="459af-128">The `pResult` parameter includes specific information about why the two assemblies are considered equivalent or not equivalent.</span></span> <span data-ttu-id="459af-129">Per ulteriori informazioni, vedere [enumerazione AssemblyComparisonResult](../../../../docs/framework/unmanaged-api/fusion/assemblycomparisonresult-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="459af-129">For more information, see [AssemblyComparisonResult Enumeration](../../../../docs/framework/unmanaged-api/fusion/assemblycomparisonresult-enumeration.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="459af-130">Requisiti</span><span class="sxs-lookup"><span data-stu-id="459af-130">Requirements</span></span>  
 <span data-ttu-id="459af-131">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="459af-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="459af-132">**Intestazione:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="459af-132">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="459af-133">**Libreria:** inclusa come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="459af-133">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="459af-134">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="459af-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="459af-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="459af-135">See Also</span></span>  
 [<span data-ttu-id="459af-136">Funzioni statiche globali Fusion</span><span class="sxs-lookup"><span data-stu-id="459af-136">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)  
 [<span data-ttu-id="459af-137">AssemblyComparisonResult (enumerazione)</span><span class="sxs-lookup"><span data-stu-id="459af-137">AssemblyComparisonResult Enumeration</span></span>](../../../../docs/framework/unmanaged-api/fusion/assemblycomparisonresult-enumeration.md)

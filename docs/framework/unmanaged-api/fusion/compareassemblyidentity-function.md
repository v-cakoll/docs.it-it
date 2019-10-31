---
title: Funzione CompareAssemblyIdentity
ms.date: 03/30/2017
api_name:
- CompareAssemblyIdentity
api_location:
- fusion.dll
- clr.dll
api_type:
- COM
f1_keywords:
- CompareAssemblyIdentity
helpviewer_keywords:
- CompareAssemblyIdentity function [.NET Framework fusion]
ms.assetid: 8b364ae1-8efa-4744-a7da-81fd093d84d6
topic_type:
- apiref
ms.openlocfilehash: f6711902fb9d5c5c16084057b731746843cf0230
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73108915"
---
# <a name="compareassemblyidentity-function"></a><span data-ttu-id="9f43e-102">Funzione CompareAssemblyIdentity</span><span class="sxs-lookup"><span data-stu-id="9f43e-102">CompareAssemblyIdentity Function</span></span>
<span data-ttu-id="9f43e-103">Confronta due identità di assembly per determinare se sono equivalenti.</span><span class="sxs-lookup"><span data-stu-id="9f43e-103">Compares two assembly identities to determine whether they are equivalent.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9f43e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9f43e-104">Syntax</span></span>  
  
```cpp  
STDAPI CompareAssemblyIdentity (  
    [in]  LPCWSTR                  pwzAssemblyIdentity1,  
    [in]  BOOL                     fUnified1,  
    [in]  LPCWSTR                  pwzAssemblyIdentity2,  
    [in]  BOOL                     fUnified2,  
    [out] BOOL                     *pfEquivalent,  
    [out] AssemblyComparisonResult *pResult  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="9f43e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="9f43e-105">Parameters</span></span>  
 `pwzAssemblyIdentity1`  
 <span data-ttu-id="9f43e-106">in Identità testuale del primo assembly nel confronto.</span><span class="sxs-lookup"><span data-stu-id="9f43e-106">[in] The textual identity of the first assembly in the comparison.</span></span>  
  
 `fUnified1`  
 <span data-ttu-id="9f43e-107">in Flag booleano che indica l'unificazione specificata dall'utente per `pwzAssemblyIdentity1`.</span><span class="sxs-lookup"><span data-stu-id="9f43e-107">[in] A Boolean flag that indicates user-specified unification for `pwzAssemblyIdentity1`.</span></span>  
  
 `pwzAssemblyIdentity2`  
 <span data-ttu-id="9f43e-108">in Identità testuale del secondo assembly nel confronto.</span><span class="sxs-lookup"><span data-stu-id="9f43e-108">[in] The textual identity of the second assembly in the comparison.</span></span>  
  
 `fUnified2`  
 <span data-ttu-id="9f43e-109">in Flag booleano che indica l'unificazione specificata dall'utente per `pwzAssemblyIdentity2`.</span><span class="sxs-lookup"><span data-stu-id="9f43e-109">[in] A Boolean flag that indicates user-specified unification for `pwzAssemblyIdentity2`.</span></span>  
  
 `pfEquivalent`  
 <span data-ttu-id="9f43e-110">out Flag booleano che indica se i due assembly sono equivalenti.</span><span class="sxs-lookup"><span data-stu-id="9f43e-110">[out] A Boolean flag that indicates whether the two assemblies are equivalent.</span></span>  
  
 `pResult`  
 <span data-ttu-id="9f43e-111">out Enumerazione [AssemblyComparisonResult](assemblycomparisonresult-enumeration.md) che contiene informazioni dettagliate sul confronto.</span><span class="sxs-lookup"><span data-stu-id="9f43e-111">[out] An [AssemblyComparisonResult](assemblycomparisonresult-enumeration.md) enumeration that contains detailed information about the comparison.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9f43e-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="9f43e-112">Return Value</span></span>  
 <span data-ttu-id="9f43e-113">`pfEquivalent` restituisce un valore booleano che indica se i due assembly sono equivalenti.</span><span class="sxs-lookup"><span data-stu-id="9f43e-113">`pfEquivalent` returns a Boolean value that indicates whether the two assemblies are equivalent.</span></span> <span data-ttu-id="9f43e-114">`pResult` restituisce uno dei valori `AssemblyComparisonResult`, per fornire una ragione più dettagliata del valore di `pfEquivalent`.</span><span class="sxs-lookup"><span data-stu-id="9f43e-114">`pResult` returns one of the `AssemblyComparisonResult` values, to give a more detailed reason for the value of `pfEquivalent`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9f43e-115">Note</span><span class="sxs-lookup"><span data-stu-id="9f43e-115">Remarks</span></span>  
 <span data-ttu-id="9f43e-116">`CompareAssemblyIdentity` controlla se `pwzAssemblyIdentity1` e `pwzAssemblyIdentity2` sono equivalenti.</span><span class="sxs-lookup"><span data-stu-id="9f43e-116">`CompareAssemblyIdentity` checks whether `pwzAssemblyIdentity1` and `pwzAssemblyIdentity2` are equivalent.</span></span> <span data-ttu-id="9f43e-117">`pfEquivalent` è impostato su `true` in una o più delle condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="9f43e-117">`pfEquivalent` is set to `true` under one or more of the following conditions:</span></span>  
  
- <span data-ttu-id="9f43e-118">Le due identità di assembly sono equivalenti.</span><span class="sxs-lookup"><span data-stu-id="9f43e-118">The two assembly identities are equivalent.</span></span> <span data-ttu-id="9f43e-119">Per gli assembly con nome sicuro, l'equivalenza richiede che il nome dell'assembly, la versione, il token di chiave pubblica e le impostazioni cultura siano identici.</span><span class="sxs-lookup"><span data-stu-id="9f43e-119">For strongly named assemblies, equivalency requires the assembly name, version, public key token, and culture to be identical.</span></span> <span data-ttu-id="9f43e-120">Per gli assembly con nome semplice, l'equivalenza richiede una corrispondenza in base al nome e alle impostazioni cultura dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="9f43e-120">For simply named assemblies, equivalency requires a match on the assembly name and culture.</span></span>  
  
- <span data-ttu-id="9f43e-121">Entrambe le identità degli assembly fanno riferimento agli assembly eseguiti nel .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9f43e-121">Both assembly identities refer to assemblies that run on the .NET Framework.</span></span> <span data-ttu-id="9f43e-122">Questa condizione restituisce `true` anche se i numeri di versione dell'assembly non corrispondono.</span><span class="sxs-lookup"><span data-stu-id="9f43e-122">This condition returns `true` even if the assembly version numbers do not match.</span></span>  
  
- <span data-ttu-id="9f43e-123">I due assembly non sono assembly gestiti, ma `fUnified1` o `fUnified2` è stato impostato su `true`.</span><span class="sxs-lookup"><span data-stu-id="9f43e-123">The two assemblies are not managed assemblies, but `fUnified1` or `fUnified2` was set to `true`.</span></span>  
  
 <span data-ttu-id="9f43e-124">Il flag `fUnified` indica che tutti i numeri di versione fino al numero di versione dell'assembly con nome sicuro sono considerati equivalenti all'assembly con nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="9f43e-124">The `fUnified` flag indicates that all version numbers up to the version number of the strongly named assembly are considered equivalent to the strongly named assembly.</span></span> <span data-ttu-id="9f43e-125">Se, ad esempio, il valore di `pwzAssemblyIndentity1` è "MyAssembly, Version = 3.0.0.0, Culture = neutral, publicKeyToken =...." e il valore di `fUnified1` è `true`, significa che tutte le versioni di MyAssembly dalla versione 0.0.0.0 a 3.0.0.0 devono essere considerate come equivalente.</span><span class="sxs-lookup"><span data-stu-id="9f43e-125">For example, if the value of `pwzAssemblyIndentity1` is "MyAssembly, version=3.0.0.0, culture=neutral, publicKeyToken=....", and the value of `fUnified1` is `true`, this indicates that all versions of MyAssembly from version 0.0.0.0 to 3.0.0.0 should be treated as equivalent.</span></span> <span data-ttu-id="9f43e-126">In tal caso, se `pwzAssemblyIndentity2` fa riferimento allo stesso assembly `pwzAssemblyIndentity1`, ad eccezione del fatto che ha un numero di versione inferiore, `pfEquivalent` viene impostato su `true`.</span><span class="sxs-lookup"><span data-stu-id="9f43e-126">In such a case, if `pwzAssemblyIndentity2` refers to the same assembly as `pwzAssemblyIndentity1`, except that it has a lower version number, `pfEquivalent` is set to `true`.</span></span> <span data-ttu-id="9f43e-127">Se `pwzAssemblyIdentity2` fa riferimento a un numero di versione superiore, `pfEquivalent` viene impostato su `true` solo se il valore di `fUnified2` è `true`.</span><span class="sxs-lookup"><span data-stu-id="9f43e-127">If `pwzAssemblyIdentity2` refers to a higher version number, `pfEquivalent` is set to `true` only if the value of `fUnified2` is `true`.</span></span>  
  
 <span data-ttu-id="9f43e-128">Il parametro `pResult` include informazioni specifiche sui motivi per cui i due assembly sono considerati equivalenti o non equivalenti.</span><span class="sxs-lookup"><span data-stu-id="9f43e-128">The `pResult` parameter includes specific information about why the two assemblies are considered equivalent or not equivalent.</span></span> <span data-ttu-id="9f43e-129">Per ulteriori informazioni, vedere [Enumerazione AssemblyComparisonResult](assemblycomparisonresult-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="9f43e-129">For more information, see [AssemblyComparisonResult Enumeration](assemblycomparisonresult-enumeration.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9f43e-130">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9f43e-130">Requirements</span></span>  
 <span data-ttu-id="9f43e-131">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9f43e-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9f43e-132">**Intestazione:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="9f43e-132">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="9f43e-133">**Libreria:** Incluso come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="9f43e-133">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="9f43e-134">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9f43e-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f43e-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9f43e-135">See also</span></span>

- [<span data-ttu-id="9f43e-136">Funzioni statiche globali Fusion</span><span class="sxs-lookup"><span data-stu-id="9f43e-136">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
- [<span data-ttu-id="9f43e-137">Enumerazione AssemblyComparisonResult</span><span class="sxs-lookup"><span data-stu-id="9f43e-137">AssemblyComparisonResult Enumeration</span></span>](assemblycomparisonresult-enumeration.md)

---
title: Funzione IsFrameworkAssembly
ms.date: 03/30/2017
api_name:
- IsFrameworkAssembly
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IsFrameworkAssembly
helpviewer_keywords:
- IsFrameworkAssembly function [.NET Framework fusion]
ms.assetid: b0c6f19b-d4fd-4971-88f0-12ffb5793da3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d0fb4c98ff2c8b071f05b42aefed61485001e97f
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57480325"
---
# <a name="isframeworkassembly-function"></a><span data-ttu-id="b6dfa-102">Funzione IsFrameworkAssembly</span><span class="sxs-lookup"><span data-stu-id="b6dfa-102">IsFrameworkAssembly Function</span></span>
<span data-ttu-id="b6dfa-103">Ottiene un valore che indica se l'assembly specificato è gestito.</span><span class="sxs-lookup"><span data-stu-id="b6dfa-103">Gets a value that indicates whether the specified assembly is managed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b6dfa-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b6dfa-104">Syntax</span></span>  
  
```  
HRESULT IsFrameworkAssembly (  
    [in]  LPCWSTR pwzAssemblyReference,  
    [out] LPBOOL  pbIsFrameworkAssembly,  
    [in]  LPWSTR  pwzFrameworkAssemblyIdentity,  
    [in]  LPDWORD pccSize  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="b6dfa-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="b6dfa-105">Parameters</span></span>  
 `pwzAssemblyReference`  
 <span data-ttu-id="b6dfa-106">[in] Il nome dell'assembly da verificare.</span><span class="sxs-lookup"><span data-stu-id="b6dfa-106">[in] The name of the assembly to check.</span></span>  
  
 `pbIsFrameworkAssembly`  
 <span data-ttu-id="b6dfa-107">[out] Valore booleano che indica se l'assembly è gestito.</span><span class="sxs-lookup"><span data-stu-id="b6dfa-107">[out] A Boolean value that indicates whether the assembly is managed.</span></span>  
  
 `pwzFrameworkAssemblyIdentity`  
 <span data-ttu-id="b6dfa-108">[in] Una stringa in formato non canonico che contiene l'identità univoca dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="b6dfa-108">[in] An uncanonicalized string that contains the unique identity of the assembly.</span></span>  
  
 `pccSize`  
 <span data-ttu-id="b6dfa-109">[in] Le dimensioni di `pwzFrameworkAssemblyIdentity`.</span><span class="sxs-lookup"><span data-stu-id="b6dfa-109">[in] The size of `pwzFrameworkAssemblyIdentity`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b6dfa-110">Note</span><span class="sxs-lookup"><span data-stu-id="b6dfa-110">Remarks</span></span>  
 <span data-ttu-id="b6dfa-111">Il `pwzAssemblyReference` parametro è un puntatore a una stringa di caratteri che contiene il nome di un assembly.</span><span class="sxs-lookup"><span data-stu-id="b6dfa-111">The `pwzAssemblyReference` parameter is a pointer to a character string that contains the name of an assembly.</span></span>  
  
 <span data-ttu-id="b6dfa-112">Se l'assembly fa parte di .NET Framework, il `pbIsFrameworkAssembly` parametro conterrà un valore booleano `true`.</span><span class="sxs-lookup"><span data-stu-id="b6dfa-112">If this assembly is part of the .NET Framework, the `pbIsFrameworkAssembly` parameter will contain a Boolean value of `true`.</span></span>  
  
 <span data-ttu-id="b6dfa-113">Se l'assembly denominato non fa parte di .NET Framework o se il `pwzAssemblyReference` parametro non corrisponde a un assembly `pbIsFrameworkAssembly` conterrà un valore booleano `false`.</span><span class="sxs-lookup"><span data-stu-id="b6dfa-113">If the named assembly is not part of the .NET Framework, or if the `pwzAssemblyReference` parameter does not name an assembly, `pbIsFrameworkAssembly` will contain a Boolean value of `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b6dfa-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b6dfa-114">Requirements</span></span>  
 <span data-ttu-id="b6dfa-115">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b6dfa-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6dfa-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b6dfa-116">See also</span></span>
- [<span data-ttu-id="b6dfa-117">Funzioni statiche globali Fusion</span><span class="sxs-lookup"><span data-stu-id="b6dfa-117">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)

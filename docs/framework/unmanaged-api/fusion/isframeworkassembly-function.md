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
ms.openlocfilehash: c3fd130759ab11b54b597d5c099c33dab93070ae
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33429250"
---
# <a name="isframeworkassembly-function"></a><span data-ttu-id="ed0a7-102">Funzione IsFrameworkAssembly</span><span class="sxs-lookup"><span data-stu-id="ed0a7-102">IsFrameworkAssembly Function</span></span>
<span data-ttu-id="ed0a7-103">Ottiene un valore che indica se l'assembly specificato è stato gestito.</span><span class="sxs-lookup"><span data-stu-id="ed0a7-103">Gets a value that indicates whether the specified assembly is managed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed0a7-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ed0a7-104">Syntax</span></span>  
  
```  
HRESULT IsFrameworkAssembly (  
    [in]  LPCWSTR pwzAssemblyReference,  
    [out] LPBOOL  pbIsFrameworkAssembly,  
    [in]  LPWSTR  pwzFrameworkAssemblyIdentity,  
    [in]  LPDWORD pccSize  
 );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ed0a7-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ed0a7-105">Parameters</span></span>  
 `pwzAssemblyReference`  
 <span data-ttu-id="ed0a7-106">[in] Il nome dell'assembly da controllare.</span><span class="sxs-lookup"><span data-stu-id="ed0a7-106">[in] The name of the assembly to check.</span></span>  
  
 `pbIsFrameworkAssembly`  
 <span data-ttu-id="ed0a7-107">[out] Valore booleano che indica se l'assembly è stato gestito.</span><span class="sxs-lookup"><span data-stu-id="ed0a7-107">[out] A Boolean value that indicates whether the assembly is managed.</span></span>  
  
 `pwzFrameworkAssemblyIdentity`  
 <span data-ttu-id="ed0a7-108">[in] Una stringa in formato non canonico che contiene l'identità univoca dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="ed0a7-108">[in] An uncanonicalized string that contains the unique identity of the assembly.</span></span>  
  
 `pccSize`  
 <span data-ttu-id="ed0a7-109">[in] Le dimensioni di `pwzFrameworkAssemblyIdentity`.</span><span class="sxs-lookup"><span data-stu-id="ed0a7-109">[in] The size of `pwzFrameworkAssemblyIdentity`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ed0a7-110">Note</span><span class="sxs-lookup"><span data-stu-id="ed0a7-110">Remarks</span></span>  
 <span data-ttu-id="ed0a7-111">Il `pwzAssemblyReference` parametro è un puntatore a una stringa di caratteri che contiene il nome di un assembly.</span><span class="sxs-lookup"><span data-stu-id="ed0a7-111">The `pwzAssemblyReference` parameter is a pointer to a character string that contains the name of an assembly.</span></span>  
  
 <span data-ttu-id="ed0a7-112">Se l'assembly fa parte di .NET Framework, il `pbIsFrameworkAssembly` parametro conterrà un valore booleano `true`.</span><span class="sxs-lookup"><span data-stu-id="ed0a7-112">If this assembly is part of the .NET Framework, the `pbIsFrameworkAssembly` parameter will contain a Boolean value of `true`.</span></span>  
  
 <span data-ttu-id="ed0a7-113">Se l'assembly denominato non fa parte di .NET Framework o se il `pwzAssemblyReference` parametro non corrisponde a un assembly, `pbIsFrameworkAssembly` conterrà un valore booleano `false`.</span><span class="sxs-lookup"><span data-stu-id="ed0a7-113">If the named assembly is not part of the .NET Framework, or if the `pwzAssemblyReference` parameter does not name an assembly, `pbIsFrameworkAssembly` will contain a Boolean value of `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ed0a7-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ed0a7-114">Requirements</span></span>  
 <span data-ttu-id="ed0a7-115">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ed0a7-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed0a7-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ed0a7-116">See Also</span></span>  
 [<span data-ttu-id="ed0a7-117">Funzioni statiche globali Fusion</span><span class="sxs-lookup"><span data-stu-id="ed0a7-117">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)

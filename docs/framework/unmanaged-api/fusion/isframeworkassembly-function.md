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
ms.openlocfilehash: 269e3702c21532f377735ba6087abb1603dde4f7
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796323"
---
# <a name="isframeworkassembly-function"></a><span data-ttu-id="956f7-102">Funzione IsFrameworkAssembly</span><span class="sxs-lookup"><span data-stu-id="956f7-102">IsFrameworkAssembly Function</span></span>
<span data-ttu-id="956f7-103">Ottiene un valore che indica se l'assembly specificato è gestito.</span><span class="sxs-lookup"><span data-stu-id="956f7-103">Gets a value that indicates whether the specified assembly is managed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="956f7-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="956f7-104">Syntax</span></span>  
  
```cpp  
HRESULT IsFrameworkAssembly (  
    [in]  LPCWSTR pwzAssemblyReference,  
    [out] LPBOOL  pbIsFrameworkAssembly,  
    [in]  LPWSTR  pwzFrameworkAssemblyIdentity,  
    [in]  LPDWORD pccSize  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="956f7-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="956f7-105">Parameters</span></span>  
 `pwzAssemblyReference`  
 <span data-ttu-id="956f7-106">in Nome dell'assembly da verificare.</span><span class="sxs-lookup"><span data-stu-id="956f7-106">[in] The name of the assembly to check.</span></span>  
  
 `pbIsFrameworkAssembly`  
 <span data-ttu-id="956f7-107">out Valore booleano che indica se l'assembly è gestito.</span><span class="sxs-lookup"><span data-stu-id="956f7-107">[out] A Boolean value that indicates whether the assembly is managed.</span></span>  
  
 `pwzFrameworkAssemblyIdentity`  
 <span data-ttu-id="956f7-108">in Stringa non canonica che contiene l'identità univoca dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="956f7-108">[in] An uncanonicalized string that contains the unique identity of the assembly.</span></span>  
  
 `pccSize`  
 <span data-ttu-id="956f7-109">[in] Le dimensioni di `pwzFrameworkAssemblyIdentity`.</span><span class="sxs-lookup"><span data-stu-id="956f7-109">[in] The size of `pwzFrameworkAssemblyIdentity`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="956f7-110">Note</span><span class="sxs-lookup"><span data-stu-id="956f7-110">Remarks</span></span>  
 <span data-ttu-id="956f7-111">Il `pwzAssemblyReference` parametro è un puntatore a una stringa di caratteri che contiene il nome di un assembly.</span><span class="sxs-lookup"><span data-stu-id="956f7-111">The `pwzAssemblyReference` parameter is a pointer to a character string that contains the name of an assembly.</span></span>  
  
 <span data-ttu-id="956f7-112">Se questo assembly fa parte dell'.NET Framework, il `pbIsFrameworkAssembly` parametro conterrà un valore booleano pari `true`a.</span><span class="sxs-lookup"><span data-stu-id="956f7-112">If this assembly is part of the .NET Framework, the `pbIsFrameworkAssembly` parameter will contain a Boolean value of `true`.</span></span>  
  
 <span data-ttu-id="956f7-113">Se l'assembly denominato non fa parte dell'.NET Framework o se il `pwzAssemblyReference` parametro non specifica un nome di assembly, `pbIsFrameworkAssembly` conterrà un valore booleano pari `false`a.</span><span class="sxs-lookup"><span data-stu-id="956f7-113">If the named assembly is not part of the .NET Framework, or if the `pwzAssemblyReference` parameter does not name an assembly, `pbIsFrameworkAssembly` will contain a Boolean value of `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="956f7-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="956f7-114">Requirements</span></span>  
 <span data-ttu-id="956f7-115">**Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="956f7-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="956f7-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="956f7-116">See also</span></span>

- [<span data-ttu-id="956f7-117">Funzioni statiche globali Fusion</span><span class="sxs-lookup"><span data-stu-id="956f7-117">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)

---
title: Metodo EmitAssemblyCustomAttribute
ms.date: 03/30/2017
api_name:
- IALink.EmitAssemblyCustomAttribute
- EmitAssemblyCustomAttribute
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EmitAssemblyCustomAttribute
helpviewer_keywords:
- EmitAssemblyCustomAttribute method
ms.assetid: b72f5409-79af-4fa7-90a7-7630eec170f1
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 67073f04cfe981dd383369029d9a4b436929a0a6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61790026"
---
# <a name="emitassemblycustomattribute-method"></a><span data-ttu-id="bfd92-102">Metodo EmitAssemblyCustomAttribute</span><span class="sxs-lookup"><span data-stu-id="bfd92-102">EmitAssemblyCustomAttribute Method</span></span>
<span data-ttu-id="bfd92-103">Chiamata per impostare gli attributi personalizzati a livello di assembly.</span><span class="sxs-lookup"><span data-stu-id="bfd92-103">Call to set assembly-level custom attributes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bfd92-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bfd92-104">Syntax</span></span>  
  
```  
HRESULT EmitAssemblyCustomAttribute(  
    mdAssembly   AssemblyID,  
    mdToken      FileToken,  
    mdToken      tkType,  
    void const*  pCustomValue,  
    DWORD        cbCustomValue,  
    BOOL         bSecurity,  
    BOOL         bAllowMulti  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="bfd92-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="bfd92-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="bfd92-106">ID dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="bfd92-106">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="bfd92-107">File che definisce l'attributo.</span><span class="sxs-lookup"><span data-stu-id="bfd92-107">File that defiles the attribute.</span></span> <span data-ttu-id="bfd92-108">Può essere NULL se `AssemblyID` non indica un netmodule non associato.</span><span class="sxs-lookup"><span data-stu-id="bfd92-108">Can be NULL if `AssemblyID` does not indicate an unbound netmodule.</span></span>  
  
 `tkType`  
 <span data-ttu-id="bfd92-109">Tipo dell'attributo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="bfd92-109">Type of the custom attribute.</span></span>  
  
 `pCustomValue`  
 <span data-ttu-id="bfd92-110">Dati valore personalizzato.</span><span class="sxs-lookup"><span data-stu-id="bfd92-110">Custom value data.</span></span>  
  
 `cbCustomValue`  
 <span data-ttu-id="bfd92-111">Lunghezza dei dati di valore personalizzato.</span><span class="sxs-lookup"><span data-stu-id="bfd92-111">Length of custom value data.</span></span>  
  
 `bSecurity`  
 <span data-ttu-id="bfd92-112">TRUE se l'attributo personalizzato è correlata alla firma dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="bfd92-112">TRUE if the custom attribute is related to assembly signing.</span></span>  
  
 `bAllowMulti`  
 <span data-ttu-id="bfd92-113">TRUE se devono essere emesse più attributi.</span><span class="sxs-lookup"><span data-stu-id="bfd92-113">TRUE if multiple attributes are to be emitted.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bfd92-114">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="bfd92-114">Return Value</span></span>  
 <span data-ttu-id="bfd92-115">Restituisce S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="bfd92-115">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bfd92-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="bfd92-116">Requirements</span></span>  
 <span data-ttu-id="bfd92-117">Richiede alink.h</span><span class="sxs-lookup"><span data-stu-id="bfd92-117">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bfd92-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bfd92-118">See also</span></span>

- [<span data-ttu-id="bfd92-119">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="bfd92-119">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="bfd92-120">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="bfd92-120">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="bfd92-121">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="bfd92-121">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)

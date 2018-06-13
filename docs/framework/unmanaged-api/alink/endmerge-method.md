---
title: Metodo EndMerge
ms.date: 03/30/2017
api_name:
- IALink.EndMerge
- EndMerge
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EndMerge
helpviewer_keywords:
- EndMerge method
ms.assetid: 1d03bb15-a2c8-4a04-8fc6-b126c89c3778
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e8f9eecd6d6d74717eb7c1e389bfa24e40afc950
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33402574"
---
# <a name="endmerge-method"></a><span data-ttu-id="11ce2-102">Metodo EndMerge</span><span class="sxs-lookup"><span data-stu-id="11ce2-102">EndMerge Method</span></span>
<span data-ttu-id="11ce2-103">Indica che tutti gli attributi personalizzati sono stati uniti nell'ambito di emissione.</span><span class="sxs-lookup"><span data-stu-id="11ce2-103">Indicates that all custom attributes have been merged into the emit scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11ce2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="11ce2-104">Syntax</span></span>  
  
```  
HRESULT EndMerge(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="11ce2-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="11ce2-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="11ce2-106">ID dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="11ce2-106">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="11ce2-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="11ce2-107">Return Value</span></span>  
 <span data-ttu-id="11ce2-108">Se il metodo ha esito positivo, restituisce S_OK.</span><span class="sxs-lookup"><span data-stu-id="11ce2-108">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="11ce2-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="11ce2-109">Requirements</span></span>  
 <span data-ttu-id="11ce2-110">Richiede alink.h</span><span class="sxs-lookup"><span data-stu-id="11ce2-110">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11ce2-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="11ce2-111">See Also</span></span>  
 [<span data-ttu-id="11ce2-112">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="11ce2-112">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="11ce2-113">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="11ce2-113">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="11ce2-114">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="11ce2-114">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)

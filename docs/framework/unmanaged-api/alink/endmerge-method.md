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
ms.openlocfilehash: 88f594117fffedb6acafef26a9e834dd951ea5bb
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70787537"
---
# <a name="endmerge-method"></a><span data-ttu-id="fc8d0-102">Metodo EndMerge</span><span class="sxs-lookup"><span data-stu-id="fc8d0-102">EndMerge Method</span></span>
<span data-ttu-id="fc8d0-103">Indica che tutti gli attributi personalizzati sono Stati Uniti nell'ambito di emissione.</span><span class="sxs-lookup"><span data-stu-id="fc8d0-103">Indicates that all custom attributes have been merged into the emit scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc8d0-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fc8d0-104">Syntax</span></span>  
  
```cpp  
HRESULT EndMerge(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="fc8d0-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="fc8d0-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="fc8d0-106">ID dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="fc8d0-106">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fc8d0-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="fc8d0-107">Return Value</span></span>  
 <span data-ttu-id="fc8d0-108">Restituisce S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="fc8d0-108">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fc8d0-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="fc8d0-109">Requirements</span></span>  
 <span data-ttu-id="fc8d0-110">Richiede ALink. h</span><span class="sxs-lookup"><span data-stu-id="fc8d0-110">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc8d0-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fc8d0-111">See also</span></span>

- [<span data-ttu-id="fc8d0-112">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="fc8d0-112">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="fc8d0-113">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="fc8d0-113">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="fc8d0-114">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="fc8d0-114">ALink API</span></span>](index.md)

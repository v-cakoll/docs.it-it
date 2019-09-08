---
title: Metodo EmitInternalExportedTypes
ms.date: 03/30/2017
api_name:
- EmitInternalExportedTypes
- IALink2.EmitInternalExportedTypes
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EmitInternalExportedTypes
helpviewer_keywords:
- EmitInternalExportedTypes method
ms.assetid: 28c8b00d-2c14-40b4-aed5-a1db0e2428eb
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 04103ad305e0ae97669f3e07e06f03c2cdb4dfbd
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70787516"
---
# <a name="emitinternalexportedtypes-method"></a><span data-ttu-id="64748-102">Metodo EmitInternalExportedTypes</span><span class="sxs-lookup"><span data-stu-id="64748-102">EmitInternalExportedTypes Method</span></span>
<span data-ttu-id="64748-103">Genera tipi aggiunti all'assembly.</span><span class="sxs-lookup"><span data-stu-id="64748-103">Emits types added to the assembly.</span></span> <span data-ttu-id="64748-104">Chiamare questo metodo dopo che sono stati aggiunti tipi interni noti.</span><span class="sxs-lookup"><span data-stu-id="64748-104">Call this method after known internal types have been added.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="64748-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="64748-105">Syntax</span></span>  
  
```cpp  
HRESULT EmitInternalExportedTypes(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="64748-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="64748-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="64748-107">ID dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="64748-107">ID of assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="64748-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="64748-108">Return Value</span></span>  
 <span data-ttu-id="64748-109">Restituisce S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="64748-109">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="64748-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="64748-110">Requirements</span></span>  
 <span data-ttu-id="64748-111">Richiede ALink. h</span><span class="sxs-lookup"><span data-stu-id="64748-111">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64748-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="64748-112">See also</span></span>

- [<span data-ttu-id="64748-113">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="64748-113">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="64748-114">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="64748-114">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="64748-115">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="64748-115">ALink API</span></span>](index.md)

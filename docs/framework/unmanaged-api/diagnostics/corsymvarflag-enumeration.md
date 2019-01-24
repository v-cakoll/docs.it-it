---
title: Enumerazione CorSymVarFlag
ms.date: 03/30/2017
api_name:
- CorSymVarFlag
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorSymVarFlag
helpviewer_keywords:
- CorSymVarFlag enumeration [.NET Framework debugging]
ms.assetid: c3f7d307-4047-4f9a-be8c-f152fca42fd0
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 50367358ba5bcf335f8cc2ca3222f6cf7ea2ff70
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54670135"
---
# <a name="corsymvarflag-enumeration"></a><span data-ttu-id="63312-102">Enumerazione CorSymVarFlag</span><span class="sxs-lookup"><span data-stu-id="63312-102">CorSymVarFlag Enumeration</span></span>
<span data-ttu-id="63312-103">Indica se una variabile è generato dal compilatore.</span><span class="sxs-lookup"><span data-stu-id="63312-103">Indicates whether a variable is compiler-generated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63312-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="63312-104">Syntax</span></span>  
  
```  
typedef enum CorSymVarFlag   
{  
    VAR_IS_COMP_GEN = 1  
} CorSymVarFlag;  
```  
  
## <a name="members"></a><span data-ttu-id="63312-105">Membri</span><span class="sxs-lookup"><span data-stu-id="63312-105">Members</span></span>  
  
|<span data-ttu-id="63312-106">Membro</span><span class="sxs-lookup"><span data-stu-id="63312-106">Member</span></span>|<span data-ttu-id="63312-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="63312-107">Description</span></span>|  
|------------|-----------------|  
|`VAR_IS_COMP_GEN`|<span data-ttu-id="63312-108">Indica che la variabile specificata è generato dal compilatore.</span><span class="sxs-lookup"><span data-stu-id="63312-108">Indicates that the given variable is compiler-generated.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="63312-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="63312-109">Requirements</span></span>  
 <span data-ttu-id="63312-110">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="63312-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63312-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="63312-111">See also</span></span>
- [<span data-ttu-id="63312-112">Enumerazioni dell'archivio simboli di diagnostica</span><span class="sxs-lookup"><span data-stu-id="63312-112">Diagnostics Symbol Store Enumerations</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-enumerations.md)

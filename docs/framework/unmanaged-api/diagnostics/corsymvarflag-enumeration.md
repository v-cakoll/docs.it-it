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
ms.openlocfilehash: 0c797378f5e13f39c1c786237a3a7b9cf577fccc
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61763650"
---
# <a name="corsymvarflag-enumeration"></a><span data-ttu-id="40458-102">Enumerazione CorSymVarFlag</span><span class="sxs-lookup"><span data-stu-id="40458-102">CorSymVarFlag Enumeration</span></span>
<span data-ttu-id="40458-103">Indica se una variabile è generato dal compilatore.</span><span class="sxs-lookup"><span data-stu-id="40458-103">Indicates whether a variable is compiler-generated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40458-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="40458-104">Syntax</span></span>  
  
```  
typedef enum CorSymVarFlag   
{  
    VAR_IS_COMP_GEN = 1  
} CorSymVarFlag;  
```  
  
## <a name="members"></a><span data-ttu-id="40458-105">Membri</span><span class="sxs-lookup"><span data-stu-id="40458-105">Members</span></span>  
  
|<span data-ttu-id="40458-106">Member</span><span class="sxs-lookup"><span data-stu-id="40458-106">Member</span></span>|<span data-ttu-id="40458-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="40458-107">Description</span></span>|  
|------------|-----------------|  
|`VAR_IS_COMP_GEN`|<span data-ttu-id="40458-108">Indica che la variabile specificata è generato dal compilatore.</span><span class="sxs-lookup"><span data-stu-id="40458-108">Indicates that the given variable is compiler-generated.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="40458-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="40458-109">Requirements</span></span>  
 <span data-ttu-id="40458-110">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="40458-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40458-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="40458-111">See also</span></span>

- [<span data-ttu-id="40458-112">Enumerazioni dell'archivio simboli di diagnostica</span><span class="sxs-lookup"><span data-stu-id="40458-112">Diagnostics Symbol Store Enumerations</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-enumerations.md)

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
ms.openlocfilehash: a6a9c5ff91989fc1ad7da4e23df0e80d9d74ec7c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33424976"
---
# <a name="corsymvarflag-enumeration"></a><span data-ttu-id="1f615-102">Enumerazione CorSymVarFlag</span><span class="sxs-lookup"><span data-stu-id="1f615-102">CorSymVarFlag Enumeration</span></span>
<span data-ttu-id="1f615-103">Indica se una variabile è generato dal compilatore.</span><span class="sxs-lookup"><span data-stu-id="1f615-103">Indicates whether a variable is compiler-generated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1f615-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1f615-104">Syntax</span></span>  
  
```  
typedef enum CorSymVarFlag   
{  
    VAR_IS_COMP_GEN = 1  
} CorSymVarFlag;  
```  
  
## <a name="members"></a><span data-ttu-id="1f615-105">Membri</span><span class="sxs-lookup"><span data-stu-id="1f615-105">Members</span></span>  
  
|<span data-ttu-id="1f615-106">Membro</span><span class="sxs-lookup"><span data-stu-id="1f615-106">Member</span></span>|<span data-ttu-id="1f615-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1f615-107">Description</span></span>|  
|------------|-----------------|  
|`VAR_IS_COMP_GEN`|<span data-ttu-id="1f615-108">Indica che la variabile specificata viene generato dal compilatore.</span><span class="sxs-lookup"><span data-stu-id="1f615-108">Indicates that the given variable is compiler-generated.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1f615-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1f615-109">Requirements</span></span>  
 <span data-ttu-id="1f615-110">**Intestazione:** CorSym. idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="1f615-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f615-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1f615-111">See Also</span></span>  
 [<span data-ttu-id="1f615-112">Enumerazioni dell'archivio simboli di diagnostica</span><span class="sxs-lookup"><span data-stu-id="1f615-112">Diagnostics Symbol Store Enumerations</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-enumerations.md)

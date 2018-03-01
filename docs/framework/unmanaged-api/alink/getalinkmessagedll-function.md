---
title: Funzione GetALinkMessageDll
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- GetALinkMessageDll
api_location:
- alink.dll
api_type:
- DLLExport
f1_keywords:
- GetALinkMessageDll
helpviewer_keywords:
- Alink API, GetALinkMessageDll function
- GetALinkMessageDll function
ms.assetid: 67985a22-88a2-4c54-8d99-4bcde9d6213e
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 16657c62d66db1570ad379ff5d42a75aaf3ea2a7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="getalinkmessagedll-function"></a><span data-ttu-id="72f7f-102">Funzione GetALinkMessageDll</span><span class="sxs-lookup"><span data-stu-id="72f7f-102">GetALinkMessageDll Function</span></span>
<span data-ttu-id="72f7f-103">Trova e carica la DLL dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="72f7f-103">Finds and loads the message DLL.</span></span> <span data-ttu-id="72f7f-104">Restituisce 0 se la DLL dei messaggi non è stato disponibile o non caricato.</span><span class="sxs-lookup"><span data-stu-id="72f7f-104">Returns 0 if the message DLL could not be located or loaded.</span></span> <span data-ttu-id="72f7f-105">La DLL dei messaggi deve essere in una sottodirectory il cui nome è un ID di lingua o nella directory corrente.</span><span class="sxs-lookup"><span data-stu-id="72f7f-105">The message DLL should be either in a subdirectory whose name is a language ID, or in the current directory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72f7f-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="72f7f-106">Syntax</span></span>  
  
```  
HINSTANCE WINAPI GetALinkMessageDll();  
```  
  
## <a name="requirements"></a><span data-ttu-id="72f7f-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="72f7f-107">Requirements</span></span>  
 <span data-ttu-id="72f7f-108">**Intestazione:** alink.h</span><span class="sxs-lookup"><span data-stu-id="72f7f-108">**Header:** alink.h</span></span>  
  
 <span data-ttu-id="72f7f-109">**Libreria**: alink.dll</span><span class="sxs-lookup"><span data-stu-id="72f7f-109">**Library**: alink.dll</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72f7f-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="72f7f-110">See Also</span></span>  
 [<span data-ttu-id="72f7f-111">Al.exe (Assembly Linker)</span><span class="sxs-lookup"><span data-stu-id="72f7f-111">Al.exe (Assembly Linker)</span></span>](../../../../docs/framework/tools/al-exe-assembly-linker.md)

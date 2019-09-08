---
title: Funzione GetALinkMessageDll
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 323e53c45a26d5703548ebe9863978f6d3929f0b
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70787470"
---
# <a name="getalinkmessagedll-function"></a><span data-ttu-id="84e8f-102">Funzione GetALinkMessageDll</span><span class="sxs-lookup"><span data-stu-id="84e8f-102">GetALinkMessageDll Function</span></span>
<span data-ttu-id="84e8f-103">Trova e carica la DLL del messaggio.</span><span class="sxs-lookup"><span data-stu-id="84e8f-103">Finds and loads the message DLL.</span></span> <span data-ttu-id="84e8f-104">Restituisce 0 se non è stato possibile trovare o caricare la DLL del messaggio.</span><span class="sxs-lookup"><span data-stu-id="84e8f-104">Returns 0 if the message DLL could not be located or loaded.</span></span> <span data-ttu-id="84e8f-105">La DLL del messaggio deve trovarsi in una sottodirectory il cui nome è un ID lingua o nella directory corrente.</span><span class="sxs-lookup"><span data-stu-id="84e8f-105">The message DLL should be either in a subdirectory whose name is a language ID, or in the current directory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84e8f-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="84e8f-106">Syntax</span></span>  
  
```cpp  
HINSTANCE WINAPI GetALinkMessageDll();  
```  
  
## <a name="requirements"></a><span data-ttu-id="84e8f-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="84e8f-107">Requirements</span></span>  
 <span data-ttu-id="84e8f-108">**Intestazione:** ALink. h</span><span class="sxs-lookup"><span data-stu-id="84e8f-108">**Header:** alink.h</span></span>  
  
 <span data-ttu-id="84e8f-109">**Libreria**: ALink. dll</span><span class="sxs-lookup"><span data-stu-id="84e8f-109">**Library**: alink.dll</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84e8f-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="84e8f-110">See also</span></span>

- [<span data-ttu-id="84e8f-111">Al.exe (Assembly Linker)</span><span class="sxs-lookup"><span data-stu-id="84e8f-111">Al.exe (Assembly Linker)</span></span>](../../tools/al-exe-assembly-linker.md)

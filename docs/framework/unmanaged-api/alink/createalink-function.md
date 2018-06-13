---
title: Funzione CreateALink
ms.date: 03/30/2017
api_name:
- CreateALink
api_location:
- alink.dll
api_type:
- DLLExport
f1_keywords:
- CreateALink
helpviewer_keywords:
- CreateALink function
- Alink API, CreateALink function
ms.assetid: fc73bcb9-6af6-44d8-bc39-2f4400325dae
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1e29c9c246649229900beba2fcc9ab482071ae46
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33400666"
---
# <a name="createalink-function"></a><span data-ttu-id="039c9-102">Funzione CreateALink</span><span class="sxs-lookup"><span data-stu-id="039c9-102">CreateALink Function</span></span>
<span data-ttu-id="039c9-103">Crea un'istanza dell'Assembly Linker e imposta un puntatore a interfaccia specificato.</span><span class="sxs-lookup"><span data-stu-id="039c9-103">Creates an instance of the Assembly Linker and sets a pointer to the specified interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="039c9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="039c9-104">Syntax</span></span>  
  
```  
HRESULT CreateALink (  
   REFIID riid,  
   IUnknown **ppInterface  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="039c9-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="039c9-105">Parameters</span></span>  
  
|<span data-ttu-id="039c9-106">Parametro</span><span class="sxs-lookup"><span data-stu-id="039c9-106">Parameter</span></span>|<span data-ttu-id="039c9-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="039c9-107">Description</span></span>|  
|---------------|-----------------|  
|`riid`|<span data-ttu-id="039c9-108">Il nome fisico di una delle interfacce di Assembly Linker.</span><span class="sxs-lookup"><span data-stu-id="039c9-108">The physical name of one of the Assembly Linker interfaces.</span></span>|  
|`ppInterface`|<span data-ttu-id="039c9-109">Il percorso che al termine dell'esecuzione contiene un puntatore per il `riid` interfaccia.</span><span class="sxs-lookup"><span data-stu-id="039c9-109">The location that on successful completion contains a pointer to the `riid` interface.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="039c9-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="039c9-110">Requirements</span></span>  
 <span data-ttu-id="039c9-111">**Libreria**: ALink. dll</span><span class="sxs-lookup"><span data-stu-id="039c9-111">**Library**: alink.dll</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="039c9-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="039c9-112">See Also</span></span>  
 [<span data-ttu-id="039c9-113">Al.exe (Assembly Linker)</span><span class="sxs-lookup"><span data-stu-id="039c9-113">Al.exe (Assembly Linker)</span></span>](../../../../docs/framework/tools/al-exe-assembly-linker.md)

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
ms.openlocfilehash: 24f7e2d5a547b78ceb4808feaf581c6f49807cf7
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70787626"
---
# <a name="createalink-function"></a><span data-ttu-id="76f97-102">Funzione CreateALink</span><span class="sxs-lookup"><span data-stu-id="76f97-102">CreateALink Function</span></span>
<span data-ttu-id="76f97-103">Crea un'istanza dell'assembly linker e imposta un puntatore sull'interfaccia specificata.</span><span class="sxs-lookup"><span data-stu-id="76f97-103">Creates an instance of the Assembly Linker and sets a pointer to the specified interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="76f97-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="76f97-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateALink (  
   REFIID riid,  
   IUnknown **ppInterface  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="76f97-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="76f97-105">Parameters</span></span>  
  
|<span data-ttu-id="76f97-106">Parametro</span><span class="sxs-lookup"><span data-stu-id="76f97-106">Parameter</span></span>|<span data-ttu-id="76f97-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="76f97-107">Description</span></span>|  
|---------------|-----------------|  
|`riid`|<span data-ttu-id="76f97-108">Nome fisico di una delle interfacce di assembly linker.</span><span class="sxs-lookup"><span data-stu-id="76f97-108">The physical name of one of the Assembly Linker interfaces.</span></span>|  
|`ppInterface`|<span data-ttu-id="76f97-109">La posizione in cui è stato completato il completamento contiene un `riid` puntatore all'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="76f97-109">The location that on successful completion contains a pointer to the `riid` interface.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="76f97-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="76f97-110">Requirements</span></span>  
 <span data-ttu-id="76f97-111">**Libreria**: ALink. dll</span><span class="sxs-lookup"><span data-stu-id="76f97-111">**Library**: alink.dll</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76f97-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="76f97-112">See also</span></span>

- [<span data-ttu-id="76f97-113">Al.exe (Assembly Linker)</span><span class="sxs-lookup"><span data-stu-id="76f97-113">Al.exe (Assembly Linker)</span></span>](../../tools/al-exe-assembly-linker.md)

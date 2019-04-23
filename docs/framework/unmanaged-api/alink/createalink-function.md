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
ms.openlocfilehash: b494b8b776f4cb0eb534233c5a03ab2d34a698ef
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59115622"
---
# <a name="createalink-function"></a><span data-ttu-id="14dcd-102">Funzione CreateALink</span><span class="sxs-lookup"><span data-stu-id="14dcd-102">CreateALink Function</span></span>
<span data-ttu-id="14dcd-103">Crea un'istanza dell'Assembly Linker e imposta un puntatore all'interfaccia specificata.</span><span class="sxs-lookup"><span data-stu-id="14dcd-103">Creates an instance of the Assembly Linker and sets a pointer to the specified interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="14dcd-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="14dcd-104">Syntax</span></span>  
  
```  
HRESULT CreateALink (  
   REFIID riid,  
   IUnknown **ppInterface  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="14dcd-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="14dcd-105">Parameters</span></span>  
  
|<span data-ttu-id="14dcd-106">Parametro</span><span class="sxs-lookup"><span data-stu-id="14dcd-106">Parameter</span></span>|<span data-ttu-id="14dcd-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="14dcd-107">Description</span></span>|  
|---------------|-----------------|  
|`riid`|<span data-ttu-id="14dcd-108">Il nome fisico di una delle interfacce Assembly Linker.</span><span class="sxs-lookup"><span data-stu-id="14dcd-108">The physical name of one of the Assembly Linker interfaces.</span></span>|  
|`ppInterface`|<span data-ttu-id="14dcd-109">Il percorso che, al termine dell'esecuzione, contiene un puntatore al `riid` interfaccia.</span><span class="sxs-lookup"><span data-stu-id="14dcd-109">The location that on successful completion contains a pointer to the `riid` interface.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="14dcd-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="14dcd-110">Requirements</span></span>  
 <span data-ttu-id="14dcd-111">**Libreria**: ALink. dll</span><span class="sxs-lookup"><span data-stu-id="14dcd-111">**Library**: alink.dll</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14dcd-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="14dcd-112">See also</span></span>

- [<span data-ttu-id="14dcd-113">Al.exe (Assembly Linker)</span><span class="sxs-lookup"><span data-stu-id="14dcd-113">Al.exe (Assembly Linker)</span></span>](../../../../docs/framework/tools/al-exe-assembly-linker.md)

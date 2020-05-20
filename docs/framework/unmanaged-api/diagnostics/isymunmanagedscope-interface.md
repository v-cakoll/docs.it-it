---
title: Interfaccia ISymUnmanagedScope
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope
helpviewer_keywords:
- ISymUnmanagedScope interface [.NET Framework debugging]
ms.assetid: 3db7a220-cfe9-4810-8ca8-a094bb8e0f5b
topic_type:
- apiref
ms.openlocfilehash: 1ee406c97fa4ccb7f87098cba2925568d8ce069f
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615345"
---
# <a name="isymunmanagedscope-interface"></a><span data-ttu-id="0e7d3-102">Interfaccia ISymUnmanagedScope</span><span class="sxs-lookup"><span data-stu-id="0e7d3-102">ISymUnmanagedScope Interface</span></span>
<span data-ttu-id="0e7d3-103">Rappresenta un ambito lessicale all'interno di un metodo.</span><span class="sxs-lookup"><span data-stu-id="0e7d3-103">Represents a lexical scope within a method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0e7d3-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="0e7d3-104">Methods</span></span>  
  
|<span data-ttu-id="0e7d3-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="0e7d3-105">Method</span></span>|<span data-ttu-id="0e7d3-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0e7d3-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0e7d3-107">Metodo GetChildren</span><span class="sxs-lookup"><span data-stu-id="0e7d3-107">GetChildren Method</span></span>](isymunmanagedscope-getchildren-method.md)|<span data-ttu-id="0e7d3-108">Ottiene gli elementi figlio di questo ambito.</span><span class="sxs-lookup"><span data-stu-id="0e7d3-108">Gets the children of this scope.</span></span>|  
|[<span data-ttu-id="0e7d3-109">Metodo GetEndOffset</span><span class="sxs-lookup"><span data-stu-id="0e7d3-109">GetEndOffset Method</span></span>](isymunmanagedscope-getendoffset-method.md)|<span data-ttu-id="0e7d3-110">Ottiene l'offset finale per questo ambito.</span><span class="sxs-lookup"><span data-stu-id="0e7d3-110">Gets the end offset for this scope.</span></span>|  
|[<span data-ttu-id="0e7d3-111">Metodo GetLocalCount</span><span class="sxs-lookup"><span data-stu-id="0e7d3-111">GetLocalCount Method</span></span>](isymunmanagedscope-getlocalcount-method.md)|<span data-ttu-id="0e7d3-112">Ottiene un conteggio delle variabili locali definite in questo ambito.</span><span class="sxs-lookup"><span data-stu-id="0e7d3-112">Gets a count of the local variables defined within this scope.</span></span>|  
|[<span data-ttu-id="0e7d3-113">Metodo GetLocals</span><span class="sxs-lookup"><span data-stu-id="0e7d3-113">GetLocals Method</span></span>](isymunmanagedscope-getlocals-method.md)|<span data-ttu-id="0e7d3-114">Ottiene le variabili locali definite in questo ambito.</span><span class="sxs-lookup"><span data-stu-id="0e7d3-114">Gets the local variables defined within this scope.</span></span>|  
|[<span data-ttu-id="0e7d3-115">Metodo GetMethod</span><span class="sxs-lookup"><span data-stu-id="0e7d3-115">GetMethod Method</span></span>](isymunmanagedscope-getmethod-method.md)|<span data-ttu-id="0e7d3-116">Ottiene il metodo che contiene questo ambito.</span><span class="sxs-lookup"><span data-stu-id="0e7d3-116">Gets the method that contains this scope.</span></span>|  
|[<span data-ttu-id="0e7d3-117">Metodo GetNamespaces</span><span class="sxs-lookup"><span data-stu-id="0e7d3-117">GetNamespaces Method</span></span>](isymunmanagedscope-getnamespaces-method.md)|<span data-ttu-id="0e7d3-118">Ottiene gli spazi dei nomi utilizzati all'interno di questo ambito.</span><span class="sxs-lookup"><span data-stu-id="0e7d3-118">Gets the namespaces that are being used within this scope.</span></span>|  
|[<span data-ttu-id="0e7d3-119">Metodo GetParent</span><span class="sxs-lookup"><span data-stu-id="0e7d3-119">GetParent Method</span></span>](isymunmanagedscope-getparent-method.md)|<span data-ttu-id="0e7d3-120">Ottiene l'ambito padre di questo ambito.</span><span class="sxs-lookup"><span data-stu-id="0e7d3-120">Gets the parent scope of this scope.</span></span>|  
|[<span data-ttu-id="0e7d3-121">Metodo GetStartOffset</span><span class="sxs-lookup"><span data-stu-id="0e7d3-121">GetStartOffset Method</span></span>](isymunmanagedscope-getstartoffset-method.md)|<span data-ttu-id="0e7d3-122">Ottiene l'offset iniziale per questo ambito.</span><span class="sxs-lookup"><span data-stu-id="0e7d3-122">Gets the start offset for this scope.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0e7d3-123">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0e7d3-123">Requirements</span></span>  
 <span data-ttu-id="0e7d3-124">**Intestazione:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="0e7d3-124">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e7d3-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0e7d3-125">See also</span></span>

- [<span data-ttu-id="0e7d3-126">Interfacce dell'archivio dei simboli di diagnostica</span><span class="sxs-lookup"><span data-stu-id="0e7d3-126">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="0e7d3-127">Interfaccia ISymUnmanagedScope2</span><span class="sxs-lookup"><span data-stu-id="0e7d3-127">ISymUnmanagedScope2 Interface</span></span>](isymunmanagedscope2-interface.md)

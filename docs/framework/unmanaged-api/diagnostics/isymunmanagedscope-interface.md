---
title: Interfaccia ISymUnmanagedScope
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedScope
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedScope
helpviewer_keywords: ISymUnmanagedScope interface [.NET Framework debugging]
ms.assetid: 3db7a220-cfe9-4810-8ca8-a094bb8e0f5b
topic_type: apiref
caps.latest.revision: "5"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: d25d62dd42e3e93124c9a3bd8945be265f192663
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="isymunmanagedscope-interface"></a><span data-ttu-id="7d38c-102">Interfaccia ISymUnmanagedScope</span><span class="sxs-lookup"><span data-stu-id="7d38c-102">ISymUnmanagedScope Interface</span></span>
<span data-ttu-id="7d38c-103">Rappresenta un ambito lessicale in un metodo.</span><span class="sxs-lookup"><span data-stu-id="7d38c-103">Represents a lexical scope within a method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7d38c-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="7d38c-104">Methods</span></span>  
  
|<span data-ttu-id="7d38c-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="7d38c-105">Method</span></span>|<span data-ttu-id="7d38c-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7d38c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7d38c-107">GetChildren (metodo)</span><span class="sxs-lookup"><span data-stu-id="7d38c-107">GetChildren Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getchildren-method.md)|<span data-ttu-id="7d38c-108">Ottiene gli elementi figlio di questo ambito.</span><span class="sxs-lookup"><span data-stu-id="7d38c-108">Gets the children of this scope.</span></span>|  
|[<span data-ttu-id="7d38c-109">GetEndOffset (metodo)</span><span class="sxs-lookup"><span data-stu-id="7d38c-109">GetEndOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getendoffset-method.md)|<span data-ttu-id="7d38c-110">Ottiene l'offset finale per questo ambito.</span><span class="sxs-lookup"><span data-stu-id="7d38c-110">Gets the end offset for this scope.</span></span>|  
|[<span data-ttu-id="7d38c-111">GetLocalCount (metodo)</span><span class="sxs-lookup"><span data-stu-id="7d38c-111">GetLocalCount Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getlocalcount-method.md)|<span data-ttu-id="7d38c-112">Ottiene un conteggio delle variabili locali definite all'interno di questo ambito.</span><span class="sxs-lookup"><span data-stu-id="7d38c-112">Gets a count of the local variables defined within this scope.</span></span>|  
|[<span data-ttu-id="7d38c-113">GetLocals (metodo)</span><span class="sxs-lookup"><span data-stu-id="7d38c-113">GetLocals Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getlocals-method.md)|<span data-ttu-id="7d38c-114">Ottiene le variabili locali definite in questo ambito.</span><span class="sxs-lookup"><span data-stu-id="7d38c-114">Gets the local variables defined within this scope.</span></span>|  
|[<span data-ttu-id="7d38c-115">GetMethod (metodo)</span><span class="sxs-lookup"><span data-stu-id="7d38c-115">GetMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getmethod-method.md)|<span data-ttu-id="7d38c-116">Ottiene il metodo che contiene questo ambito.</span><span class="sxs-lookup"><span data-stu-id="7d38c-116">Gets the method that contains this scope.</span></span>|  
|[<span data-ttu-id="7d38c-117">GetNamespaces (metodo)</span><span class="sxs-lookup"><span data-stu-id="7d38c-117">GetNamespaces Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getnamespaces-method.md)|<span data-ttu-id="7d38c-118">Ottiene gli spazi dei nomi utilizzati in questo ambito.</span><span class="sxs-lookup"><span data-stu-id="7d38c-118">Gets the namespaces that are being used within this scope.</span></span>|  
|[<span data-ttu-id="7d38c-119">GetParent (metodo)</span><span class="sxs-lookup"><span data-stu-id="7d38c-119">GetParent Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getparent-method.md)|<span data-ttu-id="7d38c-120">Ottiene l'ambito padre di questo ambito.</span><span class="sxs-lookup"><span data-stu-id="7d38c-120">Gets the parent scope of this scope.</span></span>|  
|[<span data-ttu-id="7d38c-121">GetStartOffset (metodo)</span><span class="sxs-lookup"><span data-stu-id="7d38c-121">GetStartOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getstartoffset-method.md)|<span data-ttu-id="7d38c-122">Ottiene l'offset iniziale per questo ambito.</span><span class="sxs-lookup"><span data-stu-id="7d38c-122">Gets the start offset for this scope.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7d38c-123">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7d38c-123">Requirements</span></span>  
 <span data-ttu-id="7d38c-124">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="7d38c-124">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d38c-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7d38c-125">See Also</span></span>  
 [<span data-ttu-id="7d38c-126">Interfacce dell'archivio dei simboli di diagnostica</span><span class="sxs-lookup"><span data-stu-id="7d38c-126">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)  
 [<span data-ttu-id="7d38c-127">ISymUnmanagedScope2 (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="7d38c-127">ISymUnmanagedScope2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-interface.md)

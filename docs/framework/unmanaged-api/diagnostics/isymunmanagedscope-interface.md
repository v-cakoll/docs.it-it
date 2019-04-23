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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 809368ea19528a7ce00d4fcada06ef5724eb79a6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59228159"
---
# <a name="isymunmanagedscope-interface"></a><span data-ttu-id="388f7-102">Interfaccia ISymUnmanagedScope</span><span class="sxs-lookup"><span data-stu-id="388f7-102">ISymUnmanagedScope Interface</span></span>
<span data-ttu-id="388f7-103">Rappresenta un ambito lessicale in un metodo.</span><span class="sxs-lookup"><span data-stu-id="388f7-103">Represents a lexical scope within a method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="388f7-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="388f7-104">Methods</span></span>  
  
|<span data-ttu-id="388f7-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="388f7-105">Method</span></span>|<span data-ttu-id="388f7-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="388f7-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="388f7-107">Metodo GetChildren</span><span class="sxs-lookup"><span data-stu-id="388f7-107">GetChildren Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getchildren-method.md)|<span data-ttu-id="388f7-108">Ottiene gli elementi figlio di questo ambito.</span><span class="sxs-lookup"><span data-stu-id="388f7-108">Gets the children of this scope.</span></span>|  
|[<span data-ttu-id="388f7-109">Metodo GetEndOffset</span><span class="sxs-lookup"><span data-stu-id="388f7-109">GetEndOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getendoffset-method.md)|<span data-ttu-id="388f7-110">Ottiene l'offset finale per l'ambito corrente.</span><span class="sxs-lookup"><span data-stu-id="388f7-110">Gets the end offset for this scope.</span></span>|  
|[<span data-ttu-id="388f7-111">Metodo GetLocalCount</span><span class="sxs-lookup"><span data-stu-id="388f7-111">GetLocalCount Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getlocalcount-method.md)|<span data-ttu-id="388f7-112">Ottiene un conteggio delle variabili locali definite all'interno di questo ambito.</span><span class="sxs-lookup"><span data-stu-id="388f7-112">Gets a count of the local variables defined within this scope.</span></span>|  
|[<span data-ttu-id="388f7-113">Metodo GetLocals</span><span class="sxs-lookup"><span data-stu-id="388f7-113">GetLocals Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getlocals-method.md)|<span data-ttu-id="388f7-114">Ottiene le variabili locali definite all'interno di questo ambito.</span><span class="sxs-lookup"><span data-stu-id="388f7-114">Gets the local variables defined within this scope.</span></span>|  
|[<span data-ttu-id="388f7-115">Metodo GetMethod</span><span class="sxs-lookup"><span data-stu-id="388f7-115">GetMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getmethod-method.md)|<span data-ttu-id="388f7-116">Ottiene il metodo che contiene questo ambito.</span><span class="sxs-lookup"><span data-stu-id="388f7-116">Gets the method that contains this scope.</span></span>|  
|[<span data-ttu-id="388f7-117">Metodo GetNamespaces</span><span class="sxs-lookup"><span data-stu-id="388f7-117">GetNamespaces Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getnamespaces-method.md)|<span data-ttu-id="388f7-118">Ottiene gli spazi dei nomi utilizzati all'interno di questo ambito.</span><span class="sxs-lookup"><span data-stu-id="388f7-118">Gets the namespaces that are being used within this scope.</span></span>|  
|[<span data-ttu-id="388f7-119">Metodo GetParent</span><span class="sxs-lookup"><span data-stu-id="388f7-119">GetParent Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getparent-method.md)|<span data-ttu-id="388f7-120">Ottiene l'ambito padre di questo ambito.</span><span class="sxs-lookup"><span data-stu-id="388f7-120">Gets the parent scope of this scope.</span></span>|  
|[<span data-ttu-id="388f7-121">Metodo GetStartOffset</span><span class="sxs-lookup"><span data-stu-id="388f7-121">GetStartOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getstartoffset-method.md)|<span data-ttu-id="388f7-122">Ottiene l'offset iniziale per l'ambito corrente.</span><span class="sxs-lookup"><span data-stu-id="388f7-122">Gets the start offset for this scope.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="388f7-123">Requisiti</span><span class="sxs-lookup"><span data-stu-id="388f7-123">Requirements</span></span>  
 <span data-ttu-id="388f7-124">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="388f7-124">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="388f7-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="388f7-125">See also</span></span>

- [<span data-ttu-id="388f7-126">Interfacce dell'archivio simboli di diagnostica</span><span class="sxs-lookup"><span data-stu-id="388f7-126">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="388f7-127">Interfaccia ISymUnmanagedScope2</span><span class="sxs-lookup"><span data-stu-id="388f7-127">ISymUnmanagedScope2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-interface.md)

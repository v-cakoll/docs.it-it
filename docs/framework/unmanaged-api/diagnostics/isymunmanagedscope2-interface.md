---
title: Interfaccia ISymUnmanagedScope2
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedScope2
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedScope2
helpviewer_keywords: ISymUnmanagedScope2 interface [.NET Framework debugging]
ms.assetid: 2ed6a387-ba45-483e-9a1e-b0c69f67998b
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 5eed6061c8108fcf91f8ac1ac9ff139da426f0e7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="isymunmanagedscope2-interface"></a><span data-ttu-id="13fb4-102">Interfaccia ISymUnmanagedScope2</span><span class="sxs-lookup"><span data-stu-id="13fb4-102">ISymUnmanagedScope2 Interface</span></span>
<span data-ttu-id="13fb4-103">Rappresenta un ambito lessicale in un metodo.</span><span class="sxs-lookup"><span data-stu-id="13fb4-103">Represents a lexical scope within a method.</span></span> <span data-ttu-id="13fb4-104">Questa interfaccia estende il [ISymUnmanagedScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md) interfaccia con metodi che ottengono informazioni sulle costanti definite all'interno dell'ambito.</span><span class="sxs-lookup"><span data-stu-id="13fb4-104">This interface extends the [ISymUnmanagedScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md) interface with methods that get information about constants defined within the scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="13fb4-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="13fb4-105">Methods</span></span>  
  
|<span data-ttu-id="13fb4-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="13fb4-106">Method</span></span>|<span data-ttu-id="13fb4-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="13fb4-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="13fb4-108">GetConstantCount (metodo)</span><span class="sxs-lookup"><span data-stu-id="13fb4-108">GetConstantCount Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-getconstantcount-method.md)|<span data-ttu-id="13fb4-109">Ottiene un conteggio delle costanti definite in questo ambito.</span><span class="sxs-lookup"><span data-stu-id="13fb4-109">Gets a count of the constants defined within this scope.</span></span>|  
|[<span data-ttu-id="13fb4-110">GetConstants (metodo)</span><span class="sxs-lookup"><span data-stu-id="13fb4-110">GetConstants Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-getconstants-method.md)|<span data-ttu-id="13fb4-111">Ottiene le costanti locali definite in questo ambito.</span><span class="sxs-lookup"><span data-stu-id="13fb4-111">Gets the local constants defined within this scope.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="13fb4-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="13fb4-112">Requirements</span></span>  
 <span data-ttu-id="13fb4-113">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="13fb4-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13fb4-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="13fb4-114">See Also</span></span>  
 [<span data-ttu-id="13fb4-115">Interfacce dell'archivio dei simboli di diagnostica</span><span class="sxs-lookup"><span data-stu-id="13fb4-115">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)  
 [<span data-ttu-id="13fb4-116">ISymUnmanagedScope (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="13fb4-116">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)

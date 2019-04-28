---
title: Interfaccia ISymUnmanagedScope2
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope2
helpviewer_keywords:
- ISymUnmanagedScope2 interface [.NET Framework debugging]
ms.assetid: 2ed6a387-ba45-483e-9a1e-b0c69f67998b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0109b25b1cdc42204fc4873577e495641c4ec4fd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61761572"
---
# <a name="isymunmanagedscope2-interface"></a><span data-ttu-id="3efca-102">Interfaccia ISymUnmanagedScope2</span><span class="sxs-lookup"><span data-stu-id="3efca-102">ISymUnmanagedScope2 Interface</span></span>
<span data-ttu-id="3efca-103">Rappresenta un ambito lessicale in un metodo.</span><span class="sxs-lookup"><span data-stu-id="3efca-103">Represents a lexical scope within a method.</span></span> <span data-ttu-id="3efca-104">Questa interfaccia estende la [ISymUnmanagedScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md) interfacciarsi con i metodi che ottengono informazioni sulle costanti definite all'interno dell'ambito.</span><span class="sxs-lookup"><span data-stu-id="3efca-104">This interface extends the [ISymUnmanagedScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md) interface with methods that get information about constants defined within the scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3efca-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="3efca-105">Methods</span></span>  
  
|<span data-ttu-id="3efca-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="3efca-106">Method</span></span>|<span data-ttu-id="3efca-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3efca-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3efca-108">Metodo GetConstantCount</span><span class="sxs-lookup"><span data-stu-id="3efca-108">GetConstantCount Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-getconstantcount-method.md)|<span data-ttu-id="3efca-109">Ottiene un conteggio delle costanti definite all'interno di questo ambito.</span><span class="sxs-lookup"><span data-stu-id="3efca-109">Gets a count of the constants defined within this scope.</span></span>|  
|[<span data-ttu-id="3efca-110">Metodo GetConstants</span><span class="sxs-lookup"><span data-stu-id="3efca-110">GetConstants Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-getconstants-method.md)|<span data-ttu-id="3efca-111">Ottiene le costanti locali definite all'interno di questo ambito.</span><span class="sxs-lookup"><span data-stu-id="3efca-111">Gets the local constants defined within this scope.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3efca-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3efca-112">Requirements</span></span>  
 <span data-ttu-id="3efca-113">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="3efca-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3efca-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3efca-114">See also</span></span>

- [<span data-ttu-id="3efca-115">Interfacce dell'archivio simboli di diagnostica</span><span class="sxs-lookup"><span data-stu-id="3efca-115">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="3efca-116">Interfaccia ISymUnmanagedScope</span><span class="sxs-lookup"><span data-stu-id="3efca-116">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)

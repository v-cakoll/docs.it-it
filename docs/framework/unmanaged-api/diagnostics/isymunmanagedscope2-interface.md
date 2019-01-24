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
ms.openlocfilehash: beb48835039f142ea1d9e18871f77ada1b6f4f3e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54706313"
---
# <a name="isymunmanagedscope2-interface"></a><span data-ttu-id="73ccb-102">Interfaccia ISymUnmanagedScope2</span><span class="sxs-lookup"><span data-stu-id="73ccb-102">ISymUnmanagedScope2 Interface</span></span>
<span data-ttu-id="73ccb-103">Rappresenta un ambito lessicale in un metodo.</span><span class="sxs-lookup"><span data-stu-id="73ccb-103">Represents a lexical scope within a method.</span></span> <span data-ttu-id="73ccb-104">Questa interfaccia estende la [ISymUnmanagedScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md) interfacciarsi con i metodi che ottengono informazioni sulle costanti definite all'interno dell'ambito.</span><span class="sxs-lookup"><span data-stu-id="73ccb-104">This interface extends the [ISymUnmanagedScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md) interface with methods that get information about constants defined within the scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="73ccb-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="73ccb-105">Methods</span></span>  
  
|<span data-ttu-id="73ccb-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="73ccb-106">Method</span></span>|<span data-ttu-id="73ccb-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="73ccb-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="73ccb-108">Metodo GetConstantCount</span><span class="sxs-lookup"><span data-stu-id="73ccb-108">GetConstantCount Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-getconstantcount-method.md)|<span data-ttu-id="73ccb-109">Ottiene un conteggio delle costanti definite all'interno di questo ambito.</span><span class="sxs-lookup"><span data-stu-id="73ccb-109">Gets a count of the constants defined within this scope.</span></span>|  
|[<span data-ttu-id="73ccb-110">Metodo GetConstants</span><span class="sxs-lookup"><span data-stu-id="73ccb-110">GetConstants Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-getconstants-method.md)|<span data-ttu-id="73ccb-111">Ottiene le costanti locali definite all'interno di questo ambito.</span><span class="sxs-lookup"><span data-stu-id="73ccb-111">Gets the local constants defined within this scope.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="73ccb-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="73ccb-112">Requirements</span></span>  
 <span data-ttu-id="73ccb-113">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="73ccb-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73ccb-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="73ccb-114">See also</span></span>
- [<span data-ttu-id="73ccb-115">Interfacce dell'archivio simboli di diagnostica</span><span class="sxs-lookup"><span data-stu-id="73ccb-115">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="73ccb-116">Interfaccia ISymUnmanagedScope</span><span class="sxs-lookup"><span data-stu-id="73ccb-116">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)

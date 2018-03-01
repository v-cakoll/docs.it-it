---
title: Interfaccia ISymUnmanagedSymbolSearchInfo
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ISymUnmanagedSymbolSearchInfo
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedSymbolSearchInfo
helpviewer_keywords:
- ISymUnmanagedSymbolSearchInfo interface [.NET Framework debugging]
ms.assetid: 30817373-0a21-49c1-a0c4-8e8daeecb8db
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 441330471906a891646ad55eb73ec25b44800cbc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedsymbolsearchinfo-interface"></a><span data-ttu-id="278ba-102">Interfaccia ISymUnmanagedSymbolSearchInfo</span><span class="sxs-lookup"><span data-stu-id="278ba-102">ISymUnmanagedSymbolSearchInfo Interface</span></span>
<span data-ttu-id="278ba-103">Fornisce metodi per ottenere informazioni sul percorso di ricerca.</span><span class="sxs-lookup"><span data-stu-id="278ba-103">Provides methods that get information about the search path.</span></span> <span data-ttu-id="278ba-104">Ottenere questa interfaccia chiamando `QueryInterface` su un oggetto che implementa il [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) interfaccia.</span><span class="sxs-lookup"><span data-stu-id="278ba-104">Obtain this interface by calling `QueryInterface` on an object that implements the [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="278ba-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="278ba-105">Methods</span></span>  
  
|<span data-ttu-id="278ba-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="278ba-106">Method</span></span>|<span data-ttu-id="278ba-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="278ba-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="278ba-108">Metodo GetHRESULT</span><span class="sxs-lookup"><span data-stu-id="278ba-108">GetHRESULT Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-gethresult-method.md)|<span data-ttu-id="278ba-109">Ottiene il valore HRESULT.</span><span class="sxs-lookup"><span data-stu-id="278ba-109">Gets the HRESULT.</span></span>|  
|[<span data-ttu-id="278ba-110">Metodo GetSearchPath</span><span class="sxs-lookup"><span data-stu-id="278ba-110">GetSearchPath Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-getsearchpath-method.md)|<span data-ttu-id="278ba-111">Ottiene il percorso di ricerca.</span><span class="sxs-lookup"><span data-stu-id="278ba-111">Gets the search path.</span></span>|  
|[<span data-ttu-id="278ba-112">Metodo GetSearchPathLength</span><span class="sxs-lookup"><span data-stu-id="278ba-112">GetSearchPathLength Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-getsearchpathlength-method.md)|<span data-ttu-id="278ba-113">Ottiene la lunghezza del percorso di ricerca.</span><span class="sxs-lookup"><span data-stu-id="278ba-113">Gets the search path length.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="278ba-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="278ba-114">Requirements</span></span>  
 <span data-ttu-id="278ba-115">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="278ba-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="278ba-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="278ba-116">See Also</span></span>  
 [<span data-ttu-id="278ba-117">Interfacce dell'archivio simboli di diagnostica</span><span class="sxs-lookup"><span data-stu-id="278ba-117">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)

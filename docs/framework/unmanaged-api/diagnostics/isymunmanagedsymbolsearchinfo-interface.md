---
title: Interfaccia ISymUnmanagedSymbolSearchInfo
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5dce9653d3fef534ac6567e36a4c8213e13ab231
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33429169"
---
# <a name="isymunmanagedsymbolsearchinfo-interface"></a><span data-ttu-id="a8e32-102">Interfaccia ISymUnmanagedSymbolSearchInfo</span><span class="sxs-lookup"><span data-stu-id="a8e32-102">ISymUnmanagedSymbolSearchInfo Interface</span></span>
<span data-ttu-id="a8e32-103">Fornisce metodi per ottenere informazioni sul percorso di ricerca.</span><span class="sxs-lookup"><span data-stu-id="a8e32-103">Provides methods that get information about the search path.</span></span> <span data-ttu-id="a8e32-104">Ottenere questa interfaccia chiamando `QueryInterface` su un oggetto che implementa il [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) interfaccia.</span><span class="sxs-lookup"><span data-stu-id="a8e32-104">Obtain this interface by calling `QueryInterface` on an object that implements the [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a8e32-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="a8e32-105">Methods</span></span>  
  
|<span data-ttu-id="a8e32-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="a8e32-106">Method</span></span>|<span data-ttu-id="a8e32-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a8e32-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a8e32-108">Metodo GetHRESULT</span><span class="sxs-lookup"><span data-stu-id="a8e32-108">GetHRESULT Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-gethresult-method.md)|<span data-ttu-id="a8e32-109">Ottiene il valore HRESULT.</span><span class="sxs-lookup"><span data-stu-id="a8e32-109">Gets the HRESULT.</span></span>|  
|[<span data-ttu-id="a8e32-110">Metodo GetSearchPath</span><span class="sxs-lookup"><span data-stu-id="a8e32-110">GetSearchPath Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-getsearchpath-method.md)|<span data-ttu-id="a8e32-111">Ottiene il percorso di ricerca.</span><span class="sxs-lookup"><span data-stu-id="a8e32-111">Gets the search path.</span></span>|  
|[<span data-ttu-id="a8e32-112">Metodo GetSearchPathLength</span><span class="sxs-lookup"><span data-stu-id="a8e32-112">GetSearchPathLength Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-getsearchpathlength-method.md)|<span data-ttu-id="a8e32-113">Ottiene la lunghezza del percorso di ricerca.</span><span class="sxs-lookup"><span data-stu-id="a8e32-113">Gets the search path length.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a8e32-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a8e32-114">Requirements</span></span>  
 <span data-ttu-id="a8e32-115">**Intestazione:** CorSym. idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="a8e32-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8e32-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a8e32-116">See Also</span></span>  
 [<span data-ttu-id="a8e32-117">Interfacce dell'archivio simboli di diagnostica</span><span class="sxs-lookup"><span data-stu-id="a8e32-117">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)

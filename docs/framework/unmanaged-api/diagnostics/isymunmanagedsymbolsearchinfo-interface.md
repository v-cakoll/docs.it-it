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
ms.openlocfilehash: d573264bb7a3cac02dd41afacaa2bc4a6f9e6dcd
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59207552"
---
# <a name="isymunmanagedsymbolsearchinfo-interface"></a><span data-ttu-id="83ab5-102">Interfaccia ISymUnmanagedSymbolSearchInfo</span><span class="sxs-lookup"><span data-stu-id="83ab5-102">ISymUnmanagedSymbolSearchInfo Interface</span></span>
<span data-ttu-id="83ab5-103">Fornisce metodi che ottengono informazioni sul percorso di ricerca.</span><span class="sxs-lookup"><span data-stu-id="83ab5-103">Provides methods that get information about the search path.</span></span> <span data-ttu-id="83ab5-104">Ottenere questa interfaccia chiamando `QueryInterface` su un oggetto che implementa le [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) interfaccia.</span><span class="sxs-lookup"><span data-stu-id="83ab5-104">Obtain this interface by calling `QueryInterface` on an object that implements the [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="83ab5-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="83ab5-105">Methods</span></span>  
  
|<span data-ttu-id="83ab5-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="83ab5-106">Method</span></span>|<span data-ttu-id="83ab5-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="83ab5-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="83ab5-108">Metodo GetHRESULT</span><span class="sxs-lookup"><span data-stu-id="83ab5-108">GetHRESULT Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-gethresult-method.md)|<span data-ttu-id="83ab5-109">Ottiene il valore HRESULT.</span><span class="sxs-lookup"><span data-stu-id="83ab5-109">Gets the HRESULT.</span></span>|  
|[<span data-ttu-id="83ab5-110">Metodo GetSearchPath</span><span class="sxs-lookup"><span data-stu-id="83ab5-110">GetSearchPath Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-getsearchpath-method.md)|<span data-ttu-id="83ab5-111">Ottiene il percorso di ricerca.</span><span class="sxs-lookup"><span data-stu-id="83ab5-111">Gets the search path.</span></span>|  
|[<span data-ttu-id="83ab5-112">Metodo GetSearchPathLength</span><span class="sxs-lookup"><span data-stu-id="83ab5-112">GetSearchPathLength Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-getsearchpathlength-method.md)|<span data-ttu-id="83ab5-113">Ottiene la lunghezza del percorso di ricerca.</span><span class="sxs-lookup"><span data-stu-id="83ab5-113">Gets the search path length.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="83ab5-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="83ab5-114">Requirements</span></span>  
 <span data-ttu-id="83ab5-115">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="83ab5-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83ab5-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="83ab5-116">See also</span></span>

- [<span data-ttu-id="83ab5-117">Interfacce dell'archivio dei simboli di diagnostica</span><span class="sxs-lookup"><span data-stu-id="83ab5-117">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)

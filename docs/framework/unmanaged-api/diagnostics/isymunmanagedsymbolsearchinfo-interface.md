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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61944571"
---
# <a name="isymunmanagedsymbolsearchinfo-interface"></a><span data-ttu-id="ace54-102">Interfaccia ISymUnmanagedSymbolSearchInfo</span><span class="sxs-lookup"><span data-stu-id="ace54-102">ISymUnmanagedSymbolSearchInfo Interface</span></span>
<span data-ttu-id="ace54-103">Fornisce metodi che ottengono informazioni sul percorso di ricerca.</span><span class="sxs-lookup"><span data-stu-id="ace54-103">Provides methods that get information about the search path.</span></span> <span data-ttu-id="ace54-104">Ottenere questa interfaccia chiamando `QueryInterface` su un oggetto che implementa le [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) interfaccia.</span><span class="sxs-lookup"><span data-stu-id="ace54-104">Obtain this interface by calling `QueryInterface` on an object that implements the [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ace54-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="ace54-105">Methods</span></span>  
  
|<span data-ttu-id="ace54-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="ace54-106">Method</span></span>|<span data-ttu-id="ace54-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ace54-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ace54-108">Metodo GetHRESULT</span><span class="sxs-lookup"><span data-stu-id="ace54-108">GetHRESULT Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-gethresult-method.md)|<span data-ttu-id="ace54-109">Ottiene il valore HRESULT.</span><span class="sxs-lookup"><span data-stu-id="ace54-109">Gets the HRESULT.</span></span>|  
|[<span data-ttu-id="ace54-110">Metodo GetSearchPath</span><span class="sxs-lookup"><span data-stu-id="ace54-110">GetSearchPath Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-getsearchpath-method.md)|<span data-ttu-id="ace54-111">Ottiene il percorso di ricerca.</span><span class="sxs-lookup"><span data-stu-id="ace54-111">Gets the search path.</span></span>|  
|[<span data-ttu-id="ace54-112">Metodo GetSearchPathLength</span><span class="sxs-lookup"><span data-stu-id="ace54-112">GetSearchPathLength Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-getsearchpathlength-method.md)|<span data-ttu-id="ace54-113">Ottiene la lunghezza del percorso di ricerca.</span><span class="sxs-lookup"><span data-stu-id="ace54-113">Gets the search path length.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ace54-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ace54-114">Requirements</span></span>  
 <span data-ttu-id="ace54-115">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="ace54-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ace54-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ace54-116">See also</span></span>

- [<span data-ttu-id="ace54-117">Interfacce dell'archivio simboli di diagnostica</span><span class="sxs-lookup"><span data-stu-id="ace54-117">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)

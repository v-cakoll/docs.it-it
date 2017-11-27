---
title: Interfaccia ISymUnmanagedSymbolSearchInfo
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedSymbolSearchInfo
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedSymbolSearchInfo
helpviewer_keywords: ISymUnmanagedSymbolSearchInfo interface [.NET Framework debugging]
ms.assetid: 30817373-0a21-49c1-a0c4-8e8daeecb8db
topic_type: apiref
caps.latest.revision: "6"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 967511238dceb752ab30ce10dcaba8b65f4dd9fb
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedsymbolsearchinfo-interface"></a><span data-ttu-id="61243-102">Interfaccia ISymUnmanagedSymbolSearchInfo</span><span class="sxs-lookup"><span data-stu-id="61243-102">ISymUnmanagedSymbolSearchInfo Interface</span></span>
<span data-ttu-id="61243-103">Fornisce metodi per ottenere informazioni sul percorso di ricerca.</span><span class="sxs-lookup"><span data-stu-id="61243-103">Provides methods that get information about the search path.</span></span> <span data-ttu-id="61243-104">Ottenere questa interfaccia chiamando `QueryInterface` su un oggetto che implementa il [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) interfaccia.</span><span class="sxs-lookup"><span data-stu-id="61243-104">Obtain this interface by calling `QueryInterface` on an object that implements the [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="61243-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="61243-105">Methods</span></span>  
  
|<span data-ttu-id="61243-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="61243-106">Method</span></span>|<span data-ttu-id="61243-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="61243-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="61243-108">GetHRESULT (metodo)</span><span class="sxs-lookup"><span data-stu-id="61243-108">GetHRESULT Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-gethresult-method.md)|<span data-ttu-id="61243-109">Ottiene il valore HRESULT.</span><span class="sxs-lookup"><span data-stu-id="61243-109">Gets the HRESULT.</span></span>|  
|[<span data-ttu-id="61243-110">GetSearchPath (metodo)</span><span class="sxs-lookup"><span data-stu-id="61243-110">GetSearchPath Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-getsearchpath-method.md)|<span data-ttu-id="61243-111">Ottiene il percorso di ricerca.</span><span class="sxs-lookup"><span data-stu-id="61243-111">Gets the search path.</span></span>|  
|[<span data-ttu-id="61243-112">GetSearchPathLength (metodo)</span><span class="sxs-lookup"><span data-stu-id="61243-112">GetSearchPathLength Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-getsearchpathlength-method.md)|<span data-ttu-id="61243-113">Ottiene la lunghezza del percorso di ricerca.</span><span class="sxs-lookup"><span data-stu-id="61243-113">Gets the search path length.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="61243-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="61243-114">Requirements</span></span>  
 <span data-ttu-id="61243-115">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="61243-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61243-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="61243-116">See Also</span></span>  
 [<span data-ttu-id="61243-117">Interfacce dell'archivio dei simboli di diagnostica</span><span class="sxs-lookup"><span data-stu-id="61243-117">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)

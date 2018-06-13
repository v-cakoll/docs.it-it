---
title: Interfaccia ISymUnmanagedSourceServerModule
ms.date: 03/30/2017
api_name:
- ISymUnmanagedSourceServerModule
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedSourceServerModule
helpviewer_keywords:
- ISymUnmanagedSourceServerModule interface [.NET Framework debugging]
ms.assetid: a19b23bd-2061-476e-b67d-252f57404f8b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0a63700abf77d56134ca30620033c398af735599
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33426739"
---
# <a name="isymunmanagedsourceservermodule-interface"></a><span data-ttu-id="cb467-102">Interfaccia ISymUnmanagedSourceServerModule</span><span class="sxs-lookup"><span data-stu-id="cb467-102">ISymUnmanagedSourceServerModule Interface</span></span>
<span data-ttu-id="cb467-103">Fornisce i dati di server di origine per un modulo.</span><span class="sxs-lookup"><span data-stu-id="cb467-103">Provides source server data for a module.</span></span> <span data-ttu-id="cb467-104">Ottenere questa interfaccia chiamando `QueryInterface` su un oggetto che implementa il [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) interfaccia.</span><span class="sxs-lookup"><span data-stu-id="cb467-104">Obtain this interface by calling `QueryInterface` on an object that implements the [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="cb467-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="cb467-105">Methods</span></span>  
  
|<span data-ttu-id="cb467-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="cb467-106">Method</span></span>|<span data-ttu-id="cb467-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cb467-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="cb467-108">Metodo GetSourceServerData</span><span class="sxs-lookup"><span data-stu-id="cb467-108">GetSourceServerData Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsourceservermodule-getsourceserverdata-method.md)|<span data-ttu-id="cb467-109">Restituisce i dati del server di origine per il modulo.</span><span class="sxs-lookup"><span data-stu-id="cb467-109">Returns the source server data for the module.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="cb467-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="cb467-110">Requirements</span></span>  
 <span data-ttu-id="cb467-111">**Intestazione:** CorSym. idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="cb467-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb467-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cb467-112">See Also</span></span>  
 [<span data-ttu-id="cb467-113">Interfacce dell'archivio simboli di diagnostica</span><span class="sxs-lookup"><span data-stu-id="cb467-113">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)

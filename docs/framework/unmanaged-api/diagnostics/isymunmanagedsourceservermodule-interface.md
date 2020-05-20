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
ms.openlocfilehash: d90a55b53ba00540137e44fc190790c4710903e3
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83610795"
---
# <a name="isymunmanagedsourceservermodule-interface"></a><span data-ttu-id="3da7b-102">Interfaccia ISymUnmanagedSourceServerModule</span><span class="sxs-lookup"><span data-stu-id="3da7b-102">ISymUnmanagedSourceServerModule Interface</span></span>
<span data-ttu-id="3da7b-103">Fornisce i dati del server di origine per un modulo.</span><span class="sxs-lookup"><span data-stu-id="3da7b-103">Provides source server data for a module.</span></span> <span data-ttu-id="3da7b-104">Ottenere questa interfaccia chiamando `QueryInterface` su un oggetto che implementa l'interfaccia [ISymUnmanagedReader](isymunmanagedreader-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="3da7b-104">Obtain this interface by calling `QueryInterface` on an object that implements the [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3da7b-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="3da7b-105">Methods</span></span>  
  
|<span data-ttu-id="3da7b-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="3da7b-106">Method</span></span>|<span data-ttu-id="3da7b-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3da7b-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3da7b-108">Metodo GetSourceServerData</span><span class="sxs-lookup"><span data-stu-id="3da7b-108">GetSourceServerData Method</span></span>](isymunmanagedsourceservermodule-getsourceserverdata-method.md)|<span data-ttu-id="3da7b-109">Restituisce i dati del server di origine per il modulo.</span><span class="sxs-lookup"><span data-stu-id="3da7b-109">Returns the source server data for the module.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3da7b-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3da7b-110">Requirements</span></span>  
 <span data-ttu-id="3da7b-111">**Intestazione:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="3da7b-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3da7b-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3da7b-112">See also</span></span>

- [<span data-ttu-id="3da7b-113">Interfacce dell'archivio dei simboli di diagnostica</span><span class="sxs-lookup"><span data-stu-id="3da7b-113">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)

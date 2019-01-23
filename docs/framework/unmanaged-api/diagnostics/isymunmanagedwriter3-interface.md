---
title: Interfaccia ISymUnmanagedWriter3
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter3
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter3
helpviewer_keywords:
- ISymUnmanagedWriter3 interface [.NET Framework debugging]
ms.assetid: a034c21e-e371-4360-b470-29e88288948f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7c14706068e50fd79fb39ac9d75afacd181f7ab4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54504080"
---
# <a name="isymunmanagedwriter3-interface"></a><span data-ttu-id="c9ee0-102">Interfaccia ISymUnmanagedWriter3</span><span class="sxs-lookup"><span data-stu-id="c9ee0-102">ISymUnmanagedWriter3 Interface</span></span>
<span data-ttu-id="c9ee0-103">Rappresenta un writer di simboli e fornisce metodi per definire punti di sequenza, gli ambiti lessicali, variabili e documenti.</span><span class="sxs-lookup"><span data-stu-id="c9ee0-103">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span></span> <span data-ttu-id="c9ee0-104">Questa interfaccia estende la [ISymUnmanagedWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md) interfaccia.</span><span class="sxs-lookup"><span data-stu-id="c9ee0-104">This interface extends the [ISymUnmanagedWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c9ee0-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="c9ee0-105">Methods</span></span>  
  
|<span data-ttu-id="c9ee0-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="c9ee0-106">Method</span></span>|<span data-ttu-id="c9ee0-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c9ee0-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c9ee0-108">Metodo Commit</span><span class="sxs-lookup"><span data-stu-id="c9ee0-108">Commit Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-commit-method.md)|<span data-ttu-id="c9ee0-109">Conferma le modifiche apportate finora scritte nel flusso.</span><span class="sxs-lookup"><span data-stu-id="c9ee0-109">Commits the changes written so far to the stream.</span></span>|  
|[<span data-ttu-id="c9ee0-110">Metodo OpenMethod2</span><span class="sxs-lookup"><span data-stu-id="c9ee0-110">OpenMethod2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-openmethod2-method.md)|<span data-ttu-id="c9ee0-111">Apre un metodo e fornisce l'offset di sezione reali nell'immagine.</span><span class="sxs-lookup"><span data-stu-id="c9ee0-111">Opens a method and provides its real section offset in the image.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c9ee0-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c9ee0-112">Requirements</span></span>  
 <span data-ttu-id="c9ee0-113">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="c9ee0-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9ee0-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c9ee0-114">See also</span></span>
- [<span data-ttu-id="c9ee0-115">Interfacce dell'archivio simboli di diagnostica</span><span class="sxs-lookup"><span data-stu-id="c9ee0-115">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="c9ee0-116">Interfaccia ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="c9ee0-116">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
- [<span data-ttu-id="c9ee0-117">Interfaccia ISymUnmanagedWriter2</span><span class="sxs-lookup"><span data-stu-id="c9ee0-117">ISymUnmanagedWriter2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-interface.md)

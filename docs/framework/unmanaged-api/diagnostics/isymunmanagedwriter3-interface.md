---
title: Interfaccia ISymUnmanagedWriter3
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedWriter3
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedWriter3
helpviewer_keywords: ISymUnmanagedWriter3 interface [.NET Framework debugging]
ms.assetid: a034c21e-e371-4360-b470-29e88288948f
topic_type: apiref
caps.latest.revision: "6"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 3babf8b3a54f07ac4eb14e326f66c70834953dfe
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="isymunmanagedwriter3-interface"></a><span data-ttu-id="9fa55-102">Interfaccia ISymUnmanagedWriter3</span><span class="sxs-lookup"><span data-stu-id="9fa55-102">ISymUnmanagedWriter3 Interface</span></span>
<span data-ttu-id="9fa55-103">Rappresenta un writer di simboli e fornisce metodi per definire punti di sequenza, gli ambiti lessicali, variabili e documenti.</span><span class="sxs-lookup"><span data-stu-id="9fa55-103">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span></span> <span data-ttu-id="9fa55-104">Questa interfaccia estende il [ISymUnmanagedWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md) interfaccia.</span><span class="sxs-lookup"><span data-stu-id="9fa55-104">This interface extends the [ISymUnmanagedWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9fa55-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="9fa55-105">Methods</span></span>  
  
|<span data-ttu-id="9fa55-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="9fa55-106">Method</span></span>|<span data-ttu-id="9fa55-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9fa55-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9fa55-108">Commit (metodo)</span><span class="sxs-lookup"><span data-stu-id="9fa55-108">Commit Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-commit-method.md)|<span data-ttu-id="9fa55-109">Conferma le modifiche apportate finora scritte nel flusso.</span><span class="sxs-lookup"><span data-stu-id="9fa55-109">Commits the changes written so far to the stream.</span></span>|  
|[<span data-ttu-id="9fa55-110">OpenMethod2 (metodo)</span><span class="sxs-lookup"><span data-stu-id="9fa55-110">OpenMethod2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-openmethod2-method.md)|<span data-ttu-id="9fa55-111">Apre un metodo e fornisce l'offset di sezione reale nell'immagine.</span><span class="sxs-lookup"><span data-stu-id="9fa55-111">Opens a method and provides its real section offset in the image.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9fa55-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9fa55-112">Requirements</span></span>  
 <span data-ttu-id="9fa55-113">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="9fa55-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9fa55-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9fa55-114">See Also</span></span>  
 [<span data-ttu-id="9fa55-115">Interfacce dell'archivio dei simboli di diagnostica</span><span class="sxs-lookup"><span data-stu-id="9fa55-115">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)  
 [<span data-ttu-id="9fa55-116">ISymUnmanagedWriter (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="9fa55-116">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)  
 [<span data-ttu-id="9fa55-117">ISymUnmanagedWriter2 (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="9fa55-117">ISymUnmanagedWriter2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-interface.md)

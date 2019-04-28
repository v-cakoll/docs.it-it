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
ms.openlocfilehash: e26d79a5b597b8585f2fffd7f3945f00832ca134
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61650713"
---
# <a name="isymunmanagedwriter3-interface"></a><span data-ttu-id="5b734-102">Interfaccia ISymUnmanagedWriter3</span><span class="sxs-lookup"><span data-stu-id="5b734-102">ISymUnmanagedWriter3 Interface</span></span>
<span data-ttu-id="5b734-103">Rappresenta un writer di simboli e fornisce metodi per definire punti di sequenza, gli ambiti lessicali, variabili e documenti.</span><span class="sxs-lookup"><span data-stu-id="5b734-103">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span></span> <span data-ttu-id="5b734-104">Questa interfaccia estende la [ISymUnmanagedWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md) interfaccia.</span><span class="sxs-lookup"><span data-stu-id="5b734-104">This interface extends the [ISymUnmanagedWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5b734-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="5b734-105">Methods</span></span>  
  
|<span data-ttu-id="5b734-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="5b734-106">Method</span></span>|<span data-ttu-id="5b734-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5b734-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5b734-108">Metodo Commit</span><span class="sxs-lookup"><span data-stu-id="5b734-108">Commit Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-commit-method.md)|<span data-ttu-id="5b734-109">Conferma le modifiche apportate finora scritte nel flusso.</span><span class="sxs-lookup"><span data-stu-id="5b734-109">Commits the changes written so far to the stream.</span></span>|  
|[<span data-ttu-id="5b734-110">Metodo OpenMethod2</span><span class="sxs-lookup"><span data-stu-id="5b734-110">OpenMethod2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-openmethod2-method.md)|<span data-ttu-id="5b734-111">Apre un metodo e fornisce l'offset di sezione reali nell'immagine.</span><span class="sxs-lookup"><span data-stu-id="5b734-111">Opens a method and provides its real section offset in the image.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5b734-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5b734-112">Requirements</span></span>  
 <span data-ttu-id="5b734-113">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="5b734-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b734-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5b734-114">See also</span></span>

- [<span data-ttu-id="5b734-115">Interfacce dell'archivio simboli di diagnostica</span><span class="sxs-lookup"><span data-stu-id="5b734-115">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="5b734-116">Interfaccia ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="5b734-116">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
- [<span data-ttu-id="5b734-117">Interfaccia ISymUnmanagedWriter2</span><span class="sxs-lookup"><span data-stu-id="5b734-117">ISymUnmanagedWriter2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-interface.md)

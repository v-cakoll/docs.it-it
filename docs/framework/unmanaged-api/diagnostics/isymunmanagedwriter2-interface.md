---
title: Interfaccia ISymUnmanagedWriter2
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter2
helpviewer_keywords:
- ISymUnmanagedWriter2 interface [.NET Framework debugging]
ms.assetid: 8e78faa4-cf43-44fb-a91d-94d6df692a25
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 99e8b8bbb25bc55c7d4f2f44aac8e24210d30b83
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54560548"
---
# <a name="isymunmanagedwriter2-interface"></a><span data-ttu-id="c4814-102">Interfaccia ISymUnmanagedWriter2</span><span class="sxs-lookup"><span data-stu-id="c4814-102">ISymUnmanagedWriter2 Interface</span></span>
<span data-ttu-id="c4814-103">Rappresenta un writer di simboli e fornisce metodi per definire punti di sequenza, gli ambiti lessicali, variabili e documenti.</span><span class="sxs-lookup"><span data-stu-id="c4814-103">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span></span> <span data-ttu-id="c4814-104">Questa interfaccia estende la [ISymUnmanagedWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md) interfaccia.</span><span class="sxs-lookup"><span data-stu-id="c4814-104">This interface extends the [ISymUnmanagedWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c4814-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="c4814-105">Methods</span></span>  
  
|<span data-ttu-id="c4814-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="c4814-106">Method</span></span>|<span data-ttu-id="c4814-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c4814-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c4814-108">Metodo DefineConstant2</span><span class="sxs-lookup"><span data-stu-id="c4814-108">DefineConstant2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-defineconstant2-method.md)|<span data-ttu-id="c4814-109">Definisce un nome per un valore costante.</span><span class="sxs-lookup"><span data-stu-id="c4814-109">Defines a name for a constant value.</span></span>|  
|[<span data-ttu-id="c4814-110">Metodo DefineGlobalVariable2</span><span class="sxs-lookup"><span data-stu-id="c4814-110">DefineGlobalVariable2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-defineglobalvariable2-method.md)|<span data-ttu-id="c4814-111">Definisce una variabile globale singola.</span><span class="sxs-lookup"><span data-stu-id="c4814-111">Defines a single global variable.</span></span>|  
|[<span data-ttu-id="c4814-112">Metodo DefineLocalVariable2</span><span class="sxs-lookup"><span data-stu-id="c4814-112">DefineLocalVariable2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-definelocalvariable2-method.md)|<span data-ttu-id="c4814-113">Definisce una singola variabile nell'ambito lessicale corrente.</span><span class="sxs-lookup"><span data-stu-id="c4814-113">Defines a single variable in the current lexical scope.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c4814-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c4814-114">Requirements</span></span>  
 <span data-ttu-id="c4814-115">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="c4814-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4814-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c4814-116">See also</span></span>
- [<span data-ttu-id="c4814-117">Interfacce dell'archivio simboli di diagnostica</span><span class="sxs-lookup"><span data-stu-id="c4814-117">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="c4814-118">Interfaccia ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="c4814-118">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
- [<span data-ttu-id="c4814-119">Interfaccia ISymUnmanagedWriter3</span><span class="sxs-lookup"><span data-stu-id="c4814-119">ISymUnmanagedWriter3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-interface.md)

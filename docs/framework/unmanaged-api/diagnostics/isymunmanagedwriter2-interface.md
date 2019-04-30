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
ms.openlocfilehash: 97df6d6ec9a446e89eef8a9f8a5e5e8ddc85c0f7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61970196"
---
# <a name="isymunmanagedwriter2-interface"></a><span data-ttu-id="e3a78-102">Interfaccia ISymUnmanagedWriter2</span><span class="sxs-lookup"><span data-stu-id="e3a78-102">ISymUnmanagedWriter2 Interface</span></span>
<span data-ttu-id="e3a78-103">Rappresenta un writer di simboli e fornisce metodi per definire punti di sequenza, gli ambiti lessicali, variabili e documenti.</span><span class="sxs-lookup"><span data-stu-id="e3a78-103">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span></span> <span data-ttu-id="e3a78-104">Questa interfaccia estende la [ISymUnmanagedWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md) interfaccia.</span><span class="sxs-lookup"><span data-stu-id="e3a78-104">This interface extends the [ISymUnmanagedWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e3a78-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="e3a78-105">Methods</span></span>  
  
|<span data-ttu-id="e3a78-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="e3a78-106">Method</span></span>|<span data-ttu-id="e3a78-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e3a78-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e3a78-108">Metodo DefineConstant2</span><span class="sxs-lookup"><span data-stu-id="e3a78-108">DefineConstant2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-defineconstant2-method.md)|<span data-ttu-id="e3a78-109">Definisce un nome per un valore costante.</span><span class="sxs-lookup"><span data-stu-id="e3a78-109">Defines a name for a constant value.</span></span>|  
|[<span data-ttu-id="e3a78-110">Metodo DefineGlobalVariable2</span><span class="sxs-lookup"><span data-stu-id="e3a78-110">DefineGlobalVariable2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-defineglobalvariable2-method.md)|<span data-ttu-id="e3a78-111">Definisce una variabile globale singola.</span><span class="sxs-lookup"><span data-stu-id="e3a78-111">Defines a single global variable.</span></span>|  
|[<span data-ttu-id="e3a78-112">Metodo DefineLocalVariable2</span><span class="sxs-lookup"><span data-stu-id="e3a78-112">DefineLocalVariable2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-definelocalvariable2-method.md)|<span data-ttu-id="e3a78-113">Definisce una singola variabile nell'ambito lessicale corrente.</span><span class="sxs-lookup"><span data-stu-id="e3a78-113">Defines a single variable in the current lexical scope.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e3a78-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e3a78-114">Requirements</span></span>  
 <span data-ttu-id="e3a78-115">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="e3a78-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3a78-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e3a78-116">See also</span></span>

- [<span data-ttu-id="e3a78-117">Interfacce dell'archivio simboli di diagnostica</span><span class="sxs-lookup"><span data-stu-id="e3a78-117">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="e3a78-118">Interfaccia ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="e3a78-118">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
- [<span data-ttu-id="e3a78-119">Interfaccia ISymUnmanagedWriter3</span><span class="sxs-lookup"><span data-stu-id="e3a78-119">ISymUnmanagedWriter3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-interface.md)

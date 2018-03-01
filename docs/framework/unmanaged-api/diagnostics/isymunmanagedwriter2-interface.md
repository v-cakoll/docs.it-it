---
title: Interfaccia ISymUnmanagedWriter2
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 98461cd2c2bc26d78f3f3f747b95d46576ba01e2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedwriter2-interface"></a><span data-ttu-id="77e40-102">Interfaccia ISymUnmanagedWriter2</span><span class="sxs-lookup"><span data-stu-id="77e40-102">ISymUnmanagedWriter2 Interface</span></span>
<span data-ttu-id="77e40-103">Rappresenta un writer di simboli e fornisce metodi per definire punti di sequenza, gli ambiti lessicali, variabili e documenti.</span><span class="sxs-lookup"><span data-stu-id="77e40-103">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span></span> <span data-ttu-id="77e40-104">Questa interfaccia estende il [ISymUnmanagedWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md) interfaccia.</span><span class="sxs-lookup"><span data-stu-id="77e40-104">This interface extends the [ISymUnmanagedWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="77e40-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="77e40-105">Methods</span></span>  
  
|<span data-ttu-id="77e40-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="77e40-106">Method</span></span>|<span data-ttu-id="77e40-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="77e40-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="77e40-108">Metodo DefineConstant2</span><span class="sxs-lookup"><span data-stu-id="77e40-108">DefineConstant2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-defineconstant2-method.md)|<span data-ttu-id="77e40-109">Definisce un nome per un valore costante.</span><span class="sxs-lookup"><span data-stu-id="77e40-109">Defines a name for a constant value.</span></span>|  
|[<span data-ttu-id="77e40-110">Metodo DefineGlobalVariable2</span><span class="sxs-lookup"><span data-stu-id="77e40-110">DefineGlobalVariable2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-defineglobalvariable2-method.md)|<span data-ttu-id="77e40-111">Definisce una singola variabile globale.</span><span class="sxs-lookup"><span data-stu-id="77e40-111">Defines a single global variable.</span></span>|  
|[<span data-ttu-id="77e40-112">Metodo DefineLocalVariable2</span><span class="sxs-lookup"><span data-stu-id="77e40-112">DefineLocalVariable2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-definelocalvariable2-method.md)|<span data-ttu-id="77e40-113">Definisce una singola variabile nell'ambito lessicale corrente.</span><span class="sxs-lookup"><span data-stu-id="77e40-113">Defines a single variable in the current lexical scope.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="77e40-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="77e40-114">Requirements</span></span>  
 <span data-ttu-id="77e40-115">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="77e40-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77e40-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="77e40-116">See Also</span></span>  
 [<span data-ttu-id="77e40-117">Interfacce dell'archivio simboli di diagnostica</span><span class="sxs-lookup"><span data-stu-id="77e40-117">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)  
 [<span data-ttu-id="77e40-118">Interfaccia ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="77e40-118">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)  
 [<span data-ttu-id="77e40-119">Interfaccia ISymUnmanagedWriter3</span><span class="sxs-lookup"><span data-stu-id="77e40-119">ISymUnmanagedWriter3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-interface.md)

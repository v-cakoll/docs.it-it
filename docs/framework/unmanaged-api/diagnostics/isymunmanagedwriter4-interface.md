---
title: Interfaccia ISymUnmanagedWriter4
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 4af5e8c0-987d-405e-b934-8b9e70fcae6e
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f7ab7f06ba280675ca8349500e766364d30f9349
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="isymunmanagedwriter4-interface"></a><span data-ttu-id="bb1d0-102">Interfaccia ISymUnmanagedWriter4</span><span class="sxs-lookup"><span data-stu-id="bb1d0-102">ISymUnmanagedWriter4 Interface</span></span>
<span data-ttu-id="bb1d0-103">Interfaccia ISymUnmanagedWriter4.</span><span class="sxs-lookup"><span data-stu-id="bb1d0-103">ISymUnmanagedWriter4 interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb1d0-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bb1d0-104">Syntax</span></span>  
  
```idl  
[object,uuid(BC7E3F53-F458-4C23-9DBD-A189E6E96594),pointer_default(unique)]interface ISymUnmanagedWriter4 : ISymUnmanagedWriter3  
```  
  
## <a name="methods"></a><span data-ttu-id="bb1d0-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="bb1d0-105">Methods</span></span>  
 <span data-ttu-id="bb1d0-106">Per l'interfaccia sono disponibili i seguenti metodi:</span><span class="sxs-lookup"><span data-stu-id="bb1d0-106">This interface contains the following methods:</span></span>  
  
|<span data-ttu-id="bb1d0-107">Metodo</span><span class="sxs-lookup"><span data-stu-id="bb1d0-107">Method</span></span>|<span data-ttu-id="bb1d0-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bb1d0-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="bb1d0-109">Metodo GetDebugInfoWithPadding</span><span class="sxs-lookup"><span data-stu-id="bb1d0-109">GetDebugInfoWithPadding Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter4-getdebuginfowithpadding-method.md)|<span data-ttu-id="bb1d0-110">Funziona nello stesso modo [metodo GetDebugInfo](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-getdebuginfo-method.md) ad eccezione del fatto che la stringa di percorso verrà anteposti tanti zeri che seguono il carattere di terminazione null per rendere i dati di stringa di una dimensione fissa di `MAX_PATH`.</span><span class="sxs-lookup"><span data-stu-id="bb1d0-110">Functions the same as [GetDebugInfo Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-getdebuginfo-method.md) except that the path string is padded with zeros following the terminating null character to make the string data a fixed size of `MAX_PATH`.</span></span> <span data-ttu-id="bb1d0-111">Spaziatura interna viene fornita solo se la lunghezza della stringa di percorso stesso è minore di `MAX_PATH`.</span><span class="sxs-lookup"><span data-stu-id="bb1d0-111">Padding is only given if the path string length itself is less than `MAX_PATH`.</span></span><br /><br /> <span data-ttu-id="bb1d0-112">Questo rende più semplice scrivere strumenti tale file PE di differenza.</span><span class="sxs-lookup"><span data-stu-id="bb1d0-112">This makes it easier to write tools that difference PE files.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="bb1d0-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="bb1d0-113">Requirements</span></span>  
 <span data-ttu-id="bb1d0-114">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="bb1d0-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb1d0-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bb1d0-115">See Also</span></span>  
 [<span data-ttu-id="bb1d0-116">Interfacce dell'archivio dei simboli di diagnostica</span><span class="sxs-lookup"><span data-stu-id="bb1d0-116">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)  
 [<span data-ttu-id="bb1d0-117">ISymUnmanagedWriter3 (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="bb1d0-117">ISymUnmanagedWriter3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-interface.md)

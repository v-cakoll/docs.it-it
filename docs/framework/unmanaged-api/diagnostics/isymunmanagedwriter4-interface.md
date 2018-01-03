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
ms.workload: dotnet
ms.openlocfilehash: 5531b491da70cb78de1234e750c2e15390c10ce5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedwriter4-interface"></a><span data-ttu-id="c6e26-102">Interfaccia ISymUnmanagedWriter4</span><span class="sxs-lookup"><span data-stu-id="c6e26-102">ISymUnmanagedWriter4 Interface</span></span>
<span data-ttu-id="c6e26-103">Interfaccia ISymUnmanagedWriter4.</span><span class="sxs-lookup"><span data-stu-id="c6e26-103">ISymUnmanagedWriter4 interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6e26-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c6e26-104">Syntax</span></span>  
  
```idl  
[object,uuid(BC7E3F53-F458-4C23-9DBD-A189E6E96594),pointer_default(unique)]interface ISymUnmanagedWriter4 : ISymUnmanagedWriter3  
```  
  
## <a name="methods"></a><span data-ttu-id="c6e26-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="c6e26-105">Methods</span></span>  
 <span data-ttu-id="c6e26-106">Per l'interfaccia sono disponibili i seguenti metodi:</span><span class="sxs-lookup"><span data-stu-id="c6e26-106">This interface contains the following methods:</span></span>  
  
|<span data-ttu-id="c6e26-107">Metodo</span><span class="sxs-lookup"><span data-stu-id="c6e26-107">Method</span></span>|<span data-ttu-id="c6e26-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c6e26-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c6e26-109">Metodo GetDebugInfoWithPadding</span><span class="sxs-lookup"><span data-stu-id="c6e26-109">GetDebugInfoWithPadding Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter4-getdebuginfowithpadding-method.md)|<span data-ttu-id="c6e26-110">Funziona nello stesso modo [metodo GetDebugInfo](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-getdebuginfo-method.md) ad eccezione del fatto che la stringa di percorso verrà anteposti tanti zeri che seguono il carattere di terminazione null per rendere i dati di stringa di una dimensione fissa di `MAX_PATH`.</span><span class="sxs-lookup"><span data-stu-id="c6e26-110">Functions the same as [GetDebugInfo Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-getdebuginfo-method.md) except that the path string is padded with zeros following the terminating null character to make the string data a fixed size of `MAX_PATH`.</span></span> <span data-ttu-id="c6e26-111">Spaziatura interna viene fornita solo se la lunghezza della stringa di percorso stesso è minore di `MAX_PATH`.</span><span class="sxs-lookup"><span data-stu-id="c6e26-111">Padding is only given if the path string length itself is less than `MAX_PATH`.</span></span><br /><br /> <span data-ttu-id="c6e26-112">Questo rende più semplice scrivere strumenti tale file PE di differenza.</span><span class="sxs-lookup"><span data-stu-id="c6e26-112">This makes it easier to write tools that difference PE files.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c6e26-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c6e26-113">Requirements</span></span>  
 <span data-ttu-id="c6e26-114">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="c6e26-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6e26-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c6e26-115">See Also</span></span>  
 [<span data-ttu-id="c6e26-116">Interfacce dell'archivio simboli di diagnostica</span><span class="sxs-lookup"><span data-stu-id="c6e26-116">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)  
 [<span data-ttu-id="c6e26-117">Interfaccia ISymUnmanagedWriter3</span><span class="sxs-lookup"><span data-stu-id="c6e26-117">ISymUnmanagedWriter3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-interface.md)

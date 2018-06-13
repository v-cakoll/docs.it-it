---
title: Interfaccia ISymUnmanagedWriter4
ms.date: 03/30/2017
ms.assetid: 4af5e8c0-987d-405e-b934-8b9e70fcae6e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5e8478aed662142b9ff4b73f9cb192f8d2306e2a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33429686"
---
# <a name="isymunmanagedwriter4-interface"></a><span data-ttu-id="50c25-102">Interfaccia ISymUnmanagedWriter4</span><span class="sxs-lookup"><span data-stu-id="50c25-102">ISymUnmanagedWriter4 Interface</span></span>
<span data-ttu-id="50c25-103">Interfaccia ISymUnmanagedWriter4.</span><span class="sxs-lookup"><span data-stu-id="50c25-103">ISymUnmanagedWriter4 interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="50c25-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="50c25-104">Syntax</span></span>  
  
```idl  
[object,uuid(BC7E3F53-F458-4C23-9DBD-A189E6E96594),pointer_default(unique)]interface ISymUnmanagedWriter4 : ISymUnmanagedWriter3  
```  
  
## <a name="methods"></a><span data-ttu-id="50c25-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="50c25-105">Methods</span></span>  
 <span data-ttu-id="50c25-106">Per l'interfaccia sono disponibili i seguenti metodi:</span><span class="sxs-lookup"><span data-stu-id="50c25-106">This interface contains the following methods:</span></span>  
  
|<span data-ttu-id="50c25-107">Metodo</span><span class="sxs-lookup"><span data-stu-id="50c25-107">Method</span></span>|<span data-ttu-id="50c25-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="50c25-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="50c25-109">Metodo GetDebugInfoWithPadding</span><span class="sxs-lookup"><span data-stu-id="50c25-109">GetDebugInfoWithPadding Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter4-getdebuginfowithpadding-method.md)|<span data-ttu-id="50c25-110">Funziona nello stesso modo [metodo GetDebugInfo](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-getdebuginfo-method.md) ad eccezione del fatto che la stringa di percorso verrà anteposti tanti zeri che seguono il carattere di terminazione null per rendere i dati di stringa di una dimensione fissa di `MAX_PATH`.</span><span class="sxs-lookup"><span data-stu-id="50c25-110">Functions the same as [GetDebugInfo Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-getdebuginfo-method.md) except that the path string is padded with zeros following the terminating null character to make the string data a fixed size of `MAX_PATH`.</span></span> <span data-ttu-id="50c25-111">Spaziatura interna viene fornita solo se la lunghezza della stringa di percorso stesso è minore di `MAX_PATH`.</span><span class="sxs-lookup"><span data-stu-id="50c25-111">Padding is only given if the path string length itself is less than `MAX_PATH`.</span></span><br /><br /> <span data-ttu-id="50c25-112">Questo rende più semplice scrivere strumenti tale file PE di differenza.</span><span class="sxs-lookup"><span data-stu-id="50c25-112">This makes it easier to write tools that difference PE files.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="50c25-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="50c25-113">Requirements</span></span>  
 <span data-ttu-id="50c25-114">**Intestazione:** CorSym. idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="50c25-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50c25-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="50c25-115">See Also</span></span>  
 [<span data-ttu-id="50c25-116">Interfacce dell'archivio simboli di diagnostica</span><span class="sxs-lookup"><span data-stu-id="50c25-116">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)  
 [<span data-ttu-id="50c25-117">Interfaccia ISymUnmanagedWriter3</span><span class="sxs-lookup"><span data-stu-id="50c25-117">ISymUnmanagedWriter3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-interface.md)

---
title: Interfaccia ISymUnmanagedWriter4
ms.date: 03/30/2017
ms.assetid: 4af5e8c0-987d-405e-b934-8b9e70fcae6e
ms.openlocfilehash: eaf2e8e60d9812ab6a31fb3b9050cbaae0f1a9d7
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83609469"
---
# <a name="isymunmanagedwriter4-interface"></a><span data-ttu-id="e9b3d-102">Interfaccia ISymUnmanagedWriter4</span><span class="sxs-lookup"><span data-stu-id="e9b3d-102">ISymUnmanagedWriter4 Interface</span></span>
<span data-ttu-id="e9b3d-103">Interfaccia ISymUnmanagedWriter4.</span><span class="sxs-lookup"><span data-stu-id="e9b3d-103">ISymUnmanagedWriter4 interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9b3d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e9b3d-104">Syntax</span></span>  
  
```idl  
[object,uuid(BC7E3F53-F458-4C23-9DBD-A189E6E96594),pointer_default(unique)]interface ISymUnmanagedWriter4 : ISymUnmanagedWriter3  
```  
  
## <a name="methods"></a><span data-ttu-id="e9b3d-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="e9b3d-105">Methods</span></span>  
 <span data-ttu-id="e9b3d-106">Per l'interfaccia sono disponibili i seguenti metodi:</span><span class="sxs-lookup"><span data-stu-id="e9b3d-106">This interface contains the following methods:</span></span>  
  
|<span data-ttu-id="e9b3d-107">Metodo</span><span class="sxs-lookup"><span data-stu-id="e9b3d-107">Method</span></span>|<span data-ttu-id="e9b3d-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e9b3d-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e9b3d-109">Metodo GetDebugInfoWithPadding</span><span class="sxs-lookup"><span data-stu-id="e9b3d-109">GetDebugInfoWithPadding Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter4-getdebuginfowithpadding-method.md)|<span data-ttu-id="e9b3d-110">Funziona allo stesso modo del [Metodo GetDebugInfo](isymunmanagedwriter-getdebuginfo-method.md) , con la differenza che la stringa di percorso viene riempita con zeri che seguono il carattere null di terminazione per fare in modo che i dati della stringa siano di dimensioni fisse `MAX_PATH` .</span><span class="sxs-lookup"><span data-stu-id="e9b3d-110">Functions the same as [GetDebugInfo Method](isymunmanagedwriter-getdebuginfo-method.md) except that the path string is padded with zeros following the terminating null character to make the string data a fixed size of `MAX_PATH`.</span></span> <span data-ttu-id="e9b3d-111">La spaziatura interna viene specificata solo se la lunghezza della stringa di percorso è minore di `MAX_PATH` .</span><span class="sxs-lookup"><span data-stu-id="e9b3d-111">Padding is only given if the path string length itself is less than `MAX_PATH`.</span></span><br /><br /> <span data-ttu-id="e9b3d-112">In questo modo è più semplice scrivere strumenti che differenziano i file PE.</span><span class="sxs-lookup"><span data-stu-id="e9b3d-112">This makes it easier to write tools that difference PE files.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e9b3d-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e9b3d-113">Requirements</span></span>  
 <span data-ttu-id="e9b3d-114">**Intestazione:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="e9b3d-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9b3d-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e9b3d-115">See also</span></span>

- [<span data-ttu-id="e9b3d-116">Interfacce dell'archivio dei simboli di diagnostica</span><span class="sxs-lookup"><span data-stu-id="e9b3d-116">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="e9b3d-117">Interfaccia ISymUnmanagedWriter3</span><span class="sxs-lookup"><span data-stu-id="e9b3d-117">ISymUnmanagedWriter3 Interface</span></span>](isymunmanagedwriter3-interface.md)

---
title: Interfaccia ISymUnmanagedWriter4
ms.date: 03/30/2017
ms.assetid: 4af5e8c0-987d-405e-b934-8b9e70fcae6e
ms.openlocfilehash: a656777461c50b5a1593917278eb54abda982dc2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134572"
---
# <a name="isymunmanagedwriter4-interface"></a><span data-ttu-id="a3dbe-102">Interfaccia ISymUnmanagedWriter4</span><span class="sxs-lookup"><span data-stu-id="a3dbe-102">ISymUnmanagedWriter4 Interface</span></span>
<span data-ttu-id="a3dbe-103">Interfaccia ISymUnmanagedWriter4.</span><span class="sxs-lookup"><span data-stu-id="a3dbe-103">ISymUnmanagedWriter4 interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a3dbe-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a3dbe-104">Syntax</span></span>  
  
```idl  
[object,uuid(BC7E3F53-F458-4C23-9DBD-A189E6E96594),pointer_default(unique)]interface ISymUnmanagedWriter4 : ISymUnmanagedWriter3  
```  
  
## <a name="methods"></a><span data-ttu-id="a3dbe-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="a3dbe-105">Methods</span></span>  
 <span data-ttu-id="a3dbe-106">Per l'interfaccia sono disponibili i seguenti metodi:</span><span class="sxs-lookup"><span data-stu-id="a3dbe-106">This interface contains the following methods:</span></span>  
  
|<span data-ttu-id="a3dbe-107">Metodo</span><span class="sxs-lookup"><span data-stu-id="a3dbe-107">Method</span></span>|<span data-ttu-id="a3dbe-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a3dbe-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a3dbe-109">Metodo GetDebugInfoWithPadding</span><span class="sxs-lookup"><span data-stu-id="a3dbe-109">GetDebugInfoWithPadding Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter4-getdebuginfowithpadding-method.md)|<span data-ttu-id="a3dbe-110">Funziona allo stesso modo del [Metodo GetDebugInfo](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-getdebuginfo-method.md) , con la differenza che la stringa di percorso viene riempita con zeri che seguono il carattere null di terminazione per fare in modo che i dati della stringa siano di dimensioni fisse `MAX_PATH`.</span><span class="sxs-lookup"><span data-stu-id="a3dbe-110">Functions the same as [GetDebugInfo Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-getdebuginfo-method.md) except that the path string is padded with zeros following the terminating null character to make the string data a fixed size of `MAX_PATH`.</span></span> <span data-ttu-id="a3dbe-111">La spaziatura interna viene specificata solo se la lunghezza della stringa di percorso è minore di `MAX_PATH`.</span><span class="sxs-lookup"><span data-stu-id="a3dbe-111">Padding is only given if the path string length itself is less than `MAX_PATH`.</span></span><br /><br /> <span data-ttu-id="a3dbe-112">In questo modo è più semplice scrivere strumenti che differenziano i file PE.</span><span class="sxs-lookup"><span data-stu-id="a3dbe-112">This makes it easier to write tools that difference PE files.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a3dbe-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a3dbe-113">Requirements</span></span>  
 <span data-ttu-id="a3dbe-114">**Intestazione:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="a3dbe-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3dbe-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a3dbe-115">See also</span></span>

- [<span data-ttu-id="a3dbe-116">Interfacce dell'archivio simboli di diagnostica</span><span class="sxs-lookup"><span data-stu-id="a3dbe-116">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="a3dbe-117">Interfaccia ISymUnmanagedWriter3</span><span class="sxs-lookup"><span data-stu-id="a3dbe-117">ISymUnmanagedWriter3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-interface.md)

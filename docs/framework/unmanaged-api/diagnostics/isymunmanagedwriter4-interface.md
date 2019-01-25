---
title: Interfaccia ISymUnmanagedWriter4
ms.date: 03/30/2017
ms.assetid: 4af5e8c0-987d-405e-b934-8b9e70fcae6e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8a5e44541a18f10588e899f59a166406c149691f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54650051"
---
# <a name="isymunmanagedwriter4-interface"></a><span data-ttu-id="d68e5-102">Interfaccia ISymUnmanagedWriter4</span><span class="sxs-lookup"><span data-stu-id="d68e5-102">ISymUnmanagedWriter4 Interface</span></span>
<span data-ttu-id="d68e5-103">Interfaccia ISymUnmanagedWriter4.</span><span class="sxs-lookup"><span data-stu-id="d68e5-103">ISymUnmanagedWriter4 interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d68e5-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d68e5-104">Syntax</span></span>  
  
```idl  
[object,uuid(BC7E3F53-F458-4C23-9DBD-A189E6E96594),pointer_default(unique)]interface ISymUnmanagedWriter4 : ISymUnmanagedWriter3  
```  
  
## <a name="methods"></a><span data-ttu-id="d68e5-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="d68e5-105">Methods</span></span>  
 <span data-ttu-id="d68e5-106">Per l'interfaccia sono disponibili i seguenti metodi:</span><span class="sxs-lookup"><span data-stu-id="d68e5-106">This interface contains the following methods:</span></span>  
  
|<span data-ttu-id="d68e5-107">Metodo</span><span class="sxs-lookup"><span data-stu-id="d68e5-107">Method</span></span>|<span data-ttu-id="d68e5-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d68e5-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d68e5-109">Metodo GetDebugInfoWithPadding</span><span class="sxs-lookup"><span data-stu-id="d68e5-109">GetDebugInfoWithPadding Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter4-getdebuginfowithpadding-method.md)|<span data-ttu-id="d68e5-110">Equivale [metodo GetDebugInfo](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-getdebuginfo-method.md) ad eccezione del fatto che la stringa di percorso verrà anteposti tanti zeri che seguono il carattere null di terminazione per rendere i dati di stringa di una dimensione fissa di `MAX_PATH`.</span><span class="sxs-lookup"><span data-stu-id="d68e5-110">Functions the same as [GetDebugInfo Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-getdebuginfo-method.md) except that the path string is padded with zeros following the terminating null character to make the string data a fixed size of `MAX_PATH`.</span></span> <span data-ttu-id="d68e5-111">Spaziatura interna viene assegnata solo se la lunghezza della stringa percorso stesso è minore di `MAX_PATH`.</span><span class="sxs-lookup"><span data-stu-id="d68e5-111">Padding is only given if the path string length itself is less than `MAX_PATH`.</span></span><br /><br /> <span data-ttu-id="d68e5-112">Questo rende più semplice scrivere strumenti di tale file PE differenza.</span><span class="sxs-lookup"><span data-stu-id="d68e5-112">This makes it easier to write tools that difference PE files.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d68e5-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d68e5-113">Requirements</span></span>  
 <span data-ttu-id="d68e5-114">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="d68e5-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d68e5-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d68e5-115">See also</span></span>
- [<span data-ttu-id="d68e5-116">Interfacce dell'archivio simboli di diagnostica</span><span class="sxs-lookup"><span data-stu-id="d68e5-116">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="d68e5-117">Interfaccia ISymUnmanagedWriter3</span><span class="sxs-lookup"><span data-stu-id="d68e5-117">ISymUnmanagedWriter3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-interface.md)

---
title: Interfaccia ISymUnmanagedWriter4
ms.date: 03/30/2017
ms.assetid: 4af5e8c0-987d-405e-b934-8b9e70fcae6e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e5732cc08512df25a14cc8ea9dcaa03c56207dde
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61962332"
---
# <a name="isymunmanagedwriter4-interface"></a><span data-ttu-id="c3e03-102">Interfaccia ISymUnmanagedWriter4</span><span class="sxs-lookup"><span data-stu-id="c3e03-102">ISymUnmanagedWriter4 Interface</span></span>
<span data-ttu-id="c3e03-103">Interfaccia ISymUnmanagedWriter4.</span><span class="sxs-lookup"><span data-stu-id="c3e03-103">ISymUnmanagedWriter4 interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c3e03-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c3e03-104">Syntax</span></span>  
  
```idl  
[object,uuid(BC7E3F53-F458-4C23-9DBD-A189E6E96594),pointer_default(unique)]interface ISymUnmanagedWriter4 : ISymUnmanagedWriter3  
```  
  
## <a name="methods"></a><span data-ttu-id="c3e03-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="c3e03-105">Methods</span></span>  
 <span data-ttu-id="c3e03-106">Per l'interfaccia sono disponibili i seguenti metodi:</span><span class="sxs-lookup"><span data-stu-id="c3e03-106">This interface contains the following methods:</span></span>  
  
|<span data-ttu-id="c3e03-107">Metodo</span><span class="sxs-lookup"><span data-stu-id="c3e03-107">Method</span></span>|<span data-ttu-id="c3e03-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c3e03-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c3e03-109">Metodo GetDebugInfoWithPadding</span><span class="sxs-lookup"><span data-stu-id="c3e03-109">GetDebugInfoWithPadding Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter4-getdebuginfowithpadding-method.md)|<span data-ttu-id="c3e03-110">Equivale [metodo GetDebugInfo](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-getdebuginfo-method.md) ad eccezione del fatto che la stringa di percorso verrà anteposti tanti zeri che seguono il carattere null di terminazione per rendere i dati di stringa di una dimensione fissa di `MAX_PATH`.</span><span class="sxs-lookup"><span data-stu-id="c3e03-110">Functions the same as [GetDebugInfo Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-getdebuginfo-method.md) except that the path string is padded with zeros following the terminating null character to make the string data a fixed size of `MAX_PATH`.</span></span> <span data-ttu-id="c3e03-111">Spaziatura interna viene assegnata solo se la lunghezza della stringa percorso stesso è minore di `MAX_PATH`.</span><span class="sxs-lookup"><span data-stu-id="c3e03-111">Padding is only given if the path string length itself is less than `MAX_PATH`.</span></span><br /><br /> <span data-ttu-id="c3e03-112">Questo rende più semplice scrivere strumenti di tale file PE differenza.</span><span class="sxs-lookup"><span data-stu-id="c3e03-112">This makes it easier to write tools that difference PE files.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c3e03-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c3e03-113">Requirements</span></span>  
 <span data-ttu-id="c3e03-114">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="c3e03-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3e03-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c3e03-115">See also</span></span>

- [<span data-ttu-id="c3e03-116">Interfacce dell'archivio simboli di diagnostica</span><span class="sxs-lookup"><span data-stu-id="c3e03-116">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="c3e03-117">Interfaccia ISymUnmanagedWriter3</span><span class="sxs-lookup"><span data-stu-id="c3e03-117">ISymUnmanagedWriter3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-interface.md)

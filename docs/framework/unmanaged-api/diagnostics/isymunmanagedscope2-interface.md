---
title: Interfaccia ISymUnmanagedScope2
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope2
helpviewer_keywords:
- ISymUnmanagedScope2 interface [.NET Framework debugging]
ms.assetid: 2ed6a387-ba45-483e-9a1e-b0c69f67998b
topic_type:
- apiref
ms.openlocfilehash: 886ba693183a6b99eb03635e95a9661d105de40e
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83610860"
---
# <a name="isymunmanagedscope2-interface"></a><span data-ttu-id="ef4cf-102">Interfaccia ISymUnmanagedScope2</span><span class="sxs-lookup"><span data-stu-id="ef4cf-102">ISymUnmanagedScope2 Interface</span></span>
<span data-ttu-id="ef4cf-103">Rappresenta un ambito lessicale all'interno di un metodo.</span><span class="sxs-lookup"><span data-stu-id="ef4cf-103">Represents a lexical scope within a method.</span></span> <span data-ttu-id="ef4cf-104">Questa interfaccia estende l'interfaccia [ISymUnmanagedScope](isymunmanagedscope-interface.md) con metodi che ottengono informazioni sulle costanti definite nell'ambito.</span><span class="sxs-lookup"><span data-stu-id="ef4cf-104">This interface extends the [ISymUnmanagedScope](isymunmanagedscope-interface.md) interface with methods that get information about constants defined within the scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ef4cf-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="ef4cf-105">Methods</span></span>  
  
|<span data-ttu-id="ef4cf-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="ef4cf-106">Method</span></span>|<span data-ttu-id="ef4cf-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ef4cf-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ef4cf-108">Metodo GetConstantCount</span><span class="sxs-lookup"><span data-stu-id="ef4cf-108">GetConstantCount Method</span></span>](isymunmanagedscope2-getconstantcount-method.md)|<span data-ttu-id="ef4cf-109">Ottiene un conteggio delle costanti definite in questo ambito.</span><span class="sxs-lookup"><span data-stu-id="ef4cf-109">Gets a count of the constants defined within this scope.</span></span>|  
|[<span data-ttu-id="ef4cf-110">Metodo GetConstants</span><span class="sxs-lookup"><span data-stu-id="ef4cf-110">GetConstants Method</span></span>](isymunmanagedscope2-getconstants-method.md)|<span data-ttu-id="ef4cf-111">Ottiene le costanti locali definite all'interno di questo ambito.</span><span class="sxs-lookup"><span data-stu-id="ef4cf-111">Gets the local constants defined within this scope.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ef4cf-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ef4cf-112">Requirements</span></span>  
 <span data-ttu-id="ef4cf-113">**Intestazione:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="ef4cf-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef4cf-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ef4cf-114">See also</span></span>

- [<span data-ttu-id="ef4cf-115">Interfacce dell'archivio dei simboli di diagnostica</span><span class="sxs-lookup"><span data-stu-id="ef4cf-115">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="ef4cf-116">Interfaccia ISymUnmanagedScope</span><span class="sxs-lookup"><span data-stu-id="ef4cf-116">ISymUnmanagedScope Interface</span></span>](isymunmanagedscope-interface.md)

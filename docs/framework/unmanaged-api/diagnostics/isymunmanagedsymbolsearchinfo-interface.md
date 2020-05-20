---
title: Interfaccia ISymUnmanagedSymbolSearchInfo
ms.date: 03/30/2017
api_name:
- ISymUnmanagedSymbolSearchInfo
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedSymbolSearchInfo
helpviewer_keywords:
- ISymUnmanagedSymbolSearchInfo interface [.NET Framework debugging]
ms.assetid: 30817373-0a21-49c1-a0c4-8e8daeecb8db
topic_type:
- apiref
ms.openlocfilehash: 308c501e17446719067d2dc0580d698c1770bf53
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83610665"
---
# <a name="isymunmanagedsymbolsearchinfo-interface"></a><span data-ttu-id="5d75e-102">Interfaccia ISymUnmanagedSymbolSearchInfo</span><span class="sxs-lookup"><span data-stu-id="5d75e-102">ISymUnmanagedSymbolSearchInfo Interface</span></span>
<span data-ttu-id="5d75e-103">Fornisce metodi che consentono di ottenere informazioni sul percorso di ricerca.</span><span class="sxs-lookup"><span data-stu-id="5d75e-103">Provides methods that get information about the search path.</span></span> <span data-ttu-id="5d75e-104">Ottenere questa interfaccia chiamando `QueryInterface` su un oggetto che implementa l'interfaccia [ISymUnmanagedReader](isymunmanagedreader-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="5d75e-104">Obtain this interface by calling `QueryInterface` on an object that implements the [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5d75e-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="5d75e-105">Methods</span></span>  
  
|<span data-ttu-id="5d75e-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="5d75e-106">Method</span></span>|<span data-ttu-id="5d75e-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5d75e-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5d75e-108">Metodo GetHRESULT</span><span class="sxs-lookup"><span data-stu-id="5d75e-108">GetHRESULT Method</span></span>](isymunmanagedsymbolsearchinfo-gethresult-method.md)|<span data-ttu-id="5d75e-109">Ottiene HRESULT.</span><span class="sxs-lookup"><span data-stu-id="5d75e-109">Gets the HRESULT.</span></span>|  
|[<span data-ttu-id="5d75e-110">Metodo GetSearchPath</span><span class="sxs-lookup"><span data-stu-id="5d75e-110">GetSearchPath Method</span></span>](isymunmanagedsymbolsearchinfo-getsearchpath-method.md)|<span data-ttu-id="5d75e-111">Ottiene il percorso di ricerca.</span><span class="sxs-lookup"><span data-stu-id="5d75e-111">Gets the search path.</span></span>|  
|[<span data-ttu-id="5d75e-112">Metodo GetSearchPathLength</span><span class="sxs-lookup"><span data-stu-id="5d75e-112">GetSearchPathLength Method</span></span>](isymunmanagedsymbolsearchinfo-getsearchpathlength-method.md)|<span data-ttu-id="5d75e-113">Ottiene la lunghezza del percorso di ricerca.</span><span class="sxs-lookup"><span data-stu-id="5d75e-113">Gets the search path length.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5d75e-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5d75e-114">Requirements</span></span>  
 <span data-ttu-id="5d75e-115">**Intestazione:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="5d75e-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d75e-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5d75e-116">See also</span></span>

- [<span data-ttu-id="5d75e-117">Interfacce dell'archivio dei simboli di diagnostica</span><span class="sxs-lookup"><span data-stu-id="5d75e-117">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)

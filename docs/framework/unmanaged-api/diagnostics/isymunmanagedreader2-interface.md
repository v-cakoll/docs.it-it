---
title: Interfaccia ISymUnmanagedReader2
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader2
helpviewer_keywords:
- ISymUnmanagedReader2 interface [.NET Framework debugging]
ms.assetid: a01a881b-82a3-4b3e-a3a9-9dc305c2e5f7
topic_type:
- apiref
ms.openlocfilehash: a07c75e14244fb5bdf72ff2b0d344ae27672ef89
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448262"
---
# <a name="isymunmanagedreader2-interface"></a><span data-ttu-id="56290-102">Interfaccia ISymUnmanagedReader2</span><span class="sxs-lookup"><span data-stu-id="56290-102">ISymUnmanagedReader2 Interface</span></span>
<span data-ttu-id="56290-103">Rappresenta un lettore di simboli che fornisce l'accesso a documenti, metodi e variabili all'interno di un archivio di simboli.</span><span class="sxs-lookup"><span data-stu-id="56290-103">Represents a symbol reader that provides access to documents, methods, and variables within a symbol store.</span></span> <span data-ttu-id="56290-104">Questa interfaccia estende l'interfaccia [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="56290-104">This interface extends the [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="56290-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="56290-105">Methods</span></span>  
  
|<span data-ttu-id="56290-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="56290-106">Method</span></span>|<span data-ttu-id="56290-107">description</span><span class="sxs-lookup"><span data-stu-id="56290-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="56290-108">Metodo GetMethodByVersionPreRemap</span><span class="sxs-lookup"><span data-stu-id="56290-108">GetMethodByVersionPreRemap Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-getmethodbyversionpreremap-method.md)|<span data-ttu-id="56290-109">Ottenere un metodo del lettore di simboli, dato un token del metodo e un numero di versione di modifica e continuazione.</span><span class="sxs-lookup"><span data-stu-id="56290-109">Get a symbol reader method, given a method token and an edit-and-continue version number.</span></span>|  
|[<span data-ttu-id="56290-110">Metodo GetMethodsInDocument</span><span class="sxs-lookup"><span data-stu-id="56290-110">GetMethodsInDocument Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-getmethodsindocument-method.md)|<span data-ttu-id="56290-111">Ottiene tutti i metodi che dispongono di informazioni sulla riga nel documento specificato.</span><span class="sxs-lookup"><span data-stu-id="56290-111">Gets every method that has line information in the provided document.</span></span>|  
|[<span data-ttu-id="56290-112">Metodo GetSymAttributePreRemap</span><span class="sxs-lookup"><span data-stu-id="56290-112">GetSymAttributePreRemap Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-getsymattributepreremap-method.md)|<span data-ttu-id="56290-113">Ottiene un attributo personalizzato in base al nome.</span><span class="sxs-lookup"><span data-stu-id="56290-113">Gets a custom attribute based upon its name.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="56290-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="56290-114">Requirements</span></span>  
 <span data-ttu-id="56290-115">**Intestazione:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="56290-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56290-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="56290-116">See also</span></span>

- [<span data-ttu-id="56290-117">Interfacce dell'archivio simboli di diagnostica</span><span class="sxs-lookup"><span data-stu-id="56290-117">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="56290-118">Interfaccia ISymUnmanagedReader</span><span class="sxs-lookup"><span data-stu-id="56290-118">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)

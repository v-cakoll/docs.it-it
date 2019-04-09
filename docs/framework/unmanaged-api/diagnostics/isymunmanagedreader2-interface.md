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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 890053e1bf2e0648a41cca718e94edcf21c7e612
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59165984"
---
# <a name="isymunmanagedreader2-interface"></a><span data-ttu-id="52c79-102">Interfaccia ISymUnmanagedReader2</span><span class="sxs-lookup"><span data-stu-id="52c79-102">ISymUnmanagedReader2 Interface</span></span>
<span data-ttu-id="52c79-103">Rappresenta un lettore di simboli che fornisce accesso ai documenti, metodi e le variabili all'interno di un archivio simboli.</span><span class="sxs-lookup"><span data-stu-id="52c79-103">Represents a symbol reader that provides access to documents, methods, and variables within a symbol store.</span></span> <span data-ttu-id="52c79-104">Questa interfaccia estende la [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) interfaccia.</span><span class="sxs-lookup"><span data-stu-id="52c79-104">This interface extends the [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="52c79-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="52c79-105">Methods</span></span>  
  
|<span data-ttu-id="52c79-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="52c79-106">Method</span></span>|<span data-ttu-id="52c79-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="52c79-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="52c79-108">Metodo GetMethodByVersionPreRemap</span><span class="sxs-lookup"><span data-stu-id="52c79-108">GetMethodByVersionPreRemap Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-getmethodbyversionpreremap-method.md)|<span data-ttu-id="52c79-109">Ottenere un metodo del lettore di simboli, di un token di metodo e un numero di versione di modifica e continuazione.</span><span class="sxs-lookup"><span data-stu-id="52c79-109">Get a symbol reader method, given a method token and an edit-and-continue version number.</span></span>|  
|[<span data-ttu-id="52c79-110">Metodo GetMethodsInDocument</span><span class="sxs-lookup"><span data-stu-id="52c79-110">GetMethodsInDocument Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-getmethodsindocument-method.md)|<span data-ttu-id="52c79-111">Ottiene i metodi che contiene informazioni sulla riga del documento specificato.</span><span class="sxs-lookup"><span data-stu-id="52c79-111">Gets every method that has line information in the provided document.</span></span>|  
|[<span data-ttu-id="52c79-112">Metodo GetSymAttributePreRemap</span><span class="sxs-lookup"><span data-stu-id="52c79-112">GetSymAttributePreRemap Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-getsymattributepreremap-method.md)|<span data-ttu-id="52c79-113">Ottiene un attributo personalizzato in base al relativo nome.</span><span class="sxs-lookup"><span data-stu-id="52c79-113">Gets a custom attribute based upon its name.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="52c79-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="52c79-114">Requirements</span></span>  
 <span data-ttu-id="52c79-115">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="52c79-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52c79-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="52c79-116">See also</span></span>

- [<span data-ttu-id="52c79-117">Interfacce dell'archivio dei simboli di diagnostica</span><span class="sxs-lookup"><span data-stu-id="52c79-117">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="52c79-118">Interfaccia ISymUnmanagedReader</span><span class="sxs-lookup"><span data-stu-id="52c79-118">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)

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
ms.openlocfilehash: d4c5ff46d37b1292059b18920abd8042c18bbf31
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615397"
---
# <a name="isymunmanagedreader2-interface"></a><span data-ttu-id="1303a-102">Interfaccia ISymUnmanagedReader2</span><span class="sxs-lookup"><span data-stu-id="1303a-102">ISymUnmanagedReader2 Interface</span></span>
<span data-ttu-id="1303a-103">Rappresenta un lettore di simboli che fornisce l'accesso a documenti, metodi e variabili all'interno di un archivio di simboli.</span><span class="sxs-lookup"><span data-stu-id="1303a-103">Represents a symbol reader that provides access to documents, methods, and variables within a symbol store.</span></span> <span data-ttu-id="1303a-104">Questa interfaccia estende l'interfaccia [ISymUnmanagedReader](isymunmanagedreader-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="1303a-104">This interface extends the [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1303a-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="1303a-105">Methods</span></span>  
  
|<span data-ttu-id="1303a-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="1303a-106">Method</span></span>|<span data-ttu-id="1303a-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1303a-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1303a-108">Metodo GetMethodByVersionPreRemap</span><span class="sxs-lookup"><span data-stu-id="1303a-108">GetMethodByVersionPreRemap Method</span></span>](isymunmanagedreader2-getmethodbyversionpreremap-method.md)|<span data-ttu-id="1303a-109">Ottenere un metodo del lettore di simboli, dato un token del metodo e un numero di versione di modifica e continuazione.</span><span class="sxs-lookup"><span data-stu-id="1303a-109">Get a symbol reader method, given a method token and an edit-and-continue version number.</span></span>|  
|[<span data-ttu-id="1303a-110">Metodo GetMethodsInDocument</span><span class="sxs-lookup"><span data-stu-id="1303a-110">GetMethodsInDocument Method</span></span>](isymunmanagedreader2-getmethodsindocument-method.md)|<span data-ttu-id="1303a-111">Ottiene tutti i metodi che dispongono di informazioni sulla riga nel documento specificato.</span><span class="sxs-lookup"><span data-stu-id="1303a-111">Gets every method that has line information in the provided document.</span></span>|  
|[<span data-ttu-id="1303a-112">Metodo GetSymAttributePreRemap</span><span class="sxs-lookup"><span data-stu-id="1303a-112">GetSymAttributePreRemap Method</span></span>](isymunmanagedreader2-getsymattributepreremap-method.md)|<span data-ttu-id="1303a-113">Ottiene un attributo personalizzato in base al nome.</span><span class="sxs-lookup"><span data-stu-id="1303a-113">Gets a custom attribute based upon its name.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1303a-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1303a-114">Requirements</span></span>  
 <span data-ttu-id="1303a-115">**Intestazione:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="1303a-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1303a-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1303a-116">See also</span></span>

- [<span data-ttu-id="1303a-117">Interfacce dell'archivio dei simboli di diagnostica</span><span class="sxs-lookup"><span data-stu-id="1303a-117">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="1303a-118">Interfaccia ISymUnmanagedReader</span><span class="sxs-lookup"><span data-stu-id="1303a-118">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)

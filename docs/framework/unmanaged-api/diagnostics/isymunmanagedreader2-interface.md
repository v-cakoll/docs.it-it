---
title: Interfaccia ISymUnmanagedReader2
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedReader2
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedReader2
helpviewer_keywords: ISymUnmanagedReader2 interface [.NET Framework debugging]
ms.assetid: a01a881b-82a3-4b3e-a3a9-9dc305c2e5f7
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 93f4b88d891d7b5c1d92006276a290841372aad7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedreader2-interface"></a><span data-ttu-id="595ee-102">Interfaccia ISymUnmanagedReader2</span><span class="sxs-lookup"><span data-stu-id="595ee-102">ISymUnmanagedReader2 Interface</span></span>
<span data-ttu-id="595ee-103">Rappresenta un lettore di simboli che fornisce l'accesso a documenti, metodi e variabili all'interno di un archivio dei simboli.</span><span class="sxs-lookup"><span data-stu-id="595ee-103">Represents a symbol reader that provides access to documents, methods, and variables within a symbol store.</span></span> <span data-ttu-id="595ee-104">Questa interfaccia estende il [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) interfaccia.</span><span class="sxs-lookup"><span data-stu-id="595ee-104">This interface extends the [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="595ee-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="595ee-105">Methods</span></span>  
  
|<span data-ttu-id="595ee-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="595ee-106">Method</span></span>|<span data-ttu-id="595ee-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="595ee-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="595ee-108">Metodo GetMethodByVersionPreRemap</span><span class="sxs-lookup"><span data-stu-id="595ee-108">GetMethodByVersionPreRemap Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-getmethodbyversionpreremap-method.md)|<span data-ttu-id="595ee-109">Ottenere un metodo del lettore di simboli, dato un token di metodo e un numero di versione di modifica e continuazione.</span><span class="sxs-lookup"><span data-stu-id="595ee-109">Get a symbol reader method, given a method token and an edit-and-continue version number.</span></span>|  
|[<span data-ttu-id="595ee-110">Metodo GetMethodsInDocument</span><span class="sxs-lookup"><span data-stu-id="595ee-110">GetMethodsInDocument Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-getmethodsindocument-method.md)|<span data-ttu-id="595ee-111">Ottiene i metodi che contiene informazioni sulla riga del documento specificato.</span><span class="sxs-lookup"><span data-stu-id="595ee-111">Gets every method that has line information in the provided document.</span></span>|  
|[<span data-ttu-id="595ee-112">Metodo GetSymAttributePreRemap</span><span class="sxs-lookup"><span data-stu-id="595ee-112">GetSymAttributePreRemap Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-getsymattributepreremap-method.md)|<span data-ttu-id="595ee-113">Ottiene un attributo personalizzato in base al relativo nome.</span><span class="sxs-lookup"><span data-stu-id="595ee-113">Gets a custom attribute based upon its name.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="595ee-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="595ee-114">Requirements</span></span>  
 <span data-ttu-id="595ee-115">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="595ee-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="595ee-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="595ee-116">See Also</span></span>  
 [<span data-ttu-id="595ee-117">Interfacce dell'archivio simboli di diagnostica</span><span class="sxs-lookup"><span data-stu-id="595ee-117">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)  
 [<span data-ttu-id="595ee-118">Interfaccia ISymUnmanagedReader</span><span class="sxs-lookup"><span data-stu-id="595ee-118">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)

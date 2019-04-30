---
title: Interfaccia ISymENCUnmanagedMethod
ms.date: 03/30/2017
api_name:
- ISymENCUnmanagedMethod
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymENCUnmanagedMethod
helpviewer_keywords:
- ISymENCUnmanagedMethod interface [.NET Framework debugging]
ms.assetid: faebf594-67d5-4abf-b9c1-547fd3a1ff87
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4474269688094ea6c81b06659727acfb9c2ad6c3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61940257"
---
# <a name="isymencunmanagedmethod-interface"></a><span data-ttu-id="e5a61-102">Interfaccia ISymENCUnmanagedMethod</span><span class="sxs-lookup"><span data-stu-id="e5a61-102">ISymENCUnmanagedMethod Interface</span></span>
<span data-ttu-id="e5a61-103">Vengono fornite informazioni per la funzionalità Modifica e continuazione.</span><span class="sxs-lookup"><span data-stu-id="e5a61-103">Provides information for the Edit and Continue feature.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e5a61-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="e5a61-104">Methods</span></span>  
  
|<span data-ttu-id="e5a61-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="e5a61-105">Method</span></span>|<span data-ttu-id="e5a61-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e5a61-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e5a61-107">Metodo GetDocumentsForMethod</span><span class="sxs-lookup"><span data-stu-id="e5a61-107">GetDocumentsForMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-getdocumentsformethod-method.md)|<span data-ttu-id="e5a61-108">Ottiene i documenti che questo metodo è incluse righe.</span><span class="sxs-lookup"><span data-stu-id="e5a61-108">Gets the documents that this method has lines in.</span></span>|  
|[<span data-ttu-id="e5a61-109">Metodo GetDocumentsForMethodCount</span><span class="sxs-lookup"><span data-stu-id="e5a61-109">GetDocumentsForMethodCount Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-getdocumentsformethodcount-method.md)|<span data-ttu-id="e5a61-110">Ottiene il numero di documenti che questo metodo è incluse righe.</span><span class="sxs-lookup"><span data-stu-id="e5a61-110">Gets the number of documents that this method has lines in.</span></span>|  
|[<span data-ttu-id="e5a61-111">Metodo GetFileNameFromOffset</span><span class="sxs-lookup"><span data-stu-id="e5a61-111">GetFileNameFromOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-getfilenamefromoffset-method.md)|<span data-ttu-id="e5a61-112">Ottiene il nome del file per la riga associata a un offset.</span><span class="sxs-lookup"><span data-stu-id="e5a61-112">Gets the file name for the line associated with an offset.</span></span>|  
|[<span data-ttu-id="e5a61-113">Metodo GetLineFromOffset</span><span class="sxs-lookup"><span data-stu-id="e5a61-113">GetLineFromOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-getlinefromoffset-method.md)|<span data-ttu-id="e5a61-114">Ottiene le informazioni della riga associate a un offset.</span><span class="sxs-lookup"><span data-stu-id="e5a61-114">Gets the line information associated with an offset.</span></span>|  
|[<span data-ttu-id="e5a61-115">Metodo GetSourceExtentInDocument</span><span class="sxs-lookup"><span data-stu-id="e5a61-115">GetSourceExtentInDocument Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-getsourceextentindocument-method.md)|<span data-ttu-id="e5a61-116">Ottiene il valore più piccolo start riga e la riga finale per il metodo in un documento specifico.</span><span class="sxs-lookup"><span data-stu-id="e5a61-116">Gets the smallest start line and largest end line for the method in a specific document.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e5a61-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e5a61-117">Requirements</span></span>  
 <span data-ttu-id="e5a61-118">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="e5a61-118">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5a61-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e5a61-119">See also</span></span>

- [<span data-ttu-id="e5a61-120">Interfacce dell'archivio simboli di diagnostica</span><span class="sxs-lookup"><span data-stu-id="e5a61-120">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)

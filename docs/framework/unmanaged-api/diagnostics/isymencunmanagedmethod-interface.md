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
ms.openlocfilehash: f46aeed0a303278fd67265e471bfa13b43cede12
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54680187"
---
# <a name="isymencunmanagedmethod-interface"></a><span data-ttu-id="18778-102">Interfaccia ISymENCUnmanagedMethod</span><span class="sxs-lookup"><span data-stu-id="18778-102">ISymENCUnmanagedMethod Interface</span></span>
<span data-ttu-id="18778-103">Vengono fornite informazioni per la funzionalità Modifica e continuazione.</span><span class="sxs-lookup"><span data-stu-id="18778-103">Provides information for the Edit and Continue feature.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="18778-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="18778-104">Methods</span></span>  
  
|<span data-ttu-id="18778-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="18778-105">Method</span></span>|<span data-ttu-id="18778-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="18778-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="18778-107">Metodo GetDocumentsForMethod</span><span class="sxs-lookup"><span data-stu-id="18778-107">GetDocumentsForMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-getdocumentsformethod-method.md)|<span data-ttu-id="18778-108">Ottiene i documenti che questo metodo è incluse righe.</span><span class="sxs-lookup"><span data-stu-id="18778-108">Gets the documents that this method has lines in.</span></span>|  
|[<span data-ttu-id="18778-109">Metodo GetDocumentsForMethodCount</span><span class="sxs-lookup"><span data-stu-id="18778-109">GetDocumentsForMethodCount Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-getdocumentsformethodcount-method.md)|<span data-ttu-id="18778-110">Ottiene il numero di documenti che questo metodo è incluse righe.</span><span class="sxs-lookup"><span data-stu-id="18778-110">Gets the number of documents that this method has lines in.</span></span>|  
|[<span data-ttu-id="18778-111">Metodo GetFileNameFromOffset</span><span class="sxs-lookup"><span data-stu-id="18778-111">GetFileNameFromOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-getfilenamefromoffset-method.md)|<span data-ttu-id="18778-112">Ottiene il nome del file per la riga associata a un offset.</span><span class="sxs-lookup"><span data-stu-id="18778-112">Gets the file name for the line associated with an offset.</span></span>|  
|[<span data-ttu-id="18778-113">Metodo GetLineFromOffset</span><span class="sxs-lookup"><span data-stu-id="18778-113">GetLineFromOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-getlinefromoffset-method.md)|<span data-ttu-id="18778-114">Ottiene le informazioni della riga associate a un offset.</span><span class="sxs-lookup"><span data-stu-id="18778-114">Gets the line information associated with an offset.</span></span>|  
|[<span data-ttu-id="18778-115">Metodo GetSourceExtentInDocument</span><span class="sxs-lookup"><span data-stu-id="18778-115">GetSourceExtentInDocument Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-getsourceextentindocument-method.md)|<span data-ttu-id="18778-116">Ottiene il valore più piccolo start riga e la riga finale per il metodo in un documento specifico.</span><span class="sxs-lookup"><span data-stu-id="18778-116">Gets the smallest start line and largest end line for the method in a specific document.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="18778-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="18778-117">Requirements</span></span>  
 <span data-ttu-id="18778-118">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="18778-118">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18778-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="18778-119">See also</span></span>
- [<span data-ttu-id="18778-120">Interfacce dell'archivio simboli di diagnostica</span><span class="sxs-lookup"><span data-stu-id="18778-120">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)

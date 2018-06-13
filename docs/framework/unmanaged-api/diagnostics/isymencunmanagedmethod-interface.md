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
ms.openlocfilehash: 575c732cf1b1caf4700568a9d168463359d1ad7a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33425503"
---
# <a name="isymencunmanagedmethod-interface"></a><span data-ttu-id="7cd3d-102">Interfaccia ISymENCUnmanagedMethod</span><span class="sxs-lookup"><span data-stu-id="7cd3d-102">ISymENCUnmanagedMethod Interface</span></span>
<span data-ttu-id="7cd3d-103">Vengono fornite informazioni per la funzionalità Modifica e continuazione.</span><span class="sxs-lookup"><span data-stu-id="7cd3d-103">Provides information for the Edit and Continue feature.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7cd3d-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="7cd3d-104">Methods</span></span>  
  
|<span data-ttu-id="7cd3d-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="7cd3d-105">Method</span></span>|<span data-ttu-id="7cd3d-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7cd3d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7cd3d-107">Metodo GetDocumentsForMethod</span><span class="sxs-lookup"><span data-stu-id="7cd3d-107">GetDocumentsForMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-getdocumentsformethod-method.md)|<span data-ttu-id="7cd3d-108">Ottiene i documenti che questo metodo è incluse righe.</span><span class="sxs-lookup"><span data-stu-id="7cd3d-108">Gets the documents that this method has lines in.</span></span>|  
|[<span data-ttu-id="7cd3d-109">Metodo GetDocumentsForMethodCount</span><span class="sxs-lookup"><span data-stu-id="7cd3d-109">GetDocumentsForMethodCount Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-getdocumentsformethodcount-method.md)|<span data-ttu-id="7cd3d-110">Ottiene il numero di documenti che questo metodo è incluse righe.</span><span class="sxs-lookup"><span data-stu-id="7cd3d-110">Gets the number of documents that this method has lines in.</span></span>|  
|[<span data-ttu-id="7cd3d-111">Metodo GetFileNameFromOffset</span><span class="sxs-lookup"><span data-stu-id="7cd3d-111">GetFileNameFromOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-getfilenamefromoffset-method.md)|<span data-ttu-id="7cd3d-112">Ottiene il nome del file per la riga associata a un offset.</span><span class="sxs-lookup"><span data-stu-id="7cd3d-112">Gets the file name for the line associated with an offset.</span></span>|  
|[<span data-ttu-id="7cd3d-113">Metodo GetLineFromOffset</span><span class="sxs-lookup"><span data-stu-id="7cd3d-113">GetLineFromOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-getlinefromoffset-method.md)|<span data-ttu-id="7cd3d-114">Ottiene le informazioni sulla riga associate a un offset.</span><span class="sxs-lookup"><span data-stu-id="7cd3d-114">Gets the line information associated with an offset.</span></span>|  
|[<span data-ttu-id="7cd3d-115">Metodo GetSourceExtentInDocument</span><span class="sxs-lookup"><span data-stu-id="7cd3d-115">GetSourceExtentInDocument Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-getsourceextentindocument-method.md)|<span data-ttu-id="7cd3d-116">Ottiene il valore più piccolo start riga e la riga finale per il metodo in un documento specifico.</span><span class="sxs-lookup"><span data-stu-id="7cd3d-116">Gets the smallest start line and largest end line for the method in a specific document.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7cd3d-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7cd3d-117">Requirements</span></span>  
 <span data-ttu-id="7cd3d-118">**Intestazione:** CorSym. idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="7cd3d-118">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7cd3d-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7cd3d-119">See Also</span></span>  
 [<span data-ttu-id="7cd3d-120">Interfacce dell'archivio simboli di diagnostica</span><span class="sxs-lookup"><span data-stu-id="7cd3d-120">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)

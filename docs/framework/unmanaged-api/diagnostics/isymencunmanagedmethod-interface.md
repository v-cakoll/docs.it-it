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
ms.openlocfilehash: 54c8c7f5c3ba6b4afd4ff352a8afb947a92e2d61
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/16/2020
ms.locfileid: "83441877"
---
# <a name="isymencunmanagedmethod-interface"></a><span data-ttu-id="efae8-102">Interfaccia ISymENCUnmanagedMethod</span><span class="sxs-lookup"><span data-stu-id="efae8-102">ISymENCUnmanagedMethod Interface</span></span>
<span data-ttu-id="efae8-103">Fornisce informazioni per la funzionalità di modifica e continuazione.</span><span class="sxs-lookup"><span data-stu-id="efae8-103">Provides information for the Edit and Continue feature.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="efae8-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="efae8-104">Methods</span></span>  
  
|<span data-ttu-id="efae8-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="efae8-105">Method</span></span>|<span data-ttu-id="efae8-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="efae8-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="efae8-107">Metodo GetDocumentsForMethod</span><span class="sxs-lookup"><span data-stu-id="efae8-107">GetDocumentsForMethod Method</span></span>](isymencunmanagedmethod-getdocumentsformethod-method.md)|<span data-ttu-id="efae8-108">Ottiene i documenti in cui questo metodo contiene righe.</span><span class="sxs-lookup"><span data-stu-id="efae8-108">Gets the documents that this method has lines in.</span></span>|  
|[<span data-ttu-id="efae8-109">Metodo GetDocumentsForMethodCount</span><span class="sxs-lookup"><span data-stu-id="efae8-109">GetDocumentsForMethodCount Method</span></span>](isymencunmanagedmethod-getdocumentsformethodcount-method.md)|<span data-ttu-id="efae8-110">Ottiene il numero di documenti in cui questo metodo contiene righe.</span><span class="sxs-lookup"><span data-stu-id="efae8-110">Gets the number of documents that this method has lines in.</span></span>|  
|[<span data-ttu-id="efae8-111">Metodo GetFileNameFromOffset</span><span class="sxs-lookup"><span data-stu-id="efae8-111">GetFileNameFromOffset Method</span></span>](isymencunmanagedmethod-getfilenamefromoffset-method.md)|<span data-ttu-id="efae8-112">Ottiene il nome file per la riga associata a un offset.</span><span class="sxs-lookup"><span data-stu-id="efae8-112">Gets the file name for the line associated with an offset.</span></span>|  
|[<span data-ttu-id="efae8-113">Metodo GetLineFromOffset</span><span class="sxs-lookup"><span data-stu-id="efae8-113">GetLineFromOffset Method</span></span>](isymencunmanagedmethod-getlinefromoffset-method.md)|<span data-ttu-id="efae8-114">Ottiene le informazioni sulla riga associate a un offset.</span><span class="sxs-lookup"><span data-stu-id="efae8-114">Gets the line information associated with an offset.</span></span>|  
|[<span data-ttu-id="efae8-115">Metodo GetSourceExtentInDocument</span><span class="sxs-lookup"><span data-stu-id="efae8-115">GetSourceExtentInDocument Method</span></span>](isymencunmanagedmethod-getsourceextentindocument-method.md)|<span data-ttu-id="efae8-116">Ottiene la riga iniziale più piccola e la riga finale più grande per il metodo in un documento specifico.</span><span class="sxs-lookup"><span data-stu-id="efae8-116">Gets the smallest start line and largest end line for the method in a specific document.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="efae8-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="efae8-117">Requirements</span></span>  
 <span data-ttu-id="efae8-118">**Intestazione:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="efae8-118">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="efae8-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="efae8-119">See also</span></span>

- [<span data-ttu-id="efae8-120">Interfacce dell'archivio dei simboli di diagnostica</span><span class="sxs-lookup"><span data-stu-id="efae8-120">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)

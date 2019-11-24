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
ms.openlocfilehash: 47477bb473df8b568844d07bea704df681c9b95d
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448600"
---
# <a name="isymencunmanagedmethod-interface"></a><span data-ttu-id="16314-102">Interfaccia ISymENCUnmanagedMethod</span><span class="sxs-lookup"><span data-stu-id="16314-102">ISymENCUnmanagedMethod Interface</span></span>
<span data-ttu-id="16314-103">Provides information for the Edit and Continue feature.</span><span class="sxs-lookup"><span data-stu-id="16314-103">Provides information for the Edit and Continue feature.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="16314-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="16314-104">Methods</span></span>  
  
|<span data-ttu-id="16314-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="16314-105">Method</span></span>|<span data-ttu-id="16314-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="16314-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="16314-107">Metodo GetDocumentsForMethod</span><span class="sxs-lookup"><span data-stu-id="16314-107">GetDocumentsForMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-getdocumentsformethod-method.md)|<span data-ttu-id="16314-108">Gets the documents that this method has lines in.</span><span class="sxs-lookup"><span data-stu-id="16314-108">Gets the documents that this method has lines in.</span></span>|  
|[<span data-ttu-id="16314-109">Metodo GetDocumentsForMethodCount</span><span class="sxs-lookup"><span data-stu-id="16314-109">GetDocumentsForMethodCount Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-getdocumentsformethodcount-method.md)|<span data-ttu-id="16314-110">Gets the number of documents that this method has lines in.</span><span class="sxs-lookup"><span data-stu-id="16314-110">Gets the number of documents that this method has lines in.</span></span>|  
|[<span data-ttu-id="16314-111">Metodo GetFileNameFromOffset</span><span class="sxs-lookup"><span data-stu-id="16314-111">GetFileNameFromOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-getfilenamefromoffset-method.md)|<span data-ttu-id="16314-112">Gets the file name for the line associated with an offset.</span><span class="sxs-lookup"><span data-stu-id="16314-112">Gets the file name for the line associated with an offset.</span></span>|  
|[<span data-ttu-id="16314-113">Metodo GetLineFromOffset</span><span class="sxs-lookup"><span data-stu-id="16314-113">GetLineFromOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-getlinefromoffset-method.md)|<span data-ttu-id="16314-114">Gets the line information associated with an offset.</span><span class="sxs-lookup"><span data-stu-id="16314-114">Gets the line information associated with an offset.</span></span>|  
|[<span data-ttu-id="16314-115">Metodo GetSourceExtentInDocument</span><span class="sxs-lookup"><span data-stu-id="16314-115">GetSourceExtentInDocument Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-getsourceextentindocument-method.md)|<span data-ttu-id="16314-116">Gets the smallest start line and largest end line for the method in a specific document.</span><span class="sxs-lookup"><span data-stu-id="16314-116">Gets the smallest start line and largest end line for the method in a specific document.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="16314-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="16314-117">Requirements</span></span>  
 <span data-ttu-id="16314-118">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="16314-118">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16314-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="16314-119">See also</span></span>

- [<span data-ttu-id="16314-120">Interfacce dell'archivio simboli di diagnostica</span><span class="sxs-lookup"><span data-stu-id="16314-120">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)

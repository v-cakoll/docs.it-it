---
title: Interfaccia ISymUnmanagedVariable
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable
helpviewer_keywords:
- ISymUnmanagedVariable interface [.NET Framework debugging]
ms.assetid: 704c69ba-77bc-40d7-8c0c-400061686321
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 712eca7f3f9fec9c81e638802f5a664ec6469d53
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59164346"
---
# <a name="isymunmanagedvariable-interface"></a><span data-ttu-id="eb46c-102">Interfaccia ISymUnmanagedVariable</span><span class="sxs-lookup"><span data-stu-id="eb46c-102">ISymUnmanagedVariable Interface</span></span>
<span data-ttu-id="eb46c-103">Rappresenta una variabile, ad esempio un parametro, una variabile locale o un campo.</span><span class="sxs-lookup"><span data-stu-id="eb46c-103">Represents a variable, such as a parameter, a local variable, or a field.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="eb46c-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="eb46c-104">Methods</span></span>  
  
|<span data-ttu-id="eb46c-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="eb46c-105">Method</span></span>|<span data-ttu-id="eb46c-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="eb46c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="eb46c-107">Metodo GetAddressField1</span><span class="sxs-lookup"><span data-stu-id="eb46c-107">GetAddressField1 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield1-method.md)|<span data-ttu-id="eb46c-108">Ottiene il primo campo dell'indirizzo di questa variabile.</span><span class="sxs-lookup"><span data-stu-id="eb46c-108">Gets the first address field for this variable.</span></span> <span data-ttu-id="eb46c-109">Il significato dipende dal tipo di indirizzo.</span><span class="sxs-lookup"><span data-stu-id="eb46c-109">Its meaning depends on the kind of address.</span></span>|  
|[<span data-ttu-id="eb46c-110">Metodo GetAddressField2</span><span class="sxs-lookup"><span data-stu-id="eb46c-110">GetAddressField2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield2-method.md)|<span data-ttu-id="eb46c-111">Ottiene il secondo campo dell'indirizzo di questa variabile.</span><span class="sxs-lookup"><span data-stu-id="eb46c-111">Gets the second address field for this variable.</span></span> <span data-ttu-id="eb46c-112">Il significato dipende dal tipo di indirizzo.</span><span class="sxs-lookup"><span data-stu-id="eb46c-112">Its meaning depends on the kind of address.</span></span>|  
|[<span data-ttu-id="eb46c-113">Metodo GetAddressField3</span><span class="sxs-lookup"><span data-stu-id="eb46c-113">GetAddressField3 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield3-method.md)|<span data-ttu-id="eb46c-114">Ottiene il terzo campo dell'indirizzo di questa variabile.</span><span class="sxs-lookup"><span data-stu-id="eb46c-114">Gets the third address field for this variable.</span></span> <span data-ttu-id="eb46c-115">Il significato dipende dal tipo di indirizzo.</span><span class="sxs-lookup"><span data-stu-id="eb46c-115">Its meaning depends on the kind of address.</span></span>|  
|[<span data-ttu-id="eb46c-116">Metodo GetAddressKind</span><span class="sxs-lookup"><span data-stu-id="eb46c-116">GetAddressKind Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddresskind-method.md)|<span data-ttu-id="eb46c-117">Ottiene il tipo di indirizzo della variabile.</span><span class="sxs-lookup"><span data-stu-id="eb46c-117">Gets the kind of address of this variable.</span></span>|  
|[<span data-ttu-id="eb46c-118">Metodo GetAttributes</span><span class="sxs-lookup"><span data-stu-id="eb46c-118">GetAttributes Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getattributes-method.md)|<span data-ttu-id="eb46c-119">Ottiene i flag di attributo per questa variabile.</span><span class="sxs-lookup"><span data-stu-id="eb46c-119">Gets the attribute flags for this variable.</span></span>|  
|[<span data-ttu-id="eb46c-120">Metodo GetEndOffset</span><span class="sxs-lookup"><span data-stu-id="eb46c-120">GetEndOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getendoffset-method.md)|<span data-ttu-id="eb46c-121">Ottiene l'offset finale della variabile all'interno di relativo elemento padre.</span><span class="sxs-lookup"><span data-stu-id="eb46c-121">Gets the end offset of this variable within its parent.</span></span>|  
|[<span data-ttu-id="eb46c-122">Metodo GetName</span><span class="sxs-lookup"><span data-stu-id="eb46c-122">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getname-method.md)|<span data-ttu-id="eb46c-123">Ottiene il nome della variabile.</span><span class="sxs-lookup"><span data-stu-id="eb46c-123">Gets the name of this variable.</span></span>|  
|[<span data-ttu-id="eb46c-124">Metodo GetSignature</span><span class="sxs-lookup"><span data-stu-id="eb46c-124">GetSignature Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getsignature-method.md)|<span data-ttu-id="eb46c-125">Ottiene la firma della variabile.</span><span class="sxs-lookup"><span data-stu-id="eb46c-125">Gets the signature of this variable.</span></span>|  
|[<span data-ttu-id="eb46c-126">Metodo GetStartOffset</span><span class="sxs-lookup"><span data-stu-id="eb46c-126">GetStartOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getstartoffset-method.md)|<span data-ttu-id="eb46c-127">Ottiene l'offset di inizio di questa variabile all'interno di relativo elemento padre.</span><span class="sxs-lookup"><span data-stu-id="eb46c-127">Gets the start offset of this variable within its parent.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="eb46c-128">Requisiti</span><span class="sxs-lookup"><span data-stu-id="eb46c-128">Requirements</span></span>  
 <span data-ttu-id="eb46c-129">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="eb46c-129">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb46c-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="eb46c-130">See also</span></span>

- [<span data-ttu-id="eb46c-131">Interfacce dell'archivio simboli di diagnostica</span><span class="sxs-lookup"><span data-stu-id="eb46c-131">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)

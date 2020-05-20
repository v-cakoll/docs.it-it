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
ms.openlocfilehash: d05d4451e8fb75829b22e0a1b9c9afcb0607eb8b
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83610171"
---
# <a name="isymunmanagedvariable-interface"></a><span data-ttu-id="c0f61-102">Interfaccia ISymUnmanagedVariable</span><span class="sxs-lookup"><span data-stu-id="c0f61-102">ISymUnmanagedVariable Interface</span></span>
<span data-ttu-id="c0f61-103">Rappresenta una variabile, ad esempio un parametro, una variabile locale o un campo.</span><span class="sxs-lookup"><span data-stu-id="c0f61-103">Represents a variable, such as a parameter, a local variable, or a field.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c0f61-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="c0f61-104">Methods</span></span>  
  
|<span data-ttu-id="c0f61-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="c0f61-105">Method</span></span>|<span data-ttu-id="c0f61-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c0f61-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c0f61-107">Metodo GetAddressField1</span><span class="sxs-lookup"><span data-stu-id="c0f61-107">GetAddressField1 Method</span></span>](isymunmanagedvariable-getaddressfield1-method.md)|<span data-ttu-id="c0f61-108">Ottiene il primo campo dell'indirizzo per questa variabile.</span><span class="sxs-lookup"><span data-stu-id="c0f61-108">Gets the first address field for this variable.</span></span> <span data-ttu-id="c0f61-109">Il suo significato dipende dal tipo di indirizzo.</span><span class="sxs-lookup"><span data-stu-id="c0f61-109">Its meaning depends on the kind of address.</span></span>|  
|[<span data-ttu-id="c0f61-110">Metodo GetAddressField2</span><span class="sxs-lookup"><span data-stu-id="c0f61-110">GetAddressField2 Method</span></span>](isymunmanagedvariable-getaddressfield2-method.md)|<span data-ttu-id="c0f61-111">Ottiene il secondo campo dell'indirizzo per questa variabile.</span><span class="sxs-lookup"><span data-stu-id="c0f61-111">Gets the second address field for this variable.</span></span> <span data-ttu-id="c0f61-112">Il suo significato dipende dal tipo di indirizzo.</span><span class="sxs-lookup"><span data-stu-id="c0f61-112">Its meaning depends on the kind of address.</span></span>|  
|[<span data-ttu-id="c0f61-113">Metodo GetAddressField3</span><span class="sxs-lookup"><span data-stu-id="c0f61-113">GetAddressField3 Method</span></span>](isymunmanagedvariable-getaddressfield3-method.md)|<span data-ttu-id="c0f61-114">Ottiene il terzo campo dell'indirizzo per questa variabile.</span><span class="sxs-lookup"><span data-stu-id="c0f61-114">Gets the third address field for this variable.</span></span> <span data-ttu-id="c0f61-115">Il suo significato dipende dal tipo di indirizzo.</span><span class="sxs-lookup"><span data-stu-id="c0f61-115">Its meaning depends on the kind of address.</span></span>|  
|[<span data-ttu-id="c0f61-116">Metodo GetAddressKind</span><span class="sxs-lookup"><span data-stu-id="c0f61-116">GetAddressKind Method</span></span>](isymunmanagedvariable-getaddresskind-method.md)|<span data-ttu-id="c0f61-117">Ottiene il tipo di indirizzo della variabile.</span><span class="sxs-lookup"><span data-stu-id="c0f61-117">Gets the kind of address of this variable.</span></span>|  
|[<span data-ttu-id="c0f61-118">Metodo GetAttributes</span><span class="sxs-lookup"><span data-stu-id="c0f61-118">GetAttributes Method</span></span>](isymunmanagedvariable-getattributes-method.md)|<span data-ttu-id="c0f61-119">Ottiene i flag di attributo per questa variabile.</span><span class="sxs-lookup"><span data-stu-id="c0f61-119">Gets the attribute flags for this variable.</span></span>|  
|[<span data-ttu-id="c0f61-120">Metodo GetEndOffset</span><span class="sxs-lookup"><span data-stu-id="c0f61-120">GetEndOffset Method</span></span>](isymunmanagedvariable-getendoffset-method.md)|<span data-ttu-id="c0f61-121">Ottiene l'offset finale della variabile all'interno dell'elemento padre.</span><span class="sxs-lookup"><span data-stu-id="c0f61-121">Gets the end offset of this variable within its parent.</span></span>|  
|[<span data-ttu-id="c0f61-122">Metodo GetName</span><span class="sxs-lookup"><span data-stu-id="c0f61-122">GetName Method</span></span>](isymunmanagedvariable-getname-method.md)|<span data-ttu-id="c0f61-123">Ottiene il nome della variabile.</span><span class="sxs-lookup"><span data-stu-id="c0f61-123">Gets the name of this variable.</span></span>|  
|[<span data-ttu-id="c0f61-124">Metodo GetSignature</span><span class="sxs-lookup"><span data-stu-id="c0f61-124">GetSignature Method</span></span>](isymunmanagedvariable-getsignature-method.md)|<span data-ttu-id="c0f61-125">Ottiene la firma di questa variabile.</span><span class="sxs-lookup"><span data-stu-id="c0f61-125">Gets the signature of this variable.</span></span>|  
|[<span data-ttu-id="c0f61-126">Metodo GetStartOffset</span><span class="sxs-lookup"><span data-stu-id="c0f61-126">GetStartOffset Method</span></span>](isymunmanagedvariable-getstartoffset-method.md)|<span data-ttu-id="c0f61-127">Ottiene l'offset iniziale della variabile all'interno dell'elemento padre.</span><span class="sxs-lookup"><span data-stu-id="c0f61-127">Gets the start offset of this variable within its parent.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c0f61-128">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c0f61-128">Requirements</span></span>  
 <span data-ttu-id="c0f61-129">**Intestazione:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="c0f61-129">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0f61-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c0f61-130">See also</span></span>

- [<span data-ttu-id="c0f61-131">Interfacce dell'archivio dei simboli di diagnostica</span><span class="sxs-lookup"><span data-stu-id="c0f61-131">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)

---
title: Metodo ISymUnmanagedWriter::DefineParameter
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.DefineParameter
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::DefineParameter
helpviewer_keywords:
- DefineParameter method [.NET Framework debugging]
- ISymUnmanagedWriter::DefineParameter method [.NET Framework debugging]
ms.assetid: a8e3dd32-6a44-4371-9a74-f417b11998c8
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b81ee355fe375ca7a597d5f8f2fbf92f71e0bd9b
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57481457"
---
# <a name="isymunmanagedwriterdefineparameter-method"></a><span data-ttu-id="b4a0b-102">Metodo ISymUnmanagedWriter::DefineParameter</span><span class="sxs-lookup"><span data-stu-id="b4a0b-102">ISymUnmanagedWriter::DefineParameter Method</span></span>
<span data-ttu-id="b4a0b-103">Definisce un singolo parametro nel metodo corrente.</span><span class="sxs-lookup"><span data-stu-id="b4a0b-103">Defines a single parameter in the current method.</span></span> <span data-ttu-id="b4a0b-104">Il tipo di parametro deriva dalla posizione del parametro (sequenza) all'interno di firma del metodo.</span><span class="sxs-lookup"><span data-stu-id="b4a0b-104">The parameter type is taken from the parameter's position (sequence) within the method's signature.</span></span>  
  
 <span data-ttu-id="b4a0b-105">Se i parametri vengono definiti nei metadati per un determinato metodo, non è necessario definire nuovamente utilizzando questo metodo.</span><span class="sxs-lookup"><span data-stu-id="b4a0b-105">If parameters are defined in the metadata for a given method, you do not have to define them again by using this method.</span></span> <span data-ttu-id="b4a0b-106">I reader di simboli devono controllare i metadati normale per i parametri prima di controllare l'archivio dei simboli.</span><span class="sxs-lookup"><span data-stu-id="b4a0b-106">The symbol readers must check the normal metadata for the parameters before checking the symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4a0b-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b4a0b-107">Syntax</span></span>  
  
```  
HRESULT DefineParameter(  
    [in] const WCHAR  *name,  
    [in] ULONG32      attributes,  
    [in] ULONG32      sequence,  
    [in] ULONG32      addrKind,  
    [in] ULONG32      addr1,  
    [in] ULONG32      addr2,  
    [in] ULONG32      addr3);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b4a0b-108">Parametri</span><span class="sxs-lookup"><span data-stu-id="b4a0b-108">Parameters</span></span>  
 `name`  
 <span data-ttu-id="b4a0b-109">[in] Il nome del parametro.</span><span class="sxs-lookup"><span data-stu-id="b4a0b-109">[in] The parameter name.</span></span>  
  
 `attributes`  
 <span data-ttu-id="b4a0b-110">[in] Gli attributi del parametro.</span><span class="sxs-lookup"><span data-stu-id="b4a0b-110">[in] The parameter attributes.</span></span>  
  
 `sequence`  
 <span data-ttu-id="b4a0b-111">[in] Firma del parametro.</span><span class="sxs-lookup"><span data-stu-id="b4a0b-111">[in] The parameter signature.</span></span>  
  
 `addrKind`  
 <span data-ttu-id="b4a0b-112">[in] Il tipo di indirizzo.</span><span class="sxs-lookup"><span data-stu-id="b4a0b-112">[in] The address type.</span></span>  
  
 `addr1`  
 <span data-ttu-id="b4a0b-113">[in] Il primo indirizzo relativo al parametro specificato.</span><span class="sxs-lookup"><span data-stu-id="b4a0b-113">[in] The first address for the parameter specification.</span></span>  
  
 `addr2`  
 <span data-ttu-id="b4a0b-114">[in] Il secondo indirizzo relativo al parametro specificato.</span><span class="sxs-lookup"><span data-stu-id="b4a0b-114">[in] The second address for the parameter specification.</span></span>  
  
 `addr3`  
 <span data-ttu-id="b4a0b-115">[in] Terzo indirizzo relativo al parametro specificato.</span><span class="sxs-lookup"><span data-stu-id="b4a0b-115">[in] The third address for the parameter specification.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b4a0b-116">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="b4a0b-116">Return Value</span></span>  
 <span data-ttu-id="b4a0b-117">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o qualche altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="b4a0b-117">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b4a0b-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b4a0b-118">Requirements</span></span>  
 <span data-ttu-id="b4a0b-119">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="b4a0b-119">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4a0b-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b4a0b-120">See also</span></span>
- [<span data-ttu-id="b4a0b-121">Interfaccia ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="b4a0b-121">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)

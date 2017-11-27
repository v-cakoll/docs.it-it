---
title: Metodo ISymUnmanagedWriter::DefineParameter
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedWriter.DefineParameter
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedWriter::DefineParameter
helpviewer_keywords:
- DefineParameter method [.NET Framework debugging]
- ISymUnmanagedWriter::DefineParameter method [.NET Framework debugging]
ms.assetid: a8e3dd32-6a44-4371-9a74-f417b11998c8
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 166087a27d0aa7b100da563c25f7e5a52612ce50
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedwriterdefineparameter-method"></a><span data-ttu-id="097a2-102">Metodo ISymUnmanagedWriter::DefineParameter</span><span class="sxs-lookup"><span data-stu-id="097a2-102">ISymUnmanagedWriter::DefineParameter Method</span></span>
<span data-ttu-id="097a2-103">Definisce un singolo parametro nel metodo corrente.</span><span class="sxs-lookup"><span data-stu-id="097a2-103">Defines a single parameter in the current method.</span></span> <span data-ttu-id="097a2-104">Il tipo di parametro viene ricavato dalla posizione del parametro (sequenza) all'interno della firma del metodo.</span><span class="sxs-lookup"><span data-stu-id="097a2-104">The parameter type is taken from the parameter's position (sequence) within the method's signature.</span></span>  
  
 <span data-ttu-id="097a2-105">Se i parametri vengono definiti nei metadati per un determinato metodo, non è necessario definire nuovamente utilizzando questo metodo.</span><span class="sxs-lookup"><span data-stu-id="097a2-105">If parameters are defined in the metadata for a given method, you do not have to define them again by using this method.</span></span> <span data-ttu-id="097a2-106">I lettori di simbolo devono controllare i metadati normale per i parametri prima di verificare l'archivio dei simboli.</span><span class="sxs-lookup"><span data-stu-id="097a2-106">The symbol readers must check the normal metadata for the parameters before checking the symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="097a2-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="097a2-107">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="097a2-108">Parametri</span><span class="sxs-lookup"><span data-stu-id="097a2-108">Parameters</span></span>  
 `name`  
 <span data-ttu-id="097a2-109">[in] Il nome del parametro.</span><span class="sxs-lookup"><span data-stu-id="097a2-109">[in] The parameter name.</span></span>  
  
 `attributes`  
 <span data-ttu-id="097a2-110">[in] Gli attributi di parametro.</span><span class="sxs-lookup"><span data-stu-id="097a2-110">[in] The parameter attributes.</span></span>  
  
 `sequence`  
 <span data-ttu-id="097a2-111">[in] La firma di parametro.</span><span class="sxs-lookup"><span data-stu-id="097a2-111">[in] The parameter signature.</span></span>  
  
 `addrKind`  
 <span data-ttu-id="097a2-112">[in] Il tipo di indirizzo.</span><span class="sxs-lookup"><span data-stu-id="097a2-112">[in] The address type.</span></span>  
  
 `addr1`  
 <span data-ttu-id="097a2-113">[in] Il primo indirizzo per la specifica del parametro.</span><span class="sxs-lookup"><span data-stu-id="097a2-113">[in] The first address for the parameter specification.</span></span>  
  
 `addr2`  
 <span data-ttu-id="097a2-114">[in] Il secondo indirizzo per la specifica del parametro.</span><span class="sxs-lookup"><span data-stu-id="097a2-114">[in] The second address for the parameter specification.</span></span>  
  
 `addr3`  
 <span data-ttu-id="097a2-115">[in] Terzo indirizzo per la specifica del parametro.</span><span class="sxs-lookup"><span data-stu-id="097a2-115">[in] The third address for the parameter specification.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="097a2-116">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="097a2-116">Return Value</span></span>  
 <span data-ttu-id="097a2-117">S_OK se il metodo ha esito positivo. in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="097a2-117">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="097a2-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="097a2-118">Requirements</span></span>  
 <span data-ttu-id="097a2-119">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="097a2-119">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="097a2-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="097a2-120">See Also</span></span>  
 [<span data-ttu-id="097a2-121">ISymUnmanagedWriter (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="097a2-121">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)

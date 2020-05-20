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
ms.openlocfilehash: c695aa80ea3bf90a29ce7c5d11eda7fae5fe7b2d
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614812"
---
# <a name="isymunmanagedwriterdefineparameter-method"></a><span data-ttu-id="cdb11-102">Metodo ISymUnmanagedWriter::DefineParameter</span><span class="sxs-lookup"><span data-stu-id="cdb11-102">ISymUnmanagedWriter::DefineParameter Method</span></span>
<span data-ttu-id="cdb11-103">Definisce un singolo parametro nel metodo corrente.</span><span class="sxs-lookup"><span data-stu-id="cdb11-103">Defines a single parameter in the current method.</span></span> <span data-ttu-id="cdb11-104">Il tipo di parametro viene tratto dalla posizione (sequenza) del parametro all'interno della firma del metodo.</span><span class="sxs-lookup"><span data-stu-id="cdb11-104">The parameter type is taken from the parameter's position (sequence) within the method's signature.</span></span>  
  
 <span data-ttu-id="cdb11-105">Se i parametri sono definiti nei metadati per un determinato metodo, non è necessario definirli nuovamente utilizzando questo metodo.</span><span class="sxs-lookup"><span data-stu-id="cdb11-105">If parameters are defined in the metadata for a given method, you do not have to define them again by using this method.</span></span> <span data-ttu-id="cdb11-106">I lettori di simboli devono controllare i metadati normali per i parametri prima di controllare l'archivio dei simboli.</span><span class="sxs-lookup"><span data-stu-id="cdb11-106">The symbol readers must check the normal metadata for the parameters before checking the symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cdb11-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cdb11-107">Syntax</span></span>  
  
```cpp  
HRESULT DefineParameter(  
    [in] const WCHAR  *name,  
    [in] ULONG32      attributes,  
    [in] ULONG32      sequence,  
    [in] ULONG32      addrKind,  
    [in] ULONG32      addr1,  
    [in] ULONG32      addr2,  
    [in] ULONG32      addr3);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cdb11-108">Parametri</span><span class="sxs-lookup"><span data-stu-id="cdb11-108">Parameters</span></span>  
 `name`  
 <span data-ttu-id="cdb11-109">in Nome del parametro.</span><span class="sxs-lookup"><span data-stu-id="cdb11-109">[in] The parameter name.</span></span>  
  
 `attributes`  
 <span data-ttu-id="cdb11-110">in Attributi di parametro.</span><span class="sxs-lookup"><span data-stu-id="cdb11-110">[in] The parameter attributes.</span></span>  
  
 `sequence`  
 <span data-ttu-id="cdb11-111">in Firma del parametro.</span><span class="sxs-lookup"><span data-stu-id="cdb11-111">[in] The parameter signature.</span></span>  
  
 `addrKind`  
 <span data-ttu-id="cdb11-112">in Tipo di indirizzo.</span><span class="sxs-lookup"><span data-stu-id="cdb11-112">[in] The address type.</span></span>  
  
 `addr1`  
 <span data-ttu-id="cdb11-113">in Primo indirizzo per la specifica del parametro.</span><span class="sxs-lookup"><span data-stu-id="cdb11-113">[in] The first address for the parameter specification.</span></span>  
  
 `addr2`  
 <span data-ttu-id="cdb11-114">in Secondo indirizzo per la specifica del parametro.</span><span class="sxs-lookup"><span data-stu-id="cdb11-114">[in] The second address for the parameter specification.</span></span>  
  
 `addr3`  
 <span data-ttu-id="cdb11-115">in Terzo indirizzo per la specifica del parametro.</span><span class="sxs-lookup"><span data-stu-id="cdb11-115">[in] The third address for the parameter specification.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cdb11-116">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="cdb11-116">Return Value</span></span>  
 <span data-ttu-id="cdb11-117">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="cdb11-117">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cdb11-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="cdb11-118">Requirements</span></span>  
 <span data-ttu-id="cdb11-119">**Intestazione:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="cdb11-119">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cdb11-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cdb11-120">See also</span></span>

- [<span data-ttu-id="cdb11-121">Interfaccia ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="cdb11-121">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)

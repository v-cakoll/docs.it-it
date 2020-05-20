---
title: Metodo ISymUnmanagedWriter::DefineField
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.DefineField
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::DefineField
helpviewer_keywords:
- ISymUnmanagedWriter::DefineField method [.NET Framework debugging]
- DefineField method, ISymUnmanagedWriter interface [.NET Framework debugging]
ms.assetid: c6a1f797-dbf4-40f5-ab99-d9b4bfb26148
topic_type:
- apiref
ms.openlocfilehash: aba551a1973a41a909869316cda07e8d655e9882
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614838"
---
# <a name="isymunmanagedwriterdefinefield-method"></a><span data-ttu-id="8dbc7-102">Metodo ISymUnmanagedWriter::DefineField</span><span class="sxs-lookup"><span data-stu-id="8dbc7-102">ISymUnmanagedWriter::DefineField Method</span></span>
<span data-ttu-id="8dbc7-103">Definisce una singola variabile che non si trova all'interno di un metodo.</span><span class="sxs-lookup"><span data-stu-id="8dbc7-103">Defines a single variable that is not within a method.</span></span> <span data-ttu-id="8dbc7-104">Questo metodo viene utilizzato per determinati campi in classi, campi di bit e così via.</span><span class="sxs-lookup"><span data-stu-id="8dbc7-104">This method is used for certain fields in classes, bit fields, and so on.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8dbc7-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8dbc7-105">Syntax</span></span>  
  
```cpp  
HRESULT DefineField(  
    [in] mdTypeDef    parent,  
    [in] const WCHAR  *name,  
    [in] ULONG32      attributes,  
    [in] ULONG32      cSig,  
    [in, size_is(cSig)] unsigned char signature[],  
    [in] ULONG32      addrKind,  
    [in] ULONG32      addr1,  
    [in] ULONG32      addr2,  
    [in] ULONG32      addr3);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8dbc7-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="8dbc7-106">Parameters</span></span>  
 `parent`  
 <span data-ttu-id="8dbc7-107">in Il tipo di metadati o il token del metodo.</span><span class="sxs-lookup"><span data-stu-id="8dbc7-107">[in] The metadata type or method token.</span></span>  
  
 `name`  
 <span data-ttu-id="8dbc7-108">in Nome del campo.</span><span class="sxs-lookup"><span data-stu-id="8dbc7-108">[in] The field name.</span></span>  
  
 `attributes`  
 <span data-ttu-id="8dbc7-109">in Attributi del campo.</span><span class="sxs-lookup"><span data-stu-id="8dbc7-109">[in] The field attributes.</span></span>  
  
 `cSig`  
 <span data-ttu-id="8dbc7-110">in Oggetto `ULONG32` che rappresenta la dimensione, in caratteri, del buffer necessario per contenere la firma del campo.</span><span class="sxs-lookup"><span data-stu-id="8dbc7-110">[in] A `ULONG32` that is the size, in characters, of the buffer required to contain the field signature.</span></span>  
  
 `signature`  
 <span data-ttu-id="8dbc7-111">in Matrice delle firme dei campi.</span><span class="sxs-lookup"><span data-stu-id="8dbc7-111">[in] The array of field signatures.</span></span>  
  
 `addrKind`  
 <span data-ttu-id="8dbc7-112">in Tipo di indirizzo.</span><span class="sxs-lookup"><span data-stu-id="8dbc7-112">[in] The address type.</span></span>  
  
 `addr1`  
 <span data-ttu-id="8dbc7-113">in Primo indirizzo per la specifica del campo.</span><span class="sxs-lookup"><span data-stu-id="8dbc7-113">[in] The first address for the field specification.</span></span>  
  
 `addr2`  
 <span data-ttu-id="8dbc7-114">in Secondo indirizzo per la specifica del campo.</span><span class="sxs-lookup"><span data-stu-id="8dbc7-114">[in] The second address for the field specification.</span></span>  
  
 `addr3`  
 <span data-ttu-id="8dbc7-115">in Terzo indirizzo per la specifica del campo.</span><span class="sxs-lookup"><span data-stu-id="8dbc7-115">[in] The third address for the field specification.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8dbc7-116">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="8dbc7-116">Return Value</span></span>  
 <span data-ttu-id="8dbc7-117">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="8dbc7-117">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8dbc7-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8dbc7-118">Requirements</span></span>  
 <span data-ttu-id="8dbc7-119">**Intestazione:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="8dbc7-119">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8dbc7-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8dbc7-120">See also</span></span>

- [<span data-ttu-id="8dbc7-121">Interfaccia ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="8dbc7-121">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)

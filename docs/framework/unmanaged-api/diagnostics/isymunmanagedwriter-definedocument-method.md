---
title: Metodo ISymUnmanagedWriter::DefineDocument
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.DefineDocument
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::DefineDocument
helpviewer_keywords:
- ISymUnmanagedWriter::DefineDocument method [.NET Framework debugging]
- DefineDocument method [.NET Framework debugging]
ms.assetid: c3bf15b0-3250-4bbe-b9b5-c5d695289b6f
topic_type:
- apiref
ms.openlocfilehash: fdcfb0c4f9c21eb516f4196d0c8f682669468219
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615228"
---
# <a name="isymunmanagedwriterdefinedocument-method"></a><span data-ttu-id="3b20c-102">Metodo ISymUnmanagedWriter::DefineDocument</span><span class="sxs-lookup"><span data-stu-id="3b20c-102">ISymUnmanagedWriter::DefineDocument Method</span></span>
<span data-ttu-id="3b20c-103">Definisce un documento di origine.</span><span class="sxs-lookup"><span data-stu-id="3b20c-103">Defines a source document.</span></span> <span data-ttu-id="3b20c-104">I GUID sono forniti per i linguaggi noti, i fornitori e i tipi di documento.</span><span class="sxs-lookup"><span data-stu-id="3b20c-104">GUIDs are provided for known languages, vendors, and document types.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3b20c-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3b20c-105">Syntax</span></span>  
  
```cpp  
HRESULT DefineDocument(  
    [in]  const WCHAR  *url,  
    [in]  const GUID   *language,  
    [in]  const GUID   *languageVendor,  
    [in]  const GUID   *documentType,  
    [out, retval] ISymUnmanagedDocumentWriter**  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3b20c-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="3b20c-106">Parameters</span></span>  
 `url`  
 <span data-ttu-id="3b20c-107">in Puntatore a un oggetto `WCHAR` che definisce l'URL (Uniform Resource Locator) che identifica il documento.</span><span class="sxs-lookup"><span data-stu-id="3b20c-107">[in] A pointer to a `WCHAR` that defines the uniform resource locator (URL) that identifies the document.</span></span>  
  
 `language`  
 <span data-ttu-id="3b20c-108">in Puntatore a un GUID che definisce la lingua del documento.</span><span class="sxs-lookup"><span data-stu-id="3b20c-108">[in] A pointer to a GUID that defines the document language.</span></span>  
  
 `languageVendor`  
 <span data-ttu-id="3b20c-109">in Puntatore a un GUID che definisce l'identità del fornitore per la lingua del documento.</span><span class="sxs-lookup"><span data-stu-id="3b20c-109">[in] A pointer to a GUID that defines the identity of the vendor for the document language.</span></span>  
  
 `documentType`  
 <span data-ttu-id="3b20c-110">in Puntatore a un GUID che definisce il tipo del documento.</span><span class="sxs-lookup"><span data-stu-id="3b20c-110">[in] A pointer to a GUID that defines the type of the document.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="3b20c-111">out Puntatore all'interfaccia [ISymUnmanagedWriter](isymunmanagedwriter-interface.md) restituita.</span><span class="sxs-lookup"><span data-stu-id="3b20c-111">[out] A pointer to the returned [ISymUnmanagedWriter](isymunmanagedwriter-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3b20c-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="3b20c-112">Return Value</span></span>  
 <span data-ttu-id="3b20c-113">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="3b20c-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3b20c-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3b20c-114">Requirements</span></span>  
 <span data-ttu-id="3b20c-115">**Intestazione:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="3b20c-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b20c-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3b20c-116">See also</span></span>

- [<span data-ttu-id="3b20c-117">Interfaccia ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="3b20c-117">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)

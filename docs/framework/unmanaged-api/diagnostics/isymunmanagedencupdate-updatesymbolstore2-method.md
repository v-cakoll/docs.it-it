---
title: Metodo ISymUnmanagedENCUpdate::UpdateSymbolStore2
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: reference
api_name:
- ISymUnmanagedENCUpdate.UpdateSymbolStore2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedENCUpdate::UpdateSymbolStore2
helpviewer_keywords:
- ISymUnmanagedENCUpdate::UpdateSymbolStore2 method [.NET Framework debugging]
- UpdateSymbolStore2 method [.NET Framework debugging]
ms.assetid: 35588317-6184-485c-ab41-4b15fc1765d9
topic_type:
- apiref
caps.latest.revision: 11
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 9082a05900330be27066b64f2ad0e99b87e04c61
ms.sourcegitcommit: b750a8e3979749b214e7e10c82efb0a0524dfcb1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2018
---
# <a name="isymunmanagedencupdateupdatesymbolstore2-method"></a><span data-ttu-id="1d408-102">Metodo ISymUnmanagedENCUpdate::UpdateSymbolStore2</span><span class="sxs-lookup"><span data-stu-id="1d408-102">ISymUnmanagedENCUpdate::UpdateSymbolStore2 Method</span></span>
<span data-ttu-id="1d408-103">Consente a un compilatore di omettere le funzioni che non sono state modificate dal flusso di programma (PDB) di database, purché le informazioni sulla riga soddisfa i requisiti.</span><span class="sxs-lookup"><span data-stu-id="1d408-103">Allows a compiler to omit functions that have not been modified from the program database (PDB) stream, provided the line information meets the requirements.</span></span> <span data-ttu-id="1d408-104">Le informazioni sulla riga corretto può essere determinati con le informazioni sulla riga PDB precedente e un delta per tutte le righe nella funzione.</span><span class="sxs-lookup"><span data-stu-id="1d408-104">The correct line information can be determined with the old PDB line information and one delta for all lines in the function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1d408-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1d408-105">Syntax</span></span>  
  
```  
HRESULT UpdateSymbolStore2(  
    [in]  IStream      *pIStream,  
    [in]  SYMLINEDELTA* pDeltaLines,  
    [in]  ULONG         cDeltaLines);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1d408-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="1d408-106">Parameters</span></span>  
 `pIStream`  
 <span data-ttu-id="1d408-107">[in] Un puntatore a un [IStream](https://msdn.microsoft.com/library/aa380034.aspx) che contiene le informazioni sulla riga.</span><span class="sxs-lookup"><span data-stu-id="1d408-107">[in] A pointer to an [IStream](https://msdn.microsoft.com/library/aa380034.aspx) that contains the line information.</span></span>  
  
 `pDeltaLines`  
 <span data-ttu-id="1d408-108">[in] Un puntatore a un [SYMLINEDELTA](../../../../docs/framework/unmanaged-api/diagnostics/symlinedelta-structure.md) struttura che contiene le righe che sono stati modificati.</span><span class="sxs-lookup"><span data-stu-id="1d408-108">[in] A pointer to a [SYMLINEDELTA](../../../../docs/framework/unmanaged-api/diagnostics/symlinedelta-structure.md) structure that contains the lines that have changed.</span></span>  
  
 `cDeltaLines`  
 <span data-ttu-id="1d408-109">[in] Oggetto `ULONG` che rappresenta il numero di righe che sono stati modificati.</span><span class="sxs-lookup"><span data-stu-id="1d408-109">[in] A `ULONG` that represents the number of lines that have changed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1d408-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="1d408-110">Return Value</span></span>  
 <span data-ttu-id="1d408-111">S_OK se il metodo ha esito positivo. in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="1d408-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1d408-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1d408-112">Requirements</span></span>  
 <span data-ttu-id="1d408-113">**Intestazione:** CorSym. idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="1d408-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d408-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1d408-114">See Also</span></span>  
 [<span data-ttu-id="1d408-115">Interfaccia ISymUnmanagedENCUpdate</span><span class="sxs-lookup"><span data-stu-id="1d408-115">ISymUnmanagedENCUpdate Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-interface.md)

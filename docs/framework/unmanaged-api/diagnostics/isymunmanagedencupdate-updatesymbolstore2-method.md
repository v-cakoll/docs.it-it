---
title: Metodo ISymUnmanagedENCUpdate::UpdateSymbolStore2
ms.date: 03/30/2017
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
ms.openlocfilehash: f363bed8e7002bf898755b434c919f8722dea3fb
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614500"
---
# <a name="isymunmanagedencupdateupdatesymbolstore2-method"></a><span data-ttu-id="8eff7-102">Metodo ISymUnmanagedENCUpdate::UpdateSymbolStore2</span><span class="sxs-lookup"><span data-stu-id="8eff7-102">ISymUnmanagedENCUpdate::UpdateSymbolStore2 Method</span></span>
<span data-ttu-id="8eff7-103">Consente a un compilatore di omettere le funzioni che non sono state modificate dal flusso del database di programma (PDB), purché le informazioni sulla riga soddisfino i requisiti.</span><span class="sxs-lookup"><span data-stu-id="8eff7-103">Allows a compiler to omit functions that have not been modified from the program database (PDB) stream, provided the line information meets the requirements.</span></span> <span data-ttu-id="8eff7-104">Le informazioni sulla riga corrette possono essere determinate con le informazioni sulla riga PDB precedenti e un Delta per tutte le righe nella funzione.</span><span class="sxs-lookup"><span data-stu-id="8eff7-104">The correct line information can be determined with the old PDB line information and one delta for all lines in the function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8eff7-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8eff7-105">Syntax</span></span>  
  
```cpp  
HRESULT UpdateSymbolStore2(  
    [in]  IStream      *pIStream,  
    [in]  SYMLINEDELTA* pDeltaLines,  
    [in]  ULONG         cDeltaLines);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8eff7-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="8eff7-106">Parameters</span></span>  
 `pIStream`  
 <span data-ttu-id="8eff7-107">in Puntatore a un oggetto [IStream](/windows/desktop/api/objidl/nn-objidl-istream) che contiene le informazioni sulla riga.</span><span class="sxs-lookup"><span data-stu-id="8eff7-107">[in] A pointer to an [IStream](/windows/desktop/api/objidl/nn-objidl-istream) that contains the line information.</span></span>  
  
 `pDeltaLines`  
 <span data-ttu-id="8eff7-108">in Puntatore a una struttura [SYMLINEDELTA](symlinedelta-structure.md) che contiene le righe modificate.</span><span class="sxs-lookup"><span data-stu-id="8eff7-108">[in] A pointer to a [SYMLINEDELTA](symlinedelta-structure.md) structure that contains the lines that have changed.</span></span>  
  
 `cDeltaLines`  
 <span data-ttu-id="8eff7-109">in Oggetto `ULONG` che rappresenta il numero di righe modificate.</span><span class="sxs-lookup"><span data-stu-id="8eff7-109">[in] A `ULONG` that represents the number of lines that have changed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8eff7-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="8eff7-110">Return Value</span></span>  
 <span data-ttu-id="8eff7-111">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="8eff7-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8eff7-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8eff7-112">Requirements</span></span>  
 <span data-ttu-id="8eff7-113">**Intestazione:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="8eff7-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8eff7-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8eff7-114">See also</span></span>

- [<span data-ttu-id="8eff7-115">Interfaccia ISymUnmanagedENCUpdate</span><span class="sxs-lookup"><span data-stu-id="8eff7-115">ISymUnmanagedENCUpdate Interface</span></span>](isymunmanagedencupdate-interface.md)

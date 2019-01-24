---
title: Metodo IMetaDataImport2::GetVersionString
ms.date: 03/30/2017
api_name:
- IMetaDataImport2.GetVersionString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2::GetVersionString
helpviewer_keywords:
- GetVersionString method, IMetaDataImport2 interface [.NET Framework metadata]
- IMetaDataImport2::GetVersionString method [.NET Framework metadata]
ms.assetid: 308183ee-fd44-4432-9d86-ef00d181b49b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5e041efed929255d4ce3af2d051a391bc4179cda
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54630918"
---
# <a name="imetadataimport2getversionstring-method"></a><span data-ttu-id="a0bff-102">Metodo IMetaDataImport2::GetVersionString</span><span class="sxs-lookup"><span data-stu-id="a0bff-102">IMetaDataImport2::GetVersionString Method</span></span>
<span data-ttu-id="a0bff-103">Ottiene il numero di versione del runtime che è stato usato per compilare l'assembly.</span><span class="sxs-lookup"><span data-stu-id="a0bff-103">Gets the version number of the runtime that was used to build the assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0bff-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a0bff-104">Syntax</span></span>  
  
```  
HRESULT GetVersionString (  
   [out] LPWSTR      pwzBuf,  
   [in]  DWORD       ccBufSize,  
   [out] DWORD       *pccBufSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a0bff-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a0bff-105">Parameters</span></span>  
 `pwzBuf`  
 <span data-ttu-id="a0bff-106">[out] Una matrice per archiviare la stringa che specifica la versione.</span><span class="sxs-lookup"><span data-stu-id="a0bff-106">[out] An array to store the string that specifies the version.</span></span>  
  
 `ccBufSize`  
 <span data-ttu-id="a0bff-107">[in] Le dimensioni, in caratteri "wide", del `pwzBuf` matrice.</span><span class="sxs-lookup"><span data-stu-id="a0bff-107">[in] The size, in wide characters, of the `pwzBuf` array.</span></span>  
  
 `pccBufSize`  
 <span data-ttu-id="a0bff-108">[out] Il numero di caratteri "wide", incluso un carattere di terminazione null, restituito nel `pwzBuf` matrice.</span><span class="sxs-lookup"><span data-stu-id="a0bff-108">[out] The number of wide characters, including a null terminator, returned in the `pwzBuf` array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a0bff-109">Note</span><span class="sxs-lookup"><span data-stu-id="a0bff-109">Remarks</span></span>  
 <span data-ttu-id="a0bff-110">Il `GetVersionString` metodo ottiene la versione compilata dell'ambito dei metadati corrente.</span><span class="sxs-lookup"><span data-stu-id="a0bff-110">The `GetVersionString` method gets the built-for version of the current metadata scope.</span></span> <span data-ttu-id="a0bff-111">Se l'ambito non è mai stato salvato, non disporrà di una versione e verrà restituita una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="a0bff-111">If the scope has never been saved, it will not have a built-for version, and an empty string will be returned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a0bff-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a0bff-112">Requirements</span></span>  
 <span data-ttu-id="a0bff-113">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a0bff-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a0bff-114">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="a0bff-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a0bff-115">**Libreria:** Usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="a0bff-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a0bff-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a0bff-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0bff-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a0bff-117">See also</span></span>
- [<span data-ttu-id="a0bff-118">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="a0bff-118">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
- [<span data-ttu-id="a0bff-119">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="a0bff-119">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)

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
ms.openlocfilehash: 112ddcf51a5637bb89df9479850c2a4a70d2e1d8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33448726"
---
# <a name="imetadataimport2getversionstring-method"></a><span data-ttu-id="aaec4-102">Metodo IMetaDataImport2::GetVersionString</span><span class="sxs-lookup"><span data-stu-id="aaec4-102">IMetaDataImport2::GetVersionString Method</span></span>
<span data-ttu-id="aaec4-103">Ottiene il numero di versione del runtime che è stato utilizzato per compilare l'assembly.</span><span class="sxs-lookup"><span data-stu-id="aaec4-103">Gets the version number of the runtime that was used to build the assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aaec4-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="aaec4-104">Syntax</span></span>  
  
```  
HRESULT GetVersionString (  
   [out] LPWSTR      pwzBuf,  
   [in]  DWORD       ccBufSize,  
   [out] DWORD       *pccBufSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="aaec4-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="aaec4-105">Parameters</span></span>  
 `pwzBuf`  
 <span data-ttu-id="aaec4-106">[out] Una matrice per archiviare la stringa che specifica la versione.</span><span class="sxs-lookup"><span data-stu-id="aaec4-106">[out] An array to store the string that specifies the version.</span></span>  
  
 `ccBufSize`  
 <span data-ttu-id="aaec4-107">[in] Le dimensioni, in caratteri wide, del `pwzBuf` matrice.</span><span class="sxs-lookup"><span data-stu-id="aaec4-107">[in] The size, in wide characters, of the `pwzBuf` array.</span></span>  
  
 `pccBufSize`  
 <span data-ttu-id="aaec4-108">[out] Il numero di caratteri wide, incluso un terminatore null, restituite nel `pwzBuf` matrice.</span><span class="sxs-lookup"><span data-stu-id="aaec4-108">[out] The number of wide characters, including a null terminator, returned in the `pwzBuf` array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="aaec4-109">Note</span><span class="sxs-lookup"><span data-stu-id="aaec4-109">Remarks</span></span>  
 <span data-ttu-id="aaec4-110">Il `GetVersionString` metodo ottiene la versione compilata per di ambito dei metadati corrente.</span><span class="sxs-lookup"><span data-stu-id="aaec4-110">The `GetVersionString` method gets the built-for version of the current metadata scope.</span></span> <span data-ttu-id="aaec4-111">Se l'ambito non è mai stato salvato, non disporrà di una versione e verrà restituita una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="aaec4-111">If the scope has never been saved, it will not have a built-for version, and an empty string will be returned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aaec4-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="aaec4-112">Requirements</span></span>  
 <span data-ttu-id="aaec4-113">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aaec4-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aaec4-114">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="aaec4-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="aaec4-115">**Libreria:** usata come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="aaec4-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="aaec4-116">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aaec4-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aaec4-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="aaec4-117">See Also</span></span>  
 [<span data-ttu-id="aaec4-118">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="aaec4-118">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)  
 [<span data-ttu-id="aaec4-119">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="aaec4-119">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)

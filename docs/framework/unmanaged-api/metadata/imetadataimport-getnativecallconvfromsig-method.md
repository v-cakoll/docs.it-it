---
title: Metodo IMetaDataImport::GetNativeCallConvFromSig
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetNativeCallConvFromSig
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetNativeCallConvFromSig
helpviewer_keywords:
- GetNativeCallConvFromSig method [.NET Framework metadata]
- IMetaDataImport::GetNativeCallConvFromSig method [.NET Framework metadata]
ms.assetid: 50e04026-4d4a-47d9-96c1-f4677d6d938b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ef1ac83b383a9f6bbee7f55441d2abfcb081afa6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59122746"
---
# <a name="imetadataimportgetnativecallconvfromsig-method"></a><span data-ttu-id="a0859-102">Metodo IMetaDataImport::GetNativeCallConvFromSig</span><span class="sxs-lookup"><span data-stu-id="a0859-102">IMetaDataImport::GetNativeCallConvFromSig Method</span></span>
<span data-ttu-id="a0859-103">Ottiene la convenzione di chiamata nativa per il metodo rappresentato dal puntatore a firma specificato.</span><span class="sxs-lookup"><span data-stu-id="a0859-103">Gets the native calling convention for the method that is represented by the specified signature pointer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0859-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a0859-104">Syntax</span></span>  
  
```  
HRESULT GetNativeCallConvFromSig (  
   [in]  void const  *pvSig,  
   [in]  ULONG       cbSig,  
   [out] ULONG       *pCallConv  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a0859-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a0859-105">Parameters</span></span>  
 `pvSig`  
 <span data-ttu-id="a0859-106">[in] Puntatore alla firma del metodo per restituire la convenzione di chiamata per i metadati.</span><span class="sxs-lookup"><span data-stu-id="a0859-106">[in] A pointer to the metadata signature of the method to return the calling convention for.</span></span>  
  
 `cbSig`  
 <span data-ttu-id="a0859-107">[in] La dimensione in byte di `pvSig`.</span><span class="sxs-lookup"><span data-stu-id="a0859-107">[in] The size in bytes of `pvSig`.</span></span>  
  
 `pCallConv`  
 <span data-ttu-id="a0859-108">[out] Puntatore alla convenzione di chiamata nativa.</span><span class="sxs-lookup"><span data-stu-id="a0859-108">[out] A pointer to the native calling convention.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a0859-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a0859-109">Requirements</span></span>  
 <span data-ttu-id="a0859-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a0859-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a0859-111">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="a0859-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a0859-112">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="a0859-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a0859-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a0859-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0859-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a0859-114">See also</span></span>

- <xref:System.Runtime.InteropServices.CallingConvention>
- [<span data-ttu-id="a0859-115">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="a0859-115">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="a0859-116">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="a0859-116">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)

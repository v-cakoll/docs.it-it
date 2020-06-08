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
ms.openlocfilehash: 44439eda62f85c32893b73f17bd057195cf6b2e1
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503549"
---
# <a name="imetadataimportgetnativecallconvfromsig-method"></a><span data-ttu-id="45325-102">Metodo IMetaDataImport::GetNativeCallConvFromSig</span><span class="sxs-lookup"><span data-stu-id="45325-102">IMetaDataImport::GetNativeCallConvFromSig Method</span></span>
<span data-ttu-id="45325-103">Ottiene la convenzione di chiamata nativa per il metodo rappresentato dal puntatore a firma specificato.</span><span class="sxs-lookup"><span data-stu-id="45325-103">Gets the native calling convention for the method that is represented by the specified signature pointer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="45325-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="45325-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNativeCallConvFromSig (  
   [in]  void const  *pvSig,  
   [in]  ULONG       cbSig,  
   [out] ULONG       *pCallConv  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="45325-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="45325-105">Parameters</span></span>  
 `pvSig`  
 <span data-ttu-id="45325-106">in Puntatore alla firma dei metadati del metodo per cui restituire la convenzione di chiamata.</span><span class="sxs-lookup"><span data-stu-id="45325-106">[in] A pointer to the metadata signature of the method to return the calling convention for.</span></span>  
  
 `cbSig`  
 <span data-ttu-id="45325-107">in Dimensioni in byte di `pvSig` .</span><span class="sxs-lookup"><span data-stu-id="45325-107">[in] The size in bytes of `pvSig`.</span></span>  
  
 `pCallConv`  
 <span data-ttu-id="45325-108">out Puntatore alla convenzione di chiamata nativa.</span><span class="sxs-lookup"><span data-stu-id="45325-108">[out] A pointer to the native calling convention.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="45325-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="45325-109">Requirements</span></span>  
 <span data-ttu-id="45325-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="45325-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="45325-111">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="45325-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="45325-112">**Libreria:** Incluso come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="45325-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="45325-113">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="45325-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45325-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="45325-114">See also</span></span>

- <xref:System.Runtime.InteropServices.CallingConvention>
- [<span data-ttu-id="45325-115">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="45325-115">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="45325-116">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="45325-116">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)

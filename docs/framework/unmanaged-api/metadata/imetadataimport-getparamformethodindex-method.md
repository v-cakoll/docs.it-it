---
title: Metodo IMetaDataImport::GetParamForMethodIndex
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetParamForMethodIndex
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetParamForMethodIndex
helpviewer_keywords:
- IMetaDataImport::GetParamForMethodIndex method [.NET Framework metadata]
- GetParamForMethodIndex method [.NET Framework metadata]
ms.assetid: ec3bfa95-1920-4511-932e-3ff23d76fcb8
topic_type:
- apiref
ms.openlocfilehash: 21a83e404405ca9cfe301b76cb1e1591d69e747c
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84491121"
---
# <a name="imetadataimportgetparamformethodindex-method"></a><span data-ttu-id="a1b95-102">Metodo IMetaDataImport::GetParamForMethodIndex</span><span class="sxs-lookup"><span data-stu-id="a1b95-102">IMetaDataImport::GetParamForMethodIndex Method</span></span>
<span data-ttu-id="a1b95-103">Ottiene il token che rappresenta un parametro specificato del metodo rappresentato dal token MethodDef specificato.</span><span class="sxs-lookup"><span data-stu-id="a1b95-103">Gets the token that represents a specified parameter of the method represented by the specified MethodDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1b95-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a1b95-104">Syntax</span></span>  
  
```cpp  
HRESULT GetParamForMethodIndex (  
   [in]  mdMethodDef      md,  
   [in]  ULONG            ulParamSeq,  
   [out] mdParamDef       *ppd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a1b95-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a1b95-105">Parameters</span></span>  
 `md`  
 <span data-ttu-id="a1b95-106">in Token che rappresenta il metodo per il quale restituire il token di parametro.</span><span class="sxs-lookup"><span data-stu-id="a1b95-106">[in] A token that represents the method to return the parameter token for.</span></span>  
  
 `ulParamSeq`  
 <span data-ttu-id="a1b95-107">in Posizione ordinale nell'elenco di parametri in cui si verifica il parametro richiesto.</span><span class="sxs-lookup"><span data-stu-id="a1b95-107">[in] The ordinal position in the parameter list where the requested parameter occurs.</span></span> <span data-ttu-id="a1b95-108">I parametri sono numerati a partire da uno, con il valore restituito del metodo nella posizione zero.</span><span class="sxs-lookup"><span data-stu-id="a1b95-108">Parameters are numbered starting from one, with the method's return value in position zero.</span></span>  
  
 `ppd`  
 <span data-ttu-id="a1b95-109">out Puntatore a un token ParamDef che rappresenta il parametro richiesto.</span><span class="sxs-lookup"><span data-stu-id="a1b95-109">[out] A pointer to a ParamDef token that represents the requested parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a1b95-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a1b95-110">Requirements</span></span>  
 <span data-ttu-id="a1b95-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a1b95-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a1b95-112">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="a1b95-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a1b95-113">**Libreria:** Incluso come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="a1b95-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a1b95-114">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a1b95-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1b95-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a1b95-115">See also</span></span>

- [<span data-ttu-id="a1b95-116">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="a1b95-116">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="a1b95-117">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="a1b95-117">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)

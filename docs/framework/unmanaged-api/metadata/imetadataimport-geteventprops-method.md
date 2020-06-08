---
title: Metodo IMetaDataImport::GetEventProps
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetEventProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetEventProps
helpviewer_keywords:
- IMetaDataImport::GetEventProps method [.NET Framework metadata]
- GetEventProps method [.NET Framework metadata]
ms.assetid: 5eaf3b4a-92b7-4d5b-97e0-1e83721e0052
topic_type:
- apiref
ms.openlocfilehash: 3b47d1559300a462ccda42bc88da43f66c1043ec
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84491303"
---
# <a name="imetadataimportgeteventprops-method"></a><span data-ttu-id="f9b8c-102">Metodo IMetaDataImport::GetEventProps</span><span class="sxs-lookup"><span data-stu-id="f9b8c-102">IMetaDataImport::GetEventProps Method</span></span>
<span data-ttu-id="f9b8c-103">Ottiene le informazioni sui metadati per l'evento rappresentato dal token di evento specificato, inclusi il tipo dichiarante, i metodi di aggiunta e rimozione per i delegati e tutti i flag e altri dati associati.</span><span class="sxs-lookup"><span data-stu-id="f9b8c-103">Gets metadata information for the event represented by the specified event token, including the declaring type, the add and remove methods for delegates, and any flags and other associated data.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f9b8c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f9b8c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetEventProps (  
   [in]  mdEvent       ev,  
   [out] mdTypeDef     *pClass,
   [out] LPCWSTR       szEvent,
   [in]  ULONG         cchEvent,
   [out] ULONG         *pchEvent,
   [out] DWORD         *pdwEventFlags,  
   [out] mdToken       *ptkEventType,  
   [out] mdMethodDef   *pmdAddOn,
   [out] mdMethodDef   *pmdRemoveOn,
   [out] mdMethodDef   *pmdFire,
   [out] mdMethodDef   rmdOtherMethod[],
   [in]  ULONG         cMax,  
   [out] ULONG         *pcOtherMethod  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f9b8c-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f9b8c-105">Parameters</span></span>  
 `ev`  
 <span data-ttu-id="f9b8c-106">in Token di metadati dell'evento che rappresenta l'evento per il quale ottenere i metadati.</span><span class="sxs-lookup"><span data-stu-id="f9b8c-106">[in] The event metadata token representing the event to get metadata for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="f9b8c-107">out Puntatore al token TypeDef che rappresenta la classe che dichiara l'evento.</span><span class="sxs-lookup"><span data-stu-id="f9b8c-107">[out] A pointer to the TypeDef token representing the class that declares the event.</span></span>  
  
 `szEvent`  
 <span data-ttu-id="f9b8c-108">out Nome dell'evento a cui fa riferimento `ev` .</span><span class="sxs-lookup"><span data-stu-id="f9b8c-108">[out] The name of the event referenced by `ev`.</span></span>  
  
 `pchEvent`  
 <span data-ttu-id="f9b8c-109">in Lunghezza richiesta in caratteri wide di `szEvent` .</span><span class="sxs-lookup"><span data-stu-id="f9b8c-109">[in] The requested length in wide characters of `szEvent`.</span></span>  
  
 `pdwEventFlags`  
 <span data-ttu-id="f9b8c-110">out Lunghezza restituita in caratteri wide di `szEvent` .</span><span class="sxs-lookup"><span data-stu-id="f9b8c-110">[out] The returned length in wide characters of `szEvent`.</span></span>  
  
 `ptkEventType`  
 <span data-ttu-id="f9b8c-111">out Puntatore a un token di metadati TypeRef o TypeDef che rappresenta il <xref:System.Delegate> tipo dell'evento.</span><span class="sxs-lookup"><span data-stu-id="f9b8c-111">[out] A pointer to a TypeRef or TypeDef metadata token representing the <xref:System.Delegate> type of the event.</span></span>  
  
 `pmdAddOn`  
 <span data-ttu-id="f9b8c-112">out Puntatore al token di metadati che rappresenta il metodo che aggiunge gestori per l'evento.</span><span class="sxs-lookup"><span data-stu-id="f9b8c-112">[out] A pointer to the metadata token representing the method that adds handlers for the event.</span></span>  
  
 `pmdRemoveOn`  
 <span data-ttu-id="f9b8c-113">out Puntatore al token di metadati che rappresenta il metodo che rimuove i gestori per l'evento.</span><span class="sxs-lookup"><span data-stu-id="f9b8c-113">[out] A pointer to the metadata token representing the method that removes handlers for the event.</span></span>  
  
 `pmdFire`  
 <span data-ttu-id="f9b8c-114">out Puntatore al token di metadati che rappresenta il metodo che genera l'evento.</span><span class="sxs-lookup"><span data-stu-id="f9b8c-114">[out] A pointer to the metadata token representing the method that raises the event.</span></span>  
  
 `rmdOtherMethod`  
 <span data-ttu-id="f9b8c-115">out Matrice di puntatori del token ad altri metodi associati all'evento.</span><span class="sxs-lookup"><span data-stu-id="f9b8c-115">[out] An array of token pointers to other methods associated with the event.</span></span>  
  
 `cMax`  
 <span data-ttu-id="f9b8c-116">[in] Dimensione massima della matrice `rmdOtherMethod`.</span><span class="sxs-lookup"><span data-stu-id="f9b8c-116">[in] The maximum size of the `rmdOtherMethod` array.</span></span>  
  
 `pcOtherMethod`  
 <span data-ttu-id="f9b8c-117">out Numero di token restituiti in `rmdOtherMethod` .</span><span class="sxs-lookup"><span data-stu-id="f9b8c-117">[out] The number of tokens returned in `rmdOtherMethod`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f9b8c-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f9b8c-118">Requirements</span></span>  
 <span data-ttu-id="f9b8c-119">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f9b8c-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f9b8c-120">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="f9b8c-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f9b8c-121">**Libreria:** Incluso come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="f9b8c-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f9b8c-122">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f9b8c-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9b8c-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f9b8c-123">See also</span></span>

- [<span data-ttu-id="f9b8c-124">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="f9b8c-124">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="f9b8c-125">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="f9b8c-125">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)

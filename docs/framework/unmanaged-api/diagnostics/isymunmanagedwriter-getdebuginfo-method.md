---
title: Metodo ISymUnmanagedWriter::GetDebugInfo
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.GetDebugInfo
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::GetDebugInfo
helpviewer_keywords:
- ISymUnmanagedWriter::GetDebugInfo method [.NET Framework debugging]
- GetDebugInfo method [.NET Framework debugging]
ms.assetid: dd31c210-6829-45eb-927e-cc53932638b7
topic_type:
- apiref
ms.openlocfilehash: f8eb4cb6bad95295e10a72812fa8dbb0adfcc898
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614786"
---
# <a name="isymunmanagedwritergetdebuginfo-method"></a><span data-ttu-id="02218-102">Metodo ISymUnmanagedWriter::GetDebugInfo</span><span class="sxs-lookup"><span data-stu-id="02218-102">ISymUnmanagedWriter::GetDebugInfo Method</span></span>
<span data-ttu-id="02218-103">Restituisce le informazioni necessarie affinché un compilatore scriva la voce della directory di debug nell'intestazione del file eseguibile Portable (PE).</span><span class="sxs-lookup"><span data-stu-id="02218-103">Returns the information necessary for a compiler to write the debug directory entry in the portable executable (PE) file header.</span></span> <span data-ttu-id="02218-104">Il writer di simboli compila tutti i campi ad eccezione di `TimeDateStamp` e `PointerToRawData` .</span><span class="sxs-lookup"><span data-stu-id="02218-104">The symbol writer fills out all fields except for `TimeDateStamp` and `PointerToRawData`.</span></span> <span data-ttu-id="02218-105">Il compilatore è responsabile dell'impostazione di questi due campi in modo appropriato.</span><span class="sxs-lookup"><span data-stu-id="02218-105">(The compiler is responsible for setting these two fields appropriately.)</span></span>  
  
 <span data-ttu-id="02218-106">Un compilatore deve chiamare questo metodo, creare il BLOB di dati nel file PE, impostare il `PointerToRawData` campo nell'IMAGE_DEBUG_DIRECTORY in modo che punti ai dati emessi e scrivere la IMAGE_DEBUG_DIRECTORY nel file PE.</span><span class="sxs-lookup"><span data-stu-id="02218-106">A compiler should call this method, emit the data blob to the PE file, set the `PointerToRawData` field in the IMAGE_DEBUG_DIRECTORY to point to the emitted data, and write the IMAGE_DEBUG_DIRECTORY to the PE file.</span></span> <span data-ttu-id="02218-107">Il compilatore deve inoltre impostare il `TimeDateStamp` campo in modo che corrisponda all'oggetto `TimeDateStamp` del file PE da generare.</span><span class="sxs-lookup"><span data-stu-id="02218-107">The compiler should also set the `TimeDateStamp` field to equal the `TimeDateStamp` of the PE file being generated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02218-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="02218-108">Syntax</span></span>  
  
```cpp  
HRESULT GetDebugInfo(  
    [in, out] IMAGE_DEBUG_DIRECTORY *pIDD,  
    [in]  DWORD cData,  
    [out] DWORD *pcData,  
    [out, size_is(cData),  
        length_is(*pcData)] BYTE data[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="02218-109">Parametri</span><span class="sxs-lookup"><span data-stu-id="02218-109">Parameters</span></span>  
 `pIDD`  
 <span data-ttu-id="02218-110">[in, out] Puntatore a un IMAGE_DEBUG_DIRECTORY che il writer di simboli compilerà.</span><span class="sxs-lookup"><span data-stu-id="02218-110">[in, out] A pointer to an IMAGE_DEBUG_DIRECTORY that the symbol writer will fill out.</span></span>  
  
 `cData`  
 <span data-ttu-id="02218-111">in Oggetto `DWORD` che contiene le dimensioni dei dati di debug.</span><span class="sxs-lookup"><span data-stu-id="02218-111">[in] A `DWORD` that contains the size of the debug data.</span></span>  
  
 `pcData`  
 <span data-ttu-id="02218-112">out Puntatore a un oggetto `DWORD` che riceve le dimensioni del buffer necessarie per contenere i dati di debug.</span><span class="sxs-lookup"><span data-stu-id="02218-112">[out] A pointer to a `DWORD` that receives the size of the buffer required to contain the debug data.</span></span>  
  
 `data`  
 <span data-ttu-id="02218-113">out Puntatore a un buffer sufficientemente grande da contenere i dati di debug per l'archivio dei simboli.</span><span class="sxs-lookup"><span data-stu-id="02218-113">[out] A pointer to a buffer that is large enough to hold the debug data for the symbol store.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="02218-114">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="02218-114">Return Value</span></span>  
 <span data-ttu-id="02218-115">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="02218-115">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="02218-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="02218-116">Requirements</span></span>  
 <span data-ttu-id="02218-117">**Intestazione:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="02218-117">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02218-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="02218-118">See also</span></span>

- [<span data-ttu-id="02218-119">Interfaccia ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="02218-119">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)

---
title: Struttura IDENTITY_ATTRIBUTE_BLOB
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- IDENTITY_ATTRIBUTE_BLOB
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IDENTITY_ATTRIBUTE_BLOB
helpviewer_keywords:
- IDENTITY_ATTRIBUTE_BLOB structure [.NET Framework fusion]
ms.assetid: af14ae5f-d226-47dd-ba90-8fc6e6605d4d
topic_type:
- apiref
ms.openlocfilehash: 8f838d5c812842e2a637065b25182b6a12609231
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176552"
---
# <a name="identity_attribute_blob-structure"></a><span data-ttu-id="a3591-102">Struttura IDENTITY_ATTRIBUTE_BLOB</span><span class="sxs-lookup"><span data-stu-id="a3591-102">IDENTITY_ATTRIBUTE_BLOB Structure</span></span>
<span data-ttu-id="a3591-103">Contiene informazioni su un singolo attributo in `DWORD`un assembly ed è costituito da tre s.</span><span class="sxs-lookup"><span data-stu-id="a3591-103">Contains information about a single attribute in an assembly, and consists of three `DWORD`s.</span></span> <span data-ttu-id="a3591-104">Ognuno `DWORD` è un offset in `CurrentIntoBuffer` un buffer di caratteri prodotto dal metodo dell'interfaccia [IEnumIDENTITY_ATTRIBUTE](ienumidentity-attribute-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a3591-104">Each `DWORD` is an offset into a character buffer produced by the `CurrentIntoBuffer` method of the [IEnumIDENTITY_ATTRIBUTE](ienumidentity-attribute-interface.md) interface</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a3591-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a3591-105">Syntax</span></span>  
  
```cpp  
typedef struct _IDENTITY_ATTRIBUTE_BLOB {  
    DWORD  ofsNamespace;  
    DWORD  ofsName;  
    DWORD  ofsValue;  
}   IDENTITY_ATTRIBUTE_BLOB;  
```  
  
## <a name="members"></a><span data-ttu-id="a3591-106">Members</span><span class="sxs-lookup"><span data-stu-id="a3591-106">Members</span></span>  
  
|<span data-ttu-id="a3591-107">Membro</span><span class="sxs-lookup"><span data-stu-id="a3591-107">Member</span></span>|<span data-ttu-id="a3591-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a3591-108">Description</span></span>|  
|------------|-----------------|  
|`ofsNamespace`|<span data-ttu-id="a3591-109">Primo offset nel buffer dei caratteri.</span><span class="sxs-lookup"><span data-stu-id="a3591-109">The first offset into the character buffer.</span></span> <span data-ttu-id="a3591-110">Questo offset non è seguito dallo spazio dei nomi dell'attributo, ma da una serie di caratteri null.</span><span class="sxs-lookup"><span data-stu-id="a3591-110">This offset is not followed by the attribute's namespace, but by a series of null characters.</span></span> <span data-ttu-id="a3591-111">Pertanto, non viene utilizzato.</span><span class="sxs-lookup"><span data-stu-id="a3591-111">Therefore, it is not used.</span></span>|  
|`ofsName`|<span data-ttu-id="a3591-112">Secondo offset nel buffer dei caratteri.</span><span class="sxs-lookup"><span data-stu-id="a3591-112">The second offset into the character buffer.</span></span> <span data-ttu-id="a3591-113">Questa posizione contrassegna l'inizio del nome dell'attributo.</span><span class="sxs-lookup"><span data-stu-id="a3591-113">This location marks the start of the attribute's name.</span></span>|  
|`ofsValue`|<span data-ttu-id="a3591-114">Terzo offset nel buffer dei caratteri.</span><span class="sxs-lookup"><span data-stu-id="a3591-114">The third offset into the character buffer.</span></span> <span data-ttu-id="a3591-115">Questa posizione contrassegna l'inizio del valore dell'attributo.</span><span class="sxs-lookup"><span data-stu-id="a3591-115">This location marks the start of the attribute's value.</span></span>|  
  
## <a name="sample"></a><span data-ttu-id="a3591-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="a3591-116">Sample</span></span>  
 <span data-ttu-id="a3591-117">L'esempio seguente illustra diversi passaggi di base, che alla fine generano una struttura popolata:The following example illustrates several basic steps, which eventually result in a populated `IDENTITY_ATTRIBUTE_BLOB` structure:</span><span class="sxs-lookup"><span data-stu-id="a3591-117">The following example illustrates several basic steps, which eventually result in a populated `IDENTITY_ATTRIBUTE_BLOB` structure:</span></span>  
  
1. <span data-ttu-id="a3591-118">Ottenere un [IReferenceIdentity](ireferenceidentity-interface.md) per l'assembly.</span><span class="sxs-lookup"><span data-stu-id="a3591-118">Obtain an [IReferenceIdentity](ireferenceidentity-interface.md) for the assembly.</span></span>  
  
2. <span data-ttu-id="a3591-119">Chiamare `IReferenceIdentity::EnumAttributes` il metodo e ottenere [un'IEnumIDENTITY_ATTRIBUTE](ienumidentity-attribute-interface.md).</span><span class="sxs-lookup"><span data-stu-id="a3591-119">Call the `IReferenceIdentity::EnumAttributes` method, and obtain an [IEnumIDENTITY_ATTRIBUTE](ienumidentity-attribute-interface.md).</span></span>  
  
3. <span data-ttu-id="a3591-120">Creare un buffer di caratteri `IDENTITY_ATTRIBUTE_BLOB` ed eseguire il cast come struttura.</span><span class="sxs-lookup"><span data-stu-id="a3591-120">Create a character buffer, and cast it as an `IDENTITY_ATTRIBUTE_BLOB` structure.</span></span>  
  
4. <span data-ttu-id="a3591-121">Chiamare `CurrentIntoBuffer` il metodo `IEnumIDENTITY_ATTRIBUTE` dell'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="a3591-121">Call the `CurrentIntoBuffer` method of the `IEnumIDENTITY_ATTRIBUTE` interface.</span></span> <span data-ttu-id="a3591-122">Questo metodo copia `Namespace`gli `Name`attributi `Value` , , e nel buffer di caratteri.</span><span class="sxs-lookup"><span data-stu-id="a3591-122">This method copies the attributes `Namespace`, `Name`, and `Value` into the character buffer.</span></span> <span data-ttu-id="a3591-123">I tre offset di tali stringhe `IDENTITY_ATTRIBUTE_BLOB` saranno disponibili nella struttura.</span><span class="sxs-lookup"><span data-stu-id="a3591-123">The three offsets to those strings will become available in the `IDENTITY_ATTRIBUTE_BLOB` structure.</span></span>  
  
```cpp  
// EnumAssemblyAttributes.cpp : main project file.  
  
#include "stdafx.h"  
  
#include "fusion.h"  
#include "windows.h"  
#include "stdio.h"  
#include "mscoree.h"  
#include "isolation.h"  
  
typedef HRESULT (__stdcall *PFNGETREF)(LPCWSTR pwzFile, REFIID riid, IUnknown **ppUnk);  
typedef HRESULT (__stdcall *PFNGETAUTH)(IIdentityAuthority **ppIIdentityAuthority);  
  
PFNGETREF                   g_pfnGetAssemblyIdentityFromFile = NULL;  
PFNGETAUTH                  g_pfnGetIdentityAuthority = NULL;  
IUnknown                    *g_pUnk = NULL;  
  
bool Init()  
{  
    HRESULT     hr = S_OK;  
    DWORD       dwSize = 0;  
    bool        bRC = false;  
  
    hr = CorBindToRuntimeEx(NULL, L"wks", 0, CLSID_CorRuntimeHost,  
                           IID_ICorRuntimeHost, (void **)&g_pUnk);  
    if(FAILED(hr)) {  
        printf("Error: Failed to initialize CLR runtime! hr = 0x%0x\n",  
                hr);  
        goto Exit;  
    }  
  
    if (SUCCEEDED(hr)) {  
        hr = GetRealProcAddress("GetAssemblyIdentityFromFile",  
                         (VOID **)&g_pfnGetAssemblyIdentityFromFile);  
    }  
  
    if (SUCCEEDED(hr)) {  
        hr = GetRealProcAddress("GetIdentityAuthority",  
                                (VOID **)&g_pfnGetIdentityAuthority);  
    }  
  
    if (!g_pfnGetAssemblyIdentityFromFile ||
        !g_pfnGetIdentityAuthority)  
    {  
        printf("Error: Cannot get required APIs from fusion.dll!\n");  
        goto Exit;  
    }  
  
    bRC = true;  
  
Exit:  
    return bRC;  
}  
  
void Shutdown()  
{  
    if(g_pUnk) {  
        g_pUnk->Release();  
        g_pUnk = NULL;  
    }  
}  
  
void Usage()  
{  
    printf("EnumAssemblyAttributes: A tool to enumerate the identity
            attributes of a given assembly.\n\n");  
    printf("Usage: EnumAssemblyAttributes AssemblyFilePath\n");  
    printf("\n");  
}  
  
int _cdecl wmain(int argc, LPCWSTR argv[])  
{  
    int     iResult = 1;  
    IUnknown                    *pUnk  = NULL;  
    IReferenceIdentity          *pRef  = NULL;  
    HRESULT                     hr     = S_OK;
    IEnumIDENTITY_ATTRIBUTE     *pEnum = NULL;  
    BYTE                        abData[1024];  
    DWORD                       cbAvailable;  
    DWORD                       cbUsed;  
    IDENTITY_ATTRIBUTE_BLOB     *pBlob;  
  
    if(argc != 2) {  
        Usage();  
        goto Exit;  
    }  
  
    if(!Init()) {  
        printf("Failure initializing EnumIdAttr.\n");  
        goto Exit;  
    }  
  
    hr = g_pfnGetAssemblyIdentityFromFile(argv[1],
                            __uuidof(IReferenceIdentity), &pUnk);  
  
    if (FAILED(hr)) {  
        printf("GetAssemblyIdentityFromFile failed with hr = 0x%x",
                hr);  
        goto Exit;  
    }  
  
    hr = pUnk->QueryInterface(__uuidof(IReferenceIdentity),
                              (void**)&pRef);  
    if (FAILED(hr)) {  
        goto Exit;  
    }  
  
    hr = pRef->EnumAttributes(&pEnum);  
    if (FAILED(hr)) {  
        printf("IReferenceIdentity::EnumAttributes failed with hr =
                0x%x", hr);  
        goto Exit;  
    }  
  
    pBlob = (IDENTITY_ATTRIBUTE_BLOB *)(abData);  
    while (1) {  
        cbAvailable = sizeof(abData);  
        hr = pEnum->CurrentIntoBuffer(cbAvailable, abData, &cbUsed);  
        if (FAILED(hr)) {  
            printf("IEnumIDENTITY_ATTRIBUTE::CurrentIntoBuffer failed
                    with hr = 0x%x", hr);  
            goto Exit;  
        }  
  
        if (! cbUsed) {  
            break;  
        }  
  
        LPWSTR pwzNameSpace = (LPWSTR)(abData + pBlob->ofsNamespace);  
        LPWSTR pwzName      = (LPWSTR)(abData + pBlob->ofsName);  
        LPWSTR pwzValue     = (LPWSTR)(abData + pBlob->ofsValue);  
        printf("%ws: %ws = %ws\n", pwzNameSpace, pwzName, pwzValue);  
  
        hr = pEnum->Skip(1);  
        if (FAILED(hr)) {  
            printf("IEnumIDENTITY_ATTRIBUTE::Skip failed with hr =
                    0x%x", hr);  
            goto Exit;  
        }  
    }  
  
    iResult = 0;  
  
Exit:  
  
    Shutdown();  
  
    if (pUnk) {  
        pUnk->Release();  
    }  
  
    if (pRef) {  
        pRef->Release();  
    }  
  
    if (pEnum) {  
        pEnum->Release();  
    }  
  
    return iResult;  
}  
```  
  
### <a name="to-run-the-sample"></a><span data-ttu-id="a3591-124">Per eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="a3591-124">To run the sample</span></span>  
 <span data-ttu-id="a3591-125">C:\\> EnumAssemblyAttributes.exe C:\WINDOWS\Microsoft.NET\Framework\v2.0.50727\System.dll</span><span class="sxs-lookup"><span data-stu-id="a3591-125">C:\\> EnumAssemblyAttributes.exe C:\WINDOWS\Microsoft.NET\Framework\v2.0.50727\System.dll</span></span>  
  
### <a name="sample-output"></a><span data-ttu-id="a3591-126">Output di esempio</span><span class="sxs-lookup"><span data-stu-id="a3591-126">Sample output</span></span>  
 <span data-ttu-id="a3591-127">Cultura e neutro</span><span class="sxs-lookup"><span data-stu-id="a3591-127">Culture = neutral</span></span>  
  
 <span data-ttu-id="a3591-128">nome - Sistema</span><span class="sxs-lookup"><span data-stu-id="a3591-128">name = System</span></span>  
  
 <span data-ttu-id="a3591-129">processorArchitecture - MSIL</span><span class="sxs-lookup"><span data-stu-id="a3591-129">processorArchitecture = MSIL</span></span>  
  
 <span data-ttu-id="a3591-130">Token Ditasti PubbliciO - b77a5c561934e089</span><span class="sxs-lookup"><span data-stu-id="a3591-130">PublicKeyToken = b77a5c561934e089</span></span>  
  
 <span data-ttu-id="a3591-131">Versione 2.0.0.0</span><span class="sxs-lookup"><span data-stu-id="a3591-131">Version = 2.0.0.0</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a3591-132">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a3591-132">Requirements</span></span>  
 <span data-ttu-id="a3591-133">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a3591-133">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a3591-134">**Intestazione:** Isolation.h</span><span class="sxs-lookup"><span data-stu-id="a3591-134">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="a3591-135">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a3591-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3591-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a3591-136">See also</span></span>

- [<span data-ttu-id="a3591-137">Interfaccia IReferenceIdentity</span><span class="sxs-lookup"><span data-stu-id="a3591-137">IReferenceIdentity Interface</span></span>](ireferenceidentity-interface.md)
- [<span data-ttu-id="a3591-138">Interfaccia IEnumIDENTITY_ATTRIBUTE</span><span class="sxs-lookup"><span data-stu-id="a3591-138">IEnumIDENTITY_ATTRIBUTE Interface</span></span>](ienumidentity-attribute-interface.md)
- [<span data-ttu-id="a3591-139">Struttura IDENTITY_ATTRIBUTE</span><span class="sxs-lookup"><span data-stu-id="a3591-139">IDENTITY_ATTRIBUTE Structure</span></span>](identity-attribute-structure.md)
- [<span data-ttu-id="a3591-140">Strutture Fusion</span><span class="sxs-lookup"><span data-stu-id="a3591-140">Fusion Structures</span></span>](fusion-structures.md)

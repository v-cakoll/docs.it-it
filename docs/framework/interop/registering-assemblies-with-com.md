---
title: Registrazione di assembly presso COM
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- COM interop, registering assemblies
- unregistering assemblies
- interoperation with unmanaged code, registering assemblies
- registering assemblies
ms.assetid: 87925795-a3ae-4833-b138-125413478551
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c04511772e83129be8042ba5758dc647f82243c5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="registering-assemblies-with-com"></a><span data-ttu-id="d2db1-102">Registrazione di assembly presso COM</span><span class="sxs-lookup"><span data-stu-id="d2db1-102">Registering Assemblies with COM</span></span>
<span data-ttu-id="d2db1-103">È possibile eseguire uno strumento da riga di comando denominato [Assembly Registration Tool (Regasm.exe)](../../../docs/framework/tools/regasm-exe-assembly-registration-tool.md) per registrare o annullare la registrazione di un assembly per l'uso con COM.</span><span class="sxs-lookup"><span data-stu-id="d2db1-103">You can run a command-line tool called the [Assembly Registration Tool (Regasm.exe)](../../../docs/framework/tools/regasm-exe-assembly-registration-tool.md) to register or unregister an assembly for use with COM.</span></span> <span data-ttu-id="d2db1-104">Regasm.exe aggiunge informazioni sulla classe al Registro di sistema, così che i client COM possano usare la classe di .NET Framework in modo trasparente.</span><span class="sxs-lookup"><span data-stu-id="d2db1-104">Regasm.exe adds information about the class to the system registry so COM clients can use the .NET Framework class transparently.</span></span> <span data-ttu-id="d2db1-105">La classe <xref:System.Runtime.InteropServices.RegistrationServices> fornisce funzionalità equivalenti.</span><span class="sxs-lookup"><span data-stu-id="d2db1-105">The <xref:System.Runtime.InteropServices.RegistrationServices> class provides the equivalent functionality.</span></span>  
  
 <span data-ttu-id="d2db1-106">Un componente gestito deve essere registrato nel Registro di sistema di Windows per poter essere attivato da un client COM.</span><span class="sxs-lookup"><span data-stu-id="d2db1-106">A managed component must be registered in the Windows registry before it can be activated from a COM client.</span></span> <span data-ttu-id="d2db1-107">La tabella seguente mostra le chiavi che Regasm.exe aggiunge in genere al Registro di sistema di Windows.</span><span class="sxs-lookup"><span data-stu-id="d2db1-107">The following table shows the keys that Regasm.exe typically adds to the Windows registry.</span></span> <span data-ttu-id="d2db1-108">000000 indica il valore GUID effettivo.</span><span class="sxs-lookup"><span data-stu-id="d2db1-108">(000000 indicates the actual GUID value.)</span></span>  
  
|<span data-ttu-id="d2db1-109">GUID</span><span class="sxs-lookup"><span data-stu-id="d2db1-109">GUID</span></span>|<span data-ttu-id="d2db1-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d2db1-110">Description</span></span>|<span data-ttu-id="d2db1-111">Chiave del Registro di sistema</span><span class="sxs-lookup"><span data-stu-id="d2db1-111">Registry key</span></span>|  
|----------|-----------------|------------------|  
|<span data-ttu-id="d2db1-112">CLSID</span><span class="sxs-lookup"><span data-stu-id="d2db1-112">CLSID</span></span>|<span data-ttu-id="d2db1-113">Identificatore di classe</span><span class="sxs-lookup"><span data-stu-id="d2db1-113">Class identifier</span></span>|<span data-ttu-id="d2db1-114">HKEY_CLASSES_ROOT\CLSID\\{000…000}</span><span class="sxs-lookup"><span data-stu-id="d2db1-114">HKEY_CLASSES_ROOT\CLSID\\{000…000}</span></span>|  
|<span data-ttu-id="d2db1-115">IID</span><span class="sxs-lookup"><span data-stu-id="d2db1-115">IID</span></span>|<span data-ttu-id="d2db1-116">Identificatore di interfaccia</span><span class="sxs-lookup"><span data-stu-id="d2db1-116">Interface identifier</span></span>|<span data-ttu-id="d2db1-117">HKEY_CLASSES_ROOT\Interface\\{000…000}</span><span class="sxs-lookup"><span data-stu-id="d2db1-117">HKEY_CLASSES_ROOT\Interface\\{000…000}</span></span>|  
|<span data-ttu-id="d2db1-118">LIBID</span><span class="sxs-lookup"><span data-stu-id="d2db1-118">LIBID</span></span>|<span data-ttu-id="d2db1-119">Identificatore di libreria</span><span class="sxs-lookup"><span data-stu-id="d2db1-119">Library identifier</span></span>|<span data-ttu-id="d2db1-120">HKEY_CLASSES_ROOT\TypeLib\\{000…000}</span><span class="sxs-lookup"><span data-stu-id="d2db1-120">HKEY_CLASSES_ROOT\TypeLib\\{000…000}</span></span>|  
|<span data-ttu-id="d2db1-121">ProgID</span><span class="sxs-lookup"><span data-stu-id="d2db1-121">ProgID</span></span>|<span data-ttu-id="d2db1-122">Identificatore a livello di codice</span><span class="sxs-lookup"><span data-stu-id="d2db1-122">Programmatic identifier</span></span>|<span data-ttu-id="d2db1-123">HKEY_CLASSES_ROOT\000…000</span><span class="sxs-lookup"><span data-stu-id="d2db1-123">HKEY_CLASSES_ROOT\000…000</span></span>|  
  
 <span data-ttu-id="d2db1-124">Nella chiave HKCR\CLSID\\{0000…0000} il valore predefinito viene impostato sull'oggetto ProgID della classe e vengono aggiunti due valori denominati, Class e Assembly.</span><span class="sxs-lookup"><span data-stu-id="d2db1-124">Under the HKCR\CLSID\\{0000…0000} key, the default value is set to the ProgID of the class, and two new named values, Class and Assembly, are added.</span></span> <span data-ttu-id="d2db1-125">Il runtime legge il valore di Assembly dal Registro di sistema e lo passa al resolver di assembly di runtime.</span><span class="sxs-lookup"><span data-stu-id="d2db1-125">The runtime reads the Assembly value from the registry and passes it on to the runtime assembly resolver.</span></span> <span data-ttu-id="d2db1-126">Il resolver di assembly cerca di individuare l'assembly, in base alle informazioni sull'assembly come il nome e il numero di versione.</span><span class="sxs-lookup"><span data-stu-id="d2db1-126">The assembly resolver attempts to locate the assembly, based on assembly information such as the name and version number.</span></span> <span data-ttu-id="d2db1-127">Affinché il resolver possa individuare un assembly, l'assembly deve trovarsi in una delle posizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="d2db1-127">For the assembly resolver to locate an assembly, the assembly has to be in one of the following locations:</span></span>  
  
-   <span data-ttu-id="d2db1-128">Global Assembly Cache (l'assembly deve avere un nome sicuro).</span><span class="sxs-lookup"><span data-stu-id="d2db1-128">The global assembly cache (must be a strong-named assembly).</span></span>  
  
-   <span data-ttu-id="d2db1-129">Directory dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="d2db1-129">In the application directory.</span></span> <span data-ttu-id="d2db1-130">Gli assembly caricati dal percorso dell'applicazione sono accessibili solo da tale applicazione.</span><span class="sxs-lookup"><span data-stu-id="d2db1-130">Assemblies loaded from the application path are only accessible from that application.</span></span>  
  
-   <span data-ttu-id="d2db1-131">Percorso specificato con l'opzione **/codebase** in Regasm.exe.</span><span class="sxs-lookup"><span data-stu-id="d2db1-131">Along an file path specified with the **/codebase** option to Regasm.exe.</span></span>  
  
 <span data-ttu-id="d2db1-132">Regasm.exe crea anche la chiave InProcServer32 nella chiave HKCR\CLSID\\{0000…0000}.</span><span class="sxs-lookup"><span data-stu-id="d2db1-132">Regasm.exe also creates the InProcServer32 key under the HKCR\CLSID\\{0000…0000} key.</span></span> <span data-ttu-id="d2db1-133">Il valore predefinito per la chiave è impostato sul nome della DLL che inizializza Common Language Runtime (Mscoree.dll).</span><span class="sxs-lookup"><span data-stu-id="d2db1-133">The default value for the key is set to the name of the DLL that initializes the common language runtime (Mscoree.dll).</span></span>  
  
## <a name="examining-registry-entries"></a><span data-ttu-id="d2db1-134">Esame delle voci del Registro di sistema</span><span class="sxs-lookup"><span data-stu-id="d2db1-134">Examining Registry Entries</span></span>  
 <span data-ttu-id="d2db1-135">L'interoperabilità COM fornisce un'implementazione di class factory standard per creare un'istanza di qualsiasi classe .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d2db1-135">COM interop provides a standard class factory implementation to create an instance of any .NET Framework class.</span></span> <span data-ttu-id="d2db1-136">I client possono chiamare **DllGetClassObject** sulla DLL gestita per ottenere una class factory e creare oggetti, esattamente come accade con qualsiasi altro componente COM.</span><span class="sxs-lookup"><span data-stu-id="d2db1-136">Clients can call **DllGetClassObject** on the managed DLL to get a class factory and create objects, just as they would with any other COM component.</span></span>  
  
 <span data-ttu-id="d2db1-137">Per la sottochiave `InprocServer32`, viene visualizzato un riferimento a Mscoree.dll al posto di una libreria dei tipi COM tradizionale per indicare che Common Language Runtime crea l'oggetto gestito.</span><span class="sxs-lookup"><span data-stu-id="d2db1-137">For the `InprocServer32` subkey, a reference to Mscoree.dll appears in place of a traditional COM type library to indicate that the common language runtime creates the managed object.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2db1-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d2db1-138">See Also</span></span>  
 [<span data-ttu-id="d2db1-139">Esposizione di componenti .NET Framework a COM</span><span class="sxs-lookup"><span data-stu-id="d2db1-139">Exposing .NET Framework Components to COM</span></span>](../../../docs/framework/interop/exposing-dotnet-components-to-com.md)  
 [<span data-ttu-id="d2db1-140">Procedura: fare riferimento a tipi .NET da COM</span><span class="sxs-lookup"><span data-stu-id="d2db1-140">How to: Reference .NET Types from COM</span></span>](../../../docs/framework/interop/how-to-reference-net-types-from-com.md)  
 [<span data-ttu-id="d2db1-141">La chiamata a un oggetto .NET</span><span class="sxs-lookup"><span data-stu-id="d2db1-141">Calling a .NET Object</span></span>](http://msdn.microsoft.com/en-us/40c9626c-aea6-4bad-b8f0-c1de462efd33)  
 [<span data-ttu-id="d2db1-142">Distribuzione di un'applicazione per l'accesso COM</span><span class="sxs-lookup"><span data-stu-id="d2db1-142">Deploying an Application for COM Access</span></span>](http://msdn.microsoft.com/en-us/fb63564c-c1b9-4655-a094-a235625882ce)

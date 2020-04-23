---
title: 'Procedura: generare assembly di interoperabilità tramite Tlbimp.exe'
ms.date: 03/30/2017
helpviewer_keywords:
- primary interop assemblies, generating
- Tlbimp.exe
- Type Library Importer
ms.assetid: 5419011c-6e57-40f6-8c65-386db8f7a651
ms.openlocfilehash: e46295b89b042452cb6e303302a8b88d68d58426
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123915"
---
# <a name="how-to-generate-primary-interop-assemblies-using-tlbimpexe"></a><span data-ttu-id="dc55b-102">Procedura: generare assembly di interoperabilità tramite Tlbimp.exe</span><span class="sxs-lookup"><span data-stu-id="dc55b-102">How to: Generate Primary Interop Assemblies Using Tlbimp.exe</span></span>

<span data-ttu-id="dc55b-103">È possibile generare un assembly di interoperabilità primario in due modi:</span><span class="sxs-lookup"><span data-stu-id="dc55b-103">There are two ways to generate a primary interop assembly:</span></span>

- <span data-ttu-id="dc55b-104">Usando l'[Utilità di importazione della libreria dei tipi (Tlbimp.exe)](../tools/tlbimp-exe-type-library-importer.md) fornita da Windows SDK.</span><span class="sxs-lookup"><span data-stu-id="dc55b-104">Using the [Type Library Importer (Tlbimp.exe)](../tools/tlbimp-exe-type-library-importer.md) provided by the Windows SDK.</span></span>

  <span data-ttu-id="dc55b-105">Il modo più semplice per produrre assembly di interoperabilità primari consiste nell'usare [Tlbimp.exe (utilità di importazione della libreria dei tipi)](../tools/tlbimp-exe-type-library-importer.md).</span><span class="sxs-lookup"><span data-stu-id="dc55b-105">The most straightforward way to produce primary interop assemblies is to use the [Tlbimp.exe (Type Library Importer)](../tools/tlbimp-exe-type-library-importer.md).</span></span> <span data-ttu-id="dc55b-106">Tlbimp.exe fornisce le misure di sicurezza seguenti:</span><span class="sxs-lookup"><span data-stu-id="dc55b-106">Tlbimp.exe provides the following safeguards:</span></span>

  - <span data-ttu-id="dc55b-107">Verifica di altri assembly di interoperabilità primari registrati prima della creazione di nuovi assembly di interoperabilità per eventuali riferimenti annidati alla libreria dei tipi.</span><span class="sxs-lookup"><span data-stu-id="dc55b-107">Checks for other registered primary interop assemblies before creating new interop assemblies for any nested type library references.</span></span>

  - <span data-ttu-id="dc55b-108">Nessuna generazione di assembly di interoperabilità primari se non viene specificato il nome del contenitore o del file, in modo da assegnare all'assembly di interoperabilità primario un nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="dc55b-108">Fails to emit the primary interop assembly if you do not specify either the container or file name to give the primary interop assembly a strong name.</span></span>

  - <span data-ttu-id="dc55b-109">Nessuna generazione di assembly di interoperabilità primari se vengono omessi i riferimenti agli assembly dipendenti.</span><span class="sxs-lookup"><span data-stu-id="dc55b-109">Fails to emit a primary interop assembly if you omit references to dependent assemblies.</span></span>

  - <span data-ttu-id="dc55b-110">Nessuna generazione di assembly di interoperabilità primari se vengono aggiunti riferimenti ad assembly dipendenti che non sono assembly di interoperabilità primari.</span><span class="sxs-lookup"><span data-stu-id="dc55b-110">Fails to emit a primary interop assembly if you add references to dependent assemblies that are not primary interop assemblies.</span></span>

- <span data-ttu-id="dc55b-111">Creazione manuale di assembly di interoperabilità primari nel codice sorgente mediante un linguaggio conforme con la specifica CLS (Common Language Specification), ad esempio C#.</span><span class="sxs-lookup"><span data-stu-id="dc55b-111">Creating primary interop assemblies manually in source code by using a language that is compliant with the Common Language Specification (CLS), such as C#.</span></span> <span data-ttu-id="dc55b-112">Questo approccio è utile quando non è disponibile una libreria dei tipi.</span><span class="sxs-lookup"><span data-stu-id="dc55b-112">This approach is useful when a type library is unavailable.</span></span>

<span data-ttu-id="dc55b-113">Per firmare l'assembly con un nome sicuro, è necessario disporre di una coppia di chiavi crittografiche.</span><span class="sxs-lookup"><span data-stu-id="dc55b-113">You must have a cryptographic key pair to sign the assembly with a strong name.</span></span> <span data-ttu-id="dc55b-114">Per informazioni dettagliate, vedere [Creazione di una coppia di chiavi](../../standard/assembly/create-public-private-key-pair.md).</span><span class="sxs-lookup"><span data-stu-id="dc55b-114">For details, see [Creating A Key Pair](../../standard/assembly/create-public-private-key-pair.md).</span></span>

### <a name="to-generate-a-primary-interop-assembly-using-tlbimpexe"></a><span data-ttu-id="dc55b-115">Per generare un assembly di interoperabilità primario tramite Tlbimp.exe</span><span class="sxs-lookup"><span data-stu-id="dc55b-115">To generate a primary interop assembly using Tlbimp.exe</span></span>

1. <span data-ttu-id="dc55b-116">Al prompt dei comandi digitare:</span><span class="sxs-lookup"><span data-stu-id="dc55b-116">At the command prompt, type:</span></span>

    <span data-ttu-id="dc55b-117">**tlbimp** *filetbl*  **/primary /keyfile:** *nomefile* **/out:** *nomeassembly*</span><span class="sxs-lookup"><span data-stu-id="dc55b-117">**tlbimp** *tlbfile*  **/primary /keyfile:** *filename* **/out:** *assemblyname*</span></span>

    <span data-ttu-id="dc55b-118">In questo comando *filetlb* è il file che include la libreria dei tipi COM, *nomefile* è il nome del contenitore o del file che include la coppia di chiavi e *nomeassembly* è il nome dell'assembly da firmare con un nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="dc55b-118">In this command, *tlbfile* is the file containing the COM type library, *filename* is the name of the container or file that contains the key pair, and *assemblyname* is the name of the assembly to sign with a strong name.</span></span>

<span data-ttu-id="dc55b-119">Gli assembly di interoperabilità primari possono fare riferimento solo ad altri assembly di interoperabilità primari.</span><span class="sxs-lookup"><span data-stu-id="dc55b-119">Primary interop assemblies can reference only other primary interop assemblies.</span></span> <span data-ttu-id="dc55b-120">Se l'assembly fa riferimento a tipi da una libreria dei tipi COM di terze parti, sarà necessario ottenere un assembly di interoperabilità primario dal server di pubblicazione prima di potere generarne uno.</span><span class="sxs-lookup"><span data-stu-id="dc55b-120">If your assembly references types from a third-party COM type library, you must obtain a primary interop assembly from the publisher before you can generate your primary interop assembly.</span></span> <span data-ttu-id="dc55b-121">Se si è il server di pubblicazione, sarà necessario generare un assembly di interoperabilità primario per la libreria dei tipi dipendente prima di generare l'assembly di interoperabilità primario di riferimento.</span><span class="sxs-lookup"><span data-stu-id="dc55b-121">If you are the publisher, you must generate a primary interop assembly for the dependent type library before generating the referencing primary interop assembly.</span></span>

<span data-ttu-id="dc55b-122">Un assembly di interoperabilità primario dipendente con un numero di versione diverso da quello della libreria dei tipi originali non è rilevabile quando installato nella directory corrente.</span><span class="sxs-lookup"><span data-stu-id="dc55b-122">A dependent primary interop assembly with a version number that differs from that of the original type library is not discoverable when installed in the current directory.</span></span> <span data-ttu-id="dc55b-123">È necessario registrare l'assembly di interoperabilità primario dipendente nel Registro di sistema di Windows oppure usare l'opzione **/reference** per assicurarsi che Tlbimp.exe trovi il file DLL dipendente.</span><span class="sxs-lookup"><span data-stu-id="dc55b-123">You must either register the dependent primary interop assembly in the Windows registry or use the **/reference** option to be sure that Tlbimp.exe finds the dependent DLL.</span></span>

<span data-ttu-id="dc55b-124">È anche possibile eseguire il wrapping di più versioni di una libreria dei tipi.</span><span class="sxs-lookup"><span data-stu-id="dc55b-124">You can also wrap multiple versions of a type library.</span></span> <span data-ttu-id="dc55b-125">Per istruzioni, vedere [Procedura: Eseguire il wrapping di più versioni delle librerie dei tipi](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/1565h6hc(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="dc55b-125">For instructions, see [How to: Wrap Multiple Versions of Type Libraries](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/1565h6hc(v=vs.100)).</span></span>

## <a name="example"></a><span data-ttu-id="dc55b-126">Esempio</span><span class="sxs-lookup"><span data-stu-id="dc55b-126">Example</span></span>

<span data-ttu-id="dc55b-127">L'esempio seguente importa la libreria dei tipi COM `LibUtil.tlb` e firma l'assembly `LibUtil.dll` con un nome sicuro usando il file di chiave `CompanyA.snk`.</span><span class="sxs-lookup"><span data-stu-id="dc55b-127">The following example imports the COM type library `LibUtil.tlb` and signs the assembly `LibUtil.dll` with a strong name using the key file `CompanyA.snk`.</span></span> <span data-ttu-id="dc55b-128">Omettendo un nome di spazio dei nomi specifico, questo esempio produce lo spazio dei nomi predefinito, `LibUtil`.</span><span class="sxs-lookup"><span data-stu-id="dc55b-128">By omitting a specific namespace name, this example produces the default namespace, `LibUtil`.</span></span>

```console
tlbimp LibUtil.tlb /primary /keyfile:CompanyA.snk /out:LibUtil.dll
```

<span data-ttu-id="dc55b-129">Per un nome più descrittivo (in base alle indicazioni di denominazione *NomeFornitore*.*NomeLibreria*), l'esempio seguente esegue l'override del nome del file di assembly e del nome di spazio dei nomi predefiniti.</span><span class="sxs-lookup"><span data-stu-id="dc55b-129">For a more descriptive name (using the *VendorName*.*LibraryName* naming guideline), the following example overrides the default assembly file name and namespace name.</span></span>

```console
tlbimp LibUtil.tlb /primary /keyfile:CompanyA.snk /namespace:CompanyA.LibUtil /out:CompanyA.LibUtil.dll
```

<span data-ttu-id="dc55b-130">L'esempio seguente importa `MyLib.tlb`, che fa riferimento a `CompanyA.LibUtil.dll` e firma l'assembly `CompanyB.MyLib.dll` con un nome sicuro usando il file di chiave `CompanyB.snk`.</span><span class="sxs-lookup"><span data-stu-id="dc55b-130">The following example imports `MyLib.tlb`, which references `CompanyA.LibUtil.dll`, and signs the assembly `CompanyB.MyLib.dll` with a strong name using the key file `CompanyB.snk`.</span></span> <span data-ttu-id="dc55b-131">Lo spazio dei nomi, `CompanyB.MyLib`, esegue l'override del nome di spazio dei nomi predefinito.</span><span class="sxs-lookup"><span data-stu-id="dc55b-131">The namespace, `CompanyB.MyLib`, overrides the default namespace name.</span></span>

```console
tlbimp MyLib.tlb /primary /keyfile:CompanyB.snk /namespace:CompanyB.MyLib /reference:CompanyA.LibUtil.dll /out:CompanyB.MyLib.dll
```

## <a name="see-also"></a><span data-ttu-id="dc55b-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dc55b-132">See also</span></span>

- [<span data-ttu-id="dc55b-133">Procedura: Registrare assembly di interoperabilità primari</span><span class="sxs-lookup"><span data-stu-id="dc55b-133">How to: Register Primary Interop Assemblies</span></span>](how-to-register-primary-interop-assemblies.md)

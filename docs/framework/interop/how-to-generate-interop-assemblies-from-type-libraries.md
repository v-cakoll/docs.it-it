---
title: 'Procedura: Generare assembly di interoperabilità da librerie dei tipi'
description: Genera assembly di interoperabilità da librerie dei tipi. Usare l'utilità di importazione della libreria dei tipi (Tlbimp.exe) per convertire le coclassi e le interfacce da una libreria dei tipi COM ai metadati.
ms.date: 03/30/2017
helpviewer_keywords:
- importing type library
- interop assemblies, generating
- Type Library Importer
- type libraries
- COM interop, importing type library
ms.assetid: 4afd40c3-68f2-41c5-8ec1-4951bc148b9c
ms.openlocfilehash: 6f54875d6aadb1da18cf25a1bec0a0e451f4a24c
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85619559"
---
# <a name="how-to-generate-interop-assemblies-from-type-libraries"></a><span data-ttu-id="36528-104">Procedura: Generare assembly di interoperabilità da librerie dei tipi</span><span class="sxs-lookup"><span data-stu-id="36528-104">How to: Generate Interop Assemblies from Type Libraries</span></span>
<span data-ttu-id="36528-105">[Tlbimp.exe (utilità di importazione della libreria dei tipi)](../tools/tlbimp-exe-type-library-importer.md) è uno strumento da riga di comando che converte in metadati le coclassi e le interfacce contenute in una libreria dei tipi COM.</span><span class="sxs-lookup"><span data-stu-id="36528-105">The [Type Library Importer (Tlbimp.exe)](../tools/tlbimp-exe-type-library-importer.md) is a command-line tool that converts the coclasses and interfaces contained in a COM type library to metadata.</span></span> <span data-ttu-id="36528-106">Questo strumento crea automaticamente un assembly di interoperabilità e lo spazio dei nomi per le informazioni sui tipi.</span><span class="sxs-lookup"><span data-stu-id="36528-106">This tool creates an interop assembly and namespace for the type information automatically.</span></span> <span data-ttu-id="36528-107">Dopo che i metadati di una classe sono disponibili, i client gestiti possono creare istanze del tipo COM e chiamarne i metodi, come se si trattasse di un'istanza di .NET.</span><span class="sxs-lookup"><span data-stu-id="36528-107">After the metadata of a class is available, managed clients can create instances of the COM type and call its methods, just as if it were a .NET instance.</span></span> <span data-ttu-id="36528-108">Tlbimp.exe converte un'intera libreria dei tipi in metadati in una sola operazione e non può generare informazioni sui tipi per un subset dei tipi definiti in una libreria dei tipi.</span><span class="sxs-lookup"><span data-stu-id="36528-108">Tlbimp.exe converts an entire type library to metadata at once and cannot generate type information for a subset of the types defined in a type library.</span></span>  
  
### <a name="to-generate-an-interop-assembly-from-a-type-library"></a><span data-ttu-id="36528-109">Per generare un assembly di interoperabilità da una libreria dei tipi</span><span class="sxs-lookup"><span data-stu-id="36528-109">To generate an interop assembly from a type library</span></span>  
  
1. <span data-ttu-id="36528-110">Usare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="36528-110">Use the following command:</span></span>  
  
     <span data-ttu-id="36528-111">**Tlbimp**\<*type-library-file*></span><span class="sxs-lookup"><span data-stu-id="36528-111">**tlbimp** \<*type-library-file*></span></span>  
  
     <span data-ttu-id="36528-112">L'aggiunta dell'opzione **/out:** produce un assembly di interoperabilità con un nome modificato, ad esempio LOANLib.dll.</span><span class="sxs-lookup"><span data-stu-id="36528-112">Adding the **/out:** switch produces an interop assembly with an altered name, such as LOANLib.dll.</span></span> <span data-ttu-id="36528-113">La modifica del nome di assembly di interoperabilità può essere utile per distinguerlo dalla DLL COM originale e impedire che si verifichino problemi a causa di nomi duplicati.</span><span class="sxs-lookup"><span data-stu-id="36528-113">Altering the interop assembly name can help distinguish it from the original COM DLL and prevent problems that can occur from having duplicate names.</span></span>  
  
## <a name="example"></a><span data-ttu-id="36528-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="36528-114">Example</span></span>  
 <span data-ttu-id="36528-115">Il comando seguente produce l'assembly Loanlib.dll nello spazio dei nomi `Loanlib`.</span><span class="sxs-lookup"><span data-stu-id="36528-115">The following command produces the Loanlib.dll assembly in the `Loanlib` namespace.</span></span>  
  
```console  
tlbimp Loanlib.tlb  
```  
  
 <span data-ttu-id="36528-116">Il comando seguente produce un assembly di interoperabilità con un nome modificato (LOANLib.dll).</span><span class="sxs-lookup"><span data-stu-id="36528-116">The following command produces an interop assembly with an altered name (LOANLib.dll).</span></span>  
  
```console  
tlbimp LoanLib.tlb /out: LOANLib.dll  
```  
  
## <a name="see-also"></a><span data-ttu-id="36528-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="36528-117">See also</span></span>

- [<span data-ttu-id="36528-118">Importazione di una libreria dei tipi come assembly</span><span class="sxs-lookup"><span data-stu-id="36528-118">Importing a Type Library as an Assembly</span></span>](importing-a-type-library-as-an-assembly.md)
- [<span data-ttu-id="36528-119">Esposizione di componenti COM a .NET Framework</span><span class="sxs-lookup"><span data-stu-id="36528-119">Exposing COM Components to the .NET Framework</span></span>](exposing-com-components.md)

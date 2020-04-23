---
title: 'Procedura: generare assembly di interoperabilità da librerie dei tipi'
ms.date: 03/30/2017
helpviewer_keywords:
- importing type library
- interop assemblies, generating
- Type Library Importer
- type libraries
- COM interop, importing type library
ms.assetid: 4afd40c3-68f2-41c5-8ec1-4951bc148b9c
ms.openlocfilehash: f4f099dfaf5ff02edd3958d7eab9354ce727a239
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2019
ms.locfileid: "74281794"
---
# <a name="how-to-generate-interop-assemblies-from-type-libraries"></a><span data-ttu-id="8461a-102">Procedura: generare assembly di interoperabilità da librerie dei tipi</span><span class="sxs-lookup"><span data-stu-id="8461a-102">How to: Generate Interop Assemblies from Type Libraries</span></span>
<span data-ttu-id="8461a-103">[Tlbimp.exe (utilità di importazione della libreria dei tipi)](../tools/tlbimp-exe-type-library-importer.md) è uno strumento da riga di comando che converte in metadati le coclassi e le interfacce contenute in una libreria dei tipi COM.</span><span class="sxs-lookup"><span data-stu-id="8461a-103">The [Type Library Importer (Tlbimp.exe)](../tools/tlbimp-exe-type-library-importer.md) is a command-line tool that converts the coclasses and interfaces contained in a COM type library to metadata.</span></span> <span data-ttu-id="8461a-104">Questo strumento crea automaticamente un assembly di interoperabilità e lo spazio dei nomi per le informazioni sui tipi.</span><span class="sxs-lookup"><span data-stu-id="8461a-104">This tool creates an interop assembly and namespace for the type information automatically.</span></span> <span data-ttu-id="8461a-105">Dopo che i metadati di una classe sono disponibili, i client gestiti possono creare istanze del tipo COM e chiamarne i metodi, come se si trattasse di un'istanza di .NET.</span><span class="sxs-lookup"><span data-stu-id="8461a-105">After the metadata of a class is available, managed clients can create instances of the COM type and call its methods, just as if it were a .NET instance.</span></span> <span data-ttu-id="8461a-106">Tlbimp.exe converte un'intera libreria dei tipi in metadati in una sola operazione e non può generare informazioni sui tipi per un subset dei tipi definiti in una libreria dei tipi.</span><span class="sxs-lookup"><span data-stu-id="8461a-106">Tlbimp.exe converts an entire type library to metadata at once and cannot generate type information for a subset of the types defined in a type library.</span></span>  
  
### <a name="to-generate-an-interop-assembly-from-a-type-library"></a><span data-ttu-id="8461a-107">Per generare un assembly di interoperabilità da una libreria dei tipi</span><span class="sxs-lookup"><span data-stu-id="8461a-107">To generate an interop assembly from a type library</span></span>  
  
1. <span data-ttu-id="8461a-108">Usare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="8461a-108">Use the following command:</span></span>  
  
     <span data-ttu-id="8461a-109">**tlbimp** \<*file-libreria-tipi*></span><span class="sxs-lookup"><span data-stu-id="8461a-109">**tlbimp** \<*type-library-file*></span></span>  
  
     <span data-ttu-id="8461a-110">L'aggiunta dell'opzione **/out:** produce un assembly di interoperabilità con un nome modificato, ad esempio LOANLib.dll.</span><span class="sxs-lookup"><span data-stu-id="8461a-110">Adding the **/out:** switch produces an interop assembly with an altered name, such as LOANLib.dll.</span></span> <span data-ttu-id="8461a-111">La modifica del nome di assembly di interoperabilità può essere utile per distinguerlo dalla DLL COM originale e impedire che si verifichino problemi a causa di nomi duplicati.</span><span class="sxs-lookup"><span data-stu-id="8461a-111">Altering the interop assembly name can help distinguish it from the original COM DLL and prevent problems that can occur from having duplicate names.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8461a-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="8461a-112">Example</span></span>  
 <span data-ttu-id="8461a-113">Il comando seguente produce l'assembly Loanlib.dll nello spazio dei nomi `Loanlib`.</span><span class="sxs-lookup"><span data-stu-id="8461a-113">The following command produces the Loanlib.dll assembly in the `Loanlib` namespace.</span></span>  
  
```console  
tlbimp Loanlib.tlb  
```  
  
 <span data-ttu-id="8461a-114">Il comando seguente produce un assembly di interoperabilità con un nome modificato (LOANLib.dll).</span><span class="sxs-lookup"><span data-stu-id="8461a-114">The following command produces an interop assembly with an altered name (LOANLib.dll).</span></span>  
  
```console  
tlbimp LoanLib.tlb /out: LOANLib.dll  
```  
  
## <a name="see-also"></a><span data-ttu-id="8461a-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8461a-115">See also</span></span>

- [<span data-ttu-id="8461a-116">Importazione di una libreria dei tipi come assembly</span><span class="sxs-lookup"><span data-stu-id="8461a-116">Importing a Type Library as an Assembly</span></span>](importing-a-type-library-as-an-assembly.md)
- [<span data-ttu-id="8461a-117">Esposizione di componenti COM a .NET Framework</span><span class="sxs-lookup"><span data-stu-id="8461a-117">Exposing COM Components to the .NET Framework</span></span>](exposing-com-components.md)
